---
layout: page
title: Sustainable Finance in the Quantum Era Hackathon
description: An overview of our winning project in the hackathon.
img: assets/img/illustrative_pitch.jpg
importance: 1
category: work
bootstrap: true
related_publications: true
---

## Intro

 I was a part of a winning team at the Ultrahack hackathon titled "Sustainable Finance in the Quantum Era". In approximately 36 hours, I and my 4 teammates were able to formulate a business idea and excecute a technical implementation behind the concept. Our solution was a portfolio optimization and prediction platform intended to be integrated into a stock broker's website. We implemented both a classical optimization algorithm and one with Quantum Computing based on a [Nature article](https://www.nature.com/articles/s41598-023-45392-w) {% cite buonaiuto_best_2023 %}. We also implemented a prediction tool based on geometric brownian motion and the Monte Carlo method and incorporated impact data and ESG scoring from [The Upright Project](https://www.uprightproject.com/?utm_source=google&utm_medium=search&utm_campaign=brand&utm_term=upright%20project&utm_campaign=CSR+%7C+manual&utm_source=adwords&utm_medium=ppc&hsa_acc=3032378754&hsa_cam=20030909980&hsa_grp=168345597304&hsa_ad=697647931150&hsa_src=g&hsa_tgt=kwd-569608573151&hsa_kw=upright%20project&hsa_mt=e&hsa_net=adwords&hsa_ver=3&gad_source=1&gad_campaignid=20030909980&gclid=CjwKCAiA3-3KBhBiEiwA2x7FdMO5tp6HVncIDfTt4lAR0laSYWvHlmEFc5HWShy0d2cf8XhQX6xVcxoCZUsQAvD_BwE). My main area of responsibility was on the technical implementation and the implementing the research article in practice.

## Techinal details

### Objective

The core problem in sustainable finance is balancing Alpha (returns), Risk, and Impact (beliefs and values of the investor). Our implementation was designed for integration into retail brokerages so that investors could automate this optimization. By leveraging Quantum Computing, we provided a glimpse into the future of high-dimensional portfolio management where classical solvers begin to struggle.

The core of our solution is a Multi-Objective Portfolio Optimization model. While the traditional Markowitz model balances expected return against variance (risk), our platform introduces a third dimension: Net Impact Score (sourced from the Upright Project). The goal is to find an optimal investment allocation vector $x$ that maximizes the objective function that combines expected returns, variance and impact. The optimization problem can be summarized as follows

$$
\begin{aligned}
\max& \quad \mu^T x-q\big(x^T\Sigma x\big)+\gamma \big(Ix)\\
\text{subject to }& \sum_{i=1}^{N} x_i=1,
\end{aligned}
$$

where $\mu$ is the vector of mean asset returns for each asset $i$, $\Sigma$ is the covariance matrix between returns of different assets, $q$ is a parameter expressing the risk attitude of the investor and $\gamma$ a parameter expressing the weight of sustainability relative to financial returns.

### Methods
This optimization problem can be classically solved with Sequential Quadratic Programming (SQP). Brief description.

In the Quantum version we modify the problem into a QUBO as detailed in {% cite buonaiuto_best_2023 %}. This problem is then solved using the VQE...

### Forecasts
The forecasts for mean asset returns were simulated by using the .... model:


## Pitch

You can read our pitch slides here [PDF](/assets/pdf/quantum_hackathon_pitch.pdf) or optionally you can enjoy the slide show below.

<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-2.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-3.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-4.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-5.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-6.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-7.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-8.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-9.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row mt-3 justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/pitch-slide-10.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Source Code

The unpolished version of the source code can be found [here](https://github.com/naapeli/Hanken-Hackathon-2024).
