---
name: qiskit
description: IBM quantum computing framework。在面向 IBM Quantum hardware、使用 Qiskit Runtime 处理 production workloads，或需要 IBM optimization tools 时使用。最适合 IBM hardware execution、quantum error mitigation 和 enterprise quantum computing。Google hardware 使用 cirq；gradient-based quantum ML 使用 pennylane；open quantum system simulations 使用 qutip。
license: Apache-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# Qiskit

## 概述

Qiskit 是全球最受欢迎的开源 quantum computing framework，下载量超过 13M。可用于构建 quantum circuits、针对 hardware 优化、在 simulator 或真实 quantum computer 上执行，并分析结果。支持 IBM Quantum（100+ qubit systems）、IonQ、Amazon Braket 和其他 providers。

**关键特性：**
- Transpilation 比竞品快 83 倍
- 优化后 circuit 中 two-qubit gates 减少 29%
- Backend-agnostic execution（local simulators 或 cloud hardware）
- 面向 optimization、chemistry 和 ML 的完整 algorithm libraries

## 快速开始

### 安装

```bash
uv pip install qiskit
uv pip install "qiskit[visualization]" matplotlib
```

### 第一个 Circuit

```python
from qiskit import QuantumCircuit
from qiskit.primitives import StatevectorSampler

# Create Bell state (entangled qubits)
qc = QuantumCircuit(2)
qc.h(0)           # Hadamard on qubit 0
qc.cx(0, 1)       # CNOT from qubit 0 to 1
qc.measure_all()  # Measure both qubits

# Run locally
sampler = StatevectorSampler()
result = sampler.run([qc], shots=1024).result()
counts = result[0].data.meas.get_counts()
print(counts)  # {'00': ~512, '11': ~512}
```

### Visualization

```python
from qiskit.visualization import plot_histogram

qc.draw('mpl')           # Circuit diagram
plot_histogram(counts)   # Results histogram
```

## 核心能力

### 1. Setup and Installation
关于详细安装、authentication 和 IBM Quantum account setup：
- **见 `references/setup.md`**

覆盖主题：
- 使用 uv 安装
- Python environment setup
- IBM Quantum account 和 API token configuration
- Local 与 cloud execution

### 2. Building Quantum Circuits
关于用 gates、measurements 和 composition 构建 quantum circuits：
- **见 `references/circuits.md`**

覆盖主题：
- 使用 QuantumCircuit 创建 circuits
- Single-qubit gates（H、X、Y、Z、rotations、phase gates）
- Multi-qubit gates（CNOT、SWAP、Toffoli）
- Measurements 和 barriers
- Circuit composition 和 properties
- 用于 variational algorithms 的 parameterized circuits

### 3. Primitives (Sampler and Estimator)
关于执行 quantum circuits 并计算结果：
- **见 `references/primitives.md`**

覆盖主题：
- **Sampler**：获取 bitstring measurements 和 probability distributions
- **Estimator**：计算 observables 的 expectation values
- V2 interface（StatevectorSampler、StatevectorEstimator）
- 用于 hardware 的 IBM Quantum Runtime primitives
- Sessions 和 Batch modes
- Parameter binding

### 4. Transpilation and Optimization
关于优化 circuits 并准备 hardware execution：
- **见 `references/transpilation.md`**

覆盖主题：
- 为什么 transpilation 是必要的
- Optimization levels（0-3）
- 六个 transpilation stages（init、layout、routing、translation、optimization、scheduling）
- 高级功能（virtual permutation elision、gate cancellation）
- 常见参数（initial_layout、approximation_degree、seed）
- efficient circuits 的 best practices

### 5. Visualization
关于展示 circuits、results 和 quantum states：
- **见 `references/visualization.md`**

覆盖主题：
- Circuit drawings（text、matplotlib、LaTeX）
- Result histograms
- Quantum state visualization（Bloch sphere、state city、QSphere）
- Backend topology 和 error maps
- Customization 和 styling
- 保存 publication-quality figures

### 6. Hardware Backends
关于在 simulators 和真实 quantum computers 上运行：
- **见 `references/backends.md`**

覆盖主题：
- IBM Quantum backends 和 authentication
- Backend properties 和 status
- 使用 Runtime primitives 在真实 hardware 上运行
- Job management 和 queuing
- Session mode（iterative algorithms）
- Batch mode（parallel jobs）
- Local simulators（StatevectorSampler、Aer）
- Third-party providers（IonQ、Amazon Braket）
- Error mitigation strategies

### 7. Qiskit Patterns Workflow
关于实现四步 quantum computing workflow：
- **见 `references/patterns.md`**

