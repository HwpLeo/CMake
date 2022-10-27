cmake_minimum_required(VERSION 3.2)

project(hello_shared)

add_library(hello_library SHARED src/Hello.cpp)

target_include_directories(hello_library PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(hello_binary src/main.cpp)

target_link_libraries(hello_binary PRIVATE hello_library)