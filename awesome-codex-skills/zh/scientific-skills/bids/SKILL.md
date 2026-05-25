---
name: bids
description: >
  处理 Brain Imaging Data Structure (BIDS) 数据集时使用此技能：
  组织神经科学和生物医学数据（MRI、EEG、MEG、iEEG、PET、microscopy、
  NIRS、motion capture、EMG、MR spectroscopy、behavioral），查询 BIDS layouts，
  验证合规性，将 DICOM 转换为 BIDS，编写 metadata sidecars，或
  创建 BIDS derivatives。
license: https://creativecommons.org/licenses/by/4.0/
metadata:
    skill-author: Yaroslav Halchenko
---

# 脑成像数据结构（BIDS）

## 概述

脑成像数据结构 (BIDS) 是用于组织和描述神经科学和生物医学研究数据集的社区标准。它定义了一致的文件命名约定、目录层次结构和元数据模式，以便人类和软件工具可以立即理解数据集。 BIDS受BIDS规范（当前为v1.11.x）管辖，并由社区通过BIDS标准GitHub组织进行维护。

虽然BIDS起源于MRI，但它的发展已经远远超出了神经影像学的范围。该规范目前涵盖 11 种模式，涵盖成像、电生理学和行为数据：

- **成像**：MRI（结构、功能、扩散、场图、perfusion/ASL）、PET、显微镜
- **电生理学**：EEG、MEG、iEEG（颅内EEG）、EMG
- **其他**：NIRS（近红外光谱）、动作捕捉、行为数据（无成像）、MR光谱

Active BEPs 正在进一步扩展 BIDS — 特别是 BEP032（微电极电生理学）将增加对包括 Neuropixel 探针在内的细胞外记录的支持，将 BIDS 引入动物神经科学研究中的流行方法（另请参阅神经像素分析技能）。

主要数据存储库（OpenNeuro、DANDI）、领先期刊（NeuroImage、人脑图谱、科学数据）和资助机构（NIH、ERC）要求或强烈鼓励采用。

BIDS的Python生态系统以**PyBIDS** (`pybids`)为中心，用于查询和索引BIDS数据集，以及**bids-validator**（基于Deno，可作为PyPI包使用） `bids-validator-deno` 或直接通过 Deno）进行合规性检查。从 DICOM 的转换通常使用 **HeuDiConv**、**dcm2bids** 或 **BIDScoin** 完成。

## 何时使用此技能

在以下情况下应用此技能：
- 将原始神经科学数据（成像、电生理学、行为）组织到BIDS兼容的目录结构中
- 查询现有的BIDS数据集以按主题、会话、任务、运行或模式查找特定文件
- 在共享或提交之前根据BIDS规范验证数据集
- 将扫描仪中的DICOM数据转换为BIDS格式
- 编写或编辑 JSON sidecar 元数据文件
- 创建BIDS兼容的衍生品（预处理数据、分析输出）
- 为新数据集设置`dataset_description.json`
- 使用 BIDS 实体（主题、会话、任务、获取、运行等）
- 配置 `.bidsignore` 以从验证中排除文件
- 准备数据上传到OpenNeuro、DANDI或其他BIDS感知存储库

## 安装

```bash
# Core BIDS querying library
uv pip install pybids

# BIDS validator (Deno-based, installed via PyPI wrapper)
uv pip install bids-validator-deno
# Alternative: install directly via Deno
# deno install -g -A npm:bids-validator

# DICOM-to-BIDS converters (install as needed)
uv pip install heudiconv       # HeuDiConv - heuristic-based DICOM conversion
uv pip install dcm2bids        # dcm2bids - config-file-based conversion
# BIDScoin: uv pip install bidscoin

# Useful companions
uv pip install nibabel          # NIfTI/other neuroimaging file I/O
uv pip install pydicom          # DICOM file reading (used by converters)
```

## 核心工作流程

### 1. BIDS 目录结构

最小的BIDS数据集遵循以下布局：

