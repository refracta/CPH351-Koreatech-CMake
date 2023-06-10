cmake_minimum_required(VERSION 3.9)
project(CUDA_MatrixMul LANGUAGES CXX CUDA)

set(ROOT_DIR ${PROJECT_SOURCE_DIR})

file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})
set(CMAKE_CUDA_STANDARD 23)
set(CMAKE_CXX_STANDARD 23)

find_package(CUDA)

add_executable(CUDA_MatrixMul ${SOURCES})
target_link_libraries(CUDA_MatrixMul PRIVATE DSTimer)
target_include_directories(CUDA_MatrixMul PRIVATE ../DSTimer)
set_target_properties(CUDA_MatrixMul PROPERTIES CUDA_SEPARABLE_COMPILATION ON)
target_compile_options(CUDA_MatrixMul PRIVATE $<$<COMPILE_LANGUAGE:CUDA>: -Xcompiler=-openmp>)
set_property(TARGET CUDA_MatrixMul PROPERTY CUDA_ARCHITECTURES 86)

if (APPLE)
    set_property(TARGET CUDA_MatrixMul PROPERTY BUILD_RPATH ${CMAKE_CUDA_IMPLICIT_LINK_DIRECTORIES})
endif ()

if (MSVC)
    target_link_options(CUDA_MatrixMul PRIVATE "/NODEFAULTLIB:libcmt.lib")
endif ()