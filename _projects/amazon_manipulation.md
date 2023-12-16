---
layout: page
title: Robotic Manipulation
description: <b>in Densely Packed Containers</b> <br><br> UW + Amazon Science Hub
img: assets/img/projects/work/amazon_manipulation/robot_pod_003.png
importance: 1
category: Work
related_publications: 
---

<b>Real-world Challenge & Innovative Approach:</b><br>
Revolutionizing Amazon's Fulfillment Centers, our team at the UW + Amazon Science Hub Project <a href="https://robotic-manipulation.sciencehub.uw.edu/">"Robotic Manipulation in Densely Packed Containers"</a> is pioneering the automation of the picking process.

We’re navigating through the complexity of densely stocked bins with an array of items, leveraging Robotic Manipulation, Computer Vision, Sensor Systems, Human-Robot Interaction, and Reinforcement Learning to enhance efficiency and innovate supply chain management.

<!-- Amazon Fulfillment Center -->
<div class="container">
    <div class="row">
        <div class="col">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/amazon_fulfillment_centers_003.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/amazon_fulfillment_centers_005.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/amazon_fulfillment_centers_001.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col">
            {% include figure.html path="assets/img/projects/work/amazon_manipulation/amazon_fulfillment_centers_002.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Real-world scenario in Amazon Fulfillment Centers, where nowadays people perform picking process.
</div>

<!-- Pod Full of Items -->
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/annotation/pod1_stack_lit_collect_001.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Simulation of the real-world scenario at the University of Washington + Amazon Science Hub Manipulation Project.
</div>


During my research assistantship I have accomplished the following results:<br><br>
<b>Synthetic Image Generation:</b><br>
Generated using <a href="https://github.com/owl-project/NVISII">NVISII</a> and <a href="https://blog.research.google/2022/06/scanned-objects-by-google-research.html?_hsenc=p2ANqtz-_rs8c8ci_IJOCKltH56mk4IYZRujwMvzsN0iliEWXRkQgQrs4bDYnsMcNv3-7Kd7J3yGiG">Scanned Objects by Google Research</a>.<br>
Objects:
- incrementally added into scenes, resembling a process of stowing
- randomly chosen from the given train set which do not overlap with the evaluation set
- placed depending on their shape (box, bottle or irregular), the bounding box similarity to the bin
dimensions, and a type of packing
- oriented based on remaining free space, optimality for packing with some randomness to prevent the network from overfitting
<!-- collection of images of items in bins, resolution 1024 -->
<div class="container">
    <div class="col align-self-center offset-sm-2">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_collect_003.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Synthetic bin image generation.
</div>

There might some variations in the images such as
- max number of objects within each scene, and max number of scenes
- objects relative placement (w/ & w/o stacking, partial/full occlusion, shuffled order)
- object transformation (small perturbations in orientations, rotation by 90deg and/or 180deg)
- various bin configuration (fabric texture, size aspect ratios, neighboring bins as a background)
- different view angles and light brightness, representing different scenarios of bin vs camera mounting
<!-- collection of images of items in bins, resolution 256 -->
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_collect_002.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Synthetic bin image variations.
</div>

There are several configurations of stacking items in bins:
- simply introducing new objects without any rearrangement in the previous scene
- adding a new object with shuffling the order of placement of all scene objects
- randomly reorienting the previous objects before adding new one
- a combination of replacement and reorientation

These images are used for training a novel framework <a href="https://arxiv.org/abs/2311.02337">"Discrete-Frame Segmentation and Tracking of Unseen Objects for Warehouse Picking Robots"</a>
<!-- collection of images of stacked items in bins -->
<div class="container">
    <div class="col align-self-center offset-sm-1">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/syn_data/stack_collect_001.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Several configurations of stacking items in bins.
</div>


<b>Evaluation in Real-World Scenarios:</b><br>
The average precision of the model trained on the expanded 140K-image datase has been improved from 0.424 to 0.646 overall,<br>and from 0.336 to 0.573 for stacked bins.<br>
<!-- case 1: success -->
- The new model improves the performance by exluding failures to detect objects placed on top of each other by segmenting them into a single mask.
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/collect_success_simple_12345678.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Model trained on the new dataset(top), and on the old dataset (bottom).
</div>

<!-- case 2: over-segmentation -->
- The new model is less prone to oversegmentation, although it might do so in highly packed bins or for objects of contrasting parts. 
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/collect_oversegment_0012.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Model trained on the new dataset(top), and on the old dataset (bottom).
</div>

<!-- case 3: shift -->
- Both models are not capable of differentiating several identical or similar objects such as cardboard boxes, and therefore fails to track.<br>
Also, as the new model is trained in highly packed bins where thin objects like towels/napkins are placed vertically because of optimality (which is computed according to object vs bin bounding boxes similarity mentioned above) to store and pick, it might oversegment in such scenarios.
<div class="container">
    <div class="row">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/collect_twosameobjects_0012.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="row">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/perception/real_data/eval/28Sep2023/collect_shift_0012.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Model trained on the new dataset(top), and on the old dataset (bottom).
</div>

To increase the accuracy further, we need to improve segmentation and tracking, especially in case of identical objects.<br>
So our team decided to work on improving the architecture instead of refining the training set. And now I’m investigating how to integrate Segment Anything Model (<a href="https://segment-anything.com/">SAM</a>) and/or Visaul Language Models like GPT-4.


<br><b>Reachability Analysis:</b><br>
To find an optimal pod position relative to the robot workstation, I tested the robot's reachability, i.e. moving the end-effector from the home pose (item dropping point) to a pre-grasp pose (one random pose in front of the given bin).
<!-- reachability test visualization -->
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/motion_planning_control/pod_sim/pod1_gripper_midfull_collect_001.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Visualization of the reachability test.<br>
    Red markers mean the poses are unreachable due to kinematic constraints (rotation axes limits or lengths of links). Green - successful motion plan<br>
    1st row depicts currently tested 16 bins. 2nd/3rd rows shows the entire pod
</div>

To run as accurate tests as possible, I started with enhancing simulation environment precision and robustness by revising URDF/Xacro/XML files and creating a single source for all pod models.
<!-- pod models in simulation -->
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/motion_planning_control/pod_sim/pod12_rviz.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Pod models in RViz.<br>
    Gazebo additionally includes collision scenes, which is set up by MoveIt in RViz.<br>
    Pod 1: 13 rows x 4 columns (right). Pod 2: 8 rows x 3 columns (left).
</div>

Then, I restructured the launch process by replacing pod model spawning from a launch file to a Python file, which allowed to run tests for different pod positions (x, y) in `for` loop instead of re-launching the launch file manually each time.<br><br>
All pre-grasp poses used to be perpendicular to a bin face, while in reality objects inside the bin could be picked from different angles too.<br>
So I tried for the end-effector orientation sampling two methods:
- symmetrical sigmoids (unsuccessful because it converged pre-grasp poses to the center)
- modified uniform (which is close to reality as it filters out orientations that might cause collisions with bin walls when the end-effector moves from pre-grasp pose to grasp objects inside the bin).<br><br>
<!-- sigmoid -->
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/motion_planning_control/analysis/mod_sigmoid.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Probability to sample the end-effector orientation as a symmetrical sigmoid function of pre-grasp pose coordinates (x,y) within the bin boundaries (orange).<br>
    Various orientations converge to the center of the bin (x=0), which is not true in reality as peripheral objects could be picked somewhere close to the bin boundaries (x=1).
</div>

Later on, this modified uniform sampling method caused another issue related to collision of the end-effector with a target bin’s walls when the robot moves from home pose to a pre-grasp pose. And the reason was because of 2mm thin bin’s walls which were sometimes skipped.<br>
So I solved the issue by redefining a target link for which the path is computed in MoveIt, increasing C-space discretization and collision-checking frequency in MoveIt motion planning. 


Overall, I came up with analysis of 800 pod poses (400 for each of two pods, with 1 cm step in x,y), and showed that the existing at that time pod position had failure in reachability = 20/1600 while there were some other with 1/1600.<br>
Also, the trend is shifted towards further distances with the pod center close to a plane with the robot's origin (y=0.470m). Corner cases include close positions, but those are with high variance and thus unstable to small disturbances in positions.
<!-- reachability test anaylsis graph -->
<div class="container">
    <div class="col align-self-center">
        {% include figure.html path="assets/img/projects/work/amazon_manipulation/motion_planning_control/analysis/pod12_reach_viridis.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Reachability test results for the current 13x4 pod (above), and the second 8x3 pod (below).<br>
    The current position is highlighted and less than some other possible positions with higher scores.
</div>

For fairness, I should admit the reachability test did not take the picking process (moving from pre-grasp pose to inside the bin) into account due to computational resources vs the problem urgency.<br>
And when we applied the test result in the real world, the x-coordinate was shifted slightly (~ 3-5 cm) towards the robot which is expected.
