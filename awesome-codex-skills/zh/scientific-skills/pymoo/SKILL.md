---
name: pymoo
description: Multi-objective optimization framework。面向 engineering design 和 optimization problems，支持 NSGA-II、NSGA-III、MOEA/D、Pareto fronts、constraint handling、benchmarks（ZDT、DTLZ）。
license: Apache-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# Pymoo - Python 中的 Multi-Objective Optimization

## 概览

Pymoo 是一个综合 Python framework，用于 optimization，重点面向 multi-objective problems。可使用 state-of-the-art algorithms（NSGA-II/III、MOEA/D）、benchmark problems（ZDT、DTLZ）、customizable genetic operators 和 multi-criteria decision making methods 求解 single 与 multi-objective optimization。它擅长为具有 conflicting objectives 的问题寻找 trade-off solutions（Pareto fronts）。

## 何时使用此 Skill

此 skill 应用于：
- 求解具有一个或多个 objectives 的 optimization problems
- 寻找 Pareto-optimal solutions 并分析 trade-offs
- 实现 evolutionary algorithms（GA、DE、PSO、NSGA-II/III）
- 处理 constrained optimization problems
- 在 standard test problems（ZDT、DTLZ、WFG）上 benchmark algorithms
- 自定义 genetic operators（crossover、mutation、selection）
- 可视化 high-dimensional optimization results
- 从多个 competing solutions 中做决策
- 处理 binary、discrete、continuous 或 mixed-variable problems

## 核心概念

### Unified Interface

Pymoo 对所有 optimization tasks 使用一致的 `minimize()` function：

```python
from pymoo.optimize import minimize

result = minimize(
    problem,        # What to optimize
    algorithm,      # How to optimize
    termination,    # When to stop
    seed=1,
    verbose=True
)
```

**Result object 包含：**
- `result.X`：optimal solution(s) 的 decision variables
- `result.F`：optimal solution(s) 的 objective values
- `result.G`：constraint violations（如果 constrained）
- `result.algorithm`：带 history 的 Algorithm object

### Problem Types

**Single-objective：** 一个 objective 需要 minimize/maximize
**Multi-objective：** 2-3 个 conflicting objectives → Pareto front
**Many-objective：** 4+ objectives → High-dimensional Pareto front
**Constrained：** Objectives + inequality/equality constraints
**Dynamic：** Time-varying objectives 或 constraints

## Quick Start Workflows

### Workflow 1：Single-Objective Optimization

**何时：** 优化一个 objective function

**步骤：**
1. 定义或选择 problem
2. 选择 single-objective algorithm（GA、DE、PSO、CMA-ES）
3. 配置 termination criteria
4. 运行 optimization
5. 提取 best solution

**示例：**
```python
from pymoo.algorithms.soo.nonconvex.ga import GA
from pymoo.problems import get_problem
from pymoo.optimize import minimize

# Built-in problem
problem = get_problem("rastrigin", n_var=10)

# Configure Genetic Algorithm
algorithm = GA(
    pop_size=100,
    eliminate_duplicates=True
)

# Optimize
result = minimize(
    problem,
    algorithm,
    ('n_gen', 200),
    seed=1,
    verbose=True
)

print(f"Best solution: {result.X}")
print(f"Best objective: {result.F[0]}")
```

**参见：** `scripts/single_objective_example.py` 获取完整示例

### Workflow 2：Multi-Objective Optimization（2-3 objectives）

**何时：** 优化 2-3 个 conflicting objectives，需要 Pareto front

**Algorithm choice：** NSGA-II（bi/tri-objective 的标准选择）

**步骤：**
1. 定义 multi-objective problem
2. 配置 NSGA-II
3. 运行 optimization 以获得 Pareto front
4. 可视化 trade-offs
5. 应用 decision making（可选）

**示例：**
```python
from pymoo.algorithms.moo.nsga2 import NSGA2
from pymoo.problems import get_problem
from pymoo.optimize import minimize
from pymoo.visualization.scatter import Scatter

# Bi-objective benchmark problem
problem = get_problem("zdt1")

# NSGA-II algorithm
algorithm = NSGA2(pop_size=100)

# Optimize
result = minimize(problem, algorithm, ('n_gen', 200), seed=1)

# Visualize Pareto front
plot = Scatter()
plot.add(result.F, label="Obtained Front")
plot.add(problem.pareto_front(), label="True Front", alpha=0.3)
plot.show()

print(f"Found {len(result.F)} Pareto-optimal solutions")
```

**参见：** `scripts/multi_objective_example.py` 获取完整示例

