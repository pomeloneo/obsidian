---
name: geniml
description: 当处理 genomic interval data（BED files）用于 machine learning 任务时，应使用此 skill。用于训练 region embeddings（Region2Vec、BEDspace）、single-cell ATAC-seq analysis（scEmbed）、构建 consensus peaks（universes），或任何基于 ML 的 genomic regions 分析。适用于 BED file collections、scATAC-seq data、chromatin accessibility datasets 和 region-based genomic feature learning。
license: BSD-2-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# Geniml：Genomic Interval Machine Learning

## 概述

Geniml 是一个用于在 BED files 的 genomic interval data 上构建 machine learning models 的 Python package。它提供无监督方法，用于学习 genomic regions、single cells 和 metadata labels 的 embeddings，从而支持 similarity searches、clustering 和 downstream ML tasks。

## 安装

使用 uv 安装 geniml：

```bash
uv pip install geniml
```

对于 ML dependencies（PyTorch 等）：

```bash
uv pip install 'geniml[ml]'
```

从 GitHub 安装 development version：

```bash
uv pip install git+https://github.com/databio/geniml.git
```

## 核心能力

Geniml 提供五项主要能力，每项都在专门 reference files 中详述：

### 1. Region2Vec：Genomic Region Embeddings

使用 word2vec-style learning 训练 genomic regions 的无监督 embeddings。

**用于：** BED files 的 dimensionality reduction、region similarity analysis、下游 ML 的 feature vectors。

**工作流：**
1. 使用 universe reference 对 BED files 进行 tokenization
2. 在 tokens 上训练 Region2Vec model
3. 为 regions 生成 embeddings

**参考：** 详细 workflow、parameters 和 examples 见 `references/region2vec.md`。

### 2. BEDspace：Joint Region and Metadata Embeddings

使用 StarSpace 为 region sets 和 metadata labels 训练 shared embeddings。

**用于：** Metadata-aware searches、cross-modal queries（region→label 或 label→region）、genomic content 和 experimental conditions 的联合分析。

**工作流：**
1. 预处理 regions 和 metadata
2. 训练 BEDspace model
3. 计算 distances
4. 跨 regions 和 labels 查询

**参考：** 详细 workflow、search types 和 examples 见 `references/bedspace.md`。

### 3. scEmbed：Single-Cell Chromatin Accessibility Embeddings

在 single-cell ATAC-seq data 上训练 Region2Vec models，用于 cell-level embeddings。

**用于：** scATAC-seq clustering、cell-type annotation、single cells 的 dimensionality reduction、与 scanpy workflows 集成。

**工作流：**
1. 准备带 peak coordinates 的 AnnData
2. 预先 tokenize cells
3. 训练 scEmbed model
4. 生成 cell embeddings
5. 用 scanpy cluster 和 visualize

**参考：** 详细 workflow、parameters 和 examples 见 `references/scembed.md`。

### 4. Consensus Peaks：Universe Building

使用多种 statistical methods 从 BED file collections 构建 reference peak sets（universes）。

**用于：** 创建 tokenization references、跨 datasets 标准化 regions、用统计严谨性定义 consensus features。

**工作流：**
1. 合并 BED files
2. 生成 coverage tracks
3. 使用 CC、CCF、ML 或 HMM method 构建 universe

**方法：**
- **CC (Coverage Cutoff)**：简单 threshold-based
- **CCF (Coverage Cutoff Flexible)**：边界 confidence intervals
- **ML (Maximum Likelihood)**：positions 的 probabilistic modeling
- **HMM (Hidden Markov Model)**：复杂 state modeling

**参考：** method comparison、parameters 和 examples 见 `references/consensus_peaks.md`。

### 5. Utilities：Supporting Tools

用于 caching、randomization、evaluation 和 search 的附加工具。

**可用 utilities：**
- **BBClient**：BED file caching，用于重复访问
- **BEDshift**：保留 genomic context 的 randomization
- **Evaluation**：embedding quality metrics（silhouette、Davies-Bouldin 等）
- **Tokenization**：Region tokenization utilities（hard、soft、universe-based）
- **Text2BedNN**：用于 genomic queries 的 neural search backends

**参考：** 每个 utility 的详细用法见 `references/utilities.md`。

## 常见工作流

### 基本 Region Embedding Pipeline

```python
from geniml.tokenization import hard_tokenization
from geniml.region2vec import region2vec
from geniml.evaluation import evaluate_embeddings

# Step 1: Tokenize BED files
hard_tokenization(
    src_folder='bed_files/',
    dst_folder='tokens/',
    universe_file='universe.bed',
    p_value_threshold=1e-9
)

# Step 2: Train Region2Vec
region2vec(
    token_folder='tokens/',
    save_dir='model/',
    num_shufflings=1000,
    embedding_dim=100
)

# Step 3: Evaluate
metrics = evaluate_embeddings(
    embeddings_file='model/embeddings.npy',
    labels_file='metadata.csv'
)
```

### scATAC-seq Analysis Pipeline

