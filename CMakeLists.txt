cmake_minimum_required(VERSION 2.8)
# Project Name
PROJECT(CG2016)
set (CMAKE_CXX_STANDARD 11)

#########################################################
# FIND GLUT
#########################################################
find_package(GLUT REQUIRED)
include_directories(${GLUT_INCLUDE_DIRS})
link_directories(${GLUT_LIBRARY_DIRS})
add_definitions(${GLUT_DEFINITIONS})
if(NOT GLUT_FOUND)
    message(ERROR " GLUT not found!")
endif(NOT GLUT_FOUND)
#########################################################
# FIND OPENGL
#########################################################
find_package(OpenGL REQUIRED)
include_directories(${OpenGL_INCLUDE_DIRS})
link_directories(${OpenGL_LIBRARY_DIRS})
add_definitions(${OpenGL_DEFINITIONS})
if(NOT OPENGL_FOUND)
    message(ERROR " OPENGL not found!")
endif(NOT OPENGL_FOUND)
#########################################################
# Include Files
#########################################################
add_executable(output RotateACube/RotateACube.cpp RotateACube/RotateACube.h RectangularMesh/RectangularMesh.h RectangularMesh/RectangularMesh.cpp main.cpp main.h RotatingAHouse/RotatingAHouse.cpp RotatingAHouse/RotatingAHouse.h SierpinskiGasket/SierpinskiGasket.cpp SierpinskiGasket/SierpinskiGasket.h LiangBarsky/LiangBarsky.cpp LiangBarsky/LiangBarsky.h CohenSutherland/CohenSutherland.cpp CohenSutherland/CohenSutherland.h SpinACube/SpinACube.cpp SpinACube/RotateACube.h ClippingAlgorithm/ClippingAlgorithm.cpp ClippingAlgorithm/ClippingAlgorithm.h CylinderAndParallelpiped/CylinderAndParallelpiped.cpp CylinderAndParallelpiped/CylinderAndParallelpiped.h Teapot/Teapot.cpp Teapot/Teapot.h Scanline/Scanline.cpp Scanline/Scanline.h)

########################################################
# Linking & stuff
#########################################################


# create the program "output"
target_link_libraries(output ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} )
