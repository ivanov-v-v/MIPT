cmake_minimum_required(VERSION 3.5.1)
project(client)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")

include_directories(../../lstring/ ../text-formatting-tools/)
set(SOURCE_FILES main.c ../../lstring/lstring.h ../text-formatting-tools/msgformat.h)
set_source_files_properties(main.c PROPERTIES COMPILE_FLAGS "-g -std=gnu99 -Wall -Wextra -pedantic -O2")
add_executable(client ${SOURCE_FILES})

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
target_link_libraries(client Threads::Threads)
