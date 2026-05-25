---
name: qutip
description: 用于 open quantum systems 的 quantum physics simulation library。在研究 master equations、Lindblad dynamics、decoherence、quantum optics 或 cavity QED 时使用。最适合 physics research、open system dynamics 和 educational simulations。不适用于 circuit-based quantum computing；quantum algorithms 和 hardware execution 请使用 qiskit、cirq 或 pennylane。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# QuTiP: Quantum Toolbox in Python

## 概述

QuTiP 提供用于模拟和分析 quantum mechanical systems 的完整工具。它可处理 closed（unitary）和 open（dissipative）quantum systems，并针对不同场景提供多个优化过的 solvers。

## 安装

```bash
uv pip install qutip
```

用于额外功能的可选包：

```bash
# Quantum information processing (circuits, gates)
uv pip install qutip-qip

# Quantum trajectory viewer
uv pip install qutip-qtrl
```

## 快速开始

```python
from qutip import *
import numpy as np
import matplotlib.pyplot as plt

# Create quantum state
psi = basis(2, 0)  # |0⟩ state

# Create operator
H = sigmaz()  # Hamiltonian

# Time evolution
tlist = np.linspace(0, 10, 100)
result = sesolve(H, psi, tlist, e_ops=[sigmaz()])

# Plot results
plt.plot(tlist, result.expect[0])
plt.xlabel('Time')
plt.ylabel('⟨σz⟩')
plt.show()
```

## 核心能力

### 1. Quantum Objects and States

创建并操作 quantum states 和 operators：

```python
# States
psi = basis(N, n)  # Fock state |n⟩
psi = coherent(N, alpha)  # Coherent state |α⟩
rho = thermal_dm(N, n_avg)  # Thermal density matrix

# Operators
a = destroy(N)  # Annihilation operator
H = num(N)  # Number operator
sx, sy, sz = sigmax(), sigmay(), sigmaz()  # Pauli matrices

# Composite systems
psi_AB = tensor(psi_A, psi_B)  # Tensor product
```

**参见** `references/core_concepts.md`，了解 quantum objects、states、operators 和 tensor products 的完整说明。

### 2. Time Evolution and Dynamics

面向不同场景的多个 solvers：

```python
# Closed systems (unitary evolution)
result = sesolve(H, psi0, tlist, e_ops=[num(N)])

# Open systems (dissipation)
c_ops = [np.sqrt(0.1) * destroy(N)]  # Collapse operators
result = mesolve(H, psi0, tlist, c_ops, e_ops=[num(N)])

# Quantum trajectories (Monte Carlo)
result = mcsolve(H, psi0, tlist, c_ops, ntraj=500, e_ops=[num(N)])
```

**Solver 选择指南：**
- `sesolve`：Pure states、unitary evolution
- `mesolve`：Mixed states、dissipation、general open systems
- `mcsolve`：Quantum jumps、photon counting、individual trajectories
- `brmesolve`：Weak system-bath coupling
- `fmmesolve`：Time-periodic Hamiltonians（Floquet）

**参见** `references/time_evolution.md`，了解详细 solver 文档、time-dependent Hamiltonians 和 advanced options。

### 3. Analysis and Measurement

计算 physical quantities：

```python
# Expectation values
n_avg = expect(num(N), psi)

# Entropy measures
S = entropy_vn(rho)  # Von Neumann entropy
C = concurrence(rho)  # Entanglement (two qubits)

# Fidelity and distance
F = fidelity(psi1, psi2)
D = tracedist(rho1, rho2)

# Correlation functions
corr = correlation_2op_1t(H, rho0, taulist, c_ops, A, B)
w, S = spectrum_correlation_fft(taulist, corr)

# Steady states
rho_ss = steadystate(H, c_ops)
```

**参见** `references/analysis.md`，了解 entropy、fidelity、measurements、correlation functions 和 steady state calculations。

### 4. Visualization

可视化 quantum states 和 dynamics：

```python
# Bloch sphere
b = Bloch()
b.add_states(psi)
b.show()

# Wigner function (phase space)
xvec = np.linspace(-5, 5, 200)
W = wigner(psi, xvec, xvec)
plt.contourf(xvec, xvec, W, 100, cmap='RdBu')

# Fock distribution
plot_fock_distribution(psi)

# Matrix visualization
hinton(rho)  # Hinton diagram
matrix_histogram(H.full())  # 3D bars
```

**参见** `references/visualization.md`，了解 Bloch sphere animations、Wigner functions、Q-functions 和 matrix visualizations。

### 5. Advanced Methods

用于复杂场景的 specialized techniques：

```python
# Floquet theory (periodic Hamiltonians)
T = 2 * np.pi / w_drive
f_modes, f_energies = floquet_modes(H, T, args)
result = fmmesolve(H, psi0, tlist, c_ops, T=T, args=args)

# HEOM (non-Markovian, strong coupling)
from qutip.nonmarkov.heom import HEOMSolver, BosonicBath
bath = BosonicBath(Q, ck_real, vk_real)
hsolver = HEOMSolver(H_sys, [bath], max_depth=5)
result = hsolver.run(rho0, tlist)

# Permutational invariance (identical particles)
psi = dicke(N, j, m)  # Dicke states
Jz = jspin(N, 'z')  # Collective operators
```

