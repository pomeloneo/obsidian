---
name: histolab
description: 轻量级 WSI tile extraction 和 preprocessing。用于基础 slide processing、tissue detection、tile extraction、H&E images 的 stain normalization。最适合 simple pipelines、dataset preparation、quick tile-based analysis。Advanced spatial proteomics、multiplexed imaging 或 deep learning pipelines 使用 pathml。
license: Apache-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# Histolab

## 概述

Histolab 是一个用于 digital pathology 中 whole slide images (WSI) 处理的 Python library。它自动执行 tissue detection、从 gigapixel images 中提取 informative tiles，并为 deep learning pipelines 准备 datasets。该 library 处理多种 WSI formats，实现复杂 tissue segmentation，并提供灵活的 tile extraction strategies。

## 安装

```bash
uv pip install histolab
```

## Quick Start

从 whole slide image 提取 tiles 的基本工作流：

```python
from histolab.slide import Slide
from histolab.tiler import RandomTiler

# Load slide
slide = Slide("slide.svs", processed_path="output/")

# Configure tiler
tiler = RandomTiler(
    tile_size=(512, 512),
    n_tiles=100,
    level=0,
    seed=42
)

# Preview tile locations
tiler.locate_tiles(slide, n_tiles=20)

# Extract tiles
tiler.extract(slide)
```

## 核心能力

### 1. Slide Management

加载、检查并处理各种格式的 whole slide images。

**常见操作：**
- 加载 WSI files（SVS、TIFF、NDPI 等）
- 访问 slide metadata（dimensions、magnification、properties）
- 生成 thumbnails 用于 visualization
- 处理 pyramidal image structures
- 在特定 coordinates 提取 regions

**关键 classes：** `Slide`

**参考：** `references/slide_management.md` 包含以下内容的综合文档：
- Slide initialization 和 configuration
- Built-in sample datasets（prostate、ovarian、breast、heart、kidney tissues）
- 访问 slide properties 和 metadata
- Thumbnail generation 和 visualization
- 处理 pyramid levels
- Multi-slide processing workflows

**示例工作流：**
```python
from histolab.slide import Slide
from histolab.data import prostate_tissue

# Load sample data
prostate_svs, prostate_path = prostate_tissue()

# Initialize slide
slide = Slide(prostate_path, processed_path="output/")

# Inspect properties
print(f"Dimensions: {slide.dimensions}")
print(f"Levels: {slide.levels}")
print(f"Magnification: {slide.properties.get('openslide.objective-power')}")

# Save thumbnail
slide.save_thumbnail()
```

### 2. Tissue Detection and Masks

自动识别 tissue regions，并过滤 background/artifacts。

**常见操作：**
- 创建 binary tissue masks
- 检测最大 tissue region
- 排除 background 和 artifacts
- Custom tissue segmentation
- 移除 pen annotations

**关键 classes：** `TissueMask`、`BiggestTissueBoxMask`、`BinaryMask`

**参考：** `references/tissue_masks.md` 包含以下内容的综合文档：
- TissueMask：使用 automated filters 分割所有 tissue regions
- BiggestTissueBoxMask：返回最大 tissue region 的 bounding box（默认）
- BinaryMask：custom mask implementations 的 base class
- 使用 `locate_mask()` 可视化 masks
- 创建 custom rectangular 和 annotation-exclusion masks
- Mask 与 tile extraction 集成
- Best practices 和 troubleshooting

**示例工作流：**
```python
from histolab.masks import TissueMask, BiggestTissueBoxMask

# Create tissue mask for all tissue regions
tissue_mask = TissueMask()

# Visualize mask on slide
slide.locate_mask(tissue_mask)

# Get mask array
mask_array = tissue_mask(slide)

# Use largest tissue region (default for most extractors)
biggest_mask = BiggestTissueBoxMask()
```

**何时使用各 mask：**
- `TissueMask`：多个 tissue sections、综合分析
- `BiggestTissueBoxMask`：单个主要 tissue section、排除 artifacts（默认）
- Custom `BinaryMask`：特定 ROI、排除 annotations、custom segmentation

### 3. Tile Extraction

使用不同策略从大型 WSI 中提取较小 regions。

**三种 extraction strategies：**

**RandomTiler：** 提取固定数量的随机位置 tiles
- 最适合：采样多样 regions、exploratory analysis、training data
- 关键 parameters：`n_tiles`、用于 reproducibility 的 `seed`

