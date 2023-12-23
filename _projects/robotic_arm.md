---
layout: page
title: Robotic Arm
description: <b>Bachelor's Thesis</b>. <br> Portable, with 5-DoF and enhanced maneuverability to handle versatile objects, featuring a human-mimetic end-effector for advanced research in Mechatronics. 
img: assets/img/projects/work/robotic_arm/robotic_arm.jpeg
importance: 2
category: Work
giscus_comments: false
---
<!-- thesis details -->
Affiliated Company: [ENPO SPELS](https://spels.ru/) | Feb 2022 - Jul 2022 | Moscow, Russia. \
Mentors:
- [Pavel Nekrasov](https://ieeexplore.ieee.org/author/37085345920), Associate Professor, Division of Nanotechnologies in Electronics, [MEPHI](https://home.mephi.ru/en/users/1417/public)
- Evgeniy Voloshin, Robotics Team Lead, ENPO SPELS

[Thesis [Russian]](https://github.com/SanjarNormuradov/SanjarNormuradov.github.io/tree/master/assets/pdf/projects/robotic_arm/BachelorThesisRus_NormuradovSN.pdf)


## __Situation:__
The objective was to conduct in-depth research in Mechatronics through hands-on full-stack robot development. \
Plus, the robotic arm, built by the company's Robotics Team leader to participate in the <a href="https://cup.rtc.ru/en/rtc-cup">RTC Cup Robotics Competition</a>, had big dimensions and inertia as well as limitations to pick most objects but spherical such as tennis balls.<br><br>

## __Task:__
- Revise the entire robot's mechanical design to refine and optimize for functionality and portability. Build it using FDM 3D printing.
- Design custom PCBs to meet the updated robot requirements, and manufacture them using photolithography technology.
- Develop software to harness the robot's full potential.

## __Action:__
With the technical guidance and support of mentors and SPELS, the following were accomplished:

### 1. Mechanical Desgin & Manufacturing:
- 3D CAD: [T-Flex CAD](https://www.tflex.com/products/tflex-cad/)
- 3D FDM Printers: [Tevo Tornado](https://tevoup.com/products/homers-tevo-tornado-3d-printer)
- Filaments: PLA, PETG, TPU, NYLON
<!-- structural diagram of the process -->
<div class="container">
    <div class="row">
        <div class="col align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_diagram_fullprocess1eng.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

To address the issue with grasping spherical, axially symmetric, or irregular-shaped objects I followed biomimcry - human fingers. Actually three pairs of them:
<!-- finger -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_cad_finger12.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

But for simply grasping without complex maneuvers, having three or six servos to control every finger would result in a heavy end-effector. \
So, for grasping/ungrasping I decided to rotate all three pairs of fingers simultaneously. __But__ when any of the pairs and/or fingers touches the object's surface first, it should stop rotating still applying some force to hold the object without ceasing the other pairs/fingers from rotation. \
One of the solution was to use drums shown below, and rubber bands to transfer torque as ligaments do in human body.<br><br>
The mechanism shown below on the left consists of two separate gears with saw transmission (3, 4), spring to push the gears to each other (2), and fixtures (1, 5).<br>
The upper gears of each pair of fingers is rotated by a single motor, while the lower gears rotate each finger individually.<br>
When any of the fingers stops rotating due to contact with the object surface, torque from the upper gear would be much less to rotate the lower gear.<br>
As a result, the upper gear starts jumping up-down without stopping the other gears, still applying torque to fix its finger's orientation.<br>
The design for a single pair of fingers shown below on the right was the first attempt.<br>
It didn't work because of rubber extension and slippage between gears as a result of its elacticity, that I looked for to pass it through gear mechanism.<br>
Double-edged sword.
<!-- finger-drum1 -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_finger_drum1.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

To address the rubber issues above, I switched to drums and capron thread/fishing line (of several diameters) shown below.<br>
The choice was given to capron thread rather than fishing line because of its elacticity and resistance to sun light and low humidity:
<!-- finger-drum2 -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_finger_drum2.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

As the drums with fishing line could apply greater torque than gears with rubber band, small motors for drones couldn't provie the corresponding torques.<br>
So, I switched to a more powerful motor and changed the wrist design correspondingly:
<!-- wrist -->
<div class="container">
    <div class="row">
        <div class="col align-self-center">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_wrist123.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_cad_finger45.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

Once the wrist started to grasp objects, then next step was to design the rest of the arm.<br>
The first version shown below faced significant issues such as huge inertia because of a peripheral servo at the elbow joint.<br>
__Disclaimer:__ Almost every commercial robotic manipulator has its servos at its joints, which I think is the best approach as long as high motion precision at stake. And I came to this conclusion after I tried with different transmission mentioned in this project below.  
<!-- v1 arm: peripheral servo on elbow -->
<div class="container">
    <div class="row">
        <div class="col align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_arm01.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

So, I transferred the servo from the elbow joint to the shoulder joint, and transferred torque through rubber band. <br>
But it lead to the same outcome - extension because of its elacticity, which significantly affected the end-effector pose repeatability (error in reaching the target pose in space given it's the same at each time).
<!-- v2 arm: rubber transmission for elbow -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_arm_diagram2.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

Apart from switching from rubber band to capron thread, the 5th degree of freedom was introduced to increase manipulability.<br>
But this version was far from the optimal due to its some parts with redundant mass which didn't have any significance in the overall durability.
<!-- v3 arm: rubber band -> fishing line; 4DoF -> 5DoF -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_arm_diagram3.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

Finally, after rigorous material science analysis to make the design durable and lightweight, the model shown below was built:
<!-- v4 arm: reduced weight -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/mechanical/mechanical_arm_diagram45.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

Once the mechanical part of the robotic arm was finished, additionaly its base and the remote controller were designed and printed:
<!-- final devices -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/device_base_controller.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Mechanical design of the Robotic Arm base (left) and the Remote Controller (right).
</div>


### 2. PCB Design/Manufacturing:
- 3D CAD: [Altium Designer](https://www.altium.com/altium-designer)
- Technology: photolithography with 3D SLA Printer [Anycubic Photon](https://www.anycubic.com/products/anycubic-photon-s) and dry film [Ordyl Alpha 350](https://elgaeurope.it/wp-content/uploads/2021/10/Product-Data-Sheet_Alpha300.pdf).
- Components: [STM32F103C8T6](https://www.st.com/en/microcontrollers-microprocessors/stm32f103c8.html), [nRF24L01](https://infocenter.nordicsemi.com/pdf/nRF24L01P_PS_v1.0.pdf?cp=10_4_0_0), OLED 128x64, joystick, servos (MG90s, DS3218mg), motor driver, DC-DC converters.

<!-- components -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/components/components_all.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Electric Components
</div>

<!-- structural diagrams -->
<div class="container">
    <div class="row">
        <div class="col align-self-center">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/structural_diagram_remote_controller1eng.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col align-self-center">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/structural_diagram_manipulator1eng.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Structural diagram of the Remote Controller (left) and the Robotic Arm (right).
</div>

<!-- schematics -->
<div class="container">
    <div class="row">
        <div class="col align-self-center">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/pcb/schematic_remote_manipulator.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Schematics of the Remote Controller (left) and the Robotic Arm (right).
</div>

<!-- PCB CAD -->
<!-- PCB layout of the remote controller -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/pcb/pcb_cad_remote_controller1234.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    PCB layout of the Remote Controller: top (left) and bottom (right) layers with/out ground fill.
</div>

<!-- PCB layout of the manipulator -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/pcb/pcb_cad_manipulator1234.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    PCB layout of the Robotic Arm: top (left) and bottom (right) layers with/out ground fill.
</div>

<!-- mask generation -->
Photolithography requires positive/negative masks with the PCB layout during the exposure stage.<br>
Additionally, there should be an external frame to align the masks before the exposure.
<!-- alignment frame -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/pcb/pcb_mask_manipulator_mech.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Outer frame for visual alignment in the development stage of photolithography (left) and the overal PCB layout w/o ground fill (right).
</div>
<!-- positive -> negative mask conversion -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/pcb/pcb_mask_manipulator_pos2neg.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Top (left) and bottom (right) layers were converted from positive (2nd row) to negative (3rd row) masks due to Ordyl Alpha 350 specifications.
</div>
<!-- color -> black&white -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/pcb/pcb_mask_manipulator_blacknwhite.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Final masks should be black-white due to Anycubic Photon UV integrated light (wavelenght 405nm).
</div>

<!-- photolithography -->
Photolithography process consisted of:
- Substrate (Copper Textolite) Pre-treatment.
- Photoresist Coating: 110℃ heated rollers.
- Exposure: 405nm UV light; 110sec.
- Development: 1% water solution of Na<sub>2</sub>CO<sub>3</sub>; ultrasonic bath; 30-32℃; 24.4mins.
- Hard Bake: 150℃; 2mins.
- Etching: hydrogen peroxide(150g) + lemon acid(30g) + NaCl(5g); 30-32℃; 50mins.
- Via Drill/Connection: mechanical.
- Additional Metallization/Isolation.

<!-- defect development -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/photolithography/photolithogrpahy_development34.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Poor quality photoresist (not Ordyl Alpha 350) resulted in bad results during the development stage.
</div>
<!-- successful sample. full process -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/photolithography/photolithography_manipulator.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    The entire process of photolithography and post-process treatment.
</div>

<!-- final results -->
<div class="container">
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/hardware_remote_controller123.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm-10 align-self-center offset-sm-1">
            {% include figure.html path="assets/img/projects/work/robotic_arm/electrical/hardware_manipulator123.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    The final PCBs of the Remote Controller (top) and the Robotic Arm (bottom). The Remote Controller's PCB was the first trial.
</div>


### 3. Software Development:
- Development Tool: [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html).
- Development Language: C/C++.
<!-- program flow for the remote controller -->
<div class="row">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/robotic_arm/software/algorithm_remote_controller12eng.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Program flow for the Remote Controller. The entire program (left) and the control input reading (right) from buttons/joysticks. 
</div>
<!-- program flow for the robotic arm -->
<div class="row">
    <div class="col align-self-center offset-sm-2">
        {% include figure.html path="assets/img/projects/work/robotic_arm/software/algorithm_manipulator1eng.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Program flow for the Robotic Arm.
</div>


<!-- robotic arm specifications -->
## __Results:__
- DoF: 5
- Mass (kg): 1.5
- Dimensions (mm): 300 x 150 x 200
- Payload (g): 170
- End-effector: Gripper
- Control: Remote
- Input Voltage (V): 7-40
- Programming Language: C/C++
- Cost (₽): 5000
<!-- robotic arm: itself & on mobile platform -->
<div class="container">
    <div class="row">
        <div class="col">
            {% include figure.html path="assets/img/projects/work/robotic_arm/robotic_arm_group.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>