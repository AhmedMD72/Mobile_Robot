#mobile-robot

# arabian_robot Package

## Installation & Build

Go to the `src` folder inside your workspace
```
cd ~/ws/src
```
Clone the repository
```
git clone https://github.com/AhmedMD72/intern_ws.git
```
Go back to the workspace root
```
cd ~/ws
```
Build the package
```
colcon build 
```
Source the setup file
```
source install/setup.bash 
```
To launch the package

```
ros2 launch arabian_robot arabian.launch.py 
```