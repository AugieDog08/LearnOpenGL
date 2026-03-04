cmake_minimum_required(VERSION 4.1)
project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 20)

add_executable(LearnOpenGL main.cpp glad.c
        include/shader.h)

find_package(glfw3 REQUIRED)
target_link_libraries(LearnOpenGL glfw)
target_include_directories(LearnOpenGL PRIVATE include)

file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/shaders"
DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")