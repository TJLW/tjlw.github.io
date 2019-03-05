<p align="right">
<a href="https://tjlw.github.io/">Go to Home page</a>
</p>

# Autonomous Ground Vehicles

<p align="center"> <img width="auto" src="https://github.com/TJLW/tjlw.github.io/blob/master/Projects/AGV/Images/ArloControlUnit.png?raw=True"/> </p>
<p align="center">
	Arlo Ground Vehicle Research Platform
</p>


### Description

We have utilized the Arlo Complete Robotic System by Parallax as the physical framework for our research into autonomous ground vehicles. This kit, [which can be bought here](https://www.parallax.com/product/28966), includes a frame, motors, wheels, optical encoders, a motor controller, and a Parallax Activity Board. However, as is tradition with our research, we opt to replace the Activity Board with a much more capable FPGA SoC.


### Overview

### Motivation

### Software

The software side of this current iteration utilizes a custom built Linux kernel built with the Xilinx Petalinux software. This allows for an easy generation of a kernel that is appropriate for any of the custom hardware implemented in programmable logic. A base Ubuntu 2018.4 LTS (Bionic Beaver) filesystem is used to complete our operating system.

Playing a central role in the software is the Robotic Operating System (ROS) in order to enable a well-organized control system. Currently with our selection of Ubuntu 2018.2, we are using the latest distribution (at this time) ROS Melodic Morenia.


### Hardware

As mentioned above, this iteration of our research platform includes a frame, motors, wheels, optical encoders, and a motor controller. The FPGA SoC we chose for this application is the Digilent Zybo Z7 board with the Zynq7010 SoC onboard.

Published: 4 March 2019
Updated: 4 March 2019
