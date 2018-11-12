cmake_minimum_required(VERSION 3.9)
project(cdjpeg C)

set(CMAKE_C_STANDARD 99)

set(LIBJPEG_INCLUDE_DIR ../library/bin)

include_directories($(LIBJPEG_INCLUDE_DIR))

add_executable(cjpeg cjpeg.c)
add_executable(djpeg djpeg.c)

target_link_libraries(cjpeg libjpeg)
ADD_DEPENDENCIES(cjpeg libjpeg)

target_link_libraries(djpeg libjpeg)
ADD_DEPENDENCIES(djpeg libjpeg)
