#
# This is a CMake makefile.  You can find the cmake utility and
# information about it at http://www.cmake.org
#

cmake_minimum_required(VERSION 2.8.4)

# create a variable called target_name and set it to the string "imglab"
set (target_name imglab)

PROJECT(${target_name})

# add all the cpp files we want to compile to this list.  This tells
# cmake that they are part of our target (which is the executable named imglab)
ADD_EXECUTABLE(${target_name} 
   src/main.cpp
   src/metadata_editor.h
   src/metadata_editor.cpp
   src/convert_pascal_xml.h
   src/convert_pascal_xml.cpp
   src/convert_pascal_v1.h
   src/convert_pascal_v1.cpp
   src/convert_idl.h
   src/convert_idl.cpp
   src/common.h
   src/common.cpp
   src/cluster.cpp
)


# Tell cmake to link our target executable to dlib.  
include(../../dlib/cmake)
TARGET_LINK_LIBRARIES(${target_name} dlib )


INSTALL(TARGETS ${target_name}
	RUNTIME DESTINATION bin
	)

