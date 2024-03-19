cmake_minimum_required(VERSION 3.0)
project(tetris_hsa)

add_executable(tetris_hsa src/main.c src/display_tetris.c src/display_menu.c)
target_include_directories(tetris_hsa PUBLIC include)

install(TARGETS tetris_hsa DESTINATION /usr/local/bin)
install(DIRECTORY ${CMAKE_SOURCE_DIR}/include/ DESTINATION /usr/local/include)
install(DIRECTORY ${CMAKE_SOURCE_DIR}/src/ DESTINATION /usr/local/src)

set(CPACK_CMAKE_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "hsa")
set(CPACK_DEBIAN_PACKAGE_DESCRIPTION "Tetris game")
include(CPack)