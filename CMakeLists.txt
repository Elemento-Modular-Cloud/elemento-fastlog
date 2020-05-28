cmake_minimum_required(VERSION 3.12)
project(logf)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_INSTALL_PREFIX ./bin)

include_directories(include)

add_library(logf INTERFACE)
target_include_directories(logf INTERFACE fastlog.h)
install(TARGETS logf
    DESTINATION ${CMAKE_INSTALL_PREFIX}
    )

add_executable(logf-example
        main.cpp)
install(TARGETS logf-example
    DESTINATION ${CMAKE_INSTALL_PREFIX}
    )

target_link_libraries(logf-example logf)
