## How to Run the Simulation

1. Launch the drone simulation:
   * **With GUI (Standard)**:
     ```bash
     ros2 launch ardrone_gazebo single_ardrone.launch.py
     ```
     * **Launch in Rubicon World**:
     ```bash
     ros2 launch ardrone_gazebo single_ardrone.launch.py world:=rubicon.sdf
     ```
     * **Launch in Empty World**:
     ```bash
     ros2 launch ardrone_gazebo single_ardrone.launch.py world:=ardrone_empty.sdf
     ```
3. Take off:
   ```bash
   ros2 topic pub -1 ardrone/takeoff std_msgs/msg/Empty {}
   ```
4. Control flight commands via teleop keyboard:
   ```bash
   ros2 run teleop_twist_keyboard teleop_twist_keyboard
   ```
5. Land:
   ```bash
   ros2 topic pub -1 ardrone/land std_msgs/msg/Empty {}
   ```