### Workflow 3：Many-Objective Optimization（4+ objectives）

**何时：** 优化 4 个或更多 objectives

**Algorithm choice：** NSGA-III（为 many objectives 设计）

**关键差异：** 必须提供 reference directions 以引导 population

**步骤：**
1. 定义 many-objective problem
2. 生成 reference directions
3. 使用 reference directions 配置 NSGA-III
4. 运行 optimization
5. 使用 Parallel Coordinate Plot 可视化

**示例：**
```python
from pymoo.algorithms.moo.nsga3 import NSGA3
from pymoo.problems import get_problem
from pymoo.optimize import minimize
from pymoo.util.ref_dirs import get_reference_directions
from pymoo.visualization.pcp import PCP

# Many-objective problem (5 objectives)
problem = get_problem("dtlz2", n_obj=5)

# Generate reference directions (required for NSGA-III)
ref_dirs = get_reference_directions("das-dennis", n_dim=5, n_partitions=12)

# Configure NSGA-III
algorithm = NSGA3(ref_dirs=ref_dirs)

# Optimize
result = minimize(problem, algorithm, ('n_gen', 300), seed=1)

# Visualize with Parallel Coordinates
plot = PCP(labels=[f"f{i+1}" for i in range(5)])
plot.add(result.F, alpha=0.3)
plot.show()
```

**参见：** `scripts/many_objective_example.py` 获取完整示例

### Workflow 4：Custom Problem Definition

**何时：** 求解 domain-specific optimization problem

**步骤：**
1. 扩展 `ElementwiseProblem` class
2. 在 `__init__` 中定义 problem dimensions 和 bounds
3. 为 objectives（和 constraints）实现 `_evaluate` method
4. 与任意 algorithm 一起使用

**Unconstrained example：**
```python
from pymoo.core.problem import ElementwiseProblem
import numpy as np

class MyProblem(ElementwiseProblem):
    def __init__(self):
        super().__init__(
            n_var=2,              # Number of variables
            n_obj=2,              # Number of objectives
            xl=np.array([0, 0]),  # Lower bounds
            xu=np.array([5, 5])   # Upper bounds
        )

    def _evaluate(self, x, out, *args, **kwargs):
        # Define objectives
        f1 = x[0]**2 + x[1]**2
        f2 = (x[0]-1)**2 + (x[1]-1)**2

        out["F"] = [f1, f2]
```

**Constrained example：**
```python
class ConstrainedProblem(ElementwiseProblem):
    def __init__(self):
        super().__init__(
            n_var=2,
            n_obj=2,
            n_ieq_constr=2,        # Inequality constraints
            n_eq_constr=1,         # Equality constraints
            xl=np.array([0, 0]),
            xu=np.array([5, 5])
        )

    def _evaluate(self, x, out, *args, **kwargs):
        # Objectives
        out["F"] = [f1, f2]

        # Inequality constraints (g <= 0)
        out["G"] = [g1, g2]

        # Equality constraints (h = 0)
        out["H"] = [h1]
```

**Constraint formulation rules：**
- Inequality：表示为 `g(x) <= 0`（≤ 0 时 feasible）
- Equality：表示为 `h(x) = 0`（= 0 时 feasible）
- 将 `g(x) >= b` 转换为 `-(g(x) - b) <= 0`

**参见：** `scripts/custom_problem_example.py` 获取完整 examples

### Workflow 5：Constraint Handling

**何时：** Problem 有 feasibility constraints

**Approach options：**

**1. Feasibility First（默认 - 推荐）**
```python
from pymoo.algorithms.moo.nsga2 import NSGA2

# Works automatically with constrained problems
algorithm = NSGA2(pop_size=100)
result = minimize(problem, algorithm, termination)

# Check feasibility
feasible = result.CV[:, 0] == 0  # CV = constraint violation
print(f"Feasible solutions: {np.sum(feasible)}")
```

**2. Penalty Method**
```python
from pymoo.constraints.as_penalty import ConstraintsAsPenalty

# Wrap problem to convert constraints to penalties
problem_penalized = ConstraintsAsPenalty(problem, penalty=1e6)
```

**3. Constraint as Objective**
```python
from pymoo.constraints.as_obj import ConstraintsAsObjective

# Treat constraint violation as additional objective
problem_with_cv = ConstraintsAsObjective(problem)
```

**4. Specialized Algorithms**
```python
from pymoo.algorithms.soo.nonconvex.sres import SRES

# SRES has built-in constraint handling
algorithm = SRES()
```

