cmake_minimum_required(VERSION 3.1.3)
project(heap_urdf)

set(CATKIN_PACKAGE_DEPENDENCIES
    xacro
)

find_package(catkin REQUIRED COMPONENTS
    ${CATKIN_PACKAGE_DEPENDENCIES}
)

###################################
## catkin specific configuration ##
###################################
catkin_package(
  INCLUDE_DIRS
  LIBRARIES
  CATKIN_DEPENDS ${CATKIN_PACKAGE_DEPENDENCIES}
  DEPENDS
)

###########
## Build ##
###########
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_compile_options(-Wall -Werror)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

#############
## Install ##
#############

install(DIRECTORY
        meshes
        urdf
        launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
