cmake_minimum_required(VERSION 3.2)

project(hello_cmake)

message(${CMAKE_BINARY_DIR})

message(${PROJECT_BINARY_DIR})


add_executable(${PROJECT_NAME} main.cpp)