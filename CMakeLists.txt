cmake_minimum_required(VERSION 3.13)
project(http-server-starter-cpp)
find_package(ZLIB REQUIRED)

add_executable(myproject myproject.c)
target_link_libraries(myproject PRIVATE ZLIB::ZLIB)
set(CMAKE_CXX_STANDARD 20) # Enable the C++20 standard

file(GLOB_RECURSE SOURCE_FILES src/*.cpp)

add_executable(server ${SOURCE_FILES})
