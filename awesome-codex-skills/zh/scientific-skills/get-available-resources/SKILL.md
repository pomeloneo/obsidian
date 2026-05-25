---
name: get-available-resources
description: 在任何 computationally intensive scientific task 开始时，应使用此 skill 检测并报告可用 system resources（CPU cores、GPUs、memory、disk space）。它会创建包含 resource information 和 strategic recommendations 的 JSON 文件，用于指导 computational approach decisions，例如是否使用 parallel processing（joblib、multiprocessing）、out-of-core computing（Dask、Zarr）、GPU acceleration（PyTorch、JAX），或 memory-efficient strategies。在运行 analyses、training models、processing large datasets，或任何 resource constraints 重要的任务前使用此 skill。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Get Available Resources

## 概述

检测可用 computational resources，并为 scientific computing tasks 生成 strategic recommendations。此 skill 会自动识别 CPU capabilities、GPU availability（NVIDIA CUDA、AMD ROCm、Apple Silicon Metal）、memory constraints 和 disk space，帮助对 computational approaches 做出知情决策。

## 何时使用此 Skill

在任何 computationally intensive task 前主动使用此 skill：

- **数据分析前**：判断 datasets 是否可加载到内存，或需要 out-of-core processing
- **模型训练前**：检查 GPU acceleration 是否可用以及应使用哪个 backend
- **并行处理前**：为 joblib、multiprocessing 或 Dask 识别最佳 worker 数量
- **大型文件操作前**：验证 disk space 是否充足，并选择合适 storage strategies
- **项目初始化时**：理解 baseline capabilities，用于做 architecture decisions

**示例场景：**
- "Help me analyze this 50GB genomics dataset" → 先使用此 skill 判断是否需要 Dask/Zarr
- "Train a neural network on this data" → 使用此 skill 检测可用 GPUs 和 backends
- "Process 10,000 files in parallel" → 使用此 skill 判断最佳 worker count
- "Run a computationally intensive simulation" → 使用此 skill 理解 resource constraints

## 此 Skill 如何工作

### Resource Detection

此 skill 运行 `scripts/detect_resources.py` 自动检测：

1. **CPU Information**
   - Physical 和 logical core counts
   - Processor architecture 和 model
   - CPU frequency information

2. **GPU Information**
   - NVIDIA GPUs：通过 nvidia-smi 检测，报告 VRAM、driver version、compute capability
   - AMD GPUs：通过 rocm-smi 检测
   - Apple Silicon：检测带 Metal support 和 unified memory 的 M1/M2/M3/M4 chips

3. **Memory Information**
   - Total 和 available RAM
   - 当前 memory usage percentage
   - Swap space availability

4. **Disk Space Information**
   - Working directory 的 total 和 available disk space
   - 当前 usage percentage

5. **Operating System Information**
   - OS type（macOS、Linux、Windows）
   - OS version 和 release
   - Python version

### Output Format

此 skill 会在当前 working directory 中生成 `.claude_resources.json` 文件，内容如下：

```json
{
  "timestamp": "2025-10-23T10:30:00",
  "os": {
    "system": "Darwin",
    "release": "25.0.0",
    "machine": "arm64"
  },
  "cpu": {
    "physical_cores": 8,
    "logical_cores": 8,
    "architecture": "arm64"
  },
  "memory": {
    "total_gb": 16.0,
    "available_gb": 8.5,
    "percent_used": 46.9
  },
  "disk": {
    "total_gb": 500.0,
    "available_gb": 200.0,
    "percent_used": 60.0
  },
  "gpu": {
    "nvidia_gpus": [],
    "amd_gpus": [],
    "apple_silicon": {
      "name": "Apple M2",
      "type": "Apple Silicon",
      "backend": "Metal",
      "unified_memory": true
    },
    "total_gpus": 1,
    "available_backends": ["Metal"]
  },
  "recommendations": {
    "parallel_processing": {
      "strategy": "high_parallelism",
      "suggested_workers": 6,
      "libraries": ["joblib", "multiprocessing", "dask"]
    },
    "memory_strategy": {
      "strategy": "moderate_memory",
      "libraries": ["dask", "zarr"],
      "note": "Consider chunking for datasets > 2GB"
    },
    "gpu_acceleration": {
      "available": true,
      "backends": ["Metal"],
      "suggested_libraries": ["pytorch-mps", "tensorflow-metal", "jax-metal"]
    },
    "large_data_handling": {
      "strategy": "disk_abundant",
      "note": "Sufficient space for large intermediate files"
    }
  }
}
```

### Strategic Recommendations

此 skill 会生成 context-aware recommendations：

**Parallel Processing Recommendations：**
- **High parallelism（8+ cores）**：使用 Dask、joblib 或 multiprocessing，workers = cores - 2
- **Moderate parallelism（4-7 cores）**：使用 joblib 或 multiprocessing，workers = cores - 1
- **Sequential（< 4 cores）**：优先 sequential processing，避免 overhead

