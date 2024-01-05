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

ROS features:
- Robot's physical components (sensors, actuators, etc) can be abstracted with ROS __nodes__, which contains specific set of operations.
- __ROS Master__ maintains the registry of all the active nodes on a system, allowing nodes to locate one another and communicate.
- ROS Master hosts the __parameter server__ where configuration values and parameters are shared among all nodes.
- ROS nodes can communicate with each other by passing ROS __messages__ over ROS __topics__, so that there exist publisher and subscriber nodes.
- ROS node can publish and be subscribed to __any number of topics__, constantly monitoring the topics to send/receive messages.
- ROS nodes can interact with ROS __services__ on a one-to-one basis, using __request/response__ messages.
- ROS provides a __RQT graph__ tool to show compute graph of nodes, i.e. nodes and their means of communication (services, topics)
<br>

ROS Master process is responsible for:
- providing naming and registration services to other running nodes.
- tracking all publishers and subscribers.
- aggregating log messages generated by the nodes.
- facilitating connections between nodes. 

ROS basic commands:
- `roscore` - start ROS Master process.
- `rosrun <package_name> <executable_node_name>`
- `rosnode list` - list of active ROS nodes.
- `rostopic list` - list of active ROS topics.
- `rostopic info </rostopic/name>` - print info (message type, publishers/subscribers) about a specific ROS topic.
- `rosmsg info <rosmsg/type>` - print detailed info about the content of a specific ROS message.
- `rostopic echo </rostopic/name>` - print specific ROS topic's published messages in real time.