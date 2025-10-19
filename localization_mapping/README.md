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
ros2 launch arabian_robot arabian_localization&Nav2.launch.py 
```
Save map
```
ros2 run nav2_map_server map_saver_cli -f ~/ws/src/localization_mapping/maps/map_name
```

# Navigation

Nanigation launch file 
```
ros2 launch localization_mapping navigation.launch.py 
```
Open spawn robot
``` 
ros2 launch arabian_robot arabian_localization&Nav2.launch.py 
```

[Watch Video](https://drive.google.com/file/d/1Mdbh5qZR7xEDJG6i__6BwaaVV5frPcUn/view?usp=drive_link)
