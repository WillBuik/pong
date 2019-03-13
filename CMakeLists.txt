cmake_minimum_required (VERSION 3.8)

project ("pong-sfml-sample")

set(CMAKE_MODULE_PATH 
    ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

if(UNIX)
	set(SFML_STATIC_LIBRARIES ON)
endif(UNIX)

find_package(SFML COMPONENTS graphics window system REQUIRED)

include_directories(${SFML_INCLUDE_DIR})

add_executable (pong "pong.cpp")
target_link_libraries(pong ${SFML_LIBRARIES})
if(SFML_STATIC_LIBRARIES)
	target_link_libraries(pong ${SFML_DEPENDENCIES})
endif()
