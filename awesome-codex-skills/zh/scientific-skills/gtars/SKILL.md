---
name: gtars
description: 带 Python bindings 的高性能 Rust genomic interval analysis toolkit。处理 genomic regions、BED files、coverage tracks、overlap detection、ML models tokenization，或 computational genomics 和 machine learning applications 中的 fragment analysis 时使用。
license: Unknown
metadata:
    skill-author: K-Dense Inc.
---

# Gtars：Genomic Tools and Algorithms in Rust

## 概述

Gtars 是一个用于操作、分析和处理 genomic interval data 的高性能 Rust toolkit。它提供面向 overlap detection、coverage analysis、machine learning tokenization 和 reference sequence management 的专用工具。

处理以下内容时使用此 skill：
- Genomic interval files（BED format）
- Genomic regions 之间的 overlap detection
- Coverage track generation（WIG、BigWig）
- Genomic ML preprocessing 和 tokenization
- Single-cell genomics 中的 fragment analysis
- Reference sequence retrieval 和 validation

## 安装

### Python Installation

安装 gtars Python bindings：

```bash
uv pip install gtars
```

### CLI Installation

安装 command-line tools（需要 Rust/Cargo）：

```bash
# Install with all features
cargo install gtars-cli --features "uniwig overlaprs igd bbcache scoring fragsplit"

# Or install specific features only
cargo install gtars-cli --features "uniwig overlaprs"
```

### Rust Library

在 Rust projects 的 Cargo.toml 中添加：

```toml
[dependencies]
gtars = { version = "0.1", features = ["tokenizers", "overlaprs"] }
```

## 核心能力

Gtars 组织为多个 specialized modules，每个 module 聚焦特定 genomic analysis tasks：

### 1. Overlap Detection and IGD Indexing

使用 Integrated Genome Database (IGD) data structure 高效检测 genomic intervals 之间的 overlaps。

**何时使用：**
- 查找 overlapping regulatory elements
- Variant annotation
- 比较 ChIP-seq peaks
- 识别 shared genomic features

**Quick example：**
```python
import gtars

# Build IGD index and query overlaps
igd = gtars.igd.build_index("regions.bed")
overlaps = igd.query("chr1", 1000, 2000)
```

综合 overlap detection documentation 见 `references/overlap.md`。

### 2. Coverage Track Generation

使用 uniwig module 从 sequencing data 生成 coverage tracks。

**何时使用：**
- ATAC-seq accessibility profiles
- ChIP-seq coverage visualization
- RNA-seq read coverage
- Differential coverage analysis

**Quick example：**
```bash
# Generate BigWig coverage track
gtars uniwig generate --input fragments.bed --output coverage.bw --format bigwig
```

详细 coverage analysis workflows 见 `references/coverage.md`。

### 3. Genomic Tokenization

将 genomic regions 转换为 machine learning applications 使用的离散 tokens，尤其适合 genomic data 上的 deep learning models。

**何时使用：**
- Genomic ML models 的 preprocessing
- 与 geniml library 集成
- 创建 position encodings
- 在 genomic sequences 上训练 transformer models

**Quick example：**
```python
from gtars.tokenizers import TreeTokenizer

tokenizer = TreeTokenizer.from_bed_file("training_regions.bed")
token = tokenizer.tokenize("chr1", 1000, 2000)
```

Tokenization documentation 见 `references/tokenizers.md`。

### 4. Reference Sequence Management

按照 GA4GH refget protocol 处理 reference genome sequences 并计算 digests。

**何时使用：**
- 验证 reference genome integrity
- 提取特定 genomic sequences
- 计算 sequence digests
- Cross-reference comparisons

**Quick example：**
```python
# Load reference and extract sequences
store = gtars.RefgetStore.from_fasta("hg38.fa")
sequence = store.get_subsequence("chr1", 1000, 2000)
```

Reference sequence operations 见 `references/refget.md`。

### 5. Fragment Processing

拆分和分析 fragment files，尤其适合 single-cell genomics data。

