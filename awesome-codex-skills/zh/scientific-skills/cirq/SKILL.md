---
name: cirq
description: Google 量子计算框架。在针对 Google Quantum AI 硬件、设计噪声感知电路或运行量子表征实验时使用。最适合 Google 硬件、噪声建模和低级电路设计。对于IBM硬件使用qiskit；对于具有自动微分功能的量子ML，请使用 pennylane；对于物理模拟，请使用 qutip。
license: Apache-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# Cirq - 使用 Python 进行 Quantum 计算

Cirq 是 Google Quantum AI 的开源框架，用于在量子计算机和模拟器上设计、模拟和运行量子电路。

## 安装

```bash
uv pip install cirq
```

对于硬件集成：
```bash
# Google Quantum Engine
uv pip install cirq-google

# IonQ
uv pip install cirq-ionq

# AQT (Alpine Quantum Technologies)
uv pip install cirq-aqt

# Pasqal
uv pip install cirq-pasqal

# Azure Quantum
uv pip install azure-quantum cirq
```

## 快速入门

### 基础Circuit

```python
import cirq
import numpy as np

# Create qubits
q0, q1 = cirq.LineQubit.range(2)

# Build circuit
circuit = cirq.Circuit(
    cirq.H(q0),              # Hadamard on q0
    cirq.CNOT(q0, q1),       # CNOT with q0 control, q1 target
    cirq.measure(q0, q1, key='result')
)

print(circuit)

# Simulate
simulator = cirq.Simulator()
result = simulator.run(circuit, repetitions=1000)

# Display results
print(result.histogram(key='result'))
```

### 参数化Circuit

```python
import sympy

# Define symbolic parameter
theta = sympy.Symbol('theta')

# Create parameterized circuit
circuit = cirq.Circuit(
    cirq.ry(theta)(q0),
    cirq.measure(q0, key='m')
)

# Sweep over parameter values
sweep = cirq.Linspace('theta', start=0, stop=2*np.pi, length=20)
results = simulator.run_sweep(circuit, params=sweep, repetitions=1000)

# Process results
for params, result in zip(sweep, results):
    theta_val = params['theta']
    counts = result.histogram(key='m')
    print(f"θ={theta_val:.2f}: {counts}")
```

## 核心能力

### Circuit 大楼
有关构建量子电路的全面信息，包括量子位、gates、操作、自定义gates和电路模式，请参阅：
- **[参考文献/building.md](references/building.md)** - 电路构造完整指南

常见话题：
- Qubit 类型（GridQubit、LineQubit、NamedQubit）
- 单量子位和两个量子位gates
- 参数化gates和操作
- 自定义gate分解
- Circuit 组织与时刻
- 标准电路模式（贝尔状态，GHZ，QFT）
- Import/export (OpenQASM, JSON)
- 使用 qudits 和 observables

### 模拟
有关模拟量子电路的详细信息，包括精确模拟、噪声模拟、参数扫描和Quantum虚拟机，请参阅：
- **[参考文献/simulation.md](references/simulation.md)** - 量子模拟完整指南

常见话题：
- 精确模拟（状态向量，密度矩阵）
- 采样和测量
- 参数扫描（单个和多个参数）
- 噪声模拟
- 状态直方图和可视化
- Quantum 虚拟机 (QVM)
- 期望值和可观察值
- 性能优化

### Circuit 转型
有关优化、编译和操作量子电路的信息，请参阅：
- **[参考文献/transformation.md](references/transformation.md)** - 电路转换完整指南

常见话题：
- 变压器框架
- 门分解
- Circuit优化（合并gates，弹出Zgates，删除可忽略的操作）
- Circuit 硬件编译
- Qubit 路由和 SWAP 插入
- 定制变压器
- 转型管道

### 硬件集成
有关在不同提供商的真实量子硬件上运行电路的信息，请参阅：
- **[references/hardware.md](references/hardware.md)** - 硬件集成完整指南

支持的提供商：
- **Google Quantum AI** (cirq-google) - Sycamore、Weber 处理器
- **IonQ** (cirq-ionq) - 俘获离子量子计算机
- **Azure Quantum** (azure-quantum) - IonQ 和 Honeywell 后端
- **AQT** (cirq-aqt) - Alpine Quantum 技术
- **Pasqal** (cirq-pasqal) - 中性原子量子计算机

主题包括设备表示、量子位选择、身份验证、作业管理和硬件电路优化。

### 噪声建模
有关噪声建模、噪声仿真、表征和错误缓解的信息，请参阅：
- **[references/noise.md](references/noise.md)** - 噪声建模完整指南

常见话题：
- 噪声通道（去极化、幅度阻尼、相位阻尼）
- 噪声模型（常数、门特定、量子位特定、热）
- 向电路添加噪声
- 读出噪声
- 噪声特征（随机基准测试，XEB）
- 噪声可视化（热图）
- 错误缓解技术

### Quantum 实验
有关设计实验、参数扫描、数据收集和使用 ReCirq 框架的信息，请参阅：
- **[references/experiments.md](references/experiments.md)** - 量子实验完整指南

