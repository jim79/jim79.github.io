---
title: "How to include a launch file inside a launch file"
permalink: /include-a-launch-file-inside-a-launch-file/
layout: single
---

Assume we have a launch file called ```main_launch_file.launch``` to launch another launch file called ```first_launch_file.launch``` from the ```first_bot``` package. 

The ```first_launch_file.launch``` file is within the folder named _launch_ of the ```first_bot``` package 

We can use the include tag in our ```main_launch_file.launch``` launch as given below

```<launch>
    <include file="$(find first_bot)/launch/first_launch_file.launch" />
</launch>```

Then when you run ```run roslaunch main_launch_file.launch ``` , the nodes from the ```first_launch_file.launch``` will also be launched.

