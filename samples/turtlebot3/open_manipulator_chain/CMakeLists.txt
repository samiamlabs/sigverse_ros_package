cmake_minimum_required(VERSION 2.8.3)
project(sigverse_turtlebot3_open_manipulator)

add_definitions(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  roscpp
  rospy
  std_msgs
  geometry_msgs
  trajectory_msgs
  sensor_msgs
  tf
  darknet_ros_msgs
)


catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES sigverse_ros_bridge
  CATKIN_DEPENDS 
    geometry_msgs 
    trajectory_msgs 
    roscpp 
    rospy 
    std_msgs
    darknet_ros_msgs
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)


link_directories(/usr/local/lib)


add_executable(grasping_teleop_key src/grasping_teleop_key.cpp)
target_link_libraries(grasping_teleop_key ${catkin_LIBRARIES})


# add_executable(grasping_auto src/grasping_auto.cpp)
# target_link_libraries(grasping_auto ${catkin_LIBRARIES})
# add_dependencies(grasping_auto darknet_ros_msgs_generate_messages_cpp)

add_executable(recognize_pointed_direction src/recognize_pointed_direction.cpp)
target_link_libraries(recognize_pointed_direction ${catkin_LIBRARIES})


