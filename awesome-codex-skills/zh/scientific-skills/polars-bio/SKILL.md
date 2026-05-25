---
name: polars-bio
description: 基于 Polars DataFrames 的高性能 genomic interval operations 和 bioinformatics file I/O。面向 BED/VCF/BAM/GFF intervals 的 overlap、nearest、merge、coverage、complement、subtract。Streaming、cloud-native，是更快的 bioframe 替代方案。
license: https://github.com/biodatageeks/polars-bio/blob/main/LICENSE
metadata:
    skill-author: K-Dense Inc.
---

# polars-bio

## 概览

polars-bio 是一个高性能 Python library，用于 genomic interval operations 和 bioinformatics file I/O，构建在 Polars、Apache Arrow 和 Apache DataFusion 之上。它提供熟悉的 DataFrame-centric API，用于 interval arithmetic（overlap、nearest、merge、coverage、complement、subtract）以及读写常见 bioinformatics formats（BED、VCF、BAM、CRAM、GFF/GTF、FASTA、FASTQ）。

核心价值：
- 在真实 genomic benchmarks 上比 bioframe **快 6-38 倍**
- 通过 DataFusion 为 large genomes 支持 **streaming/out-of-core**
- 支持带 predicate pushdown 的 **cloud-native** file I/O（S3、GCS、Azure）
- **两种 API 风格**：functional（`pb.overlap(df1, df2)`）和 method-chaining（`df1.lazy().pb.overlap(df2)`）
- 通过 DataFusion SQL engine 为 genomic data 提供 **SQL interface**

## 何时使用此 Skill

在以下场景使用此 skill：
- 执行 genomic interval operations（overlap、nearest、merge、coverage、complement、subtract）
- 读写 bioinformatics file formats（BED、VCF、BAM、CRAM、GFF/GTF、FASTA、FASTQ）
- 处理无法放入内存的 large genomic datasets（streaming mode）
- 在 genomic data files 上运行 SQL queries
- 从 bioframe 迁移到更快的替代方案
- 从 BAM/CRAM files 计算 read depth/pileup
- 处理包含 genomic intervals 的 Polars DataFrames

## 快速开始

### 安装

```bash
pip install polars-bio
# or
uv pip install polars-bio
```

如需 pandas compatibility：
```bash
pip install polars-bio[pandas]
```

### 基础 Overlap 示例

```python
import polars as pl
import polars_bio as pb

# Create two interval DataFrames
df1 = pl.DataFrame({
    "chrom": ["chr1", "chr1", "chr1"],
    "start": [1, 5, 22],
    "end":   [6, 9, 30],
})

df2 = pl.DataFrame({
    "chrom": ["chr1", "chr1"],
    "start": [3, 25],
    "end":   [8, 28],
})

# Functional API (returns LazyFrame by default)
result = pb.overlap(df1, df2)
result_df = result.collect()

# Get a DataFrame directly
result_df = pb.overlap(df1, df2, output_type="polars.DataFrame")

# Method-chaining API (via .pb accessor on LazyFrame)
result = df1.lazy().pb.overlap(df2)
result_df = result.collect()
```

### 读取 BED File

```python
import polars_bio as pb

# Eager read (loads entire file)
df = pb.read_bed("regions.bed")

# Lazy scan (streaming, for large files)
lf = pb.scan_bed("regions.bed")
result = lf.collect()
```

## 核心能力

### 1. Genomic Interval Operations

polars-bio 为 genomic range arithmetic 提供 8 个核心 interval operations。所有 operations 都接受带 `chrom`、`start`、`end` columns（可配置）的 Polars DataFrames。所有 operations 默认返回 `LazyFrame`（如需 eager results，使用 `output_type="polars.DataFrame"`）。

