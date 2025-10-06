<img width="1600" height="400" alt="RUWANCE" src="https://github.com/user-attachments/assets/f62e61d4-6ade-4c75-b03e-b109d2be9b4d" /># Ruwance - WRO 2025<img width="40" alt="robotek" src="https://github.com/user-attachments/assets/bffadef9-b0aa-4810-93ff-13db445ac044" /><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/Flag_of_Peru_%28state%29.svg/1200px-Flag_of_Peru_%28state%29.svg.png" alt="Peru Flag" width="30"/>

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
+ Coach: **Anthony Valladolid Ballon**

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
* `other` Extra documentation


# Table of Contents
1. [Meet the Team!](#1-meet-the-team)
   
3. [Vehicle Overview](#2-vehicle-overview)
   + [General Description of the Car](#general-description-of-the-car)
   + [Versions of the Car](#versions-of-the-car)
     
4. [System Setup](#3-system-setup)
   + [Operating Environment Overview](#operating-environment-overview)
   + [ROS](#ros)
   + [Ubuntu](#ubuntu)
   + [Raspberry Pi](#raspberry-pi)
     
5. [Mobility Management](#4-mobility-management)
   + [Steering System - Ackermann](#steering-system-ackermann)
   + [Motor and Drivetrain](#motor-and-drivetrain)
   + [Chassis Design Process](#chassis-design-process)
   + [3D Printed Parts](#3d-printed-parts)
   
6. [Power & Sense Management](#5-power--sense-management)
   + [Power Source](#power-source)
   + [Sensors Integration](#sensors-integration)
   + [BOM (Bill of Materials)](#bom-bill-of-materials)
   + [Wiring Diagram](#wiring-diagram)

7. [Obstacle Management](#6-obstacle-management)
   + [Autonomous Driving Logic](#autonomous-driving-logic)
   + [Open Challenge](#open-challenge)
   + [Obstacle Challenge](#obstacle-challenge)
     
8. [Assembly Instructions](#7-assembly-instructions)
9. [Performance Videos](#8-performance-videos)
   
<br>

# Main Content

## 1. Meet the Team!
<table>
  <tr>
    <td width="55%" valign="top">
      <strong>Vania Pachas</strong><br><br>
      <img width="15" alt="pencial" src="https://github.com/user-attachments/assets/cf4faf62-f43d-47b9-8fd1-917cc4955a78" /> <i>Responsible for Mechanical Design & Technical documentation</i><br>
       <img width="15" alt="mail" src="https://www.clipartmax.com/png/full/278-2785632_big-image-mail-icon-png-circle.png" /> vaniaapachas@gmail.com<br>
       <img width="15" alt="location" src="https://github.com/user-attachments/assets/11318a7b-9411-4503-9885-926fe4fb4ffb" /> Lima, Perú<br><br>
      Hi!! I'm Vania, an 18-year-old Peruvian passionate about innovation and STEM education. This is my first time in the WRO, and I'm excited to learn and take on this new challenge! I also love dancing salsa, crocheting, watching romcoms, and I’m a Quantum Computing enthusiast :)<br><br>
   
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
Our autonomous vehicle is built to take on both the Open and Obstacle Challenges at the Future Engineers competition. Running on Ubuntu with ROS, it can process information and make decisions in real time. The car uses an Ackermann steering system and a custom-built chassis to move smoothly through turns and straight paths. A LiDAR sensor helps it detect the field walls, while the camera identifies traffic signs and obstacles. With this setup, the car can adapt its route, count laps, and complete the course efficiently.
<br>

| Front | Left | Right |
| :--: | :--: | :--: | 
| <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="90%" /> | <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> |  <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> | 

| Back  | Top  | Bottom |
| :--: | :--: |:--: |  
| <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="90%" /> | <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> |  <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> | 
> [!NOTE]
> Visit our [`v-photos`](https://github.com/vania020/wro2025-robotek/tree/main/v-photos) folder for more detailed photos of the car 📸🚗


### **<ins>Versions of the Car</ins>**
Our vehicle has gone through **10 versions** (and since we are always improving, there are still more to come!). It all started with a cardboard prototype, then moved on to acrylic and metal chassis designs, and later, we made personalized adjustments to a HiWonder kit. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
<table>  
  <tr>
    <th width="10%">Version</th>
    <th width="40%">Car Photo</th>
    <th width="50%">Description</th>
  </tr>
  
  <!-- Version 1 -->
  <tr>
    <td align="center"><i>Version N°1</i></td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/88cb9f71-715d-41d5-8dcd-54870af7fa87" width="330"height="230"/>
    </td>
    <td>
      We built a cardboard prototype to test and understand the Ackermann steering system and wheel movement. This served as a reference to learn about the placement of components and systems.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-1">➡️ See more photos 🚗</a>
    </td>
  </tr>

  <!-- Version 2 -->
  <tr>
    <td align="center"><i>Version N°2</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/14afa30d-317e-43f8-b6ef-d63897212c88" width="330" height="230"/>
    </td>
    <td>
      <br>We cut and incorporated an acrylic chassis and designed/3D-printed housing pieces for the camera, Ackermann system, and other components. The Ackermann used a stepper motor, and to perceive its surroundings, the car relied on infrared sensors and a webcam. 
      <br><br>The main controllers were a Raspberry Pi 4 and an Arduino Nano, powered by a power bank and lithium batteries. The car’s movement was driven by a single motor.<br><br> 
      <a href="v-photos/vehicle-versions/README.md#version-2">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

  <!-- Version 3 -->
  <tr>
    <td align="center"><i>Version N°3</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/5299a922-0fb3-43a8-9a32-9bdbc77225d7" width="330" height="230"/>
    </td>
    <td>
      <br> We replaced the power bank with a smaller one, adjusted component placement into a two-level car system, and installed new wheels. Lithium batteries were replaced with higher-current ones, and the infrared sensors were moved to the front, so the vehicle could make more precise turns.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-3">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

  <!-- Version 4 -->
  <tr>
    <td align="center"><i>Version N°4</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/80568426-a136-48a6-b219-9c05dd3e2584" width="330" height="230"/>
    </td>
    <td>
    <br> We upgraded the chassis to a modified HiWonder Kit and replaced the infrared sensors with a LiDAR for more accurate obstacle detection. The webcam was also switched to a monocular camera. The original car motor was replaced by two encoder motors, adapted with gears to drive a single wheel in compliance with competition guidelines.<br><br>

For the Ackermann steering, we replaced the stepper motor with a servomotor. On top of that, we moved away from the Arduino Nano and began implementing the ROS framework.<br><br>
<a href="v-photos/vehicle-versions/README.md#version-4">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

  <!-- Version 5 -->
  <tr>
    <td align="center"><i>Version N°5</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/fe6757a1-3fe5-4b12-b856-bedcc28a5b50" width="330" height="230"/>
    </td>
    <td>
      <br>Our main improvement was the chassis. We joined the two bases by drilling them together and carefully organized the components with the Raspberry Pi inside. The LiDAR was placed on top so nothing would block its view, and we also completed and installed the camera housing.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-5">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

  <!-- Version 6 -->
  <tr>
    <td align="center"><i>Version N°6</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/7e483e4c-2f35-48e9-8125-00a2123f06a2" width="330" height="230"/>
    </td>
    <td>
      <br> Wheels were changed to adjust the car’s height so the Lidar could detect walls within the 10 cm range (previously it was too high and failed). The housing material was upgraded from PLA to polycarbonate for greater resistance, and the Open Challenge (autonomous 3 rounds driving) was completed.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-6">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

  <!-- Version 7 -->
  <tr>
    <td align="center"><i>Version N°7</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/105155b6-ddb2-4885-aa63-7e07f1468315" width="330" height="230"/>
    </td>
    <td>
      <br> Using our HiWonder kit as the base, we designed and cut a completely new, smaller chassis with personalized mounting holes for all components, new housing pieces were created, and the two-motor system was replaced by a single motor in a gear system.<br><br>
    We also moved from a two-level structure to a single-level layout, placing all the components on the same surface to give the Raspberry Pi better airflow and easier access. The car successfully detected and avoided the first traffic signs.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-7">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

  <!-- Version 8 -->
  <tr>
    <td align="center"><i>Version N°8</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/5d66a0cd-a12c-4155-ae6f-aa4655cf6e0e" width="330" height="250"/>
    </td>
    <td>
      <br> <b>Car dimensions:</b> 15 x 23 cm <br><br>
      We 3D-printed new, slimmer front wheels because the original ones stuck out too much from the chassis. A custom housing was also printed for the batteries, and most importantly, the Ackermann steering servo was mounted vertically to save space and allow for a wider turning angle.<br><br>
During previous testing, we realized the LiDAR was struggling to properly detect the walls of the field, so we 3D-printed and implemented a small angled mount to give it a slight tilt.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-8">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>

<!-- Version 9 -->
  <tr>
    <td align="center"><i>Version N°9</i></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/312c2e7e-4638-4917-b54a-fff2bb1a2965" width="330" height="450"/>
    </td>
    <td>
      <br> <b>Car dimensions:</b> 15 x 20 cm <br><br>
In this version, the components were arranged more efficiently to save space. We added a custom housing for the batteries, placed the Pi5 controller on top, and mounted the Raspberry above it, creating a layered system.<br><br>
A new chassis base was printed in MDF, and the Ackermann was moved slightly because, in the previous version, the rack was colliding with the servo. To improve traction, we added a groove to the wheels and printed small cylinders between them to prevent contact with the screws. With these adjustments, the robot managed to complete a lap in <b>20 seconds</b>.<br><br>
      <a href="v-photos/vehicle-versions/README.md#version-9">➡️ See more photos 🚗</a><br><br>
    </td>
  </tr>
  
  
</table>

<br>

> [!NOTE]
> Visit our [`vehicle-versions`](v-photos/vehicle-versions/README.md) folder to see photos and videos of our car evolution 🔝

<br>


## 3. System Setup
### **<ins>Operating Environment Overview</ins>**
The operating environment of our robotic car is designed as a structure that connects hardware, software, and middleware into a single functional system, shown in the diagram below:

<p align="center">
  <img src="https://github.com/user-attachments/assets/94d8b0e1-d5f1-4a22-9ba9-11ce9cd6ee5d" alt="diagram" width="90%">
</p>



### **<ins>Robot Operating System (ROS)</ins>** <img width="50" alt="ROS" src="https://github.com/user-attachments/assets/53574d65-315e-4dfd-a8d9-ffb38e892bab" />
ROS is a framework that connects a robot’s software and hardware, making sensors, motors, and programs work together so the robot can perform tasks smoothly. For this project, we use ROS 2 Jazzy, one of the latest versions of ROS 2. You can find the documentation here:  [ROS 2 Documentation: Jazzy](https://docs.ros.org/en/jazzy/index.html)<br>

Without ROS, everything would have to be written in one long, complicated program that’s hard to manage. We can now divide the system into smaller parts, or nodes, that each do one job, making the system easier to build, fix, and expand.<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/b94b35c9-c47d-48f0-9a54-57789c4cc455" alt="Nodes" width="80%">
</p>

> This is an official animation to better understand how nodes work. Each node does one clear job, like moving wheels or reading sensors, and they talk to each other using topics, services, actions, or parameters.
>  In practice, this is the process:
> 1. Sensors send data to ROS 2 by publishing it on topics.
> 2. Other nodes listen to that data, process it, and decide what the car should do.
> 3. Finally, a controller node sends commands, making the car move accordingly.

<br>

*<ins>Why we use ROS?</ins>*<br>

<table>
  <tr>
    <td><b>Sensor & Actuator Integration</b></td>
    <td>
      ROS connects all sensors and actuators in one system, ensuring seamless coordination. 
      This gives our autonomous car continuous information about its surroundings 
      and optimizes overall performance.
    </td>
  </tr>
  <tr>
    <td><b>Environmental Perception with LiDAR</b></td>
    <td>
      Using LiDAR, we obtain precise 360° distance data, essential for detecting obstacles and walls. 
      ROS packages like <code>laser_scan_matcher</code> and <code>gmapping</code> process this data 
      to create real-time maps of the environment.
    </td>
  </tr>
  <tr>
    <td><b>Autonomous Navigation & Path Planning</b></td>
    <td>
      With ROS navigation tools such as <code>move_base</code>, the car can plan optimal routes 
      and adjust them in real time—especially useful for the Obstacle Challenge.
    </td>
  </tr>
  <tr>
    <td><b>Efficient Simulation & Debugging</b></td>
    <td>
      Virtual environments like 
      <a href="https://gazebosim.org/home">Gazebo</a> let us fine-tune parameters before implementation. 
      Tools like 
      <a href="https://docs.ros.org/en/humble/Tutorials/Intermediate/RViz/RViz-User-Guide/RViz-User-Guide.html">RViz</a> 
      allow real-time visualization of sensor data and car status, making debugging much easier.
    </td>
  </tr>
</table>



<br>

### **<ins>Ubuntu</ins>** <img width="60" alt="UBUNTU" src="https://github.com/user-attachments/assets/38f176af-2d07-41f9-bb14-3ef8eb2c0022" />
Ubuntu is a popular, free, open-source operating system based on Linux. It is known for being reliable, flexible, and widely used in both research and industry. In our project, we use Ubuntu 24.04 as the **foundation that runs on the Raspberry Pi**.<br>

Ubuntu manages the Raspberry Pi’s resources efficiently, ensuring it runs correctly. It provides drivers and compatibility for sensors and external hardware, making integration easier. Ubuntu also allows us to install and run ROS 2 Jazzy and gives us access to important libraries and tools that simplify tasks such as sensor communication and system development.<br>

We use Ubuntu because of its stability and compatibility with ROS 2 Jazzy. Since ROS 2 packages are officially distributed for Ubuntu, using this operating system guarantees that we can easily install and manage the software needed for our car.
<br><br>

### **<ins>Raspberry Pi</ins>** <img width="70" alt="Raspberry" src="https://github.com/user-attachments/assets/6e218c1a-8fe1-47a2-8ae5-1719956508fa" />
The Raspberry Pi is a small computer that works as the brain of our car. It is powerful enough to run Ubuntu, ROS 2, and our algorithms in real time. In our project, we use the Raspberry Pi 5, which you can find here: [Raspberry Pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/)<br>

**👉 Set up and configuration**<br>

With the [Raspberry Pi Imager](https://www.raspberrypi.com/software/), we flash Ubuntu 24.04 into the microSD card of the Raspberry. After that, we configure the basics like Wi-Fi, SSH for remote access, and hostname. And finally, we install ROS 2 Jazzy by following these steps: [Installation Ubuntu (deb packages)](https://www.google.com/url?q=https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html&sa=D&source=docs&ust=1756316032253380&usg=AOvVaw24eBtKhOAoYRVzp4xh2Rkh)

| Step 1 | Step 2 | Step 3 | Step 4 |
| :--: | :--: | :--: |  :--: |
| <img src="https://github.com/user-attachments/assets/f6ee9449-517c-443a-aad2-c7a4913f8334"/> | <img src="https://github.com/user-attachments/assets/0990b9f5-a0a7-408b-a90b-2e9086ae6032" /> | <img src="https://github.com/user-attachments/assets/8b716aad-e25b-4ff4-a92a-8e5e1b085319" /> | <img src="https://github.com/user-attachments/assets/c0f70529-b1b9-4ce7-b0c2-3803a02c44db"/> |


<br>

## 4. Mobility Management 

### <ins>**Steering System - Ackermann**</ins>

<p align="center">
  <img src="https://github.com/user-attachments/assets/8cfcffdb-48aa-4297-a41c-b494a0f222c0" alt="Ackermann" width="70%">
</p>

Our autonomous car uses an Ackermann steering system, controlled by a 15 kg·cm digital servo, which provides precise and stable control for navigation and turns. <br>

The Ackermann steering geometry is designed to reduce tire slip by ensuring that all wheels align as radii of circles that share a common center when the car is turning. This configuration keeps the rear wheels fixed and places the center of rotation along a line extended from the rear axle. To achieve this geometry, the inside front wheel turns at a greater angle than the outside front wheel, allowing smoother and more efficient cornering.

### **Our own modifications ⚒️**
In the first versions of the car, we implemented the Ackermann steering system using a custom mechanism. We designed and 3D printed a gear connected to a stepper motor, along with a rack, which is a stick with grooves that fit into the gear teeth. When the motor rotated the gear, the rack would move, which in turn rotated the wheels. <br><br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/211ba653-b04c-4f56-9fca-0c7498eb9aff" width="300" height= "200">
  <img src="https://github.com/user-attachments/assets/e45a7e54-3c88-4524-b427-0ecff04898f5" width="300" height= "200">
</p>


<br> 

One of the challenges we faced was the 3D printing process itself. Printing small details such as gear teeth was difficult and often imprecise, which caused problems in the initial prototypes. To solve this, we made the gear teeth larger, and while this worked mechanically, the final design ended up taking too much space inside the chassis.<br><br>

For this reason, we decided to switch to the system we currently use, which is part of the Hiwonder kit, adapted to fit in our chassis base. Instead of gears, it uses a system of linkages connected by screws and supported by bearings. These linkages move and transfer the motion to the wheels, achieving the Ackermann steering effect in a more compact way.

<p align="center">
  <img src="https://github.com/user-attachments/assets/4843c1d0-fb98-4bd4-b9e3-5fe4925295cd" width="300" height="200">
</p>

> [!WARNING]
> At first, the Ackermann of the Hiwonderkit worked fine, the car could turn and even get through some obstacles. But after a lot of testing, we noticed that whenever the car turned left, the Ackermann didn’t rotate as much as it did when turning right. This made obstacle avoidance harder, especially in the field corners, so we knew we had to make adjustments.

We realized that the servo needed to be repositioned. First, it was placed horizontally under the Ackerman linkages. We brainstormed how to make it more efficient and changed the position of the servomotor, mounting it vertically with the accessory facing downward under the chassis. This way, the linkages could move freely with more angles, and we also freed up extra space for the other components. This new placement also allowed us to reduce the length of the chassis. <br><br>


<table>  
  <tr>
    <th width="30%">Initial position</th>
    <th width="30%">Idea</th>
    <th width="30%">Final Position</th>
  </tr>
  
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/c2211141-81ed-4bbd-ad60-2111033b03cd"/>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/fe8e9d70-c1c7-496e-81b4-c050766807a8"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/85a6c25b-8473-4ee0-b0c3-f3ce70bd4888" />
    </td>
  </tr>

  <tr>
    <td>
      Servo mounted horizontally (limited angles)
    </td>
    <td>
      Servo repositioned vertically
    </td>
    <td>
      Final placement with improved steering
    </td>
  </tr>
  
</table>
  
### <ins>**Motor and Drivetrain**</ins>

<p align="center">
<img src="https://github.com/user-attachments/assets/f636176b-af6a-4b72-bb31-53f025ab41b1" width= 70% />
</p>

The drivetrain of our autonomous car is powered by a **25 mm metal gear DC motor**, chosen for its compact size and high torque. The motor is mounted on the chassis and directly connected to the rear axle through a system of gears, ensuring efficient transfer of power to the wheels.  

Our drivetrain includes a gear reduction system:
+ The small gear is mounted on the motor shaft.
+ This small gear drives a larger gear connected to the rear axle.
+ The result is a reduction ratio that increases torque at the wheels, providing more force for acceleration and stability, even if the motor speed itself remains constant

<p align="center">
<img src="https://github.com/user-attachments/assets/1b89468f-1234-4610-8944-20d835b95d5b" />
</p>

During assembly, we noticed a gap between the metal chassis part and the axle supports. This caused instability in the drivetrain. To fix it, we designed custom 3D-printed cylindrical spacers that fill the gap and keep the axle firmly in place.
This simple solution reduces vibrations, prevents misalignment, and ensures smoother transmission of power from the motor to the wheels.

<p align="center">
<img src="https://github.com/user-attachments/assets/a3747319-fd2e-4542-ac6d-be17239430e3" width=50%/>
</p>

### <ins>**Chassis Design Process**</ins>
This autonomous car project features a carefully constructed design that combines metal components with custom 3D-printed parts to create a durable, lightweight, and functional structure.

The base and upper casing were crafted from aluminum to provide strength and lightweight support for all components. The base was designed to securely mount the Raspberry Pi and support the weight of the vehicle’s systems, offering a stable foundation and balanced weight distribution critical for stability. The upper casing, which houses the LiDAR sensor, was designed to ensure the sensor has an unobstructed view while protecting it from potential impacts and environmental factors.

<p align = "center">
  <img src = "https://github.com/user-attachments/assets/b878388c-313e-4fd7-aca1-75f875a06fa5" width="70%">
  </p>

### <ins>**3D Printed Parts**</ins>

<br>
<br>

## 5. Power & Sense Management 

### <ins>**Power Source**</ins>

<p align="center">
  <img src="https://github.com/user-attachments/assets/8d83ffe1-569e-4fe6-a97f-a14b833fa9ac" width="80%">
</p>

Our autonomous car is powered by 7.4V Li-Po batteries (2000mAh, 20C). We chose Li-Po batteries because they provide a high energy density, meaning more power in a small and lightweight package. The battery provides two main energy lines: one for the electronics and another for the motor: <br>

1. **Electronics & Sensors**  
   The battery first connects to the **RRC Lite Controller**, which regulates the power down to a safe **5 V**.  
   From there, it distributes electricity to:  
   - **Raspberry Pi 5** → acts as the brain of the car, running ROS 2 and processing sensor data.  
   - **Digital servomotor** → controls the Ackermann steering system.  
   - **STL-19P TOF LiDAR & monocular camera** → provide vision and distance perception.  

2. **Drive Motor (via L298N Motor Driver)**  
   In parallel, the battery also powers the **L298N motor driver** directly with **7.4 V**.  
   This driver regulates how much current goes to the **25 mm metal DC motor**, which is responsible for moving the car forward.  

By splitting the power into two paths (one regulated for sensitive electronics and one direct for the motor), the system ensures stability. Motors usually demand sudden spikes of current, and separating their supply avoids crashes or interruptions in the Raspberry Pi and sensors.


### <ins>**Sensors Integration**</ins>
To perceive its environment and handle the Future Engineers challenges, the car uses a combination of:  

- **STL-19P TOF LiDAR**: provides 360° distance data.  
- **2DOF Monocular Camera**: detects colors and obstacles.  

Together, these sensors give the robot a better understanding of its environment by combining depth perception with visual input.


### <ins>**STL-19P TOF LiDAR**</ins>

<p align="center">
  <img src="https://github.com/user-attachments/assets/853f8730-a645-47b5-bacf-ded61b21a6c9" width="80%">
</p>

<br>

Unlike simpler sensors such as ultrasonic or infrared, which measure only in a single direction and have limited precision, the LiDAR sensor is capable of a **360° scanning** and provides precise distance measurements by using laser pulses. It helps the robot map its surroundings over a wide range, detect obstacles, and navigate more accurately in dynamic environments.

<br>

| Characteristic        | Vaue                        |
|------------------------|------------------------------|
| Ranging distance       | 0.03 – 12 m                 |
| Size                   | 38.59 x 38.59 x 34.8 mm     |
| Scanning Angle         | 360°                        |
| Scanning Frequency     | 5 – 13 Hz                   |
| Ranging Accuracy       | ±45 mm                      |
| Ranging Frequency      | 5000 Hz                     |

<br>

> [!IMPORTANT]
> **📍Placement:**
> The LiDAR was positioned at an altitude of under 10 cm, so it can detect the walls of the path, which are also 10 cm high. This placement ensures the Lidar has a clear view of the obstacles while remaining unobstructed by other components. All other elements on the car were arranged to avoid blocking the Lidar’s line of sight. <br><br>
> <img width="1206"  src="https://github.com/user-attachments/assets/9e9d9df4-cfc6-4875-b832-435c4d2ebb1c">

  
### <ins>**2DOF Monocular Camera**</ins>

<p align = "center">
  <img src = "https://github.com/user-attachments/assets/546b6072-3ab9-4a02-b0a2-437478ac0b03" width="50%">
  </p>
<br>

The 2DOF Monocular Camera complements the LiDAR by adding visual perception. This allows the robot to recognize its environment beyond distance data, enabling future applications such as detecting the obstacles’ colors:

 + **Color detection**: Since graphical color detection is a core part of our  project, the camera can precisely identify various colors on the course. This allows our car to interact with the different traffic signs in the Obstacle challenge.
  + **Spatial awareness through data fusion**: When combining camera data with our sensor, the robot gains a richer understanding of its environment. The camera provides detailed visual context that leads to an adaptable navigation strategy.

<br>

> [!IMPORTANT]
> **📍Placement:**
> The camera is located in a special 3D mounting piece with a certain  inclination angle that points to the floor so it can better detect obstacles. At first it was placed at the front of the car but this location provided a limited vision and sticked out of the chassis lenght. See more detailed info of the housing piece in the [`3D Printed Parts`](#3d-printed-parts) section. <br><br> 
> <img width="1206"  src="https://github.com/user-attachments/assets/a286367c-681d-473b-807f-c9e470b2fb0d">



### **<ins>BOM (Bill of Materials)</ins>**
| Component | Quantity | Description | Image |
|-----------|----------|-------------|-------|
| Raspberry Pi 5 | 1 | Main processing unit for running **ROS**. Acts as the main brain and the Host Controller of the system, capable of running operating systems and handling complex processing tasks. | <img width="850" alt="Raspberry Pi 5" src="https://github.com/user-attachments/assets/ee89c342-6957-4551-b429-e7731c2a28df" /> |
| RRC Lite Controller | 1 | Integrates: ROS expansion board, High-Frequency PID Control, Motor Closed-Loop Control, Servo Control and Feedback, IMU Data Acquisition, Power Status Monitoring, and a Power Switch. | <img width="850" alt="Controller" src="https://github.com/user-attachments/assets/929afeb7-4486-4cd3-bb9e-a8a51bd91e83" /> |
| STL-19P TOF Lidar | 1 | Provides precise, 360-degree distance measurements for real-time navigation and obstacle detection in dynamic environments. | <img width="850" alt="Lidar" src="https://github.com/user-attachments/assets/927d47f4-c856-461d-9e6e-ba1c35318990" /> |
| Lidar Adapter Board | 1 | Converts the LiDAR’s UART signals to USB for PC connection and data reading. | <img width="850" alt="Adapter" src="https://github.com/user-attachments/assets/407671ef-bed2-4a04-8aef-0cb69cab464a" /> |
| 15 kg.cm Digital Servo | 1 | Provides accurate steering control. | <img width="850" alt="Servo" src="https://github.com/user-attachments/assets/b949c033-fc6d-4032-8d41-b136ea6ddc90" /> |
| 65 mm Anti-Slip Rubber Wheel | 2 | High-grip wheels to improve traction and stability. | <img width="850" alt="Wheel" src="https://github.com/user-attachments/assets/3f50620d-b008-4426-86f5-2c4f5ee6aff6" /> |
| 25MM Metal Gear Motor | 1 | Core drive motor for powering the wheels with torque and speed. | <img width="850" alt="Motor" src="https://github.com/user-attachments/assets/de6786ac-3dc2-4d36-89e3-03435708c338" /> |
| Rubber Tire Edge | 2 | Ensures 3d- printed wheels stability and grip on the floor. | <img width="850" alt="tire" src="https://github.com/user-attachments/assets/840e6304-55cd-4e40-b4e4-76193dc6ad4f" /> |
| Monocular Camera | 1 | A camera used for capturing images and videos, can be used for computer vision or live streaming. | <img width="850" alt="Camera" src="https://github.com/user-attachments/assets/47eeb574-59c4-4cdf-be45-4133167f8739" /> |
| L298N Motor Driver | 1 | Controls motor direction and speed from the Raspberry Pi. | <img width="850" alt="Motor Driver" src="https://github.com/user-attachments/assets/3ab3c2e0-8b73-4996-9412-b28877301502" /> |
| Jumper Cables | 4–8 | Electrical connections between the motor driver and Pi. | <img width="850" alt="Jumper Cables" src="https://github.com/user-attachments/assets/44758ea5-a6b2-4366-a1fb-7a0eeac5135b" /> |
| USB-USB Cable | 1 | A cable to connect the Raspberry Pi to the camera, Lidar, and Controller. | <img width="850" alt="USB Cable" src="https://github.com/user-attachments/assets/e28195ef-1993-4163-a3de-d2299c443eb0" /> |
| Li-Po Battery 7.4 V 5000mAh 20C | 1 | A lithium polymer battery that provides portable, high-density power. | <img width="850" alt="Battery" src="https://github.com/user-attachments/assets/204ea520-4bc6-4757-93e2-d99036c49403" /> |




### <ins>**Wiring Diagram**<ins>

The following diagrams illustrate how all the main components of the car are interconnected, ensuring proper communication and stable power distribution across the system.  

<p align="center">
  <img src="https://github.com/user-attachments/assets/42416f9e-0c0a-4751-b446-b05c707c9434" width="80%">
</p>

#### **1. Raspberry Pi 5 Connections**
The Raspberry Pi 5 works as the brain of the car. Its USB ports connect the main sensors and the controller:

+ Camera → provides visual input for detecting traffic signs and colored obstacles.
+ LiDAR → provides distance and wall detection for navigation.
+ RRC Lite Controller → interfaces with the digital servomotor and forwards control signals to the motor driver.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0b2efa85-6dec-49f6-ba25-af40653e8c89" width="80%">
</p>

#### **2. RRC Lite Controller**
The RRC Lite Controller acts as a bridge between the Raspberry Pi and the actuators. It regulates incoming power from the Li-Po battery (down to a safe 5 V) and distributes it to:  
- The **Raspberry Pi 5**  
- The **digital servomotor** for Ackermann steering  

It also handles communication with the motor driver to send PWM control signals.

---

#### **3. Motor Driver and DC Motor**
The **L298N Motor Driver** is powered directly by the **7.4 V Li-Po battery**.  
- It regulates both the **speed** and **direction** of the **25 mm metal gear DC motor**.  
- The motor then powers the rear axle through a gear reduction system, increasing torque for smoother acceleration.  

---

#### **4. Power Source**
The **7.4 V Li-Po battery** supplies energy to the entire system, split into two paths:  
- **Direct line (7.4 V):** powers the L298N motor driver and DC motor.  
- **Regulated line (via RRC Lite Controller):** delivers 5 V to the Raspberry Pi, servomotor, and sensors.  

<br>

## 6. Obstacle Management 
### <ins>**Autonomous Driving Logic**<ins>

### <ins>**Open Challenge**</ins>
<p align="center">
  <img src="https://github.com/user-attachments/assets/672a9f3c-875b-4f9e-a2d6-b38b62be8fdf" width="40%">
  <img src="https://github.com/user-attachments/assets/0b9e80ab-a3b6-4cbc-9457-b2b9e9251c7a" width="40%">
</p>


### <ins>**Obstacle Challenge**</ins>

<p align="center">
  <img src="https://github.com/user-attachments/assets/709c3f14-f9d9-4626-b078-1e8304557f87" width="80%">
</p>

<br><br>
## 7. Assembly Instructions 

<br><br>
## 8. Performance Videos 









