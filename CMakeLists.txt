cmake_minimum_required(VERSION 3.20)
project(ikd_tree)

find_package(Threads REQUIRED)

# ikd_tree library
add_library(ikd_tree src/ikd_Tree.cpp)

target_include_directories(
  ikd_tree PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
                  $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

target_link_libraries(ikd_tree Threads::Threads)

if(BUILD_TESTING)
  add_subdirectory(tests)
endif()
