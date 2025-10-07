## Code Explanation — [`motor.py`](./motor.py) 

### ✅ **Summary**

This camera node is a **simple real-time color detector** for the robot’s front camera. It identifies **red** and **green** obstacles, filters noise with HSV and morphology, and sends results through `/obstaculos` for the other nodes (like LIDAR or main control) to act on.


---
