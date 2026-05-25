---
name: dask
description: 面向大于 RAM 的 pandas/NumPy 工作流程的分布式计算。当您需要将现有 pandas/NumPy 代码扩展到内存之外或跨集群时使用。最适合并行文件处理、分布式 ML、与现有 pandas 代码集成。对于单机上的核外分析，请使用 vaex；对于内存内速度，请使用 polars。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# Dask

## 概述

Dask 是一个用于并行和分布式计算的 Python 库，它支持三个关键功能：
- **单机上大于内存执行**，数据超过可用RAM
- **并行处理**可提高跨多个内核的计算速度
- **分布式计算** 支持跨多台机器的 TB 级数据集

Dask从笔记本电脑（处理~100GiB）扩展到集群（处理~100TiB），同时保持熟悉的PythonAPIs。

## 何时使用此技能

该技能应该在以下情况下使用：
- 处理超出可用RAM的数据集
- 将 pandas 或 NumPy 操作缩放到更大的数据集
- 并行计算以提高性能
- 高效处理多个文件（CSVs、Parquet、JSON、文本日志）
- 构建具有任务依赖性的自定义并行工作流程
- 在多个核心或机器之间分配工作负载

## 核心能力

Dask 提供五个主要组件，每个组件适合不同的用例：

### 1. DataFrames - 并行 Pandas 操作

**目的**：通过并行处理将pandas操作扩展到更大的数据集。

**何时使用**：
- 表格数据超出可用RAM
- 需要一起处理多个CSV/Parquet文件
- Pandas 操作很慢，需要并行化
- 从pandas原型扩展到生产

**参考文档**：有关DaskDataFrames的全面指导，请参阅`references/dataframes.md`，其中包括：
- 读取数据（单个文件、多个文件、glob 模式）
- 常用操作（过滤、groupby、连接、聚合）
- `map_partitions`的自定义操作
- 性能优化技巧
- 常见模式（ETL、时间序列、多文件处理）

**简单示例**：
```python
import dask.dataframe as dd

# Read multiple files as single DataFrame
ddf = dd.read_csv('data/2024-*.csv')

# Operations are lazy until compute()
filtered = ddf[ddf['value'] > 100]
result = filtered.groupby('category').mean().compute()
```

**要点**：
- 操作是惰性的（构建任务图），直到 `.compute()` 被调用
- 使用`map_partitions`进行高效的自定义操作
- 在处理来自其他来源的结构化数据时尽早转换为 DataFrame

### 2. 数组 - 并行NumPy操作

**目的**：使用阻塞算法将NumPy功能扩展到大于内存的数据集。

**何时使用**：
- 数组超出可用RAM
- NumPy 操作需要并行化
- 使用科学数据集（HDF5、Zarr、NetCDF）
- 需要并行线性代数或数组运算

**参考文档**：有关Dask数组的全面指南，请参阅`references/arrays.md`，其中包括：
- 创建数组（从NumPy，随机，从磁盘）
- 分块策略和优化
- 常用运算（算术、归约、线性代数）
- `map_blocks`的自定义操作
- 与 HDF5、Zarr 和 XArray 集成

**简单示例**：
```python
import dask.array as da

# Create large array with chunks
x = da.random.random((100000, 100000), chunks=(10000, 10000))

# Operations are lazy
y = x + 100
z = y.mean(axis=0)

# Compute result
result = z.compute()
```

**要点**：
- 块大小至关重要（目标是每个块 ~100 MB）
- 对块的操作并行进行
- 在需要时重新分块数据以实现高效操作
- 使用 `map_blocks` 进行Dask 中不可用的操作

### 3. Bags - 非结构化数据的并行处理

**目的**：通过函数操作处理非结构化或半结构化数据（文本、JSON、日志）。

**何时使用**：
- 处理文本文件、日志或JSON记录
- 结构化分析前的数据清理和ETL
- 处理不适合 array/dataframe 格式的 Python 对象
- 需要内存高效的流处理

**参考文档**：有关Dask包的综合指南，请参阅`references/bags.md`，其中包括：
- 读取文本和JSON文件
- 函数操作（map、filter、fold、groupby）
- 转换为 DataFrames
- 常用模式（日志分析、JSON处理、文本处理）
- 性能考虑

**简单示例**：
```python
import dask.bag as db
import json

# Read and parse JSON files
bag = db.read_text('logs/*.json').map(json.loads)

# Filter and transform
valid = bag.filter(lambda x: x['status'] == 'valid')
processed = valid.map(lambda x: {'id': x['id'], 'value': x['value']})

# Convert to DataFrame for analysis
ddf = processed.to_dataframe()
```

