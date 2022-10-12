cmake_minimum_required(VERSION 3.15)

project(acl
    LANGUAGES C
    VERSION 0.1.0
    DESCRIPTION "ACL programming language"
)

message(${CMAKE_SOURCE_DIR})
message(${CMAKE_CURRENT_SOURCE_DIR})

set(target_name ${PROJECT_NAME})
set(target_sources ${CMAKE_SOURCE_DIR}/src/main.c src/getline.c)

add_executable(${target_name} ${target_sources})
target_include_directories(${target_name} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

target_compile_features(${target_name} PRIVATE c_std_99)
