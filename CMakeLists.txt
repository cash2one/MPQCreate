cmake_minimum_required(VERSION 2.0)

project(MPQCreate)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/")

if(WIN32)
  set(Boost_USE_STATIC_LIBS   ON)
  set(Boost_USE_MULTITHREADED ON)
endif(WIN32)

find_package(StormLib REQUIRED)
include_directories(${STORMLIB_INCLUDE_DIR})

find_package(Boost COMPONENTS system filesystem program_options REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_executable(mpqcreate mpqcreate.cpp)
target_link_libraries(mpqcreate ${Boost_LIBRARIES} ${STORMLIB_LIBRARIES})
