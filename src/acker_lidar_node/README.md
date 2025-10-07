# Code Explanation — acker_lidar_node.py

---

### **1. Libraries and Constants**

```python
import rclpy
from rclpy.node import Node
from sensor_msgs.msg import LaserScan
from std_msgs.msg import Float32, String
from ros_robot_controller_msgs.msg import SetAckerServoState, ButtonState
import numpy as np
import time
```

**Explanation:**

* Imports the required libraries for the robot’s LIDAR control system.

  * `rclpy`: Main ROS 2 library that manages communication between nodes.
  * `sensor_msgs/LaserScan`: Used to receive LiDAR distance data.
  * `std_msgs/Float32` and `String`: Standard ROS message types for simple values and text.
  * `ros_robot_controller_msgs`: Custom message types to control the steering servo and button input.
  * `numpy`: Used for numerical operations such as calculating averages.
  * `time`: Provides delay and timing functions when needed.

---

### **2. Node and Publishers**

```python
class AckerLidarController(Node):
    def __init__(self):
        super().__init__('acker_lidar_node')
```

**Explanation:**
Defines a ROS 2 node named **`acker_lidar_node`**, responsible for reading LiDAR data, processing it with a PID controller, and sending commands to the robot’s steering and motor.

```python
self.acker_publisher = self.create_publisher(SetAckerServoState, '/ros_robot_controller/acker_servo/set_state', 10)
self.vel_pub = self.create_publisher(Float32, '/motor_vel', 10)
```

**Explanation:**

* Publishes the steering position to **`/ros_robot_controller/acker_servo/set_state`**.
* Publishes motor velocity commands (PWM duty) to **`/motor_vel`**.

---

### **3. Subscriptions**

```python
self.scan_subscription = self.create_subscription(LaserScan, '/scan', self.scan_callback, 10)
self.button_subscription = self.create_subscription(ButtonState, '/ros_robot_controller/button', self.button_callback, 10)
self.obst_subscription = self.create_subscription(String, '/obstaculos', self.obst_callback, 10)
```

**Explanation:**

* **`/scan`**: Receives LiDAR readings.
* **`/ros_robot_controller/button`**: Reads the state of the physical start button.
* **`/obstaculos`**: Indicates the type of obstacle detected (red or green) to adjust the path.

---

### **4. PID Control Constants and Parameters**

```python
self.Kp = 1000.0
self.Ki = 0.005
self.Kd = 200.0
```

**Explanation:**
Defines the constants for the PID controller.

* **Kp** (Proportional): Reacts to the current steering error.
* **Ki** (Integral): Corrects accumulated offset over time.
* **Kd** (Derivative): Stabilizes and smooths motion.

---

### **5. Servo and Setpoint Configuration**

```python
self.center_position = 1500
self.max_position = 2050
self.min_position = 1000
self.declare_parameter('sp_step', 0.70)
self.sp_step = float(self.get_parameter('sp_step').value)
self.sp_diff = 0.0
```

**Explanation:**

* Defines the **servo limits** (minimum, maximum, and center).
* **`sp_step`** defines how much to shift the setpoint when an obstacle is detected.

  * Green obstacle → steer slightly left.
  * Red obstacle → steer slightly right.

---

### **6. Button Callback**

```python
def button_callback(self, msg):
    self.button_pressed = True
    self.vel_pub.publish(Float32(data=90.0))
```

**Explanation:**

* When the physical button is pressed, the robot starts moving.
* Publishes a velocity of **90.0** as the initial speed to the motor.

---

### **7. LiDAR Reading**

```python
def scan_callback(self, msg: LaserScan):
    total_angles = len(msg.ranges)
    left_center = int(total_angles * (240 / 360))
    right_center = int(total_angles * (120 / 360))
```

**Explanation:**

* The LiDAR gives 360° distance readings.
* The code splits them into **left** and **right** zones for comparison.

```python
self.current_error = (right_avg - left_avg) - self.sp_diff
```

**Explanation:**
Calculates how far the robot is from being centered:

* **`error = 0`** → perfectly centered.
* **Positive error** → too close to the left wall → turn right.
* **Negative error** → too close to the right wall → turn left.

---

### **8. PID Control Function**

```python
def pid_control(self):
    proportional = self.Kp * self.current_error
    self.integral += self.Ki * self.current_error
    derivative = self.Kd * (self.current_error - self.previous_error)
    output = proportional + self.integral + derivative
    self.previous_error = self.current_error
    return output
```

**Explanation:**
This function applies the PID algorithm:

* Calculates proportional, integral, and derivative terms.
* Returns the **output**, which represents how much the steering must change to stay centered.

---

### **9. Control Loop**

```python
def control_loop(self):
    if self.button_pressed:
        steering = self.pid_control()
        position = int(self.center_position - steering)
        position = min(max(position, self.min_position), self.max_position)
        self.send_servo_command(position, 0.1)
        self.vel_pub.publish(Float32(data=100.0))
```

**Explanation:**

* Runs every 0.1 seconds.
* Uses the PID result to compute the new steering position.
* Sends the command to the servo motor.
* Keeps the car moving at a constant speed (100%).
* If the button is not pressed, the robot remains stopped.

---

### **10. Main Function**

```python
def main(args=None):
    rclpy.init(args=args)
    controller = AckerLidarController()
    rclpy.spin(controller)
```

**Explanation:**

* Initializes ROS 2.
* Creates an instance of the node.
* Keeps it running so it can continuously read sensors and control the motors until the program ends.

---

### **Summary**

This node uses **LiDAR data** and a **PID controller** to keep the robot centered between walls or obstacles.
It reacts to **red and green signals** by shifting its path slightly left or right.
The car only starts after the **button** is pressed and continuously adjusts steering while moving.
