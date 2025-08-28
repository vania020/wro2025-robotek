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
1. [Meet the Team!](#meet-the-team)
2. [Vehicle Overview](#vehicle-overview)
3. [System Setup](#system-setup)
4. [Mobility Management](#mobility-management)
5. [Power & Sense Management](#power--sense-management)
6. [Obstacle Management](#obstacle-management)
7. [Assembly Instructions](#assembly-instructions)
8. [Performance Videos](#performance-videos)
   
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

### *General Description of the Car*
Our autonomous vehicle is built to take on both the Open and Obstacle Challenges at the Future Engineers competition. Running on Ubuntu with ROS, it can process information and make decisions in real time. With an Ackermann steering system and a stable chassis, the car handles turns and straightaways smoothly, while a LiDAR sensor is primarily used to detect traffic sign obstacles and adapt the path, helping the vehicle count laps and complete the course efficiently.
<br>

| Front | Left | Right |
| :--: | :--: | :--: | 
| <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="90%" /> | <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> |  <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> | 

| Back  | Top  | Bottom |
| :--: | :--: |:--: |  
| <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="90%" /> | <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> |  <img src="https://github.com/user-attachments/assets/63ed0743-32e4-4605-b754-b6c322b21799" width="85%" /> | 
> [!NOTE]
> Visit our [`v-photos`](https://github.com/vania020/wro2025-robotek/tree/main/v-photos) file for more detailed photos of the car 📸🚗

<br>

### *Versions of the Car*
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
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>

  <!-- Version 2 -->
  <tr>
    <td align="center">Version N°2</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/14afa30d-317e-43f8-b6ef-d63897212c88" width="300" height="200"/>
    </td>
    <td>
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>

  <!-- Version 3 -->
  <tr>
    <td align="center">Version N°3</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/5299a922-0fb3-43a8-9a32-9bdbc77225d7" width="300" height="200"/>
    </td>
    <td>
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>

  <!-- Version 4 -->
  <tr>
    <td align="center">Version N°4</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/80568426-a136-48a6-b219-9c05dd3e2584" width="300" height="200"/>
    </td>
    <td>
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>

  <!-- Version 5 -->
  <tr>
    <td align="center">Version N°5</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/fe6757a1-3fe5-4b12-b856-bedcc28a5b50" width="300" height="200"/>
    </td>
    <td>
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>

  <!-- Version 6 -->
  <tr>
    <td align="center">Version N°6</td>
    <td align="center"><img src="https://github.com/user-attachments/assets/7e483e4c-2f35-48e9-8125-00a2123f06a2" width="300" height="200"/>
    </td>
    <td>
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>

  <!-- Version 7 -->
  <tr>
    <td align="center">Version N°7</td>
    <td align="center">Car Photo</td>
    <td>
      Kit to better meet the competition’s challenges. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.
    </td>
  </tr>
</table>

<br>

## 3. System Setup

### *Operating Environment Overview*
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


### *Robot Operating System (ROS)* <img width="50" alt="ROS" src="https://github.com/user-attachments/assets/53574d65-315e-4dfd-a8d9-ffb38e892bab" />
ROS is a framework that connects a robot’s software and hardware, making sensors, motors, and programs work together so the robot can perform tasks smoothly. For this project, we use ROS 2 Jazzy, one of the latest versions of ROS 2. You can find the documentation here:  [ROS 2 Documentation: Jazzy](https://docs.ros.org/en/jazzy/index.html)<br>

*<ins>Why and How we use it?</ins>*<br>
We use ROS 2 because it helps us organize the car’s programs in a clear way. Without it, everything would have to be written in one long, complicated program that’s hard to manage. We can now divide the system into smaller parts, or nodes, that each do one job, making the system easier to build, fix, and expand.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b94b35c9-c47d-48f0-9a54-57789c4cc455" alt="Nodes" width="50%">
</p>

> This is an official animation to better understand how nodes work. Each node does one clear job, like moving wheels or reading sensors, and they talk to each other using topics, services, actions, or parameters.

Another advantage is that ROS 2 already comes with many libraries and tools for tasks like sensor handling, visualization, and simulation.In practice, this is the process:
1. Sensors send data to ROS 2 by publishing it on topics.
2. Other nodes listen to that data, process it, and decide what the car should do.
3. Finally, a controller node sends commands, making the car move accordingly.
<br><br>

### *Ubuntu* <img width="60" alt="UBUNTU" src="https://github.com/user-attachments/assets/38f176af-2d07-41f9-bb14-3ef8eb2c0022" />
Ubuntu is a popular, free, open-source operating system based on Linux. It is known for being reliable, flexible, and widely used in both research and industry. In our project, we use Ubuntu 24.04 as the **foundation that runs on the Raspberry Pi**.<br>

*<ins>Role in the System</ins>*<br>
Ubuntu manages the Raspberry Pi’s resources efficiently, ensuring it runs correctly. It provides drivers and compatibility for sensors and external hardware, making integration easier. Ubuntu also allows us to install and run ROS 2 Jazzy and gives us access to important libraries and tools that simplify tasks such as sensor communication and system development.<br>

We use Ubuntu because of its stability and compatibility with ROS 2 Jazzy. Since ROS 2 packages are officially distributed for Ubuntu, using this operating system guarantees that we can easily install and manage the software needed for our car.
<br><br>

### *Raspberry Pi* <img width="70" alt="Raspberry" src="https://github.com/user-attachments/assets/6e218c1a-8fe1-47a2-8ae5-1719956508fa" />
The Raspberry Pi is a small computer that works as the brain of our car. It is powerful enough to run Ubuntu, ROS 2, and our algorithms in real time. In our project, we use the Raspberry Pi 5, which you can find here: [Raspberry Pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/)<br>

*<ins>Set up and configuration</ins>*<br>
+ With the [Raspberry Pi Imager](https://www.raspberrypi.com/software/), we flash Ubuntu 24.04 into the microSD card of the Raspberry
+ After that, we configure the basics like Wi-Fi, SSH for remote access, and hostname.
+ And finally, we install ROS 2 Jazzy by following these steps: [Installation Ubuntu (deb packages)](https://www.google.com/url?q=https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html&sa=D&source=docs&ust=1756316032253380&usg=AOvVaw24eBtKhOAoYRVzp4xh2Rkh)

<br><br>
## 4. Mobility Management 

### *Motors and Powertrain*
### *Steering System - Ackermann*
### *Chassis Design Process*
### *3D Printed Parts*


<br><br>
## 5. Power & Sense Management 

### *Power Source*
### *LIDAR & Additional Sensors Integration*
### *BOM (Bill of Materials)*
### *Wiring Diagram*


<br><br>
## 6. Obstacle Management 
### *Autonomous Driving Logic*
### *Flow Diagrams*
### *Open Challenge*
### *Obstacle Challenge*

<br><br>
## 7. Assembly Instructions 

<br><br>
## 8. Performance Videos 









