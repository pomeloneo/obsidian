---
name: latchbio-integration
description: "用于生物信息学工作流程的Latch平台。使用Latch SDK、@workflow/@task 装饰器构建管道，部署无服务器工作流程、LatchFile/LatchDir、Nextflow/Snakemake集成。"
license: Unknown
metadata:
    skill-author: K-Dense Inc.
---

# LatchBio集成

## 概述

Latch是一个 Python 框架，用于将生物信息学工作流程构建和部署为无服务器管道。基于Flyte构建，使用@workflow/@task装饰器创建工作流，使用LatchFile/LatchDir管理云数据，配置资源并集成Nextflow/Snakemake管道。

## 核心功能

Latch平台提供四个主要功能领域：

### 1. 工作流创建和部署
- 使用 Python 装饰器定义无服务器工作流
- 支持原生 Python、Nextflow、和Snakemake管道
- 使用Docker自动容器化
- 自动生成的无代码用户界面
- 版本控制和可重复性

### 2. 数据管理
- 云存储抽象（LatchFile、LatchDir）
- 使用Registry进行结构化数据组织（项目 → 表 → 记录）
- 使用链接和枚举进行类型安全的数据操作
- 本地和云端之间的自动文件传输
- 用于文件选择的全局模式匹配

### 3. 资源配置
- 预配置的任务装饰器(@small_task, @large_task, @small_gpu_task, @large_gpu_task)
- 自定义资源规格（CPU、内存、GPU、存储）
- GPU支持（K80、V100、A100）
- 超时和存储配置
- 成本优化策略

### 4. 验证工作流程
- 生产就绪的预构建管道
- Bulk RNA-seq、DESeq2、通路分析
- 用于蛋白质结构预测的AlphaFold和ColabFold
- 单细胞工具(ArchR、scVelo、emptyDropsR)
- CRISPR 分析、系统发育学等

## 快速入门

### 安装和设置

```bash
# Install Latch SDK
uv pip install latch

# Login to Latch
latch login

# Initialize a new workflow
latch init my-workflow

# Register workflow to platform
latch register my-workflow
```

**先决条件：**
- Docker安装并运行
- Latch帐户凭据
- Python 3.8+

### 基本工作流程示例

```python
from latch import workflow, small_task
from latch.types import LatchFile

@small_task
def process_file(input_file: LatchFile) -> LatchFile:
    """Process a single file"""
    # Processing logic
    return output_file

@workflow
def my_workflow(input_file: LatchFile) -> LatchFile:
    """
    My bioinformatics workflow

    Args:
        input_file: Input data file
    """
    return process_file(input_file=input_file)
```

## 何时使用此技能

当遇到以下任何场景时应使用此技能：

**工作流程开发：**
- “创建Latch工作流程以进行RNA-seq分析”
- “将我的管道部署到Latch"
- "将我的Nextflow管道转换为Latch"
- "将GPU支持添加到我的工作流程中"
- 使用`@workflow`、`@task`装饰器

**数据管理：**
- “在Latch Registry中组织我的测序数据”
- “如何使用LatchFile和LatchDir？”
- “在Latch中设置样本跟踪”
- 使用`latch:///`路径

**资源配置：**
- “在Latch上为GPU配置GPU”
- “我的任务正在运行内存不足”
- “如何优化工作流程成本？”
- 使用任务装饰器

**验证的工作流程：**
- “在Latch上运行AlphaFold”
- “使用DESeq2进行差异表达”
- “可用的预构建工作流程”
- 使用`latch.verified`模块

## 详细文档

该技能包括按功能组织的综合参考文档：

### references/workflow-creation.md
**阅读此内容：**
- 创建和注册工作流程
- 任务定义和装饰器
- 支持 Python、Nextflow、Snakemake
- 启动计划和条件部分
- 工作流程执行（CLI 和编程）
- 多步骤和并行管道
- 解决注册问题

**关键主题：**
- `latch init`和`latch register`命令
- `@workflow`和`@task`装饰器
- LatchFile和LatchDir基础知识
- 类型注释和文档字符串
- 使用预设参数启动计划
- 条件 UI 部分

### references/data-management.md
**阅读此内容：**
- 使用LatchFile和LatchDir的云存储
- Registry系统（项目、表、记录）
- 链接记录和关系
- 枚举和类型化列
- 批量操作和事务
- 与工作流程集成
- 帐户和工作区管理

**关键主题：**
- `latch:///`路径格式
- 文件传输和 glob 模式
- 创建和查询Registry表
- 列类型（字符串、数字、文件、链接、枚举）
- 记录 CRUD 操作
- 工作流-Registry集成

### references/resource-configuration.md
**阅读此内容：**
- 任务资源装饰器
- 自定义 CPU，内存、GPU配置
- GPU类型（K80、V100、A100）
- 超时和存储设置
- 资源优化策略
- 经济高效的工作流程设计
- 监控和调试

