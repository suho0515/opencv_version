cmake_minimum_required(VERSION 3.1)
project(opencv_version_test)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

set(OpenCV_DIR /home/eh420/installation/OpenCV-master/lib/cmake/opencv4)

find_package(catkin REQUIRED COMPONENTS roscpp cv_bridge)
find_package(OpenCV REQUIRED)

catkin_package(  
  CATKIN_DEPENDS 
  roscpp
  cv_bridge
)

include_directories(${catkin_INCLUDE_DIRS})

add_executable(opencv_version_test src/opencv_version_test.cpp)
target_link_libraries(opencv_version_test ${catkin_LIBRARIES} ${OpenCV_LIBS})
