---
name: optimize-for-gpu
description: "使用 CuPy、Numba CUDA、Warp、cuDF、cuML、cuGraph、KvikIO、cuCIM、cuxfilter、cuVS、cuSpatial 和 RAFT 对 Python 代码进行 GPU 加速。每当用户提到 GPU/CUDA/NVIDIA 加速，或想要加速 NumPy、pandas、scikit-learn、scikit-image、NetworkX、GeoPandas 或 Faiss 工作负载时使用。涵盖 physics simulation、differentiable rendering、mesh ray casting、particle systems (DEM/SPH/fluids)、vector/similarity search、GPUDirect Storage file IO、interactive dashboards、geospatial analysis、medical imaging 和 sparse eigensolvers。当你看到可从 GPU 加速受益的 CPU-bound Python 代码（loops、大数组、ML pipelines、graph analytics、image processing）时，即使用户没有明确提出，也应使用。"
metadata:
  author: K-Dense, Inc.
---

# 使用 NVIDIA 进行 Python GPU 优化

你是一名专家级 GPU 优化工程师。你的工作是帮助用户编写新的 GPU 加速代码，或将他们现有的 CPU-bound Python 代码转换为在 NVIDIA GPUs 上运行，从而获得显著加速，适合的工作负载通常可达 10x 到 1000x。

## 此 Skill 适用场景

- 用户想加速 numerical/scientific Python 代码
- 用户正在处理大型数组、矩阵或 dataframes
- 用户提到 CUDA、GPU、NVIDIA 或并行计算
- 用户有处理大型数据集的 NumPy、pandas、SciPy、scikit-learn、NetworkX 或 scipy.sparse.linalg 代码
- 用户需要底层 GPU primitives（sparse eigensolvers、device memory management、multi-GPU communication）
- 用户正在做机器学习（training、inference、hyperparameter tuning、preprocessing）
- 用户正在做图分析（centrality、community detection、shortest paths、PageRank 等）
- 用户正在做 vector search、nearest neighbor search、similarity search，或构建 RAG pipeline
- 用户有可以 GPU 加速的 Faiss、Annoy、ScaNN 或 sklearn NearestNeighbors 代码
- 用户想要 GPU 加速的交互式 dashboards、cross-filtering 或大数据集 exploratory data analysis
- 用户正在使用 GeoPandas 或 shapely 做 geospatial analysis（point-in-polygon、spatial joins、trajectory analysis、distance calculations）
- 用户正在使用 scikit-image 或 OpenCV 做 image processing、computer vision 或 medical imaging（filtering、segmentation、morphology、feature detection）
- 用户正在处理 whole-slide images (WSI)、digital pathology、microscopy 或 remote sensing imagery
- 用户正在将大型二进制数据文件加载到 GPU memory（numpy.fromfile → cupy，或 Python open() → GPU array）
- 用户需要直接将 S3、HTTP 或 WebHDFS 中的文件读取到 GPU memory
- 用户提到 GPUDirect Storage (GDS)，或想绕过 CPU-memory staging 进行 file IO
- 用户正在做 physics simulation（particles、cloth、fluids、rigid bodies）或 differentiable simulation
- 用户需要在 GPU 上进行 mesh operations（ray casting、closest-point queries、signed distance fields）或 geometry processing
- 用户正在使用 transforms 和 quaternions 做 robotics（kinematics、dynamics、control）
- 用户有可以 JIT 编译为 GPU kernels 的 Python simulation loops
- 用户提到 NVIDIA Warp，或想将 differentiable GPU simulation 与 PyTorch/JAX 集成
- 用户正在做 simulations、signal processing、financial modeling、bioinformatics、physics 或任何 compute-intensive 工作
- 用户想优化现有代码，且 GPU 加速是正确答案

## 决策框架：使用哪个库

根据用户代码实际执行的工作选择合适工具。编写任何 GPU 代码前，先阅读相应 reference 文件。

### CuPy — 用于 array/matrix operations（NumPy 替代）
**阅读：** `references/cupy.md`

当用户代码主要是以下内容时使用 CuPy：
- NumPy array operations（element-wise math、linear algebra、FFT、sorting、reductions）
- SciPy operations（sparse matrices、signal processing、image filtering、special functions）
- 任何串联 NumPy 调用的代码 — CuPy 是 drop-in replacement

CuPy 封装了 NVIDIA 优化库（cuBLAS、cuFFT、cuSOLVER、cuSPARSE、cuRAND），因此标准操作已经过调优。大多数 NumPy 代码只需将 `import numpy as np` 改为 `import cupy as cp` 即可工作。

**最适合：** Linear algebra、FFTs、array math、image processing、signal processing、使用 array ops 的 Monte Carlo、任何 NumPy-heavy workflow。

### Numba CUDA — 用于 custom GPU kernels
**阅读：** `references/numba.md`

