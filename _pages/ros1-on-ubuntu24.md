---
title: Install ROS1 Noetic on Ubuntu 24.04 using Distrobox
permalink: /ros1-on-ubuntu24/
layout: single
---
As we know ROS1 is officially supported on Ubuntu 20.04 but in case you wish to run ROS1 on Ubuntu 24.04 , [Distrobox](https://distrobox.it/) is a good option. Distrobox is a utility that allows you to run multiple Linux distributions in your system without the need to dual boot or install them in a virtual machine.

Here is the complete, step-by-step guide to installing Ubuntu 20.04 via Distrobox and setting up ROS 1 Noetic on your Ubuntu 24.04 system.

### Part 1: Host Setup (Ubuntu 24.04)
*Do these steps in your normal terminal.*

**1. Install Distrobox and Docker**
Update your repository and install the necessary tools.
```bash
sudo apt update
sudo apt install distrobox docker.io -y
```

**2. Configure Docker Permissions**
By default, Docker requires `sudo`. We need to change this so Distrobox can run smoothly without asking for a password constantly.
```bash
sudo usermod -aG docker $USER
```

**3. Apply Changes**
You must log out and log back in for the permission changes to take effect.
*   Close all terminals.
*   Log out of Ubuntu 24.04.
*   Log back in.

---

### Part 2: Create the Ubuntu 20.04 Container
*Do these steps in your normal terminal.*

**1. Create the Container**
Run the following command. It will download the Ubuntu 20.04 image (this takes a minute) and set up the container named `ros1-noetic`.
```bash
distrobox create --image ubuntu:20.04 --name ros1-noetic
```

**2. Enter the Container**
Now, step inside your new Ubuntu 20.04 environment:
```bash
distrobox enter ros1-noetic
```
*Note: The prompt usually changes. You might see something like `user@ros1-noetic`.*

---

### Part 3: Install ROS 1 Noetic
*Perform all steps below **inside** the `distrobox enter` session.*

**1. Install Basic Tools**
The container is minimal, so we need to install some basics first.
```bash
sudo apt update
sudo apt install -y curl gnupg2 lsb-release git nano
```

**2. Add ROS Repositories**
Tell the system where to find ROS packages.
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

**3. Add ROS Keys**
Secure the download connection.
```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

**4. Install ROS 1**
This includes ROS, Rviz, Gazebo, and standard robot packages.
```bash
sudo apt update
```
You may either install **Desktop Install** that includes ROS packaging, build, and communication libraries plus tools like rqt and rviz
```bash
sudo apt install ros-noetic-desktop
```

Or install **Desktop-Full Install** that includes everything in Desktop plus 2D/3D simulators and 2D/3D perception packages
```bash
sudo apt install ros-noetic-desktop-full -y
```
*(Installation download is large. Please wait patiently.)*

Once the installation is complete, check if it is succesful by running the command
```bash
ls /opt/ros/noetic/setup.bash
```
*If it prints /opt/ros/noetic/setup.bash: The installation is successful.*
Else go back to the installation step.

**5. Setup Environment Variables**
Make ROS load automatically whenever you enter this container.
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
**6. Install Dependencies for Building Packages**
To compile code (catkin_make), you need these tools:
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential -y
```

**7. Initialize rosdep**
```bash
sudo rosdep init
rosdep update
```

### Part 4: Verification & Network Setup
*Still inside the container.*

**1. Test ROS Core**
Run the master node.
```bash
roscore
```
*Output should say "started core service [/rosout]". Press `Ctrl+C` to stop.*

**2. Test GUI (Rviz)**
1.  **Leave `roscore` running** in the current terminal.
2.  Open a **new terminal window** (or tab) on your Ubuntu host.
3.  Enter the **same** Distrobox container:
    ```bash
    distrobox enter ros1-noetic
4.  Once inside, run:
    ```bash
    rviz
    ```
*The Rviz window should pop up on your Ubuntu 24.04 desktop.*

### Part 5: Installing Gazebo 
If you have installed **Desktop-Full Install** you can skip this step as Gazebo is installed along. But if you have done **Desktop Install**, follow these steps to install **Gazebo**

## Install Gazebo
Run this command inside your `ros1` container:
```bash
sudo apt update
sudo apt install ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control -y
```
## Source your environment
After installing new packages, you must refresh ROS so it "sees" them:
```bash
source /opt/ros/noetic/setup.bash
```
## Launch Gazebo
```bash
roslaunch gazebo_ros empty_world.launch
```
*The Gazebo window should pop up on your Ubuntu 24.04 desktop.*

## Network Configuration
If you plan to communicate with an external robot from your distrobox hosted ROS1, you should check your IP address inside the container to confirm it matches your host:
```bash
hostname -I
```
*If this IP matches your Ubuntu 24.04 Wi-Fi/Ethernet IP, you are ready to go.*

To connect to a robot, simply export the IPs as you normally would:
```bash
export ROS_IP=YOUR_PC_IP
export ROS_MASTER_URI=http://ROBOT_IP:11311
```

### Steps to log into your ROS1 container
Whenever you restart your computer:
1.  Open your terminal (Ubuntu 24.04).
2.  Type: `distrobox enter ros1-noetic`
3.  You are now in ROS 1 mode. Run your commands!
