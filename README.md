# Robotics_Map_My_World
Project #4 Map My World for [Robotics Software Engineer Nanodegree Program](https://www.udacity.com/course/robotics-software-engineer--nd209)

![Mapping Using RTAB-Map](https://github.com/jordanjj8/Robotics_Map_My_World/blob/master/End.JPG)

## Overview 
Refer to this YouTube Link for how I mapped the environment: https://www.youtube.com/watch?v=amcQPbuU8bI

## Description
In this project, my robot will navigate through the world to create a 2D occupancy grid and 3D octomap from a simulated environment with the RTAB-Map package.

## Requirements 
* [Gazebo](http://gazebosim.org/) any version later than v7.0.0 
* ROS Kinetic -follow instructions here: [ROS Installation Instructions](http://wiki.ros.org/ROS/Installation)
* GNU make 
  - Installation for Windows 
  - Installation for Mac
  - make is installed by default for most Linux distros 
* C++11 Complier (gcc/g++)

Recommended Virtual Machine Alternative Specs:
* Ubuntu 64-bit Disk Image 
* 2 GB of RAM 
* 20 GB Disk Space
* 4 Logical Cores 

## Setup
1. After installing and meeting the requirements listed above, open up a terminal.
2. Create and initialize a catkin workspace:
``` 
    $ mkdir -p /home/workspace/catkin_ws/src
    $ cd /home/workspace/catkin_ws/src
    $ catkin_init_workspace
```
3. Clone the project repository & move the `my_robot` and `teleop_twist_keyboard` directories into the `src` directory:
```
    $ cd /home/workspace/catkin_ws/src
    $ git clone https://github.com/jordanjj8/Map_My_World.git
    $ mv Robotics_Map_My_World/teleop_twist_keyboard /home/workspace/catkin_ws/src/teleop_twist_keyboard 
    $ mv Robotics_Map_My_World/my_robot /home/workspace/catkin_ws/src/my_robot
    $ rm -rf Robotics_Map_My_World
```
4. Navigate back to the catkin workspace and build the executables:
```
    $ cd /home/workspace/catkin_ws/
    $ catkin_make
```
5. Source the setup script and launch the launch file. The robot in Gazebo should open up:
``` 
    $ cd /home/workspace/catkin_ws/
    $ source devel/setup.bash
    $ roslaunch my_robot world.launch 
```
6. Now open up another terminal and launch teleop.launch in the teleop_twist_keyboard package. This will enable the user to move the robot.
```
    $ cd /home/workspace/catkin_ws/
    $ source devel/setup.bash
    $ roslaunch teleop_twist_keyboard teleop.launch
```
7. Now open up a 3rd terminal and launch mapping.launch in the my_robot package. This will launch the RTAB-Map, which is a solution for SLAM. Essentially allowing the user to create a 3D map of the environment. 
```
    $ cd /home/workspace/catkin_ws/
    $ source devel/setup.bash
    $ rosrun my_robot mapping.launch
```
## Related Links
http://wiki.ros.org/rtabmap_ros/Tutorials/SetupOnYourRobot

http://wiki.ros.org/rtabmap_ros

## Generated Map
[Jordan's RTAB-Map](https://drive.google.com/file/d/1ri2tReLaP2ABAebjvOoi2olMTl1NMBm1/view?usp=sharing)
