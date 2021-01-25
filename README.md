## Welcome to mmperf

mmperf is a single core GEMM benchmark. This repository aims to benchmark Matrix Multiply (SGEMM) hand-tuned libraries and code generation stacks on a single thread on one CPU core. The focus will be on machine learning workloads so FP32 or smaller and irregular sizes of matrices. The goal is to expose high performance atomic kernels that can then be used to build highly efficient higher level implemenations spanning multiple cores or distributed across systems when efficient atomic kernels are asynchrously scheduled with overlapping communicaitons (interchip, in a system or across a system).

# Hand Optimized kernels:

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

### Sample results on Intel(R) Xeon(R) E-2276M Coffeelake (Thinkpad P53)
![Results](https://github.com/mmperf/mmperf/blob/main/official_results/haswell/2021-01-24_15-25-42/matmul.png)


### Code
For more details see [mmperf on Github](https://github.com/mmperf/mmperf/).

### Support or Contact

mmperf aims to be a collaborative effort though primarily developed by [nod.ai](https://nod.ai) so if you notice a way to configure the libraries to get better performance please submit a PR. 