当用户需要以下能力时使用 Numba：
- 无法映射到标准 array operations 的 custom algorithms
- 对 GPU threads、blocks 和 shared memory 进行细粒度控制
- 带复杂逻辑的 element-wise operations（使用 `@vectorize(target='cuda')`）
- 带自定义逻辑的 reduction operations
- Stencil computations 或依赖邻域的计算
- 任何需要直接使用 CUDA programming model 的内容

Numba 将 Python 直接编译成 CUDA kernels。它提供对 GPU thread hierarchy、shared memory 和 synchronization 的完整控制，这对于无法表达为 array operations 的算法至关重要。

**最适合：** Custom kernels、particle simulations、stencil codes、custom reductions、需要 shared memory 的算法、任何包含复杂 per-element logic 的代码。

### Warp — 用于 simulation、spatial computing 和 differentiable programming
**阅读：** `references/warp.md`

当用户代码主要是以下内容时使用 Warp：
- Physics simulation（particles、cloth、fluids、rigid bodies、DEM、SPH）
- Geometry processing（mesh operations、ray casting、signed distance fields、marching cubes）
- Robotics（使用 transforms 和 quaternions 的 kinematics、dynamics、control）
- 用于 ML training 的 differentiable simulation（与 PyTorch/JAX autograd 集成）
- 任何需要 JIT 编译到 GPU 的 Python simulation loop
- 使用 meshes、volumes (NanoVDB)、hash grids 或 BVH queries 的 spatial computing

Warp 将 `@wp.kernel` Python 函数 JIT 编译为 CUDA，并提供面向 spatial computing 的内置类型（vec3、mat33、quat、transform）以及 geometry queries primitives（Mesh、Volume、HashGrid、BVH）。所有 kernels 都自动可微。

**最适合：** Physics simulation、mesh ray casting、particle systems、differentiable rendering、robotics kinematics、SDF operations、任何结合 spatial data structures 与 GPU compute 的工作负载。

**Warp vs Numba：** 两者都会将 Python 编译为 CUDA，但 Warp 提供更高级的 spatial types（vec3、quat、Mesh、Volume）和 automatic differentiation，而 Numba 提供原始 CUDA 控制（shared memory、block/thread management、atomics）。simulation/geometry 使用 Warp，general-purpose custom kernels 使用 Numba。

### cuDF — 用于 dataframe operations（pandas 替代）
**阅读：** `references/cudf.md`

当用户代码主要是以下内容时使用 cuDF：
- pandas DataFrame operations（filtering、groupby、joins、aggregations）
- CSV/Parquet/JSON 读取和处理
- 大数据集上的 ETL pipelines 或 data wrangling
- 任何数据集可放入 GPU memory 的 pandas-heavy workflow

cuDF 的 `cudf.pandas` accelerator mode 可以在零代码改动的情况下加速现有 pandas 代码。要获得最高性能，请使用原生 cuDF API。

**最适合：** Data wrangling、ETL、groupby/aggregations、joins、dataframes 上的 string processing、tabular data 上的 time series。

### cuML — 用于 machine learning（scikit-learn 替代）
**阅读：** `references/cuml.md`

当用户代码主要是以下内容时使用 cuML：
- scikit-learn estimators（classification、regression、clustering、dimensionality reduction）
- ML preprocessing（scaling、encoding、imputation、feature extraction）
- Hyperparameter tuning 或 cross-validation
- Tree model inference（XGBoost、LightGBM、通过 FIL 的 sklearn Random Forest）
- 大数据集上的 UMAP、t-SNE、HDBSCAN 或 KNN

cuML 的 `cuml.accel` accelerator mode 可以在零代码改动的情况下加速现有 sklearn 代码。要获得最高性能，请使用原生 cuML API。对于简单 linear models，加速通常为 2-10x；对于 HDBSCAN 和 KNN 等复杂算法，可达 60-600x。

**最适合：** Classification、regression、clustering、dimensionality reduction、preprocessing pipelines、model inference、任何 scikit-learn-heavy workflow。

### cuGraph — 用于 graph analytics（NetworkX 替代）
**阅读：** `references/cugraph.md`

当用户代码主要是以下内容时使用 cuGraph：
- NetworkX graph algorithms（centrality、community detection、shortest paths、PageRank）
- 大型网络的图构建和分析
- Social network analysis、knowledge graphs 或 recommendation systems
- 任何 10K+ edges 网络上的 graph algorithm

cuGraph 的 `nx-cugraph` backend 可以通过环境变量在零代码改动的情况下加速现有 NetworkX 代码。要获得最高性能，请配合 cuDF DataFrames 使用原生 cuGraph API。加速范围从小图的 10x 到大图（数百万 edges）的 500x+。

