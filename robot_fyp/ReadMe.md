sudo apt update && apt upgrade
cd catkin_ws/src/robot_fyp
1. roscore

2. roslaunch robot_fyp empty.launch
   roslaunch robot_fyp test.launch

3. roslaunch robot_fyp gmapping.launch        (run rviz and gmapping)
   roslaunch robot_fyp rviz.launch            (run rviz only to in empty world to check odometry)

4. rosrun robot_fyp keyboard_teleop.py        (run controller)

5. rosrun map_server map_saver -f ~/test_map  (save map)

6. roslaunch robot_fyp amcl_move_base.launch (start amcl,move_base) (run rviz and navigate robot inside created map)

7. rostopic list
   rostopic echo /odom     (check robot pose)
   rostopic echo /cmd_vel  (check robot translation and rotation velocity)
