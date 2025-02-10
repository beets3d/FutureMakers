---
title: Walking Robot (B3D1)
lang_name: en 
comments: true
---

# Walking Robot  (B3D1) Project 

## What is this?

  ![Robot-Side-1](images/Robot-Side-1.png){ width=30% }
  ![Robot-Front](images/Robot-Front.png){ width=30% }
  ![Robot-Side-2](images/Robot-Side-2.png){ width=30% }



A walking crank robot that demonstrates fundamental walking mechanism concepts through hands-on experimentation. This educational platform allows students and teachers to explore how different physical attributes affect robot locomotion. By modifying key components like leg length and foot design using LEGO blocks, students can investigate:

- Walking speed and efficiency
- Robot stability and balance
- Different walking gaits and patterns


Understanding the concepts of walking mechanisms, balance, and motion dynamics is crucial for developing a deeper understanding of robotics. For details, please refer to the [Concepts of Walking](concept-of-walking.md) page.

Key Features:

- Modular design for easy modification
- Basic walking functions (forward movement and potential turn left/right)
- Customizable foot attachments for experimenting with different concepts by changing leg length and foot design by using LEGO blocks
- Remote control capability to test different walking patterns

The robot serves as an excellent teaching tool for understanding mechanical principles, robotics fundamentals, and the relationship between design choices and movement outcomes.

## What you will learn
- **Mechanical Principles**: Walking mechanisms, balance, motion dynamics
- **Design & Experimentation**: Testing different foot designs, leg lengths, and their effects on robot movement
- **Electronics**: Working with micro:bit, motor control, basic circuitry
- **Coding**: Programming to control robot, and remote control 
- **Engineering**: Understanding gear systems, mechanical advantage
- **Problem Solving**: Analyzing movement patterns, improving stability, optimizing performance
- **Documentation**: Recording observations, comparing different configurations
- **Teamwork**: Collaborative experimentation, sharing findings
- **STEM Integration**: Connecting physics concepts with real-world robotics applications

## What you need

### Hardware

- 2x BBC micro:bit
- USB cable for programming (please note V2 is used to developed this project)
    - 1x Main control board for connecting to Micro:bit including motor driver and Battery pack (developed by Beets3D)
    - 4 X AA Batteries
    - 2x Geared motors (N20 DC motor)
    - 3D printed parts (chassis and mechanical components)
    - Outer shell components (External casing)
    - LEGO blocks (for modifications)


### Software
- MakeCode for micro:bit (web-based programming platform Or using iPad app)
- 3D printing software (for customizing parts, recommended using Fusion 360)

### Tools
- Screwdriver
- Wire cutters/strippers (for jumper wires)
- 3D printer access (for parts)

### Age
Suitable for ages 11-17 

## How it works
![Walking Robot Overview](images/Walking-Robot-Drawing.jpg){ width=80% }

### The Design

It is designed using Autodesk Fusion 360, the STEP file is available in [Design File](cad/Walking-Crank-Robot-v91.step).

#### Core Walking Mechanism
   - Motor Unit - consists of 2 geared motors   
   ![Motor Unit](images/Motor-Unit.png){: style="width: 50%; display: block; margin-left: auto; margin-right: auto;"}

   - Leg (left / right) - consists of leg with mechamism to simulate the walking Pendulum motion, and foot with LEGO compatible attachment.


   ![Leg 1](images/leg-1.png){: style="width: 30%; display: inline-block; margin-right: 10px;"} ![Leg 2](images/leg-2.png){: style="width: 30%; display: inline-block;"} 
      
   ![LEGO Attachment](images/leg-lego-attachment.png){: style="width: 30%; display: inline-block; margin-right: 10px;"} ![Foot](images/leg-foot.png){: style="width: 30%; display: inline-block;"}

#### Electronics
   - Main Board
   - Micro:bit

      ![Leg 1](images/microbit-1.png){: style="width: 30%; display: inline-block; margin-left: auto; margin-right: auto;"} ![Leg 2](images/microbit-2.png){: style="width: 30%; display: inline-block;margin-left: auto; margin-right: auto;"} 

   - Battery Cases
#### Outter Shell
   - **Body**- This is the main body of the walking robot, designed to house the internal components and provide structural support for the legs and head.
      ![Body](images/body.png){: style="width: 50%; display: block; margin-left: auto; margin-right: auto;"}

   - **Head** - This component serves as the robot's head, providing a visual representation and housing any necessary sensors or features for interaction. This can be customised according the learning needs.
      ![Head](images/head.png){: style="width: 50%; display: block; margin-left: auto; margin-right: auto;"}
   - **Outer Shell** - This component provides the external casing for the robot, giving a nice outlook and customise base any requirements.  
      ![Shell](images/body-outter-shell.png){: style="width: 50%; display: block; margin-left: auto; margin-right: auto;"}
#### Remote Control
You can use another Micro:bit to control the walking pattern by pressing the A or B button. Each button corresponds to the movement of one leg; pressing a button will make the associated leg step forward. For example, let's assume the A button controls the left leg and the B button controls the right leg. When you press the A button, the left leg will step forward, and when you press the B button, the right leg will step forward. This setup allows you to manage the timing and motion of both legs, providing an opportunity to explore how "control timing" affects balance, speed, and direction during walking.


#### Customization Options
   - **LEGO attachment** - Foot is designed to allow any LEGO attachment to be added
      ![LEGO Attachment](images/lego-attachment-2.png){: style="width: 30%; display: inline-block; margin-left: auto; margin-right: auto;"} 
      ![LEGO Foot](images/lego-attachment.png){: style="width: 30%; display: inline-block;margin-left: auto; margin-right: auto;"} 

   - **Adjustable leg lengths** - With the LEGO attachment, you can adjust the length of the legs by adding LEGO blocks, which will change the range of motion for each steps.
   - **Adjustable foot shape** - You can also design the any shapes to test out the different effect to walking behavior, taking consideration of balance.


### Assembly Guide
1. Mechanical Assembly
   - Left and right legs assembly
   - Motor and gear installation
   - Main board installation
   - Install Micro:bit to main board
   - LEGO attachment points setup

2. Electronics Setup
   - Micro:bit wiring
   - Battery pack setup

3. Programming
   - Basic Micro:bit programming using MakeCode
   - Remote control setup
   - Testing and calibration

## Lesson Plan
1. **Day 1: Introduction and Design** (45 min)
   - Walking mechanism principles
   - Robot components overview
   - Safety guidelines
   
2. **Day 2: Assembly** (45 min)
   - Mechanical assembly
   - Electronics connection
   - Initial testing
   
3. **Day 3: Programming** (45 min)
   - MakeCode basics
   - Movement programming
   - Remote control setup
   
4. **Day 4: Experimentation** (45 min)
   - Foot design testing
   - Performance optimization
   - Documentation of results

## Exercise
1. Basic Walking Test
   - Forward/backward movement
   - Speed measurement
   - Stability assessment

2. Design Challenges
   - Create different foot designs
   - Test various leg lengths
   - Compare walking efficiency

3. Documentation
   - Record observations
   - Compare different configurations
   - Present findings

## Student / Teacher Materials
### Student Resources
![Assembly Guide Example](images/assembly-guide.jpg)
- Assembly guide with pictures
- Programming tutorial
- Experiment worksheet
- Design challenge tasks

### Teacher Resources
- Detailed lesson plans
- Assessment rubrics
- Troubleshooting guide
- Extension activities