**最适合：** PageRank、betweenness centrality、community detection（Louvain、Leiden）、BFS/SSSP、connected components、link prediction、graph neural network sampling、任何 NetworkX-heavy workflow。

### KvikIO — 用于高性能 GPU file IO
**阅读：** `references/kvikio.md`

当用户代码主要是以下内容时使用 KvikIO：
- 直接将大型二进制数据文件加载到 GPU memory
- 将 GPU arrays 写入磁盘而不先复制到 host
- 从远程存储（S3、HTTP、WebHDFS）读取数据到 GPU memory
- 在 GPU 上处理 Zarr arrays（GDSStore backend）
- 任何 file IO 是存储与 GPU 之间瓶颈的 pipeline

KvikIO 提供 NVIDIA cuFile 的 Python bindings，启用 GPUDirect Storage (GDS) — 数据直接在 NVMe storage 和 GPU memory 之间流动，完全绕过 CPU memory。GDS 不可用时，它会透明 fallback 到 POSIX IO。它能无缝处理 host 和 device data。

**最适合：** 将二进制数据加载到 GPU、将 GPU arrays 保存到磁盘、直接从 S3/HTTP 读取到 GPU、GPU 上的 Zarr arrays、替换 `numpy.fromfile()` → `cupy` 模式、任何 IO-heavy GPU pipeline 且 CPU memory staging 成为瓶颈的场景。

**注意：** 对于 tabular formats（CSV、Parquet、JSON），请改用 cuDF 内置 reader — 它们已针对这些格式优化。KvikIO 用于 raw binary data 和 remote file access。

### cuxfilter — 用于 GPU 加速的 interactive dashboards
**阅读：** `references/cuxfilter.md`

当用户需要以下能力时使用 cuxfilter：
- 大数据集（数百万行）上的 interactive cross-filtering dashboards
- 使用相互过滤的 linked charts 进行 exploratory data analysis
- 使用 scatter plots、bar charts、heatmaps、choropleths 或 graph visualizations 进行 GPU-accelerated visualization
- 从 Jupyter notebooks 以最少代码原型化 dashboard
- 可视化 cuDF、cuML 或 cuGraph pipelines 的结果

cuxfilter 利用 cuDF 在 GPU 上执行所有数据操作 — filtering、groupby 和 aggregation 全部在 GPU 上完成，只把渲染结果发送到浏览器。它集成了 Bokeh、Datashader（用于数百万点）、Deck.gl（用于地图）和 Panel widgets。

**最适合：** Interactive data exploration dashboards、multi-chart cross-filtering、geospatial visualization、graph visualization、可视化 RAPIDS pipeline 结果、任何用户需要交互式探索和过滤大型 GPU-resident datasets 的场景。

### cuCIM — 用于 image processing（scikit-image 替代）
**阅读：** `references/cucim.md`

当用户代码主要是以下内容时使用 cuCIM：
- scikit-image operations（filtering、morphology、segmentation、feature detection、color conversion）
- Deep learning 的 image preprocessing pipelines（resize、normalize、augment）
- Digital pathology（whole-slide image reading、H&E stain normalization、cell counting）
- Microscopy、remote sensing 或 medical imaging workflows
- 任何处理 512x512 或更大图像的 scikit-image-heavy pipeline

cuCIM 的 `cucim.skimage` 模块用 200+ 个 GPU 加速函数镜像 scikit-image API。它还提供高性能 WSI reader（`CuImage`），速度比 OpenSlide 快 5-6x。所有函数都在 CuPy arrays 上工作 — zero-copy，全部在 GPU 上。

**最适合：** Filtering（Gaussian、Sobel、Frangi）、morphology、thresholding、connected component labeling、region properties、color space conversion、image registration、denoising、whole-slide image processing、DL preprocessing pipelines。

### cuVS — 用于 vector search（Faiss/Annoy 替代）
**阅读：** `references/cuvs.md`

当用户代码主要是以下内容时使用 cuVS：
- 高维向量上的 approximate nearest neighbor (ANN) search
- 面向 RAG、recommender systems 或 semantic retrieval 的 similarity search
- 用于 clustering 或 visualization 的 k-NN graph construction
- 大型 embedding datasets 上的任何 Faiss、Annoy、ScaNN 或 sklearn NearestNeighbors 工作负载

cuVS 提供 GPU 加速 ANN index types（CAGRA、IVF-Flat、IVF-PQ、brute force），以及用于从 GPU-built indexes 进行 CPU serving 的 HNSW。它支撑了 Faiss、Milvus 和 Lucene 的 GPU backends。多数用例从 CAGRA 开始 — 它是最快的 GPU-native algorithm。

**最适合：** Embedding search、RAG retrieval、recommender systems、image/text/audio similarity search、k-NN graph construction、任何 10K+ vectors 上的 nearest-neighbor workload。

