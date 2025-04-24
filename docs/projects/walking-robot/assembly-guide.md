---
title: Assembly Guide
lang: en
lang_name: English
comments: true
---

# Assembly Guide

This guide will walk you through the assembly process of the walking robot. The assembly consists of three main parts:

1. **Mechanical Assembly**: This includes all the physical components like motors, legs, main board, and the remote control.
2. **Programming**: This covers the software setup for both the robot and remote control using Micro:bit.
3. **Testing and Calibration**: This section guides you through testing the assembled robot and calibrating its movements for optimal performance.

Let's get started with the mechanical assembly first.

## 1. Mechanical Assembly
### 1.1 Motor Module installation

![Motor Module](images/component-motor-module.png){ width=200px }  

**Parts involve:**

| Item               | Description                | Quantity | Image                |
|--------------------|----------------------------|----------|----------------------|
| Motor (N20 DC Motor 6V 60rpm) | Small DC motor for driving | 2        | ![Motor](images/part-motor.png){ width=50px }  |
| part-motor-case.stl         | Enclosure for the motor    | 1        | ![Motor Case](images/part-motor-case.png){ width=50px } |


**Video Instruction**

[Watch the assembly video](https://youtube.com/shorts/HkKQfT87Ntc?feature=share)


### 1.2 Left and right legs assembly

![Left and Right Legs](images/component-left-right-legs.png){ width=200px }  

**Parts involve:**

| Item                                             | Description                       | Quantity | Image |
|--------------------------------------------------|-----------------------------------|----------|-------|
| part-frame.stl        | Main body component                | 2        | ![frame](images/part-frame.png){ width=50px }      |
| part-control-bar-bottom.stl | Control bar (bottom) component       | 2        | ![control-bar-bottom](images/part-control-bar-bottom.png){ width=50px }      |
| part-control-bar-top.stl | Control bar (top) component       | 2        | ![control-bar-top](images/part-control-bar-top.png){ width=50px }      |
| part-foot.stl  | Foot component                     | 2        |  ![foot](images/part-foot.png){ width=50px }       |
| part-foot-palm.stl  | Foot Palm component                     | 2        |  ![foot-palm](images/part-foot-palm.png){ width=50px }       |
| part-foot-sole.stl  | Foot Sole component (Optional)              | 2        |  ![foot-sole](images/part-foot-sole.png){ width=50px }       |
| part-leg-main.stl  | Leg Main component                     | 2        |  ![leg-main](images/part-leg-main.png){ width=50px }       |
| part-gear.stl  | Gear component                     | 2        |  ![gear](images/part-gear.png){ width=50px }       |
| part-screw-M4x5  | Screw M4X5                      | 4        |  ![M4X5](images/part-screw-M4x5.png){ width=50px }       |
| part-screw-M4x10  | Screw M4X10                     | 8        |  ![M4X10](images/part-screw-M4x10.png){ width=50px }       |
| part-gear.stl  | Screw small                      | 2        |  ![Small Screw](images/part-screw-small.png){ width=50px }       |

**Video Instruction**

[Watch the assembly video](https://youtu.be/bTmAOl0an0w)

* Please repeat and assemble 2 of this.

### 1.3 Main board installation

**Part involves:**

| Item                                             | Description                       | Quantity | Image |
|--------------------------------------------------|-----------------------------------|----------|-------|
| part-main-frame.stl        | Main body component                | 1       | ![](images/part-main-frame.png){ width=50px }      |
| part-battery-case| Battery Case       | 2        | ![](images/part-battery-case.png){ width=50px }      |
| micro:bit        | Micro:bit               | 1       | ![](images/part-microbit.png){ width=50px }      |
| Beets Control Board    | Control Board to integrate all electronic components                | 1       | ![](images/part-beets-control-board.png){ width=50px }  ![](images/part-beets-control-board-back.png){ width=50px }      |
| Legs Component       | Legs assembly from section 1.2           | 1       | ![](images/component-left-right-legs.png){ width=50px }      |
| Motor Module       | Motor module assembly from section 1.1           | 1       | ![](images/component-motor-module.png){ width=50px }      |

**Video Instruction**

[Watch the assembly video]()


### 1.5 Body and Outter Shell

**Part involves:**

| Item                                             | Description                       | Quantity | Image |
|--------------------------------------------------|-----------------------------------|----------|-------|
| part-body.stl        | Main body component                | 1        | ![](images/part-body.png){ width=50px }      |
| part-head.stl | Head component       | 1        | ![](images/part-head.png){ width=50px }      |
| part-shell-front.stl | Front Shell component       | 1       | ![](images/part-shell-front.png){ width=50px }      |
| part-shell-back.stl | Back Shell component       | 1      | ![](images/part-shell-back.png){ width=50px }      |


**Video**

### 1.7 Remote Control

![Remote Control](images/component-remote-controller.png){ width=200px }  

**Parts involve:**

| Item                                             | Description                       | Quantity | Image |
|--------------------------------------------------|-----------------------------------|----------|-------|
| part-controller-main.stl        | Main body component                | 1        | ![](images/part-controller-main.png){ width=50px }      |
| part-controllor-battery.stl | Battery case holder       | 1        | ![](images/part-controller-battery.png){ width=50px }      |
| part-battery-case| Battery Case       | 1        | ![](images/part-battery-case.png){ width=50px }      |
| part-microbit | microbit                   | 1        |  ![](images/part-microbit.png){ width=50px }       |

You can download the stl files from this link
[Download the stl files here](https://www.printables.com/model/248633-bbc-microbit-controller-case-with-detachable-batte/files)

**Video Instruction**

[Watch the assembly video](https://youtube.com/shorts/qm5MiA7BIWI)


## 2. Programming

You will be using Microsoft MakeCode in this section. 
1. It can be access via https://makecode.microbit.org/#
2. You will need to sign up for an account

Once you have got an account, please go to the next steps.

![](images/screen-makecode-import.png){ width=500px }  

### 2.1 Basic Micro:bit programming using MakeCode

1. Click on "Import" button
2. Choose "Import URL" 

![](images/screen-makecode-import-2.png){ width=500px }  
3. Open project URL, enter: https://github.com/beets3d/b3d1-walking-bot-main
![](images/screen-makecode-projecturl.png){ width=500px }  
4. Plug in your micro:bit using a USB cable, and Click "Download

### 2.2 Remote control setup

Repeat the above, using this project URL: https://github.com/beets3d/b3d1-walking-bot-controller

## 3. Testing and calibration 

**Video Instruction**