**参见：** `references/constraints_mcdm.md` 获取 comprehensive constraint handling guide

### Workflow 6：从 Pareto Front 做 Decision Making

**何时：** 已有 Pareto front，需要选择 preferred solution(s)

**步骤：**
1. 运行 multi-objective optimization
2. 将 objectives normalize 到 [0, 1]
3. 定义 preference weights
4. 应用 MCDM method
5. 可视化 selected solution

**使用 Pseudo-Weights 的示例：**
```python
from pymoo.mcdm.pseudo_weights import PseudoWeights
import numpy as np

# After obtaining result from multi-objective optimization
# Normalize objectives
F_norm = (result.F - result.F.min(axis=0)) / (result.F.max(axis=0) - result.F.min(axis=0))

# Define preferences (must sum to 1)
weights = np.array([0.3, 0.7])  # 30% f1, 70% f2

# Apply decision making
dm = PseudoWeights(weights)
selected_idx = dm.do(F_norm)

# Get selected solution
best_solution = result.X[selected_idx]
best_objectives = result.F[selected_idx]

print(f"Selected solution: {best_solution}")
print(f"Objective values: {best_objectives}")
```

**其他 MCDM methods：**
- Compromise Programming：选择最接近 ideal point 的方案
- Knee Point：查找 balanced trade-off solutions
- Hypervolume Contribution：选择 most diverse subset

**参见：**
- `scripts/decision_making_example.py` 获取完整示例
- `references/constraints_mcdm.md` 获取详细 MCDM methods

### Workflow 7：Visualization

**根据 objectives 数量选择 visualization：**

**2 objectives：Scatter Plot**
```python
from pymoo.visualization.scatter import Scatter

plot = Scatter(title="Bi-objective Results")
plot.add(result.F, color="blue", alpha=0.7)
plot.show()
```

**3 objectives：3D Scatter**
```python
plot = Scatter(title="Tri-objective Results")
plot.add(result.F)  # Automatically renders in 3D
plot.show()
```

**4+ objectives：Parallel Coordinate Plot**
```python
from pymoo.visualization.pcp import PCP

plot = PCP(
    labels=[f"f{i+1}" for i in range(n_obj)],
    normalize_each_axis=True
)
plot.add(result.F, alpha=0.3)
plot.show()
```

**Solution comparison：Petal Diagram**
```python
from pymoo.visualization.petal import Petal

plot = Petal(
    bounds=[result.F.min(axis=0), result.F.max(axis=0)],
    labels=["Cost", "Weight", "Efficiency"]
)
plot.add(solution_A, label="Design A")
plot.add(solution_B, label="Design B")
plot.show()
```

**参见：** `references/visualization.md` 获取所有 visualization types 和 usage

## Algorithm Selection Guide

### Single-Objective Problems

| Algorithm | 最适合 | Key Features |
|-----------|----------|--------------|
| **GA** | General-purpose | Flexible, customizable operators |
| **DE** | Continuous optimization | Good global search |
| **PSO** | Smooth landscapes | Fast convergence |
| **CMA-ES** | Difficult/noisy problems | Self-adapting |

### Multi-Objective Problems（2-3 objectives）

| Algorithm | 最适合 | Key Features |
|-----------|----------|--------------|
| **NSGA-II** | Standard benchmark | Fast, reliable, well-tested |
| **R-NSGA-II** | Preference regions | Reference point guidance |
| **MOEA/D** | Decomposable problems | Scalarization approach |

### Many-Objective Problems（4+ objectives）

| Algorithm | 最适合 | Key Features |
|-----------|----------|--------------|
| **NSGA-III** | 4-15 objectives | Reference direction-based |
| **RVEA** | Adaptive search | Reference vector evolution |
| **AGE-MOEA** | Complex landscapes | Adaptive geometry |

### Constrained Problems

| Approach | Algorithm | 何时使用 |
|----------|-----------|-------------|
| Feasibility-first | Any algorithm | Large feasible region |
| Specialized | SRES, ISRES | Heavy constraints |
| Penalty | GA + penalty | Algorithm compatibility |

**参见：** `references/algorithms.md` 获取 comprehensive algorithm reference

## Benchmark Problems

### 快速访问 problem：
```python
from pymoo.problems import get_problem

# Single-objective
problem = get_problem("rastrigin", n_var=10)
problem = get_problem("rosenbrock", n_var=10)

# Multi-objective
problem = get_problem("zdt1")        # Convex front
problem = get_problem("zdt2")        # Non-convex front
problem = get_problem("zdt3")        # Disconnected front

# Many-objective
problem = get_problem("dtlz2", n_obj=5, n_var=12)
problem = get_problem("dtlz7", n_obj=4)
```

