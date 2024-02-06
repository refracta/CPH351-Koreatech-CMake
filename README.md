# CPH351-Koreatech
본 레포지토리는 멀티코어 프로그래밍 과목의 소스 코드를 CMake를 이용하여 빌드할 수 있도록 수정한 것 입니다. CMake 기반 빌드 시스템을 갖춘 IDE 또는 CMake 명령어를 이용하여 손쉽게 본 과목의 예제 프로그램들을 빌드하여 실행해볼 수 있습니다.

# [CPH351](https://sites.google.com/view/hpclab/courses/multicore-programming) Multi-core programming, [KOREATECH](https://www.koreatech.ac.kr/)
Instructor : [Duksu Kim](https://sites.google.com/view/duksukim/)

### Course overview
Parallel computing is a form of computation that utilizes multiple computing resources for solving a problem. Recently, parallel computing is widely employed in various fields (e.g., simulation, graphics, AI, Etc.) to improve the performance in the perspective of speed or accuracy. Among various parallel computing architectures, multi-core CPUs and GPUs are most commonly employed computing resources. This course aims to understand the power of parallel computing and learn a basic programming skill for developing a parallel program. During the 16-week course, students will learn
- Concept of parallel computing, How to design parallel algorithms
- OpenMP - A programming interface for utilizing multi-core CPUs (MIMD architecture)
- CUDA - A programming interface for utilizing a NVIDIA GPU (many-core SIMT architecture)
Also, students will join two team projects whose goal is improving the performance of an application by using multi-core CPUs or/and GPUs.


### Lecture notes and videos (KOR) are available in [Here](https://hpclab.tistory.com/4)

### Contents
- Codes used in lectures
  - [OpenMP 1 (Lecture 4)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_Lecture1)
  - [OpenMP 2 (Lecture 5)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_Lecture2)
  - [OpenMP 3 (Lecture 6)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_Lecture3)
  - [CUDA 1 (Lecture 8)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_Lecture1)
  - [CUDA 2 (Lecture 9)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_Lecture2)
  - [CUDA 3 (Lecture 10)] No codes for this lecture
  - [CUDA 4 (Lecture 11)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_Lecture4)
  - [CUDA 5 (Lecture 12)](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_Lecture5)
- [OpenMP] [Hello OpenMP](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/HelloOpenMP) (A solution code for Lab. 1-1)
  - Our first parallel program
- [OpenMP] [VecterSum](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_VectorSum) (A solution code for Lab. 1-2)
  - The first version of parallel vector summation
  - This version only uses the parallel construct
- [OpenMP] [Matrix-Vector Mulitplication](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_MatMulVet) (A solution code for Lab. 2-1)
  - A simple parllel algorithm for matrix-vector multiplication
- [OpenMP] [Trapezoidal Rule](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_Trapezoidal) (A solution code for Lab. 2-2)
  - Parallel trapezodial rule algorithm that calcuate area of a function (e.g., x*x) for a given range
  - Various types of parallel algorithms are avaialbe
- [OpenMP] [Histogram](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/OpenMP_Histogram) (A solution code for Lab. 3)
  - Parallel histogram construction algorithm
  - Various parallel algorithms are implemented
- [CUDA] [VectorSum](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_VectorSum) (A solution code for Lab. 4-1)
  - CUDA program that compute the summation of two vectors
  - Support a large vectors (e.g., larger than 1024)
- [CUDA] [MatrixAdd](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_MatrixAdd) (A solution code for Lab. 4-2)
  - Matrix addtion
  - Three types of thread layouts are available
- [CUDA] [MatrixMul](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_MatrixMul) (A solution code for Lab. 5 and Lab 6-1)
  - Matrix multiplication
  - Three types of kernels are available
    - Global memory version
    - Shared memory version
    - Shared memory without bank conflict version
- [CUDA] [Trapezodial Rule on GPU](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/CUDA_Trapezodial) (A solution code for Lab. 7)
  - Various types of parallel algorithms are available
- [DSTimer](https://gitlab.com/DuksuKim/multi-core-programming-.-cph351-koreatech/tree/master/CPH351/DSTimer) (Utility program)
  - The timer class used for measuring processing time in this project
  - This is a part of [DSLib](https://gitlab.com/DuksuKim/dslib?nav_source=navbar)
