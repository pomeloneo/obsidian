---
name: scvi-tools
description: 用于 single-cell omics 的 deep generative models。需要 probabilistic batch correction（scVI）、transfer learning、带 uncertainty 的 differential expression，或 multi-modal integration（TOTALVI、MultiVI）时使用。最适合 advanced modeling、batch effects 和 multimodal data。标准 analysis pipelines 使用 scanpy。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# scvi-tools

## 概述

scvi-tools 是一个用于 single-cell genomics 中 probabilistic models 的综合 Python framework。它构建在 PyTorch 和 PyTorch Lightning 之上，提供使用 variational inference 的 deep generative models，用于分析多种 single-cell data modalities。

## 何时使用此技能

在以下情况使用此 skill：
- 分析 single-cell RNA-seq data（dimensionality reduction、batch correction、integration）
- 处理 single-cell ATAC-seq 或 chromatin accessibility data
- 集成 multimodal data（CITE-seq、multiome、paired/unpaired datasets）
- 分析 spatial transcriptomics data（deconvolution、spatial mapping）
- 对 single-cell data 进行 differential expression analysis
- 开展 cell type annotation 或 transfer learning tasks
- 处理 specialized single-cell modalities（methylation、cytometry、RNA velocity）
- 为 single-cell analysis 构建 custom probabilistic models

## 核心能力

scvi-tools 按 data modality 组织 models：

### 1. Single-cell RNA-seq 分析
Expression analysis、batch correction 和 integration 的 core models。见 `references/models-scrna-seq.md`：
- **scVI**：Unsupervised dimensionality reduction 和 batch correction
- **scANVI**：Semi-supervised cell type annotation 和 integration
- **AUTOZI**：Zero-inflation detection 和 modeling
- **VeloVI**：RNA velocity analysis
- **contrastiveVI**：Perturbation effect isolation

### 2. Chromatin accessibility（ATAC-seq）
用于分析 single-cell chromatin data 的 models。见 `references/models-atac-seq.md`：
- **PeakVI**：Peak-based ATAC-seq analysis 和 integration
- **PoissonVI**：Quantitative fragment count modeling
- **scBasset**：带 motif analysis 的 deep learning approach

### 3. Multimodal 与 multi-omics integration
多种 data types 的 joint analysis。见 `references/models-multimodal.md`：
- **totalVI**：CITE-seq protein 和 RNA joint modeling
- **MultiVI**：Paired 和 unpaired multi-omic integration
- **MrVI**：Multi-resolution cross-sample analysis

### 4. Spatial transcriptomics
Spatially-resolved transcriptomics analysis。见 `references/models-spatial.md`：
- **DestVI**：Multi-resolution spatial deconvolution
- **Stereoscope**：Cell type deconvolution
- **Tangram**：Spatial mapping 和 integration
- **scVIVA**：Cell-environment relationship analysis

### 5. Specialized modalities
其他 specialized analysis tools。见 `references/models-specialized.md`：
- **MethylVI/MethylANVI**：Single-cell methylation analysis
- **CytoVI**：Flow/mass cytometry batch correction
- **Solo**：Doublet detection
- **CellAssign**：Marker-based cell type annotation

## 典型工作流

所有 scvi-tools models 遵循一致 API pattern：

```python
# 1. Load and preprocess data (AnnData format)
import scvi
import scanpy as sc

adata = scvi.data.heart_cell_atlas_subsampled()
sc.pp.filter_genes(adata, min_counts=3)
sc.pp.highly_variable_genes(adata, n_top_genes=1200)

# 2. Register data with model (specify layers, covariates)
scvi.model.SCVI.setup_anndata(
    adata,
    layer="counts",  # Use raw counts, not log-normalized
    batch_key="batch",
    categorical_covariate_keys=["donor"],
    continuous_covariate_keys=["percent_mito"]
)

# 3. Create and train model
model = scvi.model.SCVI(adata)
model.train()

# 4. Extract latent representations and normalized values
latent = model.get_latent_representation()
normalized = model.get_normalized_expression(library_size=1e4)

# 5. Store in AnnData for downstream analysis
adata.obsm["X_scVI"] = latent
adata.layers["scvi_normalized"] = normalized

# 6. Downstream analysis with scanpy
sc.pp.neighbors(adata, use_rep="X_scVI")
sc.tl.umap(adata)
sc.tl.leiden(adata)
```

**关键设计原则：**
- **需要 raw counts**：models 需要 unnormalized count data 以获得最佳 performance
- **Unified API**：所有 models 使用一致 interface（setup → train → extract）
- **AnnData-centric**：与 scanpy ecosystem 无缝集成
- **GPU acceleration**：自动利用可用 GPUs
- **Batch correction**：通过 covariate registration 处理 technical variation

## 常见分析任务

### Differential expression 分析
使用 learned generative models 进行 probabilistic DE analysis：

```python
de_results = model.differential_expression(
    groupby="cell_type",
    group1="TypeA",
    group2="TypeB",
    mode="change",  # Use composite hypothesis testing
    delta=0.25      # Minimum effect size threshold
)
```

详细 methodology 和 interpretation 见 `references/differential-expression.md`。

### Model 持久化
保存并加载 trained models：

```python
# Save model
model.save("./model_directory", overwrite=True)

# Load model
model = scvi.model.SCVI.load("./model_directory", adata=adata)
```

### Batch correction 和 integration
跨 batches 或 studies 集成 datasets：

```python
# Register batch information
scvi.model.SCVI.setup_anndata(adata, batch_key="study")

# Model automatically learns batch-corrected representations
model = scvi.model.SCVI(adata)
model.train()
latent = model.get_latent_representation()  # Batch-corrected
```

## 理论基础

scvi-tools 基于：
- **Variational inference**：用于 scalable Bayesian inference 的 approximate posterior distributions
- **Deep generative models**：学习 complex data distributions 的 VAE architectures
- **Amortized inference**：用于跨 cells 高效学习的 shared neural networks
- **Probabilistic modeling**：有原则地进行 uncertainty quantification 和 statistical testing

Mathematical framework 的详细背景见 `references/theoretical-foundations.md`。

## 其他资源

- **Workflows**：`references/workflows.md` 包含 common workflows、best practices、hyperparameter tuning 和 GPU optimization
- **Model references**：`references/` directory 中各 model category 的详细文档
- **官方文档**: https://docs.scvi-tools.org/en/stable/
- **教程**: https://docs.scvi-tools.org/en/stable/tutorials/index.html
- **API reference**: https://docs.scvi-tools.org/en/stable/api/index.html

## 安装

```bash
uv pip install scvi-tools
# For GPU support
uv pip install scvi-tools[cuda]
```

## 最佳实践

1. **使用 raw counts**：始终向 models 提供 unnormalized count data
2. **过滤 genes**：analysis 前移除 low-count genes（例如 `min_counts=3`）
3. **注册 covariates**：在 `setup_anndata` 中包含已知 technical factors（batch、donor 等）
4. **Feature selection**：使用 highly variable genes 提升 performance
5. **保存 model**：始终保存 trained models，避免 retraining
6. **GPU usage**：大型 datasets 开启 GPU acceleration（`accelerator="gpu"`）
7. **Scanpy integration**：将 outputs 存入 AnnData objects 以进行 downstream analysis
