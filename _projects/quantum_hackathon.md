---
layout: page
title: Sustainable Finance in the Quantum Era Hackathon
description: An overview of our winning project in the hackathon.
img: assets/img/illustrative_pitch.jpg
importance: 1
category: work
related_publications: true
---

## Intro

 I was a part of a winning team at the Ultrahack hackathon titled "Sustainable Finance in the Quantum Era". In approximately 36 hours, I and my 4 teammates were able to formulate a business idea and excecute a technical implementation behind the concept. Our solution was a portfolio optimization and prediction platform intended to be integrated into a stock broker's website. We implemented both a classical optimization algorithm and one with Quantum Computing based on a [Nature article](https://www.nature.com/articles/s41598-023-45392-w). We also implemented a prediction tool based on geometric brownian motion and the Monte Carlo method and incorporated impact data and ESG scoring from [The Upright Project](https://www.uprightproject.com/?utm_source=google&utm_medium=search&utm_campaign=brand&utm_term=upright%20project&utm_campaign=CSR+%7C+manual&utm_source=adwords&utm_medium=ppc&hsa_acc=3032378754&hsa_cam=20030909980&hsa_grp=168345597304&hsa_ad=697647931150&hsa_src=g&hsa_tgt=kwd-569608573151&hsa_kw=upright%20project&hsa_mt=e&hsa_net=adwords&hsa_ver=3&gad_source=1&gad_campaignid=20030909980&gclid=CjwKCAiA3-3KBhBiEiwA2x7FdMO5tp6HVncIDfTt4lAR0laSYWvHlmEFc5HWShy0d2cf8XhQX6xVcxoCZUsQAvD_BwE). My main area of responsibility was on the technical implementation and the implementing the research article in practice.



## Techinal implementation



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

  <!-- Previous/Next Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#presentation-carousel" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#presentation-carousel" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
