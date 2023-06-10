# [CPH351](http://hpc.koreatech.ac.kr/course_mp.html) Multi-core programming, [KOREATECH](https://www.koreatech.ac.kr/)

### Trapezodial Rule

![Trapezodial](CPH351/OpenMP_Trapezoidal/Trape.png)

### Implemented algorithms

- Serial algorithm
- Implicit barrier version
    - Paralell algorithm using an implicit barrier
- Implicit barrier version with locally used shared variables
    - Similar with the implicit barrier version
    - In the main loop, this uses shared varibles for local calculations
- Locking version
    - This algorithm uses an explicit synchronization function, locking
- Reduction
    - It uses the reduction clause for gathering results of threads

### Performance comparision

- Testing environment
    - Intel i7-8700 Quad-core CPU, 32GB memory, Windows 10
        - Use 4 threads for parallel algorithms
    - Function: f(x) = x * x
    - Range = -1.0 ~ 1.0
    - n : (1024 * 1024 * 1024) = 1,073,741,824
- Performance

|  Serial   |    Parallel    |     Parallel      |  Parallel   | Parallel  
|:---------:|:--------------:|:-----------------:|:-----------:|:---------:|
|           | Implicit. Bar. | Shared Local Var. |   Locking   | Reduction |
| 1129.2 ms |    581.2 ms    |    18506.3 ms     | 136016.8 ms | 544.58 ms |
|   1.0 x   |     1.94 x     |      0.06 x       |   0.01 x    |  2.07 x   |