# ROS-Navigation-stack-project
In this project the urdf file used is from the previous task for [urdf and plugins](https://github.com/Mo-Elshamy/Robotic-operating-system-ROS-course/tree/main/plugin_task/robo/src). First, gmaping is used to generate a map for the enviroment and save it. Second, implementing amcl algorithm to localize the robot in the enviroment. Finaly, implementing the navigation stack and adjust its parameters to reach maximum desired performance efficency.

## First: generating map using Gmaping :
[Gmaping pkg](./src/robo_gmapping/)
To run the pkg. First, run the roscore ,gazebo and rviz. the use the command:
```
roslaunch robo_gmaping slam_gmapping_pr2.launch 
```
then, open the teleop twist keyboard to move the robot manualy in the enviroment using the command:
```
roslaunch turtlebot_teleop keyboard_teleop.launch
```
and move the robot all over the enviroment to scan the map as shown below.


https://github.com/Mo-Elshamy/ROS-Navigation-stack-project/assets/121442515/de7e606a-fe24-4243-89f9-b835518f5c98


Then, save the final map which is named home in this project by using the following command:
```
rosrun map_server map_saver -f home
```

## Second: implementing AMCL algorithm:
[AMCL pkg](./src/amcl/)

First adjust the parameters in the launch file [(AMCL lunch file)](./src/amcl/launch/amcl.launch). Then, run the pkg use the command:
```
roslaunch amcl amcl.launch
```
Then try move the robot in the enviroment as shown below to get the same results.

https://github.com/Mo-Elshamy/ROS-Navigation-stack-project/assets/121442515/c2ec2af2-2f4f-4e50-9be6-3c0b7f6c81ce


## Third: Navigation( using dijkstra ):
[Navigation pkg](./src/robo_navigation/)

First adjust the parameters files in the file [(param)](./src/robo_navigation/param/). the [navguide.pdf](https://github.com/Mo-Elshamy/ROS-Navigation-stack-project/files/12002612/navguide.pdf) can be helpful in adjusting the parameters. Then adjust the [(move base lunch file)](./src/robo_navigation/launch/move_base.launch) 
then run the pkg useing the command:
```
roslaunch robo_navigation move_base.launch
```
Start testing the robot by setting goals and enhance its preformence from the adjusting the parameters to get the best result.

https://github.com/Mo-Elshamy/ROS-Navigation-stack-project/assets/121442515/14936e51-5e43-4a06-a2ee-30c59c312a7a



https://github.com/Mo-Elshamy/ROS-Navigation-stack-project/assets/121442515/c6c8e5e3-5348-487f-b426-83ea16b4f26f




https://github.com/Mo-Elshamy/ROS-Navigation-stack-project/assets/121442515/c3bab7c1-f323-488d-af0a-2b96f12bb554


