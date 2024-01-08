---
layout: page
title: Robotics Software Engineer
description: <b>Udacity Nanodegree</b>
img: assets/img/projects/course/udacity_robotics_swe/course_icon.png
importance: 1
category: Course
related_publications: 
---
Notes are based on [Robotics Software Engineer Udacity Nanodegree](https://www.udacity.com/course/robotics-software-engineer--nd209) 
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

__ROS PublishAndSubscribe Class Template:__
```
#include <ros/ros.h>

class PublishAndSubscribe
{
public:
    PublishAndSubscribe()
    {
        // Define publisher's topic "/published_topic"
        pub_ = n_.advertise<PUBLISHED_MESSAGE_TYPE>("/published_topic", 1);

        // Define subscriber's topic "/subscribed_topic" and declare its callback function
        sub_ = n_.subscribe("/subscribed_topic", 1, &PublishAndSubscribe::callback, this);
    }

    // Define subscriber's callback function
    void callback(const SUBSCRIBED_MESSAGE_TYPE& input)
    {
        PUBLISHED_MESSAGE_TYPE output;
        //.... do something with the input and generate the output...
        pub_.publish(output);
    }

private:
    ros::NodeHandle n_; 
    ros::Publisher pub_;
    ros::Subscriber sub_;

}; // End of class PublishAndSubscribe

int main(int argc, char **argv)
{
    // Initialize ROS node "publish_and_subscribe"
    ros::init(argc, argv, "publish_and_subscribe");

    // Create an instance of PublishAndSubscribe class that will take care of everything
    PublishAndSubscribe SaPObject;

    // Check for an incoming message to the subscriber, or for a service request for the server
    ros::spin();

    return 0;
}
```

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
- __Kalman Filters__ (standard, Extended, Unscented) - a type of Bayesian filter that assumes the robot's (non-)linear dynamic model and the measurements are subject to Gaussian noise. Computationally efficient.
- __Histogram Filters__ - a type of non-parametric Bayesian filter that uses discretized representation of the state space. The belief about the robot's pose is represented as a probability distribution over this grid. Limited to discretized thus less flexible for continous spaces, and computationally inefficient for high-dimensional spaces.
- __Particle Filters__ (Monte-Carlo Localization) - a type of non-parametric Bayesian filter that doesn't assume any specific distribution (like Gaussian in Kalman filter), thus can represent complex and irregular distributions modelling non-linear and non-Gaussian processes. Set of particles is used to represent the belief distribution. Computationally heavy.

#### __Kalman Filter__
Given the proper initial estimate and Gaussian noise in measurments and movements\
Pros:
- computationally efficient - no need for large-scale numerical simulations to make an estimate, as it uses linear equations.
- sequential processing - data coming continuously in online systems updates sequentially the estimate at each step.
- sensor fusion - data from multiple sensors (GPS, LIDAR, etc) weighed according to their variance (more accurate measurement is given more weight) and combined together result in Gaussian distribution with a minimized overall variance.

Cons:
- non-linear systems needs modifications (EKF, UKF).
- non-Gaussian noise needs more flexible pose estimate.
- poor initialization of the base estimate result in inaccurate future estimates.

__Types of sensors used in Kalman Filter:__
- Inertial Measurement Unit (IMU): 3-DoF Gyroscope for angular velocity + 3-DoF Accelerometer for linear acceleration measuring.<br> $$ x = \int\int g \, dt $$. The error from double integration might accumulate over time. Check the drift. 
- Inertial and Magnetic Measurement Unit (IMMU): 6-DoF IMU + 3-DoF Magnetometer for magnetic field measuring.  
- Rotary Encoders: measures wheels velocity and position. $$ x = \int v \, dt $$. Wheel slippage and lockup would lead to inaccurate and noisy measurments.<br> High-resolution (CPR: counts per revolution) encoders are more sensitive to slippage.
- Vision Cameras (Stereo, RGB-D), LIDAR: measures distance to obstacles.<br> Light conditions, surface texture, max-min range, and sensor sensitivity determine the accuracy of measurements. 

##### __Gaussian Distributions:__
- univariate with __Mean__ $$ \mu $$ and __Variance__ $$ \sigma $$
  - $$ p(x | \mu, \sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right) $$
- multivariate
  - $$ \text{Mean Vector: } \boldsymbol{\mu} = \begin{bmatrix} \mu_x \\ \mu_y \end{bmatrix} $$
  - $$ \text{Covariance Matrix: } \boldsymbol{\Sigma} = \begin{bmatrix} \sigma_x^2 & \rho\sigma_x\sigma_y \\ \rho\sigma_x\sigma_y & \sigma_y^2 \end{bmatrix} $$
  - $$ p(\mathbf{x} | \boldsymbol{\mu}, \boldsymbol{\Sigma}) = \frac{1}{2\pi |\boldsymbol{\Sigma}|^{1/2}} \exp\left(-\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^\top \boldsymbol{\Sigma}^{-1}(\mathbf{x} - \boldsymbol{\mu})\right) $$

##### __Univariate Kalman Filter: Mean & Variance computation:__
State Prediction
- $$ \mu^{\prime} = \mu_1 + \mu_2 $$
- $$ \sigma^{\prime \, 2} = \sigma_1^2 + \sigma_2^2 $$
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/kalman_state_prediction.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>

Measurement Update
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/kalman_measurement_update.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>

- $$ \mu^{\prime} = \frac{r^2 \mu + \sigma^2 v}{r^2 + \sigma^2} $$
- $$ \sigma^{\prime \, 2} = \frac{r^2 \, \sigma^2}{r^2 + \sigma^2} $$

##### __Multivariate Kalman Filter: Mean & Variance computation:__
State Prediction
- $$ \text{Prior Mean Vector: } \mathbf{x} = \begin{bmatrix} x \\ \dot{x} \\ \ddot{x} \end{bmatrix} $$
- $$ \text{State Prediction (noise-free): } {\begin{bmatrix} x \\ \dot{x} \\ \ddot{x} \end{bmatrix}}^\prime = \begin{bmatrix} 1 & \Delta t & \frac{1}{2} \Delta t^2 \\ 0 & 1 & \Delta t \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} x \\ \dot{x} \\ \ddot{x} \end{bmatrix} $$
- $$ \text{State Prediction Function (noise-free): } \mathbf{F} = \begin{bmatrix} 1 & \Delta t & \frac{1}{2} \Delta t^2 \\ 0 & 1 & \Delta t \\ 0 & 0 & 1 \end{bmatrix} $$
- $$ \text{Covariance Matrix (noise-free): } \mathbf{P}^\prime = \mathbf{F} \mathbf{P} \mathbf{F}^T $$
- $$ \text{State Prediction (with Gaussian noise): } \mathbf{x}^\prime = \mathbf{F} \mathbf{x} + \text{noise}, \ \text{noise} \sim \mathbf{N} (0, \mathbf{Q}) $$
- $$ \text{Covariance Matrix (with Gaussian noise): } \mathbf{P}^\prime = \mathbf{F} \mathbf{P} \mathbf{F}^T + \mathbf{Q}$$

