---
title: "Simple Subscriber"
permalink: /ros-simple-subscriber/
layout: wide
---
## A ROS subsriber node line by line commented
```python

#!/usr/bin/env python    # shebang 

import rospy # import rospy

from std_msgs.msg import String # import String message type from std_msgs package

def print_message(msg): # function to print the message received from the publisher. Also know as callback function

    rospy.loginfo("Message received") # rospy.loginfo would print the message received on the terminal
    
    rospy.loginfo(msg) # print the message

def lab_subscriber1(): # subscriber function

    rospy.init_node('joaquim_sub') # intitialize a subscriber node 'joaquim_sub'
    
     # declare that your node is subscribing to the topic 'robotics_lab' using the message type String and that the callback function is 		print_message
     
    sub = rospy.Subscriber("robotics_lab", String, print_message)  

    rospy.spin() #  simply keeps your node from exiting until the node has been shutdown

if __name__=='__main__': # ensures that the code runs only when its is executed as script

    lab_subscriber1() # call the subscriber function
    
```