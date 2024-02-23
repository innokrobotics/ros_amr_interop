cmake_minimum_required(VERSION 3.0.2)
project(vda5050_connector)

add_compile_options(-std=c++14)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  actionlib
  actionlib_msgs
  tf2
  tf2_ros
  geometry_msgs
  vda5050_msgs
  
)

catkin_python_setup()

add_action_files(
  DIRECTORY action
  FILES
  NavigateToNode.action
  ProcessVDAAction.action
)

add_service_files(
  DIRECTORY srv
  FILES
  GetState.srv
  SupportedActions.srv
)

generate_messages(
  DEPENDENCIES
  vda5050_msgs
  actionlib_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS 
)

include_directories(
 include
 ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
                      scripts/mqtt_bridge
                      scripts/vda5050_controller
                      DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY
  config
  launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)