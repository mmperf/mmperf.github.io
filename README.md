## Welcome to mmperf

mmperf is a single core GEMM benchmark. This repository aims to benchmark Matrix Multiply (SGEMM) hand-tuned libraries and code generation stacks on a single thread on one CPU core. The focus will be on machine learning workloads so FP32 or smaller and irregular sizes of matrices. The goal is to expose high performance atomic kernels that can then be used to build highly efficient higher level implemenations spanning multiple cores or distributed across systems when efficient atomic kernels are asynchrously scheduled with overlapping communicaitons (interchip, in a system or across a system).

# Hand Engineered Libraries:

- Intel MKL
- OpenBLAS
- RUY
- Accelerate
- (TODO) OpenBLIS
- (TODO) ATLAS

# Compiler / Codegen kernels

- MLIR
- Halide
- (TODO) TVM 

### Results


### Sample results on Intel XEON Skylake (GCP C2 instance, AVX512)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/skylake-avx512/2021-01-26_01-12-27/matmul.png)

### Sample results on AMD Threadripper 3990x (ZenV2, AVX2)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/znver2/2021-01-25_13-24-25/matmul.png)


### Code
For more details see [mmperf on Github](https://github.com/mmperf/mmperf/).

### Support or Contact

mmperf aims to be a collaborative effort though primarily developed by [nod.ai](https://nod.ai) so if you can get better performance or add a new backend please submit a PR. 
