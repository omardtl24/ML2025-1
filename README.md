# ML2025-1

This repository contains the solutions to various practical exercises from the **Machine Learning post-graduate course** at the **National University of Colombia**.

## 📚 Course Topics

### 1. Introduction to Machine Learning  
- 1.1 History of Machine Learning  
- 1.2 The Learning Problem  
- 1.3 Design and Analysis of ML Experiments  

### 2. Probabilistic Models  
- 2.1 Bayesian Decision Theory  
- 2.2 Parametric Estimation  
- 2.3 Non-Parametric Estimation  

### 3. Instance-Based Learning  
- 3.1 K-Nearest Neighbors  
- 3.2 Kernel Methods  
- 3.3 Support Vector Machines  

### 4. Function Approximation and Neural Networks  
- 4.1 Neural Networks  
- 4.2 Differentiable Programming  
- 4.3 Deep Learning  

### 5. Generative Models  
- 5.1 Variational Inference  
- 5.2 Diffusion Models  
- 5.3 Large Language Models  

### 6. Kernel Density Matrices  
- 6.1 Density Matrices  
- 6.2 KDM for Density Estimation  
- 6.3 KDM for Classification and Regression  
- 6.4 KDM for Generative Modeling

# Environment Configuration

This project uses a `.env` file to configure CUDA, cuDNN, and TensorFlow settings for reproducible and flexible GPU usage.

## How it works

- The code loads environment variables from `.env` using `python-dotenv`.
- These variables control:
  - **CUDA toolkit and library paths** (for custom installations)
  - **TensorFlow and CUDA logging levels** (to reduce console noise)
  - **Which GPUs are visible to TensorFlow** (via `CUDA_VISIBLE_DEVICES`)
  - **Optional version info** for documentation/debugging

## Setting up your `.env`

1. **Copy the example file:**
   ```sh
   cp .env.example .env
   ```
2. **Edit `.env`** to match your system’s CUDA/cuDNN installation and desired GPU configuration.

## Variable explanations

| Variable                | Purpose                                                                 | Example Value                  |
|-------------------------|-------------------------------------------------------------------------|-------------------------------|
| `CUDA_HOME`             | Path to CUDA toolkit installation                                       | `/usr/local/cuda-12.9`        |
| `CUSTOM_CUDA_PATH`      | Path to CUDA binaries (for PATH)                                        | `/usr/local/cuda-12.9/bin`    |
| `CUSTOM_CUDA_LIB_PATH`  | Path to CUDA/cuDNN libraries (for LD_LIBRARY_PATH)                      | `/usr/local/cuda-12.9/lib64`  |
| `CUDA_VERSION`          | (Optional) CUDA version (for info)                                      | `12.5.1`                      |
| `CUDNN_VERSION`         | (Optional) cuDNN version (for info)                                     | `9`                           |
| `TF_CPP_MIN_LOG_LEVEL`  | TensorFlow log level (0=all, 3=errors only)                             | `3`                           |
| `CUDA_LOG_LEVEL`        | CUDA log level (0=all, 1=errors, etc.)                                  | `1`                           |
| `CUDA_DEVICE_LOG_LEVEL` | CUDA device log level                                                   | `1`                           |
| `NVIDIA_LOG_LEVEL`      | cuDNN log level (optional)                                              | `ERROR`                       |
| `CUDA_VISIBLE_DEVICES`  | Which GPUs TensorFlow can see (e.g., `0`, `0,1`, `-1` for CPU only)     | `0`                           |
| `ABSL_LOG_LEVEL`        | absl logging level for TensorFlow (optional)                            | `3`                           |

## Notes

- If you leave `CUDA_VISIBLE_DEVICES` empty or unset, TensorFlow will use all available GPUs.
- Adjust paths and versions to match your system.
- The `.env` file is **not committed** to version control; use `.env.example` as a template.

---
