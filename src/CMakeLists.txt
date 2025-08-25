add_library(riverlane_lib
    "../include/example.h"
    example.cpp)
add_library(riverlane::lib ALIAS riverlane_lib)
target_include_directories(riverlane_lib PUBLIC "${PROJECT_SOURCE_DIR}/include")

add_library(riverlane_another
    "../include/another.h"
    another.cpp)
add_library(riverlane::another ALIAS riverlane_another)
target_include_directories(riverlane_another PUBLIC "${PROJECT_SOURCE_DIR}/include")

add_executable(main "main.cpp")
target_link_libraries(main PRIVATE riverlane::lib riverlane::another)