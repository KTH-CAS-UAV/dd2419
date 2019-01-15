# dd2419

## Install instructions
```bash
cd ~/catkin_ws
wstool init src
wstool merge -t src https://raw.githubusercontent.com/danielduberg/dd2419/master/.rosinstall --merge-replace
wstool update -t src
rosdep install --from-paths src --ignore-src -r -y
catkin build
source devel/setup.bash
roscd dd2419_simulation
mkdir build
cd build
cmake ../../sim_cf/crazyflie-firmware/sitl_make/
make
```

## Launch instructions
```bash
# Launch the simulation
roslaunch simulation simulation.launch

# Launch aruco_ros
roslaunch simulation aruco.launch gui:=true
```

## Insert objects into the world
In Gazebo press the tnsert tab. In the list you will find objects such as `gate`, `b2` (stop sign), `aruco_visual_mark_X`, and so on.