**关键主题：**
- `@small_task`、`@large_task`、`@small_gpu_task`、`@large_gpu_task`
- 具有精确规格的`@custom_task`
- 多GPU配置
- 按工作负载类型选择资源
- 平台限制和配额

### 引用/verified-workflows.md
**阅读此内容：**
- 预构建的生产工作流程
- Bulk RNA-seq和DESeq2
- AlphaFold和ColabFold
- 单细胞分析（ArchR、scVelo）
- CRISPR 编辑分析
- 通路富集
- 与自定义工作流程集成

**关键主题：**
- `latch.verified`模块导入
- 可用的已验证工作流程
- 工作流程参数和选项
- 组合已验证步骤和自定义步骤
- 版本管理

## 常见工作流程模式

### 完成RNA-seq管道

```python
from latch import workflow, small_task, large_task
from latch.types import LatchFile, LatchDir

@small_task
def quality_control(fastq: LatchFile) -> LatchFile:
    """Run FastQC"""
    return qc_output

@large_task
def alignment(fastq: LatchFile, genome: str) -> LatchFile:
    """STAR alignment"""
    return bam_output

@small_task
def quantification(bam: LatchFile) -> LatchFile:
    """featureCounts"""
    return counts

@workflow
def rnaseq_pipeline(
    input_fastq: LatchFile,
    genome: str,
    output_dir: LatchDir
) -> LatchFile:
    """RNA-seq analysis pipeline"""
    qc = quality_control(fastq=input_fastq)
    aligned = alignment(fastq=qc, genome=genome)
    return quantification(bam=aligned)
```

### GPU-加速工作流程

```python
from latch import workflow, small_task, large_gpu_task
from latch.types import LatchFile

@small_task
def preprocess(input_file: LatchFile) -> LatchFile:
    """Prepare data"""
    return processed

@large_gpu_task
def gpu_computation(data: LatchFile) -> LatchFile:
    """GPU-accelerated analysis"""
    return results

@workflow
def gpu_pipeline(input_file: LatchFile) -> LatchFile:
    """Pipeline with GPU tasks"""
    preprocessed = preprocess(input_file=input_file)
    return gpu_computation(data=preprocessed)
```

### Registry-集成工作流程

```python
from latch import workflow, small_task
from latch.registry.table import Table
from latch.registry.record import Record
from latch.types import LatchFile

@small_task
def process_and_track(sample_id: str, table_id: str) -> str:
    """Process sample and update Registry"""
    # Get sample from registry
    table = Table.get(table_id=table_id)
    records = Record.list(table_id=table_id, filter={"sample_id": sample_id})
    sample = records[0]

    # Process
    input_file = sample.values["fastq_file"]
    output = process(input_file)

    # Update registry
    sample.update(values={"status": "completed", "result": output})
    return "Success"

@workflow
def registry_workflow(sample_id: str, table_id: str):
    """Workflow integrated with Registry"""
    return process_and_track(sample_id=sample_id, table_id=table_id)
```

## 最佳实践

### 工作流程设计
1. 对所有参数使用类型注释
2. 编写清晰的文档字符串（出现在 UI 中）
3. 从标准任务装饰器开始，根据需要进行扩展
4. 将复杂的工作流程分解为模块化任务
5. 实施正确的错误处理

### 数据管理
6. 使用一致的文件夹结构
7. 在批量输入之前定义Registry架构
8. 使用关系的链接记录
9. 将元数据存储在Registry中以实现可追溯性

### 资源配置
10. 适当大小的资源（不要过度分配）
11. 仅当算法支持时才使用GPU
12. 监控执行指标并优化
13. 尽可能设计并行执行

### 开发工作流程
14. 注册前使用Docker进行本地测试
15. 对工作流程代码使用版本控制
16. 记录资源需求
17. 配置工作流程以确定实际需求

## 故障排除

### 常见问题

**注册失败：**
- 确保Docker正在运行
- 使用`latch login`检查身份验证
- 验证 Dockerfile 中的所有依赖项
- 使用`--verbose`标志查看详细日志

**资源问题：**
- 内存不足：增加内存任务装饰器
- 超时：增加超时参数
- 存储问题：增加临时 storage_gib

**数据访问：**
- 使用正确的`latch:///`路径格式
- 验证工作区中是否存在文件
- 检查共享工作区的权限

**类型错误：**
- 为所有参数添加类型注释
- 对文件/目录参数使用LatchFile/LatchDir
- 确保工作流返回类型与实际返回匹配

## 其他资源

- **官方文档**：https://docs.latch.bio
- **GitHub 存储库**：https://github.com/latchbio/latch
- **Slack 社区**：加入Latch SDK工作区
- **API参考**：https://docs.latch.bio/api/latch.html
- **博客**：https://blog.latch.bio

## 支持

如有问题或疑问：
1. 检查
上面的文档链接 2. 搜索 GitHub 问题
3. 在 Slack 社区提问
4. 联系 support@latch.bio

