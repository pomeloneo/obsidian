---
name: scanpy
description: 标准 single-cell RNA-seq analysis pipeline。用于 QC、normalization、dimensionality reduction（PCA/UMAP/t-SNE）、clustering、differential expression 和 visualization。最适合使用成熟 workflow 的 exploratory scRNA-seq analysis。Deep learning models 使用 scvi-tools；data format 问题使用 anndata。
license: BSD-3-Clause
metadata:
    skill-author: K-Dense Inc.
---

# Scanpy: Single-Cell Analysis

## 概述

Scanpy 是一个基于 AnnData 的可扩展 Python toolkit，用于分析 single-cell RNA-seq data。将此 skill 用于完整 single-cell workflows，包括 quality control、normalization、dimensionality reduction、clustering、marker gene identification、visualization 和 trajectory analysis。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 分析 single-cell RNA-seq data（.h5ad、10X、CSV formats）
- 对 scRNA-seq datasets 执行 quality control
- 创建 UMAP、t-SNE 或 PCA visualizations
- 识别 cell clusters 并查找 marker genes
- 基于 gene expression 注释 cell types
- 进行 trajectory inference 或 pseudotime analysis
- 生成 publication-quality single-cell plots

## 快速开始

### Basic Import and Setup

```python
import scanpy as sc
import pandas as pd
import numpy as np

# Configure settings
sc.settings.verbosity = 3
sc.settings.set_figure_params(dpi=80, facecolor='white')
sc.settings.figdir = './figures/'
```

### Loading Data

```python
# From 10X Genomics
adata = sc.read_10x_mtx('path/to/data/')
adata = sc.read_10x_h5('path/to/data.h5')

# From h5ad (AnnData format)
adata = sc.read_h5ad('path/to/data.h5ad')

# From CSV
adata = sc.read_csv('path/to/data.csv')
```

### Understanding AnnData Structure

AnnData object 是 scanpy 的核心数据结构：

```python
adata.X          # Expression matrix (cells × genes)
adata.obs        # Cell metadata (DataFrame)
adata.var        # Gene metadata (DataFrame)
adata.uns        # Unstructured annotations (dict)
adata.obsm       # Multi-dimensional cell data (PCA, UMAP)
adata.raw        # Raw data backup

# Access cell and gene names
adata.obs_names  # Cell barcodes
adata.var_names  # Gene names
```

## Standard Analysis Workflow

### 1. Quality Control

识别并过滤 low-quality cells 和 genes：

```python
# Identify mitochondrial genes
adata.var['mt'] = adata.var_names.str.startswith('MT-')

# Calculate QC metrics
sc.pp.calculate_qc_metrics(adata, qc_vars=['mt'], inplace=True)

# Visualize QC metrics
sc.pl.violin(adata, ['n_genes_by_counts', 'total_counts', 'pct_counts_mt'],
             jitter=0.4, multi_panel=True)

# Filter cells and genes
sc.pp.filter_cells(adata, min_genes=200)
sc.pp.filter_genes(adata, min_cells=3)
adata = adata[adata.obs.pct_counts_mt < 5, :]  # Remove high MT% cells
```

**使用 QC script 进行自动分析：**
```bash
python scripts/qc_analysis.py input_file.h5ad --output filtered.h5ad
```

### 2. Normalization and Preprocessing

```python
# Normalize to 10,000 counts per cell
sc.pp.normalize_total(adata, target_sum=1e4)

# Log-transform
sc.pp.log1p(adata)

# Save raw counts for later
adata.raw = adata

# Identify highly variable genes
sc.pp.highly_variable_genes(adata, n_top_genes=2000)
sc.pl.highly_variable_genes(adata)

# Subset to highly variable genes
adata = adata[:, adata.var.highly_variable]

# Regress out unwanted variation
sc.pp.regress_out(adata, ['total_counts', 'pct_counts_mt'])

# Scale data
sc.pp.scale(adata, max_value=10)
```

### 3. Dimensionality Reduction

```python
# PCA
sc.tl.pca(adata, svd_solver='arpack')
sc.pl.pca_variance_ratio(adata, log=True)  # Check elbow plot

# Compute neighborhood graph
sc.pp.neighbors(adata, n_neighbors=10, n_pcs=40)

# UMAP for visualization
sc.tl.umap(adata)
sc.pl.umap(adata, color='leiden')

# Alternative: t-SNE
sc.tl.tsne(adata)
```