### cuSpatial — 用于 geospatial analytics（GeoPandas 替代）
**阅读：** `references/cuspatial.md`

当用户代码主要是以下内容时使用 cuSpatial：
- GeoPandas spatial operations（point-in-polygon、spatial joins、distance calculations）
- Trajectory analysis（分组 GPS traces、计算 speeds/distances）
- 大规模 spatial joins 的 spatial indexing（quadtree）
- lat/lon coordinates 上的 Haversine distance calculations
- 大型 geospatial datasets 上任何 GeoPandas/shapely-heavy workflow

cuSpatial 提供 GPU 加速的 `GeoSeries` 和 `GeoDataFrame` 类型，兼容 GeoPandas，并提供 spatial join、distance 和 trajectory functions。使用 `cuspatial.from_geopandas()` 从 GeoPandas 转换。

**最适合：** Point-in-polygon tests、数百万 points/polygons 上的 spatial joins、haversine 和 Euclidean distance calculations、trajectory reconstruction and analysis、任何 GeoPandas-heavy geospatial workflow。

### RAFT (pylibraft) — 用于底层 GPU primitives 和 multi-GPU
**阅读：** `references/raft.md`

当用户需要以下能力时使用 RAFT：
- GPU 加速 sparse eigenvalue problems（`scipy.sparse.linalg.eigsh` 替代）
- 底层 GPU device memory management（`device_ndarray`）
- Random graph generation（用于 benchmarking 的 R-MAT model）
- Multi-node multi-GPU communication infrastructure（通过 `raft-dask`）
- 支撑更高层 RAPIDS libraries 的 building blocks

RAFT 提供 cuML 和 cuGraph 所构建于其上的 foundational primitives。大多数用户应先选择这些更高层库 — 只有在需要 RAFT 暴露的特定 primitives（sparse eigensolvers、device memory、graph generation）或通过 Dask 做 multi-GPU communication 时，才直接使用 RAFT。

**最适合：** Sparse eigenvalue decomposition（spectral methods、graph partitioning）、R-MAT graph generation、底层 device memory management、multi-GPU orchestration。

**注意：** Vector search algorithms（k-NN、IVFPQ、CAGRA）已经迁移到 cuVS — 不要将 RAFT 用于 vector search。

### 组合使用库

许多真实工作负载都受益于组合多个库。它们通过 CUDA Array Interface 互操作 — 在 CuPy、Numba、Warp、cuDF、cuML、cuGraph、cuVS、cuCIM、cuSpatial、KvikIO、PyTorch、JAX 和其他 GPU libraries 之间进行 zero-copy data sharing。

常见组合：
- **cuDF + cuML**：用 cuDF 加载和预处理数据，用 cuML 训练/预测 — 完整 RAPIDS pipeline
- **cuDF + cuGraph**：从 cuDF edge lists 构建图，用 cuGraph 运行 graph analytics
- **cuGraph + cuML**：用 cuGraph 提取 graph features，输入 cuML 做 ML
- **cuML + cuVS**：用 cuML 训练 embedding model，用 cuVS 索引和搜索 embeddings
- **cuDF + CuPy**：用 cuDF 加载和过滤数据，然后用 CuPy 做 numerical analysis
- **CuPy + cuVS**：用 CuPy operations 生成 embeddings，构建 cuVS search index — zero-copy
- **Warp + PyTorch**：在 Warp 中做 differentiable simulation，将 gradients backpropagate 到 PyTorch training loop
- **Warp + CuPy**：用 CuPy 做 array math，用 Warp 做 spatial queries（mesh、volume）— 通过 CUDA Array Interface zero-copy
- **Warp + JAX**：将 Warp kernels 作为 jitted functions 内的 JAX primitives
- **CuPy + Numba**：用 CuPy 做标准 ops，进入 Numba 编写 custom kernels
- **cuDF + Numba**：用 cuDF 处理 dataframes，通过 Numba UDFs 应用 custom GPU functions
- **cuML + CuPy**：用 cuML 训练，用 CuPy 做 custom post-processing
- **cuDF + cuxfilter**：用 cuDF 加载数据，用 cuxfilter 构建 interactive cross-filtering dashboards
- **cuML + cuxfilter**：用 cuML 运行 ML（例如 UMAP、clustering），用 cuxfilter 交互式可视化结果
- **cuGraph + cuxfilter**：用 cuGraph 运行 graph analytics，用 cuxfilter 的 datashader graph chart 可视化 graph structure
- **cuCIM + CuPy**：cuCIM 原生操作 CuPy arrays — 将 image processing 与 array math 串联
- **cuCIM + PyTorch**：用 cuCIM 预处理图像，通过 DLPack 直接传给 PyTorch — zero-copy
- **cuCIM + cuML**：用 cuCIM 提取 image features（regionprops），用 cuML 训练 classifiers
- **KvikIO + CuPy**：通过 GDS 将 raw binary data 直接加载到 CuPy arrays，绕过 CPU memory
- **KvikIO + Numba**：用 KvikIO 直接读取数据到 GPU，再用 custom Numba CUDA kernels 处理
- **KvikIO + Zarr**：使用 GDSStore backend 在 GPU 上直接 read/write chunked N-dimensional arrays
- **cuSpatial + cuDF**：用 cuDF 加载 geospatial data，用 cuSpatial 做 spatial joins/analysis
- **cuSpatial + cuML**：用 cuSpatial 提取 spatial features，用 cuML 训练 ML models
- **RAFT + CuPy**：在使用 CuPy/cupyx.scipy.sparse 构建的 sparse matrices 上使用 RAFT 的 eigsh()
- **RAFT + raft-dask**：通过 Dask 将 GPU workloads 扩展到多个 GPUs/nodes

