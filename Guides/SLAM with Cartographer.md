## How to install and run NAV2 Cartographer
### Instructions for Ubuntu
#### Installing cartographer

`sudo apt install ros-foxy-turtlebot3-cartographer`

This will install cartographer, turtlebot3 (a webot with approapriate sensors), and a world with a room simulation.

#### Running Cartographer

The webots world can be opened with the following command:

`ros2 launch webots_ros2_turtlebot robot_launch.py`

In a second terminal launch cartographer using the following command:

`export TURTLEBOT3_MODEL='burger'
ros2 launch turtlebot3_navigation2.launch.py use_sim_time:=true map:=$(ros2 pkg prefix webots_ros2_turtlebot --share)/resource/turtlebot3_burger_example_map.yaml`
    
#### Using Cartographer for SLAM

To initialize SLAM you must select "2D Pose Estimate" and then click where burger bot is. To move the bot you can select anywhere in the room with "Navigation2 Goal" the bot will then attempt to navigate to the selected point
