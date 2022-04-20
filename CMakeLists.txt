cmake_minimum_required(VERSION 3.16.0)
project(test_pcl_install)

include(CTest)
include(GNUInstallDirs)

find_package(PCL 1.10 REQUIRED COMPONENTS common io octree filters features)

add_executable(test_pcl_install test_pcl_install.cpp)
target_include_directories(test_pcl_install PUBLIC ${PCL_INCLUDE_DIRS})
target_link_libraries(test_pcl_install PUBLIC ${PCL_LIBRARIES})
add_test(NAME test_pcl_install COMMAND test_pcl_install)