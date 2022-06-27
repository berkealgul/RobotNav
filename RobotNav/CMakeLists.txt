cmake_minimum_required(VERSION 3.0.2)
project(RobotNav)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  sensor_msgs
)


catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES rover_20_image
#  CATKIN_DEPENDS roscpp rospy std_msgs
#  DEPENDS system_lib
)

find_package(Eigen3 REQUIRED)
find_package(PCL REQUIRED)
find_package(OpenCV REQUIRED)
link_directories(${PCL_LIBRARY_DIRS})

include_directories(
  include 
  ${catkin_INCLUDE_DIRS}
  ${Eigen_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS}
  ${OpenCV_LIBS}
)

add_library(oc_map 
  src/map/map.cpp
  src/map/costmap.cpp
  src/map/occmap.cpp
)

target_link_libraries(oc_map ${catkin_LIBRARIES})

add_executable(fake_scan_demo src/fake_scan_demo.cpp)
target_link_libraries(fake_scan_demo oc_map ${catkin_LIBRARIES})

add_executable(mapping src/mapping.cpp)
target_link_libraries(mapping oc_map ${catkin_LIBRARIES})
