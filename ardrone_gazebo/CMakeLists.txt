cmake_minimum_required(VERSION 3.8)
project(ardrone_gazebo)

find_package(ament_cmake REQUIRED)

# Install directories
install(DIRECTORY
  launch
  meshes
  models
  urdf
  worlds
  DESTINATION share/${PROJECT_NAME}
)

# Install Python scripts
install(PROGRAMS
  scripts/ardrone_driver.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