**GridTiler：** 按 grid pattern 系统地跨 tissue 提取 tiles
- 最适合：Complete coverage、spatial analysis、reconstruction
- 关键 parameters：用于 sliding windows 的 `pixel_overlap`

**ScoreTiler：** 基于 scoring functions 提取 top-ranked tiles
- 最适合：最 informative regions、quality-driven selection
- 关键 parameters：`scorer`（NucleiScorer、CellularityScorer、custom）

**常见 parameters：**
- `tile_size`：Tile dimensions（例如 (512, 512)）
- `level`：用于 extraction 的 pyramid level（0 = highest resolution）
- `check_tissue`：按 tissue content 过滤 tiles
- `tissue_percent`：最小 tissue coverage（默认 80%）
- `extraction_mask`：定义 extraction region 的 mask

**参考：** `references/tile_extraction.md` 包含以下内容的综合文档：
- 每种 tiler strategy 的详细解释
- Available scorers（NucleiScorer、CellularityScorer、custom）
- 使用 `locate_tiles()` 预览 tiles
- Extraction workflows 和 reporting
- Advanced patterns（multi-level、hierarchical extraction）
- Performance optimization 和 troubleshooting

**示例工作流：**

```python
from histolab.tiler import RandomTiler, GridTiler, ScoreTiler
from histolab.scorer import NucleiScorer

# Random sampling (fast, diverse)
random_tiler = RandomTiler(
    tile_size=(512, 512),
    n_tiles=100,
    level=0,
    seed=42,
    check_tissue=True,
    tissue_percent=80.0
)
random_tiler.extract(slide)

# Grid coverage (comprehensive)
grid_tiler = GridTiler(
    tile_size=(512, 512),
    level=0,
    pixel_overlap=0,
    check_tissue=True
)
grid_tiler.extract(slide)

# Score-based selection (most informative)
score_tiler = ScoreTiler(
    tile_size=(512, 512),
    n_tiles=50,
    scorer=NucleiScorer(),
    level=0
)
score_tiler.extract(slide, report_path="tiles_report.csv")
```

**提取前始终预览：**
```python
# Preview tile locations on thumbnail
tiler.locate_tiles(slide, n_tiles=20)
```

### 4. Filters and Preprocessing

应用 image processing filters 用于 tissue detection、quality control 和 preprocessing。

**Filter categories：**

**Image Filters：** Color space conversions、thresholding、contrast enhancement
- `RgbToGrayscale`、`RgbToHsv`、`RgbToHed`
- `OtsuThreshold`、`AdaptiveThreshold`
- `StretchContrast`、`HistogramEqualization`

**Morphological Filters：** 对 binary images 进行 structural operations
- `BinaryDilation`、`BinaryErosion`
- `BinaryOpening`、`BinaryClosing`
- `RemoveSmallObjects`、`RemoveSmallHoles`

**Composition：** 将多个 filters 串联
- `Compose`：创建 filter pipelines

**参考：** `references/filters_preprocessing.md` 包含以下内容的综合文档：
- 每种 filter type 的详细解释
- Filter composition 和 chaining
- 常见 preprocessing pipelines（tissue detection、pen removal、nuclei enhancement）
- 将 filters 应用于 tiles
- Custom mask filters
- Quality control filters（blur detection、tissue coverage）
- Best practices 和 troubleshooting

**示例工作流：**

```python
from histolab.filters.compositions import Compose
from histolab.filters.image_filters import RgbToGrayscale, OtsuThreshold
from histolab.filters.morphological_filters import (
    BinaryDilation, RemoveSmallHoles, RemoveSmallObjects
)

# Standard tissue detection pipeline
tissue_detection = Compose([
    RgbToGrayscale(),
    OtsuThreshold(),
    BinaryDilation(disk_size=5),
    RemoveSmallHoles(area_threshold=1000),
    RemoveSmallObjects(area_threshold=500)
])

# Use with custom mask
from histolab.masks import TissueMask
custom_mask = TissueMask(filters=tissue_detection)

# Apply filters to tile
from histolab.tile import Tile
filtered_tile = tile.apply_filters(tissue_detection)
```

### 5. Visualization

可视化 slides、masks、tile locations 和 extraction quality。

**常见 visualization tasks：**
- 显示 slide thumbnails
- 可视化 tissue masks
- 预览 tile locations
- 评估 tile quality
- 创建 reports 和 figures

