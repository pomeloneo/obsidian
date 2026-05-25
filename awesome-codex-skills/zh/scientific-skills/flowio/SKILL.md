---
name: flowio
description: 解析 FCS（Flow Cytometry Standard）files v2.0-3.1。将 events 提取为 NumPy arrays，读取 metadata/channels，转换为 CSV/DataFrame，用于 flow cytometry data preprocessing。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# FlowIO：Flow Cytometry Standard 文件处理器

## 概述

FlowIO 是一个用于读写 Flow Cytometry Standard (FCS) 文件的轻量级 Python library。可解析 FCS metadata、提取 event data，并以最少依赖创建新的 FCS 文件。该 library 支持 FCS versions 2.0、3.0 和 3.1，适合 backend services、data pipelines 和基础 cytometry file operations。

## 何时使用此 Skill

以下情况应使用此 skill：

- FCS files 需要 parsing 或 metadata extraction
- Flow cytometry data 需要转换为 NumPy arrays
- Event data 需要导出为 FCS format
- Multi-dataset FCS files 需要拆分
- Channel information extraction（scatter、fluorescence、time）
- Cytometry file validation 或 inspection
- Advanced analysis 前的 pre-processing workflows

**相关工具：** 对于包含 compensation、gating 和 FlowJo/GatingML support 的高级 flow cytometry analysis，建议将 FlowKit library 作为 FlowIO 的配套工具。

## 安装

```bash
uv pip install flowio
```

需要 Python 3.9 或更高版本。

## Quick Start

### 基本文件读取

```python
from flowio import FlowData

# Read FCS file
flow_data = FlowData('experiment.fcs')

# Access basic information
print(f"FCS Version: {flow_data.version}")
print(f"Events: {flow_data.event_count}")
print(f"Channels: {flow_data.pnn_labels}")

# Get event data as NumPy array
events = flow_data.as_array()  # Shape: (events, channels)
```

### 创建 FCS 文件

```python
import numpy as np
from flowio import create_fcs

# Prepare data
data = np.array([[100, 200, 50], [150, 180, 60]])  # 2 events, 3 channels
channels = ['FSC-A', 'SSC-A', 'FL1-A']

# Create FCS file
create_fcs('output.fcs', data, channels)
```

## 核心工作流

### 读取和解析 FCS 文件

FlowData class 提供读取 FCS 文件的主要接口。

**标准读取：**

```python
from flowio import FlowData

# Basic reading
flow = FlowData('sample.fcs')

# Access attributes
version = flow.version              # '3.0', '3.1', etc.
event_count = flow.event_count      # Number of events
channel_count = flow.channel_count  # Number of channels
pnn_labels = flow.pnn_labels        # Short channel names
pns_labels = flow.pns_labels        # Descriptive stain names

# Get event data
events = flow.as_array()            # Preprocessed (gain, log scaling applied)
raw_events = flow.as_array(preprocess=False)  # Raw data
```

**内存高效的 Metadata 读取：**

只需要 metadata（不需要 event data）时：

```python
# Only parse TEXT segment, skip DATA and ANALYSIS
flow = FlowData('sample.fcs', only_text=True)

# Access metadata
metadata = flow.text  # Dictionary of TEXT segment keywords
print(metadata.get('$DATE'))  # Acquisition date
print(metadata.get('$CYT'))   # Instrument name
```

**处理有问题的文件：**

某些 FCS 文件存在 offset discrepancies 或 errors：

```python
# Ignore offset discrepancies between HEADER and TEXT sections
flow = FlowData('problematic.fcs', ignore_offset_discrepancy=True)

# Use HEADER offsets instead of TEXT offsets
flow = FlowData('problematic.fcs', use_header_offsets=True)

# Ignore offset errors entirely
flow = FlowData('problematic.fcs', ignore_offset_error=True)
```

**排除 Null Channels：**

```python
# Exclude specific channels during parsing
flow = FlowData('sample.fcs', null_channel_list=['Time', 'Null'])
```

### 提取 Metadata 和 Channel Information

FCS 文件在 TEXT segment 中包含丰富 metadata。

**常见 Metadata Keywords：**

```python
flow = FlowData('sample.fcs')

# File-level metadata
text_dict = flow.text
acquisition_date = text_dict.get('$DATE', 'Unknown')
instrument = text_dict.get('$CYT', 'Unknown')
data_type = flow.data_type  # 'I', 'F', 'D', 'A'

# Channel metadata
for i in range(flow.channel_count):
    pnn = flow.pnn_labels[i]      # Short name (e.g., 'FSC-A')
    pns = flow.pns_labels[i]      # Descriptive name (e.g., 'Forward Scatter')
    pnr = flow.pnr_values[i]      # Range/max value
    print(f"Channel {i}: {pnn} ({pns}), Range: {pnr}")
```