Measurement Update
- $$ \text{Actual Measurement Vector: } \mathbf{z} $$
- $$ \begin{gather*} \text{Expected Measurement Vector: } \mathbf{H} \mathbf{x}^\prime, \\ \text{where} \ \mathbf{H} \text{ is Measurement Function, mapping the state to an observation} \end{gather*} $$
- $$ \text{Measurement Residual Vector: } \mathbf{y} = \mathbf{z} - \mathbf{H} \mathbf{x}^\prime $$
- $$ \text{Covariance Matrix (with Gaussian noise): } \mathbf{S}^\prime = \mathbf{H} \mathbf{P}^\prime \mathbf{H}^T + \mathbf{R} $$

Kalman Gain Calculation
- $$ \text{Kalman Gain: } \mathbf{K} = \mathbf{P}^\prime \mathbf{H}^T \mathbf{S}^{-1} $$

Posterior Mean and Covariance Calculations
- $$ \text{Posterior Mean Vector: } \hat{\mathbf{x}} = \mathbf{x}^\prime + \mathbf{K} \mathbf{y} $$
- $$ \text{Posterior Covariance Matrix: } \hat{\mathbf{P}} = (\mathbf{I} - \mathbf{K} \mathbf{H}) \mathbf{P}^\prime $$

###### __Analysis of Kalman Gain:__
1. Perfect sensor measurements $$ \mathbf{R} = \begin{bmatrix} 0 \end{bmatrix} $$
  - $$ \mathbf{S}^\prime = \mathbf{H} \mathbf{P}^\prime \mathbf{H}^T + \mathbf{R} = \mathbf{H} \mathbf{P}^\prime \mathbf{H}^T $$
  - $$ \mathbf{K} = \mathbf{P}^\prime \mathbf{H}^T \mathbf{S}^{-1} = \mathbf{P}^\prime \mathbf{H}^T (\mathbf{H} \mathbf{P}^\prime \mathbf{H}^T)^{-1} = \mathbf{P}^\prime \mathbf{H}^T (\mathbf{H}^{T - 1} \mathbf{P}^{\prime - 1} \mathbf{H}^{-1}) = \mathbf{H}^{-1} $$
  - $$ \begin{gather*} \hat{\mathbf{x}} = \mathbf{x}^\prime + \mathbf{K} \mathbf{y} = \mathbf{x}^\prime + \mathbf{H}^{-1} (\mathbf{z} - \mathbf{H} \mathbf{x}^\prime) = \mathbf{H}^{-1} \mathbf{z}, \\ \text{rely entirely on sensor measurements, state prediction is unreliable} \end{gather*} $$

