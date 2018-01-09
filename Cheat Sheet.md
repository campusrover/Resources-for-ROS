#Cheat Sheet for Common Commands of ROS
##Hints on how to get the STDR running:
1. Create a package (cd to catkin_ws/src)
```
catkin_create_pkg <package_name> [depend1] [depend2] [depend3]
E.g. catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
```
2. Put the python in <pkg>/src or gedit filename.py
3. Make it(python code) excecutable(cd to <pkg>/src)
`chmod +x <fileName>.py`
4. (cd to catkin_ws/)
`catkin_make`
5. (excecute code)
```
roscore
rosrun <package_name> <excecutable>
```

##UI Instructions:
- Simple use case, server, gui and a robot
`$ roslaunch stdr_launchers server_with_map_and_gui_plus_robot.launch`
- No map, no robot
```
$ roslaunch stdr_launchers server_no_map.launch
$ roslaunch stdr_gui stdr_gui.launch
```
 
##Using Rviz to visualize robot, sensor measurements
`$ roslaunch stdr_launchers rviz.launch`
 
##MAP
- Loading a map, using load_map tool
```
$ roscd stdr_resources
$ rosrun stdr_server load_map maps/sparse_obstacles.yaml
```
- Spawn a server with a map already loaded
```
<node type="stdr_server_node" pkg="stdr_server" name="stdr_server" args="$(find stdr_resources)/maps/sparse_obstacles.yaml"/>
$ roslaunch stdr_launchers server_with_map.launch
```
 
##Robot Manipulation
[http://wiki.ros.org/stdr_simulator/Tutorials/Robot%20manipulation](http://wiki.ros.org/stdr_simulator/Tutorials/Robot%20manipulation)
`$ roslaunch turblebot_teleop_key.launch`
