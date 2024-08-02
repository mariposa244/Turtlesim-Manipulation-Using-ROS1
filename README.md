# Turtlesim-Manipulation-Using-ROS1
This GitHub repository offers a comprehensive guide for installing and running the TurtleSim package within the Robot Operating System (ROS) framework. 
The guide covers not only the initial setup and installation process, but also provides step-by-step instructions for exploring the various components of the TurtleSim package, including topics, nodes, and services.

Additionally, the repository includes detailed guidance on how to control the virtual turtle within the simulation environment using keyboard commands. This allows users to interactively manipulate the turtle's movements and behavior, enabling them to gain a deeper understanding of the ROS ecosystem and the specific functionality provided by the TurtleSim package.

By following the instructions and resources outlined in this repository, users can quickly set up a ROS development environment, familiarize themselves with the TurtleSim package, and experiment with the capabilities of the simulated turtle. This serves as an excellent starting point for newcomers to the ROS platform, providing a hands-on learning experience and a foundation for further exploration of robotics and autonomous systems.

# Installation
1-Update your package list:

```

sudo apt-get update
```
2- Install the TurtleSim package:

```
sudo apt-get install ros-$(rosversion -d)-turtlesim
```

![image](https://github.com/user-attachments/assets/1dc67a20-b5ab-45bc-970b-925ad5444580)

# Running TurtleSim
1- Launch the ROS core:

```
roscore
```
2- run the TurtleSim node but make sure it is in a new terminal window:
```
rosrun turtlesim turtlesim_node
```
![image](https://github.com/user-attachments/assets/4cfea2e7-6d33-47e1-adc3-6c022de173b8)


a window should open displaying the TurtleSim environment with a turtle in the center.

# Exploring several Topics and nodes:
To list all active nodes:
```
rosnode list
```
![image](https://github.com/user-attachments/assets/ec0d23de-29c8-410e-a0da-3dd1c73346c7)


To get detailed information about a specific node
```
rosnode info /turtlesim
```
## 1- Publications:
/rosout [rosgraph_msgs/Log]: This node publishes ROS system log messages to the /rosout topic. These messages can be used for system tracking and diagnostics.

/turtle1/color_sensor [turtlesim/Color]: This node publishes turtle color sensor data to the /turtle1/color_sensor topic.

/turtle1/pose [turtlesim/Pose]: This node publishes the turtle's pose (coordinates and angle) to the /turtle1/pose topic.


## 2- Subscriptions:
/turtle1/cmd_vel [unknown type]: This node subscribes to the /turtle1/cmd_vel topic to receive velocity commands and move the turtle accordingly. The message type is unknown here but is typically geometry_msgs/Twist.

## 3- Services:
/clear: Service to clear the screen.

/kill: Service to kill a specified turtle.

/reset: Service to reset the simulation.

/spawn: Service to spawn a new turtle at a specified location.

/turtle1/set_pen: Service to set the turtle's pen color, line width, and whether to raise or lower the pen.

/turtle1/teleport_absolute: Service to teleport the turtle to an absolute position.

/turtle1/teleport_relative: Service to teleport the turtle relative to its current position.

/turtlesim/get_loggers: Service to get information about the system's loggers.

/turtlesim/set_logger_level: Service to set the logging level of the system.


### To list all active topics:
```
rostopic list
```
/rosout: For logging messages in the ROS system.

/rosout_agg: For aggregating and displaying logged messages.

/turtle1/cmd_vel: For sending movement (velocity) commands to the turtle.

/turtle1/color_sensor: For publishing color sensor data from the turtle.

/turtle1/pose: For publishing the turtle's pose (coordinates and orientation).

![image](https://github.com/user-attachments/assets/4c863148-38c5-49ad-8f4b-93a93d158e02)


![image](https://github.com/user-attachments/assets/3c9a9088-a8bc-4716-bc11-5a3f397f2028)

# Publishing a Message to the turtle1/cmd_vel Topic:

```
rostopic pub -1 /turtle1/cmd_vel geometry_msgs/Twist '{linear: {x: 1.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.0}}'
```
![image](https://github.com/user-attachments/assets/fee34adf-5da2-4087-8150-db859a8a8325)

## Resetting the Turtle:
```
rosservice call /reset
```
# Controlling the Turtle:
In a new terminal, run the teleop node to control the turtle using the keyboard:
```
rosrun turtlesim turtle_teleop_key
```
Use the arrow keys to move the turtle. Press q to quit.
![image](https://github.com/user-attachments/assets/0c2a8fb2-bd0b-413e-bfaf-397fd5ccf1f3)

# Getting Help for rostopic Commands:
To display help for rostopic commands:

```
rostopic --help
```
![image](https://github.com/user-attachments/assets/915d3221-7143-4fcc-8625-c6e61ac5c45d)


The Manipulate-with-turtlesim-package-in-ROS-noetic repository provides a comprehensive guide for working with the TurtleSim package in the ROS (Robot Operating System) Noetic distribution. The guide covers the installation process, running the TurtleSim node, and exploring the different nodes, topics, and services associated with the package.
Overall, this repository serves as a valuable resource for anyone interested in learning about the TurtleSim package and exploring the fundamentals of ROS through hands-on examples and instructions.
