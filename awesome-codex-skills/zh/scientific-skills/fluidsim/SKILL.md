---
name: fluidsim
description: 使用 Python 进行 computational fluid dynamics simulations 的 framework。运行 fluid dynamics simulations，包括 Navier-Stokes equations（2D/3D）、shallow water equations、stratified flows，或分析 turbulence、vortex dynamics、geophysical flows 时使用。提供带 FFT 的 pseudospectral methods、HPC support 和综合 output analysis。
license: CeCILL FREE SOFTWARE LICENSE AGREEMENT
metadata:
    skill-author: K-Dense Inc.
---

# FluidSim

## 概述

FluidSim 是一个面向 high-performance computational fluid dynamics (CFD) simulations 的面向对象 Python framework。它使用带 FFT 的 pseudospectral methods 为 periodic-domain equations 提供 solvers，性能可与 Fortran/C++ 相当，同时保留 Python 的易用性。

**关键优势**：
- 多种 solvers：2D/3D Navier-Stokes、shallow water、stratified flows
- 高性能：Pythran/Transonic compilation、MPI parallelization
- 完整工作流：Parameter configuration、simulation execution、output analysis
- 交互式分析：基于 Python 的 post-processing 和 visualization

## 核心能力

### 1. 安装和设置

使用 uv 并带合适 feature flags 安装 fluidsim：

```bash
# Basic installation
uv pip install fluidsim

# With FFT support (required for most solvers)
uv pip install "fluidsim[fft]"

# With MPI for parallel computing
uv pip install "fluidsim[fft,mpi]"
```

设置输出目录的 environment variables（可选）：

```bash
export FLUIDSIM_PATH=/path/to/simulation/outputs
export FLUIDDYN_PATH_SCRATCH=/path/to/working/directory
```

无需 API keys 或 authentication。

完整 installation instructions 和 environment configuration 见 `references/installation.md`。

### 2. 运行 Simulations

标准工作流由五步组成：

**Step 1**：Import solver
```python
from fluidsim.solvers.ns2d.solver import Simul
```

**Step 2**：创建并配置 parameters
```python
params = Simul.create_default_params()
params.oper.nx = params.oper.ny = 256
params.oper.Lx = params.oper.Ly = 2 * 3.14159
params.nu_2 = 1e-3
params.time_stepping.t_end = 10.0
params.init_fields.type = "noise"
```

**Step 3**：实例化 simulation
```python
sim = Simul(params)
```

**Step 4**：执行
```python
sim.time_stepping.start()
```

**Step 5**：分析结果
```python
sim.output.phys_fields.plot("vorticity")
sim.output.spatial_means.plot()
```

完整 examples、restarting simulations 和 cluster deployment 见 `references/simulation_workflow.md`。

### 3. 可用 Solvers

根据 physical problem 选择 solver：

**2D Navier-Stokes** (`ns2d`)：2D turbulence、vortex dynamics
```python
from fluidsim.solvers.ns2d.solver import Simul
```

**3D Navier-Stokes** (`ns3d`)：3D turbulence、realistic flows
```python
from fluidsim.solvers.ns3d.solver import Simul
```

**Stratified flows** (`ns2d.strat`, `ns3d.strat`)：Oceanic/atmospheric flows
```python
from fluidsim.solvers.ns2d.strat.solver import Simul
params.N = 1.0  # Brunt-Väisälä frequency
```

**Shallow water** (`sw1l`)：Geophysical flows、rotating systems
```python
from fluidsim.solvers.sw1l.solver import Simul
params.f = 1.0  # Coriolis parameter
```

完整 solver list 和 selection guidance 见 `references/solvers.md`。

### 4. Parameter Configuration

Parameters 按层级组织，并通过 dot notation 访问：

**Domain and resolution**：
```python
params.oper.nx = 256  # grid points
params.oper.Lx = 2 * pi  # domain size
```

**Physical parameters**：
```python
params.nu_2 = 1e-3  # viscosity
params.nu_4 = 0     # hyperviscosity (optional)
```

**Time stepping**：
```python
params.time_stepping.t_end = 10.0
params.time_stepping.USE_CFL = True  # adaptive time step
params.time_stepping.CFL = 0.5
```

**Initial conditions**：
```python
params.init_fields.type = "noise"  # or "dipole", "vortex", "from_file", "in_script"
```

**Output settings**：
```python
params.output.periods_save.phys_fields = 1.0  # save every 1.0 time units
params.output.periods_save.spectra = 0.5
params.output.periods_save.spatial_means = 0.1
```

Parameters object 会对拼写错误抛出 `AttributeError`，避免静默配置错误。

完整 parameter documentation 见 `references/parameters.md`。

### 5. Output and Analysis

FluidSim 会在 simulation 期间自动保存多种 output types：

**Physical fields**：HDF5 format 的 velocity、vorticity
```python
sim.output.phys_fields.plot("vorticity")
sim.output.phys_fields.plot("vx")
```

**Spatial means**：volume-averaged quantities 的 time series
```python
sim.output.spatial_means.plot()
```

**Spectra**：Energy 和 enstrophy spectra
```python
sim.output.spectra.plot1d()
sim.output.spectra.plot2d()
```

