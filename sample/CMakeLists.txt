
cmake_minimum_required(VERSION 2.8)
cmake_policy(VERSION 2.8)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_SOURCE_DIR}/cmake)

project(wlcpp_sample)

add_definitions(-Wall --std=c++11)

find_package(WaylandClient REQUIRED)
include_directories(${WaylandClient_INCLUDE_DIRS})

add_executable(wlcpp_sample
    main.cpp
    display.hpp
    display.cpp
    event_queue.hpp
    event_queue.cpp
    proxy.hpp
    proxy.cpp
    wlcpp.hpp
    wlcpp.cpp
)

target_link_libraries(wlcpp_sample
    ${WaylandClient_LIBRARIES}
)