常见话题：
- 实验设计模式
- 参数扫描和数据收集
- ReCirq 框架结构
- 常用算法（VQE、QAOA、QPE）
- 数据分析与可视化
- 统计分析和保真度估计
- 并行数据采集

## 常见模式

### 变分算法模板

```python
import scipy.optimize

def variational_algorithm(ansatz, cost_function, initial_params):
    """Template for variational quantum algorithms."""

    def objective(params):
        circuit = ansatz(params)
        simulator = cirq.Simulator()
        result = simulator.simulate(circuit)
        return cost_function(result)

    # Optimize
    result = scipy.optimize.minimize(
        objective,
        initial_params,
        method='COBYLA'
    )

    return result

# Define ansatz
def my_ansatz(params):
    q = cirq.LineQubit(0)
    return cirq.Circuit(
        cirq.ry(params[0])(q),
        cirq.rz(params[1])(q)
    )

# Define cost function
def my_cost(result):
    state = result.final_state_vector
    # Calculate cost based on state
    return np.real(state[0])

# Run optimization
result = variational_algorithm(my_ansatz, my_cost, [0.0, 0.0])
```

### 硬件执行模板

```python
def run_on_hardware(circuit, provider='google', device_name='weber', repetitions=1000):
    """Template for running on quantum hardware."""

    if provider == 'google':
        import cirq_google
        engine = cirq_google.get_engine()
        processor = engine.get_processor(device_name)
        job = processor.run(circuit, repetitions=repetitions)
        return job.results()[0]

    elif provider == 'ionq':
        import cirq_ionq
        service = cirq_ionq.Service()
        result = service.run(circuit, repetitions=repetitions, target='qpu')
        return result

    elif provider == 'azure':
        from azure.quantum.cirq import AzureQuantumService
        # Setup workspace...
        service = AzureQuantumService(workspace)
        result = service.run(circuit, repetitions=repetitions, target='ionq.qpu')
        return result

    else:
        raise ValueError(f"Unknown provider: {provider}")
```

### 噪声研究模板

```python
def noise_comparison_study(circuit, noise_levels):
    """Compare circuit performance at different noise levels."""

    results = {}

    for noise_level in noise_levels:
        # Create noisy circuit
        noisy_circuit = circuit.with_noise(cirq.depolarize(p=noise_level))

        # Simulate
        simulator = cirq.DensityMatrixSimulator()
        result = simulator.run(noisy_circuit, repetitions=1000)

        # Analyze
        results[noise_level] = {
            'histogram': result.histogram(key='result'),
            'dominant_state': max(
                result.histogram(key='result').items(),
                key=lambda x: x[1]
            )
        }

    return results

# Run study
noise_levels = [0.0, 0.001, 0.01, 0.05, 0.1]
results = noise_comparison_study(circuit, noise_levels)
```

## 最佳实践

1. **Circuit 设计**
   - 为您的拓扑使用适当的量子位类型
   - 保持电路模块化和可重用
   - 用描述性键标记测量值
   - 在执行前根据器件约束验证电路

2. **模拟**
   - 对纯状态使用状态向量模拟（更高效）
   - 仅在需要时使用密度矩阵模拟（混合状态、噪声）
   - 利用参数扫描而不是单独运行
   - 监控大型系统的内存使用情况（2^n 快速增长）

3. **硬件执行**
   - 始终首先在模拟器上进行测试
   - 使用校准数据选择最佳量子位
   - 针对目标硬件门组优化电路
   - 为生产运行实施错误缓解
   - 立即存储昂贵的硬件结果

4. **Circuit优化**
   - 从高级内置变压器开始
   - 按顺序链接多个优化
   - 轨道深度和 gate 计数减少
   - 验证转换后的正确性

5. **噪声建模**
   - 使用来自校准数据的真实噪声模型
   - 包括所有误差源（gate、退相干、读数）
   - 缓解前表征
   - 保持电路较浅以尽量减少噪声积累

6. **实验**
   - 清晰分离的结构实验（数据生成、收集、分析）
   - 使用 ReCirq 模式来实现可重复性
   - 经常保存中间结果
   - 并行化独立任务
   - 使用元数据彻底记录

## 其他资源

- **官方文档**：https://quantumai.google/cirq
- **API参考**：https://quantumai.google/reference/python/cirq
- **教程**：https://quantumai.google/cirq/tutorials
- **示例**：https://github.com/quantumlib/Cirq/tree/master/examples
- **ReCirq**: https://github.com/quantumlib/ReCirq

## 常见问题

**Circuit 对于硬件来说太深了**：
- 使用电路优化变压器来减少深度
- 参见`transformation.md`了解优化技术

**模拟内存问题**：
- 从密度矩阵切换到状态向量模拟器
- 减少量子位数量或为 Clifford 电路使用稳定器模拟器

**设备验证错误**：
- 使用 device.metadata.nx_graph 检查量子位连接
- 将gates分解为设备原生门集
- 请参阅 `hardware.md` 以了解特定于设备的编译

**嘈杂的模拟太慢**：
- 密度矩阵模拟是 O(2^2n) - 考虑减少量子位
- 仅在关键操作上有选择地使用噪声模型
- 请参阅`simulation.md`了解性能优化