```
my_dataset/
  dataset_description.json      # Required: name, BIDSVersion, etc.
  participants.tsv              # Recommended: subject-level phenotypic data
  participants.json             # Recommended: column descriptions
  README                        # Recommended: dataset documentation
  CHANGES                       # Recommended: version history
  .bidsignore                   # Optional: patterns to exclude from validation
  sub-01/
    anat/
      sub-01_T1w.nii.gz
      sub-01_T1w.json           # Sidecar metadata
    func/
      sub-01_task-rest_bold.nii.gz
      sub-01_task-rest_bold.json
      sub-01_task-rest_events.tsv     # Event timing for task fMRI
      sub-01_task-rest_events.json
    dwi/
      sub-01_dwi.nii.gz
      sub-01_dwi.json
      sub-01_dwi.bvec
      sub-01_dwi.bval
    fmap/
      sub-01_phasediff.nii.gz
      sub-01_phasediff.json
      sub-01_magnitude1.nii.gz
    perf/
      sub-01_asl.nii.gz
      sub-01_asl.json
  sub-01/
    ses-pre/
      anat/
        sub-01_ses-pre_T1w.nii.gz
      func/
        sub-01_ses-pre_task-nback_bold.nii.gz
    ses-post/
      ...
```

**要点**：
- 每个NIfTI文件应该有一个对应的`.json` sidecar
- 文件名编码实体：`sub-<label>[_ses-<label>][_task-<label>][_acq-<label>][_run-<index>]_<suffix>.<extension>`
- 文件名中的实体顺序由规范固定
- 根级别仅严格要求`dataset_description.json`

### 2. 创建dataset_description.json

```python
import json

dataset_description = {
    "Name": "My Neuroimaging Study",
    "BIDSVersion": "1.10.0",
    "DatasetType": "raw",
    "License": "CC0",
    "Authors": ["First Author", "Second Author"],
    "Acknowledgements": "Funded by NIH R01-MH123456",
    "HowToAcknowledge": "Please cite: Author et al. (2025) Journal Name.",
    "Funding": ["NIH R01-MH123456", "NSF BCS-7654321"],
    "ReferencesAndLinks": ["https://doi.org/10.xxxx/xxxxx"],
    "DatasetDOI": "10.18112/openneuro.ds000001.v1.0.0",
    "GeneratedBy": [
        {
            "Name": "HeuDiConv",
            "Version": "1.3.1",
            "CodeURL": "https://github.com/nipy/heudiconv"
        }
    ]
}

with open("dataset_description.json", "w") as f:
    json.dump(dataset_description, f, indent=4)
```

对于 **衍生品**，设置 `"DatasetType": "derivative"` 并添加 `"GeneratedBy"` 列出管道：

```python
deriv_description = {
    "Name": "fMRIPrep - fMRI PREProcessing",
    "BIDSVersion": "1.10.0",
    "DatasetType": "derivative",
    "GeneratedBy": [
        {
            "Name": "fMRIPrep",
            "Version": "24.1.0",
            "CodeURL": "https://github.com/nipreps/fmriprep"
        }
    ]
}
```

### 3. 查询BIDS包含PyBIDS的数据集

```python
from bids import BIDSLayout

# Index a BIDS dataset (validates structure on load)
layout = BIDSLayout("/path/to/bids_dataset")

# Basic queries
subjects = layout.get_subjects()          # ['01', '02', '03', ...]
sessions = layout.get_sessions()          # ['pre', 'post'] or []
tasks = layout.get_tasks()                # ['rest', 'nback']
runs = layout.get_runs()                  # [1, 2] or []

# Find specific files
bold_files = layout.get(
    suffix="bold",
    extension=".nii.gz",
    return_type="filename"
)

# Filter by subject, task, session
nback_sub01 = layout.get(
    subject="01",
    task="nback",
    suffix="bold",
    extension=".nii.gz",
    return_type="filename"
)

# Get metadata from JSON sidecars (automatic inheritance)
metadata = layout.get_metadata("/path/to/sub-01/func/sub-01_task-rest_bold.nii.gz")
tr = metadata["RepetitionTime"]

# Get all entities for a file
entities = layout.get_entities()

# Build a path from entities using BIDSLayout
bids_file = layout.get(subject="01", suffix="T1w", extension=".nii.gz")[0]
print(bids_file.path)
print(bids_file.get_entities())
```

**要点**：
- `BIDSLayout` 在初始化时索引整个数据集；对于大型数据集，使用`database_path`来缓存索引
- 元数据继承：较高级别（e.g.，根或主题）的JSON sidecar 被下面的所有文件继承，除非被覆盖
- 使用 `return_type="filename"` 获取路径，使用 `return_type="object"`（默认）获取 `BIDSFile` 对象

### 4. 验证BIDS数据集

