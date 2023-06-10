cmake_minimum_required(VERSION 3.9)
project(CryptoImage LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(ROOT_DIR ${PROJECT_SOURCE_DIR})
file(GLOB PROJECT_SRC ${ROOT_DIR}/*)
set(SOURCES ${PROJECT_SRC})
file(GLOB COMMON_SRC ${ROOT_DIR}/Src/*)
file(GLOB LAB_CRYPTOIMG_SOURCE ${ROOT_DIR}/Lab_CryptoImg/*)

find_package(OpenMP REQUIRED)

set(OpenCV_DIR "/your/opencv/build")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(CryptoImage_Encryptor Encryptor/main.cpp ${COMMON_SRC})
target_link_libraries(CryptoImage_Encryptor PRIVATE ${OpenCV_LIBS} OpenMP::OpenMP_CXX)

add_executable(CryptoImage_Lab_CryptoImg ${LAB_CRYPTOIMG_SOURCE})
target_link_libraries(CryptoImage_Lab_CryptoImg PRIVATE OpenMP::OpenMP_CXX)

add_executable(CryptoImage_Viewer Viewer/main.cpp ${COMMON_SRC})
target_link_libraries(CryptoImage_Encryptor PRIVATE ${OpenCV_LIBS} OpenMP::OpenMP_CXX)