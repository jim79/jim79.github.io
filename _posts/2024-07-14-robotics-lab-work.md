---
title: "M1RAA - Robotics lab (221LIA001) : Lab work"
categories : [Robotics Lab, Robotics Lab Work]
---
### Lab 1 : 
- Ubuntu 20.04 LTS installation
    - [Ubuntu desktop install](https://ubuntu.com/tutorials/install-ubuntu-desktop)
- Ubuntu/Linux basics
    - Basic commands
        -[Ubuntu command line tutorial](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview)
    - Linux File System/Structure Explained
        -[Linux File System/Structure](https://youtu.be/HbgzrKJvDRw)

### Lab 2 : 
- Completing ROS installation and remaining tasks from lab 1
- ROS basics
- Setting up ROS environment on your PC
    -[Setting up ROS environment on your PC](https://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment)
- Navigating the ROS Filesystem
    -[Navigating the ROS Filesystem](https://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem) 

### Preparatory work to be completed by all students before lab 3 
- Python basics \
    -[PyFlo - A Free, Interactive Guide to Python Programming](https://pyflo.net/)\
        - Complete the modules on PyFlo uptill and including *Guided Project 3*
- ROS crash tutorial by Edouard Renard \
    -[ROS crash course](https://www.youtube.com/playlist?list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q) \
        - Follow this crash course and try to complete the tasks atleast till tutorial 6

### Lab 3 :
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
    -[A ROS publisher node - line by line commented](https://drive.google.com/file/d/1o_lco9381vvnrU7JJ3yNdNtaM9gThMUJ/view?usp=sharing) \
    -[A ROS subsriber node line by line commented](https://drive.google.com/file/d/1qp_ia2wvsR_FFrSJIz1QmI-mqkge7547/view?usp=sharing)

### Preparatory work to be completed by all students before lab 4
-  GitHub fundamentals \
    -[GitHub Tutorial - Beginner's Training Guide](https://youtu.be/iv8rSLsi1xo?si=wE-eT0DSa-FoOVH8) \
    -[installing git on Ubuntu 20.04](https://linuxhint.com/git-source-code-management-system/) \
    -[Git Tutorial for Beginners: Command-Line Fundamentals](https://youtu.be/HVsySz-h9r4?si=Mo8WTDtsDALJxIcL)
<!-- - ### 17/10/23 : Assignment 1 : Posted in GitHub classroom. Due on 26/10/23, 2.00 p.m.
- ### 24/10/23 : Assignment 2 : Posted in GitHub classroom. Due on 01/11/23, 2.00 p.m.
- ### 25/10/23 : Creating a Custom ROS Message  -->
    - [Creating a Custom ROS Message (Video tutorial)](https://youtu.be/8paLh2kklJo?si=HRi1JlB6B-lP2SKN)

### Lab 4 : 
- Service and Client nodes \
    -[Basics of ROS Service-Client (Video )](https://youtu.be/MVnXfGLQb-c?si=8RsL4O5-2Glr6E8F) \
    -[Simple Service and Client nodes](http://wiki.ros.org/ROS/Tutorials/WritingServiceClient%28python%29) \
    -[Examining the Simple Service and Client](http://wiki.ros.org/ROS/Tutorials/ExaminingServiceClient) \
    -[Changes to be made in CMakeLists.txt and package.xml files of the Service-Client package](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv) \
    -[Summary of changes to be made to CMakeLists.txt and package.xml](https://drive.google.com/file/d/1Y9vgTEqkxMyuBAlwpRrahAf45Wr_BUsm/view?usp=sharing) \
    -[ROS Service - Server node (coding) Video tutorial](https://youtu.be/1-5tm4RIK6o) \
    -[ROS Service - Client node (coding) Video tutorial](https://youtu.be/Fp4x8WlLVb8) 
     
### ROS Cheat sheets
-[ROS Noetic Cheat sheet](https://drive.google.com/file/d/1gzXz8cnPt5RkFKG0k8GlhVUFRh4p49OW/view?usp=sharing) \
-[ROS cheat sheet](https://drive.google.com/file/d/1MmeQpeK1hb3gyFwAWWn3LSILsPPYwQoQ/view?usp=sharing) \
[cheat sheet 1 source](https://gomarketing.ottomotors.com/l/92812/2023-03-22/92z4ql/92812/1679526697SkoPBmzi/ROS_Cheat_Sheet_Noetic.pdf) \
[cheat sheet 2 source](https://courses.edx.org/assets/courseware/v1/83b19d128b084ebf43b778f572b14932/asset-v1:DelftX+ROS1x+1T2020+type@asset+block/ROScheatsheet.pdf)
### 01/11/23 : Assignment 3 : Posted in GitHub classroom. Due on 08/11/23, 2.00 p.m.

### Extras
#### shebang
 ```#!/usr/bin/env python```
line that you write at the beginning of the python script is called **shebang**\
shebang indicates the path to the python interpreter. \
Always start your python scripts with a #! shebang. Preferably with ```#!/usr/bin/env python```
[read more](https://dev.to/meleu/what-the-shebang-really-does-and-why-it-s-so-important-in-your-shell-scripts-2755) 

#### What does if __name__ == "__main__": do?
[What does if __name__ == "__main__": do?](https://stackoverflow.com/questions/419163/what-does-if-name-main-do)

### Lab 5 : 
- Launch files \
    -[Launch multiple nodes using launch file (Video tutorial)](https://youtu.be/kKoPqGDgwMo) \
    -[Launch files advanced topics - args, params, remap](https://youtu.be/0-zTU4_S6vY?si=OEzvyIl3sEIZxDgw)
- URDF \
    -[How do we describe a robot? With URDF!](https://youtu.be/CwdbsvcpOHM?si=PnAr6AdEhopQSnq7) \
    -[Create a visual model of a robot that you can view in Rviz](http://wiki.ros.org/urdf/Tutorials/Building%20a%20Visual%20Robot%20Model%20with%20URDF%20from%20Scratch) 
    

### Lab 6 : 
- Mobile robot URDF \
    -[Creating urdf model of a robot (Video demonstration)](https://youtu.be/-fMxgG1cPDA?si=9V84MQ9Tzgh1Xdjj) \
    -[Adding Physical and Collision Properties to a URDF Model](http://wiki.ros.org/urdf/Tutorials/Adding%20Physical%20and%20Collision%20Properties%20to%20a%20URDF%20Model) \
    -[Using Xacro to Clean Up a URDF File](http://wiki.ros.org/urdf/Tutorials/Using%20Xacro%20to%20Clean%20Up%20a%20URDF%20File) \
    -[ROS mobile robot URDF , Xacros with Meshes(Video demonstration)](https://youtu.be/yXFL5GWdvBE?si=XiqKn2PAhxOZAo6t)

### Lab 7 : 
- Gazebo \
Gazebo is an open-source 3D robotics simulator \
    **Read and understand the _gazebo ros_ documentation in the two links below before you install _gazebo_** \
    -[Which combination of ROS/Gazebo versions to use](https://classic.gazebosim.org/tutorials?tut=ros_wrapper_versions&cat=connect_ros) \
    -[Installing gazebo_ros_pkgs (ROS 1)](https://classic.gazebosim.org/tutorials?tut=ros_installing&cat=connect_ros) 

    -Create a gazebo world for the mobile robot you built in lab 6 \
    [Building a Gazebo world](https://classic.gazebosim.org/tutorials?tut=build_world&cat=build_world) 

    **Navigate your mobile robot in the gazebo world** \
    _To navigate your mobile robot in the gazebo world you may need to install additional controllers and packages (as given below)_ \
    ```sudo apt-get install ros-kinetic-noetic-ros-pkgs ros-noetic-gazebo-ros-control ros-noetic-ros-control ros-noetic-ros-controllers``` \
    **Additional references**: \
    -[Teleop twist keyboard](http://wiki.ros.org/teleop_twist_keyboard) \
    -[Steer drive controller](http://wiki.ros.org/steer_drive_controller)

### Lab 8
- ros_serial arduino 
    - [Simple publisher on Arduino](https://drive.google.com/file/d/1VgLc7mcEj2kEtpNgEPlX_J6ENYEIByQu/view?usp=sharing)

### Lab 9
- [DC motor interfacing with ROS Serial](https://github.com/jim79/DC-motor-interfacing-with-ROS-serial)


- MoveIt \
MoveIt is an open-source robotic manipulation platform that allows you to develop complex manipulation applications using ROS \
-[A sample Moveit application](https://robotnik.eu/moveit-manipulation-application/) \
-[MoveIt tutorials](https://ros-planning.github.io/moveit_tutorials/index.html) \
-[Getting started with MoveIt](https://ros-planning.github.io/moveit_tutorials/doc/getting_started/getting_started.html) \
-[MoveIt Quickstart in RViz](https://ros-planning.github.io/moveit_tutorials/doc/quickstart_in_rviz/quickstart_in_rviz_tutorial.html) \
-[MoveGroup](https://ros-planning.github.io/moveit_tutorials/index.html#movegroup-ros-wrappers-in-c-and-python)

### Secure Shell protocol (SSH)
-[SSH crash video tutorial](https://youtu.be/v45p_kJV9i4?si=dA238EWHt2v2mq4W) \
-[Install SSH client in Windows 10](https://youtu.be/JbMgOKlj5fE?si=QPKwaJHyvE0fhmLi) \
-[Secure copy command](https://youtu.be/2u0I-U0D7Uk?si=rpJq4tqP_MVN9y6Z)