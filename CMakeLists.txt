cmake_minimum_required(VERSION 3.8)
project(pong-sfml-sample)

find_package(SFML CONFIG COMPONENTS graphics REQUIRED)
add_executable(pong "pong.cpp")
target_link_libraries(pong PRIVATE sfml-graphics)

configure_file(resources/sansation.ttf resources/sansation.ttf COPYONLY)