### 4. Clustering

```python
# Leiden clustering (recommended)
sc.tl.leiden(adata, resolution=0.5)
sc.pl.umap(adata, color='leiden', legend_loc='on data')

# Try multiple resolutions to find optimal granularity
for res in [0.3, 0.5, 0.8, 1.0]:
    sc.tl.leiden(adata, resolution=res, key_added=f'leiden_{res}')
```

### 5. Marker Gene Identification

```python
# Find marker genes for each cluster
sc.tl.rank_genes_groups(adata, 'leiden', method='wilcoxon')

# Visualize results
sc.pl.rank_genes_groups(adata, n_genes=25, sharey=False)
sc.pl.rank_genes_groups_heatmap(adata, n_genes=10)
sc.pl.rank_genes_groups_dotplot(adata, n_genes=5)

# Get results as DataFrame
markers = sc.get.rank_genes_groups_df(adata, group='0')
```

### 6. Cell Type Annotation

```python
# Define marker genes for known cell types
marker_genes = ['CD3D', 'CD14', 'MS4A1', 'NKG7', 'FCGR3A']

# Visualize markers
sc.pl.umap(adata, color=marker_genes, use_raw=True)
sc.pl.dotplot(adata, var_names=marker_genes, groupby='leiden')

# Manual annotation
cluster_to_celltype = {
    '0': 'CD4 T cells',
    '1': 'CD14+ Monocytes',
    '2': 'B cells',
    '3': 'CD8 T cells',
}
adata.obs['cell_type'] = adata.obs['leiden'].map(cluster_to_celltype)

# Visualize annotated types
sc.pl.umap(adata, color='cell_type', legend_loc='on data')
```

### 7. Save Results

```python
# Save processed data
adata.write('results/processed_data.h5ad')

# Export metadata
adata.obs.to_csv('results/cell_metadata.csv')
adata.var.to_csv('results/gene_metadata.csv')
```

## Common Tasks

### Creating Publication-Quality Plots

```python
# Set high-quality defaults
sc.settings.set_figure_params(dpi=300, frameon=False, figsize=(5, 5))
sc.settings.file_format_figs = 'pdf'

# UMAP with custom styling
sc.pl.umap(adata, color='cell_type',
           palette='Set2',
           legend_loc='on data',
           legend_fontsize=12,
           legend_fontoutline=2,
           frameon=False,
           save='_publication.pdf')

# Heatmap of marker genes
sc.pl.heatmap(adata, var_names=genes, groupby='cell_type',
              swap_axes=True, show_gene_labels=True,
              save='_markers.pdf')

# Dot plot
sc.pl.dotplot(adata, var_names=genes, groupby='cell_type',
              save='_dotplot.pdf')
```

完整 visualization examples 见 `references/plotting_guide.md`。

### Trajectory Inference

```python
# PAGA (Partition-based graph abstraction)
sc.tl.paga(adata, groups='leiden')
sc.pl.paga(adata, color='leiden')

# Diffusion pseudotime
adata.uns['iroot'] = np.flatnonzero(adata.obs['leiden'] == '0')[0]
sc.tl.dpt(adata)
sc.pl.umap(adata, color='dpt_pseudotime')
```

### Differential Expression Between Conditions

```python
# Compare treated vs control within cell types
adata_subset = adata[adata.obs['cell_type'] == 'T cells']
sc.tl.rank_genes_groups(adata_subset, groupby='condition',
                         groups=['treated'], reference='control')
sc.pl.rank_genes_groups(adata_subset, groups=['treated'])
```

### Gene Set Scoring

```python
# Score cells for gene set expression
gene_set = ['CD3D', 'CD3E', 'CD3G']
sc.tl.score_genes(adata, gene_set, score_name='T_cell_score')
sc.pl.umap(adata, color='T_cell_score')
```

### Batch Correction

```python
# ComBat batch correction
sc.pp.combat(adata, key='batch')

# Alternative: use Harmony or scVI (separate packages)
```

## 需要调整的关键参数

