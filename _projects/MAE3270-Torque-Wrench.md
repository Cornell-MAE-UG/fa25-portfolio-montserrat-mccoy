---
layout: project
title: MAE 3270 Torque Wrench
description: Materials Project
technologies: [Autodesk Fusion, Ansys]
permalink: /MAE3270-Torque-Wrench/
---

#### CAD with dimensions
![Photo of deformatiion]({{ "/assets/images/CAD.png" | relative_url }}){: .inline-image-l}
<br>
L is the length from drive to where load applied
<br>
h = width 
<br>
b = thickness
<br>
c = distance from center of drive to center of strain gauge
<br>
<br>

#### Material choice
For my torque wrench, I chose to use AISI 4340 Quenched and Tempered steel because of its high yield strength in bending, its high fatigue resistance at 106 cycles, and its high fracture toughness, allowing it to reach all the safety factors while still permitting a small gauge section to achieve the required ≥ 1.0 mV/V sensitivity at 600 in-lbf. Its high yielding strength allows it to withstand yielding under peak torque and maintain a slim geometry while still meeting the strength requirement, something that lower-strength alloys would not allow without increasing the cross-sectional area. A steel with a lower strength would require a bulkier design, or otherwise risk plastic deformation when applying the torque.  Steel 4340 also has a high fracture toughness that gives it strong resistance against crack propagation. For a tool like a torque wrench that experiences high stress concentrations near the drive and has fillets, this toughness helps prevent brittle failure. 4340 also has high fatigue strength, which is necessary because torque wrenches experience many repeated load cycles when in use.  

#### FEM Results
Maximum normal stress: 85096 
<br>
Strains at the strain gauge: 1150.3 µε
<br>
Deflection of load point: 0.51263 in

![Shaded rendering of earlier version]({{ "/assets/images/maxprincipalstress.png" | relative_url }}){: .inline-image-r style="width: 200px"}
![Shaded rendering of earlier version]({{ "/assets/images/normalstress.png" | relative_url }}){: .inline-image-r style="width: 200px"}
![Shaded rendering of earlier version]({{ "/assets/images/strainsatgaguge.png" | relative_url }}){: .inline-image-r style="width: 200px"}
![Shaded rendering of earlier version]({{ "/assets/images/totalelasticdef.png" | relative_url }}){: .inline-image-r style="width: 200px"}

<section class="image-stack">
  <img src="/assets/maxprincipalstress/.png" alt="Image 1 description">
  <img src="/assets/images/normalstress.png" alt="Image 2 description">
  <img src="/assets/images/totalelasticdef.png" alt="Image 3 description">
  <img src="/assets/images/strainsatgaguge.png" alt="Image 4 description">
</section>


