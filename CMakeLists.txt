cmake_minimum_required(VERSION 3.13)
project(http-server-starter-cpp)
add_subdirectory(http-server-starter-cpp zlib EXCLUDE_FROM_ALL)
# Use EXCLUDE_FROM_ALL to prevent all targets from being added to the solution

add_executable(http-server-starter-cpp http-server-starter-cpp.c)
target_link_libraries(http-server-starter-cpp PRIVATE zlibstatic)
set(CMAKE_CXX_STANDARD 20) # Enable the C++20 standard

file(GLOB_RECURSE SOURCE_FILES src/*.cpp)

add_executable(server ${SOURCE_FILES})
