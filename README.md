## Welcome to mmperf

mmperf is a single core GEMM benchmark. This repository aims to benchmark Matrix Multiply (SGEMM) hand-tuned libraries and code generation stacks on a single thread on one CPU core. The focus will be on machine learning workloads so FP32 or smaller and irregular sizes of matrices. The goal is to expose high performance atomic kernels that can then be used to build highly efficient higher level implemenations spanning multiple cores or distributed across systems when efficient atomic kernels are asynchrously scheduled with overlapping communicaitons (interchip, in a system or across a system).

# Engineered Libraries:

- Intel MKL
- OpenBLAS
- RUY
- Accelerate
- BLIS

# Compiler / Codegen kernels

- MLIR
- Halide
- TVM 

## Results


### Results on AMD Ryzen 5950x (ZenV3, compared to AMD's BLIS and OpenBLAS for RESNET50 sizes)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/znver2/2021-01-29_16-16-24-502902/matmul.png)

### Results on Intel XEON Skylake (GCP C2 instance, AVX512)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/skylake-avx512/2021-01-26_01-12-27/matmul.png)

### Results on Intel XEON E-2276M Coffee lake (Thinkpad P53, AVX2)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/haswell/2021-01-26_16-42-20/matmul.png)

### Results on Apple M1 (NEON - no AMX2)
Note: 8GB Mac Mini runs roughly 25% slower than the 16GB version on other tests.
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/apple-a13/2021-01-26_15-39-08/matmul.png)

### Results on Apple M1 (RUY/MLIR using NEON - Accelerate with AMX2)
Note 0: 8GB Mac Mini runs roughly 25% slower than the 16GB version on other tests.
Note 1: Set veclib_maximum_threads=1 but there is no way to verify it is honored by Accelerate. 
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/apple-a13/2021-01-26_18-33-13/matmul.png)

### Code
For more details see [mmperf on Github](https://github.com/mmperf/mmperf/).

### Support or Contact

mmperf aims to be a collaborative effort though primarily developed by [nod.ai](https://nod.ai) so if you can get better performance or add a new backend please submit a PR. 
