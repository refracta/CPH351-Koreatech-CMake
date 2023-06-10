cmake_minimum_required(VERSION 3.23)
project(CPH351)

file(GLOB children RELATIVE ${CMAKE_SOURCE_DIR} ${CMAKE_SOURCE_DIR}/*)

# add_subdirectory(extraRes) # No CMakeLists.txt
add_subdirectory(DSTimer)
add_subdirectory(HelloOpenMP)
add_subdirectory(Lab_OpenMP_MatMul)
add_subdirectory(OpenMP_Histogram)
add_subdirectory(OpenMP_Lecture1)
add_subdirectory(OpenMP_Lecture2)
add_subdirectory(OpenMP_Lecture3)
add_subdirectory(OpenMP_MatMulVet)
add_subdirectory(OpenMP_Trapezoidal)
add_subdirectory(OpenMP_VectorSum)
# add_subdirectory(CryptoImage) # Need OpenCV

add_subdirectory(CUDA_Histogram)
add_subdirectory(CUDA_Lecture1)
add_subdirectory(CUDA_Lecture2)
# add_subdirectory(CUDA_Lecture3) # No CMakeLists.txt
add_subdirectory(CUDA_Lecture4)
add_subdirectory(CUDA_Lecture5)
add_subdirectory(CUDA_MatrixAdd)
add_subdirectory(CUDA_MatrixMul)
add_subdirectory(CUDA_Trapezodial)
add_subdirectory(CUDA_VectorSum)