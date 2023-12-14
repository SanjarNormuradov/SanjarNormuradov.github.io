---
layout: page
title: Robotic Manipulation
description: <b>in Densely Packed Containers</b> <br><br> UW + Amazon Science Hub
img: assets/img/projects/work/amazon_manipulation/robot_pod_003.png
importance: 1
category: 
related_publications: 
---

<a href="https://robotic-manipulation.sciencehub.uw.edu/"><i class="fa-brands fa-amazon"></i></a>

<b>Synthetic Data Generation</b>:

<!-- case 1: success simple -->
<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_success_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_success_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_success_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_success_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_success_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_success_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
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
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/success_simple_0012.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/success_simple_0034.png" title="example image" class="img-fluid rounded z-depth-1" %}
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
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_successsimple3_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_successsimple3_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_successsimple3_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_successsimple3_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_successsimple3_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_successsimple3_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
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
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentsimple_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentsimple_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentsimple_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentsimple_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentsimple_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentsimple_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentsimple_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentsimple_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
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
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentcomplex_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentcomplex_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentcomplex_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentcomplex_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_oversegmentcomplex_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentcomplex_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentcomplex_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentcomplex_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentcomplex_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_oversegmentcomplex_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
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
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_twosameobjects_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_twosameobjects_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_twosameobjects_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_twosameobjects_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_twosameobjects_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_twosameobjects_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
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
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_shift_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_shift_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_shift_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_shift_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/stack_shift_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_shift_0001.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_shift_0002.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_shift_0003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_shift_0004.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/nostack_shift_0005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    simple example. model with stacking: success. model without stacking: failure in tracking
</div>

