---
title: "Robotics lab (221LIA001) : Lab work"
permalink: /robotics-lab-work/
layout: single
---
### Lab 1 : 14/08/26
- Operating Systems - Introduction
- ROS - Introduction
- TurtleBot3 demo

### Lab 2 : 21/08/26
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

### Home Assignment 1 - ROS Nodes
- Completing ROS installation and remaining tasks from lab 1
- #### ROS basics 
- Navigating the ROS Filesystem \
    -[Navigating the ROS Filesystem](https://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem) 
- CMake basics [Lecture]
- Creating a ROS workspace 

- #### Understanding ROS Nodes 
    -[ROS nodes](https://wiki.ros.org/ROS/Tutorials/UnderstandingNodes) 
        - Learn about ROS nodes, topics, ROS commands - roscore, rosnode, rosrun 
    - Understanding ROS Topics \
        -[ROS topics](https://wiki.ros.org/ROS/Tutorials/UnderstandingTopics) 
        -[video demo](https://youtu.be/rIPmFy_Ax2A?si=WgEjDfC164pchmbd) 

##### Task 
- Create a new package named *lab2_sub_pub* in the src folder of your catkin_ws. The package dependencies are std_msgs and rospy \
    -[Video demo - Creating ROS package using catkin_create_pkg command](https://youtu.be/QRJ9mbzWPcY?si=iVz5lwKnvlBRC__Z)

### ### Home Assignment 2 - Publisher Subscriber
- Understanding ROS Nodes (Review) \
        -[ROS nodes](https://wiki.ros.org/ROS/Tutorials/UnderstandingNodes) \
    Learn about ROS nodes, topics, ROS commands - roscore, rosnode, rosrun 
        - Understanding ROS Topics \
        -[ROS topics](https://wiki.ros.org/ROS/Tutorials/UnderstandingTopics) \
        -[video demo](https://youtu.be/rIPmFy_Ax2A?si=WgEjDfC164pchmbd)
- Simple Publisher and Subscriber \
        -[Simple Publisher and Subscriber](https://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29) \
        -[Examining the Simple Publisher and Subscriber](https://wiki.ros.org/ROS/Tutorials/ExaminingPublisherSubscriber) \
        -[A ROS publisher node - line by line commented](https://jim79.github.io/ros-simple-publisher) \
        -[A ROS subsriber node line by line commented](https://jim79.github.io/ros-simple-subscriber)

##### Task   
- Create a new package named *lab3_sub_pub* in the src folder of your catkin_ws. The package dependencies are std_msgs and rospy \
        -[Video demo - Creating ROS package using catkin_create_pkg command](https://youtu.be/QRJ9mbzWPcY?si=iVz5lwKnvlBRC__Z) 
- Create a simple publisher and Subscriber
- Create three publishers within a ROS node
- Create two ROS nodes that subscribes to the topics published (ROS node1 : subcribes to topic 1 & 3, ROS node 2 : subscribes to topic2) 