**参考：** `references/visualization.md` 包含以下内容的综合文档：
- Slide thumbnail display 和 saving
- 使用 `locate_mask()` 可视化 mask
- 使用 `locate_tiles()` 预览 tile location
- 显示 extracted tiles 和 mosaics
- Quality assessment（score distributions、top vs bottom tiles）
- Multi-slide visualization
- Filter effect visualization
- 导出 high-resolution figures 和 PDF reports
- Jupyter notebooks 中的 interactive visualization

**示例工作流：**

```python
import matplotlib.pyplot as plt
from histolab.masks import TissueMask

# Display slide thumbnail
plt.figure(figsize=(10, 10))
plt.imshow(slide.thumbnail)
plt.title(f"Slide: {slide.name}")
plt.axis('off')
plt.show()

# Visualize tissue mask
tissue_mask = TissueMask()
slide.locate_mask(tissue_mask)

# Preview tile locations
tiler = RandomTiler(tile_size=(512, 512), n_tiles=50)
tiler.locate_tiles(slide, n_tiles=20)

# Display extracted tiles in grid
from pathlib import Path
from PIL import Image

tile_paths = list(Path("output/tiles/").glob("*.png"))[:16]
fig, axes = plt.subplots(4, 4, figsize=(12, 12))
axes = axes.ravel()

for idx, tile_path in enumerate(tile_paths):
    tile_img = Image.open(tile_path)
    axes[idx].imshow(tile_img)
    axes[idx].set_title(tile_path.stem, fontsize=8)
    axes[idx].axis('off')

plt.tight_layout()
plt.show()
```

## 典型工作流

### Workflow 1：Exploratory Tile Extraction

快速采样多样 tissue regions，用于初始分析。

```python
from histolab.slide import Slide
from histolab.tiler import RandomTiler
import logging

# Enable logging for progress tracking
logging.basicConfig(level=logging.INFO)

# Load slide
slide = Slide("slide.svs", processed_path="output/random_tiles/")

# Inspect slide
print(f"Dimensions: {slide.dimensions}")
print(f"Levels: {slide.levels}")
slide.save_thumbnail()

# Configure random tiler
random_tiler = RandomTiler(
    tile_size=(512, 512),
    n_tiles=100,
    level=0,
    seed=42,
    check_tissue=True,
    tissue_percent=80.0
)

# Preview locations
random_tiler.locate_tiles(slide, n_tiles=20)

# Extract tiles
random_tiler.extract(slide)
```

### Workflow 2：Comprehensive Grid Extraction

覆盖完整 tissue，用于 whole-slide analysis。

```python
from histolab.slide import Slide
from histolab.tiler import GridTiler
from histolab.masks import TissueMask

# Load slide
slide = Slide("slide.svs", processed_path="output/grid_tiles/")

# Use TissueMask for all tissue sections
tissue_mask = TissueMask()
slide.locate_mask(tissue_mask)

# Configure grid tiler
grid_tiler = GridTiler(
    tile_size=(512, 512),
    level=1,  # Use level 1 for faster extraction
    pixel_overlap=0,
    check_tissue=True,
    tissue_percent=70.0
)

# Preview grid
grid_tiler.locate_tiles(slide)

# Extract all tiles
grid_tiler.extract(slide, extraction_mask=tissue_mask)
```

### Workflow 3：Quality-Driven Tile Selection

基于 nuclei density 提取最 informative tiles。

```python
from histolab.slide import Slide
from histolab.tiler import ScoreTiler
from histolab.scorer import NucleiScorer
import pandas as pd
import matplotlib.pyplot as plt

# Load slide
slide = Slide("slide.svs", processed_path="output/scored_tiles/")

# Configure score tiler
score_tiler = ScoreTiler(
    tile_size=(512, 512),
    n_tiles=50,
    level=0,
    scorer=NucleiScorer(),
    check_tissue=True
)

# Preview top tiles
score_tiler.locate_tiles(slide, n_tiles=15)

# Extract with report
score_tiler.extract(slide, report_path="tiles_report.csv")

# Analyze scores
report_df = pd.read_csv("tiles_report.csv")
plt.hist(report_df['score'], bins=20, edgecolor='black')
plt.xlabel('Tile Score')
plt.ylabel('Frequency')
plt.title('Distribution of Tile Scores')
plt.show()
```

