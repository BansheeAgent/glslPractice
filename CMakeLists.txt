cmake_minimum_required(VERSION 3.16)
project(glslPractice VERSION 1.0)

set(CMAKE_CXX_STANDARD 14)

#MACROS====================================================

#============================================================
add_executable(glslPractice main.cpp lib/glad/src/glad.c)

# after downloading the glfw files, include the subdirectory for glfw using add_subdirectory
add_subdirectory(lib/glfw)
add_subdirectory(lib/glm)


# step 3 including a directory for glfw located in the project folder
include_directories(lib/glfw/include)
include_directories(lib/glad/include)
include_directories(lib/glm)


# step 4 target the project folder, and include glad and glfw.
#   Specify the GLFW_Library in brackets
target_link_libraries(glslPractice glfw ${GLFW_LIBRARY})