cmake_minimum_required(VERSION 3.22.1)

project(LearnGStreamer C)

find_package(PkgConfig REQUIRED)

pkg_check_modules(gstreamr-1.0 REQUIRED gstreamer-1.0)
include_directories(${gstreamr-1.0_INCLUDE_DIRS})

pkg_check_modules(GTK3 REQUIRED gtk+-3.0)
include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})

add_executable(basic-tutorial-2-exercise basic-tutorial-2-exercise.c)
target_link_directories(basic-tutorial-2-exercise PRIVATE ${gstreamr-1.0_LIBRARY_DIRS})
target_link_libraries(basic-tutorial-2-exercise ${gstreamr-1.0_LIBRARIES})

add_executable(basic-tutorial-3-exercise basic-tutorial-3-exercise.c)
target_link_directories(basic-tutorial-3-exercise PRIVATE ${gstreamr-1.0_LIBRARY_DIRS})
target_link_libraries(basic-tutorial-3-exercise ${gstreamr-1.0_LIBRARIES})

