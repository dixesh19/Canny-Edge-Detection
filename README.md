# CUDA Multi CPU Comparison Assignment

## Student Information

| Field | Details |
|------|------|
| Name | Dinesh |
| Register Number | 212224240037 |
| Course | Parallel Computing / CUDA Programming |
| Technology | CUDA C++ |

---

# Objective

The objective of this assignment is to implement a CUDA-based GPU program that compares two floating-point vectors received from two CPU-based Python programs.

For every element:

- If `a[i] > b[i]` → output `1.0`
- If `a[i] == b[i]` → output `0.0`
- If `a[i] < b[i]` → output `-1.0`

The CUDA kernel performs parallel comparison of vector elements and stores the result into output CSV files.

---

# Software Requirements

- NVIDIA CUDA Toolkit
- GCC Compiler
- Linux Environment
- Python 3
- CUDA-enabled GPU

---

# Files Used

| File Name | Purpose |
|------|------|
| input_a.csv | Input vector A |
| input_b.csv | Input vector B |
| output_a.csv | CUDA comparison output |
| output_b.csv | CUDA comparison output |
| results.csv | Submission file |
| multi_cpu.cu | CUDA source code |

---

# CUDA Kernel Logic

The CUDA kernel compares vector elements using branchless comparison:

```cpp
c[i] = (a[i] > b[i]) - (a[i] < b[i]);