**Operations：**
- `overlap` / `count_overlaps` - 查找或计数两个集合之间的 overlapping intervals
- `nearest` - 查找 nearest intervals（可配置 `k`、`overlap`、`distance` params）
- `merge` - 合并集合内 overlapping/bookended intervals
- `cluster` - 为 overlapping intervals 分配 cluster IDs
- `coverage` - 计算 per-interval coverage counts（two-input operation）
- `complement` - 查找 genome 内 intervals 之间的 gaps
- `subtract` - 移除与另一集合重叠的 interval portions

**示例：**
```python
import polars_bio as pb

# Find overlapping intervals (returns LazyFrame)
result = pb.overlap(df1, df2, suffixes=("_1", "_2"))

# Count overlaps per interval
counts = pb.count_overlaps(df1, df2)

# Merge overlapping intervals
merged = pb.merge(df1)

# Find nearest intervals
nearest = pb.nearest(df1, df2)

# Collect any LazyFrame result to DataFrame
result_df = result.collect()
```

**参考：** 参见 `references/interval_operations.md`，了解所有 operations、parameters、output schemas 和 performance considerations 的详细文档。

### 2. Bioinformatics File I/O

使用 `read_*`、`scan_*`、`write_*` 和 `sink_*` functions 读写常见 bioinformatics formats。支持 cloud storage（S3、GCS、Azure）和 compression（GZIP、BGZF）。

**Supported formats：**
- **BED** - Genomic intervals（`read_bed`、`scan_bed`、通过 generic `write_*`）
- **VCF** - Genetic variants（`read_vcf`、`scan_vcf`、`write_vcf`、`sink_vcf`）
- **BAM** - Aligned reads（`read_bam`、`scan_bam`、`write_bam`、`sink_bam`）
- **CRAM** - Compressed alignments（`read_cram`、`scan_cram`、`write_cram`、`sink_cram`）
- **GFF** - Gene annotations（`read_gff`、`scan_gff`）
- **GTF** - Gene annotations（`read_gtf`、`scan_gtf`）
- **FASTA** - Reference sequences（`read_fasta`、`scan_fasta`）
- **FASTQ** - Sequencing reads（`read_fastq`、`scan_fastq`、`write_fastq`、`sink_fastq`）
- **SAM** - Text alignments（`read_sam`、`scan_sam`、`write_sam`、`sink_sam`）
- **Hi-C pairs** - Chromatin contacts（`read_pairs`、`scan_pairs`）

**示例：**
```python
import polars_bio as pb

# Read VCF file
variants = pb.read_vcf("samples.vcf.gz")

# Lazy scan BAM file (streaming)
alignments = pb.scan_bam("aligned.bam")

# Read GFF annotations
genes = pb.read_gff("annotations.gff3")

# Cloud storage (individual params, not a dict)
df = pb.read_bed("s3://bucket/regions.bed",
                 allow_anonymous=True)
```

**参考：** 参见 `references/file_io.md`，了解每种 format 的 column schemas、parameters、cloud storage options 和 compression support。

### 3. SQL Data Processing

将 bioinformatics files 注册为 tables，并用 DataFusion SQL 查询它们。结合 SQL 能力与 polars-bio 的 genomic-aware readers。

```python
import polars as pl
import polars_bio as pb

# Register files as SQL tables (path first, name= keyword)
pb.register_vcf("samples.vcf.gz", name="variants")
pb.register_bed("target_regions.bed", name="regions")

# Query with SQL (returns LazyFrame)
result = pb.sql("SELECT chrom, start, end, ref, alt FROM variants WHERE qual > 30")
result_df = result.collect()

# Register a Polars DataFrame as a SQL table
pb.from_polars("my_intervals", df)
result = pb.sql("SELECT * FROM my_intervals WHERE chrom = 'chr1'").collect()
```

**参考：** 参见 `references/sql_processing.md`，了解 register functions、SQL syntax 和 examples。

### 4. Pileup Operations

使用 CIGAR-aware depth calculation 从 BAM/CRAM files 计算 per-base read depth。