**Channel Type Identification：**

FlowIO 会自动分类 channels：

```python
# Get indices by channel type
scatter_idx = flow.scatter_indices    # [0, 1] for FSC, SSC
fluoro_idx = flow.fluoro_indices      # [2, 3, 4] for FL channels
time_idx = flow.time_index            # Index of time channel (or None)

# Access specific channel types
events = flow.as_array()
scatter_data = events[:, scatter_idx]
fluorescence_data = events[:, fluoro_idx]
```

**ANALYSIS Segment：**

如果存在，可访问 processed results：

```python
if flow.analysis:
    analysis_keywords = flow.analysis  # Dictionary of ANALYSIS keywords
    print(analysis_keywords)
```

### 创建新的 FCS 文件

从 NumPy arrays 或其他 data sources 生成 FCS 文件。

**基本创建：**

```python
import numpy as np
from flowio import create_fcs

# Create event data (rows=events, columns=channels)
events = np.random.rand(10000, 5) * 1000

# Define channel names
channel_names = ['FSC-A', 'SSC-A', 'FL1-A', 'FL2-A', 'Time']

# Create FCS file
create_fcs('output.fcs', events, channel_names)
```

**带描述性 Channel Names：**

```python
# Add optional descriptive names (PnS)
channel_names = ['FSC-A', 'SSC-A', 'FL1-A', 'FL2-A', 'Time']
descriptive_names = ['Forward Scatter', 'Side Scatter', 'FITC', 'PE', 'Time']

create_fcs('output.fcs',
           events,
           channel_names,
           opt_channel_names=descriptive_names)
```

**带 Custom Metadata：**

```python
# Add TEXT segment metadata
metadata = {
    '$SRC': 'Python script',
    '$DATE': '19-OCT-2025',
    '$CYT': 'Synthetic Instrument',
    '$INST': 'Laboratory A'
}

create_fcs('output.fcs',
           events,
           channel_names,
           opt_channel_names=descriptive_names,
           metadata=metadata)
```

**注意：** FlowIO 导出为 FCS 3.1，并使用 single-precision floating-point data。

### 导出修改后的数据

修改现有 FCS 文件并重新导出。

**方法 1：使用 write_fcs() Method：**

```python
from flowio import FlowData

# Read original file
flow = FlowData('original.fcs')

# Write with updated metadata
flow.write_fcs('modified.fcs', metadata={'$SRC': 'Modified data'})
```

**方法 2：提取、修改并重建：**

用于修改 event data：

```python
from flowio import FlowData, create_fcs

# Read and extract data
flow = FlowData('original.fcs')
events = flow.as_array(preprocess=False)

# Modify event data
events[:, 0] = events[:, 0] * 1.5  # Scale first channel

# Create new FCS file with modified data
create_fcs('modified.fcs',
           events,
           flow.pnn_labels,
           opt_channel_names=flow.pns_labels,
           metadata=flow.text)
```

### 处理 Multi-Dataset FCS 文件

一些 FCS 文件在单个文件中包含多个 datasets。

**检测 Multi-Dataset Files：**

```python
from flowio import FlowData, MultipleDataSetsError

try:
    flow = FlowData('sample.fcs')
except MultipleDataSetsError:
    print("File contains multiple datasets")
    # Use read_multiple_data_sets() instead
```

**读取所有 Datasets：**

```python
from flowio import read_multiple_data_sets

# Read all datasets from file
datasets = read_multiple_data_sets('multi_dataset.fcs')

print(f"Found {len(datasets)} datasets")

# Process each dataset
for i, dataset in enumerate(datasets):
    print(f"\nDataset {i}:")
    print(f"  Events: {dataset.event_count}")
    print(f"  Channels: {dataset.pnn_labels}")

    # Get event data for this dataset
    events = dataset.as_array()
    print(f"  Shape: {events.shape}")
    print(f"  Mean values: {events.mean(axis=0)}")
```

**读取特定 Dataset：**

```python
from flowio import FlowData

# Read first dataset (nextdata_offset=0)
first_dataset = FlowData('multi.fcs', nextdata_offset=0)

# Read second dataset using NEXTDATA offset from first
next_offset = int(first_dataset.text['$NEXTDATA'])
if next_offset > 0:
    second_dataset = FlowData('multi.fcs', nextdata_offset=next_offset)
```

## Data Preprocessing

