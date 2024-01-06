---
layout: page
title: Robotics Software Engineer
description: <b>Udacity Nanodegree</b>
img: assets/img/projects/course/udacity_robotics_swe/course_icon.png
importance: 1
category: Course
related_publications: 
---

## Curriculum:
### 1. Introduction to Robotics
Essential elements of Robotics:
1. __Perception__ through sensors (RGB-D camera, LIDAR, RADAR, encoder, GPS, IMU, microphone, thermometer, barometer, etc).
2. __Decision Making__ by anaylzing sensor measurements (color, distance, position, relative coordinates, acceleration, sound, temperature, pressure, etc).
3. __Action__ using actuators (linear / rotary, electric / pneumatic / hydraulic / magnetic / thermal), and other commands (communicate, measure, etc).

### 2. Gazebo World
Gazebo features:
1. __Dynamics Simulation:__ Model a robot's dynamics with a high-performance physics engine.
2. __Advanced 3D Graphics:__ Render your environment with high-fidelity graphics, including lighting, shadows, and textures.
3. __Sensors:__ Add sensors to your robot, generate data, and simulate noise.
4. __Plugins:__ Write a plugin to interact with your world, robot, or sensor.
5. __Model Database:__ Download a robot or environment from Gazebo library or build your own through their engine.
6. __Socket-Based Communication:__ Interact with Gazebo running on a remote server through [socket-based](https://en.wikipedia.org/wiki/Network_socket) communication.
7. __Cloud Simulation:__ Run Gazebo on a server and interact with it through a browser.
8. __Command Line Tools:__ Control your simulated environment through the command line tools.
<br>

Components involved in running an instance of a Gazebo simulation:
1. __Gazebo Server:__
    ```
    $ gzserver
    ```
    It is responsible for parsing the description files related to the scene we are trying to simulate, as well as the objects within. It then simulates the complete scene using a physics and sensor engine.
2. __Gazebo Client__
    ```
    $ gzclient
    ```
    It provides the very essential Graphical Client that connects to the __gzserver__ and renders the simulation scene along with useful interactive tools. While you can technically run __gzclient__ by itself, but it does nothing at all (except consume your compute resources) as it does not have a __gzserver__ to connect to and receive instructions from.<br>
    It is a common practice to run __gzserver__ first, followed by __gzclient__, allowing some time to initialize the simulation scene, objects within, and associated parameters before rendering it. But it could be combined with
    ```
    $ gazebo
    ```
3. __World Files__
    ```
    $ gazebo <yourworld>.world
    ```
    A __world__ file in Gazebo contains all the elements in the simulated environment. These elements are your robot model, its environment, lighting, sensors, and other objects. It is formatted using the __Simulation Description Format__ ([SDF](http://sdformat.org/spec?ver=1.6&elem=world)) such as
    ```
    <?xml version="1.0" ?>
    <sdf version="1.5">
        <world name="default">
            <physics type="ode">
            ...
            </physics>
            
            <scene>
            ...
            </scene>

            <model name="box">
            ...
            </model>

            <model name="sphere">
            ...
            </model>

            <light name="spotlight">
            ...
            </light>

        </world>
    </sdf>
    ```
4. __Model Files__<br>
    For simplification, you must create a separate __SDF__ file of your robot with exactly the same format as your __world__ file. This __model__ file should only represent a single model (ex: a robot) and can be imported by your __world__ file. The reason why you need to keep your model in a separate file is to use it in other projects. To include a __model__ file of a robot or any other model inside your __world__ file, you can add the following code to the __world’s SDF__ file:
    ```
    <include>
        <uri>model://model_file_name</uri>
    </include>
    ```
5. __Environment Variables__<br>
    There are many environment variables that Gazebo uses, primarily to locate files (world, model, …) and set up communications between gzserver and gzclient such as `GAZEBO_MODEL_PATH:` - a list of directories where Gazebo looks to populate a model file.
6. __Plugins__<br>
    To interact with a world, model, or sensor in Gazebo, you can write plugins. These plugins can be either loaded from the command line or added to your __SDF__ world file. Include the path to your custom plugins with
    ```
    $ export GAZEBO_PLUGIN_PATH=${GAZEBO_PLUGIN_PATH}:/path/to/compiled/files/of/your/custom/plugins
    ```
#### Project1: Build My World <a href="https://github.com/SanjarNormuradov/RoboticsSoftwareEngineer_Project1"><i class="fa-brands fa-github"></i></a>
<!-- Gazebo world -->
<div class="container">
    <div class="row">
        <div class="align-self-center">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/project1_gazebo_world.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

### 3. ROS Essentials
ROS is an open-source software framework for robotics development. <br>
It is not an operating system in the typical sense. But like an OS, it provides a means of communicating with hardware. <br>
It also provides a way for different processes to communicate with one another via message passing. <br>
Lastly, ROS features a slick build and package management system called __catkin__, allowing you to develop and deploy software with ease. <br>
ROS also has tools for visualization, simulation, and analysis, as well as extensive community support and interfaces to numerous powerful software libraries.<br>

__ROS features__:
- Robot's physical components (sensors, actuators, etc) can be abstracted with ROS __nodes__, which contains specific set of operations.
- __ROS Master__ maintains the registry of all the active nodes on a system, allowing nodes to locate one another and communicate.
- ROS Master hosts the __parameter server__ where configuration values and parameters are shared among all nodes.
- ROS nodes can communicate with each other by passing ROS __messages__ over ROS __topics__, so that there exist publisher and subscriber nodes.
- ROS node can publish and be subscribed to __any number of topics__, constantly monitoring the topics to send/receive messages.
- ROS nodes can interact with ROS __services__ on a one-to-one basis, using __request/response__ messages.
- ROS provides a __RQT graph__ tool to show compute graph of nodes, i.e. nodes and their means of communication (services, topics)
<br>

__ROS Master__ process is responsible for:
- providing naming and registration services to other running nodes.
- tracking all publishers and subscribers.
- aggregating log messages generated by the nodes.
- facilitating connections between nodes. 

__ROS basic commands__:
- `$ roscore` - start ROS Master process.
- `$ rosrun <package_name> <executable_node_name>`
- `$ rosnode list` - list of active ROS nodes.
- `$ rostopic list` - list of active ROS topics.
- `$ rostopic info </rostopic/name>` - print info (message type, publishers/subscribers) about a specific ROS topic.
- `$ rosmsg info <rosmsg/type>` - print detailed info about the content of a specific ROS message.
- `$ rostopic echo </rostopic/name>` - print specific ROS topic's published messages in real time.
- `$ rosparam set </parameter/name> <value>` - set the ROS parameter

`$ roslaunch <package_name> <filename>.launch` allows to:
- launch the ROS Master and multiple nodes
- set default parameters on the parameter server
- automatically re-spawn processes that have died

`$ rosdep` tool will check for a package's missing dependencies, download them, and install them.<br>
`$ rosdep check <package_name>` - check for missing dependencies in a ROS package.<br>
`$ rosdep install -i <package name>` - install packages.<br>

__ROS package__ directory structure:
- scripts (python executables)
- src (C++ source files)
- msg (for custom message definitions)
- srv (for service message definitions)
- include (headers/libraries that are needed as dependencies)
- config (configuration files)
- urdf (Universal Robot Description Files)
- meshes (CAD files in .dae (Collada) or .stl (STereoLithography) format)
- worlds (XML like files that are used for Gazebo simulation environments)

__ROS Publishers & Subscribers:__
```
ros::Publisher pub1 = n.advertise<message_type>("/topic_name", queue_size);
pub1.publish(msg);

ros::Subscriber sub1 = n.subscribe("/topic_name", queue_size, callback_function);
void callback_function(package_name::ServiceName::Request& req, package_name::ServiceName::Response& res) {}
```

__ROS Services:__
```
ros::ServiceServer service = n.advertiseService(`service_name`, handler);
ros::ServiceClient client = n.serviceClient<package_name::service_file_name>("service_name");
client.call(srv);  // request a service 
```
`$ rosservice call <service_name> “request”` - service call
`$ rossrv show <service_name>` - print detailed info (request/response message types) about the service

[ROS Cheatsheet (Download PDF)](https://github.com/ros/cheatsheet/releases/download/0.0.1/ROScheatsheet_catkin.pdf)

#### Project2: Go Chase It <a href="https://github.com/SanjarNormuradov/RoboticsSoftwareEngineer_Project2"><i class="fa-brands fa-github"></i></a>
<!-- Gazebo world -->
<div class="container">
    <div class="row">
        <div class="align-self-center">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/project2_go_chase_it.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

### 4. Localization
Types of localization problems, given a known map of the environment:
- __Local Localization (Position Tracking)__, when the robot has an initial pose and continuously updated this estimate as it moves.
- __Global Localization (Global Pose Estimation)__, when the robot has no initial pose and must determine its location from scratch.
- __Kidnapped Robot Problem__, when the robot has no initial pose and can be moved to unknown location at any time without warning.

__Markov Properties__ in terms of Localization in Robotics:
- static world.
- noise in sensor readings and motion commands independent of the noise from previous readings and movements.
- perfect model with no approximation errors, matching the actual dynamics and sensing of the robot.
- estimation of the current pose depends only on the previous belief and current action, and not on the sequence of events that preceded it.
- observation (sensor measurement) depends only on the current estimated pose, and not on the sequence of events that preceded it.

__Markov Localization__, based on Markov Properties above, maintains a belief distribution (probability distribution) over the set of all possible states (robot's poses) and updates this belief according to sensor measurements and motion commands. It could be implemented depending on the specific requirements of the environment and the robot's sensors with:
- __Kalman Filters__ (vanilla, Extended, Unscented) - a type of Bayesian filter that assumes the robot's (non-)linear dynamic model and the measurements are subject to Gaussian noise. Computationally efficient.
- __Histogram Filters__ - a type of non-parametric Bayesian filter that uses discretized representation of the state space. The belief about the robot's pose is represented as a probability distribution over this grid. Limited to discretized thus less flexible for continous spaces, and computationally inefficient for high-dimensional spaces.
- __Particle Filters__ (Monte-Carlo Localization) - a type of non-parametric Bayesian filter that doesn't assume any specific distribution (like Gaussian in Kalman filter), thus can represent complex and irregular distributions modelling non-linear and non-Gaussian processes. Set of particles is used to represent the belief distribution. Computationally heavy.