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

