---
name: polars
description: 面向可放入 RAM 的 datasets 的快速 in-memory DataFrame library。当 pandas 太慢但数据仍能放入内存时使用。支持 lazy evaluation、parallel execution，基于 Apache Arrow backend。最适合 1-100GB datasets、ETL pipelines，以及作为更快的 pandas replacement。对于 larger-than-RAM data，请使用 dask 或 vaex。
license: https://github.com/pola-rs/polars/blob/main/LICENSE
metadata:
    skill-author: K-Dense Inc.
---

# Polars

## 概览

Polars 是一个基于 Apache Arrow、面向 Python 和 Rust 的高速 DataFrame library。使用 Polars 的 expression-based API、lazy evaluation framework 和 high-performance data manipulation 能力，进行高效 data processing、pandas migration 和 data pipeline optimization。

## 快速开始

### 安装与基础使用

安装 Polars：
```python
uv pip install polars
```

基础 DataFrame 创建和操作：
```python
import polars as pl

# Create DataFrame
df = pl.DataFrame({
    "name": ["Alice", "Bob", "Charlie"],
    "age": [25, 30, 35],
    "city": ["NY", "LA", "SF"]
})

# Select columns
df.select("name", "age")

# Filter rows
df.filter(pl.col("age") > 25)

# Add computed columns
df.with_columns(
    age_plus_10=pl.col("age") + 10
)
```

## 核心概念

### Expressions

Expressions 是 Polars operations 的基础构建块。它们描述对数据的 transformations，并且可以组合、复用和优化。

**关键原则：**
- 使用 `pl.col("column_name")` 引用 columns
- 通过链式 methods 构建复杂 transformations
- Expressions 是 lazy 的，只会在 contexts（select、with_columns、filter、group_by）中执行

**示例：**
```python
# Expression-based computation
df.select(
    pl.col("name"),
    (pl.col("age") * 12).alias("age_in_months")
)
```

### Lazy vs Eager Evaluation

**Eager（DataFrame）：** Operations 立即执行
```python
df = pl.read_csv("file.csv")  # Reads immediately
result = df.filter(pl.col("age") > 25)  # Executes immediately
```

**Lazy（LazyFrame）：** Operations 构建 query plan，并在执行前优化
```python
lf = pl.scan_csv("file.csv")  # Doesn't read yet
result = lf.filter(pl.col("age") > 25).select("name", "age")
df = result.collect()  # Now executes optimized query
```

**何时使用 lazy：**
- 处理 large datasets
- 复杂 query pipelines
- 只需要部分 columns/rows
- 性能至关重要

**lazy evaluation 的好处：**
- Automatic query optimization
- Predicate pushdown
- Projection pushdown
- Parallel execution

关于详细概念，加载 `references/core_concepts.md`。

## 常见操作

### Select
选择和操作 columns：
```python
# Select specific columns
df.select("name", "age")

# Select with expressions
df.select(
    pl.col("name"),
    (pl.col("age") * 2).alias("double_age")
)

# Select all columns matching a pattern
df.select(pl.col("^.*_id$"))
```

### Filter
按条件过滤 rows：
```python
# Single condition
df.filter(pl.col("age") > 25)

# Multiple conditions (cleaner than using &)
df.filter(
    pl.col("age") > 25,
    pl.col("city") == "NY"
)

# Complex conditions
df.filter(
    (pl.col("age") > 25) | (pl.col("city") == "LA")
)
```

### With Columns
在保留现有 columns 的同时添加或修改 columns：
```python
# Add new columns
df.with_columns(
    age_plus_10=pl.col("age") + 10,
    name_upper=pl.col("name").str.to_uppercase()
)

# Parallel computation (all columns computed in parallel)
df.with_columns(
    pl.col("value") * 10,
    pl.col("value") * 100,
)
```

### Group By 和 Aggregations
对数据分组并计算 aggregations：
```python
# Basic grouping
df.group_by("city").agg(
    pl.col("age").mean().alias("avg_age"),
    pl.len().alias("count")
)

# Multiple group keys
df.group_by("city", "department").agg(
    pl.col("salary").sum()
)

# Conditional aggregations
df.group_by("city").agg(
    (pl.col("age") > 30).sum().alias("over_30")
)
```

关于详细 operation patterns，加载 `references/operations.md`。

## Aggregations 与 Window Functions

### Aggregation Functions
`group_by` context 中的常见 aggregations：
- `pl.len()` - count rows
- `pl.col("x").sum()` - sum values
- `pl.col("x").mean()` - average
- `pl.col("x").min()` / `pl.col("x").max()` - extremes
- `pl.first()` / `pl.last()` - first/last values

### 使用 `over()` 的 Window Functions
在保留 row count 的同时应用 aggregations：
```python
# Add group statistics to each row
df.with_columns(
    avg_age_by_city=pl.col("age").mean().over("city"),
    rank_in_city=pl.col("salary").rank().over("city")
)

# Multiple grouping columns
df.with_columns(
    group_avg=pl.col("value").mean().over("category", "region")
)
```

