cmake_minimum_required(VERSION 3.2)

project(hello_head)

set(SRC_LIST src/Hello.cpp src/main.cpp)

add_executable(hello_binary ${SRC_LIST})

target_include_directories(hello_binary PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)