**要点**：
- 用于初始数据清理，然后转换为DataFrame/Array
- 使用`foldby`代替`groupby`以获得更好的性能
- 操作是流式的并且内存效率高
- 转换为结构化格式（DataFrame）以进行复杂操作

### 4. Futures - 基于任务的并行化

**目的**：通过对任务执行和依赖关系的细粒度控制来构建自定义并行工作流程。

**何时使用**：
- 构建动态、不断发展的工作流程
- 需要立即执行任务（不是懒惰）
- 计算取决于运行时条件
- 实现自定义并行算法
- 需要有状态计算

**参考文档**：有关Dask Futures的全面指导，请参阅`references/futures.md`，其中包括：
- 设置分布式客户端
- 提交任务并使用 future
- 任务依赖性和数据移动
- 高级协调（队列、锁、事件、参与者）
- 常见模式（参数扫描、动态任务、迭代算法）

**简单示例**：
```python
from dask.distributed import Client

client = Client()  # Create local cluster

# Submit tasks (executes immediately)
def process(x):
    return x ** 2

futures = client.map(process, range(100))

# Gather results
results = client.gather(futures)

client.close()
```

**要点**：
- 需要分布式客户端（即使是单机）
- 任务提交后立即执行
- 大数据预分散，避免重复传输
- 每个任务约 1 毫秒的开销（不适合数百万个微小任务）
- 使用参与者进行有状态的工作流程

### 5. 调度程序 - 执行后端

**目的**：控制Dask任务的执行方式和地点（线程、进程、分布式）。

**何时选择Scheduler**：
- **线程**（默认）：NumPy/Pandas操作，GIL释放库，共享内存好处
- **进程**：纯Python代码、文本处理、GIL绑定操作
- **同步**：使用 pdb 进行调试、分析、理解错误
- **分布式**：需要dashboard，多机集群，高级功能

**参考文档**：有关Dask调度程序的全面指导，请参阅`references/schedulers.md`，其中包括：
- 详细的调度程序描述和特性
- 配置方法（全局、上下文管理器、每个计算）
- 性能考虑和开销
- 常见模式和故障排除
- 线程配置以获得最佳性能

**简单示例**：
```python
import dask
import dask.dataframe as dd

# Use threads for DataFrame (default, good for numeric)
ddf = dd.read_csv('data.csv')
result1 = ddf.mean().compute()  # Uses threads

# Use processes for Python-heavy work
import dask.bag as db
bag = db.read_text('logs/*.txt')
result2 = bag.map(python_function).compute(scheduler='processes')

# Use synchronous for debugging
dask.config.set(scheduler='synchronous')
result3 = problematic_computation.compute()  # Can use pdb

# Use distributed for monitoring and scaling
from dask.distributed import Client
client = Client()
result4 = computation.compute()  # Uses distributed with dashboard
```

**要点**：
- 线程：最低开销（~10 µs/任务），最适合数字工作
- 进程：避免GIL（~10ms/task），最适合Python工作
- 分布式：监控 dashboard (~1 ms/task)，扩展到集群
- 可以根据计算或全局切换调度程序

## 最佳实践

有关全面的性能优化指南、内存管理策略和要避免的常见陷阱，请参阅`references/best-practices.md`。主要原则包括：

### 从更简单的解决方案开始
在使用Dask之前，探索：
- 更好的算法
- 高效的文件格式（Parquet而不是CSV）
- 编译代码（Numba、Cython）
- 数据采样

### 关键性能规则

**1。不要在本地加载数据然后交给Dask**
```python
# Wrong: Loads all data in memory first
import pandas as pd
df = pd.read_csv('large.csv')
ddf = dd.from_pandas(df, npartitions=10)

# Correct: Let Dask handle loading
import dask.dataframe as dd
ddf = dd.read_csv('large.csv')
```

**2。避免重复的compute()调用**
```python
# Wrong: Each compute is separate
for item in items:
    result = dask_computation(item).compute()

# Correct: Single compute for all
computations = [dask_computation(item) for item in items]
results = dask.compute(*computations)
```

**3。不要构建过大的任务图**
- 如果有数百万个任务，则增加块大小
- 使用`map_partitions`/`map_blocks`来熔断操作
- 检查任务图大小：`len(ddf.__dask_graph__())`

**4。选择合适的块尺寸**
- 目标：每个块 ~100 MB（或工作内存中每个核心 10 个块）
- 太大：内存溢出
- 太小：调度开销

**5。使用仪表板**
```python
from dask.distributed import Client
client = Client()
print(client.dashboard_link)  # Monitor performance, identify bottlenecks
```

