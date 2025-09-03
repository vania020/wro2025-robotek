# Ruwance - WRO 2025<img width="40" alt="robotek" src="https://github.com/user-attachments/assets/bffadef9-b0aa-4810-93ff-13db445ac044" /><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/Flag_of_Peru_%28state%29.svg/1200px-Flag_of_Peru_%28state%29.svg.png" alt="Peru Flag" width="30"/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/fbcddbcc-7a4a-4e44-bd8f-0d2e3b5a059e" alt="Banner Ruwance" width="100%">
</p>

[![Instagram](https://img.shields.io/badge/Instagram-%23FFA500.svg?style=for-the-badge&logo=Instagram&logoColor=white&style=plastic)](https://www.instagram.com/robotekperu/)
[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white&style=plastic)](https://www.youtube.com)
[![Facebook](https://img.shields.io/badge/Facebook-%232B25CF.svg?style=for-the-badge&logo=Facebook&logoColor=white&style=plastic)](https://www.facebook.com/p/Robotek-Per%C3%BA-61566493439700/)


+ Team Name: **Ruwance**
+ Car Name: **Riska**
+ Club Name: **Robotek**
+ Team Members: **Isabella Gonzales & Vania Pachas**

---

*Welcome! 🎉* <br>
We are Team Ruwance, proudly representing Perú at the 2025 World Robot Olympiad! This GitHub repository contains the documentation, code, and full development journey of our autonomous vehicle, designed and built to compete in the Future Engineers Challenge.



# Repository Structure
* `t-photos` team photos (official one and funny one)
* `v-photos` photos of our vehicle (from every side, from top and bottom)
* `video` demonstration video link of the robot in the challenges
* `schemes` Wiring diagram with pins and electronic components
* `src` code of the robotic vehicle system
* `models` 3D printed parts and other chassis pieces 
* `other` Documentation on datasets, and hardware specifications


# Table of Contents
1. [Meet the Team!](#1-meet-the-team)
2. [Vehicle Overview](#2-vehicle-overview)
3. [System Setup](#3-system-setup)
4. [Mobility Management](#4-mobility-management)
5. [Power & Sense Management](#5-power--sense-management)
6. [Obstacle Management](#6-obstacle-management)
7. [Assembly Instructions](#7-assembly-instructions)
8. [Performance Videos](#8-performance-videos)
   
<br>

## 1. Meet the Team!

<table>
  <tr>
    <td width="55%" valign="top">
      <strong>Vania Pachas</strong><br><br>
      <img width="15" alt="pencial" src="https://github.com/user-attachments/assets/cf4faf62-f43d-47b9-8fd1-917cc4955a78" /> <i>Responsible for Mechanical Design & Technical documentation</i><br>
       <img width="15" alt="mail" src="https://www.clipartmax.com/png/full/278-2785632_big-image-mail-icon-png-circle.png" /> vaniaapachas@gmail.com<br>
       <img width="15" alt="location" src="https://github.com/user-attachments/assets/11318a7b-9411-4503-9885-926fe4fb4ffb" /> Lima, Perú<br><br>
      Hi!! I'm Vania, a 17-year-old Peruvian passionate about innovation and STEM education. This is my first time in the WRO, and I'm excited to learn and take on this new challenge! I also love dancing salsa, crocheting, watching romcoms, and I’m a Quantum Computing enthusiast :)<br><br>
   
  <td width="45%" align="center">
    <img src="https://github.com/user-attachments/assets/36a0b27f-ee27-486c-8914-90469e85a03d" alt="Vania"/>
    </td>
  </tr>
  
</table>

<table>
  <tr>
    <td width="55%" valign="top">
      <strong>Isabella Gonzales</strong><br><br>
      <img width="15" alt="pencial" src="https://github.com/user-attachments/assets/cf4faf62-f43d-47b9-8fd1-917cc4955a78" /> <i>Responsible for Electronics and Technical Designer documentation</i><br>
       <img width="15" alt="mail" src="https://www.clipartmax.com/png/full/278-2785632_big-image-mail-icon-png-circle.png" /> isabellamilagros842@gmail.com<br>
       <img width="15" alt="location" src="https://github.com/user-attachments/assets/11318a7b-9411-4503-9885-926fe4fb4ffb" /> Lima, Perú<br><br>
      Hello! My name is Isabella, I'm 16 years old, and I love robotics. I founded Robotek Perú, a club where students can learn robotics and join competitions, and this is my second time at the WRO. My favorite hobbies are singing with my choir, practicing taekwondo, and art. <br><br>
   
  <td width="45%" align="center">
    <img src="https://github.com/user-attachments/assets/07735d5c-00a2-43e7-8e0f-f4cf62ae2247" alt="Isa"/>
    </td>
  </tr>
  
</table>

<br>

> [!NOTE]
> 🤔Why is our team named *Ruwance*?<br><br>
> The name *Ruwance* comes from combining the Quechua word "**ruway**" and the English word "**chance**". Ruway means "to create" or "to do", which really reflects who we are, a team that is always making, building, and experimenting. As students of Robotek from Lima, Peru, we have learned that creativity and resilience are important traits to succeed in and enjoy our robotics journey.

<br>

## 2. Vehicle Overview

<p align="center">
  <img src="https://github.com/user-attachments/assets/105155b6-ddb2-4885-aa63-7e07f1468315" alt="Vehicle Overview" width="100%">
</p>

### **<ins>General Description of the Car</ins>**
Our autonomous vehicle is built to take on both the Open and Obstacle Challenges at the Future Engineers competition. Running on Ubuntu with ROS, it can process information and make decisions in real time. With an Ackermann steering system and a stable chassis, the car handles turns and straightaways smoothly, while a LiDAR sensor is primarily used to detect traffic sign obstacles and adapt the path, helping the vehicle count laps and complete the course efficiently.
<br>

| Front | Left | Right |
| :--: | :--: | :--: | 
| <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="90%" /> | <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> |  <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> | 

| Back  | Top  | Bottom |
| :--: | :--: |:--: |  
| <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="90%" /> | <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> |  <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> | 
> [!NOTE]
> Visit our [`v-photos`](https://github.com/vania020/wro2025-robotek/tree/main/v-photos) folder for more detailed photos of the car 📸🚗

<br>

### **<ins>Versions of the Car</ins>**
Our vehicle has gone through **7 versions** (and since we are always improving, there are still more to come!). It all started with a cardboard prototype, then moved on to acrylic and metal chassis designs, and later, we made personalized adjustments to a HiWonder kit. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
<table>  
  <tr>
    <th width="15%">Version</th>
    <th width="35%">Car Photo</th>
    <th width="50%">Description</th>
  </tr>
  
  <!-- Version 1 -->
  <tr>
    <td align="center">Version N°1</td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/88cb9f71-715d-41d5-8dcd-54870af7fa87" width="300"height="200"/>
    </td>
    <td>
      We built a cardboard prototype to test and understand the Ackermann steering system and wheel movement. This served as a reference to learn about the placement of components and systems.
    </td>
  </tr>

  <!-- Version 2 -->
  <tr>
    <td align="center">Version N°2</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/14afa30d-317e-43f8-b6ef-d63897212c88" width="300" height="200"/>
    </td>
    <td>
      <br>We cut and incorporated an acrylic chassis and designed/3D-printed housing pieces for the camera, Ackermann system, and other components. The Ackermann used a stepper motor, and to perceive its surroundings, the car relied on infrared sensors and a webcam. 
      <br><br>The main controllers were a Raspberry Pi 4 and an Arduino Nano, powered by a power bank and lithium batteries. The car’s movement was driven by a single motor.<br><br> 
    </td>
  </tr>

  <!-- Version 3 -->
  <tr>
    <td align="center">Version N°3</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/5299a922-0fb3-43a8-9a32-9bdbc77225d7" width="300" height="200"/>
    </td>
    <td>
      We replaced the power bank with a smaller one, adjusted component placement into a two-level car system, and installed new wheels. Lithium batteries were replaced with higher-current ones, and the infrared sensors were moved to the front, so the vehicle could make more precise turns.<br>
    </td>
  </tr>

  <!-- Version 4 -->
  <tr>
    <td align="center">Version N°4</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/80568426-a136-48a6-b219-9c05dd3e2584" width="300" height="200"/>
    </td>
    <td>
    <br> We upgraded the chassis to a modified HiWonder Kit and replaced the infrared sensors with a LiDAR for more accurate obstacle detection. The webcam was also switched to a monocular camera. The original car motor was replaced by two encoder motors, adapted with gears to drive a single wheel in compliance with competition guidelines.<br><br>

For the Ackermann steering, we replaced the stepper motor with a servomotor. On top of that, we moved away from the Arduino Nano and began implementing the ROS framework.<br><br>
    </td>
  </tr>

  <!-- Version 5 -->
  <tr>
    <td align="center">Version N°5</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/fe6757a1-3fe5-4b12-b856-bedcc28a5b50" width="300" height="200"/>
    </td>
    <td>
      <br>Our main improvement was the chassis. We joined the two bases by drilling them together and carefully organized the components with the Raspberry Pi inside. The LiDAR was placed on top so nothing would block its view, and we also completed and installed the camera housing.<br><br>
    </td>
  </tr>

  <!-- Version 6 -->
  <tr>
    <td align="center">Version N°6
    </td>
    <td align="center"><img src="https://github.com/user-attachments/assets/7e483e4c-2f35-48e9-8125-00a2123f06a2" width="300" height="200"/>
    </td>
    <td>
      Wheels were changed to adjust the car’s height so the Lidar could detect walls within the 10 cm range (previously it was too high and failed). The housing material was upgraded from PLA to polycarbonate for greater resistance, and the Open Challenge (autonomous 3 rounds driving) was completed.<br><br>
    </td>
  </tr>

  <!-- Version 7 -->
  <tr>
    <td align="center">Version N°7</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/105155b6-ddb2-4885-aa63-7e07f1468315" width="300" height="200"/>
    </td>
    <td>
      <br> Using our HiWonder kit as the base, we designed and cut a completely new, smaller chassis with personalized mounting holes for all components, new housing pieces were created, and the two-motor system was replaced by a single motor on one wheel.<br><br>
    We also moved from a two-level structure to a single-level layout, placing all the components on the same surface to give the Raspberry Pi better airflow and easier access. The car successfully detected and avoided the first traffic signs.<br><br>
    </td>
  </tr>
</table>

<br>

> [!NOTE]
> Visit our [`vehicle-versions`](v-photos/vehicle-versions/README.md) folder to see photos and videos of our car evolution 🔝

<br>

## 3. System Setup

### **<ins>Operating Environment Overview</ins>**
The operating environment of our robotic car is designed as a structure that connects hardware, software, and middleware into a single functional system, shown in the mermaid diagram below:

```mermaid
flowchart LR
    A[Hardware] --> B[Ubuntu]
    B --> C[ROS 2]
    C --> D[Nodes]
```
+ At the base, we have the **hardware**, including sensors such as LiDAR and a camera, along with actuators like motors and servos. All of these devices are controlled by the Raspberry Pi, which acts as the main controller.
+ On top of this runs **Ubuntu 24.04**, which provides the necessary drivers, system libraries, and support for robotics applications.
+ The next layer is **ROS 2 Jazzy**, the middleware that ensures communication between **nodes**.
+ Finally, in the application, we implement our own algorithms for perception, navigation, and control that directly solve the challenges of the competition.<br><br>


### **<ins>Robot Operating System (ROS)</ins>** <img width="50" alt="ROS" src="https://github.com/user-attachments/assets/53574d65-315e-4dfd-a8d9-ffb38e892bab" />
ROS is a framework that connects a robot’s software and hardware, making sensors, motors, and programs work together so the robot can perform tasks smoothly. For this project, we use ROS 2 Jazzy, one of the latest versions of ROS 2. You can find the documentation here:  [ROS 2 Documentation: Jazzy](https://docs.ros.org/en/jazzy/index.html)<br>

Without ROS, everything would have to be written in one long, complicated program that’s hard to manage. We can now divide the system into smaller parts, or nodes, that each do one job, making the system easier to build, fix, and expand.<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/b94b35c9-c47d-48f0-9a54-57789c4cc455" alt="Nodes" width="70%">
</p>

> This is an official animation to better understand how nodes work. Each node does one clear job, like moving wheels or reading sensors, and they talk to each other using topics, services, actions, or parameters.
>  In practice, this is the process:
> 1. Sensors send data to ROS 2 by publishing it on topics.
> 2. Other nodes listen to that data, process it, and decide what the car should do.
> 3. Finally, a controller node sends commands, making the car move accordingly.

<br>

*<ins>Reasons for using ROS</ins>*<br><br>
We use ROS 2 because it helps us clearly organize the car’s programs. Here are some advantages:

+ **Sensor & Actuator Integration:** ROS connects all sensors and actuators in one system, ensuring seamless coordination, providing our autonomous car with continuous information about its surroundings, and optimizing the overall system performance.
+ **Environmental Perception with LiDAR:** By using LiDAR, we obtain precise 360-degree distance data, which is essential for detecting obstacles and walls. ROS packages like `laser_scan_matcher` and `gmapping` help us process this data to create real-time maps of the environment.
+ **Autonomous Navigation and Path Planning:** ROS navigation tools such as `move_base` allow our car to plan optimal routes and adjust them in real-time. This is particularly important for the Obstacle Challenge.
+ **Efficient Simulation and Debugging:** We simulate the car’s behavior in virtual environments like [`Gazebo`](https://gazebosim.org/home) to fine-tune our parameters before implementation. Also, tools like [`RViz`](https://docs.ros.org/en/humble/Tutorials/Intermediate/RViz/RViz-User-Guide/RViz-User-Guide.html) let us visualize sensor data and the car’s status in real-time, making debugging easier.

<br>

### **<ins>Ubuntu</ins>** <img width="60" alt="UBUNTU" src="https://github.com/user-attachments/assets/38f176af-2d07-41f9-bb14-3ef8eb2c0022" />
Ubuntu is a popular, free, open-source operating system based on Linux. It is known for being reliable, flexible, and widely used in both research and industry. In our project, we use Ubuntu 24.04 as the **foundation that runs on the Raspberry Pi**.<br>

*<ins>Role in the System</ins>*<br>
Ubuntu manages the Raspberry Pi’s resources efficiently, ensuring it runs correctly. It provides drivers and compatibility for sensors and external hardware, making integration easier. Ubuntu also allows us to install and run ROS 2 Jazzy and gives us access to important libraries and tools that simplify tasks such as sensor communication and system development.<br>

We use Ubuntu because of its stability and compatibility with ROS 2 Jazzy. Since ROS 2 packages are officially distributed for Ubuntu, using this operating system guarantees that we can easily install and manage the software needed for our car.
<br><br>

### **<ins>Raspberry Pi</ins>** <img width="70" alt="Raspberry" src="https://github.com/user-attachments/assets/6e218c1a-8fe1-47a2-8ae5-1719956508fa" />
The Raspberry Pi is a small computer that works as the brain of our car. It is powerful enough to run Ubuntu, ROS 2, and our algorithms in real time. In our project, we use the Raspberry Pi 5, which you can find here: [Raspberry Pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/)<br>

*<ins>Set up and configuration</ins>*<br>
+ With the [Raspberry Pi Imager](https://www.raspberrypi.com/software/), we flash Ubuntu 24.04 into the microSD card of the Raspberry

| Step 1 | Step 2 | Step 3 | Step 4 |
| :--: | :--: | :--: |  :--: |
| <img src="https://github.com/user-attachments/assets/f6ee9449-517c-443a-aad2-c7a4913f8334"/> | <img src="https://github.com/user-attachments/assets/0990b9f5-a0a7-408b-a90b-2e9086ae6032" /> | <img src="https://github.com/user-attachments/assets/8b716aad-e25b-4ff4-a92a-8e5e1b085319" /> | <img src="https://github.com/user-attachments/assets/c0f70529-b1b9-4ce7-b0c2-3803a02c44db"/> |

+ After that, we configure the basics like Wi-Fi, SSH for remote access, and hostname.
+ And finally, we install ROS 2 Jazzy by following these steps: [Installation Ubuntu (deb packages)](https://www.google.com/url?q=https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html&sa=D&source=docs&ust=1756316032253380&usg=AOvVaw24eBtKhOAoYRVzp4xh2Rkh)



<br><br>
## 4. Mobility Management 

### <ins>**Motors and Powertrain**</ins>
### <ins>**Steering System - Ackermann**</ins>
Our autonomous car uses an Ackermann steering system, controlled by a 15 kg·cm digital servo, which provides precise and stable control for navigation and turns. <br>

The Ackermann steering geometry is designed to reduce tire slip by ensuring that all wheels align as radii of circles that share a common center when the car is turning. This configuration keeps the rear wheels fixed and places the center of rotation along a line extended from the rear axle. To achieve this geometry, the inside front wheel turns at a greater angle than the outside front wheel, allowing smoother and more efficient cornering.


<p align="center">
  <img src="https://github.com/user-attachments/assets/9084a317-b240-41f0-a42a-a9f9108c9fde" alt="Ackermann" width="70%">
</p>

> This is an  animation to better understand the Ackerman Steering system. Credits: @The Automotives By M-KAT




### <ins>**Chassis Design Process**</ins>
### <ins>**3D Printed Parts**</ins>


<br><br>
## 5. Power & Sense Management 

### <ins>**Power Source**</ins>
### <ins>**LIDAR & Additional Sensors Integration**</ins>
### **<ins>BOM (Bill of Materials)</ins>**
| Component | Quantity | Description | Image |
|-----------|----------|-------------|-------|
| Raspberry Pi 5 | 1 | Main processing unit for running **ROS**. Acts as the main brain and the Host Controller of the system, capable of running operating systems and handling complex processing tasks. | <img width="800" alt="Raspberry Pi 5" src="https://github.com/user-attachments/assets/ee89c342-6957-4551-b429-e7731c2a28df" /> |
| Low-profile Plus Cooler for Raspberry Pi 5 | 1 | Keeps the Raspberry Pi 5 at optimal temperature during heavy processing. | <img width="800" alt="Cooler" src="https://github.com/user-attachments/assets/d8217edc-ebfc-4288-bd3b-4651305057c0" /> |
| RRC Lite Controller | 1 | Integrates: ROS expansion board, High-Frequency PID Control, Motor Closed-Loop Control, Servo Control and Feedback, IMU Data Acquisition, Power Status Monitoring, and a Power Switch. | <img width="800" alt="Controller" src="https://github.com/user-attachments/assets/929afeb7-4486-4cd3-bb9e-a8a51bd91e83" /> |
| STL-19P TOF Lidar | 1 | Provides precise, 360-degree distance measurements for real-time navigation and obstacle detection in dynamic environments. | <img width="800" alt="Lidar" src="https://github.com/user-attachments/assets/927d47f4-c856-461d-9e6e-ba1c35318990" /> |
| Lidar Adapter Board | 1 | Converts the LiDAR’s UART signals to USB for PC connection and data reading. | <img width="800" alt="Adapter" src="https://github.com/user-attachments/assets/407671ef-bed2-4a04-8aef-0cb69cab464a" /> |
| 15 kg.cm Digital Servo | 1 | Provides accurate steering control. | <img width="800" alt="Servo" src="https://github.com/user-attachments/assets/b949c033-fc6d-4032-8d41-b136ea6ddc90" /> |
| 65 mm Anti-Slip Rubber Wheel | 1 | High-grip wheels to improve traction and stability. | <img width="800" alt="Wheel" src="https://github.com/user-attachments/assets/3f50620d-b008-4426-86f5-2c4f5ee6aff6" /> |
| 25MM Metal Gear Motor | 1 | Core drive motors for powering the wheels with torque and speed. | <img width="800" alt="Motor" src="https://github.com/user-attachments/assets/de6786ac-3dc2-4d36-89e3-03435708c338" /> |
| Monocular Camera | 1 | A camera used for capturing images and videos, can be used for computer vision or live streaming. | <img width="800" alt="Camera" src="https://github.com/user-attachments/assets/c0966a05-8bad-4da5-b012-cc7dbcc65617" /> |
| L298N Motor Driver | 1 | Controls motor direction and speed from the Raspberry Pi. | <img width="800" alt="Motor Driver" src="https://github.com/user-attachments/assets/3ab3c2e0-8b73-4996-9412-b28877301502" /> |
| Jumper Cables | 4–8 | Electrical connections between the motor driver and Pi. | <img width="800" alt="Jumper Cables" src="https://github.com/user-attachments/assets/44758ea5-a6b2-4366-a1fb-7a0eeac5135b" /> |
| USB-USB Cable | 1 | A cable to connect the Raspberry Pi to the camera, Lidar, and Controller. | <img width="800" alt="USB Cable" src="https://github.com/user-attachments/assets/e28195ef-1993-4163-a3de-d2299c443eb0" /> |
| Li-Po Battery 7.4 V 2200mAh 20C | 1 | A lithium polymer battery that provides portable, high-density power. | <img width="800" alt="Battery" src="https://github.com/user-attachments/assets/204ea520-4bc6-4757-93e2-d99036c49403" /> |




### <ins>**Wiring Diagram**<ins>


<br><br>
## 6. Obstacle Management 
### <ins>**Autonomous Driving Logic**<ins>
### <ins>**Flow Diagrams**</ins>
### <ins>**Open Challenge**</ins>
### <ins>**Obstacle Challenge**</ins>

<br><br>
## 7. Assembly Instructions 

<br><br>
## 8. Performance Videos 









