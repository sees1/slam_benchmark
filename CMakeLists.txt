cmake_minimum_required(VERSION 3.0.2)
project(slam_benchmark)

find_package(catkin)

catkin_package()

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)