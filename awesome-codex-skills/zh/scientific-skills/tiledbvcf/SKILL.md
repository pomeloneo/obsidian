---
name: tiledbvcf
description: 使用 TileDB 高效存储和检索基因组变异数据。可扩展的 VCF/BCF 摄取、增量样本添加、压缩存储、并行查询和群体基因组学导出特征。
license: MIT license
metadata:
    skill-author: Jeremy Leipzig
---

# TileDB-VCF

## 概述

TileDB-VCF 是一个高性能 C++ 库，具有 Python 和 CLI 接口，可高效存储和检索基因组变异调用数据。它基于 TileDB 的稀疏阵列技术而构建，可实现 VCF/BCF 文件的可扩展摄取、增量样本添加（无需昂贵的合并操作）以及对本地或云中存储的变体数据进行高效并行查询。

## 何时使用此技能

该技能应该在以下情况下使用：
- 学习 TileDB-VCF 概念和工作流程
- 基因组学分析原型和 pipeline
- 使用中小型数据集（< 1000 个样本）
- 需要将新样本增量添加到现有数据集中
- 需要对许多样本中的特定基因组区域进行高效查询
- 使用云存储的变体数据（S3、Azure、GCS）
- 需要导出大型 VCF 数据集的子集
- 为队列研究建立变异数据库
- 教育项目和方法开发
- 性能对于变量数据操作至关重要

## 快速开始

### 安装

**首选方法：Conda/Mamba**
```bash
# Enter the following two lines if you are on a M1 Mac
CONDA_SUBDIR=osx-64
conda config --env --set subdir osx-64

# Create the conda environment
conda create -n tiledb-vcf "python<3.10"
conda activate tiledb-vcf

# Mamba is a faster and more reliable alternative to conda
conda install -c conda-forge mamba

# Install TileDB-Py and TileDB-VCF, align with other useful libraries
mamba install -y -c conda-forge -c bioconda -c tiledb tiledb-py tiledbvcf-py pandas pyarrow numpy
```

**替代方案：Docker 镜像**
```bash
docker pull tiledb/tiledbvcf-py     # Python interface
docker pull tiledb/tiledbvcf-cli    # Command-line interface
```

### 基本示例

**创建并填充数据集：**
```python
import tiledbvcf

# Create a new dataset
ds = tiledbvcf.Dataset(uri="my_dataset", mode="w",
                      cfg=tiledbvcf.ReadConfig(memory_budget=1024))

# Ingest VCF files (must be single-sample with indexes)
# Requirements:
# - VCFs must be single-sample (not multi-sample)
# - Must have indexes: .csi (bcftools) or .tbi (tabix)
ds.ingest_samples(["sample1.vcf.gz", "sample2.vcf.gz"])
```

**查询变体数据：**
```python
# Open existing dataset for reading
ds = tiledbvcf.Dataset(uri="my_dataset", mode="r")

# Query specific regions and samples
df = ds.read(
    attrs=["sample_name", "pos_start", "pos_end", "alleles", "fmt_GT"],
    regions=["chr1:1000000-2000000", "chr2:500000-1500000"],
    samples=["sample1", "sample2", "sample3"]
)
print(df.head())
```

**导出到 VCF：**
```python
import os

# Export two VCF samples
ds.export(
    regions=["chr21:8220186-8405573"],
    samples=["HG00101", "HG00097"],
    output_format="v",
    output_dir=os.path.expanduser("~"),
)
```

## 核心能力

### 1. 数据集创建和摄取

创建 TileDB-VCF 数据集并从多个 VCF/BCF 文件增量摄取变体数据。这适用于建立群体基因组数据库和队列研究。

**要求：**
- **仅限单样本 VCF**：不支持多样本 VCF
- **需要索引文件**：VCF/BCF 文件必须具有索引（.csi 或 .tbi）

**常用操作：**
- 使用优化的数组模式创建新数据集
- 并行摄取单个或多个 VCF/BCF 文件
- 增量添加新样本，无需重新处理现有数据
- 配置内存使用和压缩设置
- 处理各种 VCF 格式和 INFO/FORMAT 字段
- 恢复中断的摄取过程
- 验证摄取期间的数据完整性


### 2. 高效的查询和过滤

跨基因组区域、样本和变异属性高性能查询变异数据。这适用于关联研究、变异发现和群体分析。

**常用操作：**
- 查询特定基因组区域（单个或多个）
- 按样品名称或样品组过滤
- 提取特定的变异属性（位置、等位基因、基因型、质量）
- 高效访问 INFO 和 FORMAT 字段
- 结合空间和基于属性的过滤
- 流式传输大型查询结果
- 跨样本或区域执行聚合


### 3. 数据导出和互操作性

以各种格式导出数据以进行下游分析或与其他基因组学工具集成。这适用于共享数据集、创建分析子集或提供其他 pipeline。

**常用操作：**
- 导出为标准 VCF/BCF 格式
- 生成具有选定字段的 TSV 文件
- 创建特定于样本/区域的子集
- 维护数据来源和元数据
- 无损数据导出保留所有注释
- 压缩输出格式
- 大型数据集的流式导出