**参见** `references/advanced.md`，了解 Floquet theory、HEOM、permutational invariance、stochastic solvers、superoperators 和 performance optimization。

## 常见 Workflow

### 模拟 Damped Harmonic Oscillator

```python
# System parameters
N = 20  # Hilbert space dimension
omega = 1.0  # Oscillator frequency
kappa = 0.1  # Decay rate

# Hamiltonian and collapse operators
H = omega * num(N)
c_ops = [np.sqrt(kappa) * destroy(N)]

# Initial state
psi0 = coherent(N, 3.0)

# Time evolution
tlist = np.linspace(0, 50, 200)
result = mesolve(H, psi0, tlist, c_ops, e_ops=[num(N)])

# Visualize
plt.plot(tlist, result.expect[0])
plt.xlabel('Time')
plt.ylabel('⟨n⟩')
plt.title('Photon Number Decay')
plt.show()
```

### Two-Qubit Entanglement Dynamics

```python
# Create Bell state
psi0 = bell_state('00')

# Local dephasing on each qubit
gamma = 0.1
c_ops = [
    np.sqrt(gamma) * tensor(sigmaz(), qeye(2)),
    np.sqrt(gamma) * tensor(qeye(2), sigmaz())
]

# Track entanglement
def compute_concurrence(t, psi):
    rho = ket2dm(psi) if psi.isket else psi
    return concurrence(rho)

tlist = np.linspace(0, 10, 100)
result = mesolve(qeye([2, 2]), psi0, tlist, c_ops)

# Compute concurrence for each state
C_t = [concurrence(state.proj()) for state in result.states]

plt.plot(tlist, C_t)
plt.xlabel('Time')
plt.ylabel('Concurrence')
plt.title('Entanglement Decay')
plt.show()
```

### Jaynes-Cummings Model

```python
# System parameters
N = 10  # Cavity Fock space
wc = 1.0  # Cavity frequency
wa = 1.0  # Atom frequency
g = 0.05  # Coupling strength

# Operators
a = tensor(destroy(N), qeye(2))  # Cavity
sm = tensor(qeye(N), sigmam())  # Atom

# Hamiltonian (RWA)
H = wc * a.dag() * a + wa * sm.dag() * sm + g * (a.dag() * sm + a * sm.dag())

# Initial state: cavity in coherent state, atom in ground state
psi0 = tensor(coherent(N, 2), basis(2, 0))

# Dissipation
kappa = 0.1  # Cavity decay
gamma = 0.05  # Atomic decay
c_ops = [np.sqrt(kappa) * a, np.sqrt(gamma) * sm]

# Observables
n_cav = a.dag() * a
n_atom = sm.dag() * sm

# Evolve
tlist = np.linspace(0, 50, 200)
result = mesolve(H, psi0, tlist, c_ops, e_ops=[n_cav, n_atom])

# Plot
fig, axes = plt.subplots(2, 1, figsize=(8, 6), sharex=True)
axes[0].plot(tlist, result.expect[0])
axes[0].set_ylabel('⟨n_cavity⟩')
axes[1].plot(tlist, result.expect[1])
axes[1].set_ylabel('⟨n_atom⟩')
axes[1].set_xlabel('Time')
plt.tight_layout()
plt.show()
```

## 高效模拟建议

1. **截断 Hilbert spaces**：使用能捕捉 dynamics 的最小 dimension
2. **选择合适 solver**：pure states 下 `sesolve` 比 `mesolve` 更快
3. **Time-dependent terms**：String format（例如 `'cos(w*t)'`）最快
4. **只存储所需数据**：使用 `e_ops`，不要存储所有 states
5. **调整 tolerances**：通过 `Options` 在 accuracy 与 computation time 间平衡
6. **并行 trajectories**：`mcsolve` 会自动使用多个 CPUs
7. **检查 convergence**：改变 `ntraj`、Hilbert space size 和 tolerances

## Troubleshooting

**Memory issues**：降低 Hilbert space dimension，使用 `store_final_state` 选项，或考虑 Krylov methods

**Slow simulations**：使用 string-based time-dependence，稍微增大 tolerances，或对 stiff problems 尝试 `method='bdf'`

**Numerical instabilities**：减小 time steps（`nsteps` 选项）、增大 tolerances，或检查 Hamiltonian/operators 是否正确定义

**Import errors**：确保 QuTiP 已正确安装；quantum gates 需要 `qutip-qip` package

## 参考

此 skill 包含详细 reference documentation：

- **`references/core_concepts.md`**：Quantum objects、states、operators、tensor products、composite systems
- **`references/time_evolution.md`**：所有 solvers（sesolve、mesolve、mcsolve、brmesolve 等）、time-dependent Hamiltonians、solver options
- **`references/visualization.md`**：Bloch sphere、Wigner functions、Q-functions、Fock distributions、matrix plots
- **`references/analysis.md`**：Expectation values、entropy、fidelity、entanglement measures、correlation functions、steady states
- **`references/advanced.md`**：Floquet theory、HEOM、permutational invariance、stochastic methods、superoperators、performance tips

## 外部资源

- Documentation: https://qutip.readthedocs.io/
- Tutorials: https://qutip.org/qutip-tutorials/
- API Reference: https://qutip.readthedocs.io/en/stable/apidoc/apidoc.html
- GitHub: https://github.com/qutip/qutip
