cmake_minimum_required(VERSION 3.10)
project(GraphicsProject)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(PROJECT_NAME "GraphicsProject")

set(SOURCE_FILES  main.cpp glutfunctions.h algos.h usage.h  headers.h renderer.h)
add_executable(${PROJECT_NAME} ${SOURCE_FILES})

find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIRS})

find_package(GLUT REQUIRED)
include_directories(${GLUT_INCLUDE_DIRS})

#find_package(GLUT REQUIRED)

find_package(Threads REQUIRED)


target_link_libraries(${PROJECT_NAME}  ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} Threads::Threads)