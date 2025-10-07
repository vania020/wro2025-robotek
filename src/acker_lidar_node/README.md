# Code Explanation — acker_lidar_node.py

1. Libraries and Initialization
import rclpy
from rclpy.node import Node
from sensor_msgs.msg import LaserScan
from std_msgs.msg import Float32, String
from ros_robot_controller_msgs.msg import SetAckerServoState, ButtonState
import numpy as np
import time


Explanation:
This code imports all the essential ROS 2 and Python libraries:

rclpy – The main ROS 2 client library for Python. It lets us create publishers, subscribers, and timers.

sensor_msgs.msg.LaserScan – Used to receive LiDAR readings.

std_msgs.msg.Float32 and String – Used to send motor velocity and string messages between nodes.

ros_robot_controller_msgs.msg.SetAckerServoState and ButtonState – Custom messages for controlling the steering servo and reading the start button.

numpy – For calculations like averages and filtering LiDAR data.

time – For simple timing operations inside the node.

2. Class Definition and Publishers
class AckerLidarController(Node):
    def __init__(self):
        super().__init__('acker_lidar_node')


Explanation:
We define a ROS 2 node called AckerLidarController, which handles:

Reading LiDAR data.

Running a PID control loop to keep the car centered.

Publishing commands to the servo (for steering) and the motor (for speed).

Then we create publishers:

self.acker_publisher = self.create_publisher(SetAckerServoState, '/ros_robot_controller/acker_servo/set_state', 10)
self.vel_pub = self.create_publisher(Float32, '/motor_vel', 10)


These send:

Servo positions to /ros_robot_controller/acker_servo/set_state

Motor speed (PWM duty cycle) to /motor_vel

3. Subscriptions
self.scan_subscription = self.create_subscription(LaserScan, '/scan', self.scan_callback, 10)
self.button_subscription = self.create_subscription(ButtonState, '/ros_robot_controller/button', self.button_callback, 10)
self.obst_subscription = self.create_subscription(String, '/obstaculos', self.obst_callback, 10)


Explanation:
The node listens to three topics:

/scan → LiDAR readings from the 360° sensor.

/ros_robot_controller/button → The start button on the car.

/obstaculos → Indicates if a “green” or “red” obstacle is detected (used to bias turning).

4. PID Controller Setup
self.Kp = 1000.0
self.Ki = 0.005
self.Kd = 200.0


Explanation:
The PID (Proportional–Integral–Derivative) controller keeps the car centered between the walls.

Kp: reacts to current error.

Ki: corrects long-term drift.

Kd: smooths quick changes.

It calculates how much the servo should turn left or right based on the distance difference from LiDAR.

5. Setpoint Adjustment Based on Obstacles
self.declare_parameter('sp_step', 0.70)
self.sp_step = float(self.get_parameter('sp_step').value)
self.sp_diff = 0.0


Explanation:
The setpoint (sp_diff) shifts slightly when the system detects an obstacle:

If a green obstacle is found → the car moves slightly left.

If a red obstacle is found → the car moves slightly right.

6. Button Activation
def button_callback(self, msg):
    self.button_pressed = True
    self.vel_pub.publish(Float32(data=90.0))


Explanation:
When the start button is pressed, the node activates the car’s motor (starting with a safe initial duty of 90%).

7. Reading LiDAR Data
def scan_callback(self, msg: LaserScan):
    ...
    left_avg = sum(valid_left) / len(valid_left)
    right_avg = sum(valid_right) / len(valid_right)
    self.current_error = (right_avg - left_avg) - self.sp_diff


Explanation:
The LiDAR readings are divided into left and right sections.
The node computes the average distance on each side and finds the error between them:

error = 0 → the car is centered.

error > 0 → too close to the left wall → turn right.

error < 0 → too close to the right wall → turn left.

8. PID Output and Servo Control
def pid_control(self):
    proportional = self.Kp * self.current_error
    self.integral += self.Ki * self.current_error
    derivative = self.Kd * (self.current_error - self.previous_error)
    output = proportional + self.integral + derivative
    self.previous_error = self.current_error
    return output


Explanation:
The PID calculates a control value called output, used to adjust the servo angle.
This ensures the robot follows walls smoothly and remains stable when driving.

9. Control Loop
def control_loop(self):
    if self.button_pressed:
        steering = self.pid_control()
        position = int(self.center_position - steering)
        position = min(max(position, self.min_position), self.max_position)
        self.send_servo_command(position, 0.1)
        self.vel_pub.publish(Float32(data=100.0))


Explanation:
Every 0.1 seconds, this loop runs:

Calculates the new servo position from the PID controller.

Sends the position command to the servo.

Keeps the car moving at a constant speed (100 duty).

If the start button isn’t pressed, the motor stays off.

10. Main Function
def main(args=None):
    rclpy.init(args=args)
    controller = AckerLidarController()
    rclpy.spin(controller)


Explanation:
This is where the ROS 2 node starts running.
It keeps the controller active, continuously processing LiDAR and button inputs, and sending commands to steer and move the car.

✅ Tip: You can add a link at the top of your README like this:

[Back to Top ↑](#ackerlidar_nodepy)
