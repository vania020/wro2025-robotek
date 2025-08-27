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
* `t-photos` team photos (official one and one funny)
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
      Hello!! My name is Isabella Gonzales, I'm 16 years old, and I love robotics. I love music (singing and playing the guitar), making origami, and painting. A fun fact about me is that I sang in the National Theather wearing pijamas when I was 6.<br><br>
   
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
> Visit our [`v-photos`](https://github.com/vania020/wro2025-robotek/tree/main/v-photos) file for more detailed photos of the car.

<br>

### *Versions of the Car*
Our vehicle has gone through about **seven versions** (and since we are always improving, there are still more to come!). It all started with a cardboard prototype, then moved on to acrylic and metal chassis designs, and later, we made personalized adjustments to a HiWonder kit. Along the way, we also experimented with different wheel designs, repositioned components, tested sensors like LiDAR, and finally adopted a new operating environment with ROS and Ubuntu.

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

<br>

## 3. System Setup

### *Operating Environment Overview*
The operating environment of our robotic car is designed as a structure that connects hardware, software, and middleware into a single functional system, shown in the diagram below:

```mermaid
flowchart LR
    A[Hardware] --> B[Ubuntu]
    B --> C[ROS 2]
    C --> D[Nodes]
```

At the base, we have the hardware, including sensors such as LiDAR and a camera, along with actuators like motors and servos. All of these devices are controlled by the Raspberry Pi, which acts as the main controller.
On top of this runs Ubuntu 24.04, which provides the necessary drivers, system libraries, and support for robotics applications.
The next layer is ROS 2 Jazzy, the middleware that ensures communication between nodes.
Finally, at the application, we implement our own algorithms for perception, navigation, and control that directly solve the challenges of the competition.


