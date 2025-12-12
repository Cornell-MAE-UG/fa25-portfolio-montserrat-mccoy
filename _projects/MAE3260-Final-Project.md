---
layout: project
title: Drilling Down Into the Dynamics, How Feedback Keeps the Bit from Having a Fit
description: System Dynamics Project
technologies: [MATLAB]
image: /assets/images/drill.png
permalink: /MAE3260-FinalProject/
---


For this project, my group decided to dissect and model a drill. A physical dissection allowed us to directly connect course concepts to a tangible device that a lot of us use in our work on project teams. We chose the drill specifically as it connects electrical and mechanical subsystems together, like the DC motor, gear train, and clutch. Within the drill system, we developed an ODE model and then then use this to analyze the transient response through a step change in input and/or load, and investigate the open loop response via a simple experimental set-up under no load. 

### Dissection
We began this exploration by dissecting the drill, with the goal of closely examining the physical components to map them to the parameters that may appear in the ODE based on the DC motor models we have looked at in class and in Lab 1. During this process, we removed half of the drill casing and pressed the trigger switch to observe how each component moved. To help us name the components and learn more about them, we followed a labeled image that looked similar to our drill.  Once we triggered the drill, it was easy to identify the components that rotated, including the windings, rotor, gear train, and chuck. We also observed what the wires from the trigger switch connected to in order to understand how the electrical and mechanical components interacted with each other. After this first inspection, we took apart the individual parts to examine them more closely. We observed the brushes, windings, planetary gear systems, gear grease, and chuck. As we advanced through each component, we filled out the table below to map each component to the ODE variables we learned about in the semester, identify the type, and in what ODE it might show up. This set us up to later model the system as two coupled ODEs. 
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="{{ '/assets/images/dissection.png' | relative_url }}"
       alt="Description"
       style="width: 100%;">

  <figcaption style="margin-top: 8px; font-size: 14px; color: #555;">
    Dissection results.
  </figcaption>
</figure>


### Modeling
<u>ODEs</u>
<br>
After dissecting the drill, we proceeded to model it as a coupled electromechanical system where the electrical subsystem is composed of the trigger circuit and motor, while the mechanical subsystem includes the rotor, gear train, and chuck. To capture the behavior of the drill, we came up with two differential equations, one for each subsystem. The electrical ODE follows Kirchoff’s Voltage Law while the mechanical ODE follows Newton’s second law in rotation. These ODEs are coupled, showing how the input voltage v generates the motor torque Tm, and the torque yields the rotational speed ω. 
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="{{ '/assets/images/odes.png' | relative_url }}"
       alt="Description"
       style="width: 60%;">

  <figcaption style="margin-top: 8px; font-size: 14px; color: #555;">
    ODE derivation.
  </figcaption>
</figure>
<br>
<u>State Space</u>
<br>
In order to track how the internal states of the drill, namely i(t) and ω(t) , change with time, we derived a state space model of the system. This allowed us to understand how the voltage creates current, the current creates the motor torque, and the torque accelerates the drill.
<figure style="text-align: center; margin-bottom: 20px;">
  <img src="{{ '/assets/images/statespace.png' | relative_url }}"
       alt="Description"
       style="width: 60%;">

  <figcaption style="margin-top: 8px; font-size: 14px; color: #555;">
    State space model derivation.
  </figcaption>
</figure>

### Open-Loop
Aenean tincidunt aliquam arcu, in euismod dui dapibus eu. In placerat, mi et ultrices consequat, quam ligula cursus mauris, in semper neque nibh at est. Maecenas hendrerit dignissim porta. Phasellus nec fringilla dolor. Etiam efficitur nisi sit amet velit pharetra feugiat. Etiam ultrices turpis at leo semper, eleifend scelerisque neque malesuada. Aliquam molestie congue rhoncus. Donec blandit neque dolor, nec tristique mi pretium ac. Mauris tincidunt ullamcorper magna, nec pellentesque mi sagittis quis.


