# RobotNav
Minimal 2D ROS navigation system including custom OG mapping and motion planning systems. 
This package can navigate a robot from point A to B without hitting obstacles.

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
- Control algorithm is based on rotation around robots central z-axis
