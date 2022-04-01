cmake_minimum_required(VERSION 3.5)
project(EConsole LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/out)


if(WIN32)
    add_subdirectory("lib/PDCurses 3.9")
elseif(UNIX)
    message("Ncurses временно отсутствует!")
endif()


set(files
    src/ConsoleConstructor.cpp
    include/ConsoleConstructor.h)

add_library(EConsole SHARED ${files})
target_link_libraries(EConsole PRIVATE PDCurses)
target_include_directories(EConsole PRIVATE include)