覆盖主题：
- **Map**：将问题转换为 quantum circuits
- **Optimize**：为 hardware transpile
- **Execute**：使用 primitives 运行
- **Post-process**：提取并分析结果
- 完整 VQE 示例
- Session 与 Batch execution
- 常见 workflow patterns

### 8. Quantum Algorithms and Applications
关于实现特定 quantum algorithms：
- **见 `references/algorithms.md`**

覆盖主题：
- **Optimization**：VQE、QAOA、Grover's algorithm
- **Chemistry**：Molecular ground states、excited states、Hamiltonians
- **Machine Learning**：Quantum kernels、VQC、QNN
- **Algorithm libraries**：Qiskit Nature、Qiskit ML、Qiskit Optimization
- Physics simulations 和 benchmarking

## Workflow Decision Guide

**如果你需要：**

- 安装 Qiskit 或设置 IBM Quantum account → `references/setup.md`
- 构建新的 quantum circuit → `references/circuits.md`
- 理解 gates 和 circuit operations → `references/circuits.md`
- 运行 circuits 并获取 measurements → `references/primitives.md`
- 计算 expectation values → `references/primitives.md`
- 为 hardware 优化 circuits → `references/transpilation.md`
- 可视化 circuits 或 results → `references/visualization.md`
- 在 IBM Quantum hardware 上执行 → `references/backends.md`
- 连接 third-party providers → `references/backends.md`
- 实现端到端 quantum workflow → `references/patterns.md`
- 构建特定 algorithm（VQE、QAOA 等）→ `references/algorithms.md`
- 解决 chemistry 或 optimization problems → `references/algorithms.md`

## Best Practices

### Development Workflow

1. **从 simulators 开始**：使用 hardware 前先在本地测试
   ```python
   from qiskit.primitives import StatevectorSampler
   sampler = StatevectorSampler()
   ```

2. **始终 transpile**：执行前优化 circuits
   ```python
   from qiskit import transpile
   qc_optimized = transpile(qc, backend=backend, optimization_level=3)
   ```

3. **使用合适的 primitives**：
   - Sampler 用于 bitstrings（optimization algorithms）
   - Estimator 用于 expectation values（chemistry、physics）

4. **选择 execution mode**：
   - Session：Iterative algorithms（VQE、QAOA）
   - Batch：独立 parallel jobs
   - Single job：一次性 experiments

### Performance Optimization

- production 使用 optimization_level=3
- 尽量减少 two-qubit gates（主要 error source）
- 使用 hardware 前先用 noisy simulators 测试
- 保存并复用 transpiled circuits
- 在 variational algorithms 中监控 convergence

### Hardware Execution

- 提交前检查 backend status
- 测试时使用 least_busy()
- 保存 job IDs 以便之后检索
- 应用 error mitigation（resilience_level）
- 从较少 shots 开始，final runs 时增加

## Common Patterns

### Pattern 1: Simple Circuit Execution

```python
from qiskit import QuantumCircuit, transpile
from qiskit.primitives import StatevectorSampler

qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
qc.measure_all()

sampler = StatevectorSampler()
result = sampler.run([qc], shots=1024).result()
counts = result[0].data.meas.get_counts()
```

### Pattern 2: Hardware Execution with Transpilation

```python
from qiskit_ibm_runtime import QiskitRuntimeService, SamplerV2 as Sampler
from qiskit import transpile

service = QiskitRuntimeService()
backend = service.backend("ibm_brisbane")

qc_optimized = transpile(qc, backend=backend, optimization_level=3)

sampler = Sampler(backend)
job = sampler.run([qc_optimized], shots=1024)
result = job.result()
```

### Pattern 3: Variational Algorithm (VQE)

```python
from qiskit_ibm_runtime import Session, EstimatorV2 as Estimator
from scipy.optimize import minimize

with Session(backend=backend) as session:
    estimator = Estimator(session=session)

    def cost_function(params):
        bound_qc = ansatz.assign_parameters(params)
        qc_isa = transpile(bound_qc, backend=backend)
        result = estimator.run([(qc_isa, hamiltonian)]).result()
        return result[0].data.evs

    result = minimize(cost_function, initial_params, method='COBYLA')
```

## 其他资源

- **Official Docs**：https://quantum.ibm.com/docs
- **Qiskit Textbook**：https://qiskit.org/learn
- **API Reference**：https://docs.quantum.ibm.com/api/qiskit
- **Patterns Guide**：https://quantum.cloud.ibm.com/docs/en/guides/intro-to-patterns
