## Code Explanation — [`acker_lidar_node.py`](./acker_lidar_node.py) 

### **Summary**

This node uses **LiDAR data** and a **PID controller** to keep the robot centered between walls or obstacles. It reacts to **red and green signals** by shifting its path slightly left or right. The car only starts after the **button** is pressed and continuously adjusts steering while moving.


### 1. Libraries and Initialization

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
This code imports all the essential ROS 2 and Python libraries:

* **rclpy** – The main ROS 2 client library for Python. It lets us create publishers, subscribers, and timers.
* **sensor_msgs.msg.LaserScan** – Used to receive LiDAR readings.
* **std_msgs.msg.Float32 and String** – Allow us to send motor velocity and string messages between nodes.
* **ros_robot_controller_msgs.msg.SetAckerServoState, ButtonState** – Custom messages for controlling the steering servo and reading the start button.
* **numpy** – For calculations like averages and filtering LiDAR data.
* **time** – For simple timing operations inside the node.

---

### 2. Class Definition and Publishers

```python
class AckerLidarController(Node):
    def __init__(self):
        super().__init__('acker_lidar_node')
```

**Explanation:**
Here we define a ROS 2 node called **`AckerLidarController`**, which will handle:

* Reading **LiDAR data**.
* Running a **PID control** loop to keep the car centered.
* Publishing commands to the **servo** (for steering) and the **motor** (for speed).

Then we create **publishers**:

```python
self.acker_publisher = self.create_publisher(SetAckerServoState, '/ros_robot_controller/acker_servo/set_state', 10)
self.vel_pub = self.create_publisher(Float32, '/motor_vel', 10)
```

These send:

* **Servo positions** to `/ros_robot_controller/acker_servo/set_state`
* **Motor speed (PWM duty cycle)** to `/motor_vel`

---

### 3. Subscriptions

```python
self.scan_subscription = self.create_subscription(LaserScan, '/scan', self.scan_callback, 10)
self.button_subscription = self.create_subscription(ButtonState, '/ros_robot_controller/button', self.button_callback, 10)
self.obst_subscription = self.create_subscription(String, '/obstaculos', self.obst_callback, 10)
```

**Explanation:**
The node listens to three topics:

* **`/scan`** → LiDAR readings from the 360° sensor.
* **`/ros_robot_controller/button`** → The start button on the car.
* **`/obstaculos`** → A topic that tells if there’s a “green” or “red” obstacle (used to bias turning).

---

### 4. PID Controller Setup

```python
self.Kp = 1000.0
self.Ki = 0.005
self.Kd = 200.0
```

**Explanation:**
The **PID (Proportional–Integral–Derivative)** controller keeps the car centered between the walls.

* **Kp**: reacts to current error
* **Ki**: corrects long-term drift
* **Kd**: smooths quick changes

It calculates how much the car should turn the servo left or right based on the **distance difference** from LiDAR.

---

### 5. Setpoint Adjustment Based on Obstacles

```python
self.declare_parameter('sp_step', 0.70)
self.sp_step = float(self.get_parameter('sp_step').value)
self.sp_diff = 0.0
```

**Explanation:**
The **setpoint (sp_diff)** shifts slightly when the system detects an obstacle.
If a **green obstacle** is found → the car moves slightly **left**.
If a **red obstacle** is found → the car moves slightly **right**.

---

### 6. Button Activation

```python
def button_callback(self, msg):
    self.button_pressed = True
    self.vel_pub.publish(Float32(data=90.0))
```

**Explanation:**
When the **start button** is pressed, the node activates the car’s motor (starting with a safe initial duty of 90%).

---

### 7. Reading LiDAR Data

```python
def scan_callback(self, msg: LaserScan):
    ...
    left_avg = sum(valid_left) / len(valid_left)
    right_avg = sum(valid_right) / len(valid_right)
    self.current_error = (right_avg - left_avg) - self.sp_diff
```

**Explanation:**
The LiDAR readings are split into **left** and **right** zones.
The node computes the **average distance** on each side and finds the **error** between them.
If `error = 0`, the car is centered.
If `error > 0`, it’s too close to the left wall → turn right.
If `error < 0`, it’s too close to the right wall → turn left.

---

### 8. PID Output and Servo Control

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
The PID calculates a control value called **`output`**, which is used to set the servo angle.
This keeps the robot stable and smooth while following the corridor or avoiding walls.

---

### 9. Control Loop

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
Every 0.1 seconds, the control loop runs:

1. Calculates the new servo position from PID.
2. Sends the command to the servo.
3. Keeps the car moving with a constant speed (100 duty).

If no button is pressed, the car stays stopped.

---

### 10. Main Function

```python
def main(args=None):
    rclpy.init(args=args)
    controller = AckerLidarController()
    rclpy.spin(controller)
```

**Explanation:**
This is where the ROS 2 node actually starts running.
It keeps the controller active, listening to LiDAR and button inputs, and publishing movement commands.

---

