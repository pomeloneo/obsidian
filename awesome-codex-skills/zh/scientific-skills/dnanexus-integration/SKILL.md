---
name: dnanexus-integration
description: DNAnexus cloud genomics platform。构建 apps/applets，管理数据（upload/download），使用 dxpy Python SDK，运行 workflows，处理 FASTQ/BAM/VCF，用于 genomics pipeline 的开发与执行。
license: Unknown
compatibility: Requires a DNAnexus account
metadata:
    skill-author: K-Dense Inc.
---

# DNAnexus Integration

## 概述

DNAnexus 是一个面向生物医学数据分析和 genomics 的云平台。可构建和部署 apps/applets、管理 data objects、运行 workflows，并使用 dxpy Python SDK 进行 genomics pipeline 开发和执行。

## 何时使用此 Skill

以下情况应使用此 skill：
- 创建、构建或修改 DNAnexus apps/applets
- 上传、下载、搜索或组织 files 和 records
- 运行 analyses、监控 jobs、创建 workflows
- 编写使用 dxpy 与平台交互的脚本
- 设置 dxapp.json、管理依赖、使用 Docker
- 处理 FASTQ、BAM、VCF 或其他 bioinformatics 文件
- 管理 projects、permissions 或 platform resources

## 核心能力

此 skill 分为五个主要领域，每个领域都有详细参考文档：

### 1. App Development

**目的**：创建在 DNAnexus 平台上运行的可执行程序（apps/applets）。

**关键操作**：
- 使用 `dx-app-wizard` 生成 app skeleton
- 使用正确 entry points 编写 Python 或 Bash apps
- 处理 input/output data objects
- 用 `dx build` 或 `dx build --app` 部署
- 在平台上测试 apps

**常见使用场景**：
- Bioinformatics pipelines（alignment、variant calling）
- 数据处理 workflows
- 质量控制和过滤
- 格式转换工具

**参考**：查看 `references/app-development.md` 获取：
- 完整 app 结构和模式
- Python entry point decorators
- 使用 dxpy 的 input/output 处理
- 开发最佳实践
- 常见问题和解决方案

### 2. Data Operations

**目的**：管理平台上的 files、records 和其他 data objects。

**关键操作**：
- 使用 `dxpy.upload_local_file()` 和 `dxpy.download_dxfile()` 上传/下载文件
- 创建并管理带 metadata 的 records
- 按名称、properties 或 type 搜索 data objects
- 在 projects 之间 clone data
- 管理 project folders 和 permissions

**常见使用场景**：
- 上传 sequencing data（FASTQ files）
- 组织分析结果
- 搜索特定 samples 或 experiments
- 跨 projects 备份数据
- 管理 reference genomes 和 annotations

**参考**：查看 `references/data-operations.md` 获取：
- 完整 file 和 record 操作
- Data object 生命周期（open/closed states）
- Search 和 discovery 模式
- Project 管理
- Batch operations

### 3. Job Execution

**目的**：运行 analyses、监控执行并编排 workflows。

**关键操作**：
- 用 `applet.run()` 或 `app.run()` 启动 jobs
- 监控 job status 和 logs
- 创建 subjobs 进行并行处理
- 构建并运行 multi-step workflows
- 使用 output references 串联 jobs

**常见使用场景**：
- 在 sequencing data 上运行 genomics analyses
- 对多个 samples 并行处理
- Multi-step analysis pipelines
- 监控长时间运行的 computations
- 调试失败 jobs

**参考**：查看 `references/job-execution.md` 获取：
- 完整 job 生命周期和 states
- Workflow 创建与编排
- 并行执行模式
- Job 监控和调试
- Resource management

### 4. Python SDK (dxpy)

**目的**：通过 Python 程序化访问 DNAnexus 平台。

**关键操作**：
- 使用 data object handlers（DXFile、DXRecord、DXApplet 等）
- 使用高级函数执行常见任务
- 对高级操作发起直接 API calls
- 在 objects 之间创建 links 和 references
- 搜索并发现 platform resources

**常见使用场景**：
- 数据管理自动化脚本
- 自定义 analysis pipelines
- Batch processing workflows
- 与外部工具集成
- 数据迁移和组织

**参考**：查看 `references/python-sdk.md` 获取：
- 完整 dxpy class reference
- 高级 utility functions
- API method 文档
- Error handling 模式
- 常见 code patterns

### 5. Configuration and Dependencies

**目的**：配置 app metadata 并管理 dependencies。

**关键操作**：
- 编写包含 inputs、outputs 和 run specs 的 dxapp.json
- 安装系统包（execDepends）
- 打包自定义工具和资源
- 使用 assets 共享 dependencies
- 集成 Docker containers
- 配置 instance types 和 timeouts

**常见使用场景**：
- 定义 app input/output specifications
- 安装 bioinformatics tools（samtools、bwa 等）
- 管理 Python package dependencies
- 对复杂环境使用 Docker images
- 选择计算资源

**参考**：查看 `references/configuration.md` 获取：
- 完整 dxapp.json specification
- Dependency management 策略
- Docker integration 模式
- Regional 和 resource configuration
- 示例配置

## Quick Start 示例

### 上传并分析数据

```python
import dxpy

# Upload input file
input_file = dxpy.upload_local_file("sample.fastq", project="project-xxxx")

# Run analysis
job = dxpy.DXApplet("applet-xxxx").run({
    "reads": dxpy.dxlink(input_file.get_id())
})

# Wait for completion
job.wait_on_done()

# Download results
output_id = job.describe()["output"]["aligned_reads"]["$dnanexus_link"]
dxpy.download_dxfile(output_id, "aligned.bam")
```