#### 通过 PyPI 使用出价验证器（推荐）

`bids-validator-deno` PyPI 包将基于 Deno 的验证器捆绑为独立的 CLI：

```bash
# Install
uv pip install bids-validator-deno

# Validate a dataset
bids-validator /path/to/bids_dataset

# Ignore specific warnings/errors
bids-validator /path/to/bids_dataset --ignoreNiftiHeaders --ignoreSubjectConsistency
```

#### 直接通过 Deno 使用 bids-validator

如果 Deno 已经可用，您可以在没有 PyPI 的情况下安装或运行验证器：

```bash
# Install globally via Deno
deno install -g -A npm:bids-validator

# Or run without installing
deno run -A npm:bids-validator /path/to/bids_dataset
```

#### 旧版 Node.js 验证器

旧的基于 Node.js 的验证器 (`npm install -g bids-validator`) 已被弃用，取而代之的是基于 Deno 的版本。 Deno 版本是BIDS规范v1.9+的参考实现。

#### 使用.bidsignore

在数据集根目录创建 `.bidsignore` 以从验证中排除文件（gitignore 语法）：

```
# Exclude sourcedata and extra files
sourcedata/
extra_data/
*.log
*_sbref.nii.gz
**/.DS_Store
```

### 5. BIDS 实体和文件命名

