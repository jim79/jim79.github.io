---
title: "Custom ROS message on rosserial_arduino"
categories : [Robotics Lab,Tutorials]
---


1. Make a new ROS package and create the custom message in a folder named ```msg``` within the package. Alternatively you can create a ```msg``` folder in your ROS package and create the custom message file in it.

2. Make the necessary modifications in the ```CMakeLists.txt``` and ```package.xml``` of the package

3. Open the Arduino project in Platformio IDE for VS Code 
    - Right click on ```lib`` folder in VS Code explorer tab and choose the option _Open In Integrated Terminal_ 
    - Assuming that our ROS package name is ```jimbot_msgs``` , type in the following command in the terminal launched.

```rosrun rosserial_arduino make_libraries.py /lib jimbot_msgs```
4. Now the folder ```jimbot_msgs``` with the custom message header file will be created within ```lib\ros_lib``` folder of the Arduino project
5. The custom message can be imported into the Arduino project as ```#include <jimbot_msgs\custom message header file name>```