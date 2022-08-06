cmake_minimum_required(VERSION 3.10.0)

project(rs2pcd VERSION 1.0)

find_package(OpenCV REQUIRED)
find_package(realsense2 REQUIRED)
find_package(PCL 1.8 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

#set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

add_executable(${PROJECT_NAME} rs2pcd.cpp)
target_link_libraries(${PROJECT_NAME} 
                      ${realsense2_LIBRARY} 
                      ${OpenCV_LIBS} 
                      ${PCL_LIBRARIES}
                     )