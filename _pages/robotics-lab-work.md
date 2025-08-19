---
title: "Robotics lab (221LIA001) : Lab work"
permalink: /robotics-lab-work/
layout: single
---
### Lab 1 : 14/08/25
- Ubuntu 20.04 LTS installation
    - [Ubuntu desktop install](https://ubuntu.com/tutorials/install-ubuntu-desktop)
- Ubuntu/Linux basics
    - Basic commands
        -[Ubuntu command line tutorial](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview)
    - Linux File System/Structure Explained
        -[Linux File System/Structure](https://youtu.be/HbgzrKJvDRw)
- ROS basics
    - ROS installation basics

### Tasks expected to be completed before Lab 2
- Install ROS on Windows 11 using Windows Subsystem for Linux 2 (WSL2)
    - [Installing Ubuntu 20.04 LTS on Windows using WSL2](https://learn.microsoft.com/en-us/windows/wsl/install-manual)
    - [Installing ROS Noetic on Ubuntu](https://wiki.ros.org/noetic/Installation)
- Setting up ROS environment on your PC
    -[Setting up ROS environment on your PC](https://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment)
- Navigating the ROS Filesystem
    -[Navigating the ROS Filesystem](https://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem) 
##### Python Basics Refresher 
- Python basics
     -[PyFlo - A Free, Interactive Guide to Python Programming](https://pyflo.net/) 

### Lab 2 : 21/08/25
- Completing ROS installation and remaining tasks from lab 1
- #### ROS basics \
- Navigating the ROS Filesystem
    -[Navigating the ROS Filesystem](https://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem) 
- CMake basics
- Creating a ROS workspace


- #### Understanding ROS Nodes \ 
        -[ROS nodes](https://wiki.ros.org/ROS/Tutorials/UnderstandingNodes) \
    Learn about ROS nodes, topics, ROS commands - roscore, rosnode, rosrun 
        - Understanding ROS Topics \
        -[ROS topics](https://wiki.ros.org/ROS/Tutorials/UnderstandingTopics) \
        -[video demo](https://youtu.be/rIPmFy_Ax2A?si=WgEjDfC164pchmbd)
##### Lab Task \
- Create a new package named *lab2_sub_pub* in the src folder of your catkin_ws. The package dependencies are std_msgs and rospy \
        -[Video demo - Creating ROS package using catkin_create_pkg command](https://youtu.be/QRJ9mbzWPcY?si=iVz5lwKnvlBRC__Z)

<!-- ### Lab 3 : 14/10/24
- Understanding ROS Nodes \
        -[ROS nodes](https://wiki.ros.org/ROS/Tutorials/UnderstandingNodes) \
    Learn about ROS nodes, topics, ROS commands - roscore, rosnode, rosrun 
        - Understanding ROS Topics \
        -[ROS topics](https://wiki.ros.org/ROS/Tutorials/UnderstandingTopics) \
        -[video demo](https://youtu.be/rIPmFy_Ax2A?si=WgEjDfC164pchmbd)
- Create a new package named *lab3_sub_pub* in the src folder of your catkin_ws. The package dependencies are std_msgs and rospy \
        -[Video demo - Creating ROS package using catkin_create_pkg command](https://youtu.be/QRJ9mbzWPcY?si=iVz5lwKnvlBRC__Z) 
- Simple Publisher and Subscriber \
        -[Simple Publisher and Subscriber](https://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29) \
        -[Examining the Simple Publisher and Subscriber](https://wiki.ros.org/ROS/Tutorials/ExaminingPublisherSubscriber) \
        -[A ROS publisher node - line by line commented](https://jim79.github.io/ros-simple-publisher) \
        -[A ROS subsriber node line by line commented](https://jim79.github.io/ros-simple-subscriber)

### Preparatory work (To be completed by all students before lab 4)
-  GitHub fundamentals \
        -[GitHub Tutorial - Beginner's Training Guide](https://youtu.be/iv8rSLsi1xo?si=wE-eT0DSa-FoOVH8) \
        -[installing git on Ubuntu 20.04](https://linuxhint.com/git-source-code-management-system/) \
        -[Git Tutorial for Beginners: Command-Line Fundamentals](https://youtu.be/HVsySz-h9r4?si=Mo8WTDtsDALJxIcL)

### Lab 4 : 21/10/24
- Service and Client nodes \
        -[Basics of ROS Service-Client (Video )](https://youtu.be/MVnXfGLQb-c?si=8RsL4O5-2Glr6E8F) \
        -[Simple Service and Client nodes](http://wiki.ros.org/ROS/Tutorials/WritingServiceClient%28python%29) \
        -[Examining the Simple Service and Client](http://wiki.ros.org/ROS/Tutorials/ExaminingServiceClient) \
        -[Changes to be made in CMakeLists.txt and package.xml files of the Service-Client package](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv) \
        -[Summary of changes to be made to CMakeLists.txt and package.xml](https://jim79.github.io/ros-service-client-cmake-package-modifications) \
        -[ROS Service - Server node (coding) Video tutorial](https://youtu.be/1-5tm4RIK6o) \
        -[ROS Service - Client node (coding) Video tutorial](https://youtu.be/Fp4x8WlLVb8) 

### Lab 5 : 28/10/24
- turtlesim \
        -[Getting Started with Turtlesim](https://wiki.ros.org/turtlesim) \
        -[Understanding ROS using Turtlesim by Prof. Madhur Behl](https://jim79.github.io/assets/ros-turtlesim.pdf) \
        -[Madhur Behl, University of Virginia](https://engineering.virginia.edu/faculty/madhur-behl)\
        -[Tutorials Using Turtlesim](https://wiki.ros.org/turtlesim/Tutorials)  Scroll to the bottom of the page to find the tutorials \
        - Control the turtle with rqt_robot_steering GUI \```rosrun rqt_robot_steering rqt_robot_steering```
- Launch files \
        -[launch files - Chapter from the book 'A Gentle Introduction to ROS'](https://jokane.net/agitr/agitr-small-launch.pdf) [link 2](https://jim79.github.io/assets/launch_files_gentle_intro_ros.pdf) \
        -[Launch multiple nodes using launch file (Video tutorial)](https://youtu.be/kKoPqGDgwMo) 

### Lab 6 : 4/11/24
- URDF \
        -[How do we describe a robot? With URDF!](https://youtu.be/CwdbsvcpOHM?si=PnAr6AdEhopQSnq7) \
        -[Create a visual model of a robot that you can view in Rviz](http://wiki.ros.org/urdf/Tutorials/Building%20a%20Visual%20Robot%20Model%20with%20URDF%20from%20Scratch) 
- Mobile robot URDF \
        -[Creating urdf model of a robot (Video demonstration)](https://youtu.be/-fMxgG1cPDA?si=9V84MQ9Tzgh1Xdjj) \
        -[Adding Physical and Collision Properties to a URDF Model](http://wiki.ros.org/urdf/Tutorials/Adding%20Physical%20and%20Collision%20Properties%20to%20a%20URDF%20Model) \
        -[Using Xacro to Clean Up a URDF File](http://wiki.ros.org/urdf/Tutorials/Using%20Xacro%20to%20Clean%20Up%20a%20URDF%20File) \
        -[ROS mobile robot URDF , Xacros with Meshes(Video demonstration)](https://youtu.be/yXFL5GWdvBE?si=XiqKn2PAhxOZAo6t)

### Lab 7 : 11/11/24
- ROS serial link for Arduino \
        - [Familiarizartion with Arduino](https://docs.arduino.cc/built-in-examples/) \
        - [Configure VS Code for rosserial_arduino](https://jim79.github.io/rosserial-arduino-vscode) \
        - [Hello ROS serial node running on Arduino](https://github.com/jim79/hello-ros-serial)
        - [DC motor interfacing with ROS serial](https://jim79.github.io/dc-motor-interfacing-with-ros-serial) \
    - Experiments to be done : 
    1. Hello ROS serial node running on Arduino
    2. Led blinking and displaying led status on serial terminal

### Lab 8 : 18/11/24
- Lab Viva 
- Gazebo \
    Gazebo is an open-source 3D robotics simulator \
    **Read and understand the _gazebo ros_ documentation in the two links below before you install _gazebo_** \
    -[Which combination of ROS/Gazebo versions to use](https://classic.gazebosim.org/tutorials?tut=ros_wrapper_versions&cat=connect_ros) \
    -[Installing gazebo_ros_pkgs (ROS 1)](https://classic.gazebosim.org/tutorials?tut=ros_installing&cat=connect_ros) 

    -Create a gazebo world for the mobile robot you built in lab 6 \
    [Building a Gazebo world](https://classic.gazebosim.org/tutorials?tut=build_world&cat=build_world) 

    **Navigate your mobile robot (Lab 6 work) in the gazebo world** \
    _To navigate your mobile robot in the gazebo world you may need to install additional controllers and packages (as given below)_ \
    ```sudo apt-get install ros-kinetic-noetic-ros-pkgs ros-noetic-gazebo-ros-control ros-noetic-ros-control ros-noetic-ros-controllers``` \
    **Additional references**: \
    -[Teleop twist keyboard](http://wiki.ros.org/teleop_twist_keyboard) \
    -[Steer drive controller](http://wiki.ros.org/steer_drive_controller)

### Lab 9 : 25/11/24
- Lab Viva 
- MoveIt \
    MoveIt is an open-source robotic manipulation platform that allows you to develop complex manipulation applications using ROS \
    -[A sample Moveit application](https://robotnik.eu/moveit-manipulation-application/) \
    -[MoveIt tutorials](https://docs.ros.org/en/melodic/api/moveit_tutorials/html/index.html) \
    _MoveIt tutorials for Noetic are Not available at this [link](https://ros-planning.github.io/moveit_tutorials/) as on November 25, 2024._ --> -->