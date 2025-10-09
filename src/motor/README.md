## Code Explanation — [`motor.py`](./motor.py) 

### ✅ **Summary**

This code creates a motor controller node for ROS 2. It listens to a topic `/motor_vel` where another node sends the desired speed. That number is converted into a PWM signal that the Raspberry Pi sends through a GPIO pin to the motor driver, making the car move faster or slower. When the program ends, it stops the PWM and powers down the motor safely.

---

## 1. Importing Required Libraries

```python
from rclpy.node import Node
from std_msgs.msg import Float32
import lgpio
import time
import threading
import rclpy
```

* `rclpy` and `Node`: allow the creation of a ROS 2 node.
* `Float32`: message type used to receive the motor speed (a decimal number).
* `lgpio`: provides access to the Raspberry Pi’s GPIO pins.
* `threading` and `time`: allow continuous background execution and precise time control.

These imports enable both the ROS 2 communication layer and the low-level GPIO control.

---

## 2. Defining the Node Class

```python
class MotorPWMNode(Node):
    def __init__(self):
        super().__init__('motor_pwm_node')
```

Every ROS 2 component is implemented as a *node*.
Here, a new node called **`motor_pwm_node`** is initialized.
This gives the process an identity in the ROS 2 network so other nodes can communicate with it.

---

## 3. Configuring the PWM Parameters

```python
self.CHIP = 4
self.PWM_PIN = 12  # BCM18 (physical pin 12)
self.freq = 1000   # 1000 Hz
self.period = 1 / self.freq
self.duty = 0.0
```

* **`PWM_PIN`** = GPIO 18 (physical pin 12) is used to output the PWM signal.
* **`freq`** = 1000 Hz → the signal turns ON and OFF one thousand times per second.
* **`period`** = the time length of a single PWM cycle.
* **`duty`** = how long the signal stays ON during each cycle (from 0.0 to 1.0).

A duty of 0 means no power (motor off), while 1.0 means full power.

---

## 4. Initializing the GPIO Output

```python
self.h = lgpio.gpiochip_open(self.CHIP)
lgpio.gpio_claim_output(self.h, self.PWM_PIN)
```

The script opens the GPIO controller and claims the selected pin as an **output**.
This ensures that the pin is ready to send electrical signals rather than receive them.

---

## 5. Subscribing to the `/motor_vel` Topic

```python
self.subscription = self.create_subscription(
    Float32,
    '/motor_vel',
    self.vel_callback,
    10
)
```

The node subscribes to the topic `/motor_vel`, expecting `Float32` messages.
Whenever another ROS 2 node publishes a new speed value, the function **`vel_callback()`** is triggered.
Typical values range between 0 and 100, representing the motor’s desired speed in percent.

---

## 6. Starting a Background Thread

```python
self.running = True
self.pwm_thread = threading.Thread(target=self.pwm_loop)
self.pwm_thread.start()
```

Generating a stable PWM signal requires precise timing.
To avoid blocking ROS 2 communications, the script runs the PWM generation in a **separate thread** (`pwm_loop`).
This allows ROS 2 to continue processing messages while PWM pulses are produced continuously.

---

## 7. Processing Speed Commands

```python
def vel_callback(self, msg):
    self.duty = max(0.0, min(1.0, msg.data / 100.0))
    self.get_logger().info(f"Duty updated: {self.duty * 100:.1f}%")
```

Each time a new message arrives on `/motor_vel`:

1. The numeric value (e.g., 50.0) is converted from 0–100 to a duty cycle between 0.0 and 1.0.
2. The value is limited to prevent out-of-range errors.
3. A short log message confirms the update.

For example, sending `60` on the topic sets the PWM duty cycle to 0.6 (60% power).

---

## 8. Generating the PWM Signal

```python
def pwm_loop(self):
    while self.running:
        if self.duty > 0:
            lgpio.gpio_write(self.h, self.PWM_PIN, 1)
            time.sleep(self.period * self.duty)
            lgpio.gpio_write(self.h, self.PWM_PIN, 0)
            time.sleep(self.period * (1 - self.duty))
        else:
            lgpio.gpio_write(self.h, self.PWM_PIN, 0)
            time.sleep(self.period)
```

This loop runs continuously while the node is active:

* If the motor should move (`duty > 0`), the pin alternates between
  **HIGH** (on) for part of the period and **LOW** (off) for the rest.
* If `duty = 0`, the pin remains LOW, stopping the motor.

The faster this ON/OFF cycle, the smoother the motor speed.

---

## 9. Stopping the Node Safely

```python
def destroy_node(self):
    self.running = False
    self.pwm_thread.join()
    lgpio.gpio_write(self.h, self.PWM_PIN, 0)
    lgpio.gpiochip_close(self.h)
    super().destroy_node()
```

When the node shuts down (for example, when the user presses Ctrl + C):

* The PWM thread stops running.
* The output pin is set LOW so the motor immediately stops.
* The GPIO controller is closed properly.
* The node itself is destroyed.

This prevents the motor from staying active after program termination.

---

## 10. Main Entry Point

```python
def main(args=None):
    rclpy.init(args=args)
    node = MotorPWMNode()
    try:
        rclpy.spin(node)
    except KeyboardInterrupt:
        pass
    finally:
        node.destroy_node()
        rclpy.shutdown()
```

The `main()` function initializes ROS 2, creates the node, and keeps it alive using `rclpy.spin()`.
When the user interrupts execution, it performs a clean shutdown and powers the motor off safely.



This structure allows the Raspberry Pi to control the motor’s speed smoothly and safely while remaining fully integrated with the ROS 2 communication framework.