**加载 previous simulations**：
```python
from fluidsim import load_sim_for_plot
sim = load_sim_for_plot("simulation_dir")
sim.output.phys_fields.plot()
```

**Advanced visualization**：在 ParaView 或 VisIt 中打开 `.h5` 文件进行 3D visualization。

详细 analysis workflows、parametric study analysis 和 data export 见 `references/output_analysis.md`。

### 6. 高级功能

**Custom forcing**：维持 turbulence 或驱动特定 dynamics
```python
params.forcing.enable = True
params.forcing.type = "tcrandom"  # time-correlated random forcing
params.forcing.forcing_rate = 1.0
```

**Custom initial conditions**：在脚本中定义 fields
```python
params.init_fields.type = "in_script"
sim = Simul(params)
X, Y = sim.oper.get_XY_loc()
vx = sim.state.state_phys.get_var("vx")
vx[:] = sin(X) * cos(Y)
sim.time_stepping.start()
```

**MPI parallelization**：在多个 processors 上运行
```bash
mpirun -np 8 python simulation_script.py
```

**Parametric studies**：用不同 parameters 运行多个 simulations
```python
for nu in [1e-3, 5e-4, 1e-4]:
    params = Simul.create_default_params()
    params.nu_2 = nu
    params.output.sub_directory = f"nu{nu}"
    sim = Simul(params)
    sim.time_stepping.start()
```

Forcing types、custom solvers、cluster submission 和 performance optimization 见 `references/advanced_features.md`。

## 常见使用场景

### 2D Turbulence Study

```python
from fluidsim.solvers.ns2d.solver import Simul
from math import pi

params = Simul.create_default_params()
params.oper.nx = params.oper.ny = 512
params.oper.Lx = params.oper.Ly = 2 * pi
params.nu_2 = 1e-4
params.time_stepping.t_end = 50.0
params.time_stepping.USE_CFL = True
params.init_fields.type = "noise"
params.output.periods_save.phys_fields = 5.0
params.output.periods_save.spectra = 1.0

sim = Simul(params)
sim.time_stepping.start()

# Analyze energy cascade
sim.output.spectra.plot1d(tmin=30.0, tmax=50.0)
```

### Stratified Flow Simulation

```python
from fluidsim.solvers.ns2d.strat.solver import Simul

params = Simul.create_default_params()
params.oper.nx = params.oper.ny = 256
params.N = 2.0  # stratification strength
params.nu_2 = 5e-4
params.time_stepping.t_end = 20.0

# Initialize with dense layer
params.init_fields.type = "in_script"
sim = Simul(params)
X, Y = sim.oper.get_XY_loc()
b = sim.state.state_phys.get_var("b")
b[:] = exp(-((X - 3.14)**2 + (Y - 3.14)**2) / 0.5)
sim.state.statephys_from_statespect()

sim.time_stepping.start()
sim.output.phys_fields.plot("b")
```

### 使用 MPI 的 High-Resolution 3D Simulation

```python
from fluidsim.solvers.ns3d.solver import Simul

params = Simul.create_default_params()
params.oper.nx = params.oper.ny = params.oper.nz = 512
params.nu_2 = 1e-5
params.time_stepping.t_end = 10.0
params.init_fields.type = "noise"

sim = Simul(params)
sim.time_stepping.start()
```

运行方式：
```bash
mpirun -np 64 python script.py
```

### Taylor-Green Vortex Validation

```python
from fluidsim.solvers.ns2d.solver import Simul
import numpy as np
from math import pi

params = Simul.create_default_params()
params.oper.nx = params.oper.ny = 128
params.oper.Lx = params.oper.Ly = 2 * pi
params.nu_2 = 1e-3
params.time_stepping.t_end = 10.0
params.init_fields.type = "in_script"

sim = Simul(params)
X, Y = sim.oper.get_XY_loc()
vx = sim.state.state_phys.get_var("vx")
vy = sim.state.state_phys.get_var("vy")
vx[:] = np.sin(X) * np.cos(Y)
vy[:] = -np.cos(X) * np.sin(Y)
sim.state.statephys_from_statespect()

sim.time_stepping.start()

# Validate energy decay
df = sim.output.spatial_means.load()
# Compare with analytical solution
```

## 快速参考

**Import solver**：`from fluidsim.solvers.ns2d.solver import Simul`

**创建 parameters**：`params = Simul.create_default_params()`

**设置 resolution**：`params.oper.nx = params.oper.ny = 256`

**设置 viscosity**：`params.nu_2 = 1e-3`

**设置 end time**：`params.time_stepping.t_end = 10.0`

**运行 simulation**：`sim = Simul(params); sim.time_stepping.start()`

**绘制结果**：`sim.output.phys_fields.plot("vorticity")`

**加载 simulation**：`sim = load_sim_for_plot("path/to/sim")`

## 资源

**Documentation**：https://fluidsim.readthedocs.io/

**Reference files**：
- `references/installation.md`：完整 installation instructions
- `references/solvers.md`：Available solvers 和 selection guide
- `references/simulation_workflow.md`：详细 workflow examples
- `references/parameters.md`：综合 parameter documentation
- `references/output_analysis.md`：Output types 和 analysis methods
- `references/advanced_features.md`：Forcing、MPI、parametric studies、custom solvers