### Workflow 4：Multi-Slide Processing Pipeline

使用一致 parameters 处理整个 slide collection。

```python
from pathlib import Path
from histolab.slide import Slide
from histolab.tiler import RandomTiler
import logging

logging.basicConfig(level=logging.INFO)

# Configure tiler once
tiler = RandomTiler(
    tile_size=(512, 512),
    n_tiles=50,
    level=0,
    seed=42,
    check_tissue=True
)

# Process all slides
slide_dir = Path("slides/")
output_base = Path("output/")

for slide_path in slide_dir.glob("*.svs"):
    print(f"\nProcessing: {slide_path.name}")

    # Create slide-specific output directory
    output_dir = output_base / slide_path.stem
    output_dir.mkdir(parents=True, exist_ok=True)

    # Load and process slide
    slide = Slide(slide_path, processed_path=output_dir)

    # Save thumbnail for review
    slide.save_thumbnail()

    # Extract tiles
    tiler.extract(slide)

    print(f"Completed: {slide_path.name}")
```

### Workflow 5：Custom Tissue Detection and Filtering

处理带 artifacts、annotations 或 unusual staining 的 slides。

```python
from histolab.slide import Slide
from histolab.masks import TissueMask
from histolab.tiler import RandomTiler
from histolab.filters.compositions import Compose
from histolab.filters.image_filters import RgbToGrayscale, OtsuThreshold
from histolab.filters.morphological_filters import (
    BinaryDilation, RemoveSmallObjects, RemoveSmallHoles
)

# Define custom filter pipeline for aggressive artifact removal
aggressive_filters = Compose([
    RgbToGrayscale(),
    OtsuThreshold(),
    BinaryDilation(disk_size=10),
    RemoveSmallHoles(area_threshold=5000),
    RemoveSmallObjects(area_threshold=3000)  # Remove larger artifacts
])

# Create custom mask
custom_mask = TissueMask(filters=aggressive_filters)

# Load slide and visualize mask
slide = Slide("slide.svs", processed_path="output/")
slide.locate_mask(custom_mask)

# Extract with custom mask
tiler = RandomTiler(tile_size=(512, 512), n_tiles=100)
tiler.extract(slide, extraction_mask=custom_mask)
```

## 最佳实践

### Slide Loading and Inspection
1. 处理前始终检查 slide properties
2. 保存 thumbnails 以便快速 visual review
3. 检查 pyramid levels 和 dimensions
4. 使用 thumbnails 验证 tissue 存在

### Tissue Detection
1. Extraction 前用 `locate_mask()` 预览 masks
2. 多个 sections 使用 `TissueMask`，单个 sections 使用 `BiggestTissueBoxMask`
3. 为特定 stains 自定义 filters（H&E vs IHC）
4. 用 custom masks 处理 pen annotations
5. 在多样 slides 上测试 masks

### Tile Extraction
1. **提取前始终用 `locate_tiles()` 预览**
2. 选择合适 tiler：
   - RandomTiler：Sampling 和 exploration
   - GridTiler：Complete coverage
   - ScoreTiler：Quality-driven selection
3. 设置合适 `tissue_percent` threshold（通常 70-90%）
4. 在 RandomTiler 中使用 seeds 保证 reproducibility
5. 根据 analysis resolution 在合适 pyramid level 提取
6. 对 large datasets 启用 logging

### Performance
1. 在较低 levels（1、2）提取以加快 processing
2. 合适时使用 `BiggestTissueBoxMask` 而不是 `TissueMask`
3. 调整 `tissue_percent` 以减少 invalid tile attempts
4. 初始探索时限制 `n_tiles`
5. 对 non-overlapping grids 使用 `pixel_overlap=0`

### Quality Control
1. 验证 tile quality（检查 blur、artifacts、focus）
2. 查看 ScoreTiler 的 score distributions
3. 检查 top 和 bottom scoring tiles
4. 监控 tissue coverage statistics
5. 如需进一步质量控制，按 additional quality metrics 过滤 extracted tiles

## 常见使用场景

### Training Deep Learning Models
- 使用 RandomTiler 跨多个 slides 提取 balanced datasets
- 使用带 NucleiScorer 的 ScoreTiler 聚焦 cell-rich regions
- 以一致 resolution（level 0 或 level 1）提取
- 生成 CSV reports 追踪 tile metadata

