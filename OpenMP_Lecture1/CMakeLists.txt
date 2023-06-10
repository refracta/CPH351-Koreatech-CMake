cmake_minimum_required(VERSION 3.9)
project(OpenMP_Lecture1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(ROOT_DIR ${PROJECT_SOURCE_DIR})
file(GLOB PROJECT_SRC ${ROOT_DIR}/*.cpp)

find_package(OpenMP REQUIRED)

foreach (source_file ${PROJECT_SRC})
    get_filename_component(name ${source_file} NAME_WE)
    set(target_name "${PROJECT_NAME}_${name}")
    add_executable(${target_name} ${source_file})
    target_link_libraries(${target_name} PRIVATE OpenMP::OpenMP_CXX DSTimer)
    target_include_directories(${target_name} PRIVATE ../DSTimer)
endforeach ()