**Mapping strategies：**
- `group_to_rows`（默认）：保留原始 row order
- `explode`：更快，但会把 rows 按组放在一起
- `join`：创建 list columns

## Data I/O

### Supported Formats
Polars 支持读写：
- CSV, Parquet, JSON, Excel
- Databases（via connectors）
- Cloud storage（S3、Azure、GCS）
- Google BigQuery
- Multiple/partitioned files

### 常见 I/O Operations

**CSV:**
```python
# Eager
df = pl.read_csv("file.csv")
df.write_csv("output.csv")

# Lazy (preferred for large files)
lf = pl.scan_csv("file.csv")
result = lf.filter(...).select(...).collect()
```

**Parquet (recommended for performance):**
```python
df = pl.read_parquet("file.parquet")
df.write_parquet("output.parquet")
```

**JSON:**
```python
df = pl.read_json("file.json")
df.write_json("output.json")
```

关于完整 I/O 文档，加载 `references/io_guide.md`。

## Transformations

### Joins
合并 DataFrames：
```python
# Inner join
df1.join(df2, on="id", how="inner")

# Left join
df1.join(df2, on="id", how="left")

# Join on different column names
df1.join(df2, left_on="user_id", right_on="id")
```

### Concatenation
堆叠 DataFrames：
```python
# Vertical (stack rows)
pl.concat([df1, df2], how="vertical")

# Horizontal (add columns)
pl.concat([df1, df2], how="horizontal")

# Diagonal (union with different schemas)
pl.concat([df1, df2], how="diagonal")
```

### Pivot and Unpivot
重塑 data：
```python
# Pivot (wide format)
df.pivot(values="sales", index="date", columns="product")

# Unpivot (long format)
df.unpivot(index="id", on=["col1", "col2"])
```

关于详细 transformation examples，加载 `references/transformations.md`。

## Pandas Migration

Polars 通过更简洁的 API 相比 pandas 提供显著性能提升。关键差异：

### Conceptual Differences
- **No index**：Polars 只使用 integer positions
- **Strict typing**：没有 silent type conversions
- **Lazy evaluation**：通过 LazyFrame 可用
- **Parallel by default**：Operations 自动 parallelized

### 常见 Operation Mappings

| Operation | Pandas | Polars |
|-----------|--------|--------|
| Select column | `df["col"]` | `df.select("col")` |
| Filter | `df[df["col"] > 10]` | `df.filter(pl.col("col") > 10)` |
| Add column | `df.assign(x=...)` | `df.with_columns(x=...)` |
| Group by | `df.groupby("col").agg(...)` | `df.group_by("col").agg(...)` |
| Window | `df.groupby("col").transform(...)` | `df.with_columns(...).over("col")` |

### 关键 Syntax Patterns

**Pandas sequential（慢）：**
```python
df.assign(
    col_a=lambda df_: df_.value * 10,
    col_b=lambda df_: df_.value * 100
)
```

**Polars parallel（快）：**
```python
df.with_columns(
    col_a=pl.col("value") * 10,
    col_b=pl.col("value") * 100,
)
```

关于完整 migration guide，加载 `references/pandas_migration.md`。

## Best Practices

### Performance Optimization

1. **对 large datasets 使用 lazy evaluation：**
   ```python
   lf = pl.scan_csv("large.csv")  # Don't use read_csv
   result = lf.filter(...).select(...).collect()
   ```

2. **避免在 hot paths 中使用 Python functions：**
   - 保持在 expression API 内以获得 parallelization
   - 仅在必要时使用 `.map_elements()`
   - 优先使用 native Polars operations

3. **对 very large data 使用 streaming：**
   ```python
   lf.collect(streaming=True)
   ```

4. **尽早只选择需要的 columns：**
   ```python
   # Good: Select columns early
   lf.select("col1", "col2").filter(...)

   # Bad: Filter on all columns first
   lf.filter(...).select("col1", "col2")
   ```

5. **使用合适 data types：**
   - low-cardinality strings 使用 Categorical
   - 使用合适 integer sizes（i32 vs i64）
   - temporal data 使用 Date types

### Expression Patterns

**Conditional operations：**
```python
pl.when(condition).then(value).otherwise(other_value)
```

**跨多个 columns 的 Column operations：**
```python
df.select(pl.col("^.*_value$") * 2)  # Regex pattern
```

**Null handling：**
```python
pl.col("x").fill_null(0)
pl.col("x").is_null()
pl.col("x").drop_nulls()
```

关于更多 best practices 和 patterns，加载 `references/best_practices.md`。

## 资源

此 skill 包含完整参考文档：

### references/
- `core_concepts.md` - expressions、lazy evaluation 和 type system 的详细解释
- `operations.md` - 所有常见 operations 的完整指南和 examples
- `pandas_migration.md` - 从 pandas 到 Polars 的完整 migration guide
- `io_guide.md` - 所有 supported formats 的 Data I/O operations
- `transformations.md` - joins、concatenation、pivots 和 reshaping operations
- `best_practices.md` - performance optimization tips 和 common patterns

当用户需要特定主题的详细信息时，按需加载这些 references。
