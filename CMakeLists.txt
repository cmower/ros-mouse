cmake_minimum_required(VERSION 3.0.2)
project(mouse)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  sensor_msgs
  message_generation
)

add_message_files(
  FILES
  MouseButton.msg
  MouseMotion.msg
  MouseWheel.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package()

include_directories(
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
  scripts/mouse
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
