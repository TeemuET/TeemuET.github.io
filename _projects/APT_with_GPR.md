---
layout: page
title: Gaussian Process Regression Applied to Atom Probe Tomography Data Reconstruction
description: An overview of my work at the Complex Systems and Materials Group
img: assets/img/GPR_illustration.jpg
importance: 3
category: work
related_publications: true
---

## Introduction
I completed my Bachelor's thesis on the topic of Gaussian Process Regression (GPR) in Atom Probe Tomography (APT) data reconstruction in the summer of 2024 at the Complex Systems and Materials Group at Aalto University’s Department of Applied Physics. This work continued after my thesis and culminated in a research manuscript which is currently under review. A more complete view of the project can be gained from my [Bachelor's thesis](/assets/pdf/BScThesis.pdf).

### Problem
Traditional APT reconstruction relies on geometric algorithms that assume linear ion flight paths. However, physical evaporation is often non-linear and probabilistic. To contextualize the importance of this imaging technique and the motivation for using machine learning, the following short excerpts and figures from my thesis describe the APT process:

> **Atom probe tomography (APT)** is an imaging technique that combines precise sub-nanometer imaging of materials with simultaneous compositional analysis {% cite gault_atom_2021 %}. APT provides a solution to one of the main challenges of material science: understanding the properties of materials at an atomic scale. This level of understanding has become increasingly essential in the development of microelectronics, and APT has seen important application in the development of semiconductors {% cite giddings_industrial_2018 %}. In APT, a specimen of interest is evaporated onto a detector by the method of field evaporation. The resulting data gathered on the detectoris utilized in the spatial and chemical reconstruction of the specimen. Reconstructing the three-dimensional (3D) lattice of the evaporated specimen is a central part in determining the precision and robustness of APT. 

<div class="row">
    <!-- Left column for the 2/3 image -->
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/imaging.png" title="Atom probe imaging setup" class="img-fluid rounded z-depth-1" %}
    </div>
    <!-- Right column for the two stacked 1/3 images -->
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="Example image 1" class="img-fluid rounded z-depth-1 mb-3" %}
        {% include figure.liquid path="assets/img/11.jpg" title="Example image 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An illustration of the atom probe imaging setup (left) and simulated evaporation events on the detector (right).
</div>

> The aim of this thesis is to test and assess the performance of **Gaussian process regression (GPR)** in APT data reconstruction, while providing a thorough mathematical review of GPR. GPR provides a highly flexible and probabilistic method that can capture, in theory, the uncertainty inherent in field evaporation events. The performance of GPR is estimated by performing data reconstruction for two crystallographic specimens with different grain structures, where both specimens have been evaporated with a simulation model that incorporates theorized field evaporation events.

## Manuscript
In the research manuscript this work was refined and extended to comparisons between traditional APT data reconstruction and GPR.

## Source Code
Will be available once published [here]().
