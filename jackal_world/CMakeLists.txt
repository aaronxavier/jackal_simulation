cmake_minimum_required(VERSION 2.8.3)
project(jackal_world)

find_package(catkin REQUIRED COMPONENTS roslaunch)

catkin_package()

roslaunch_add_file_check(launch/jackal_world.launch)

install(DIRECTORY meshes launch urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

link_directories(${GAZEBO_LIBRARY_DIRS})

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${src}
  ${GAZEBO_INCLUDE_DIRS}
)
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

if(WIN32)
install(PROGRAMS scripts/env_run.bat
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
else()
install(PROGRAMS scripts/env_run
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
endif()
