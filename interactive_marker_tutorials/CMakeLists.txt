# http://ros.org/doc/groovy/api/catkin/html/user_guide/supposed.html
cmake_minimum_required(VERSION 2.8.3)
project(interactive_marker_tutorials)
# Load catkin and all dependencies required for this package
find_package(catkin REQUIRED COMPONENTS roscpp visualization_msgs interactive_markers)

if(NOT CMAKE_CONFIGURATION_TYPES AND NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
    DEPENDS 
    CATKIN-DEPENDS roscpp visualization_msgs interactive_markers 
    INCLUDE_DIRS 
    LIBRARIES 
)

include_directories( ${catkin_INCLUDE_DIRS})
link_directories(${catkin_LIBRARY_DIRS})

add_executable(simple_marker src/simple_marker.cpp)
target_link_libraries(simple_marker ${catkin_LIBRARIES})
add_executable(basic_controls src/basic_controls.cpp)
target_link_libraries(basic_controls ${catkin_LIBRARIES})
add_executable(selection src/selection.cpp)
target_link_libraries(selection ${catkin_LIBRARIES})
add_executable(pong src/pong.cpp)
target_link_libraries(pong ${catkin_LIBRARIES})
add_executable(cube src/cube.cpp)
target_link_libraries(cube ${catkin_LIBRARIES})
add_executable(menu src/menu.cpp)
target_link_libraries(menu ${catkin_LIBRARIES})
add_executable(point_cloud src/point_cloud.cpp)
target_link_libraries(point_cloud ${catkin_LIBRARIES})

install(TARGETS simple_marker basic_controls selection pong cube menu point_cloud
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

