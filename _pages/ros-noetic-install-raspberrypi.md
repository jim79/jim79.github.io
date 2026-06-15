---
title: Installing ROS Noetic on Raspberry Pi 3/4
permalink: /ros-noetic-install-raspberrypi/
layout: single
---
To allow ROS to run smoothly on resource limited Raspberry Pi 3, we shall install Raspberry Pi OS lite on Raspberry Pi. ROS Noetic is supported on Debian Buster (Debian 10) only. So we install the Buster image of Raspberry Pi OS lite on Pi.

### 1. Installing Raspberry Pi OS lite on Raspberry Pi 
1. Download the Debian Buster image from the link 
[Download the Debian Buster image](https://downloads.raspberrypi.org/raspios_lite_arm64/images/raspios_lite_arm64-2021-05-28/) 
2. Unzip the file _2021-05-07-raspios-buster-arm64-lite.zip_ 
3. Flash the OS image file (unzipped in step 2) _2021-05-07-raspios-buster-arm64-lite.img_ to SD card \
The easiest way to do this would be to use [Raspberry Pi Imager](https://www.raspberrypi.com/news/raspberry-pi-imager-imaging-utility/) \
[Video tutorial](https://youtu.be/xSkQJFH4nW0) 
4. Insert the SD card into Raspberry Pi and power it 
5. Wait for 5 minutes for the OS to do its first boot and then SSH to Raspberry Pi 
6. Run update ```sudo apt-get update``` \
and ```sudo apt-get dist-upgrade``` 

### 2. Debian install of ROS Noetic 
Follow the steps given on ROS wiki link below \
[Debian install of ROS Noetic](https://wiki.ros.org/noetic/Installation/Debian) \
**Step 1.1 on the ROS wiki page above may be skipped** 

**We shall install ROS-Base on Raspberry Pi** \
ROS-Base: (Bare Bones) ROS packaging, build, and communication libraries. No GUI tools. 

```sudo apt install ros-noetic-ros-base```

### 3. Dependencies for building packages
 _(The content below is borrowed from ROS wiki)_ \
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.\

To install this tool and other dependencies for building ROS packages, run:

```sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential```

### 4. Initialize rosdep
Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. If you have not yet installed rosdep, do so as follows.

```sudo apt install python3-rosdep``` \
With the following, you can initialize rosdep. \
```sudo rosdep init```

```rosdep update```

### 5. Environment setup
Source setup.bash to .bashrc \
```echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc``` \
```source ~/.bashrc```

### 6. Create a ROS Workspace 
[Create a ROS Workspace](https://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) 
