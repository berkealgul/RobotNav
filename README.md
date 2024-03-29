# RobotNav
Minimal 2D ROS navigation system including custom OG mapping, motion planning and robot control systems. 
This package can navigate a robot from point A to B without hitting obstacles.

This package uses laserscan and odometry information

Watch [demo](https://www.youtube.com/watch?v=UGfTxcI47rI&list=PLFcVgs9SAZn24gF2VCl5zmnnEZ0ZZHbgb&index=3)

## Features

Custom 2D Occupancy Grid Mapping

A* Path Planning and PID robot control

## Usage
- Change topics at config/mapping.yaml
- run mapping launch to mapping
- run scripts/motion-planning.py for A* algorithm
- run path_follower.py for robot control system
 
Output is given as Twist message

## Limitations
- Localization is not included and must be provided externally
- Control algorithm assumes robot rotation is based around robots central z-axis