```python
import scanpy as sc
from geniml.scembed import ScEmbed
from geniml.io import tokenize_cells

# Step 1: Load data
adata = sc.read_h5ad('scatac_data.h5ad')

# Step 2: Tokenize cells
tokenize_cells(
    adata='scatac_data.h5ad',
    universe_file='universe.bed',
    output='tokens.parquet'
)

# Step 3: Train scEmbed
model = ScEmbed(embedding_dim=100)
model.train(dataset='tokens.parquet', epochs=100)

# Step 4: Generate embeddings
embeddings = model.encode(adata)
adata.obsm['scembed_X'] = embeddings

# Step 5: Cluster with scanpy
sc.pp.neighbors(adata, use_rep='scembed_X')
sc.tl.leiden(adata)
sc.tl.umap(adata)
```

### Universe Building and Evaluation

```bash
# Generate coverage
cat bed_files/*.bed > combined.bed
uniwig -m 25 combined.bed chrom.sizes coverage/

# Build universe with coverage cutoff
geniml universe build cc \
  --coverage-folder coverage/ \
  --output-file universe.bed \
  --cutoff 5 \
  --merge 100 \
  --filter-size 50

# Evaluate universe quality
geniml universe evaluate \
  --universe universe.bed \
  --coverage-folder coverage/ \
  --bed-folder bed_files/
```

## CLI Reference

Geniml 为主要操作提供 command-line interfaces：

```bash
# Region2Vec training
geniml region2vec --token-folder tokens/ --save-dir model/ --num-shuffle 1000

# BEDspace preprocessing
geniml bedspace preprocess --input regions/ --metadata labels.csv --universe universe.bed

# BEDspace training
geniml bedspace train --input preprocessed.txt --output model/ --dim 100

# BEDspace search
geniml bedspace search -t r2l -d distances.pkl -q query.bed -n 10

# Universe building
geniml universe build cc --coverage-folder coverage/ --output universe.bed --cutoff 5

# BEDshift randomization
geniml bedshift --input peaks.bed --genome hg38 --preserve-chrom --iterations 100
```

## 何时使用哪个工具

**以下情况使用 Region2Vec：**
- 处理 bulk genomic data（ChIP-seq、ATAC-seq 等）
- 需要不带 metadata 的 unsupervised embeddings
- 跨 experiments 比较 region sets
- 为 downstream supervised learning 构建 features

**以下情况使用 BEDspace：**
- 有 metadata labels（cell types、tissues、conditions）
- 需要按 metadata 查询 regions 或反向查询
- 想要 regions 和 labels 的 joint embedding space
- 构建 searchable genomic databases

**以下情况使用 scEmbed：**
- 分析 single-cell ATAC-seq data
- 按 chromatin accessibility 聚类 cells
- 从 scATAC-seq 注释 cell types
- 需要与 scanpy 集成

**以下情况使用 Universe Building：**
- 需要用于 tokenization 的 reference peak sets
- 将多个 experiments 合并为 consensus
- 想要 statistically rigorous region definitions
- 为项目构建 standard references

**以下情况使用 Utilities：**
- 需要缓存 remote BED files（BBClient）
- 生成用于统计的 null models（BEDshift）
- 评估 embedding quality（Evaluation）
- 构建 search interfaces（Text2BedNN）

## 最佳实践

### General Guidelines

- **Universe quality 很关键**：投入时间构建 comprehensive、well-constructed universes
- **Tokenization validation**：训练前检查 coverage（理想 >80%）
- **Parameter tuning**：尝试不同 embedding dimensions、learning rates 和 training epochs
- **Evaluation**：始终用 multiple metrics 和 visualizations 验证 embeddings
- **Documentation**：记录 parameters 和 random seeds 以保证 reproducibility

### Performance Considerations

- **Pre-tokenization**：对于 scEmbed，始终预先 tokenize cells 以加快训练
- **Memory management**：大型 datasets 可能需要 batch processing 或 downsampling
- **Computational resources**：ML/HMM universe methods 计算密集
- **Model caching**：使用 BBClient 避免重复 downloads

### Integration Patterns

- **With scanpy**：scEmbed embeddings 可作为 `adata.obsm` entries 无缝集成
- **With BEDbase**：使用 BBClient 访问 remote BED repositories
- **With Hugging Face**：导出 trained models 以便 sharing 和 reproducibility
- **With R**：使用 reticulate 进行 R integration（见 utilities reference）

## 相关项目

Geniml 是 BEDbase ecosystem 的一部分：

- **BEDbase**：genomic regions 的统一平台
- **BEDboss**：BED files processing pipeline
- **Gtars**：Genomic tools and utilities
- **BBClient**：BEDbase repositories 的 client

## 其他资源

- **Documentation**: https://docs.bedbase.org/geniml/
- **GitHub**: https://github.com/databio/geniml
- **Pre-trained models**: Available on Hugging Face (databio organization)
- **Publications**: Cited in documentation for methodological details

## 故障排除

**"Tokenization coverage too low"：**
- 检查 universe quality 和 completeness
- 调整 p-value threshold（尝试 1e-6，而不是 1e-9）
- 确保 universe 匹配 genome assembly

**"Training not converging"：**
- 调整 learning rate（尝试 0.01-0.05 范围）
- 增加 training epochs
- 检查 data quality 和 preprocessing

**"Out of memory errors"：**
- 减小 scEmbed 的 batch size
- 分 chunks 处理数据
- 对 single-cell data 使用 pre-tokenization

**"StarSpace not found"（BEDspace）：**
- 单独安装 StarSpace：https://github.com/facebookresearch/StarSpace
- 正确设置 `--path-to-starspace` 参数

如需详细 troubleshooting 和 method-specific issues，请查阅对应 reference file。
