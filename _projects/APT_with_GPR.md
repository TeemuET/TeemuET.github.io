---
layout: page
title: Gaussian Process Regression Applied to Atom Probe Tomography Data Reconstruction
description: An overview of my work at the Complex Systems and Materials Group
img: assets/img/figure04_single_crystal_err.svg
importance: 3
category: work
related_publications: true
---

## Introduction

In the summer of 2024, I joined the Complex Systems and Materials Group at Aalto University to write my Bachelor's thesis on applying Gaussian Process Regression (GPR) to Atom Probe Tomography (APT). That initial research evolved into a much larger project, leading to a first-authored paper published in *Microscopy and Microanalysis* (August 2026).

You can read the full, peer-reviewed article [here](https://doi.org/10.1093/mam/ozag027). 

However, since the manuscript is quite dense, I wanted to provide a more relaxed highlight reel here. Below are some of the core concepts and cool visual results from the project!

### The Problem: The Ions Don't Fly Straight

Atom probe tomography (APT) is an imaging technique that provides sub-nanometer, 3D compositional analysis of materials {% cite gault_atom_2021 %}. It is useful in modern material science and semiconductor development {% cite giddings_industrial_2018 %}. 

In APT, we evaporate a specimen onto a detector and try to reverse-engineer where the atoms originally came from. Traditional reconstruction algorithms (like the standard WFOV method) assume these atoms fly in perfectly straight, predictable lines. In reality, atoms are messy. They "roll up" and move laterally across the surface before evaporating, creating non-linear, probabilistic flight paths that distort the final 3D image. Below is an illustration of the imaging set up and of simulated evaporation events on the detector. 

<div class="row mt-3 uniform-image-grid">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/imaging.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/GB_detector_hits_roll.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/GB_detector_map_roll.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An illustration of the atom probe imaging setup (left) and simulated evaporation events on the detector (right).
</div>


### The Solution: Probabilistic Machine Learning

<div class="float-right ml-4 mb-3 rounded z-depth-1 p-2" style="width: 35%; min-width: 250px; background-color: #ffffff;">
    {% include figure.liquid path="assets/img/figure02_workflow.svg" class="img-fluid" %}
    <div class="caption mt-2 mb-0" style="font-size: 0.85em; line-height: 1.3;">
        Our reconstruction workflow: Fed simulated detector hits into a multitask GPR model running on high-memory GPUs.
    </div>
</div>

To address the geometric limitations of standard algorithms, we introduced a probabilistic machine learning approach using **Gaussian Process Regression (GPR)**. You can view our reconstruction workflow on the right.

To handle the massive datasets inherent to APT, we scaled the GPR model training on an HPC cluster utilizing high-memory GPU acceleration.

### Case Study 1: The Single Crystal

We first tested the model on a simulated single-crystal specimen. In the heatmap below, darker colors mean the atom was placed almost exactly where it belongs, while yellow indicates higher error. 

<div class="row mt-3">
    <div class="col-sm-10 mt-3 mt-md-0 mx-auto">
        {% include figure.liquid path="assets/img/figure04_single_crystal_err.svg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    (a) The reconstructed crystal. (b) A zoomed-in look at a specific surface terrace. (c) The error distribution proving GPR (blue) had significantly smaller errors than the traditional WFOV method (orange). Note the logarithmic scale!
</div>

As you can see in the graph on the right, the GPR model's error distribution was nearly two orders of magnitude better than the traditional algorithm. 

But to really prove our model worked, we needed to look inside the crystal structure. We extracted a tiny 3D slice (a voxel) from the apex of the tip to see if the GPR model successfully rebuilt the actual atomic planes:

<div class="row mt-3">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/figure05_voxels.svg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Zooming in on the atomic planes: (a) The original lattice, (b) our GPR reconstruction, and (c) the traditional WFOV reconstruction.
</div>

The traditional method (c) bends and distorts the atomic planes due to the non-linear evaporation paths. Our GPR model (b) learned to compensate for those distortions, keeping the planes flat and perfectly preserving the long-range crystallographic order (which we verified using the Fourier transforms in d, e, and f).

---

## Case Study 2: Grain Boundaries in Polycrystals

Homogeneous, perfect crystals are relatively easy, but material scientists actually care about defects. Hence, we also tested a specimen with a grain boundary, that is, two differently oriented crystal structures joined together at a grain boundary.

<div class="row mt-3">
    <div class="col-sm-9 mt-3 mt-md-0 mx-auto">
        {% include figure.liquid path="assets/img/figure07_polycrystalline.svg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Reconstructing a polycrystalline specimen. The highest errors are strictly isolated to the chaotic grain boundary interface (the yellow stripe).
</div>


<div class="float-right ml-4 mb-3 rounded z-depth-1 p-3" style="width: 35%; min-width: 250px; background-color: #ffffff;">
    
    <!-- Top Image -->
    {% include figure.liquid path="assets/img/figure09_grains.svg" class="img-fluid mb-3" %}
    
    <!-- Bottom Image -->
    {% include figure.liquid path="assets/img/figure10_gb.svg" class="img-fluid" %}
    
    <!-- Shared Caption -->
    <div class="caption mt-3 mb-0" style="font-size: 0.85em; line-height: 1.3;">
        <strong>Top:</strong> Voxels taken from the two different grain orientations.<br>
        <strong>Bottom:</strong> A voxel taken directly from the chaotic grain boundary interface.
    </div>
</div>

Even with the chaotic lattice mismatch at the grain boundary, the GPR model successfully reconstructed the specimen. 

When we zoom into the voxels for this specimen, you can see how the differently oriented crystals meet. The model had to reconstruct two entirely different crystal orientations simultaneously, alongside the chaotic interface where they meet.

By treating Atom Probe Tomography as a statistical machine learning problem rather than a pure geometry problem, we were able to improve spatial accuracy.

---

## Challenges & Limitations

While GPR vastly outperformed traditional geometric reconstruction, this approach comes with its own set of challenges that need to be solved before it could be utilized for experimental data:

* **Scalability:** Exact Gaussian Process Regression scales poorly with dataset size ($O(N^3)$ complexity). Our current models were limited to 200k–500k atoms and required an 80 GB GPU running for 14 hours. Scaling this to the millions of atoms found in real APT datasets will require approximate methods like Sparse GPR or inducing-point techniques.
* **Hyperparameter Rigidity at Boundaries:** We found that a single smoothness parameter (the Matérn $\nu$) struggled slightly right at the grain boundary. Because the lattice mismatch causes a dramatic, abrupt change in the data's smoothness, a stationary kernel can't adapt perfectly to that highly localized chaos, leaving a thin layer of higher error. 
* **Ground Truth::** Right now, the model learns from a known simulated ground truth. To deploy this on pure, unknown experimental data, we would likely need to use amortized inference, i.e., training neural networks to approximate the GPR posterior so they can recognize statistical signatures across entirely new crystallographic orientations.

Despite these hurdles, treating APT as a probabilistic inverse problem rather than a rigid geometric one opens the door to more accurate data-driven reconstructions.
