---
title: Configure VS Code for rosserial_arduino
permalink: /rosserial-arduino-vscode/
layout: single
---

### Configure VS Code for rosserial_arduino
 The package *rosserial_arduino* contains Arduino-specific extensions required to run rosserial_client on an Arduino boards. Roswiki has [detailed tutorials and examples](http://wiki.ros.org/rosserial_arduino/Tutorials) to configure the Arduino IDE to use *rosserial_arduino*. Here we disuss the steps to configure [VS Code](https://code.visualstudio.com) for *rosserial_arduino* project.

1. Install platformio extension from VS code extensions

In case of the Platformio installation error *PlatformIO IDE can't find Python interpreter on Linux* install python3-venv
```sudo apt install python3-venv```
2. Once the platformio extension is installed, create a new project in platformio vscode 
- give a project name 
- select the board     // search for *uno*
- select a project location

3. Platformio automatically detects the USB port to which Arduino board is connect to the PC. In case, it does not, follow these steps \
a) Run the command ```ls /dev/tty* ``` in a terminal \
b) USB port would be listed as /dev/ttyUSB* \
c) Edit the *platformio.ini* file within the project folder \
	- Add the line
    *monitor_port* *= /dev/ttyUSB0*  
  &nbsp;&nbsp;&nbsp;&nbsp;if the step b lists the port as ```/dev/ttyUSB0```

4. Build *ros_lib* library in the project folder \
 - Right click on the ```lib``` folder in the project folder within the VS code explorer pane.
    - Select the option “Open in Integrated Terminal”. _This will open the directory in a terminal within VS code
    - In the terminal window you just opened, run the following command:

```rosrun rosserial_arduino make_libraries.py . ```    
&nbsp;&nbsp;&nbsp;&nbsp;Note the "." at the end; this would create *ros_lib* library in the *lib* folder. \

This will build the ros_lib library in your project. Once this is finished we can move on to using our test script for out microcontroller. 

5. Write the script to be downloaded to Arduino in the project name/src/main.cpp

6. Build the project and upload it to the Arduino board

### [Video tutorial](https://youtu.be/RZAXBMoWJcE)

### Other Errors
- In case of the following error *avrdude stk500_recv() programmer is not responding* comes up while uploading the code to the Arduino board, follow the solutions in the links given below.

[99-platformio-udev.rules](https://docs.platformio.org/en/latest/core/installation/udev-rules.html) \\
[platformio-arduino-error message](https://techoverflow.net/2021/11/11/how-i-fixed-platformio-arduino/) 

- *avrdude stk500_recv() programmer is not responding* may also arise if ROS Serial is running while code is being dumped to Arduino board. \\
The solution is simple : Stop the rosserial_arduino running in the terminal and then and then again try to dump code to Arduino.

