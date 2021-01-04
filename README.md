# Robotics_ROS_Ball_Chaser

ROS imlementation of a simple Robot within a Gazebo simulated office.  The robot uses
a camera to look for a white ball and navigates towards it.

Contains two ROS packages:
1. **my_robot**:  Simple robot consisting of 2 rotation wheels and a caster wheel for movement, a Camera and LiDAR sensor for sensing.

2. **ball_chaser**:  Ball chaser package with 2 nodes implemented in C++:
- **drive_bot**:  Service for commanding robot's movement
- **process_image**:  Subcribes to raw images, detects if a white ball is withing Field of View and drives the bot accordingly.

## Usage

Clone this project into your catkin workspace's **src** directory:
```
$ cd ~/catkin_ws/src
$ git clone https://github.com/jarix/Robotics_ROS_Ball_Chaser.git
```

Build project:
```$ cd ~/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

Launch the Robot world (my_robot, Gazebo, and RViz):

`roslaunch my_robot world.launch`

Launch the ball chaser node:

`roslaunch ball_chaser ball_chaser.launch`

## Environment

Developed and tested on ROS Kinetic

## Screenshots

### Office Environment in Gazebo
![Gazebo office world](./screenshots/gazebo_world.jpg)

### Robot with 2 wheels and caster, Camera and LiDAR sensors
![Robot with two wheels and caster](./screenshots/robot.jpg)

### RViz with Camera and LiDAR views
![RViz with Camera and Lidar Views](./screenshots/rviz_view.jpg)
