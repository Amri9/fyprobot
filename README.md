sudo apt update && apt upgrade
cd catkin_ws/src/robot_fyp

1. roscore  (start rosmaster)

2. roslaunch robot_fyp empty.launch      (launch robot in empty world)
   roslaunch robot_fyp test.launch       (launch robot in the created environment)

3. roslaunch robot_fyp gmapping.launch        (run rviz and gmapping to do mapping process)
   roslaunch robot_fyp rviz.launch            (run rviz only in empty world to check odometry, camera and sensor data)

4. rosrun robot_fyp keyboard_teleop.py        (run keyboard controller to control robot manually inside the environment to do mapping process) 

5. rosrun map_server map_saver -f ~/test_map  (save map after mapping process done)

6. roslaunch robot_fyp amcl_move_base.launch (start amcl,move_base or navigation stack package) (run rviz and navigate robot inside created map)

7. rostopic list
   rostopic echo /odom     (check robot position and velocity, timestamp)
   rostopic echo /cmd_vel  (check robot translation and rotation velocity)
   rostopic pub /cmd_vel geometry_msgs/Twist  (give input velocity to the robot)