2. Noisy sensor measurements $$ \mathbf{R} = \begin{bmatrix} \infty \end{bmatrix} $$
  - $$ \mathbf{S}^\prime = \mathbf{H} \mathbf{P}^\prime \mathbf{H}^T + \mathbf{R} = \begin{bmatrix} \infty \end{bmatrix} $$
  - $$ \mathbf{K} = \mathbf{P}^\prime \mathbf{H}^T \mathbf{S}^{-1} = \begin{bmatrix} 0 \end{bmatrix} $$
  - $$ \begin{gather*} \hat{\mathbf{x}} = \mathbf{x}^\prime + \mathbf{K} \mathbf{y} = \mathbf{x}^\prime, \\ \text{rely entirely on state prediction, sensor measurement is unreliable} \end{gather*} $$


#### __Extended Kalman Filter__
Non-linear motion and measurment functions can be used to update the mean vector, but need to be linearized over a small section to update the covariance matrix. Otherwise, Gaussian distribution would turn into non-Gaussian distribution, dealing with which is computationally inefficient.\
- $$ \begin{gather*} \text{Linearization is achieved through Taylor series:} \\ \mathbf{T}(\mathbf{x}) = f(\boldsymbol{\mu}) + (\mathbf{x} - \boldsymbol{\mu})^T \, \nabla f(\boldsymbol{\mu}) + \frac{1}{2!} (\mathbf{x} - \boldsymbol{\mu})^T \, \nabla^2 f(\boldsymbol{\mu}) (\mathbf{x} - \boldsymbol{\mu}) + ... \end{gather*} $$
- $$ \begin{gather*} \text{where } \nabla f(\mathbf{\boldsymbol{\mu}}) \text{ is the gradient of } f \text{ evaluated at } \boldsymbol{\mu}, \text{which is a Jacobian matrix } \mathbf{J} \text{ of partial derivatives:} \\ \nabla f(\mathbf{\boldsymbol{\mu}}) = \mathbf{J} = \begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\ \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\ \vdots & \vdots & \ddots & \vdots \\ \frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n} \end{bmatrix} \end{gather*} $$

__Example:__
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/ekf_example_drone.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>

Measurement Update
- $$ \text{State Vector: } \mathbf{x} = \begin{bmatrix} \phi \\ \dot{y} \\ y \end{bmatrix}, \text{where } \phi \text{ is the roll angle} $$
- $$ \text{Measurement Function: } h(\mathbf{x}) = \begin{bmatrix} \frac{wall - y}{ \cos{\phi}} \end{bmatrix} $$
- $$ \text{Measurement Function Linearization: } h(\mathbf{x}) \simeq h(\mathbf{x}) + (\mathbf{x} - \boldsymbol{\mu})^T \, \nabla h(\mathbf{\boldsymbol{\mu}}) $$
- $$ \nabla h(\mathbf{\boldsymbol{\mu}}) = \mathbf{H} = \begin{bmatrix} \frac{\partial h}{\partial \phi} & \frac{\partial h}{\partial \dot{y}} & \frac{\partial h}{\partial y} \end{bmatrix} = \begin{bmatrix} \frac{\sin{\phi}}{\cos^2{\phi}} (wall - y) & 0 & \frac{-1}{\cos{\phi}} \end{bmatrix} $$

##### __Extended Kalman Filter Equations:__
State Prediction
- $$ \mathbf{x}^\prime = f(\mathbf{x}) $$
- $$ \mathbf{P}^\prime = \mathbf{F} \mathbf{P} \mathbf{F}^T + \mathbf{Q}$$

