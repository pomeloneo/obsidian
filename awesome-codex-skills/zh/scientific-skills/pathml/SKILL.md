---
name: pathml
description: 功能完整的 computational pathology toolkit。用于高级 WSI analysis，包括 multiplexed immunofluorescence（CODEX、Vectra）、nucleus segmentation、tissue graph construction，以及在 pathology data 上训练 ML models。支持 160+ slide formats。对于从 H&E slides 进行简单 tile extraction，histolab 可能更简单。
license: GPL-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# PathML

## 概览

PathML 是面向 computational pathology workflows 的综合 Python toolkit，旨在促进 whole-slide pathology images 的 machine learning 和 image analysis。该 framework 提供模块化、可组合工具，用于加载多种 slide formats、预处理图像、构建 spatial graphs、训练 deep learning models，以及分析来自 CODEX 和 multiplex immunofluorescence 等技术的 multiparametric imaging data。

## 何时使用此 Skill

将此 skill 用于：
- 加载和处理各种 proprietary formats 的 whole-slide images（WSI）
- 使用 stain normalization 预处理 H&E stained tissue images
- Nucleus detection、segmentation 和 classification workflows
- 为 spatial analysis 构建 cell 和 tissue graphs
- 在 pathology data 上训练或部署 machine learning models（HoVer-Net、HACTNet）
- 分析用于 spatial proteomics 的 multiparametric imaging（CODEX、Vectra、MERFISH）
- 从 multiplex immunofluorescence 定量 marker expression
- 使用 HDF5 storage 管理 large-scale pathology datasets
- Tile-based analysis 和 stitching operations

## 核心能力

PathML 提供六个主要能力领域，reference files 中有详细文档：

### 1. Image Loading 与 Formats

从 160+ proprietary formats 加载 whole-slide images，包括 Aperio SVS、Hamamatsu NDPI、Leica SCN、Zeiss ZVI、DICOM 和 OME-TIFF。PathML 会自动处理 vendor-specific formats，并提供统一接口来访问 image pyramids、metadata 和 regions of interest。

**参见：** `references/image_loading.md`，了解 supported formats、loading strategies，以及如何处理不同 slide types。

### 2. Preprocessing Pipelines

通过组合用于 image manipulation、quality control、stain normalization、tissue detection 和 mask operations 的 transforms，构建模块化 preprocessing pipelines。PathML 的 Pipeline 架构支持在大型数据集上进行可复现、可扩展的预处理。

**关键 transforms：**
- `StainNormalizationHE` - Macenko/Vahadane stain normalization
- `TissueDetectionHE`, `NucleusDetectionHE` - Tissue/nucleus segmentation
- `MedianBlur`, `GaussianBlur` - noise reduction
- `LabelArtifactTileHE` - artifacts 的 quality control

**参见：** `references/preprocessing.md`，了解完整 transform catalog、pipeline construction 和 preprocessing workflows。

### 3. Graph Construction

构建表示 cellular 与 tissue-level relationships 的 spatial graphs。从 segmented objects 提取 features，创建适合 graph neural networks 和 spatial analysis 的 graph-based representations。

**参见：** `references/graphs.md`，了解 graph construction methods、feature extraction 和 spatial analysis workflows。

### 4. Machine Learning

训练和部署用于 nucleus detection、segmentation 和 classification 的 deep learning models。PathML 集成 PyTorch、pre-built models（HoVer-Net、HACTNet）、custom DataLoaders，以及用于 inference 的 ONNX 支持。

**关键 models：**
- **HoVer-Net** - 同时进行 nucleus segmentation 和 classification
- **HACTNet** - hierarchical cell-type classification

**参见：** `references/machine_learning.md`，了解 model training、evaluation、inference workflows，以及如何处理 public datasets。

### 5. Multiparametric Imaging

分析来自 CODEX、Vectra、MERFISH 和其他 multiplex imaging platforms 的 spatial proteomics 与 gene expression data。PathML 提供 specialized slide classes 和 transforms，用于处理 multiparametric data、使用 Mesmer 进行 cell segmentation，以及 quantification workflows。

**参见：** `references/multiparametric.md`，了解 CODEX/Vectra workflows、cell segmentation、marker quantification，以及与 AnnData 的集成。

### 6. Data Management

使用 HDF5 format 高效存储和管理大型 pathology datasets。PathML 在为 machine learning workflows 优化的统一 storage structures 中处理 tiles、masks、metadata 和 extracted features。

**参见：** `references/data_management.md`，了解 HDF5 integration、tile management、dataset organization 和 batch processing strategies。

## 快速开始

### 安装

```bash
# Install PathML
uv pip install pathml

# With optional dependencies for all features
uv pip install pathml[all]
```

### 基础 Workflow 示例

```python
from pathml.core import SlideData
from pathml.preprocessing import Pipeline, StainNormalizationHE, TissueDetectionHE

# Load a whole-slide image
wsi = SlideData.from_slide("path/to/slide.svs")

# Create preprocessing pipeline
pipeline = Pipeline([
    TissueDetectionHE(),
    StainNormalizationHE(target='normalize', stain_estimation_method='macenko')
])

# Run pipeline
pipeline.run(wsi)

# Access processed tiles
for tile in wsi.tiles:
    processed_image = tile.image
    tissue_mask = tile.masks['tissue']
```

### 常见 Workflows

**H&E Image Analysis：**
1. 使用合适的 slide class 加载 WSI
2. 应用 tissue detection 和 stain normalization
3. 执行 nucleus detection 或训练 segmentation models
4. 提取 features 并构建 spatial graphs
5. 进行 downstream analysis

**Multiparametric Imaging（CODEX）：**
1. 使用 `CODEXSlide` 加载 CODEX slide
2. 折叠 multi-run channel data
3. 使用 Mesmer model 分割 cells
4. 定量 marker expression
5. 导出到 AnnData 进行 single-cell analysis

**Training ML Models：**
1. 使用 public pathology data 准备 dataset
2. 用 PathML datasets 创建 PyTorch DataLoader
3. 训练 HoVer-Net 或 custom models
4. 在 held-out test sets 上评估
5. 使用 ONNX 部署以进行 inference

## 详细文档参考

处理具体任务时，请参考对应 reference file 获取完整信息：

- **Loading images：** `references/image_loading.md`
- **Preprocessing workflows：** `references/preprocessing.md`
- **Spatial analysis：** `references/graphs.md`
- **Model training：** `references/machine_learning.md`
- **CODEX/multiplex IF：** `references/multiparametric.md`
- **Data storage：** `references/data_management.md`

## 资源

此 skill 包含按能力领域组织的完整参考文档。每个 reference file 都包含特定 PathML 功能的详细 API 信息、workflow examples、best practices 和 troubleshooting guidance。

### references/

提供 PathML 能力深入说明的文档文件：

- `image_loading.md` - whole-slide image formats、loading strategies、slide classes
- `preprocessing.md` - 完整 transform catalog、pipeline construction、preprocessing workflows
- `graphs.md` - graph construction methods、feature extraction、spatial analysis
- `machine_learning.md` - model architectures、training workflows、evaluation、inference
- `multiparametric.md` - CODEX、Vectra、multiplex IF analysis、cell segmentation、quantification
- `data_management.md` - HDF5 storage、tile management、batch processing、dataset organization

处理具体 computational pathology tasks 时，按需加载这些 references。
