cmake_minimum_required(VERSION 3.9)
project(CUDA_Trapezodial LANGUAGES CXX CUDA)

set(ROOT_DIR ${PROJECT_SOURCE_DIR})

file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})
set(CMAKE_CUDA_STANDARD 23)
set(CMAKE_CXX_STANDARD 23)

find_package(CUDA)

add_executable(CUDA_Trapezodial ${SOURCES})
target_link_libraries(CUDA_Trapezodial PRIVATE DSTimer)
target_include_directories(CUDA_Trapezodial PRIVATE ../DSTimer)
set_target_properties(CUDA_Trapezodial PROPERTIES CUDA_SEPARABLE_COMPILATION ON)
target_compile_options(CUDA_Trapezodial PRIVATE $<$<COMPILE_LANGUAGE:CUDA>: -Xcompiler=-openmp>)
set_property(TARGET CUDA_Trapezodial PROPERTY CUDA_ARCHITECTURES 86)

if (APPLE)
    set_property(TARGET CUDA_Trapezodial PROPERTY BUILD_RPATH ${CMAKE_CUDA_IMPLICIT_LINK_DIRECTORIES})
endif ()

if (MSVC)
    target_link_options(CUDA_Trapezodial PRIVATE "/NODEFAULTLIB:libcmt.lib")
endif ()