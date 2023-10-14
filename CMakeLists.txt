cmake_minimum_required(VERSION 3.20)

project(RedEngine)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# should be added before the dependency packages 
add_subdirectory(RedEngine)

add_subdirectory(sandbox)

