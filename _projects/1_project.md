---
layout: page
title: Robotic Manipulation
description: <b>in Densely Packed Containers</b> <br><br> UW + Amazon Science Hub
img: assets/img/projects/work/amazon_manipulation/pod_arm.png
importance: 1
category: Work
related_publications: 
---
<a href="https://robotic-manipulation.sciencehub.uw.edu/"><i class="fa-brands fa-amazon"></i></a>

<b>Synthetic Data Generation</b>:

<!-- case 1: success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_success_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_success_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_success_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_success_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_success_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_success_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    model with stacking: success. model without stacking: failure in segmentation (over-segmentation) and tracking
</div>

<!-- case 2: success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_successsimple2_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_successsimple2_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_successsimple2_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_successsimple2_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_successsimple2_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_successsimple2_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in segmentation (under-segmentation) and tracking
</div>

<!-- case 3: success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_successsimple3_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_successsimple3_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_successsimple3_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_successsimple3_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_successsimple3_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_successsimple3_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in tracking
</div>

<!-- case 4: success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentsimple_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentsimple_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentsimple_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentsimple_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentsimple_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentsimple_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentsimple_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentsimple_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in tracking
</div>

<!-- case 5: success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentcomplex_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentcomplex_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentcomplex_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentcomplex_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_oversegmentcomplex_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentcomplex_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentcomplex_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentcomplex_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentcomplex_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_oversegmentcomplex_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in tracking
</div>

<!-- case 6 success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_twosameobjects_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_twosameobjects_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_twosameobjects_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_twosameobjects_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_twosameobjects_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_twosameobjects_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in tracking
</div>

<!-- case 7 success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_shift_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_shift_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_shift_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_shift_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_shift_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_shift_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_shift_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_shift_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_shift_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/nostack_shift_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in tracking
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal its glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
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
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
