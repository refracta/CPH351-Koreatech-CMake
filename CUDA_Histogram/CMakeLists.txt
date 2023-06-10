cmake_minimum_required(VERSION 3.9)
project(CUDA_Histogram LANGUAGES CXX CUDA)

set(ROOT_DIR ${PROJECT_SOURCE_DIR})

file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})
set(CMAKE_CUDA_STANDARD 23)
set(CMAKE_CXX_STANDARD 23)

find_package(CUDA)

add_executable(CUDA_Histogram ${SOURCES})
target_link_libraries(CUDA_Histogram PRIVATE DSTimer)
target_include_directories(CUDA_Histogram PRIVATE ../DSTimer)
set_target_properties(CUDA_Histogram PROPERTIES CUDA_SEPARABLE_COMPILATION ON)
target_compile_options(CUDA_Histogram PRIVATE $<$<COMPILE_LANGUAGE:CUDA>: -Xcompiler=-openmp>)
set_property(TARGET CUDA_Histogram PROPERTY CUDA_ARCHITECTURES 86)

if (APPLE)
    set_property(TARGET CUDA_Histogram PROPERTY BUILD_RPATH ${CMAKE_CUDA_IMPLICIT_LINK_DIRECTORIES})
endif ()

if (MSVC)
    target_link_options(CUDA_Histogram PRIVATE "/NODEFAULTLIB:libcmt.lib")
endif ()