## 安装

重要：始终使用 `uv add` 安装包 — 不要使用 `pip install` 或 `conda install`。这适用于代码注释、docstrings、错误消息以及你生成的任何其他输出中的安装说明。如果用户项目使用不同的 package manager，则跟随其做法，但默认使用 `uv add`。

```bash
# CuPy (choose the right CUDA version)
uv add cupy-cuda12x          # For CUDA 12.x (most common)

# Numba with CUDA support
uv add numba numba-cuda      # numba-cuda is the actively maintained NVIDIA package

# Warp (simulation, spatial computing, differentiable programming)
uv add warp-lang              # CUDA 12 runtime included

# cuDF (RAPIDS)
uv add --extra-index-url=https://pypi.nvidia.com cudf-cu12  # For CUDA 12.x
# For cudf.pandas accelerator mode, that's all you need
# Load it with: python -m cudf.pandas your_script.py

# cuML (RAPIDS machine learning)
uv add --extra-index-url=https://pypi.nvidia.com cuml-cu12   # For CUDA 12.x
# For cuml.accel accelerator mode (zero-change sklearn acceleration):
# Load it with: python -m cuml.accel your_script.py

# cuGraph (RAPIDS graph analytics)
uv add --extra-index-url=https://pypi.nvidia.com cugraph-cu12    # Core cuGraph
uv add --extra-index-url=https://pypi.nvidia.com nx-cugraph-cu12 # NetworkX backend
# For nx-cugraph zero-change NetworkX acceleration:
# NX_CUGRAPH_AUTOCONFIG=True python your_script.py

# KvikIO (high-performance GPU file IO)
uv add kvikio-cu12               # For CUDA 12.x
# Optional: uv add zarr          # For Zarr GPU backend support

# cuxfilter (GPU-accelerated interactive dashboards)
uv add --extra-index-url=https://pypi.nvidia.com cuxfilter-cu12   # For CUDA 12.x
# Depends on cuDF — installs it automatically

# cuCIM (RAPIDS image processing — scikit-image on GPU)
uv add --extra-index-url=https://pypi.nvidia.com cucim-cu12    # For CUDA 12.x

# cuVS (RAPIDS vector search)
uv add --extra-index-url=https://pypi.nvidia.com cuvs-cu12   # For CUDA 12.x

# cuSpatial (RAPIDS geospatial)
uv add --extra-index-url=https://pypi.nvidia.com cuspatial-cu12   # For CUDA 12.x

# RAFT (low-level GPU primitives)
uv add --extra-index-url=https://pypi.nvidia.com pylibraft-cu12   # Core primitives
uv add --extra-index-url=https://pypi.nvidia.com raft-dask-cu12   # Multi-GPU support (optional)
```

安装后检查 CUDA 可用性：

```python
# CuPy
import cupy as cp
print(cp.cuda.runtime.getDeviceCount())  # Should be >= 1

# Numba
from numba import cuda
print(cuda.is_available())               # Should be True
print(cuda.detect())                     # Shows GPU details

# cuDF
import cudf
print(cudf.Series([1, 2, 3]))           # Should print a GPU series

# cuML
import cuml
print(cuml.__version__)                  # Should print version

# cuGraph
import cugraph
print(cugraph.__version__)               # Should print version

# Warp
import warp as wp
wp.init()                                # Should print device info

# KvikIO
import kvikio
import kvikio.cufile_driver
print(kvikio.cufile_driver.get("is_gds_available"))  # True if GDS is set up

# cuxfilter
import cuxfilter
print(cuxfilter.__version__)             # Should print version

# cuVS
from cuvs.neighbors import cagra
import cupy as cp
dataset = cp.random.rand(1000, 128, dtype=cp.float32)
index = cagra.build(cagra.IndexParams(), dataset)
print("cuVS working")                    # Should print confirmation

# cuSpatial
import cuspatial
from shapely.geometry import Point
gs = cuspatial.GeoSeries([Point(0, 0)])
print("cuSpatial working")              # Should print confirmation

# RAFT (pylibraft)
from pylibraft.common import DeviceResources
handle = DeviceResources()
handle.sync()
print("pylibraft is working")
```

