---
layout: page
title: Investigation into Online Calibrated Bayesian Optimization
description: An overview of my work at the Probabilistic Machine Learning Group, Summer 2025.
img: assets/img/online_calib_illustration.jpg
importance: 2
category: work
related_publications: true
---

## Introduction
During the summer of 2025, I served as a Research Assistant within the **Probabilistic Machine Learning Group** at Aalto University’s Department of Computer Science. Working under the supervision of Prof. Samuel Kaski. and doctoral student Marshal Sinaga, my research focused on enhancing the robustness of **Bayesian Optimization (BO)**. Specifically, I investigated how model calibration and conformal prediction could be used to provide more reliable uncertainty quantification during the optimization of expensive black-box functions.

The fundamental objective in BO is to find the global optimum of an expensive-to-evaluate black-box function

$$
x^*=\arg \max_{x\in\mathcal{X}} f(x).
$$

The black-box function $f$ is approximated with a surrogate model (most often a Gaussian Process (GP)) which is iteratively updated as new data points are sampled via an **acquisition function**. Acquisition functions balance the exploration-exploitation trade-off. That is, we must exploit regions where the surrogate predicts high objective values while simultaneously exploring regions with high predictive uncertainty where a global optimum might remain hidden. In this context, accurate uncertainty quantification is essential for decision-making and the performance of BO. **My research specifically addressed how to guarantee BO performance bounds even under model misspecification, primarily by exploring the trade-off between calibration and sharpness. While the project involved a deep dive into the literature of conformal prediction, my core experimental work focused on implementing and evaluating online calibration strategies.**

## Research Questions
After a comprehensive literature review, the research shifted toward addressing specific gaps in how online calibration affects optimization performance. My work aimed to resolve the following three questions:
* **Calibration vs. Performance**: How are calibration, sharpness, and proper scores fundamentally connected to Bayesian Optimization (BO) performance? 
* **Methodological Advancements**: Is the new online method proposed by Deshpande et al. (2024) {% cite pmlr-v238-deshpande24a %} fundamentally different from the older methods that sparked initial critiques of recalibrated BO?
* **Optimization Focus**: Ultimately, what should the focus be (calibration, sharpness or a balance between the two) to achieve superior BO performance?

## Presentation
For a more complete view of the project, you can read my final presentation slides here [PDF](/assets/pdf/onlineCalib_presentation.pdf) or view them below.

<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-4.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-5.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-6.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-7.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-8.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-9.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-10.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-11.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-12.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-13.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-14.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-15.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-16.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-17.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/slide-18.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Source Code

The repository for the experiment framework is available [here](https://github.com/TeemuET/online-calibrated-bo-experiments). The repository builds on the work by Foldager et al. {% cite pmlr-v216-foldager23a %}.