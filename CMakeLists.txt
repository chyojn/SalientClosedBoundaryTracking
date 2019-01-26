cmake_minimum_required(VERSION 3.6)
project(SalientClosedBoundaryTracking)

set(CMAKE_CXX_STANDARD 11)

include_directories(../ED_Lib)
link_directories(../ED_Lib/cmake-build-release)

set(OpenCV_DIR /usr/local/opt/opencv@3/share/OpenCV)
find_package(OpenCV 3)
include_directories(${OpenCV_INCLUDE_DIRS})

find_package(Boost)
include_directories(${Boost_INCLUDE_DIRS})

add_executable(SalientClosedBoundaryTracking
        BDSP_optimization.cpp
        BDSP_optimization.h
        CmdLine.cpp
        CmdLine.h
        CommonFunctions.cpp
        CommonFunctions.h
        construct_graph.cpp
        construct_graph.h
        construct_graph_dt.cpp
        construct_graph_dt.h
        mat_main.cpp
        mat_main.h
        match.c
        match.h
        SalientBoundaryTracking.cpp
        shapeTracker.cpp
        shapeTracker.h
        Timer.h)
target_link_libraries(SalientClosedBoundaryTracking
        ${OpenCV_LIBS} EDLib)