### 4. 群体基因组学工作流程

TileDB-VCF 擅长大规模群体基因组学分析，需要有效访问多个样本和基因组区域的变异数据。

**常见工作流程：**
- 全基因组关联研究（GWAS）数据准备
- 罕见变异负荷测试
- 人口分层分析
- 跨人群等位基因频率计算
- 跨大群体的质量控制
- 变异注释和过滤
- 跨人群比较分析


## 关键概念

### 数组模式和数据模型

**TileDB-VCF 数据模型：**
- 以基因组坐标作为维度存储为稀疏数组的变体
- 样本存储为属性，允许高效的样本特定查询
- 使用原始数据类型保留的 INFO 和 FORMAT 字段
- 自动压缩和分块以实现最佳存储

**架构配置：**
```python
# Custom schema with specific tile extents
config = tiledbvcf.ReadConfig(
    memory_budget=2048,  # MB
    region_partition=(0, 3095677412),  # Full genome
    sample_partition=(0, 10000)  # Up to 10k samples
)
```

### 坐标系和区域

**重要：** TileDB-VCF 使用 **基于 1 的基因组坐标**，遵循 VCF 标准：
- 位置以 1 为基础（第一个基地是位置 1）
- 范围两端均包含在内
- 区域“chr1:1000-2000”包括位置 1000-2000（总共 1001 个碱基）

**区域规范格式：**
```python
# Single region
regions = ["chr1:1000000-2000000"]

# Multiple regions
regions = ["chr1:1000000-2000000", "chr2:500000-1500000"]

# Whole chromosome
regions = ["chr1"]

# BED-style (0-based, half-open converted internally)
regions = ["chr1:999999-2000000"]  # Equivalent to 1-based chr1:1000000-2000000
```

### 内存管理

**性能考虑：**
1. **根据可用系统内存设置适当的内存预算**
2. **对非常大的结果集使用流式查询**
3. **对大量摄取进行分区**以避免内存耗尽
4. **配置图块缓存**以进行重复区域访问
5. **对多个文件使用并行摄取**
6. **通过合并附近区域来优化区域查询**

### 云存储集成

TileDB-VCF 与云存储无缝配合：
```python
# S3 dataset
ds = tiledbvcf.Dataset(uri="s3://bucket/dataset", mode="r")

# Azure Blob Storage
ds = tiledbvcf.Dataset(uri="azure://container/dataset", mode="r")

# Google Cloud Storage
ds = tiledbvcf.Dataset(uri="gcs://bucket/dataset", mode="r")
```

## 常见陷阱

1. **摄取期间内存耗尽：** 对大型 VCF 文件使用适当的内存预算和 batch processing
2. **低效的区域查询：** 合并附近的区域而不是许多单独的查询
3. **缺少样本名称：** 确保 VCF 标头中的样本名称与查询样本规范匹配
4. **坐标系混乱：**记住TileDB-VCF使用基于1的坐标，如VCF标准
5. **大型结果集：** 使用流式处理或分页进行返回数百万个变体的查询
6. **云权限：** 确保云存储访问的正确身份验证
7. **并发访问：**同一数据集的多个写入者可能会导致损坏 - 使用适当的锁定

## CLI 用法

TileDB-VCF 提供了带有以下子命令的命令行界面：

**可用子命令：**
- `create` - 创建一个空的 TileDB-VCF 数据集
- `store` - 将样本提取到 TileDB-VCF 数据集中
- `export` - 从 TileDB-VCF 数据集导出数据
- `list` - 列出 TileDB-VCF 数据集中存在的所有样本名称
- `stat` - 打印有关 TileDB-VCF 数据集的高级统计信息
- `utils` - 用于处理 TileDB-VCF 数据集的实用程序
- `version` - 打印版本信息并退出

```bash
# Create empty dataset
tiledbvcf create --uri my_dataset

# Ingest samples (requires single-sample VCFs with indexes)
tiledbvcf store --uri my_dataset --samples sample1.vcf.gz,sample2.vcf.gz

# Export data
tiledbvcf export --uri my_dataset \
  --regions "chr1:1000000-2000000" \
  --sample-names "sample1,sample2"

# List all samples
tiledbvcf list --uri my_dataset

# Show dataset statistics
tiledbvcf stat --uri my_dataset
```

## 高级特征

### 等位基因频率分析
```python
# Calculate allele frequencies
af_df = tiledbvcf.read_allele_frequency(
    uri="my_dataset",
    regions=["chr1:1000000-2000000"],
    samples=["sample1", "sample2", "sample3"]
)
```

### 样品质量控制
```python
# Perform sample QC
qc_results = tiledbvcf.sample_qc(
    uri="my_dataset",
    samples=["sample1", "sample2"]
)
```

### 自定义配置
```python
# Advanced configuration
config = tiledbvcf.ReadConfig(
    memory_budget=4096,
    tiledb_config={
        "sm.tile_cache_size": "1000000000",
        "vfs.s3.region": "us-east-1"
    }
)
```


