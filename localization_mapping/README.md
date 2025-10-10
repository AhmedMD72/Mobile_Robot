# Localization 

localization launch file
```
ros2 launch localization_mapping localization.launch.py 
```
Open spawn robot
```
ros2 launch arabian_robot arabian_localization.launch.py 
```
show pose
```
ros2 topic echo /amcl_pose 
```

# Mapping

Mapping launch file
```
ros2 launch localization_mapping online_sync_launch.py 
```
Open spawn robot
``` 
ros2 launch arabian_robot arabian_localization.launch.py 
```
Save map
```
ros2 run nav2_map_server map_saver_cli -f ~/ws/src/localization_mapping/maps/map_name
```