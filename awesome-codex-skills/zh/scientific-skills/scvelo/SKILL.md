---
name: scvelo
description: 使用 scVelo 进行 RNA velocity 分析。从 unspliced/spliced mRNA dynamics 估计细胞状态转变，推断轨迹方向，计算 latent time，并在 single-cell RNA-seq 数据中识别 driver genes。作为 Scanpy/scVI-tools 的 trajectory inference 补充。
license: BSD-3-Clause
metadata:
    skill-author: Kuan-lin Huang
---

# scVelo — RNA velocity 分析

## 概述

scVelo 是 single-cell RNA-seq 数据中进行 RNA velocity 分析的领先 Python package。它通过建模 mRNA splicing kinetics 推断细胞状态转变，使用 unspliced（pre-mRNA）与 spliced（mature mRNA）abundances 的比例判断每个 cell 中某个 gene 是上调还是下调。这允许在不需要 time-course data 的情况下重建发育轨迹并识别 cell fate decisions。

**安装：** `pip install scvelo`

**关键资源：**
- 文档: https://scvelo.readthedocs.io/
- GitHub: https://github.com/theislab/scvelo
- 论文: Bergen et al. (2020) Nature Biotechnology. PMID: 32747759

## 何时使用此技能

在以下情况使用 scVelo：

- **从 snapshot data 进行 trajectory inference**：判断 cells 正在向哪个方向 differentiation
- **Cell fate prediction**：识别 progenitor cells 及其 downstream fates
- **Driver gene identification**：查找 dynamics 最能解释观测轨迹的 genes
- **Developmental biology**：建模 hematopoiesis、neurogenesis、epithelial-to-mesenchymal transitions
- **Latent time estimation**：沿由 splicing dynamics 推导出的 pseudotime 排序 cells
- **Scanpy 补充**：为 UMAP embeddings 添加方向信息

## 前提条件

scVelo 需要 **unspliced** 和 **spliced** RNA 的 count matrices。这些数据由以下工具生成：
1. **STARsolo** 或 **kallisto|bustools**，使用 `lamanno` mode
2. **velocyto** CLI：`velocyto run10x` / `velocyto run`
3. **alevin-fry** / **simpleaf**，带 spliced/unspliced output

数据存储在带有 `layers["spliced"]` 和 `layers["unspliced"]` 的 `AnnData` object 中。

## 标准 RNA velocity 工作流

### 1. 设置和数据加载

```python
import scvelo as scv
import scanpy as sc
import numpy as np
import matplotlib.pyplot as plt

# Configure settings
scv.settings.verbosity = 3       # Show computation steps
scv.settings.presenter_view = True
scv.settings.set_figure_params('scvelo')

# Load data (AnnData with spliced/unspliced layers)
# Option A: Load from loom (velocyto output)
adata = scv.read("cellranger_output.loom", cache=True)

# Option B: Merge velocyto loom with Scanpy-processed AnnData
adata_processed = sc.read_h5ad("processed.h5ad")  # Has UMAP, clusters
adata_velocity = scv.read("velocyto.loom")
adata = scv.utils.merge(adata_processed, adata_velocity)

# Verify layers
print(adata)
# obs × var: N × G
# layers: 'spliced', 'unspliced' (required)
# obsm['X_umap'] (required for visualization)
```

### 2. 预处理

```python
# Filter and normalize (follows Scanpy conventions)
scv.pp.filter_and_normalize(
    adata,
    min_shared_counts=20,   # Minimum counts in spliced+unspliced
    n_top_genes=2000        # Top highly variable genes
)

# Compute first and second order moments (means and variances)
# knn_connectivities must be computed first
sc.pp.neighbors(adata, n_neighbors=30, n_pcs=30)
scv.pp.moments(
    adata,
    n_pcs=30,
    n_neighbors=30
)
```

### 3. Velocity 估计 — stochastic model

Stochastic model 速度快，适合探索性分析：