## 资源

## 寻求帮助

### 开源 TileDB-VCF 资源

**开源文档：**
- TileDB 学院：https://cloud.tiledb.com/academy/
- 群体基因组学指南：https://cloud.tiledb.com/academy/structure/life-sciences/population-genomics/
- TileDB-VCF GitHub: https://github.com/TileDB-Inc/TileDB-VCF

### TileDB-云资源

**对于大规模/生产基因组学：**
- TileDB-云平台：https://cloud.tiledb.com
- TileDB 学院（所有文档）：https://cloud.tiledb.com/academy/

**开始使用：**
- 免费帐户注册：https://cloud.tiledb.com
- 企业需求联系方式：sales@tiledb.com

## 扩展到 TileDB-云

当您的基因组学工作负载超出单节点处理能力时，TileDB-Cloud 可为生产基因组学 pipeline 提供企业级特征。

**注意**：本节根据可用文档介绍 TileDB-Cloud 特征。有关完整的 API 详细信息和当前特征，请参阅官方 TileDB-Cloud 文档和 API 参考。

### 设置TileDB-云

**1.创建帐户并获取 API token**
```bash
# Sign up at https://cloud.tiledb.com
# Generate API token in your account settings
```

**2.安装TileDB-云Python客户端**
```bash
# Base installation
pip install tiledb-cloud

# With genomics-specific functionality
pip install tiledb-cloud[life-sciences]
```

**3.配置身份验证**
```bash
# Set environment variable with your API token
export TILEDB_REST_TOKEN="your_api_token"
```

```python
import tiledb.cloud

# Authentication is automatic via TILEDB_REST_TOKEN
# No explicit login required in code
```

### 从开源迁移到 TileDB-Cloud

**大规模摄取**
```python
# TileDB-Cloud: Distributed VCF ingestion
import tiledb.cloud.vcf

# Use specialized VCF ingestion module
# Note: Exact API requires TileDB-Cloud documentation
# This represents the available functionality structure
tiledb.cloud.vcf.ingestion.ingest_vcf_dataset(
    source="s3://my-bucket/vcf-files/",
    output="tiledb://my-namespace/large-dataset",
    namespace="my-namespace",
    acn="my-s3-credentials",
    ingest_resources={"cpu": "16", "memory": "64Gi"}
)
```

**分布式查询处理**
```python
# TileDB-Cloud: VCF querying across distributed storage
import tiledb.cloud.vcf
import tiledbvcf

# Define the dataset URI
dataset_uri = "tiledb://TileDB-Inc/gvcf-1kg-dragen-v376"

# Get all samples from the dataset
ds = tiledbvcf.Dataset(dataset_uri, tiledb_config=cfg)
samples = ds.samples()

# Define attributes and ranges to query on
attrs = ["sample_name", "fmt_GT", "fmt_AD", "fmt_DP"]
regions = ["chr13:32396898-32397044", "chr13:32398162-32400268"]

# Perform the read, which is executed in a distributed fashion
df = tiledb.cloud.vcf.read(
    dataset_uri=dataset_uri,
    regions=regions,
    samples=samples,
    attrs=attrs,
    namespace="my-namespace",  # specifies which account to charge
)
df.to_pandas()
```

### 企业特色

**数据共享与协作**
```python
# TileDB-Cloud provides enterprise data sharing capabilities
# through namespace-based permissions and group management

# Access shared datasets via TileDB-Cloud URIs
dataset_uri = "tiledb://shared-namespace/population-study"

# Collaborate through shared notebooks and compute resources
# (Specific API requires TileDB-Cloud documentation)
```

**成本优化**
- **无服务器计算**：仅按实际计算时间付费
- **自动缩放**：根据工作负载自动放大/缩小
- **Spot 实例**：为批处理作业使用成本优化的计算
- **数据分层**：自动热/冷存储管理

**安全性与合规性**
- **端到端加密**：传输中和静态时加密的数据
- **访问控制**：细粒度的权限和审核日志
- **HIPAA/SOC2 合规性**：企业安全标准
- **VPC 支持**：部署在私有云环境中

### 何时迁移清单

✅ **如果您有以下情况，请迁移到 TileDB-Cloud：**
- [ ] 数据集 > 1000 个样本
- [ ] 需要处理 > 100GB 的 VCF 数据
- [ ] 需要分布式计算
- [ ] 多个团队成员需要访问权限
- [ ] 需要企业安全/合规性
- [ ] 想要成本优化的无服务器计算
- [ ] 需要 24/7 生产正常运行时间

### TileDB-云入门

1. **免费开始**：TileDB-Cloud 提供免费评估套餐
2. **迁移支持**：TileDB 团队提供迁移帮助
3. **训练**：访问基因组学特定教程和示例
4. **专业服务**：定制部署和优化

**后续步骤：**
- 访问https://cloud.tiledb.com创建账户
- 查看 https://cloud.tiledb.com/academy/ 的文档
- 企业需求请联系 sales@tiledb.com