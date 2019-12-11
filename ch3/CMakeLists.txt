cmake_minimum_required(VERSION 2.8)

project(ch3)

# 设置编译模式
set(CMAKE_BUILD_TYPE "Debug")

SET(CMAKE_CXX_FLAGS "-std=c++11 -O3") #加的，要不然会报错

include_directories("/usr/include/eigen3")
add_executable(coordinateTransform coordinateTransform.cpp)

find_package(Pangolin REQUIRED)
include_directories(${Pangolin_INCLUDE_DIRS})
add_executable(plotTrajectory plotTrajectory.cpp)
target_link_libraries(plotTrajectory ${Pangolin_LIBRARIES})
