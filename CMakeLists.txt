cmake_minimum_required(VERSION 4.1)
project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 20)

add_executable(LearnOpenGL main.cpp glad.c)

find_package(glfw3 REQUIRED)
target_link_libraries(LearnOpenGL glfw)
target_include_directories(LearnOpenGL PRIVATE include)

set(ASSET_FOLDERS "shaders" "textures")

foreach(FOLDER ${ASSET_FOLDERS})
    add_custom_command(
            TARGET LearnOpenGL POST_BUILD
            COMMAND ${CMAKE_COMMAND} -E copy_directory
            "${CMAKE_CURRENT_SOURCE_DIR}/${FOLDER}"
            "${CMAKE_CURRENT_BINARY_DIR}/${FOLDER}"
            COMMENT "Copying ${FOLDER} to build directory..."
    )
endforeach()