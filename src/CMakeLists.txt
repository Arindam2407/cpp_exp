add_library(cpp_exp_lib
    "../include/example.h"
    example.cpp)
add_library(cpp_exp::lib ALIAS cpp_exp_lib)
target_include_directories(cpp_exp_lib PUBLIC "${PROJECT_SOURCE_DIR}/include")

add_library(cpp_exp_another
    "../include/another.h"
    another.cpp)
add_library(cpp_exp::another ALIAS cpp_exp_another)
target_include_directories(cpp_exp_another PUBLIC "${PROJECT_SOURCE_DIR}/include")

add_executable(main "main.cpp")
target_link_libraries(main PRIVATE cpp_exp::lib cpp_exp::another)