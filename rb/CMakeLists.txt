cmake_minimum_required(VERSION 2.8.3)
project(rb)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  urdf
  xacro
  geometry_msgs
  roscpp
  message_generation
)

catkin_package(
  CATKIN_DEPENDS 
  geometry_msgs
  std_msgs
  roscpp
)

find_package(roslaunch)

foreach(dir config launch meshes urdf)
          install(DIRECTORY ${dir}/
            DESTINATION
${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)