```python
# Stochastic velocity (faster, less accurate)
scv.tl.velocity(adata, mode='stochastic')
scv.tl.velocity_graph(adata)

# Visualize
scv.pl.velocity_embedding_stream(
    adata,
    basis='umap',
    color='leiden',
    title="RNA Velocity (Stochastic)"
)
```

### 4. Velocity 估计 — dynamical model（推荐）

Dynamical model 拟合完整 splicing kinetics，准确性更高：

```python
# Recover dynamics (computationally intensive; ~10-30 min for 10K cells)
scv.tl.recover_dynamics(adata, n_jobs=4)

# Compute velocity from dynamical model
scv.tl.velocity(adata, mode='dynamical')
scv.tl.velocity_graph(adata)
```

### 5. Latent time（潜在时间）

Dynamical model 可计算共享 latent time（pseudotime）：

```python
# Compute latent time
scv.tl.latent_time(adata)

# Visualize latent time on UMAP
scv.pl.scatter(
    adata,
    color='latent_time',
    color_map='gnuplot',
    size=80,
    title='Latent time'
)

# Identify top genes ordered by latent time
top_genes = adata.var['fit_likelihood'].sort_values(ascending=False).index[:300]
scv.pl.heatmap(
    adata,
    var_names=top_genes,
    sortby='latent_time',
    col_color='leiden',
    n_convolve=100
)
```

### 6. Driver gene 分析

```python
# Identify genes with highest velocity fit
scv.tl.rank_velocity_genes(adata, groupby='leiden', min_corr=0.3)
df = scv.DataFrame(adata.uns['rank_velocity_genes']['names'])
print(df.head(10))

# Speed and coherence
scv.tl.velocity_confidence(adata)
scv.pl.scatter(
    adata,
    c=['velocity_length', 'velocity_confidence'],
    cmap='coolwarm',
    perc=[5, 95]
)

# Phase portraits for specific genes
scv.pl.velocity(adata, ['Cpe', 'Gnao1', 'Ins2'],
               ncols=3, figsize=(16, 4))
```

### 7. Velocity arrows 和 pseudotime

```python
# Arrow plot on UMAP
scv.pl.velocity_embedding(
    adata,
    arrow_length=3,
    arrow_size=2,
    color='leiden',
    basis='umap'
)

# Stream plot (cleaner visualization)
scv.pl.velocity_embedding_stream(
    adata,
    basis='umap',
    color='leiden',
    smooth=0.8,
    min_mass=4
)

# Velocity pseudotime (alternative to latent time)
scv.tl.velocity_pseudotime(adata)
scv.pl.scatter(adata, color='velocity_pseudotime', cmap='gnuplot')
```

### 8. PAGA trajectory graph

```python
# PAGA graph with velocity-informed transitions
scv.tl.paga(adata, groups='leiden')
df = scv.get_df(adata, 'paga/transitions_confidence', precision=2).T
df.style.background_gradient(cmap='Blues').format('{:.2g}')

# Plot PAGA with velocity
scv.pl.paga(
    adata,
    basis='umap',
    size=50,
    alpha=0.1,
    min_edge_width=2,
    node_size_scale=1.5
)
```

## 完整工作流脚本

```python
import scvelo as scv
import scanpy as sc

def run_rna_velocity(adata, n_top_genes=2000, mode='dynamical', n_jobs=4):
    """
    Complete RNA velocity workflow.

    Args:
        adata: AnnData with 'spliced' and 'unspliced' layers, UMAP in obsm
        n_top_genes: Number of top HVGs for velocity
        mode: 'stochastic' (fast) or 'dynamical' (accurate)
        n_jobs: Parallel jobs for dynamical model

    Returns:
        Processed AnnData with velocity information
    """
    scv.settings.verbosity = 2

    # 1. Preprocessing
    scv.pp.filter_and_normalize(adata, min_shared_counts=20, n_top_genes=n_top_genes)

    if 'neighbors' not in adata.uns:
        sc.pp.neighbors(adata, n_neighbors=30)

    scv.pp.moments(adata, n_pcs=30, n_neighbors=30)

    # 2. Velocity estimation
    if mode == 'dynamical':
        scv.tl.recover_dynamics(adata, n_jobs=n_jobs)

    scv.tl.velocity(adata, mode=mode)
    scv.tl.velocity_graph(adata)

    # 3. Downstream analyses
    if mode == 'dynamical':
        scv.tl.latent_time(adata)
        scv.tl.rank_velocity_genes(adata, groupby='leiden', min_corr=0.3)

    scv.tl.velocity_confidence(adata)
    scv.tl.velocity_pseudotime(adata)

    return adata
```

