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
- Nod.AI

## Results

###

### Results on Nvidia A100 (cublas vs SHARK)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/cuda_nodai7.png)

### Results on Intel Alderlake 12900k (AVX2)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/alderlake/2022-01-27_23-40-34-673036/matmul.png)

### Results on Intel XEON Skylake (iMAC PRO, AVX512)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/skylake-avx512/2021-01-31_19-11-51-528540/matmul.png)

### Results on Xeon Cascade Lake (GCP C2 instance, AVX 512)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/cascadelake/2021-01-31_15-47-19-968148/matmul.png)

### Results on Xeon Cascade Lake Codegen TVM, Halide, MLIR (GCP C2 instance, AVX 512)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/skylake-avx512/2021-02-03_21-27-25-624537/matmul.png)

### Results on AMD Ryzen 5950x (ZenV3, compared to AMD's BLIS and OpenBLAS for RESNET50 sizes)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/znver2/2021-01-29_16-16-24-502902/matmul.png)

### Results on Intel XEON E-2276M Coffee lake (Thinkpad P53, AVX2)
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/haswell/2021-02-03_14-06-35-488724/matmul.png)

### Results on Apple M1 (NEON - no AMX2)
Note: 8GB Mac Mini runs roughly 25% slower than the 16GB version on other tests.
![Results](https://github.com/mmperf/mmperf/raw/main/official_results/apple-a13/2021-01-26_15-39-08/matmul.png)

### Code
For more details see [mmperf on Github](https://github.com/mmperf/mmperf/).

### Support or Contact

mmperf aims to be a collaborative effort though primarily developed by [nod.ai](https://nod.ai) so if you can get better performance or add a new backend please submit a PR. 
