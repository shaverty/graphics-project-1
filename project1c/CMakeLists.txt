cmake_minimum_required(VERSION 2.8)

PROJECT(project1C)
SET(VTK_DIR /home/sean/Documents/VTK)
SET(CMAKE_BUILD_TYPE Debug)
SET(VERBOSE 1)

find_package(VTK REQUIRED)
include(${VTK_USE_FILE})

add_executable(project1C MACOSX_BUNDLE project1C)

if(VTK_LIBRARIES)
  target_link_libraries(project1C ${VTK_LIBRARIES})
else()
  target_link_libraries(project1C vtkHybrid)
endif()

