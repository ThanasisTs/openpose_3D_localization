# OpenPose ROS packages for Human-Robot Collaboration

A collection of ROS catkin packages that utilize the OpenPose library from https://github.com/CMU-Perceptual-Computing-Lab/openpose in order to detect human presence near a robotic arm workspace and provide the robot's motion planner with the input which is necessary to guarantee safe Human-Robot Collaboration.

This repo depends on:

* https://github.com/firephinx/openpose_ros
* https://github.com/ros-perception/ar_track_alvar
* https://github.com/Roboskel-Manipulation/manos_vision
* https://github.com/gstavrinos/tf_based_on_ar_marker


Note: The zed_wrapper package, which is also a dependency, has not been added to the package.xml, in order to allow for easier compilation. You will need to install it if you are planning to use a ZED camera.


## Contents

* **openpose_ros_receiver**: Receive the OpenPose output's skeletons and transform their keypoints coordinates from the camera coordinate frame to the robot coordinate frame.
* **openpose_ros_receiver_msgs**: The messages used to publish the openpose_ros_receiver output (human body skeletons with keypoint coordinates in the robot coordinate frame) to a ROS environment. 
* **openpose_ros_avoid**: Receive human body skeletons based on the BODY_25 human pose model and insert them as obstacles in a robotic arm's workspace.
* **openpose_utils_launch**: Launch files for all the above.

## System

Tested on:
* ROS Indigo / Kinetic / Melodic
* openpose_ros commit #6222834
* OpenPose v1.5.0