当 `preprocess=True` 时，FlowIO 会应用标准 FCS preprocessing transformations。

**Preprocessing Steps：**

1. **Gain Scaling：** 将数值乘以 PnG（gain）keyword
2. **Logarithmic Transformation：** 如果存在 PnE，则应用 exponential transformation
   - Formula：`value = a * 10^(b * raw_value)`，其中 PnE = "a,b"
3. **Time Scaling：** 将 time values 转换为合适单位

**控制 Preprocessing：**

```python
# Preprocessed data (default)
preprocessed = flow.as_array(preprocess=True)

# Raw data (no transformations)
raw = flow.as_array(preprocess=False)
```

## Error Handling

适当处理常见 FlowIO exceptions。

```python
from flowio import (
    FlowData,
    FCSParsingError,
    DataOffsetDiscrepancyError,
    MultipleDataSetsError
)

try:
    flow = FlowData('sample.fcs')
    events = flow.as_array()

except FCSParsingError as e:
    print(f"Failed to parse FCS file: {e}")
    # Try with relaxed parsing
    flow = FlowData('sample.fcs', ignore_offset_error=True)

except DataOffsetDiscrepancyError as e:
    print(f"Offset discrepancy detected: {e}")
    # Use ignore_offset_discrepancy parameter
    flow = FlowData('sample.fcs', ignore_offset_discrepancy=True)

except MultipleDataSetsError as e:
    print(f"Multiple datasets detected: {e}")
    # Use read_multiple_data_sets instead
    from flowio import read_multiple_data_sets
    datasets = read_multiple_data_sets('sample.fcs')

except Exception as e:
    print(f"Unexpected error: {e}")
```

## 常见使用场景

### 检查 FCS 文件内容

快速探索 FCS file structure：

```python
from flowio import FlowData

flow = FlowData('unknown.fcs')

print("=" * 50)
print(f"File: {flow.name}")
print(f"Version: {flow.version}")
print(f"Size: {flow.file_size:,} bytes")
print("=" * 50)

print(f"\nEvents: {flow.event_count:,}")
print(f"Channels: {flow.channel_count}")

print("\nChannel Information:")
for i, (pnn, pns) in enumerate(zip(flow.pnn_labels, flow.pns_labels)):
    ch_type = "scatter" if i in flow.scatter_indices else \
              "fluoro" if i in flow.fluoro_indices else \
              "time" if i == flow.time_index else "other"
    print(f"  [{i}] {pnn:10s} | {pns:30s} | {ch_type}")

print("\nKey Metadata:")
for key in ['$DATE', '$BTIM', '$ETIM', '$CYT', '$INST', '$SRC']:
    value = flow.text.get(key, 'N/A')
    print(f"  {key:15s}: {value}")
```

### 批量处理多个文件

处理一个 FCS files 目录：

```python
from pathlib import Path
from flowio import FlowData
import pandas as pd

# Find all FCS files
fcs_files = list(Path('data/').glob('*.fcs'))

# Extract summary information
summaries = []
for fcs_path in fcs_files:
    try:
        flow = FlowData(str(fcs_path), only_text=True)
        summaries.append({
            'filename': fcs_path.name,
            'version': flow.version,
            'events': flow.event_count,
            'channels': flow.channel_count,
            'date': flow.text.get('$DATE', 'N/A')
        })
    except Exception as e:
        print(f"Error processing {fcs_path.name}: {e}")

# Create summary DataFrame
df = pd.DataFrame(summaries)
print(df)
```

### 将 FCS 转换为 CSV

将 event data 导出为 CSV format：

```python
from flowio import FlowData
import pandas as pd

# Read FCS file
flow = FlowData('sample.fcs')

# Convert to DataFrame
df = pd.DataFrame(
    flow.as_array(),
    columns=flow.pnn_labels
)

# Add metadata as attributes
df.attrs['fcs_version'] = flow.version
df.attrs['instrument'] = flow.text.get('$CYT', 'Unknown')

# Export to CSV
df.to_csv('output.csv', index=False)
print(f"Exported {len(df)} events to CSV")
```

### 过滤 Events 并重新导出

应用 filters 并保存 filtered data：

```python
from flowio import FlowData, create_fcs
import numpy as np

# Read original file
flow = FlowData('sample.fcs')
events = flow.as_array(preprocess=False)

# Apply filtering (example: threshold on first channel)
fsc_idx = 0
threshold = 500
mask = events[:, fsc_idx] > threshold
filtered_events = events[mask]

print(f"Original events: {len(events)}")
print(f"Filtered events: {len(filtered_events)}")

# Create new FCS file with filtered data
create_fcs('filtered.fcs',
           filtered_events,
           flow.pnn_labels,
           opt_channel_names=flow.pns_labels,
           metadata={**flow.text, '$SRC': 'Filtered data'})
```