Measurement Update
- $$ \mathbf{y} = \mathbf{z} - h(\mathbf{x}^\prime) $$
- $$ \mathbf{S}^\prime = \mathbf{H} \mathbf{P}^\prime \mathbf{H}^T + \mathbf{R} $$

Kalman Gain Calculation
- $$ \mathbf{K} = \mathbf{P}^\prime \mathbf{H}^T \mathbf{S}^{-1} $$

Posterior Mean and Covariance Calculations
- $$ \hat{\mathbf{x}} = \mathbf{x}^\prime + \mathbf{K} \mathbf{y} $$
- $$ \hat{\mathbf{P}} = (\mathbf{I} - \mathbf{K} \mathbf{H}) \mathbf{P}^\prime $$

##### __Lab: Extended Kalman Filter:__

Used ROS packages:
- [turtlebot_gazebo](http://wiki.ros.org/turtlebot_teleop) to spawn TurtleBot 2 in a Gazebo environment.
- [turtlebot_teleop](https://github.com/turtlebot/turtlebot) to publish robot control commands to `/cmd_vel_mux/input/teleop` ROS topic from keyboard.
- __rviz__ to visualize the estimated robot poses.
- [robot_pose_ekf](http://wiki.ros.org/robot_pose_ekf) to estimate the robot poses from teleop motion commands and fusion of two sensor measurements: IMU (`/mobile_base/sensors/imu_data`) and rotary encoders (`/odom`). 
- __odom_to_trajectory__ (by Udacity) to generate trajectory paths from filtered (`/ekfpath`) and unfiltered (`/odompath`) poses.


<div class="container">
    <div class="row">
        <div class="align-self-center">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/ekf_lab_overall_graph.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="align-self-center">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/ekf_lab_sim.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<br>

#### __Monte-Carlo Localization__
__Pros:__
- can be used for both local and global localization problems, while EKF is for local only.
- not limited to Gaussian noise as EKF.
- memory & resolution can be control through the number of particles.
- particles represent belief distribution of where the robot might be.
- easier to implement than EKF.

__Cons:__
- computationally and memory-wise expensive (especially to achieve high resolution).
- poor resampling result in particle deprevation and worse resolution.

For more information, check out the paper ["Robust Monte-Carlo Localization for Mobile Robots"](http://robots.stanford.edu/papers/thrun.robust-mcl.pdf)

<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_2Dmap_with_particles.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-2">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_2Dmap_with_converged_particles.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Paricles with higher weight, which is defined by how close the predicted pose to the robot actual pose, are more likely to survive during the resampling process.  
</div>

###### __Types of Range Sensor (LIDAR) Noise__
<ol type="a">
  <li>Local Measurement Noise: caused by limited resolution of range sensors; atmespheric effects on the measurement signals.</li>
  <li>Unexpected Objects: caused by dynamic environment (e.g. people) in static map.</li>
  <li>Sensor Failures: caused by black, light-absorbing objects; bright sunlight; smooth surfaces such as walls, which
effectively becomes a mirror (surface material, sensitivity of the sensor).</li>
  <li>Random Measurements: caused by cross-talk between different sensors; phantom readings from signals bounced off walls.</li>
</ol>
<!-- four types of sensor noise -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-3">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_sensor_noise_types.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    $$ z^k_t \text{ - reading from } k^{th} \text{ beam sensor at time } t, \, x_t \text{ - robot position at time } t, m \text{ - map} $$
</div>
<!-- overall sensor model -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-3">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_overall_sensor_model.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-3">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_sensor_model_function.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Sensor Model that takes into account different types of noises.
</div>

##### __MCL Pseudo-Code__
<!-- pseudo-code -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-3">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_pseudo_code.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    State Prediction (4) through Motion Model; Measurement Update (5) through Sensor Model; Resampling (8-11).
</div>
<!-- sensor model -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-3">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_beam_sensor_model.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    LIDAR Sensor Model.
</div>
<!-- low-variance resampler -->
<div class="container">
    <div class="row">
        <div class="col-sm-8 align-self-center offset-sm-3">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/mcl_low_variance_resampler.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Low-Variance Resampler.
</div>

#### Project3: Where Am I <a href="https://github.com/SanjarNormuradov/RoboticsSoftwareEngineer_Project3"><i class="fa-brands fa-github"></i></a>
<!-- Gazebo world -->
<div class="container">
    <div class="row">
        <div class="align-self-center">
            {% include figure.html path="assets/img/projects/course/udacity_robotics_swe/project3_where_am_i.png" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
</div>

