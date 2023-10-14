cmake_minimum_required(VERSION 3.20)

project(RedEngine)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)


# RedEngine
add_library(RedEngine SHARED
    RedEngine/src/lib.hpp
    RedEngine/src/lib.cpp
)

add_executable(sandbox
    sandbox/src/main.cpp
)

target_include_directories(sandbox PRIVATE RedEngine/include)

target_link_libraries(sandbox PRIVATE RedEngine)

if (WIN32)
target_compile_definitions(RedEngine PRIVATE RE_API=__declspec\(dllexport\))
target_compile_definitions(sandbox PRIVATE RE_API=__declspec\(dllimport\))
else()
target_compile_definitions(RedEngine PRIVATE RE_API=)
target_compile_definitions(sandbox PRIVATE RE_API=)
endif()