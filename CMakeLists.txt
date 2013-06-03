cmake_minimum_required(VERSION 2.8.3)
project(reflexxes_type2)

if (NOT CMAKE_CONFIGURATION_TYPES AND NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

include_directories(include)

find_package(catkin)

catkin_package(
  INCLUDE_DIRS
  LIBRARIES ${PROJECT_NAME}
  DEPENDS 
  )

file(GLOB_RECURSE RML_SOURCE_CODE src/TypeIIRML/*.cpp)
add_library(${PROJECT_NAME} ${RML_SOURCE_CODE})

install(DIRECTORY include/ DESTINATION include)

install(TARGETS ${PROJECT_NAME}
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})

