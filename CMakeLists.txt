# CMakeLists.txt
cmake_minimum_required(VERSION 4.2.1 FATAL_ERROR)
# Define the project
set(PROJECT_NAME cpp_opengl)    
project(${PROJECT_NAME} LANGUAGES CXX)
# Set C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
# Set build type to Debug
set(CMAKE_BUILD_TYPE Debug)
# Specify Clang as the compiler
set(CMAKE_C_COMPILER clang)
set(CMAKE_CXX_COMPILER clang++)
# Add the executable
add_executable(${PROJECT_NAME} src/main.cpp)
# GLFW options
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)
# Subdirectories
add_subdirectory(external/glfw)
target_link_libraries(${PROJECT_NAME} PRIVATE glfw)