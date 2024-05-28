cmake_minimum_required(VERSION 3.10)
project(Rasterizer)


find_package(OpenCV REQUIRED)
find_package(Eigen3 REQUIRED)  # 注意这里是使用Eigen3进行查找
message("Eigen3_FOUND = ${Eigen3_FOUND}")

set(CMAKE_CXX_STANDARD 17)

message("EIGEN3_INCLUDE_DIR = ${EIGEN3_INCLUDE_DIR}")
#include_directories(${EIGEN3_INCLUDE_DIR})

add_executable(Rasterizer main.cpp rasterizer.hpp rasterizer.cpp Triangle.hpp Triangle.cpp)
target_link_libraries(Rasterizer ${OpenCV_LIBRARIES})
target_link_libraries(Rasterizer Eigen3::Eigen)  # 使用Eigen3的链接方式
