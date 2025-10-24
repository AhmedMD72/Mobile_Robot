# Arabian Robot – Localization, Mapping & Navigation (ROS2)

This repository provides full launch pipelines to:
- Localize the robot on a pre-built map (AMCL)
- Build a map using SLAM
- Navigate autonomously using NAV2

All steps are listed in the correct execution order so that anyone can run the robot easily.

Before running any launch file:

```bash
cd ~/ws
colcon build
source install/setup.bash
```

# Localization (Using AMCL on an Existing Map)

Step 1 — Start Localization System

This launches AMCL, map server and TF configuration:
```
ros2 launch localization_mapping localization.launch.py 
```
Step 2 — Spawn the Robot into Simulation

This loads the robot into the world for localization:
```
ros2 launch arabian_robot arabian_localization_Nav2.launch.py 
```
Step 3 — Check Localization Output

Verify that AMCL is publishing pose estimation:
```
ros2 topic echo /amcl_pose 
```

# Mapping (SLAM Mode)

Step 1 — Start SLAM System

SLAM for real-time map building:
```
ros2 launch localization_mapping online_sync_launch.py 
```
Step 2 — Spawn the Robot

Robot appears in simulation and starts mapping:
``` 
ros2 launch arabian_robot arabian_mapping.launch.py 
```
Move the robot around to expand the map.

Step 3 — Save the Map

Export the map for later use in navigation:
```
ros2 run nav2_map_server map_saver_cli -f ~/ws/src/localization_mapping/maps/map_name
```
Replace map_name with a custom map name (example: lab_map).

# Navigation (Autonomous Navigation using Nav2)

Step 1 — Launch Navigation Stack

This loads Nav2 behavior-tree, planner, controller, etc.:
```
ros2 launch localization_mapping navigation.launch.py 
```
Step 2 — Spawn Robot with the Saved Map

Robot loads into the world with a map for navigation:
``` 
ros2 launch arabian_robot arabian_localization_Nav2.launch.py 
```
Step 3 — Send a Navigation Goal

In RViz2:
-Click 2D Goal Pose
-Choose a target location

Robot will plan and drive autonomously to the goal.

[Watch Video](https://drive.google.com/file/d/1Mdbh5qZR7xEDJG6i__6BwaaVV5frPcUn/view?usp=drive_link)
