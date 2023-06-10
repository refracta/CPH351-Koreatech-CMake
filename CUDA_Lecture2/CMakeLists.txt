cmake_minimum_required(VERSION 3.9)
project(CUDA_Lecture2 LANGUAGES CXX CUDA)

set(ROOT_DIR ${PROJECT_SOURCE_DIR})

file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})
set(CMAKE_CUDA_STANDARD 23)
set(CMAKE_CXX_STANDARD 23)
file(GLOB PROJECT_SRC ${ROOT_DIR}/*.cu)

find_package(CUDA)

foreach (source_file ${PROJECT_SRC})
    get_filename_component(name ${source_file} NAME_WE)
    set(target_name "${PROJECT_NAME}_${name}")

    add_executable(${target_name} ${source_file})
    target_link_libraries(${target_name} PRIVATE DSTimer)
    target_include_directories(${target_name} PRIVATE ../DSTimer)
    set_target_properties(${target_name} PROPERTIES CUDA_SEPARABLE_COMPILATION ON)
    target_compile_options(${target_name} PRIVATE $<$<COMPILE_LANGUAGE:CUDA>: -Xcompiler=-openmp>)
    set_property(TARGET ${target_name} PROPERTY CUDA_ARCHITECTURES 86)

    if (APPLE)
        set_property(TARGET ${target_name} PROPERTY BUILD_RPATH ${CMAKE_CUDA_IMPLICIT_LINK_DIRECTORIES})
    endif ()

    if (MSVC)
        target_link_options(${target_name} PRIVATE "/NODEFAULTLIB:libcmt.lib")
    endif ()
endforeach ()