---
title: Custom ROS service-client package file modifications
permalink: /ros-service-client-cmake-package-modifications/
layout: single
---

## For your custom ROS service client to run properly, modifications are to be made in the CMakeLists.txt and package.xml files of your package

## 1. CMakeLists.txt modifications

### Around line no 7 
#### Uncomment and modify as below 
```
## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  message_generation
)
```

### Around line no 56 
#### Uncomment and modify as below 
```
## Generate services in the 'srv' folder
 add_service_files(
  FILES
  <your service file name>.srv
)
```
### Around line no 69 
#### Uncomment and modify as below 
```
## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  std_msgs  # Or other packages containing msgs
)
```
### Around line no 159
#### Uncomment and modify as below 
```
## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
 catkin_install_python(PROGRAMS
   scripts/<name of your server node script>.py scripts/<name of your client node script>.py 
   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
 )
```

## 2. package.xml modifications

### Uncomment line 40
```
<build_depend>message_generation</build_depend>
```
### Uncomment line 46
```
<exec_depend>message_runtime</exec_depend>
```

