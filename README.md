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

## Autonomous Visual SLAM & Exploration

This mode launches the drone in a custom depot environment, builds a 2D map using the onboard RGBD camera via RTAB-Map, and autonomously explores the unknown areas using MRTSP and Nav2.

1. **Launch the fully autonomous system**:
   ```bash
   ros2 launch ardrone_gazebo visual_slam_drone.launch.py
   ```
   *Note: This automatically spawns the drone in `tugbot_depot.sdf`, opens RViz2 with the mapping configuration, and starts an `rqt_image_view` window for the drone's live camera feed.*

2. **Wait for Auto-Takeoff**:
   The drone will take off automatically after 8 seconds of initialization. Once airborne, the MRTSP exploration node will take control and autonomously navigate the drone to map the environment.


## Manual Exploration using TELEOP:

This mode launches the drone in a custom depot environment, builds a 2D map using the onboard RGBD camera via RTAB-Map, and u can manually explore the areas.

1. **Launch the manual system**:
   ```bash
   ros2 launch ardrone_gazebo manual_teleop_drone.launch.py
   ```
   *Note: This automatically spawns the drone in `tugbot_depot.sdf`, opens RViz2 with the mapping configuration, and starts an `rqt_image_view` window for the drone's live camera feed.*

2. **Wait for Auto-Takeoff**:
   The drone will take off automatically after 8 seconds of initialization. After that, you can control the drone using TELEOP.
