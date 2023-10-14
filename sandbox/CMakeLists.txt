add_executable(sandbox main.cpp)

target_include_directories(sandbox PRIVATE ../RedEngine/include)

target_link_libraries(sandbox PRIVATE RedEngine)