### Whole Slide Analysis
- 使用 GridTiler 完整覆盖 tissue
- 在多个 pyramid levels 提取以进行 hierarchical analysis
- 通过 grid positions 保持 spatial relationships
- 使用 `pixel_overlap` 实现 sliding window approaches

### Tissue Characterization
- 用 RandomTiler 采样多样 regions
- 用 masks 量化 tissue coverage
- 通过 HED decomposition 提取 stain-specific information
- 比较 slides 间的 tissue patterns

### Quality Assessment
- 使用 ScoreTiler 识别 optimal focus regions
- 使用 custom masks 和 filters 检测 artifacts
- 评估 slide collection 中的 staining quality
- 标记 problematic slides 供 manual review

### Dataset Curation
- 使用 ScoreTiler 优先选择 informative tiles
- 按 tissue percentage 过滤 tiles
- 生成带 tile scores 和 metadata 的 reports
- 跨 slides 和 tissue types 创建 stratified datasets

## 故障排除

### No tiles extracted
- 降低 `tissue_percent` threshold
- 验证 slide 中包含 tissue（检查 thumbnail）
- 确保 extraction_mask 捕获 tissue regions
- 检查 tile_size 是否适合 slide resolution

### Many background tiles
- 启用 `check_tissue=True`
- 提高 `tissue_percent` threshold
- 使用合适 mask（TissueMask vs BiggestTissueBoxMask）
- 自定义 mask filters 以更好检测 tissue

### Extraction very slow
- 在较低 pyramid level 提取（level=1 或 2）
- 减少 RandomTiler/ScoreTiler 的 `n_tiles`
- 使用 RandomTiler 代替 GridTiler 进行 sampling
- 使用 BiggestTissueBoxMask 代替 TissueMask

### Tiles have artifacts
- 实现 custom annotation-exclusion masks
- 调整 filter parameters 进行 artifact removal
- 提高 small object removal threshold
- 应用 post-extraction quality filtering

### Inconsistent results across slides
- 对 RandomTiler 使用相同 seed
- 使用 preprocessing filters 进行 staining normalization
- 按 staining quality 调整 `tissue_percent`
- 实现 slide-specific mask customization

## 资源

此 skill 在 `references/` 目录中包含详细 reference documentation：

### references/slide_management.md
关于加载、检查和处理 whole slide images 的综合指南：
- Slide initialization 和 configuration
- Built-in sample datasets
- Slide properties 和 metadata
- Thumbnail generation 和 visualization
- Working with pyramid levels
- Multi-slide processing workflows
- Best practices 和 common patterns

### references/tissue_masks.md
Tissue detection 和 masking 完整文档：
- TissueMask、BiggestTissueBoxMask、BinaryMask classes
- Tissue detection filters 如何工作
- 使用 filter chains 自定义 masks
- Visualizing masks
- 创建 custom rectangular 和 annotation-exclusion masks
- 与 tile extraction 集成
- Best practices 和 troubleshooting

### references/tile_extraction.md
Tile extraction strategies 的详细解释：
- RandomTiler、GridTiler、ScoreTiler comparison
- Available scorers（NucleiScorer、CellularityScorer、custom）
- Common 和 strategy-specific parameters
- 使用 locate_tiles() 预览 tiles
- Extraction workflows 和 CSV reporting
- Advanced patterns（multi-level、hierarchical）
- Performance optimization
- Troubleshooting common issues

### references/filters_preprocessing.md
完整 filter reference 和 preprocessing guide：
- Image filters（color conversion、thresholding、contrast）
- Morphological filters（dilation、erosion、opening、closing）
- Filter composition 和 chaining
- Common preprocessing pipelines
- Applying filters to tiles
- Custom mask filters
- Quality control filters
- Best practices 和 troubleshooting

### references/visualization.md
综合 visualization guide：
- Slide thumbnail display 和 saving
- Mask visualization techniques
- Tile location preview
- Displaying extracted tiles 和 creating mosaics
- Quality assessment visualizations
- Multi-slide comparison
- Filter effect visualization
- 导出 high-resolution figures 和 PDFs
- Jupyter notebooks 中的 interactive visualization

**Usage pattern：** Reference files 包含深入信息，用于支持此主 skill 文档中描述的 workflows。需要 detailed implementation guidance、troubleshooting 或 advanced features 时，按需加载具体 reference files。
