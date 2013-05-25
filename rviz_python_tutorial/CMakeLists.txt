# http://ros.org/doc/groovy/api/catkin/html/user_guide/supposed.html
cmake_minimum_required(VERSION 2.8.3)
project(rviz_python_tutorial)
# Load catkin and all dependencies required for this package
find_package(catkin REQUIRED COMPONENTS rviz)

## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
    DEPENDS
    CATKIN-DEPENDS rviz 
    INCLUDE_DIRS 
    LIBRARIES 
)
