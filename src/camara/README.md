## Code Explanation — [`camara_node.py`](./camara.py) 

### ✅ **Summary**

This camera node is a **simple real-time color detector** for the robot’s front camera. It identifies **red** and **green** obstacles, filters noise with HSV and morphology, and sends results through `/obstaculos` for the other nodes (like LIDAR or main control) to act on.


---

### **1. Libraries and Imports**

```python
import rclpy
from rclpy.node import Node
from rclpy.qos import QoSProfile, ReliabilityPolicy, HistoryPolicy
from sensor_msgs.msg import Image
from std_msgs.msg import String
from cv_bridge import CvBridge
import cv2
import numpy as np
```

**Explanation:**

* `rclpy` → the main ROS 2 Python client library.
* `Node` → allows us to create ROS 2 nodes.
* `QoSProfile`, `ReliabilityPolicy`, and `HistoryPolicy` → manage how image data is transmitted (best effort, last N frames, etc.).
* `Image` → message type that contains the camera frames.
* `String` → simple message type used to publish obstacle color (“red”, “green”, “free”).
* `CvBridge` → converts ROS images into OpenCV images.
* `cv2` and `numpy` → handle image processing and numeric operations.

---

### **2. Node Definition**

```python
class ColorObstacleDetector(Node):
    """
    Subscribes: /usb_cam/image_raw
    Publishes: /obstaculos  ->  "rojo" | "verde" | "libre"

    - Detects colored obstacles using HSV filters.
    - Keeps last detected color for a short time after losing it.
    """
```

**Explanation:**
This node listens to the camera image feed and classifies what it sees into three categories:

* **red obstacle**
* **green obstacle**
* **free (no obstacle)**

It uses **color segmentation** in the HSV color space and smooths out false detections using several frames in a row.

---

### **3. Initialization and Parameters**

```python
def __init__(self):
    super().__init__('color_obstacle_detector')

    self.declare_parameter('min_area', 1400)
    self.declare_parameter('consecutive_required', 3)
    self.declare_parameter('hold_seconds', 1.0)

    self.min_area = int(self.get_parameter('min_area').value)
    self.consecutive_required = int(self.get_parameter('consecutive_required').value)
    self.hold_seconds = float(self.get_parameter('hold_seconds').value)
```

**Explanation:**

* `min_area`: Minimum pixel area for a color blob to count as an obstacle.
* `consecutive_required`: Number of consecutive frames required to confirm detection (to avoid flicker).
* `hold_seconds`: Keeps the last detected color even if it temporarily disappears.

---

### **4. HSV Color Ranges**

```python
# Green
self.lower_green = np.array([45, 0, 0], dtype=np.uint8)
self.upper_green = np.array([85, 255, 255], dtype=np.uint8)

# Red (two ranges because HSV red wraps around)
self.lower_red1 = np.array([0, 50, 50], dtype=np.uint8)
self.upper_red1 = np.array([8, 255, 255], dtype=np.uint8)
self.lower_red2 = np.array([170, 40, 40], dtype=np.uint8)
self.upper_red2 = np.array([179, 255, 255], dtype=np.uint8)
```

**Explanation:**
These values define how “red” and “green” appear in HSV color space.
The red color is split into **two intervals** because it appears on both ends of the HSV hue circle (0–8 and 170–179).

---

### **5. Subscriptions and Publishers**

```python
self.bridge = CvBridge()

image_qos = QoSProfile(
    reliability=ReliabilityPolicy.BEST_EFFORT,
    history=HistoryPolicy.KEEP_LAST,
    depth=10,
)

self.image_sub = self.create_subscription(
    Image, '/usb_cam/image_raw', self.image_callback, image_qos
)
self.pub = self.create_publisher(String, '/obstaculos', 10)
```

**Explanation:**

* The node **subscribes** to `/usb_cam/image_raw` to get live images from the camera.
* It **publishes** the detection result (`rojo`, `verde`, or `libre`) to `/obstaculos`.
* The QoS settings make sure it only keeps the most recent frames (avoiding lag).

---

### **6. State Variables**

```python
self.green_count = 0
self.red_count = 0
self.last_label = 'libre'
self.last_detect_time = None
```

**Explanation:**

