### Testing setup

- Input size
    - Matrix : 10,000 by 10,000
    - Vector : 1 by 10,000
- System
    - Intel i7-8700 Quad-core CPU
        - Hyper-threading support
    - 32 GB memory
    - Windows 10

### Performance

- Serial : 95.5 ms (1.00x)
- Parallel
    - 2 threads : 47.9 ms (1.99x)
    - 4 threads : 24.7 ms (3.86x)
    - 8 threads : 14.4 ms (6.63x)