### 提取特定 Channels

提取并处理特定 channels：

```python
from flowio import FlowData
import numpy as np

flow = FlowData('sample.fcs')
events = flow.as_array()

# Extract fluorescence channels only
fluoro_indices = flow.fluoro_indices
fluoro_data = events[:, fluoro_indices]
fluoro_names = [flow.pnn_labels[i] for i in fluoro_indices]

print(f"Fluorescence channels: {fluoro_names}")
print(f"Shape: {fluoro_data.shape}")

# Calculate statistics per channel
for i, name in enumerate(fluoro_names):
    channel_data = fluoro_data[:, i]
    print(f"\n{name}:")
    print(f"  Mean: {channel_data.mean():.2f}")
    print(f"  Median: {np.median(channel_data):.2f}")
    print(f"  Std Dev: {channel_data.std():.2f}")
```

## 最佳实践

1. **Memory Efficiency：** 不需要 event data 时使用 `only_text=True`
2. **Error Handling：** 用 try-except blocks 包裹 file operations 以获得稳健代码
3. **Multi-Dataset Detection：** 检查 MultipleDataSetsError 并使用合适函数
4. **Preprocessing Control：** 根据 analysis needs 显式设置 `preprocess` 参数
5. **Offset Issues：** 如果 parsing 失败，尝试 `ignore_offset_discrepancy=True` 参数
6. **Channel Validation：** 处理前验证 channel counts 和 names 符合预期
7. **Metadata Preservation：** 修改文件时，保留原始 TEXT segment keywords

## 高级主题

### 理解 FCS 文件结构

FCS 文件由四个 segments 组成：

1. **HEADER：** FCS version 和其他 segments 的 byte offsets
2. **TEXT：** Key-value metadata pairs（delimiter-separated）
3. **DATA：** Raw event data（binary/float/ASCII format）
4. **ANALYSIS**（可选）：data processing 结果

通过 FlowData attributes 访问这些 segments：
- `flow.header` - HEADER segment
- `flow.text` - TEXT segment keywords
- `flow.events` - DATA segment（as bytes）
- `flow.analysis` - ANALYSIS segment keywords（如果存在）

### 详细 API Reference

完整 API documentation，包括所有 parameters、methods、exceptions 和 FCS keyword reference，请查阅详细 reference file：

**Read:** `references/api_reference.md`

该 reference 包括：
- 完整 FlowData class documentation
- 所有 utility functions（read_multiple_data_sets、create_fcs）
- Exception classes 和 handling
- FCS file structure details
- 常见 TEXT segment keywords
- 扩展 example workflows

处理复杂 FCS operations 或遇到不常见 file formats 时，加载此 reference 获取详细指导。

## Integration Notes

**NumPy Arrays：** 所有 event data 都以 shape 为 (events, channels) 的 NumPy ndarrays 返回

**Pandas DataFrames：** 可轻松转换为 DataFrames 进行 analysis：
```python
import pandas as pd
df = pd.DataFrame(flow.as_array(), columns=flow.pnn_labels)
```

**FlowKit Integration：** 对于高级 analysis（compensation、gating、FlowJo support），使用基于 FlowIO parsing capabilities 构建的 FlowKit library

**Web Applications：** FlowIO 的最小依赖使其非常适合处理 FCS uploads 的 web backend services

## 故障排除

**问题：** "Offset discrepancy error"
**解决方案：** 使用 `ignore_offset_discrepancy=True` 参数

**问题：** "Multiple datasets error"
**解决方案：** 使用 `read_multiple_data_sets()` function，而不是 FlowData constructor

**问题：** 大文件 out of memory
**解决方案：** metadata-only operations 使用 `only_text=True`，或分 chunks 处理 events

**问题：** Unexpected channel counts
**解决方案：** 检查 null channels；使用 `null_channel_list` 参数排除它们

**问题：** 无法就地修改 event data
**解决方案：** FlowIO 不支持直接修改；提取 data、修改，然后使用 `create_fcs()` 保存

## 总结

FlowIO 为 flow cytometry workflows 提供基本 FCS file handling capabilities。用它进行 parsing、metadata extraction 和 file creation。对于简单 file operations 和 data extraction，FlowIO 已足够。对于包含 compensation 和 gating 的复杂 analysis，请与 FlowKit 或其他 specialized tools 集成。
