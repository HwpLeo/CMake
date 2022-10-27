cmake_minimum_required(VERSION 3.2)

project(cmake-install)

add_library(hello_lib SHARED src/Hello.cpp)

target_include_directories(hello_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(hello_binary src/main.cpp)

target_link_libraries(hello_binary PRIVATE hello_lib)

# windows系统CMAKE_INSTALL_PREFIX默认是C:/Program Files/${PROJECT_NAME}
# windows下指定CMAKE_INSTALL_PREFIX：
# 方法一：cmake -DCMAKE_INSTALL_PREFIX=<install/path>
# 方法二：set(CMAKE_INSTALL_PREFIX <install/path>)，需要加在project之后

# message(${CMAKE_INSTALL_PREFIX})
# set(CMAKE_INSTALL_PREFIX ${CMAKE_SOURCE_DIR}/install)
# install binary
install(TARGETS hello_binary DESTINATION bin)
# install library
install(TARGETS hello_lib DESTINATION lib)
# install directory
install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include DESTINATION include)
# install file
install(FILES cmake-examples.conf DESTINATION etc)