```python
import polars_bio as pb

# Compute depth across a BAM file
depth_lf = pb.depth("aligned.bam")
depth_df = depth_lf.collect()

# With quality filter
depth_lf = pb.depth("aligned.bam", min_mapping_quality=20)
```

**参考：** 参见 `references/pileup_operations.md`，了解 parameters 和 integration patterns。

## 关键概念

### Coordinate Systems

polars-bio 默认使用 **1-based** coordinates（genomic convention）。可全局更改：

```python
import polars_bio as pb

# Switch to 0-based coordinates
pb.set_option("coordinate_system", "0-based")

# Switch back to 1-based (default)
pb.set_option("coordinate_system", "1-based")
```

I/O functions 也接受 `use_zero_based`，用于在生成的 DataFrame 上设置 coordinate metadata：

```python
# Read BED with explicit 0-based metadata
df = pb.read_bed("regions.bed", use_zero_based=True)
```

**重要：** BED files 在文件格式中始终是 0-based half-open。polars-bio 读取 BED files 时会自动处理转换。Coordinate metadata 由 I/O functions 附加到 DataFrames，并通过 operations 传播。

### 两种 API 风格

**Functional API** - standalone functions，显式 inputs：
```python
result = pb.overlap(df1, df2, suffixes=("_1", "_2"))
merged = pb.merge(df)
```

**Method-chaining API** - 通过 **LazyFrames**（不是 DataFrames）上的 `.pb` accessor：
```python
result = df1.lazy().pb.overlap(df2)
merged = df.lazy().pb.merge()
```

**重要：** 用于 interval operations 的 `.pb` accessor 只在 `LazyFrame` 上可用。在 `DataFrame` 上，`.pb` 只提供 write operations（`write_bam`、`write_vcf` 等）。

Method-chaining 可实现 fluent pipelines：
```python
# Chain interval operations (note: overlap outputs suffixed columns,
# so rename before merge which expects chrom/start/end)
result = (
    df1.lazy()
    .pb.overlap(df2)
    .filter(pl.col("start_2") > 1000)
    .select(
        pl.col("chrom_1").alias("chrom"),
        pl.col("start_1").alias("start"),
        pl.col("end_1").alias("end"),
    )
    .pb.merge()
    .collect()
)
```

### Probe-Build Architecture

对于 two-input operations（overlap、nearest、count_overlaps、coverage），polars-bio 使用 probe-build join strategy：
- **第一个** DataFrame 是 **probe**（被迭代）
- **第二个** DataFrame 是 **build**（为查找建立索引）

为了获得最佳性能，将较大的 DataFrame 作为第一个参数（probe），较小的作为第二个参数（build）。

### Column Conventions

默认情况下，polars-bio 期望 columns 命名为 `chrom`、`start`、`end`。可通过 lists 指定自定义 column names：

```python
result = pb.overlap(
    df1, df2,
    cols1=["chromosome", "begin", "finish"],
    cols2=["chr", "pos_start", "pos_end"],
)
```

### Return Types 与 Collecting Results

所有 interval operations 和 `pb.sql()` 默认返回 **LazyFrame**。使用 `.collect()` 物化 results，或传入 `output_type="polars.DataFrame"` 进行 eager evaluation：

```python
# Lazy (default) - collect when needed
result_lf = pb.overlap(df1, df2)
result_df = result_lf.collect()

# Eager - get DataFrame directly
result_df = pb.overlap(df1, df2, output_type="polars.DataFrame")
```

### Streaming 与 Out-of-Core Processing

对于大于可用 RAM 的 datasets，使用 `scan_*` functions 和 streaming execution：

```python
# Scan files lazily
lf = pb.scan_bed("large_intervals.bed")

# Process with streaming
result = lf.collect(streaming=True)
```

interval operations 默认启用 DataFusion streaming，会按 batches 处理数据，而不将完整 dataset 加载到内存。

## 常见陷阱

1. **DataFrame vs LazyFrame 上的 `.pb` accessor：** Interval operations（overlap、merge 等）只在 `LazyFrame.pb` 上。`DataFrame.pb` 只有 write methods。chaining interval ops 前使用 `.lazy()` 转换。

