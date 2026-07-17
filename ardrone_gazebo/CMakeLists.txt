cmake_minimum_required(VERSION 3.8)
project(ardrone_gazebo)

find_package(ament_cmake REQUIRED)

# Install directories
install(DIRECTORY
  config
  launch
  meshes
  models
  rviz
  urdf
  worlds
  DESTINATION share/${PROJECT_NAME}
)

# Install Python scripts
install(PROGRAMS
  scripts/ardrone_driver.py
  scripts/odom_tf_publisher.py
  scripts/auto_takeoff.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