### 搜索并下载文件

```python
import dxpy

# Find BAM files from a specific experiment
files = dxpy.find_data_objects(
    classname="file",
    name="*.bam",
    properties={"experiment": "exp001"},
    project="project-xxxx"
)

# Download each file
for file_result in files:
    file_obj = dxpy.DXFile(file_result["id"])
    filename = file_obj.describe()["name"]
    dxpy.download_dxfile(file_result["id"], filename)
```

### 创建简单 App

```python
# src/my-app.py
import dxpy
import subprocess

@dxpy.entry_point('main')
def main(input_file, quality_threshold=30):
    # Download input
    dxpy.download_dxfile(input_file["$dnanexus_link"], "input.fastq")

    # Process
    subprocess.check_call([
        "quality_filter",
        "--input", "input.fastq",
        "--output", "filtered.fastq",
        "--threshold", str(quality_threshold)
    ])

    # Upload output
    output_file = dxpy.upload_local_file("filtered.fastq")

    return {
        "filtered_reads": dxpy.dxlink(output_file)
    }

dxpy.run()
```

## Workflow 决策树

使用 DNAnexus 时，遵循此决策树：

1. **需要创建新的 executable？**
   - 是 → 使用 **App Development**（references/app-development.md）
   - 否 → 继续第 2 步

2. **需要管理 files 或 data？**
   - 是 → 使用 **Data Operations**（references/data-operations.md）
   - 否 → 继续第 3 步

3. **需要运行 analysis 或 workflow？**
   - 是 → 使用 **Job Execution**（references/job-execution.md）
   - 否 → 继续第 4 步

4. **正在编写用于自动化的 Python scripts？**
   - 是 → 使用 **Python SDK**（references/python-sdk.md）
   - 否 → 继续第 5 步

5. **正在配置 app settings 或 dependencies？**
   - 是 → 使用 **Configuration**（references/configuration.md）

你通常会需要组合多种能力（例如 app development + configuration，或 data operations + job execution）。

## 安装和认证

### 安装 dxpy

```bash
uv pip install dxpy
```

### 登录 DNAnexus

```bash
dx login
```

这会认证你的 session，并设置对 projects 和 data 的访问。

### 验证安装

```bash
dx --version
dx whoami
```

## 常见模式

### Pattern 1：Batch Processing

用同一个 analysis 处理多个文件：

```python
# Find all FASTQ files
files = dxpy.find_data_objects(
    classname="file",
    name="*.fastq",
    project="project-xxxx"
)

# Launch parallel jobs
jobs = []
for file_result in files:
    job = dxpy.DXApplet("applet-xxxx").run({
        "input": dxpy.dxlink(file_result["id"])
    })
    jobs.append(job)

# Wait for all completions
for job in jobs:
    job.wait_on_done()
```

### Pattern 2：Multi-Step Pipeline

将多个 analyses 串联在一起：

```python
# Step 1: Quality control
qc_job = qc_applet.run({"reads": input_file})

# Step 2: Alignment (uses QC output)
align_job = align_applet.run({
    "reads": qc_job.get_output_ref("filtered_reads")
})

# Step 3: Variant calling (uses alignment output)
variant_job = variant_applet.run({
    "bam": align_job.get_output_ref("aligned_bam")
})
```

### Pattern 3：Data Organization

系统化组织 analysis results：

```python
# Create organized folder structure
dxpy.api.project_new_folder(
    "project-xxxx",
    {"folder": "/experiments/exp001/results", "parents": True}
)

# Upload with metadata
result_file = dxpy.upload_local_file(
    "results.txt",
    project="project-xxxx",
    folder="/experiments/exp001/results",
    properties={
        "experiment": "exp001",
        "sample": "sample1",
        "analysis_date": "2025-10-20"
    },
    tags=["validated", "published"]
)
```

## 最佳实践

1. **Error Handling**：始终用 try-except blocks 包裹 API calls
2. **Resource Management**：为 workloads 选择合适的 instance types
3. **Data Organization**：使用一致的 folder structures 和 metadata
4. **Cost Optimization**：归档旧数据，使用合适的 storage classes
5. **Documentation**：在 dxapp.json 中包含清晰描述
6. **Testing**：生产使用前用各种 input types 测试 apps
7. **Version Control**：对 apps 使用 semantic versioning
8. **Security**：永远不要在 source code 中硬编码 credentials
9. **Logging**：包含有助于调试的信息性 log messages
10. **Cleanup**：删除 temporary files 和 failed jobs

## 资源

此 skill 包含详细参考文档：

### references/

- **app-development.md** - 构建和部署 apps/applets 的完整指南
- **data-operations.md** - File management、records、search 和 project operations
- **job-execution.md** - Running jobs、workflows、monitoring 和 parallel processing
- **python-sdk.md** - 带所有 classes 和 functions 的完整 dxpy library reference
- **configuration.md** - dxapp.json specification 和 dependency management

当需要特定操作的详细信息，或处理复杂任务时，加载这些 references。

## 获取帮助

- Official documentation: https://documentation.dnanexus.com/
- API reference: http://autodoc.dnanexus.com/
- GitHub repository: https://github.com/dnanexus/dx-toolkit
- Support: support@dnanexus.com
