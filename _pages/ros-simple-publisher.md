---
title: "Simple Publisher"
permalink: /ros-simple-publisher/
layout: wide
---

## A ROS publisher node - line by line commented
```python

#!/usr/bin/env python    # shebang 

import rospy # import rospy
from std_msgs.msg import String # import String message type from std_msgs package

def lab_publisher1(): # function for the publisher

    rospy.init_node('joaquim_pub') # initialize a ros node with name 'joaquim_pub'

    # declare that your node is publishing to the topic 'robotics_lab' using the message type String.
    pub = rospy.Publisher('robotics_lab', String, queue_size=10) 
    
    
    rate = rospy.Rate(2) # creates a Rate object rate. 
    # argument of 2, we want to execute the publisher code 2 times per second 
    
    rospy.loginfo('publishing test') # rospy.loginfo can be regarded as print function, it prints the argument in the terminal
    # rospy also has other methods like rospy.logerr, rospy.logdebug, rospy.logwarn

    while not rospy.is_shutdown(): # while loop : run the program in an infinite loop until the user stops it (say by pressing ctrl+c) 
        
        msg = String() 
        msg.data = "Hello lab test" # message to be published
        
        pub.publish(msg) # publish the message via the publisher pub
        
        # rospy.loginfo(msg) # uncomment to publish message on the terminal
        
        rate.sleep() # sleep for 2 seconds (ie rate )


if __name__=='__main__':
    try:
        lab_publisher1() # call the function lab_publisher1
        
    except rospy.ROSInterruptException: # if any interruption in program occurs go to the next line. 
    
        # one interrupt in our case is keyboard interrupt ctrl + c
        
        pass # just exit 
        
```