2. **LazyFrame returns：** 所有 interval operations 和 `pb.sql()` 默认返回 `LazyFrame`。不要忘记 `.collect()`，或使用 `output_type="polars.DataFrame"`。

3. **Column name mismatches：** polars-bio 默认期望 `chrom`、`start`、`end`。如果你的 columns 名称不同，使用 `cols1`/`cols2` parameters（lists）。

4. **Coordinate system metadata：** 手动构建 DataFrames（不是通过 `read_*`/`scan_*`）时，polars-bio 会警告缺少 coordinate metadata。全局使用 `pb.set_option("coordinate_system", "0-based")`，或使用会自动设置 metadata 的 I/O functions。

5. **Probe-build order matters：** 对 overlap、nearest 和 coverage，第一个 DataFrame 会 against 第二个 DataFrame 进行 probe。交换参数会改变哪些 intervals 出现在 left vs right output columns，也可能影响性能。

6. **INT32 position limit：** Genomic positions 以 32-bit integers 存储，将 coordinates 限制在约 21 亿以内。这对所有已知 genomes 都足够，但对 custom coordinate spaces 可能成为问题。

7. **BAM index requirements：** `read_bam` 和 `scan_bam` 要求 BAM 旁边有 `.bai` index file。如果缺失，用 `samtools index` 创建。

8. **Parallel execution 默认关闭：** DataFusion parallelism 默认 1 个 partition。大型 datasets 请启用：
   ```python
   pb.set_option("datafusion.execution.target_partitions", 8)
   ```

9. **CRAM 有独立 functions：** 对 CRAM files 使用 `read_cram`/`scan_cram`/`register_cram`（不是 `read_bam`）。CRAM functions 需要 `reference_path` 参数。

## Best Practices

1. **对 large files 使用 `scan_*`：** 对大于可用 RAM 的文件，优先使用 `scan_bed`、`scan_vcf` 等，而不是 `read_*`。Scan functions 支持 streaming 和 predicate pushdown。

2. **为 large datasets 配置 parallelism：**
   ```python
   import os
   pb.set_option("datafusion.execution.target_partitions", os.cpu_count())
   ```

3. **使用 BGZF compression：** BGZF-compressed files（`.bed.gz`、`.vcf.gz`）支持 parallel block decompression，显著快于普通 GZIP。

4. **尽早选择 columns：** 当只需要特定 columns 时，尽早选择以降低 memory usage：
   ```python
   df = pb.read_vcf("large.vcf.gz").select("chrom", "start", "end", "ref", "alt")
   ```

5. **直接使用 cloud paths：** 将 S3/GCS/Azure URIs 直接传给 read/scan functions，而不是先下载文件：
   ```python
   df = pb.read_bed("s3://my-bucket/regions.bed", allow_anonymous=True)
   ```

6. **单次 operations 优先 functional API，pipelines 优先 method-chaining：** 对 one-off operations 使用 `pb.overlap()`，构建 multi-step pipelines 时使用 `.lazy().pb.overlap()`。

## 资源

### references/

每项主要能力的详细文档：

- **interval_operations.md** - 全部 8 个 interval operations，包含 parameters、examples、output schemas 和 performance tips。genomic range arithmetic 的核心参考。

- **file_io.md** - Supported formats table、per-format column schemas、cloud storage configuration、compression support 和 common parameters。

- **sql_processing.md** - Register functions、DataFusion SQL syntax、SQL 与 interval operations 结合，以及 example queries。

- **pileup_operations.md** - 从 BAM/CRAM files 计算 per-base read depth、parameters，以及与 interval operations 的集成。

- **configuration.md** - Global settings（parallelism、coordinate systems、streaming modes）、logging 和 metadata management。

- **bioframe_migration.md** - Operation mapping table、API differences、performance comparison、migration code examples 和 pandas compatibility mode。
