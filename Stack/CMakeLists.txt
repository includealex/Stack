cmake_minimum_required(VERSION 3.16.3)
project(StackLib VERSION 1.0.0 DESCRIPTION "Stack library")

add_subdirectory(test)
add_subdirectory(timeResearch)

file(GLOB_RECURSE STACK_SOURCES *.cpp)
file(GLOB_RECURSE STACK_HEADERS *.h)

add_library(stack STATIC ${STACK_SOURCES} ${STACK_HEADERS})

set(STACK_INCLUDE ${CMAKE_CURRENT_SOURCE_DIR}/includes)
target_include_directories(stack PUBLIC ${STACK_INCLUDE})

set_target_properties(stack PROPERTIES
    CXX_STANDARD          11
    CXX_STANDARD_REQUIRED ON
)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Werror -Wextra -Wpedantic -Wcast-qual -Wcast-align -Wconversion \
    -Wsign-promo -Wfloat-equal -Wenum-compare -Wold-style-cast -Wredundant-decls -Wsign-conversion -Wnon-virtual-dtor \
    -Wctor-dtor-privacy -Woverloaded-virtual -Wno-float-equal"
)