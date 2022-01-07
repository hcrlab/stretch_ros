# Bumped to support Cython commands
cmake_minimum_required(VERSION 3.3.2)
project(stretch_funmap)

find_package(catkin REQUIRED COMPONENTS
  rospy
)

find_package(PythonLibs 3.8 REQUIRED)

catkin_python_setup()

catkin_package(
)

###########
## Build ##
###########

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${PYTHON_INCLUDE_DIRS}
)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/src/cmake)
find_package(Cython)
add_subdirectory(src/cython_min_cost_path)

set_target_properties(cython_min_cost_path
  PROPERTIES
  LIBRARY_OUTPUT_DIRECTORY
  ${CATKIN_DEVEL_PREFIX}/${CATKIN_PACKAGE_PYTHON_DESTINATION})