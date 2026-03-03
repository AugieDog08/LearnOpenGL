cmake_minimum_required(VERSION 4.1)
project(opengl)

set(CMAKE_CXX_STANDARD 20)

add_executable(opengl main.cpp glad.c)

find_package(glfw3 REQUIRED)
target_link_libraries(opengl glfw)
target_include_directories(opengl PRIVATE include)