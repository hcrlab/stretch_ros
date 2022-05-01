cmake_minimum_required(VERSION 3.0.2)
project(stretch_description)


find_package(catkin REQUIRED COMPONENTS
  message_generation
  message_runtime
  rospy
)

catkin_package(
)


install(DIRECTORY config launch meshes robots urdf
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
        )