**参见：** `references/problems.md` 获取完整 test problem reference

## Genetic Operator Customization

### Standard operator configuration：
```python
from pymoo.algorithms.soo.nonconvex.ga import GA
from pymoo.operators.crossover.sbx import SBX
from pymoo.operators.mutation.pm import PM

algorithm = GA(
    pop_size=100,
    crossover=SBX(prob=0.9, eta=15),
    mutation=PM(eta=20),
    eliminate_duplicates=True
)
```

### 按 variable type 选择 operator：

**Continuous variables：**
- Crossover：SBX（Simulated Binary Crossover）
- Mutation：PM（Polynomial Mutation）

**Binary variables：**
- Crossover：TwoPointCrossover、UniformCrossover
- Mutation：BitflipMutation

**Permutations（TSP、scheduling）：**
- Crossover：OrderCrossover（OX）
- Mutation：InversionMutation

**参见：** `references/operators.md` 获取 comprehensive operator reference

## Performance 与 Troubleshooting

### 常见问题与解决方案：

**Problem：Algorithm not converging**
- 增加 population size
- 增加 number of generations
- 检查 problem 是否 multimodal（尝试不同 algorithms）
- 验证 constraints 是否 correctly formulated

**Problem：Poor Pareto front distribution**
- 对 NSGA-III：调整 reference directions
- 增加 population size
- 检查 duplicate elimination
- 验证 problem scaling

**Problem：Few feasible solutions**
- 使用 constraint-as-objective approach
- 应用 repair operators
- 对 constrained problems 尝试 SRES/ISRES
- 检查 constraint formulation（应为 g <= 0）

**Problem：High computational cost**
- 减少 population size
- 减少 number of generations
- 使用更简单 operators
- 启用 parallelization（如果 problem 支持）

### Best practices：

1. 当 scales 差异显著时，**Normalize objectives**
2. 为 reproducibility **Set random seed**
3. **Save history** 以分析 convergence：`save_history=True`
4. **Visualize results** 以理解 solution quality
5. 可用时 **Compare with true Pareto front**
6. **Use appropriate termination criteria**（generations、evaluations、tolerance）
7. 根据 problem characteristics **Tune operator parameters**

## 资源

此 skill 包含 comprehensive reference documentation 和 executable examples：

### references/
用于深入理解的详细文档：

- **algorithms.md**：包含 parameters、usage 和 selection guidelines 的完整 algorithm reference
- **problems.md**：Benchmark test problems（ZDT、DTLZ、WFG）及其 characteristics
- **operators.md**：Genetic operators（sampling、selection、crossover、mutation）及 configuration
- **visualization.md**：所有 visualization types、examples 和 selection guide
- **constraints_mcdm.md**：Constraint handling techniques 和 multi-criteria decision making methods

**References 的 search patterns：**
- Algorithm details: `grep -r "NSGA-II\|NSGA-III\|MOEA/D" references/`
- Constraint methods: `grep -r "Feasibility First\|Penalty\|Repair" references/`
- Visualization types: `grep -r "Scatter\|PCP\|Petal" references/`

### scripts/
演示 common workflows 的 executable examples：

- **single_objective_example.py**：使用 GA 的 basic single-objective optimization
- **multi_objective_example.py**：使用 NSGA-II 的 multi-objective optimization 与 visualization
- **many_objective_example.py**：使用 NSGA-III 和 reference directions 的 many-objective optimization
- **custom_problem_example.py**：定义 custom problems（constrained 和 unconstrained）
- **decision_making_example.py**：带不同 preferences 的 multi-criteria decision making

**运行 examples：**
```bash
python3 scripts/single_objective_example.py
python3 scripts/multi_objective_example.py
python3 scripts/many_objective_example.py
python3 scripts/custom_problem_example.py
python3 scripts/decision_making_example.py
```

## Additional Notes

**Installation：**
```bash
uv pip install pymoo
```

**Dependencies：** NumPy、SciPy、matplotlib、autograd（gradient-based 可选）

**Documentation：** https://pymoo.org/

**Version：** 此 skill 基于 pymoo 0.6.x

**Common patterns：**
- custom problems 始终使用 `ElementwiseProblem`
- Constraints 表述为 `g(x) <= 0` 和 `h(x) = 0`
- NSGA-III 需要 reference directions
- MCDM 前 normalize objectives
- 使用合适 termination：`('n_gen', N)` 或 `get_termination("f_tol", tol=0.001)`