## AnnData 中的关键输出字段

运行 workflow 后，会添加以下 fields：

| 位置 | Key | 描述 |
|----------|-----|-------------|
| `adata.layers` | `velocity` | 每个 gene、每个 cell 的 RNA velocity |
| `adata.layers` | `fit_t` | 每个 gene、每个 cell 的 fitted latent time |
| `adata.obsm` | `velocity_umap` | UMAP 上的 2D velocity vectors |
| `adata.obs` | `velocity_pseudotime` | 来自 velocity 的 pseudotime |
| `adata.obs` | `latent_time` | 来自 dynamical model 的 latent time |
| `adata.obs` | `velocity_length` | 每个 cell 的速度 |
| `adata.obs` | `velocity_confidence` | 每个 cell 的 confidence score |
| `adata.var` | `fit_likelihood` | gene-level model fit 质量 |
| `adata.var` | `fit_alpha` | transcription rate |
| `adata.var` | `fit_beta` | splicing rate |
| `adata.var` | `fit_gamma` | degradation rate |
| `adata.uns` | `velocity_graph` | cell-cell transition probability matrix |

## Velocity models 对比

| Model | 速度 | 准确性 | 适用场景 |
|-------|-------|----------|-------------|
| `stochastic` | 快 | 中等 | 探索性分析；large datasets |
| `deterministic` | 中等 | 中等 | 简单 linear kinetics |
| `dynamical` | 慢 | 高 | publication-quality；识别 driver genes |

## 最佳实践

- **先用 stochastic mode** 进行探索；final analysis 切换到 dynamical
- **需要良好的 unspliced reads coverage**：Short reads（< 100 bp）可能缺少 intron coverage
- **至少 2,000 个 cells**：RNA velocity 在更少 cells 下噪声较大
- **Velocity 应保持一致**：arrows 应符合 known biology；随机方向提示存在问题
- **k-NN bandwidth 很重要**：neighbors 太少 → velocity 噪声大；太多 → oversmoothed
- **Sanity check**：root cells（progenitors）的 marker genes 应有较高 unspliced/spliced ratios
- **Dynamical model 需要 distinct kinetic states**：最适合清晰的 differentiation processes

## 故障排查

| 问题 | 解决方案 |
|---------|---------|
| 缺少 unspliced layer | 重新运行 velocyto，或使用带 `--soloFeatures Gene Velocyto` 的 STARsolo |
| velocity genes 很少 | 降低 `min_shared_counts`；检查 sequencing depth |
| arrows 看起来随机 | 尝试不同 `n_neighbors` 或 velocity model |
| dynamical model 出现 memory error | 设置 `n_jobs=1`；减少 `n_top_genes` |
| 各处 velocity 都为负 | 检查 spliced/unspliced layers 是否被交换 |

## 其他资源

- **scVelo 文档**: https://scvelo.readthedocs.io/
- **教程 notebooks**: https://scvelo.readthedocs.io/tutorials/
- **GitHub**: https://github.com/theislab/scvelo
- **论文**: Bergen V et al. (2020) Nature Biotechnology. PMID: 32747759
- **velocyto** (preprocessing): http://velocyto.org/
- **CellRank** (fate prediction，扩展 scVelo): https://cellrank.readthedocs.io/
- **dynamo** (metabolic labeling 替代方案): https://dynamo-release.readthedocs.io/
