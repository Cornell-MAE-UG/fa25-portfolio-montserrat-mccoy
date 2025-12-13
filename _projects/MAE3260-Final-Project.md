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
<u>Data Collection</u>
To model the drill we used a high speed camera to record data of the drill ramping up to full speed. Looking back at the data we were able to use step inputs of the amount of time it took the drill to make one rotation as it ramped up to full speed. From the video, the set of times it took the drill to complete one full rotation in seconds was:
[0.0656, 0.0574, 0.0543, 0.0521, 0.0489, 0.0482, 0.0475, 0.0481, 0.0467, 0.0461, 0.0459, 0.0454, 0.0458, 0.0461, 0.0455]

It is important to note that these times were all measured by hand with a stop watch, and were originally about 8-20 seconds before being transferred into real time. From these numbers the frequency step response and bode plots above were generated. Some other experimental parameters we were able to calculate from the video are:
The rotational speed from the first rotation: 95.8 rad/s (915 RPM)
The steady state rotational speed: 138.1 rad/s (1319 RPM)
Time constant: 0.176 s
Step magnitude/gain: 42.6 rad/s (404 RPM)
Bandwidth 1/T= 5.69 rad/s (0.91 Hz)
<br>
<u>Performance Limits</u>
With these values, the steady state speed ceiling of the drill of 915 RPM and the acceleration limit from the time constant of 0.176s show the max speed of the drill and how long it will take to get there. These values show how quickly the drill reaches usable speed. 
The bandwidth of 0.91 Hz describes the range of input frequencies that the drill can accelerate at before the lag from the time constant begins to take effect. This value describes how quickly the drill can follow changes to input. 
There is a variability of about 0.0023 s per revolution or 6.6 rad/s (65 RPM) in the steady state velocity of the drill. This means that there is either variability with the steady state velocity or with our calculations, probably some combination of both. 	
The fitted first‑order exponential model closely follows the measured speed data, with deviations within ±5%. This confirms that the drill’s ramp‑up can be approximated as a first‑order system, though small discrepancies are expected due to manual timing and load fluctuations.	
Overall, the drill reaches steady‑state speed of 1319 RPM in under one second, with a bandwidth of 0.91 Hz and variability of ±65 RPM. These values define the drill’s performance envelope and can be used to model the drill, for controller design or for comparative analysis of similar systems.
<br>
<u>Bode Plots</u>
<figure style="margin-bottom:20px;">
  <img src="{{ '/assets/images/bode1.png' | relative_url }}" alt="Image 1" style="width:100%;">
  <figcaption style="text-align:center; margin-top:8px; font-size:14px; color:#555;">
    Bode Plot showing open loop magnitude and phase vs input frequency. 
  </figcaption>
</figure>

<figure style="margin-bottom:20px;">
  <img src="{{ '/assets/images/bode2.png' | relative_url }}" alt="Image 2" style="width:100%;">
  <figcaption style="text-align:center; margin-top:8px; font-size:14px; color:#555;">
    Frequency step response graphs in rad/s and RPM showing the speed step response, with a fitted first order curve from the calculated system parameters. 
  </figcaption>
</figure>




