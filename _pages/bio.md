---
layout: profiles
permalink: /bio/
title: bio
description: Biography of Hafizul Abdullah
nav: true
<!--nav_order: 2-->

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - align: right
    image: withMySV.jpg
    content: bio-01.md
    image_circular: false # crops the image to make it circular
    more_info: <!--<p>caption if necessary</p>-->

  - align: left
    image: shortcourse.jpg
    content: bio-02.md
    image_circular: false # crops the image to make it circular
    more_info: <!--<p>caption if necessary</p>-->

  - align: right
    image: jomLaunch4.jpg
    content: bio-03.md
    image_circular: false # crops the image to make it circular
    more_info: <!--<p>caption if necessary</p>-->

  - align: right
    image: 
    content: bio-04.md
    image_circular: false # crops the image to make it circular
    more_info: <!--<p>caption if necessary</p>-->
---

<h3>Gallery</h3>
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/g1.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/g2.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/g3.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/g4.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/movingFwd.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    “A ship in harbour is safe, but that is not what ships are built for.” - John A Shedd, 1928.
</div>
