cmake_minimum_required(VERSION 3.9)
project(Stack)

add_subdirectory(Stack)

file(GLOB_RECURSE ALL_CXX_SOURCE_FILES *.cpp *.h)

find_program(CLANG_FORMAT "clang-format" REQUIRED)
add_custom_target(
    stack-format
    COMMAND clang-format
    -i
    -style=file
    ${ALL_CXX_SOURCE_FILES}
)