**何时使用：**
- Processing single-cell ATAC-seq data
- 按 cell barcodes 拆分 fragments
- Cluster-based fragment analysis
- Fragment quality control

**Quick example：**
```bash
# Split fragments by clusters
gtars fragsplit cluster-split --input fragments.tsv --clusters clusters.txt --output-dir ./by_cluster/
```

Fragment processing commands 见 `references/cli.md`。

### 6. Fragment Scoring

根据 reference datasets 为 fragment overlaps 打分。

**何时使用：**
- 评估 fragment enrichment
- 将 experimental data 与 references 比较
- Quality metrics computation
- 跨 samples 批量 scoring

**Quick example：**
```bash
# Score fragments against reference
gtars scoring score --fragments fragments.bed --reference reference.bed --output scores.txt
```

## 常见工作流

### Workflow 1：Peak Overlap Analysis

识别 overlapping genomic features：

```python
import gtars

# Load two region sets
peaks = gtars.RegionSet.from_bed("chip_peaks.bed")
promoters = gtars.RegionSet.from_bed("promoters.bed")

# Find overlaps
overlapping_peaks = peaks.filter_overlapping(promoters)

# Export results
overlapping_peaks.to_bed("peaks_in_promoters.bed")
```

### Workflow 2：Coverage Track Pipeline

生成用于 visualization 的 coverage tracks：

```bash
# Step 1: Generate coverage
gtars uniwig generate --input atac_fragments.bed --output coverage.wig --resolution 10

# Step 2: Convert to BigWig for genome browsers
gtars uniwig generate --input atac_fragments.bed --output coverage.bw --format bigwig
```

### Workflow 3：ML Preprocessing

为 machine learning 准备 genomic data：

```python
from gtars.tokenizers import TreeTokenizer
import gtars

# Step 1: Load training regions
regions = gtars.RegionSet.from_bed("training_peaks.bed")

# Step 2: Create tokenizer
tokenizer = TreeTokenizer.from_bed_file("training_peaks.bed")

# Step 3: Tokenize regions
tokens = [tokenizer.tokenize(r.chromosome, r.start, r.end) for r in regions]

# Step 4: Use tokens in ML pipeline
# (integrate with geniml or custom models)
```

## Python vs CLI Usage

**以下情况使用 Python API：**
- 与 analysis pipelines 集成
- 需要 programmatic control
- 使用 NumPy/Pandas
- 构建 custom workflows

**以下情况使用 CLI：**
- 快速 one-off analyses
- Shell scripting
- Batch processing files
- Prototyping workflows

## 参考文档

综合 module documentation：

- **`references/python-api.md`** - 带 RegionSet operations、NumPy integration 和 data export 的完整 Python API reference
- **`references/overlap.md`** - IGD indexing、overlap detection 和 set operations
- **`references/coverage.md`** - 使用 uniwig 生成 Coverage track
- **`references/tokenizers.md`** - 用于 ML applications 的 Genomic tokenization
- **`references/refget.md`** - Reference sequence management 和 digests
- **`references/cli.md`** - Command-line interface complete reference

## 与 geniml 集成

Gtars 是 geniml Python package 的基础，为 machine learning workflows 提供核心 genomic interval operations。处理 geniml 相关任务时，使用 gtars 进行 data preprocessing 和 tokenization。

## Performance Characteristics

- **Native Rust performance**：快速执行，低 memory overhead
- **Parallel processing**：面向 large datasets 的 multi-threaded operations
- **Memory efficiency**：支持 streaming 和 memory-mapped files
- **Zero-copy operations**：与 NumPy 集成，并尽量减少 data copying

## Data Formats

Gtars 使用标准 genomic formats：

- **BED**：Genomic intervals（3-column 或 extended）
- **WIG/BigWig**：Coverage tracks
- **FASTA**：Reference sequences
- **Fragment TSV**：带 barcodes 的 single-cell fragment files

## Error Handling and Debugging

启用 verbose logging 进行 troubleshooting：

```python
import gtars

# Enable debug logging
gtars.set_log_level("DEBUG")
```

```bash
# CLI verbose mode
gtars --verbose <command>
```