* `green_count` and `red_count` track how many frames a color was seen consecutively.
* `last_label` stores the most recent detected color.
* `last_detect_time` remembers when that color was last seen (for the “hold” effect).

---

### **7. Image Callback**

```python
def image_callback(self, msg: Image):
    try:
        frame = self.bridge.imgmsg_to_cv2(msg, desired_encoding='bgr8')
    except Exception as e:
        self.get_logger().error(f'CvBridge error: {e}')
        return

    hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
```

**Explanation:**
Every time the camera sends a new frame, this function runs.
It converts the ROS image message into an OpenCV image and then into HSV format for easier color detection.

---

### **8. Creating the Color Masks**

```python
mask_green = cv2.inRange(hsv, self.lower_green, self.upper_green)
mask_red = cv2.bitwise_or(
    cv2.inRange(hsv, self.lower_red1, self.upper_red1),
    cv2.inRange(hsv, self.lower_red2, self.upper_red2)
)

kernel = np.ones((7, 7), np.uint8)
mask_green = cv2.morphologyEx(mask_green, cv2.MORPH_OPEN, kernel, iterations=2)
mask_green = cv2.morphologyEx(mask_green, cv2.MORPH_CLOSE, kernel, iterations=2)
mask_red = cv2.morphologyEx(mask_red, cv2.MORPH_OPEN, kernel, iterations=2)
mask_red = cv2.morphologyEx(mask_red, cv2.MORPH_CLOSE, kernel, iterations=2)
```

**Explanation:**

* Creates **binary masks** that highlight only green or red pixels.
* The morphological operations (`OPEN` and `CLOSE`) remove small noise and fill small holes, making detection more stable.

---

### **9. Detecting Color Areas**

```python
green_area = self._max_contour_area(mask_green)
red_area = self._max_contour_area(mask_red)
green_ok = green_area >= self.min_area
red_ok = red_area >= self.min_area
```

**Explanation:**

* Finds the largest blob (contour) of each color.
* Only considers it valid if the area is above `min_area`.
* This prevents false detections from small dots or reflections.

---

### **10. Decision Logic**

```python
self.green_count = self.green_count + 1 if green_ok else 0
self.red_count = self.red_count + 1 if red_ok else 0
g_ready = self.green_count >= self.consecutive_required
r_ready = self.red_count >= self.consecutive_required
```

**Explanation:**
If a color appears several frames in a row, it becomes a confirmed detection.
This prevents false positives caused by lighting changes or fast camera motion.

---

### **11. Publishing the Result**

```python
if g_ready or r_ready:
    if g_ready and r_ready:
        decided_label = 'rojo' if red_area >= green_area else 'verde'
    elif r_ready:
        decided_label = 'rojo'
    else:
        decided_label = 'verde'
    self.last_label = decided_label
    self.last_detect_time = now
else:
    if self.last_detect_time and (now - self.last_detect_time) <= self.hold_seconds:
        decided_label = self.last_label
    else:
        decided_label = 'libre'

self.pub.publish(String(data=decided_label))
self.get_logger().info(f"/obstaculos: {decided_label}  (red={red_area}, green={green_area})")
```

**Explanation:**

* Chooses which color is currently dominant and publishes it.
* If no obstacle is seen but the last detection was recent, it “remembers” that color for a few moments (the **hold time**).
* Publishes the final decision to `/obstaculos`.

---

### **12. Helper Function**

```python
@staticmethod
def _max_contour_area(mask: np.ndarray) -> int:
    contours, _ = cv2.findContours(mask, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
    return 0 if not contours else int(max(cv2.contourArea(c) for c in contours))
```

**Explanation:**
Finds all the shapes (contours) in the binary mask and returns the largest one’s area.

---

### **13. Main Function**

```python
def main(args=None):
    rclpy.init(args=args)
    node = ColorObstacleDetector()
    try:
        rclpy.spin(node)
    except KeyboardInterrupt:
        pass
    finally:
        node.destroy_node()
        rclpy.shutdown()

if __name__ == '__main__':
    main()
```

**Explanation:**
This is the standard entry point in ROS 2.
It initializes the system, starts the node, and keeps it running until you stop it (Ctrl+C).

---