## 优化工作流

帮助用户优化代码时，请遵循以下流程：

### 1. 先做 Profile
优化前，先了解时间实际花在哪里：
```python
import time
# or use cProfile, line_profiler, or py-spy for detailed profiling
```
不要猜测 — 要测量。瓶颈可能并不在用户以为的位置。

### 2. 评估 GPU 适配性
不是所有代码都能从 GPU 加速中受益。GPU 擅长以下场景：
- **数据并行度高**：同一操作应用到数千/数百万元素
- **计算强度高**：每访问一个字节内存有很多 FLOPs
- **数据足够大**：GPU 开销意味着小数组（< ~10K elements）在 GPU 上可能更慢
- **内存可容纳**：数据必须放入 GPU memory（通常 8-80 GB）

GPU 不适合以下场景：
- 数据很小（< 10K elements）
- 算法本质上是顺序的，步骤之间存在数据依赖
- 代码受 I/O 限制（disk、network），而不是 compute bound — 不过当 IO 向 GPU compute 供数时，带 GPUDirect Storage 的 KvikIO 可能有帮助
- 许多小型、异构操作（kernel launch overhead 占主导）

### 3. 先简单，再优化
1. **先尝试 drop-in replacement。** NumPy 用 CuPy，pandas 用 cudf.pandas，sklearn 用 cuml.accel，NetworkX 用 nx-cugraph。仅此一步通常就能带来 5-50x 加速。
2. **最小化 host-device transfers。** 让数据留在 GPU 上。每次跨 PCI-e 传输都很昂贵（约 12 GB/s），而 GPU memory bandwidth 约为 900 GB/s+。
3. **批量操作。** 少量大型 GPU 操作胜过大量小操作。
4. **仅在需要时编写 custom kernels。** CuPy 和 cuDF 使用 NVIDIA 手工调优库。Custom Numba kernels 应保留给没有库等价实现的操作。
5. **Profile GPU 版本。** 使用 `nvprof`、`nsys` 或 CuPy 内置 benchmarking。

### 4. 内存管理原则
这些原则适用于所有库：
- **预分配 output arrays**，而不是在循环中创建新数组
- **复用 GPU memory** — 使用 memory pools（CuPy 内置）
- **使用 pinned（page-locked）host memory** 加快 CPU-GPU transfers
- **避免不必要的 copies** — 尽可能使用 in-place operations
- **使用 stream operations** 以重叠 compute 和 data transfer

### 5. 常见陷阱
- **隐式 CPU fallback**：某些操作会静默 fallback 到 CPU。注意 warnings。
- **Synchronization overhead**：GPU 操作是异步的。调用 `.get()` 或 `cp.asnumpy()` 会强制同步。
- **dtype mismatches**：在精度允许时使用 `float32` 而不是 `float64` — GPU float32 throughput 高 2x-32x。
- **小型 kernel launches**：每次 kernel launch 有约 5-20us 开销。尽可能融合操作。

## 代码转换模式

转换现有 CPU 代码时，应用以下模式：

### NumPy 到 CuPy
```python
# Before (CPU)
import numpy as np
a = np.random.rand(10_000_000)
b = np.fft.fft(a)
c = np.sort(b.real)

# After (GPU) — often just change the import
import cupy as cp
a = cp.random.rand(10_000_000)
b = cp.fft.fft(a)
c = cp.sort(b.real)
```

### pandas 到 cuDF
```python
# Before (CPU)
import pandas as pd
df = pd.read_parquet("large_data.parquet")
result = df.groupby("category")["value"].mean()

# After (GPU) — change the import
import cudf
df = cudf.read_parquet("large_data.parquet")
result = df.groupby("category")["value"].mean()

# Or zero-code-change: python -m cudf.pandas your_script.py
```

### Custom loop 到 Numba CUDA kernel
```python
# Before (CPU) — slow Python loop
def process(data, out):
    for i in range(len(data)):
        out[i] = math.sin(data[i]) * math.exp(-data[i])

# After (GPU) — Numba kernel
from numba import cuda
import math

@cuda.jit
def process(data, out):
    i = cuda.grid(1)
    if i < data.size:
        out[i] = math.sin(data[i]) * math.exp(-data[i])

threads = 256
blocks = (len(data) + threads - 1) // threads
process[blocks, threads](d_data, d_out)
```

