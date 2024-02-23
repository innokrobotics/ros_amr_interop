cmake_minimum_required(VERSION 3.5)
project(vda5050_msgs)


if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(catkin REQUIRED COMPONENTS
   roscpp
   rospy
   std_msgs
   message_generation
)

add_message_files(
  FILES
  Action.msg
  ActionParameter.msg
  ActionParameterDefinition.msg
  AGVAction.msg
  AGVGeometry.msg
  AGVPosition.msg
  BatteryState.msg
  BoundingBoxReference.msg
  Connection.msg
  ControlPoint.msg
  CurrentAction.msg
  Edge.msg
  EdgeState.msg
  Envelope2D.msg
  Envelope3D.msg
  Error.msg
  ErrorReference.msg
  Factsheet.msg
  Info.msg
  InfoReference.msg
  Header.msg
  InstantActions.msg
  Load.msg
  LoadDimensions.msg
  LoadSet.msg
  LoadSpecification.msg
  MaxArrayLens.msg
  MaxStringLens.msg
  Node.msg
  NodePosition.msg
  NodeState.msg
  OptionalParameter.msg
  Order.msg
  OrderState.msg
  PhysicalParameters.msg
  PolygonPoint.msg
  Position.msg
  ProtocolFeatures.msg
  ProtocolLimits.msg
  SafetyState.msg
  Timing.msg
  Trajectory.msg
  TypeSpecification.msg
  Velocity.msg
  Visualization.msg
  WheelDefinition.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS 
  message_runtime
)
