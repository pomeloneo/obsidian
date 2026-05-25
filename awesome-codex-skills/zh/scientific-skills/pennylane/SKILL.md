---
name: pennylane
description: 硬件无关的 quantum ML framework，支持 automatic differentiation。当通过 gradients 训练 quantum circuits、构建 hybrid quantum-classical models，或需要在 IBM/Google/Rigetti/IonQ 之间进行 device portability 时使用。最适合 variational algorithms（VQE、QAOA）、quantum neural networks，以及与 PyTorch/JAX/TensorFlow 集成。hardware-specific optimizations 请用 qiskit（IBM）或 cirq（Google）；open quantum systems 请用 qutip。
license: Apache-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# PennyLane

## 概览

PennyLane 是一个 quantum computing library，可像训练 neural networks 一样训练 quantum computers。它提供 quantum circuits 的 automatic differentiation、device-independent programming，以及与 classical machine learning frameworks 的无缝集成。

## 安装

使用 uv 安装：

```bash
uv pip install pennylane
```

如需访问 quantum hardware，安装 device plugins：

```bash
# IBM Quantum
uv pip install pennylane-qiskit

# Amazon Braket
uv pip install amazon-braket-pennylane-plugin

# Google Cirq
uv pip install pennylane-cirq

# Rigetti Forest
uv pip install pennylane-rigetti

# IonQ
uv pip install pennylane-ionq
```

## 快速开始

构建 quantum circuit 并优化其 parameters：

```python
import pennylane as qml
from pennylane import numpy as np

# Create device
dev = qml.device('default.qubit', wires=2)

# Define quantum circuit
@qml.qnode(dev)
def circuit(params):
    qml.RX(params[0], wires=0)
    qml.RY(params[1], wires=1)
    qml.CNOT(wires=[0, 1])
    return qml.expval(qml.PauliZ(0))

# Optimize parameters
opt = qml.GradientDescentOptimizer(stepsize=0.1)
params = np.array([0.1, 0.2], requires_grad=True)

for i in range(100):
    params = opt.step(circuit, params)
```

## 核心能力

### 1. Quantum Circuit Construction

使用 gates、measurements 和 state preparation 构建 circuits。参见 `references/quantum_circuits.md`，了解：
- Single and multi-qubit gates
- Controlled operations 和 conditional logic
- Mid-circuit measurements 和 adaptive circuits
- 各类 measurement types（expectation、probability、samples）
- Circuit inspection 和 debugging

### 2. Quantum Machine Learning

创建 hybrid quantum-classical models。参见 `references/quantum_ml.md`，了解：
- 与 PyTorch、JAX、TensorFlow 的集成
- Quantum neural networks 和 variational classifiers
- Data encoding strategies（angle、amplitude、basis、IQP）
- 使用 backpropagation 训练 hybrid models
- 使用 quantum circuits 进行 transfer learning

### 3. Quantum Chemistry

模拟 molecules 并计算 ground state energies。参见 `references/quantum_chemistry.md`，了解：
- Molecular Hamiltonian generation
- Variational Quantum Eigensolver（VQE）
- 用于 chemistry 的 UCCSD ansatz
- Geometry optimization 和 dissociation curves
- Molecular property calculations

### 4. Device Management

在 simulators 或 quantum hardware 上执行。参见 `references/devices_backends.md`，了解：
- Built-in simulators（default.qubit、lightning.qubit、default.mixed）
- Hardware plugins（IBM、Amazon Braket、Google、Rigetti、IonQ）
- Device selection 和 configuration
- Performance optimization 和 caching
- GPU acceleration 和 JIT compilation

### 5. Optimization

使用多种 optimizers 训练 quantum circuits。参见 `references/optimization.md`，了解：
- Built-in optimizers（Adam、gradient descent、momentum、RMSProp）
- Gradient computation methods（backprop、parameter-shift、adjoint）
- Variational algorithms（VQE、QAOA）
- Training strategies（learning rate schedules、mini-batches）
- 处理 barren plateaus 和 local minima

### 6. 高级功能

