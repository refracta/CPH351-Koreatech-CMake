cmake_minimum_required(VERSION 3.9)
project(Lab_OpenMP_MatMul LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(ROOT_DIR ${PROJECT_SOURCE_DIR})
file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})

find_package(OpenMP REQUIRED)

add_executable(Lab_OpenMP_MatMul ${SOURCES})
target_link_libraries(Lab_OpenMP_MatMul PRIVATE OpenMP::OpenMP_CXX)