实体、其排序、允许的后缀和所有文件名规则的权威、机器可读的真实来源是 **BIDS 模式** — 规范的结构化 YAML/JSON 表示。 JSON 出口会在 `references/bids_schema.json` 处使用此技能发货。该架构在 [bids-specation `src/schema/`](https://github.com/bids-standard/bids-specification/tree/master/src/schema) 目录中定义，并在 https://bids-specification.readthedocs.io/en/stable/schema.json. BEP 上发布，特定架构预览可在 https://github.com/bids-standard/bids-schema/tree/main/BEPs. 获取

运行 `scripts/update_schema.py` 从上游刷新模式和 BEPs 列表（除了 stdlib 之外没有依赖项）。

下表是一个方便的总结；如有疑问，请查阅架构。

BIDS 文件名是根据有序键值实体对构建的：

| 实体 | 密钥 | 示例 | 需要 |
|--------|-----|---------|--------------|
| 主题 | `sub-` | `sub-01` | 所有文件 |
| 会议 | `ses-` | `ses-pre` | 多次研究 |
| 任务 | `task-` | `task-rest` | func（粗体、cbv、阶段）、eeg、meg |
| 收购 | `acq-` | `acq-highres` | 区分采集参数 |
| 对比度增强剂 | `ce-` | `ce-gadolinium` | 对比度增强的图像 |
| 重建 | `rec-` | `rec-magnitude` | 重建变体 |
| 方向 | `dir-` | `dir-AP` | 场图，DWI，相位编码 |
| 运行 | `run-` | `run-01` | 多次相同的收购 |
| 回声 | `echo-` | `echo-1` | 多回波序列 |
| 部分 | `part-` | `part-mag` | Magnitude/phase 分裂 |
| 空间 | `space-` | `space-MNI152NLin2009cAsym` | 模板空间中的导数 |
| 描述 | `desc-` | `desc-preproc` | 仅衍生品 |

**文件名中的实体顺序**由规范固定（在`rules.entities` in `bids_schema.json` 中定义）。有关完整编号的订购表，请参阅`references/bids_specification.md`。一个公共子集：
`sub-<label>[_ses-<label>][_task-<label>][_acq-<label>][_ce-<label>][_rec-<label>][_dir-<label>][_run-<index>][_echo-<index>][_part-<label>][_space-<label>][_desc-<label>]_<suffix>.<extension>`

**按数据类型划分的常见后缀**：

| 数据类型 | 后缀 |
|----------|----------|
| anat | `T1w`, `T2w`, `FLAIR`, `T2star`, `T1map`, `T2map`, `defacemask` |
| 函数 | `bold`, `cbv`, `sbref`, `events`, `physio`, `stim` |
| dwi | `dwi`, `sbref` |
| fmap | `phasediff`, `phase1`, `phase2`, `magnitude1`, `magnitude2`, `fieldmap`, `epi` |
| 性能 | `asl`, `m0scan`, `aslcontext` |
| 脑电图 | `eeg`, `channels`, `electrodes`, `events` |
| 梅格 | `meg`, `channels`, `coordsystem`, `events` |
| ieeg | `ieeg`, `channels`, `electrodes`, `coordsystem`, `events` |
| 宠物 | `pet`, `blood` |

### 6. DICOM 到 BIDS 转换

#### HeuDiConv

HeuDiConv 是最灵活的DICOM到BIDS转换器。它支持三种使用模式——从全自动到完全自定义——并可以开箱即用地处理重复、来源跟踪和源数据归档。

**模式1：ReproIn（交钥匙，推荐用于新研究）**

如果扫描仪协议名称遵循 [ReproIn 命名约定](https://github.com/repronim/reproin)，则转换是全自动的 — 无需写入启发式文件：

```bash
# Turnkey conversion: HeuDiConv maps ReproIn protocol names to BIDS automatically
heudiconv --files dicom/001 -o /path/to/bids -f reproin --bids --minmeta
```

ReproIn 协议名称直接编码 BIDS 实体：
- `anat-T1w` → `sub-XX/anat/sub-XX_T1w.nii.gz`
- `func-bold_task-rest` → `sub-XX/func/sub-XX_task-rest_bold.nii.gz`
- `dwi_dir-AP` → `sub-XX/dwi/sub-XX_dir-AP_dwi.nii.gz`
- `fmap_dir-PA` → `sub-XX/fmap/sub-XX_dir-PA_epi.nii.gz`

会话可以在定位器上设置一次（e.g.，`anat-scout_ses-pre`），并且ReproIn将其传播到该程序中的所有序列。主题 ID 是从 DICOM 元数据中提取的。重复的运行会自动编号。

**模式2：自定义启发式映射到ReproIn（对于现有数据）**

如果您已经拥有非ReproIn协议名称的数据，您可以编写一个简单的启发式方法，将您的名称映射到ReproIn约定，从而获得所有ReproIn好处（自动实体处理、重复管理等）。请参阅 https://github.com/repronim/reproin/issues/18 了解 HOWTO。

**模式 3：自定义启发式（完全灵活性）**

对于复杂的映射，编写一个Python启发式文件：

```bash
# Step 1: Reconnaissance — discover DICOM series
heudiconv --files dicom/219/itbs/*/*.dcm -o Nifti/ -f convertall -s 219 -c none

# This creates .heudiconv/219/info/dicominfo.tsv — inspect it to understand
# what was acquired and map series to BIDS names.

# Step 2: Write a heuristic file (see references/conversion_tools.md)

# Step 3: Convert
heudiconv --files dicom/219/itbs/*/*.dcm -s 219 -ss itbs \
  -f Nifti/code/heuristic.py -c dcm2niix --bids --minmeta -o Nifti/
```

有关完整的启发式文件示例，请参阅 `references/conversion_tools.md`。

**要点**：
- HeuDiConv 包装 `dcm2niix` 以进行实际的 DICOM 到NIfTI 转换
- **`--minmeta`**：始终使用此标志来防止过多的DICOM元数据溢出JSON sidecar（可能会崩溃fMRIPrep/MRIQC）
- **重复处理**：在模板中使用`{item:03d}`，当同一协议运行多次时自动编号；没有它，后面的运行会覆盖前面的
- **`.heudiconv/`目录**：与输出一起创建，存储出处（启发式使用，dicominfo.tsv，转换记录）。将其与您的数据放在一起以确保可重复性
- **`sourcedata/`**：HeuDiConv 将原始 DICOM 存档为 `.tgz` 文件，并放在 `sourcedata/` 下，以便可重复
- **`is_motion_corrected` 过滤器**：用于启发式排除扫描仪生成的 MOCO 系列（e.g.、`if not s.is_motion_corrected`）
- 支持`--files`（显式路径）和`-d`（带有`{subject}`、`{session}`占位符的模板）来指定DICOM输入

#### dcm2bids（基于配置文件）

```bash
# Step 1: Generate helper output to inspect series
dcm2bids_helper -d /path/to/dicom

# Step 2: Create config file (dcm2bids_config.json)
# Step 3: Convert
dcm2bids -d /path/to/dicom -p 01 -c dcm2bids_config.json -o /path/to/bids_output
```

详细配置示例请参见`references/conversion_tools.md`。

### 7. 元数据 Sidecar

每个BIDS数据文件应该有一个带有采集参数的JSON sidecar。元数据字段遵循继承原则：较高目录级别的 sidecar 适用于下面的所有匹配文件。

**继承示例**：
```
my_dataset/
  task-rest_bold.json           # Applies to ALL rest BOLD files
  sub-01/
    func/
      sub-01_task-rest_bold.json  # Overrides/extends for sub-01 only
```

**按模式划分的关键元数据字段**：

对于 **func (BOLD)**：
```json
{
    "RepetitionTime": 2.0,
    "TaskName": "rest",
    "PhaseEncodingDirection": "j-",
    "TotalReadoutTime": 0.05,
    "SliceTiming": [0, 0.5, 1.0, 1.5],
    "EffectiveEchoSpacing": 0.00058,
    "EchoTime": 0.03
}
```

对于**anat**：
```json
{
    "MagneticFieldStrength": 3,
    "Manufacturer": "Siemens",
    "ManufacturersModelName": "Prisma",
    "RepetitionTime": 2.3,
    "EchoTime": 0.00293,
    "FlipAngle": 8
}
```

对于**DWI**：
```json
{
    "PhaseEncodingDirection": "j-",
    "TotalReadoutTime": 0.05,
    "EchoTime": 0.089,
    "RepetitionTime": 3.4,
    "MultipartID": "dwi_1"
}
```

**要点**：
- `dcm2niix` 从 DICOM 标头自动生成大多数 sidecar 字段
- `RepetitionTime` 和 `TaskName` 是 BOLD 所必需的
- `SliceTiming` 对于fMRI 预处理中的切片时序校正至关重要
- `PhaseEncodingDirection`和`TotalReadoutTime`（或`EffectiveEchoSpacing`）用于畸变校正
- 请参阅 `references/metadata_fields.md` 获取全面的现场参考

### 8. 任务fMRI的事件文件

基于任务的fMRI需要`_events.tsv`文件：

```
onset	duration	trial_type	response_time
0.0	0.5	face	0.435
2.5	0.5	house	0.367
5.0	0.5	face	0.512
7.5	0.5	scrambled	0.298
```

**必填列**：
- `onset` - 相对于采集开始的起始时间（以秒为单位）
- `duration` - 持续时间（以秒为单位）（对于瞬时事件使用 `n/a`）

**推荐专栏**：
- `trial_type` - 条件的分类标签
- `response_time` - RT 以秒为单位
- 根据需要自定义列（在相应的`.json` sidecar 中有描述）

### 9. 参与者档案

```
participant_id	age	sex	group	handedness
sub-01	25	M	control	right
sub-02	30	F	patient	left
sub-03	28	M	control	right
```

`participants.json` sidecar 描述了列：

```json
{
    "age": {
        "Description": "Age of the participant at time of scanning",
        "Units": "years"
    },
    "sex": {
        "Description": "Biological sex",
        "Levels": {
            "M": "male",
            "F": "female"
        }
    },
    "group": {
        "Description": "Experimental group",
        "Levels": {
            "control": "Healthy control",
            "patient": "Patient group"
        }
    },
    "handedness": {
        "Description": "Dominant hand",
        "Levels": {
            "right": "Right-handed",
            "left": "Left-handed",
            "ambidextrous": "Ambidextrous"
        }
    }
}
```

### 10. BIDS 衍生品

处理后的输出位于 `derivatives/` 目录下：

```
my_dataset/
  derivatives/
    fmriprep-24.1.0/
      dataset_description.json      # DatasetType: "derivative"
      sub-01/
        anat/
          sub-01_space-MNI152NLin2009cAsym_desc-preproc_T1w.nii.gz
          sub-01_space-MNI152NLin2009cAsym_desc-brain_mask.nii.gz
        func/
          sub-01_task-rest_space-MNI152NLin2009cAsym_desc-preproc_bold.nii.gz
          sub-01_task-rest_desc-confounds_timeseries.tsv
    mriqc-24.0.0/
      dataset_description.json
      sub-01/
        anat/
          sub-01_T1w.html
        func/
          sub-01_task-rest_bold.html
      group_T1w.tsv
      group_bold.tsv
```

**衍生约定**：
- `space-<label>` - template/reference 空间（e.g.、`MNI152NLin2009cAsym`、`T1w`）
- `desc-<label>` - 处理描述（e.g.、`preproc`、`brain`、`smoothed`）
- `res-<label>` - 分辨率（e.g.、`2` 对于 2mm 各向同性）
- 每个管道在`derivatives/`下都有自己的目录
- 必须有自己的 `dataset_description.json` 和 `GeneratedBy`

### 11. PyBIDS：高级用法

```python
from bids import BIDSLayout
from bids.layout import BIDSLayoutIndexer

# Cache the layout index for faster repeated access
layout = BIDSLayout("/path/to/dataset", database_path="/path/to/cache.db")

# Include derivatives
layout = BIDSLayout(
    "/path/to/dataset",
    derivatives=["/path/to/dataset/derivatives/fmriprep-24.1.0"]
)

# Get derivative files
preproc = layout.get(
    subject="01",
    task="rest",
    desc="preproc",
    suffix="bold",
    space="MNI152NLin2009cAsym",
    extension=".nii.gz",
    return_type="filename"
)

# Get confound regressors
confounds = layout.get(
    subject="01",
    task="rest",
    desc="confounds",
    suffix="timeseries",
    extension=".tsv",
    return_type="filename"
)

# Build BIDS path from entities
from bids import BIDSLayout
layout = BIDSLayout("/path/to/dataset")
path = layout.build_path(
    {
        "subject": "01",
        "session": "pre",
        "task": "rest",
        "suffix": "bold",
        "extension": ".nii.gz",
        "datatype": "func"
    },
    validate=True
)

# Get all files for a subject as a DataFrame
import pandas as pd
files_df = layout.to_df()
sub01_df = files_df[files_df["subject"] == "01"]
```

### 12. BIDS-应用程序

BIDS - 应用程序是容器化分析管道，接受 BIDS 数据集作为输入：

```bash
# General BIDS-App invocation pattern
docker run -v /path/to/bids:/data:ro -v /path/to/output:/out \
    <bids-app-image> /data /out participant --participant_label 01

# Common BIDS-Apps:
# fMRIPrep - fMRI preprocessing
docker run nipreps/fmriprep /data /out participant \
    --participant-label 01 --fs-license-file /license.txt

# MRIQC - MRI quality control
docker run nipreps/mriqc /data /out participant \
    --participant-label 01

# QSIPrep - diffusion MRI preprocessing
docker run pennbbl/qsiprep /data /out participant \
    --participant-label 01
```

**BIDS-App界面约定**：
```
bids-app input_dataset output_dir {participant|group} [options]
```

- `participant` 级别：每个科目运行
- `group` 级别：涵盖所有科目（aggregation/group 统计数据）

## 参考资料

该技能包含详细的参考文档：

- **bids_schema.json**：机器可读的BIDS架构（来自https://bids-specification.readthedocs.io/en/stable/schema.json）。这是实体定义、排序规则、文件名模板、每种数据类型允许的后缀以及元数据字段要求的权威来源。 BEP特定模式位于https://github.com/bids-standard/bids-schema/tree/main/BEPs.
- **beps.yml**：所有 BIDS 扩展提案的当前列表，包括标题、线索、状态和链接（来自 [bids-website](https://github.com/bids-standard/bids-website/blob/main/data/beps/beps.yml)）
- **bids_specification.md**：人类可读的实体表摘要、数据类型参考、目录结构规则、模板空间和规范变更日志
- **metadata_fields.md**：每个BIDS模态的必需和推荐JSON sidecar 字段（anat、func、dwi、fmap、eeg、meg、pet 等）
- **conversion_tools.md**：HeuDiConv、dcm2bids和BIDScoin的详细工作流程，包括heuristic/config示例和故障排除

更新架构和 BEPs：`python scripts/update_schema.py`

## 常见问题及解决方案

### 1. 验证器报告“不是BIDS数据集”
**原因**：根部缺少`dataset_description.json`。
**修复**：创建至少包含`{"Name": "...", "BIDSVersion": "1.10.0"}`的文件。

### 2. 科目不一致警告
**原因**：并非所有受试者都具有相同的文件集（某些缺少会话、运行等）。
**修复**：这是警告，而不是错误。如果有意，请使用 `--ignoreSubjectConsistency`。将缺失的数据记录在`participants.tsv`或`scans.tsv`中。

### 3. 缺失SliceTiming
**原因**：`dcm2niix`无法从DICOM标头中提取切片时序。
**修复**：根据扫描协议确定切片顺序并手动添加到JSON sidecar。常见模式：升序、降序、交错（奇数优先或偶数优先）。

### 4.相位编码方向混乱
**原因**：轴标签（i/j/k vs x/y/z vs LR/AP/SI）令人困惑。
**修复**：在BIDS中，使用NIfTI图像轴：`i`=第一轴，`j`=第二轴，`k`=第三轴。 `-`表示负方向。对于标准轴向采集：`j` 通常是前后位。使用采集协议进行验证。

### 5. PyBIDS 在大型数据集上速度很慢
**原因**：每个 `BIDSLayout()` 调用上都有完整的文件系统索引。
**修复**：使用`database_path`将索引缓存到SQLite文件：
```python
layout = BIDSLayout("/data", database_path="/data/.pybids_cache.db")
```

### 6. PyBIDS 未找到衍生品
**原因**：衍生品目录缺少自己的`dataset_description.json`。
**修复**：每个衍生目录必须有`dataset_description.json`和`"DatasetType": "derivative"`。

### 7. 事件文件计时关闭
**原因**：`onset`时间与错误参考相关（e.g.，触发时间与第一卷）。
**修复**：起始时间必须以秒为单位，相对于该运行采集的第一个体积。考虑虚拟扫描（如果它们被丢弃）。

### 8. TSV 文件验证失败
**原因**：编码或分隔符问题（空格而不是制表符、BOM字符、Windows 行结尾）。
**修复**：确保使用 UTF-8 编码和 Unix 行结尾 (`\n`) 制表符分隔值。使用 `n/a`（不是 `NA`、`NaN` 或空）来查找缺失值。

## 最佳实践

1. **尽早且经常验证** - 每次转换或修改后运行 BIDS 验证器。在错误复合之前修复错误。

2. **使用元数据继承** - 将共享元数据（e.g.、`TaskName`、扫描仪参数）放置在顶级 sidecar 文件中，而不是在每个主题的目录中复制。

3. **保留源数据** - 将原始 DICOM（或其他原始）数据存储在 `sourcedata/` 下，以便转换可重现。将 `sourcedata/` 添加到 `.bidsignore`。

4. **从一开始就使用一致的命名** - 在数据收集之前定义您的 BIDS 命名方案。使用扫描协议的 ReproIn 命名约定来启用自动转换。

5. **记录您的数据集** - 编写完整的 `README` 描述研究设计、采集参数、已知问题以及与 BIDS 的任何偏差。

6. **使用 scans.tsv 获取运行级别元数据** - 记录每次运行的采集时间和质量说明：
   ```
   filename	acq_time	quality
   func/sub-01_task-rest_bold.nii.gz	2025-01-15T10:30:00	good
   ```

7. **对数据集进行版本控制** - 使用 `CHANGES` 记录数据集修改。考虑使用 DataLad 对大型数据集进行完整版本控制。

8. **破坏解剖图像** - 在共享之前从T1w/T2w图像中删除面部特征（e.g.，使用`pydeface`、`mri_deface`或`afni_refacer`）。将损坏的版本存储为主要数据或使用 `_defacemask` 文件。

9. **使用BIDSURIs作为出处** - 在衍生产品中，使用BIDSURIs参考源文件：`bids::sub-01/anat/sub-01_T1w.nii.gz`。

10. **更喜欢社区工具** - 尽可能使用已建立的BIDS-应用程序（fMRIPrep、MRIQC、QSIPrep）而不是自定义管道。他们正确处理BIDSI/O并生产BIDS兼容的衍生品。

11. **研究 bids-examples** - [bids-examples](https://github.com/bids-standard/bids-examples) 存储库是涵盖不同模式和用例的原型 BIDS 数据集的规范集合（MRI、fMRI、DWI、 EEG、MEG、iEEG、PET、ASL、遗传学、衍生物等）。在构建您自己的数据集时将其用作参考，作为 BIDS 工具的测试数据，或了解应如何组织特定模态。每个示例都通过BIDS验证器。

## BIDS 扩展提案 (BEPs)

BEPs 是社区驱动的提案，旨在将 BIDS 扩展到新的模式、衍生品或元数据。包含状态、潜在客户和链接的完整列表位于 `references/beps.yml`（从 [bids-website](https://github.com/bids-standard/bids-website/blob/main/data/beps/beps.yml) 获取）。 BEP特定架构预览在https://github.com/bids-standard/bids-schema/tree/main/BEPs.处呈现

**当前 BEPs** （截至架构更新）：

| BEP | 标题 | 内容 | 状态 |
|-----|-------|---------|--------|
| 004 | 磁化率加权成像 | 原始 | 寻找新领导 |
| 011 | 结构预处理导数 | 衍生品 | Has PR (#518) |
| 012 | 函数预处理导数 | 衍生品 | 已实现PR (#519)，已实现模式 |
| 014 | 仿射变换和非线性场扭曲 | 衍生品 | X5 format development |
| 016 | 扩散加权成像导数 | 衍生品 | Has PR (#2211) |
| 017 | 通用BIDS 连接数据模式 | 衍生品 | 开发中 |
| 021 | 常见电生理导数 | 衍生品 | 开发中 |
| 023 | PET Preprocessing derivatives | 衍生品 | 开发中 |
| 024 | 计算机断层扫描 | 原始 | 寻求贡献者 |
| 026 | 微电极记录 | 原始 | 寻找新领导 |
| 028 | 出处 | 元数据 | 有 PR (#2099) |
| 032 | 微电极电生理学 | 原始 | 有 PR (#2307)，预览可用 — 涵盖 Neuropixels 和其他细胞外探针；与神经像素分析技能相关 |
| 033 | 高级扩散加权成像 | 原始 | 寻求贡献者 |
| 034 | 计算建模 | 衍生品 | 有 PR (#967) |
| 035 | 对不合规衍生品进行大型分析 | 衍生品 | 开发中 |
| 036 | 表型数据指南 | 原始 | 社区评论 |
| 037 | 非侵入性大脑刺激 | 原始 | 开发中 |
| 039 | 基于降维的网络 | 原始 | 开发中 |
| 040 | 功能性超声 | 原始 | 开发中 |
| 041 | 统计模型导数 | 衍生品 | 收集反馈 |
| 043 | BIDS 术语映射 | 元数据 | 收集反馈 |
| 044 | 刺激 | 原始 | 有 PR (#2022)，社区审查 |
| 045 | 外周生理记录 | 原始 | 有 PR (#2267) |
| 046 | 扩散纤维束成像 | 衍生品 | 开发中 |
| 047 | Audio/video 行为实验录音 | 原始 | 有 PR (#2231) |

**相关标准**：
- **BIDS-统计模型**：JSON定义基于GLM的神经影像分析的规范
- **BIDS-衍生品** (BEP003)：preprocessed/analysis输出的标准（部分合并到规范中）

## 相关工具生态系统

| 工具 | 目的 |
|------|---------|
| **fMRIPrep** | fMRI预处理（产生BIDS衍生品） |
| **MRIQC** | MRI 质量控制（生产 BIDS 衍生物） |
| **QSIPrep** | 扩散MRI预处理 |
| **TemplateFlow** | 具有类似 BIDS 命名的神经影像模板和图集 |
| **菲特林斯** | BIDS 统计模型实现 |
| **DataLad** | 大数据集的版本控制，与BIDS集成 |
| **OpenNeuro** | 免费BIDS数据集存储库 |
| **DANDI** | 神经生理学数据存档（对于某些模式使用 BIDS） |
| **HeuDiConv** | DICOM-to-BIDS，带有启发式 Python 文件 |
| **dcm2bids** | DICOM-到-BIDS，带有 JSON 配置 |
| **BIDScoin** | DICOM-到-BIDS，带有 GUI 和 YAML 配置 |
| **nwb2bids** | 将NWB（无边界神经数据）文件转换为BIDS |
| **CuBIDS** | BIDS 数据集管理和协调 |
| **bids2table** | BIDS 数据集的高效表格索引 |
| **出价示例** | 所有模式的原型BIDS数据集的规范集合 |

## 文档

- **BIDS 规格**：https://bids-specification.readthedocs.io/
- **BIDS 网站**：https://bids.neuroimaging.io/
- **PyBIDS 文档**：https://bids-standard.github.io/pybids/
- **BIDS 验证者**：https://github.com/bids-standard/bids-validator
- **BIDS 入门套件**：https://bids-standard.github.io/bids-starter-kit/
- **BIDS 示例**：https://github.com/bids-standard/bids-examples — 每个 BIDS 模态的规范参考数据集；用作模板和测试数据
- **HeuDiConv 文档**：https://heudiconv.readthedocs.io/
- **原始BIDS论文**：Gorgolewski 等人。 （2016）科学数据，doi：10.1038/sdata.2016.44