### Quality Control
- `min_genes`：每个 cell 的 minimum genes（通常 200-500）
- `min_cells`：每个 gene 的 minimum cells（通常 3-10）
- `pct_counts_mt`：Mitochondrial threshold（通常 5-20%）

### Normalization
- `target_sum`：每个 cell 的 target counts（默认 1e4）

### Feature Selection
- `n_top_genes`：HVGs 数量（通常 2000-3000）
- `min_mean`, `max_mean`, `min_disp`：HVG selection parameters

### Dimensionality Reduction
- `n_pcs`：Principal components 数量（检查 variance ratio plot）
- `n_neighbors`：Neighbors 数量（通常 10-30）

### Clustering
- `resolution`：Clustering granularity（0.4-1.2，越高 = clusters 越多）

## 常见陷阱和 Best Practices

1. **始终保存 raw counts**：过滤 genes 前设置 `adata.raw = adata`
2. **仔细检查 QC plots**：根据 dataset quality 调整 thresholds
3. **优先使用 Leiden 而不是 Louvain**：效率更高，结果更好
4. **尝试多个 clustering resolutions**：找到 optimal granularity
5. **验证 cell type annotations**：使用多个 marker genes
6. **Gene expression plots 使用 `use_raw=True`**：显示 original counts
7. **检查 PCA variance ratio**：确定最佳 PCs 数量
8. **保存 intermediate results**：长 workflow 可能中途失败

## Bundled Resources

### scripts/qc_analysis.py
自动 quality control script，可计算 metrics、生成 plots 并过滤 data：

```bash
python scripts/qc_analysis.py input.h5ad --output filtered.h5ad \
    --mt-threshold 5 --min-genes 200 --min-cells 3
```

### references/standard_workflow.md
完整 step-by-step workflow，包含以下内容的详细解释和 code examples：
- Data loading and setup
- 带 visualization 的 quality control
- Normalization and scaling
- Feature selection
- Dimensionality reduction（PCA、UMAP、t-SNE）
- Clustering（Leiden、Louvain）
- Marker gene identification
- Cell type annotation
- Trajectory inference
- Differential expression

从头进行完整分析时阅读此 reference。

### references/api_reference.md
按 module 组织的 scanpy functions 快速 reference guide：
- Reading/writing data（`sc.read_*`、`adata.write_*`）
- Preprocessing（`sc.pp.*`）
- Tools（`sc.tl.*`）
- Plotting（`sc.pl.*`）
- AnnData structure and manipulation
- Settings and utilities

用于快速查找 function signatures 和 common parameters。

### references/plotting_guide.md
完整 visualization guide，包括：
- Quality control plots
- Dimensionality reduction visualizations
- Clustering visualizations
- Marker gene plots（heatmaps、dot plots、violin plots）
- Trajectory and pseudotime plots
- Publication-quality customization
- Multi-panel figures
- Color palettes and styling

创建 publication-ready figures 时参考此文档。

### assets/analysis_template.py
完整 analysis template，提供从 data loading 到 cell type annotation 的完整 workflow。为新分析复制并定制此模板：

```bash
cp assets/analysis_template.py my_analysis.py
# Edit parameters and run
python my_analysis.py
```

该模板包含所有标准步骤，并提供可配置参数和 helpful comments。

## 其他资源

- **Official scanpy documentation**：https://scanpy.readthedocs.io/
- **Scanpy tutorials**：https://scanpy-tutorials.readthedocs.io/
- **scverse ecosystem**：https://scverse.org/（相关工具：squidpy、scvi-tools、cellrank）
- **Best practices**：Luecken & Theis (2019) "Current best practices in single-cell RNA-seq"

## 高效分析建议

1. **从 template 开始**：使用 `assets/analysis_template.py` 作为起点
2. **先运行 QC script**：使用 `scripts/qc_analysis.py` 进行 initial filtering
3. **按需参考 references**：将 workflow 和 API references 加载到 context
4. **迭代 clustering**：尝试多个 resolutions 和 visualization methods
5. **进行 biological validation**：检查 marker genes 是否符合预期 cell types
6. **记录 parameters**：记录 QC thresholds 和 analysis settings
7. **保存 checkpoints**：在关键步骤写入 intermediate results
