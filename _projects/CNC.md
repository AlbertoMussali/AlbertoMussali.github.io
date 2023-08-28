---
layout: distill
title: 5-Axis CNC Program Design
description: Design and Simulation of 5-Axis Machining Process for Complex Part
img: /assets/img/Proj_CNC/bg.jpg
importance: 1
category: Tech
related_publications:
bibliography: Proj_EEG.bib
noDistHeader: true
---

# Design and Simulation of 5-Axis Machining Process for Complex Part


<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/bg.jpg" title="d" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Welcome to a detailed exploration of a  technical project that delves into the intricacies of designing and simulating a complex 5-axis machining process. Our objective was to craft a comprehensive process that effectively machines a sophisticated part, exploring the realms of geometry, material properties, tool selection, and simulation.

## Introduction

At the heart of this project lay the challenge of creating a 5-axis NC machining process for a complex part using Siemens NX and verifying it through simulation using Vericut on a Haas UMC750 vertical 5-axis machining center. This intricate part comprised diverse features such as fillets, chamfers, slanted walls, pockets, and closed angle corners, all crafted from Al 6061 material. The project's core objectives encompassed tool selection, fixture design, optimal machining sequence in NX, and a meticulous comparison of the simulated part with the original design.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/part.png" title="The part" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The ultimate goal: manufacture this part using a 5-axis CNC.</div>

## Model Review

Diving into the dimensions and features of the part, we encountered a square base topped with a cylinder and an intricate cup-like feature. This feature was adorned with ellipsoidal pockets, circular pockets, and precise chamfers. Each dimension and curvature was meticulously detailed to ensure accuracy and efficiency throughout the machining process.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/analyzePart.png" title="Part Review" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Reviewing the part's details to guide tool selection.</div>

## Fixture and Tools

To ensure our machining endeavors were precise and efficient, we selected the Kurt MaxLock 5-Axis Vise – PF440D fixture, facilitating secure clamping on the Haas UMC 750 machine table. Our tool selection from Kennametal in Machining Cloud was tailored to suit the challenging characteristics of Al 6061. Tools like AADE Double Rake Flute Form, KOR5TM DA 5 Flutes, DUO-LOCKTM MaxiMetTM ABBE Ball Nose, and others were harnessed to ensure optimal material removal and surface finish.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/chtoovi.png" title="Chuck Tool Vise" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">An example of the chuck, tool, and vise selection based on the identified features.</div>

## Machining Process Overview

Our journey through the machining process was punctuated with a series of operations, each meticulously tailored to tackle specific geometries and features of the part. From cavity milling to roughing and finishing of walls, pockets, and chamfers, we navigated the intricate landscape of the part's geometry. Every tool, pass, and feed rate were strategically chosen to ensure precision and efficiency.

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/tp_design.png" title="Toolpath design" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/tp_achieved.png" title="Preliminary toolpath simulation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Example of a designed and simulated toolpath for a roughing operation.</div>

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/deform_1.png" title="Preliminary deformation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Preliminary check of achieved material removal and evaluation of tolerances.</div>

## Vericut Simulation

Vericut became our testing ground, where our meticulously designed NC program and tools were put to the test. Through simulation, we confronted and resolved a range of challenges, from tool-path optimization to post-processing issues. In this virtual realm, we witnessed the fruition of our design, learning from collisions, gouges, and damages that helped us fine-tune our approach.

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/sim1.png" title="Simulation" class="img-fluid rounded z-depth-1" %}
    </div>    
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_CNC/sim2.png" title="Simulation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Simulating the machining center, vise, tools, chucks, and toolpaths simultaneously in Vericut.</div>

## Conclusion

In the end, our journey through this technical project illuminated the complexities of 5-axis machining. We navigated a terrain that demanded deep technical knowledge, careful design considerations, and thorough simulations. Our project demonstrated not only the intricacies of designing a machining process but also the value of meticulous planning and the iterative nature of problem-solving in the realm of precision manufacturing. Through it all, we uncovered the vital connection between theory, design, simulation, and practice, ultimately enriching our understanding of this intricate art of machining.