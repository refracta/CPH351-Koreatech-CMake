cmake_minimum_required(VERSION 3.9)
project(OpenMP_Histogram LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(ROOT_DIR ${PROJECT_SOURCE_DIR})
file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})

find_package(OpenMP REQUIRED)

add_executable(OpenMP_Histogram ${SOURCES})
target_link_libraries(OpenMP_Histogram PRIVATE OpenMP::OpenMP_CXX DSTimer)
target_include_directories(OpenMP_Histogram PRIVATE ../DSTimer)