**Memory Strategy Recommendations：**
- **Memory constrained（< 4GB available）**：使用 Zarr、Dask 或 H5py 进行 out-of-core processing
- **Moderate memory（4-16GB available）**：datasets > 2GB 时使用 Dask/Zarr
- **Memory abundant（> 16GB available）**：大多数 datasets 可直接加载到 memory

**GPU Acceleration Recommendations：**
- **检测到 NVIDIA GPUs**：使用 PyTorch、TensorFlow、JAX、CuPy 或 RAPIDS
- **检测到 AMD GPUs**：使用 PyTorch-ROCm 或 TensorFlow-ROCm
- **检测到 Apple Silicon**：使用带 MPS backend 的 PyTorch、TensorFlow-Metal 或 JAX-Metal
- **未检测到 GPU**：使用 CPU-optimized libraries

**Large Data Handling Recommendations：**
- **Disk constrained（< 10GB）**：使用 streaming 或 compression strategies
- **Moderate disk（10-100GB）**：使用 Zarr、H5py 或 Parquet formats
- **Disk abundant（> 100GB）**：可以自由创建大型 intermediate files

## 使用说明

### Step 1：运行 Resource Detection

在任何 computationally intensive task 开始时执行检测脚本：

```bash
python scripts/detect_resources.py
```

可选参数：
- `-o, --output <path>`：指定自定义 output path（默认：`.claude_resources.json`）
- `-v, --verbose`：向 stdout 打印完整 resource information

### Step 2：读取并应用 Recommendations

运行检测后，读取生成的 `.claude_resources.json` 文件以指导 computational decisions：

```python
# Example: Use recommendations in code
import json

with open('.claude_resources.json', 'r') as f:
    resources = json.load(f)

# Check parallel processing strategy
if resources['recommendations']['parallel_processing']['strategy'] == 'high_parallelism':
    n_jobs = resources['recommendations']['parallel_processing']['suggested_workers']
    # Use joblib, Dask, or multiprocessing with n_jobs workers

# Check memory strategy
if resources['recommendations']['memory_strategy']['strategy'] == 'memory_constrained':
    # Use Dask, Zarr, or H5py for out-of-core processing
    import dask.array as da
    # Load data in chunks

# Check GPU availability
if resources['recommendations']['gpu_acceleration']['available']:
    backends = resources['recommendations']['gpu_acceleration']['backends']
    # Use appropriate GPU library based on available backend
```

### Step 3：做出知情决策

使用 resource information 和 recommendations 做出 strategic choices：

**For data loading：**
```python
memory_available_gb = resources['memory']['available_gb']
dataset_size_gb = 10

if dataset_size_gb > memory_available_gb * 0.5:
    # Dataset is large relative to memory, use Dask
    import dask.dataframe as dd
    df = dd.read_csv('large_file.csv')
else:
    # Dataset fits in memory, use pandas
    import pandas as pd
    df = pd.read_csv('large_file.csv')
```

**For parallel processing：**
```python
from joblib import Parallel, delayed

n_jobs = resources['recommendations']['parallel_processing'].get('suggested_workers', 1)

results = Parallel(n_jobs=n_jobs)(
    delayed(process_function)(item) for item in data
)
```

**For GPU acceleration：**
```python
import torch

if 'CUDA' in resources['gpu']['available_backends']:
    device = torch.device('cuda')
elif 'Metal' in resources['gpu']['available_backends']:
    device = torch.device('mps')
else:
    device = torch.device('cpu')

model = model.to(device)
```

## Dependencies

检测脚本需要以下 Python packages：

```bash
uv pip install psutil
```

所有其他功能使用 Python standard library modules（json、os、platform、subprocess、sys、pathlib）。

## Platform Support

- **macOS**：完整支持，包括 Apple Silicon（M1/M2/M3/M4）GPU detection
- **Linux**：完整支持，包括 NVIDIA（nvidia-smi）和 AMD（rocm-smi）GPU detection
- **Windows**：完整支持，包括 NVIDIA GPU detection

## 最佳实践

1. **尽早运行**：在项目开始或主要 computational tasks 前执行 resource detection
2. **定期重跑**：System resources 会随时间变化（memory usage、disk space）
3. **扩展前检查**：扩大 parallel workers 或 data sizes 前验证 resources
4. **记录决策**：将 `.claude_resources.json` 文件保留在 project directories 中，以记录 resource-aware decisions
5. **配合 versioning 使用**：不同机器能力不同；resource files 有助于保持 portability

## 故障排除

**GPU not detected：**
- 确保 GPU drivers 已安装（nvidia-smi、rocm-smi，或 Apple Silicon 的 system_profiler）
- 检查 GPU utilities 是否在 system PATH 中
- 验证 GPU 未被其他 processes 占用

**Script execution fails：**
- 确保 psutil 已安装：`uv pip install psutil`
- 检查 Python version compatibility（Python 3.6+）
- 验证脚本有 execute permissions：`chmod +x scripts/detect_resources.py`

**Inaccurate memory readings：**
- Memory readings 是 snapshots；实际 available memory 会持续变化
- 为获得准确 “available” memory，检测前关闭其他 applications
- 考虑运行多次检测并取平均值
