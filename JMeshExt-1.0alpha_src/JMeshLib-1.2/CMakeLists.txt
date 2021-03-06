cmake_minimum_required(VERSION 2.6)
project(libjmesh)

SET(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-strict-aliasing")

add_definitions(-DIS64BITPLATFORM)

include_directories( ${PROJECT_SOURCE_DIR}/include )

file(GLOB SOURCES_JMESH "${PROJECT_SOURCE_DIR}/src/JMESH/*.cpp")
file(GLOB SOURCES_MESH_STRUCTURE "${PROJECT_SOURCE_DIR}/src/MESH_STRUCTURE/*.cpp")
file(GLOB SOURCES_OBJECTS "${PROJECT_SOURCE_DIR}/src/OBJECTS/*.cpp")
file(GLOB SOURCES_PRIMITIVES "${PROJECT_SOURCE_DIR}/src/PRIMITIVES/*.cpp")
add_library(jmesh STATIC 
  ${SOURCES_JMESH} 
  ${SOURCES_MESH_STRUCTURE}
  ${SOURCES_OBJECTS} 
  ${SOURCES_PRIMITIVES})
