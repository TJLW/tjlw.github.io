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

Complete list of current hardware:
- Arlo Complete Robotic System
- Digilent Zybo Z7 7010 SoC
- RPLIDAR A1 Rangefinder
- USB WiFi Dongle (Realtek 8192CU Chipset)
- Four port USB 2.0 Hub, Powered

As mentioned above, this iteration of our research platform includes a frame, motors, wheels, optical encoders, and a motor controller. The motor controller will handle the interpretation of the encoder signals and is the primary interface for control, configuration, and status updates of the motors.

The FPGA SoC we chose for this application is the Digilent Zybo Z7 board with the Zynq7010 SoC onboard.

Without any internal wireless chipset, we needed to include a USB WiFi dongle in order to utilize the wireless networking stack in our Linux kernel and subsequently for ROS and other user applications.

For perception, we are currently evaluating the versatility of a single two-dimensional 360 degree laser range-finder or lidar. We are using the Slamtec RPLIDAR A1, [available here](https://www.slamtec.com/en/Lidar/A1). This communicates with our FPGA over USB connected to the onboard Zynq processor running our Linux distribution. The default serial baud rate is 19200 but can be increased to 115200 for faster transfer rates. In our case, we are currently maximizing this to ensure we are able to quickly issue motor speed commands and request motor speed updates.

Digilent support documentation for Zybo Z7 warns that many USB devices will exceed the current limit set by the SoC circuitry. As we are using more than one USB device, we selected a USB hub capable of accepting an external power supply. The Arlo power distribution board provides a number of power connections, one of which was utilized to provide a stable 5 volts at maximum 2 amps.


Published: 4 March 2019
Updated: 4 March 2019
