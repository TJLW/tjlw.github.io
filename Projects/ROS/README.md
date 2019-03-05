<p align="right">
<a href="https://tjlw.github.io/">Go to Home page</a>
</p>




# Robotic Operating System

<p align="center"> <img width="auto" src="https://github.com/TJLW/tjlw.github.io/blob/master/Projects/ROS/Images/ros_logo.png?raw=True"/> </p>


## Overview



## Robot Specific ROS Nodes




### Robot Description

One of the foundations of ROS functionality is the TF library, or the transform library. This allows an easy method for transforming between various frames of reference. For instance, the ground on which our robot will always be a static frame of reference as it never moves. However, our robot with wheels can move along the ground changing position and orientation with respect to the ground. If one intends to draw a map using only data from the robot, the current transformation from the ground frame to the robot's frame must be known.

<p align="center"> <img width="auto" src="https://github.com/TJLW/tjlw.github.io/blob/master/Projects/ROS/Images/SimpleTFExample.png?raw=True"/> </p>
<p align="center">
	The simple grids above show two examples of how the robot's frame, marked by the red circle, can change with respect to the static ground frame, denoted by the grid. The robot's orientation is denoted with the green (positive X) and blue (positive Y) axes. In grid a), the robot orientation is inline with the ground frame and thus no transformation is needed to change between frames. In grid b), the robot has moved to position (-2,0) on the map grid and has also turned 90 degrees counterclockwise. Here, we must apply a translation and rotation to change between the map and robot frame.
</p>

ROS transformations allow for translations and rotations in the X, Y and Z dimensions.

In order to effectively apply transformations and quickly change between frames, ROS allows for a robot model or description to be given as URDF file of links and joints. Links are physical structures of the robot such as the wheel, while joints denote connections between links, such as the axle joint connection the wheel and robot frame links. This description must be in the form of a valid TF tree such that every child link must have only a single parent link.

With a given robot description, the ROS package robot_state_publisher will handle the broadcast of the current robot state to the TF library, thus ensuring the appropriate transform is available when needed to all ROS nodes.

For the [Arlo Autonomous Ground Vehicle](https://tjlw.github.io/Projects/ArloAGV), the primary transformations needed are from the laser scanner frame to the robot base frame, both wheel frames to the robot base frame, and lastly, the robot base frame to the static map frame or ground. The former two are static as the laser and the wheels are both mounted to the robot base frame. The final robot base frame to map frame transformation can be determined by dead-reckoning odometry from wheel encoders or more sophisticated odometry methods using the laser scanner.



PLACE ARLO TF TREE EXAMPLE HERE (ARLO NODES ONLY)
<p align="center">
	This local TF tree denotes the relationships written in the robot description URDF file.
</p>


PLACE ARLO TF TREE EXAMPLE HERE (WITH MAP)
<p align="center">
	This global TF tree additionally add the map frame. Note the map frame is not given in the URDF file and is, in our case, intended to be served by a ROS node that builds a map.
</p>



### Odometry

As can be seen in the Global TF tree above, the primary parent is the map frame with a single child, the odometry frame. The robot description



### Joint Interface




### Mobility



## Cartography

## Localization

## Obstacle Avoidance









Updated: 4 March 2019, Published: 4 March 2019