### NetworkX 到 cuGraph
```python
# Before (CPU)
import networkx as nx
G = nx.read_edgelist("edges.csv", delimiter=",", nodetype=int)
pr = nx.pagerank(G)
bc = nx.betweenness_centrality(G)

# After (GPU) — direct cuGraph API
import cugraph
import cudf
edges = cudf.read_csv("edges.csv", names=["src", "dst"], dtype=["int32", "int32"])
G = cugraph.Graph()
G.from_cudf_edgelist(edges, source="src", destination="dst")
pr = cugraph.pagerank(G)
bc = cugraph.betweenness_centrality(G)

# Or zero-code-change: NX_CUGRAPH_AUTOCONFIG=True python your_script.py
```

### scikit-learn 到 cuML
```python
# Before (CPU)
from sklearn.ensemble import RandomForestClassifier
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
model = RandomForestClassifier(n_estimators=100)
model.fit(X_train, y_train)

# After (GPU) — change the imports
from cuml.ensemble import RandomForestClassifier
from cuml.preprocessing import StandardScaler
from cuml.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
model = RandomForestClassifier(n_estimators=100)
model.fit(X_train, y_train)

# Or zero-code-change: python -m cuml.accel your_script.py
```

### Simulation loop 到 Warp kernel
```python
# Before (CPU) — slow Python loop over particles
import numpy as np

def integrate(positions, velocities, forces, dt):
    for i in range(len(positions)):
        velocities[i] += forces[i] * dt
        positions[i] += velocities[i] * dt

# After (GPU) — Warp kernel, JIT-compiled to CUDA
import warp as wp

@wp.kernel
def integrate(positions: wp.array(dtype=wp.vec3),
              velocities: wp.array(dtype=wp.vec3),
              forces: wp.array(dtype=wp.vec3),
              dt: float):
    tid = wp.tid()
    velocities[tid] = velocities[tid] + forces[tid] * dt
    positions[tid] = positions[tid] + velocities[tid] * dt

wp.launch(integrate, dim=num_particles,
          inputs=[positions, velocities, forces, 0.01], device="cuda")
```

### 使用 KvikIO 将 File IO 转到 GPU
```python
# Before — CPU staging (disk → CPU → GPU)
import numpy as np
import cupy as cp

data = np.fromfile("data.bin", dtype=np.float32)
gpu_data = cp.asarray(data)  # Extra copy through CPU memory

# After — direct to GPU (disk → GPU via GDS)
import cupy as cp
import kvikio

gpu_data = cp.empty(1_000_000, dtype=cp.float32)
with kvikio.CuFile("data.bin", "r") as f:
    f.read(gpu_data)  # Bypasses CPU memory with GPUDirect Storage

# Reading from S3 directly to GPU
with kvikio.RemoteFile.open_s3_url("s3://bucket/data.bin") as f:
    buf = cp.empty(f.nbytes() // 4, dtype=cp.float32)
    f.read(buf)
```

### 使用 cuxfilter 构建 GPU-accelerated dashboard
```python
# Before — static matplotlib/seaborn plots, no interactivity
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_parquet("large_dataset.parquet")
fig, axes = plt.subplots(1, 2)
df.plot.scatter(x="feature1", y="feature2", ax=axes[0])
df["category"].value_counts().plot.bar(ax=axes[1])
plt.show()

# After (GPU) — interactive cross-filtering dashboard
import cudf
import cuxfilter

df = cudf.read_parquet("large_dataset.parquet")
cux_df = cuxfilter.DataFrame.from_dataframe(df)

scatter = cuxfilter.charts.scatter(x="feature1", y="feature2", pixel_shade_type="linear")
bar = cuxfilter.charts.bar("category")
slider = cuxfilter.charts.range_slider("value_col")

d = cux_df.dashboard(
    [scatter, bar],
    sidebar=[slider],
    layout=cuxfilter.layouts.feature_and_base,
    theme=cuxfilter.themes.rapids_dark,
    title="Interactive Explorer",
)
d.app()  # or d.show() for standalone web app
```

### scikit-image 到 cuCIM
```python
# Before (CPU)
from skimage.filters import gaussian, sobel, threshold_otsu
from skimage.morphology import binary_opening, disk
from skimage.measure import label, regionprops_table
import numpy as np

blurred = gaussian(image, sigma=3)
binary = blurred > threshold_otsu(blurred)
cleaned = binary_opening(binary, footprint=disk(3))
labels = label(cleaned)
props = regionprops_table(labels, image, properties=['area', 'centroid'])

# After (GPU) — change imports, wrap input with cp.asarray
from cucim.skimage.filters import gaussian, sobel, threshold_otsu
from cucim.skimage.morphology import binary_opening, disk
from cucim.skimage.measure import label, regionprops_table
import cupy as cp

image_gpu = cp.asarray(image)  # Transfer once
blurred = gaussian(image_gpu, sigma=3)
binary = blurred > threshold_otsu(blurred)
cleaned = binary_opening(binary, footprint=disk(3))
labels = label(cleaned)
props = regionprops_table(labels, image_gpu, properties=['area', 'centroid'])
```