## 常见工作流程模式

### ETL 管道
```python
import dask.dataframe as dd

# Extract: Read data
ddf = dd.read_csv('raw_data/*.csv')

# Transform: Clean and process
ddf = ddf[ddf['status'] == 'valid']
ddf['amount'] = ddf['amount'].astype('float64')
ddf = ddf.dropna(subset=['important_col'])

# Load: Aggregate and save
summary = ddf.groupby('category').agg({'amount': ['sum', 'mean']})
summary.to_parquet('output/summary.parquet')
```

### 非结构化到结构化管道
```python
import dask.bag as db
import json

# Start with Bag for unstructured data
bag = db.read_text('logs/*.json').map(json.loads)
bag = bag.filter(lambda x: x['status'] == 'valid')

# Convert to DataFrame for structured analysis
ddf = bag.to_dataframe()
result = ddf.groupby('category').mean().compute()
```

### 大规模Array计算
```python
import dask.array as da

# Load or create large array
x = da.from_zarr('large_dataset.zarr')

# Process in chunks
normalized = (x - x.mean()) / x.std()

# Save result
da.to_zarr(normalized, 'normalized.zarr')
```

### 自定义并行工作流程
```python
from dask.distributed import Client

client = Client()

# Scatter large dataset once
data = client.scatter(large_dataset)

# Process in parallel with dependencies
futures = []
for param in parameters:
    future = client.submit(process, data, param)
    futures.append(future)

# Gather results
results = client.gather(futures)
```

## 选择正确的组件

使用此决策指南选择适当的 Dask 组件：

**数据类型**：
- 表格数据 → **DataFrames**
- 数字数组 → **数组**
- Text/JSON/logs → **包**（然后转换为DataFrame）
- 自定义 Python 对象 → **包** 或 **Futures**

**操作类型**：
- 标准pandas操作 → **DataFrames**
- 标准 NumPy 操作 → **数组**
- 自定义并行任务 → **Futures**
- 文本 processing/ETL → **包**

**控制级别**：
- 高级，自动 → **DataFrames/Arrays**
- 低级，手动 → **Futures**

**工作流程类型**：
- 静态计算图 → **DataFrames/Arrays/Bags**
- 动态，不断发展 → **Futures**

## 集成注意事项

### 文件格式
- **高效**：Parquet、HDF5、Zarr（柱状、压缩、并行友好）
- **兼容但速度较慢**：CSV（仅用于初始摄取）
- **对于数组**：HDF5、Zarr、NetCDF

### 集合之间的转换
```python
# Bag → DataFrame
ddf = bag.to_dataframe()

# DataFrame → Array (for numeric data)
arr = ddf.to_dask_array(lengths=True)

# Array → DataFrame
ddf = dd.from_dask_array(arr, columns=['col1', 'col2'])
```

### 与其他库
- **XArray**：用标记维度（地理空间、成像）包裹 Dask 数组
- **Dask-ML**：机器学习与scikit-learn兼容APIs
- **分布式**：高级集群管理和监控

## 调试与开发

### 迭代开发工作流程

1. **使用同步调度程序对小数据进行测试**：
```python
dask.config.set(scheduler='synchronous')
result = computation.compute()  # Can use pdb, easy debugging
```

2. **使用示例上的线程进行验证**：
```python
sample = ddf.head(1000)  # Small sample
# Test logic, then scale to full dataset
```

3. **具有分布式监控规模**：
```python
from dask.distributed import Client
client = Client()
print(client.dashboard_link)  # Monitor performance
result = computation.compute()
```

### 常见问题

**内存错误**：
- 减少块大小
- 有策略地使用`persist()`并在完成后删除
- 检查自定义函数中的内存泄漏

**慢启动**：
- 任务图太大（增加块大小）
- 使用`map_partitions`或`map_blocks`减少任务

**并行化较差**：
- 块太大（增加分区数量）
- 使用带有Python代码的线程（切换到进程）
- 数据依赖性阻碍并行性

## 参考文件

所有参考文档文件均可根据需要阅读以获取详细信息：

- `references/dataframes.md` - 完整Dask DataFrame 指南
- `references/arrays.md` - 完整Dask Array 指南
- `references/bags.md` - 完整Dask 包指南
- `references/futures.md` - 完整的Dask Futures和分布式计算指南
- `references/schedulers.md` - 完整的调度程序选择和配置指南
- `references/best-practices.md` - 全面的性能优化和故障排除

当用户需要有关特定 Dask 组件、操作或模式的详细信息（超出此处提供的快速指南）时加载这些文件。
