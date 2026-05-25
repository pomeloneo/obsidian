---
name: omero-integration
description: 显微镜数据管理平台。通过 Python 访问图像、检索数据集、分析像素、管理 ROI/注释并执行批处理，适用于 high-content screening 和显微镜工作流。
license: Unknown
metadata:
    skill-author: K-Dense Inc.
---

# OMERO 集成

## 概述

OMERO 是一个用于管理、可视化和分析显微镜图像及元数据的开源平台。通过 Python API 访问图像、检索数据集、分析像素、管理 ROI 和注释，适用于 high-content screening 和显微镜工作流。

## 何时使用此技能

此技能适用于：
- 使用 OMERO Python API (omero-py) 访问显微镜数据
- 以编程方式检索图像、数据集、项目或 screening 数据
- 分析像素数据并创建派生图像
- 在显微镜图像上创建或管理 ROI (regions of interest)
- 向 OMERO 对象添加注释、标签或元数据
- 在 OMERO tables 中存储测量结果
- 创建用于批处理的服务器端脚本
- 执行 high-content screening 分析

## 核心能力

此技能覆盖八个主要能力领域。每个领域都在 references/ 目录中有详细文档：

### 1. 连接与会话管理
**文件**: `references/connection.md`

建立与 OMERO 服务器的安全连接，管理会话，处理身份验证，并使用组上下文。用于初始设置和连接模式。

**常见场景：**
- 使用凭据连接到 OMERO server
- 使用现有 session IDs
- 在组上下文之间切换
- 使用 context managers 管理连接生命周期

### 2. 数据访问与检索
**文件**: `references/data_access.md`

浏览 OMERO 的层级数据结构 (Projects → Datasets → Images) 和 screening 数据 (Screens → Plates → Wells)。检索对象，按属性查询，并访问元数据。

**常见场景：**
- 列出用户的所有项目和数据集
- 按 ID 或数据集检索图像
- 访问 screening plate 数据
- 使用过滤器查询对象

### 3. 元数据与注释
**文件**: `references/metadata.md`

创建和管理注释，包括标签、键值对、文件附件和评论。将注释链接到图像、数据集或其他对象。

**常见场景：**
- 向图像添加标签
- 将分析结果作为文件附加
- 创建自定义键值元数据
- 按 namespace 查询注释

### 4. 图像处理与渲染
**文件**: `references/image_processing.md`

以 NumPy arrays 访问原始像素数据，操作渲染设置，创建派生图像，并管理物理尺寸。

**常见场景：**
- 提取像素数据用于计算分析
- 生成缩略图
- 创建最大强度投影
- 修改通道渲染设置

### 5. 感兴趣区域 (ROIs)
**文件**: `references/rois.md`

使用各种形状（矩形、椭圆、多边形、mask、点、线）创建、检索和分析 ROI。从 ROI 区域提取强度统计。

**常见场景：**
- 在图像上绘制矩形 ROI
- 为分割创建 polygon masks
- 分析 ROI 内的像素强度
- 导出 ROI 坐标

### 6. OMERO 表
**文件**: `references/tables.md`

存储和查询与 OMERO 对象关联的结构化表格数据。适用于分析结果、测量值和元数据。

**常见场景：**
- 存储图像的定量测量值
- 创建包含多种列类型的表
- 使用条件查询表数据
- 将表链接到特定图像或数据集

### 7. 脚本与批量操作
**文件**: `references/scripts.md`

创建在服务器端运行的 OMERO.scripts，用于批处理、自动化工作流以及与 OMERO clients 集成。

**常见场景：**
- 批量处理多张图像
- 创建自动化分析流水线
- 跨数据集生成汇总统计
- 以自定义格式导出数据

### 8. 高级功能
**文件**: `references/advanced.md`

涵盖权限、filesets、跨组查询、删除操作以及其他高级功能。

**常见场景：**
- 处理组权限
- 访问原始导入文件
- 执行跨组查询
- 使用 callbacks 删除对象

## 安装

```bash
uv pip install omero-py
```

**要求：**
- Python 3.7+
- Zeroc Ice 3.6+
- 可访问 OMERO server（host、port、credentials）

## 快速开始

基本连接模式：

```python
from omero.gateway import BlitzGateway

# Connect to OMERO server
conn = BlitzGateway(username, password, host=host, port=port)
connected = conn.connect()

if connected:
    # Perform operations
    for project in conn.listProjects():
        print(project.getName())

    # Always close connection
    conn.close()
else:
    print("Connection failed")
```

**使用 context manager 的推荐模式：**

```python
from omero.gateway import BlitzGateway

with BlitzGateway(username, password, host=host, port=port) as conn:
    # Connection automatically managed
    for project in conn.listProjects():
        print(project.getName())
    # Automatically closed on exit
```

## 选择合适的能力

**用于数据探索：**
- 从 `references/connection.md` 开始建立连接
- 使用 `references/data_access.md` 浏览层级结构
- 查看 `references/metadata.md` 了解注释细节

**用于图像分析：**
- 使用 `references/image_processing.md` 访问像素数据
- 使用 `references/rois.md` 进行基于区域的分析
- 使用 `references/tables.md` 存储结果

**用于自动化：**
- 使用 `references/scripts.md` 进行服务器端处理
- 使用 `references/data_access.md` 进行批量数据检索

**用于高级操作：**
- 使用 `references/advanced.md` 处理权限和删除
- 查看 `references/connection.md` 了解跨组查询

## 常见工作流

### 工作流 1：检索并分析图像

1. 连接到 OMERO server (`references/connection.md`)
2. 导航到数据集 (`references/data_access.md`)
3. 从数据集中检索图像 (`references/data_access.md`)
4. 以 NumPy array 访问像素数据 (`references/image_processing.md`)
5. 执行分析
6. 将结果存储为表或文件注释 (`references/tables.md` 或 `references/metadata.md`)

### 工作流 2：批量 ROI 分析

1. 连接到 OMERO server
2. 检索已有 ROI 的图像 (`references/rois.md`)
3. 对每张图像，获取 ROI shapes
4. 提取 ROI 内的像素强度 (`references/rois.md`)
5. 将测量值存储到 OMERO table (`references/tables.md`)

### 工作流 3：创建分析脚本

1. 设计分析工作流
2. 使用 OMERO.scripts framework (`references/scripts.md`)
3. 通过脚本参数访问数据
4. 批量处理图像
5. 生成输出（新图像、表、文件）

## 错误处理

始终将 OMERO 操作包裹在 try-except 块中，并确保正确关闭连接：

```python
from omero.gateway import BlitzGateway
import traceback

try:
    conn = BlitzGateway(username, password, host=host, port=port)
    if not conn.connect():
        raise Exception("Connection failed")

    # Perform operations

except Exception as e:
    print(f"Error: {e}")
    traceback.print_exc()
finally:
    if conn:
        conn.close()
```

## 其他资源

- **官方文档**: https://omero.readthedocs.io/en/stable/developers/Python.html
- **BlitzGateway API**: https://omero.readthedocs.io/en/stable/developers/Python.html#omero-blitzgateway
- **OMERO Model**: https://omero.readthedocs.io/en/stable/developers/Model.html
- **社区论坛**: https://forum.image.sc/tag/omero

## 注意事项

- OMERO 使用基于组的权限 (READ-ONLY, READ-ANNOTATE, READ-WRITE)
- OMERO 中的图像按层级组织：Project > Dataset > Image
- Screening 数据使用：Screen > Plate > Well > WellSample > Image
- 始终关闭连接以释放服务器资源
- 使用 context managers 进行自动资源管理
- 像素数据会作为 NumPy arrays 返回用于分析