利用 templates、transforms 和 compilation。参见 `references/advanced_features.md`，了解：
- Circuit templates 和 layers
- Transforms 和 circuit optimization
- Pulse-level programming
- Catalyst JIT compilation
- Noise models 和 error mitigation
- Resource estimation

## 常见 Workflows

### 训练 Variational Classifier

```python
# 1. Define ansatz
@qml.qnode(dev)
def classifier(x, weights):
    # Encode data
    qml.AngleEmbedding(x, wires=range(4))

    # Variational layers
    qml.StronglyEntanglingLayers(weights, wires=range(4))

    return qml.expval(qml.PauliZ(0))

# 2. Train
opt = qml.AdamOptimizer(stepsize=0.01)
weights = np.random.random((3, 4, 3))  # 3 layers, 4 wires

for epoch in range(100):
    for x, y in zip(X_train, y_train):
        weights = opt.step(lambda w: (classifier(x, w) - y)**2, weights)
```

### 为 Molecular Ground State 运行 VQE

```python
from pennylane import qchem

# 1. Build Hamiltonian
symbols = ['H', 'H']
coords = np.array([0.0, 0.0, 0.0, 0.0, 0.0, 0.74])
H, n_qubits = qchem.molecular_hamiltonian(symbols, coords)

# 2. Define ansatz
@qml.qnode(dev)
def vqe_circuit(params):
    qml.BasisState(qchem.hf_state(2, n_qubits), wires=range(n_qubits))
    qml.UCCSD(params, wires=range(n_qubits))
    return qml.expval(H)

# 3. Optimize
opt = qml.AdamOptimizer(stepsize=0.1)
params = np.zeros(10, requires_grad=True)

for i in range(100):
    params, energy = opt.step_and_cost(vqe_circuit, params)
    print(f"Step {i}: Energy = {energy:.6f} Ha")
```

### 在 Devices 之间切换

```python
# Same circuit, different backends
circuit_def = lambda dev: qml.qnode(dev)(circuit_function)

# Test on simulator
dev_sim = qml.device('default.qubit', wires=4)
result_sim = circuit_def(dev_sim)(params)

# Run on quantum hardware
dev_hw = qml.device('qiskit.ibmq', wires=4, backend='ibmq_manila')
result_hw = circuit_def(dev_hw)(params)
```

## 详细文档

关于特定主题的全面说明，请查阅 reference files：

- **Getting started**：`references/getting_started.md` - Installation、basic concepts、first steps
- **Quantum circuits**：`references/quantum_circuits.md` - Gates、measurements、circuit patterns
- **Quantum ML**：`references/quantum_ml.md` - Hybrid models、framework integration、QNNs
- **Quantum chemistry**：`references/quantum_chemistry.md` - VQE、molecular Hamiltonians、chemistry workflows
- **Devices**：`references/devices_backends.md` - Simulators、hardware plugins、device configuration
- **Optimization**：`references/optimization.md` - Optimizers、gradients、variational algorithms
- **Advanced**：`references/advanced_features.md` - Templates、transforms、JIT compilation、noise

## Best Practices

1. **从 simulators 开始** - 部署到 hardware 前先在 `default.qubit` 上测试
2. **对 hardware 使用 parameter-shift** - Backpropagation 只适用于 simulators
3. **选择合适 encodings** - 让 data encoding 匹配问题结构
4. **谨慎初始化** - 使用小 random values 以避免 barren plateaus
5. **监控 gradients** - 检查 deep circuits 中的 vanishing gradients
6. **缓存 devices** - 复用 device objects 以减少 initialization overhead
7. **Profile circuits** - 使用 `qml.specs()` 分析 circuit complexity
8. **本地测试** - 提交到 hardware 前先在 simulators 上验证
9. **使用 templates** - 利用 built-in templates 处理常见 circuit patterns
10. **可行时编译** - 对 performance-critical code 使用 Catalyst JIT

## 资源

- Official documentation: https://docs.pennylane.ai
- Codebook（tutorials）: https://pennylane.ai/codebook
- QML demonstrations: https://pennylane.ai/qml/demonstrations
- Community forum: https://discuss.pennylane.ai
- GitHub: https://github.com/PennyLaneAI/pennylane
