How to Run the Simulation
Launch the drone simulation:
With GUI (Standard):
ros2 launch ardrone_gazebo single_ardrone.launch.py
Launch in Rubicon World:
ros2 launch ardrone_gazebo single_ardrone.launch.py world:=rubicon.sdf
Launch in Empty World:
ros2 launch ardrone_gazebo single_ardrone.launch.py world:=ardrone_empty.sdf
Take off:
ros2 topic pub -1 ardrone/takeoff std_msgs/msg/Empty {}
Control flight commands via teleop keyboard:
ros2 run teleop_twist_keyboard teleop_twist_keyboard
Land:
ros2 topic pub -1 ardrone/land std_msgs/msg/Empty {}