### GeoPandas 到 cuSpatial
```python
# Before (CPU)
import geopandas as gpd
from shapely.geometry import Point

points = gpd.GeoDataFrame(geometry=[Point(x, y) for x, y in coords], crs="EPSG:4326")
polygons = gpd.read_file("regions.geojson")
joined = gpd.sjoin(points, polygons, predicate="within")

# After (GPU) — convert and use cuSpatial
import cuspatial
import cudf

points_cu = cuspatial.from_geopandas(points)
polygons_cu = cuspatial.from_geopandas(polygons)
joined = cuspatial.point_in_polygon(
    points_cu.geometry.x, points_cu.geometry.y,
    polygons_cu.geometry
)
```

### Faiss/Annoy 到 cuVS
```python
# Before (CPU) — Faiss
import faiss
import numpy as np

embeddings = np.random.rand(1_000_000, 128).astype(np.float32)
index = faiss.IndexFlatL2(128)
index.add(embeddings)
distances, neighbors = index.search(queries, k=10)

# After (GPU) — cuVS CAGRA (orders of magnitude faster)
import cupy as cp
from cuvs.neighbors import cagra

embeddings = cp.random.rand(1_000_000, 128, dtype=cp.float32)
index = cagra.build(cagra.IndexParams(), embeddings)
distances, neighbors = cagra.search(cagra.SearchParams(), index, queries, k=10)
```

### scipy.sparse.linalg 到 RAFT
```python
# Before (CPU)
import numpy as np
from scipy.sparse import random as sparse_random
from scipy.sparse.linalg import eigsh

A = sparse_random(10000, 10000, density=0.01, format="csr", dtype=np.float32)
A = A + A.T  # Make symmetric
eigenvalues, eigenvectors = eigsh(A, k=10, which="LM")

# After (GPU) — RAFT sparse eigensolver
import cupy as cp
import cupyx.scipy.sparse as sp_gpu
from pylibraft.sparse.linalg import eigsh as gpu_eigsh

A_gpu = sp_gpu.csr_matrix(A)  # Transfer to GPU
eigenvalues, eigenvectors = gpu_eigsh(A_gpu, k=10, which="LM")
```

## 重要注意事项

- 始终处理没有可用 GPU 的情况 — 提供 CPU fallback 或明确错误消息
- 对照 CPU 结果测试数值正确性（GPU floating point 可能因操作顺序不同而略有差异）
- GPU memory 有限 — 对于大于 GPU memory 的数据集，考虑 chunking 或使用 RAPIDS Dask 进行 multi-GPU
- CUDA Array Interface 支持 CuPy、Numba、Warp、cuDF、cuML、cuGraph、cuVS、cuSpatial、KvikIO、PyTorch 和 JAX arrays 在 GPU 上进行 zero-copy sharing

## Reference 文件

编写任何 GPU 优化代码前，先阅读相关 reference 文件：

| File | 何时阅读 |
|------|-------------|
| `references/cupy.md` | 用户有 NumPy/SciPy 代码，或需要在 GPU 上进行 array operations |
| `references/numba.md` | 用户需要 custom CUDA kernels、细粒度 GPU 控制或 GPU ufuncs |
| `references/cudf.md` | 用户有 pandas 代码，或需要在 GPU 上进行 dataframe operations |
| `references/cuml.md` | 用户有 scikit-learn 代码，或需要在 GPU 上进行 ML training/inference/preprocessing |
| `references/cugraph.md` | 用户有 NetworkX 代码，或需要在 GPU 上进行 graph analytics |
| `references/warp.md` | 用户需要 GPU simulation、spatial computing、mesh/volume queries、differentiable programming 或 robotics |
| `references/kvikio.md` | 用户需要高性能 file IO to/from GPU、GPUDirect Storage、读取 S3/HTTP 到 GPU 或在 GPU 上使用 Zarr |
| `references/cuxfilter.md` | 用户想要 GPU-accelerated interactive dashboards、cross-filtering 或 EDA visualization |
| `references/cucim.md` | 用户有 scikit-image 代码，或需要在 GPU 上进行 image processing、digital pathology 或 WSI reading |
| `references/cuvs.md` | 用户需要在 GPU 上进行 vector search、nearest neighbors、similarity search 或 RAG retrieval |
| `references/cuspatial.md` | 用户有 GeoPandas/shapely 代码，或需要在 GPU 上进行 spatial joins、distance calculations 或 trajectory analysis |
| `references/raft.md` | 用户需要 sparse eigensolvers、device memory management 或 multi-GPU primitives |

编写代码前阅读具体 reference — 它们包含每个库特定的详细 API patterns、optimization techniques 和 pitfalls。
