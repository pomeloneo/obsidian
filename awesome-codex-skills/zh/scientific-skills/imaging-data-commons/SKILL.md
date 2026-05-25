---
name: imaging-data-commons
description: 使用 idc-index 查询和下载 NCI Imaging Data Commons 中的 public cancer imaging data。用于访问大规模 radiology（CT、MR、PET）和 pathology datasets，以进行 AI training 或 research。无需 authentication。按 metadata 查询，在 browser 中可视化，检查 licenses。
license: This skill is provided under the MIT License. IDC data itself has individual licensing (mostly CC-BY, some CC-NC) that must be respected when using the data.
metadata:
    version: 1.4.0
    skill-author: Andrey Fedorov, @fedorov
    idc-index: "0.11.14"
    idc-data-version: "v23"
    repository: https://github.com/ImagingDataCommons/idc-claude-skill
---

# Imaging Data Commons

## 概述

使用 `idc-index` Python package 查询和下载 National Cancer Institute Imaging Data Commons (IDC) 中的 public cancer imaging data。访问数据无需 authentication。

**当前 IDC Data Version：v23**（始终用 `IDCClient().get_idc_version()` 验证）

**主要工具：** `idc-index` ([GitHub](https://github.com/imagingdatacommons/idc-index))

**关键 - 检查 package version 并在需要时升级（先运行此项）：**

```python
import idc_index

REQUIRED_VERSION = "0.11.14"  # Must match metadata.idc-index in this file
installed = idc_index.__version__

if installed < REQUIRED_VERSION:
    print(f"Upgrading idc-index from {installed} to {REQUIRED_VERSION}...")
    import subprocess
    subprocess.run(["pip3", "install", "--upgrade", "--break-system-packages", "idc-index"], check=True)
    print("Upgrade complete. Restart Python to use new version.")
else:
    print(f"idc-index {installed} meets requirement ({REQUIRED_VERSION})")
```

**验证 IDC data version 并检查当前 data scale：**

```python
from idc_index import IDCClient
client = IDCClient()

# Verify IDC data version (should be "v23")
print(f"IDC data version: {client.get_idc_version()}")

# Get collection count and total series
stats = client.sql_query("""
    SELECT
        COUNT(DISTINCT collection_id) as collections,
        COUNT(DISTINCT analysis_result_id) as analysis_results,
        COUNT(DISTINCT PatientID) as patients,
        COUNT(DISTINCT StudyInstanceUID) as studies,
        COUNT(DISTINCT SeriesInstanceUID) as series,
        SUM(instanceCount) as instances,
        SUM(series_size_MB)/1000000 as size_TB
    FROM index
""")
print(stats)
```

**核心工作流：**
1. 查询 metadata → `client.sql_query()`
2. 下载 DICOM files → `client.download_from_selection()`
3. 在 browser 中可视化 → `client.get_viewer_URL(seriesInstanceUID=...)`

## 何时使用此 Skill

- 查找公开可用的 radiology（CT、MR、PET）或 pathology（slide microscopy）images
- 按 cancer type、modality、anatomical site 或其他 metadata 选择 image subsets
- 从 IDC 下载 DICOM data
- 在 research 或 commercial applications 中使用前检查 data licenses
- 无需本地 DICOM viewer software，在 browser 中可视化 medical images

## Quick Navigation

**Core Sections（inline）：**
- IDC Data Model - Collection 和 analysis result hierarchy
- Index Tables - 可用 tables 和 joining patterns
- Installation - Package setup 和 version verification
- Core Capabilities - Essential API patterns（query、download、visualize、license、citations、batch）
- Best Practices - Usage guidelines
- Troubleshooting - Common issues 和 solutions

**Reference Guides（按需加载）：**

| Guide | When to Load |
|-------|--------------|
| `index_tables_guide.md` | Complex JOINs、schema discovery、DataFrame access |
| `use_cases.md` | End-to-end workflow examples（training datasets、batch downloads） |
| `sql_patterns.md` | Filter discovery、annotations、size estimation 的 quick SQL patterns |
| `clinical_data_guide.md` | Clinical/tabular data、imaging+clinical joins、value mapping |
| `cloud_storage_guide.md` | Direct S3/GCS access、versioning、UUID mapping |
| `dicomweb_guide.md` | DICOMweb endpoints、PACS integration |
| `digital_pathology_guide.md` | Slide microscopy（SM）、annotations（ANN）、pathology workflows |
| `bigquery_guide.md` | Full DICOM metadata、private elements（需要 GCP） |
| `cli_guide.md` | Command-line tools（`idc download`、manifest files） |
| `parquet_access_guide.md` | 通过 GCS 直接查询 Parquet（无需安装 idc-index） |

## IDC Data Model

IDC 在标准 DICOM hierarchy（Patient → Study → Series → Instance）之上添加了两个 grouping levels：

- **collection_id**：按 disease、modality 或 research focus 分组 patients（例如 `tcga_luad`、`nlst`）。一个 patient 只属于一个 collection。
- **analysis_result_id**：标识跨一个或多个 original collections 的 derived objects（segmentations、annotations、radiomics features）。

使用 `collection_id` 查找 original imaging data，其中可能包含随 images 一起提交的 annotations；使用 `analysis_result_id` 查找 AI-generated 或 expert annotations。

**查询关键 identifiers：**
| Identifier | Scope | Use for |
|------------|-------|---------|
| `collection_id` | Dataset grouping | 按 project/study 过滤 |
| `PatientID` | Patient | 按 patient 分组 images |
| `StudyInstanceUID` | DICOM study | 相关 series 的 grouping、visualization |
| `SeriesInstanceUID` | DICOM series | 相关 series 的 grouping、visualization |

## Index Tables

`idc-index` package 提供多个 metadata index tables，可通过 SQL 或 pandas DataFrames 访问。

**完整 index table documentation：** 使用 https://idc-index.readthedocs.io/en/latest/indices_reference.html 快速检查可用 tables 和 columns，无需执行代码。

**重要：** 使用 `client.indices_overview` 获取当前 table descriptions 和 column schemas。这是可用 columns 及其 types 的权威来源；编写 SQL 或探索 data structure 时始终查询它。

### Available Tables

| Table | Row Granularity | Loaded | Description |
|-------|-----------------|--------|-------------|
| `index` | 1 row = 1 DICOM series | Auto | 当前所有 IDC data 的 primary metadata |
| `prior_versions_index` | 1 row = 1 DICOM series | Auto | 以前 IDC releases 的 series；用于下载 deprecated data |
| `collections_index` | 1 row = 1 collection | fetch_index() | Collection-level metadata 和 descriptions |
| `analysis_results_index` | 1 row = 1 analysis result collection | fetch_index() | Derived datasets（annotations、segmentations）的 metadata |
| `clinical_index` | 1 row = 1 clinical data column | fetch_index() | 将 clinical table columns 映射到 collections 的 dictionary |
| `sm_index` | 1 row = 1 slide microscopy series | fetch_index() | Slide Microscopy（pathology）series metadata |
| `sm_instance_index` | 1 row = 1 slide microscopy instance | fetch_index() | Slide microscopy 的 instance-level（SOPInstanceUID）metadata |
| `seg_index` | 1 row = 1 DICOM Segmentation series | fetch_index() | Segmentation metadata：algorithm、segment count、source image series reference |
| `ann_index` | 1 row = 1 DICOM ANN series | fetch_index() | Microscopy Bulk Simple Annotations series metadata；引用 annotated image series |
| `ann_group_index` | 1 row = 1 annotation group | fetch_index() | 详细 annotation group metadata：graphic type、annotation count、property codes、algorithm |
| `contrast_index` | 1 row = 1 series with contrast info | fetch_index() | Contrast agent metadata：agent name、ingredient、administration route（CT、MR、PT、XA、RF） |
| `volume_geometry_index` | 1 row = 1 CT/MR/PT series | fetch_index() | Single-frame CT、MR 和 PT series 的 3D volume geometry validation；orientation、spacing、dimensions 和 slice positions 的 boolean checks；composite `regularly_spaced_3d_volume` flag |
| `rtstruct_index` | 1 row = 1 RTSTRUCT series | fetch_index() | RT Structure Set metadata：total ROI count、ROI names、generation algorithms、interpreted types，以及 referenced image series UID |

**Auto** = 实例化 `IDCClient()` 时自动加载
**fetch_index()** = 需要 `client.fetch_index("table_name")` 加载

### Joining Tables

**Key columns 没有显式标注，以下是可用于 joins 的子集。**

| Join Column | Tables | Use Case |
|-------------|--------|----------|
| `collection_id` | index, prior_versions_index, collections_index, clinical_index | 将 series 连接到 collection metadata 或 clinical data |
| `SeriesInstanceUID` | index, prior_versions_index, sm_index, sm_instance_index | 跨 tables 连接 series；连接到 slide microscopy details |
| `StudyInstanceUID` | index, prior_versions_index | 跨 current 和 historical data 连接 studies |
| `PatientID` | index, prior_versions_index | 跨 current 和 historical data 连接 patients |
| `analysis_result_id` | index, analysis_results_index | 将 series 连接到 analysis result metadata（annotations、segmentations） |
| `source_DOI` | index, analysis_results_index | 按 publication DOI 连接 |
| `crdc_series_uuid` | index, prior_versions_index | 按 CRDC unique identifier 连接 |
| `Modality` | index, prior_versions_index | 按 imaging modality 过滤 |
| `SeriesInstanceUID` | index, seg_index, ann_index, ann_group_index, contrast_index | 将 segmentation/annotation/contrast series 连接到其 index metadata |
| `segmented_SeriesInstanceUID` | seg_index → index | 将 segmentation 连接到 source image series（join seg_index.segmented_SeriesInstanceUID = index.SeriesInstanceUID） |
| `referenced_SeriesInstanceUID` | ann_index → index | 将 annotation 连接到 source image series（join ann_index.referenced_SeriesInstanceUID = index.SeriesInstanceUID） |
| `SeriesInstanceUID` | index, volume_geometry_index | 将 series 连接到 3D geometry validation result（join index.SeriesInstanceUID = volume_geometry_index.SeriesInstanceUID） |
| `SeriesInstanceUID` / `referenced_SeriesInstanceUID` | index, rtstruct_index | 将 RTSTRUCT series 连接到其 metadata（index.SeriesInstanceUID = rtstruct_index.SeriesInstanceUID）；用 rtstruct_index.referenced_SeriesInstanceUID 查找 source image series |

**Note：** `Subjects`、`Updated` 和 `Description` 出现在多个 tables 中，但含义不同（counts vs identifiers，不同 update contexts）。

详细 join examples、schema discovery patterns、key columns reference 和 DataFrame access 见 `references/index_tables_guide.md`。

### Clinical Data Access

```python
# Fetch clinical index (also downloads clinical data tables)
client.fetch_index("clinical_index")

# Query clinical index to find available tables and their columns
tables = client.sql_query("SELECT DISTINCT table_name, column_label FROM clinical_index")

# Load a specific clinical table as DataFrame
clinical_df = client.get_clinical_table("table_name")
```

包含 value mapping patterns 和 imaging+clinical join 的详细 workflows 见 `references/clinical_data_guide.md`。

## Data Access Options

| Method | Auth Required | Best For |
|--------|---------------|----------|
| `idc-index` | No | Key queries 和 downloads（推荐） |
| Direct Parquet（GCS） | No | 不安装 idc-index 的快速 queries；始终使用最新 data |
| IDC Portal | No | Interactive exploration、manual selection、browser-based download |
| BigQuery | Yes（GCP account） | Complex queries、full DICOM metadata |
| DICOMweb proxy | No | 通过 DICOMweb API 进行 tool integration |
| Cloud storage（S3/GCS） | No | Direct file access、bulk downloads、custom pipelines |

**Cloud storage organization**

IDC 在 AWS S3 和 Google Cloud Storage 之间镜像 public cloud storage buckets 中的所有 DICOM files。Files 按 CRDC UUIDs（不是 DICOM UIDs）组织，以支持 versioning。

| Bucket (AWS / GCS) | License | Content |
|--------------------|---------|---------|
| `idc-open-data` / `idc-open-data` | 无商业限制 | >90% IDC data |
| `idc-open-data-two` / `idc-open-idc1` | 无商业限制 | 可能包含 head scans 的 collections |
| `idc-open-data-cr` / `idc-open-cr` | Commercial use restricted（CC BY-NC） | 约 4% data |

Files 存储为 `<crdc_series_uuid>/<crdc_instance_uuid>.dcm`。通过 AWS CLI、gsutil 或 s5cmd 使用 anonymous access 可免费访问（无 egress fees）。S3 URLs 使用 index 中的 `series_aws_url` column；GCS 使用相同 path structure。

Bucket details、access commands、UUID mapping 和 versioning 见 `references/cloud_storage_guide.md`。

**DICOMweb access**

IDC data 可通过 DICOMweb interface（Google Cloud Healthcare API implementation）访问，用于与 PACS systems 和 DICOMweb-compatible tools 集成。

| Endpoint | Auth | Use Case |
|----------|------|----------|
| Public proxy | No | Testing、moderate queries、daily quota |
| Google Healthcare | Yes（GCP） | Production use、higher quotas |

Endpoint URLs、code examples、supported operations 和 implementation details 见 `references/dicomweb_guide.md`。

**Direct Parquet access**

所有 idc-index metadata tables 都以 Parquet files 形式发布到 public GCS bucket（`idc-index-data-artifacts`），并带 unrestricted CORS。这支持不安装 idc-index 的 DuckDB 或 pandas queries，包括 cross-table joins，以及针对 `volume_geometry_index` 和 `rtstruct_index` 的 queries。

URL patterns、available files 和 DuckDB query examples 见 `references/parquet_access_guide.md`。

## Installation and Setup

**Required（用于基本访问）：**
```bash
pip install --upgrade idc-index
```

**重要：** 新 IDC data release 总会触发新的 `idc-index` version。安装时始终使用 `--upgrade` flag，除非为了 reproducibility 需要旧版本。

**IMPORTANT：** 当前 IDC data version 是 v23。始终验证你的 version：
```python
print(client.get_idc_version())  # Should return "v23"
```
如果看到旧版本，使用 `pip install --upgrade idc-index` 升级。

**Tested with：** idc-index 0.11.14（IDC data version v23）

**Optional（用于 data analysis）：**
```bash
pip install pandas numpy pydicom
```

## 核心能力

### 1. Data Discovery and Exploration

发现 IDC 中可用的 imaging collections 和 data：

```python
from idc_index import IDCClient

client = IDCClient()

# Get summary statistics from primary index
query = """
SELECT
  collection_id,
  COUNT(DISTINCT PatientID) as patients,
  COUNT(DISTINCT SeriesInstanceUID) as series,
  SUM(series_size_MB) as size_mb
FROM index
GROUP BY collection_id
ORDER BY patients DESC
"""
collections_summary = client.sql_query(query)

# For richer collection metadata, use collections_index
client.fetch_index("collections_index")
collections_info = client.sql_query("""
    SELECT collection_id, CancerTypes, TumorLocations, Species, Subjects, SupportingData
    FROM collections_index
""")

# For analysis results (annotations, segmentations), use analysis_results_index
client.fetch_index("analysis_results_index")
analysis_info = client.sql_query("""
    SELECT analysis_result_id, analysis_result_title, Subjects, Collections, Modalities
    FROM analysis_results_index
""")
```

**`collections_index`** 为每个 collection 提供 curated metadata：cancer types、tumor locations、species、subject counts 和 supporting data types，无需从 primary index 聚合。

**`analysis_results_index`** 列出 derived datasets（AI segmentations、expert annotations、radiomics features）及其 source collections 和 modalities。

### 2. Querying Metadata with SQL

使用 SQL 查询 IDC mini-index 以查找特定 datasets。

**首先探索 filter columns 的可用 values：**
```python
from idc_index import IDCClient

client = IDCClient()

# Check what Modality values exist
modalities = client.sql_query("""
    SELECT DISTINCT Modality, COUNT(*) as series_count
    FROM index
    GROUP BY Modality
    ORDER BY series_count DESC
""")
print(modalities)

# Check what BodyPartExamined values exist for MR modality
body_parts = client.sql_query("""
    SELECT DISTINCT BodyPartExamined, COUNT(*) as series_count
    FROM index
    WHERE Modality = 'MR' AND BodyPartExamined IS NOT NULL
    GROUP BY BodyPartExamined
    ORDER BY series_count DESC
    LIMIT 20
""")
print(body_parts)
```

**然后使用已验证 filter values 查询：**
```python
# Find breast MRI scans (use actual values from exploration above)
results = client.sql_query("""
    SELECT
      collection_id,
      PatientID,
      SeriesInstanceUID,
      Modality,
      SeriesDescription,
      license_short_name
    FROM index
    WHERE Modality = 'MR'
      AND BodyPartExamined = 'BREAST'
    LIMIT 20
""")

# Access results as pandas DataFrame
for idx, row in results.iterrows():
    print(f"Patient: {row['PatientID']}, Series: {row['SeriesInstanceUID']}")
```

**按 cancer type 过滤时，join `collections_index`：**
```python
client.fetch_index("collections_index")
results = client.sql_query("""
    SELECT i.collection_id, i.PatientID, i.SeriesInstanceUID, i.Modality
    FROM index i
    JOIN collections_index c ON i.collection_id = c.collection_id
    WHERE c.CancerTypes LIKE '%Breast%'
      AND i.Modality = 'MR'
    LIMIT 20
""")
```

**可用 metadata fields**（完整列表使用 `client.indices_overview`）：
- Identifiers：collection_id、PatientID、StudyInstanceUID、SeriesInstanceUID
- Imaging：Modality、BodyPartExamined、Manufacturer、ManufacturerModelName
- Clinical：PatientAge、PatientSex、StudyDate
- Descriptions：StudyDescription、SeriesDescription
- Licensing：license_short_name

**Note：** Cancer type 在 `collections_index.CancerTypes` 中，而不在 primary `index` table 中。

### 3. Downloading DICOM Files

从 IDC cloud storage 高效下载 imaging data：

**下载整个 collection：**
```python
from idc_index import IDCClient

client = IDCClient()

# Download small collection (RIDER Pilot ~1GB)
client.download_from_selection(
    collection_id="rider_pilot",
    downloadDir="./data/rider"
)
```

**下载特定 series：**
```python
# First, query for series UIDs
series_df = client.sql_query("""
    SELECT SeriesInstanceUID
    FROM index
    WHERE Modality = 'CT'
      AND BodyPartExamined = 'CHEST'
      AND collection_id = 'nlst'
    LIMIT 5
""")

# Download only those series
client.download_from_selection(
    seriesInstanceUID=list(series_df['SeriesInstanceUID'].values),
    downloadDir="./data/lung_ct"
)
```

**Custom directory structure：**

默认 `dirTemplate`：`%collection_id/%PatientID/%StudyInstanceUID/%Modality_%SeriesInstanceUID`

```python
# Simplified hierarchy (omit StudyInstanceUID level)
client.download_from_selection(
    collection_id="tcga_luad",
    downloadDir="./data",
    dirTemplate="%collection_id/%PatientID/%Modality"
)
# Results in: ./data/tcga_luad/TCGA-05-4244/CT/

# Flat structure (all files in one directory)
client.download_from_selection(
    seriesInstanceUID=list(series_df['SeriesInstanceUID'].values),
    downloadDir="./data/flat",
    dirTemplate=""
)
# Results in: ./data/flat/*.dcm
```

**Downloaded file names：**

单个 DICOM files 使用其 CRDC instance UUID 命名：`<crdc_instance_uuid>.dcm`（例如 `0d73f84e-70ae-4eeb-96a0-1c613b5d9229.dcm`）。这种 UUID-based naming：
- 支持 version tracking（文件内容变化时 UUIDs 会变化）
- 匹配 cloud storage organization（`s3://idc-open-data/<crdc_series_uuid>/<crdc_instance_uuid>.dcm`）
- 不同于 DICOM UIDs（SOPInstanceUID），后者保存在 file metadata 内部

要识别 files，请在 queries 中使用 `crdc_instance_uuid` column，或从 files 读取 DICOM metadata（SOPInstanceUID）。

### Command-Line Download

`idc download` command 提供无需编写 Python code 的 command-line download 功能。安装 `idc-index` 后可用。

**自动检测 input type：** manifest file path，或 identifiers（collection_id、PatientID、StudyInstanceUID、SeriesInstanceUID、crdc_series_uuid）。

```bash
# Download entire collection
idc download rider_pilot --download-dir ./data

# Download specific series by UID
idc download "1.3.6.1.4.1.9328.50.1.69736" --download-dir ./data

# Download multiple items (comma-separated)
idc download "tcga_luad,tcga_lusc" --download-dir ./data

# Download from manifest file (auto-detected)
idc download manifest.txt --download-dir ./data
```

**Options：**

| Option | Description |
|--------|-------------|
| `--download-dir` | Output directory（默认：current directory） |
| `--dir-template` | Directory hierarchy template（默认：`%collection_id/%PatientID/%StudyInstanceUID/%Modality_%SeriesInstanceUID`） |
| `--log-level` | Verbosity：debug、info、warning、error、critical |

**Manifest files：**

Manifest files 包含 S3 URLs（每行一个），可来自：
- 在 cohort selection 后从 IDC Portal export
- Collaborators 共享，用于 reproducible data access
- 从 query results 程序化生成

Format（每行一个 S3 URL）：
```
s3://idc-open-data/cb09464a-c5cc-4428-9339-d7fa87cfe837/*
s3://idc-open-data/88f3990d-bdef-49cd-9b2b-4787767240f2/*
```

**示例：从 Python query 生成 manifest：**

```python
from idc_index import IDCClient

client = IDCClient()

# Query for series URLs
results = client.sql_query("""
    SELECT series_aws_url
    FROM index
    WHERE collection_id = 'rider_pilot' AND Modality = 'CT'
""")

# Save as manifest file
with open('ct_manifest.txt', 'w') as f:
    for url in results['series_aws_url']:
        f.write(url + '\n')
```

然后下载：
```bash
idc download ct_manifest.txt --download-dir ./ct_data
```

### 4. Visualizing IDC Images

不下载即可在 browser 中查看 DICOM data：

```python
from idc_index import IDCClient
import webbrowser

client = IDCClient()

# First query to get valid UIDs
results = client.sql_query("""
    SELECT SeriesInstanceUID, StudyInstanceUID
    FROM index
    WHERE collection_id = 'rider_pilot' AND Modality = 'CT'
    LIMIT 1
""")

# View single series
viewer_url = client.get_viewer_URL(seriesInstanceUID=results.iloc[0]['SeriesInstanceUID'])
webbrowser.open(viewer_url)

# View all series in a study (useful for multi-series exams like MRI protocols)
viewer_url = client.get_viewer_URL(studyInstanceUID=results.iloc[0]['StudyInstanceUID'])
webbrowser.open(viewer_url)
```

该方法会自动为 radiology 选择 OHIF v3，或为 slide microscopy 选择 SLIM。按 study 查看适用于 DICOM Study 包含多个 Series 的情况（例如单次 MRI session 中的 T1、T2、DWI sequences）。

### 5. Understanding and Checking Licenses

使用前检查 data licensing（对 commercial applications 尤其关键）：

```python
from idc_index import IDCClient

client = IDCClient()

# Check licenses for all collections
query = """
SELECT DISTINCT
  collection_id,
  license_short_name,
  COUNT(DISTINCT SeriesInstanceUID) as series_count
FROM index
GROUP BY collection_id, license_short_name
ORDER BY collection_id
"""

licenses = client.sql_query(query)
print(licenses)
```

**IDC 中的 License types：**
- **CC BY 4.0** / **CC BY 3.0**（约 97% data）- 允许 attribution 下的 commercial use
- **CC BY-NC 4.0** / **CC BY-NC 3.0**（约 3% data）- 仅 non-commercial use
- **Custom licenses**（少见）- 某些 collections 有特定 terms（例如 NLM Terms and Conditions）

**重要：** 在 publications 或 commercial applications 中使用 IDC data 前，始终检查 license。每个 DICOM file 的 metadata 中都标有其具体 license。

### Generating Citations for Attribution

`source_DOI` column 包含指向描述数据生成方式的 publications 的 DOI。为满足 attribution requirements，使用 `citations_from_selection()` 生成格式正确的 citations：

```python
from idc_index import IDCClient

client = IDCClient()

# Get citations for a collection (APA format by default)
citations = client.citations_from_selection(collection_id="rider_pilot")
for citation in citations:
    print(citation)

# Get citations for specific series
results = client.sql_query("""
    SELECT SeriesInstanceUID FROM index
    WHERE collection_id = 'tcga_luad' LIMIT 5
""")
citations = client.citations_from_selection(
    seriesInstanceUID=list(results['SeriesInstanceUID'].values)
)

# Alternative format: BibTeX (for LaTeX documents)
bibtex_citations = client.citations_from_selection(
    collection_id="tcga_luad",
    citation_format=IDCClient.CITATION_FORMAT_BIBTEX
)
```

**Parameters：**
- `collection_id`：按 collection(s) 过滤
- `patientId`：按 patient ID(s) 过滤
- `studyInstanceUID`：按 study UID(s) 过滤
- `seriesInstanceUID`：按 series UID(s) 过滤
- `citation_format`：使用 `IDCClient.CITATION_FORMAT_*` constants：
  - `CITATION_FORMAT_APA`（默认）- APA style
  - `CITATION_FORMAT_BIBTEX` - LaTeX 用 BibTeX
  - `CITATION_FORMAT_JSON` - CSL JSON
  - `CITATION_FORMAT_TURTLE` - RDF Turtle

**Best practice：** 发表使用 IDC data 的结果时，包含生成的 citations，以正确 attribute data sources 并满足 license requirements。

### 6. Batch Processing and Filtering

通过 filtering 高效处理 large datasets：

```python
from idc_index import IDCClient
import pandas as pd

client = IDCClient()

# Find chest CT scans from GE scanners
query = """
SELECT
  SeriesInstanceUID,
  PatientID,
  collection_id,
  ManufacturerModelName
FROM index
WHERE Modality = 'CT'
  AND BodyPartExamined = 'CHEST'
  AND Manufacturer = 'GE MEDICAL SYSTEMS'
  AND license_short_name = 'CC BY 4.0'
LIMIT 100
"""

results = client.sql_query(query)

# Save manifest for later
results.to_csv('lung_ct_manifest.csv', index=False)

# Download in batches to avoid timeout
batch_size = 10
for i in range(0, len(results), batch_size):
    batch = results.iloc[i:i+batch_size]
    client.download_from_selection(
        seriesInstanceUID=list(batch['SeriesInstanceUID'].values),
        downloadDir=f"./data/batch_{i//batch_size}"
    )
```

### 7. Advanced Queries with BigQuery

对于需要 full DICOM metadata、complex JOINs、clinical data tables 或 private DICOM elements 的 queries，使用 Google BigQuery。需要启用 billing 的 GCP account。

**Quick reference：**
- Dataset：`bigquery-public-data.idc_current.*`
- Main table：`dicom_all`（combined metadata）
- Full metadata：`dicom_metadata`（all DICOM tags）
- Private elements：`OtherElements` column（vendor-specific tags，例如 diffusion b-values）

Setup、table schemas、query patterns、private element access 和 cost optimization 见 `references/bigquery_guide.md`。

**使用 BigQuery 前**，始终检查 specialized index table 是否已包含你需要的 metadata：
1. 使用 `client.indices_overview` 或 [idc-index indices reference](https://idc-index.readthedocs.io/en/latest/indices_reference.html) 发现所有可用 tables 和 columns
2. 获取相关 index：`client.fetch_index("table_name")`
3. 使用 `client.sql_query()` 本地查询（免费，无需 GCP account）

常见 specialized indices：`seg_index`（segmentations）、`ann_index` / `ann_group_index`（microscopy annotations）、`sm_index`（slide microscopy）、`collections_index`（collection metadata）。只有在需要 private DICOM elements 或任何 index 中都没有的 attributes 时，才使用 BigQuery。

**需要 BigQuery 的 use cases（无 idc-index equivalent）：**
- **Per-segment anatomy search**：`seg_index` 提供 series-level SEG metadata，但 BigQuery `segmentations` table 会逐个 segment 暴露其 DICOM coded structure name（例如查找所有包含 "Liver" 或 "Neoplasm" segment 的 SEG series）
- **Quantitative measurements from SR**：`quantitative_measurements` BigQuery table 包含从 DICOM SR TID1500 objects 预提取的 radiomics features（volume、diameter、shape descriptors、texture、intensity statistics）；没有 idc-index equivalent
- **Qualitative measurements from SR**：`qualitative_measurements` BigQuery table 包含来自 DICOM SR TID1500 的 coded assessments（malignancy rating、calcification、texture、margin）；没有 idc-index equivalent

这些 tables 的 schemas、column descriptions 和 query examples 见 `references/bigquery_guide.md`。

### 8. Tool Selection Guide

| Task | Tool | Reference |
|------|------|-----------|
| Programmatic queries & downloads | `idc-index` | This document |
| Interactive exploration | IDC Portal | https://portal.imaging.datacommons.cancer.gov/ |
| Complex metadata queries | BigQuery | `references/bigquery_guide.md` |
| 3D visualization & analysis | SlicerIDCBrowser | https://github.com/ImagingDataCommons/SlicerIDCBrowser |

**Default choice：** 大多数任务使用 `idc-index`（no auth、easy API、batch downloads）。

### 9. Integration with Analysis Pipelines

将 IDC data 集成到 imaging analysis workflows：

**读取下载的 DICOM files：**
```python
import pydicom
import os

# Read DICOM files from downloaded series
series_dir = "./data/rider/rider_pilot/RIDER-1007893286/CT_1.3.6.1..."

dicom_files = [os.path.join(series_dir, f) for f in os.listdir(series_dir)
               if f.endswith('.dcm')]

# Load first image
ds = pydicom.dcmread(dicom_files[0])
print(f"Patient ID: {ds.PatientID}")
print(f"Modality: {ds.Modality}")
print(f"Image shape: {ds.pixel_array.shape}")
```

**从 CT series 构建 3D volume：**
```python
import pydicom
import numpy as np
from pathlib import Path

def load_ct_series(series_path):
    """Load CT series as 3D numpy array"""
    files = sorted(Path(series_path).glob('*.dcm'))
    slices = [pydicom.dcmread(str(f)) for f in files]

    # Sort by slice location
    slices.sort(key=lambda x: float(x.ImagePositionPatient[2]))

    # Stack into 3D array
    volume = np.stack([s.pixel_array for s in slices])

    return volume, slices[0]  # Return volume and first slice for metadata

volume, metadata = load_ct_series("./data/lung_ct/series_dir")
print(f"Volume shape: {volume.shape}")  # (z, y, x)
```

**与 SimpleITK 集成：**
```python
import SimpleITK as sitk
from pathlib import Path

# Read DICOM series
series_path = "./data/ct_series"
reader = sitk.ImageSeriesReader()
dicom_names = reader.GetGDCMSeriesFileNames(series_path)
reader.SetFileNames(dicom_names)
image = reader.Execute()

# Apply processing
smoothed = sitk.CurvatureFlow(image1=image, timeStep=0.125, numberOfIterations=5)

# Save as NIfTI
sitk.WriteImage(smoothed, "processed_volume.nii.gz")
```

## 常见使用场景

完整 end-to-end workflow examples 见 `references/use_cases.md`，包括：
- 从 lung CT scans 构建 deep learning training datasets
- 跨 scanner manufacturers 比较 image quality
- 下载前在 browser 中 preview data
- Commercial use 的 license-aware batch downloads

## 最佳实践

- **生成响应前验证 IDC version**：在 session 开始时始终调用 `client.get_idc_version()`，确认使用 expected data version（当前 v23）。如果使用旧版本，建议 `pip install --upgrade idc-index`
- **使用前检查 licenses**：始终查询 `license_short_name` field，并遵守 licensing terms（CC BY vs CC BY-NC）
- **生成 attribution citations**：使用 `citations_from_selection()` 从 `source_DOI` values 获取格式正确的 citations；在 publications 中包含它们
- **从 small queries 开始**：探索时使用 `LIMIT` clause，避免长时间下载并理解 data structure
- **简单 queries 使用 mini-index**：只有需要 comprehensive metadata 或 complex JOINs 时才使用 BigQuery
- **用 dirTemplate 组织 downloads**：使用有意义 directory structures，例如 `%collection_id/%PatientID/%Modality`
- **缓存 query results**：将 DataFrames 保存到 CSV files，避免重复 querying 并确保 reproducibility
- **先估计 size**：下载前检查 collection size，有些 collection sizes 是 terabytes！
- **保存 manifests**：始终保存带 Series UIDs 的 query results，以保证 reproducibility 和 data provenance
- **阅读 documentation**：IDC data structure 和 metadata fields 记录在 https://learn.canceridc.dev/
- **使用 IDC forum**：在 https://discourse.canceridc.dev/ 搜索 questions/answers，并向 IDC maintainers 和 users 提问

## 故障排除

**Issue: `ModuleNotFoundError: No module named 'idc_index'`**
- **Cause:** idc-index package not installed
- **Solution:** 使用 `pip install --upgrade idc-index` 安装

**Issue: Download fails with connection timeout**
- **Cause:** Network instability 或 download size 过大
- **Solution:**
  - 下载更小 batches（例如每次 10-20 series）
  - 检查 network connection
  - 使用 `dirTemplate` 按 batch 组织 downloads
  - 实现带 delays 的 retry logic

**Issue: `BigQuery quota exceeded` or billing errors**
- **Cause:** BigQuery 需要 billing-enabled GCP project
- **Solution:** 简单 queries 使用 idc-index mini-index（无需 billing），或查看 `references/bigquery_guide.md` 的 cost optimization tips

**Issue: Series UID not found or no data returned**
- **Cause:** UID 拼写错误、data 不在当前 IDC version 中，或 field name 错误
- **Solution:**
  - 检查 data 是否在当前 IDC version 中（一些 old data 可能已 deprecated）
  - 先使用 `LIMIT 5` 测试 query
  - 对照 metadata schema documentation 检查 field names

**Issue: Downloaded DICOM files won't open**
- **Cause:** Corrupted download 或 incompatible viewer
- **Solution:**
  - 检查 DICOM object type（Modality 和 SOPClassUID attributes），某些 object types 需要 specialized tools
  - 验证 file integrity（检查 file sizes）
  - 使用 pydicom 验证：`pydicom.dcmread(file, force=True)`
  - 尝试不同 DICOM viewer（3D Slicer、Horos、RadiAnt、QuPath）
  - 重新下载 series

## Common SQL Query Patterns

Quick-reference SQL patterns 见 `references/sql_patterns.md`，包括：
- Filter value discovery（modalities、body parts、manufacturers）
- Annotation 和 segmentation queries（包括 seg_index、ann_index joins）
- Slide microscopy queries（sm_index patterns）
- Download size estimation
- Clinical data linking

Segmentation 和 annotation details 也见 `references/digital_pathology_guide.md`。

## Related Skills

以下 skills 可补充 IDC workflows 的 downstream analysis 和 visualization：

### DICOM Processing
- **pydicom** - 读取、写入和操作 downloaded DICOM files。用于 extracting pixel data、reading metadata、anonymization 和 format conversion。处理 IDC radiology data（CT、MR、PET）时必不可少。

### Pathology and Slide Microscopy
兼容 DICOM 的工具（highdicom、wsidicom、TIA-Toolbox、Slim viewer）见 `references/digital_pathology_guide.md`。

### Metadata Visualization
- **matplotlib** - 用于完全自定义的 low-level plotting。用于创建总结 IDC query results 的 static figures（modalities bar charts、series counts histograms 等）。
- **seaborn** - 带 pandas integration 的 statistical visualization。用于快速探索 IDC metadata distributions、variables 之间关系，以及带 attractive defaults 的 categorical comparisons。
- **plotly** - Interactive visualization。当需要 hover info、zoom、pan 来探索 IDC metadata，或创建 collection statistics 的 web-embeddable dashboards 时使用。

### Data Exploration
- **exploratory-data-analysis** - 对 scientific data files 进行综合 EDA。下载 IDC data 后，用于在分析前理解 file structure、quality 和 characteristics。

## 资源

### Schema Reference（Primary Source）

**始终使用 `client.indices_overview` 获取当前 column schemas。** 这可确保与已安装 idc-index version 准确匹配：

```python
# Get all column names and types for any table
schema = client.indices_overview["index"]["schema"]
columns = [(c['name'], c['type'], c.get('description', '')) for c in schema['columns']]
```

### Reference Documentation

完整 reference guides 列表及 decision triggers 见顶部 Quick Navigation section。

- **[indices_reference](https://idc-index.readthedocs.io/en/latest/indices_reference.html)** - Index tables 的外部文档（可能领先于 installed version）

### External Links

- **IDC Portal**: https://portal.imaging.datacommons.cancer.gov/explore/
- **Documentation**: https://learn.canceridc.dev/
- **Tutorials**: https://github.com/ImagingDataCommons/IDC-Tutorials
- **User Forum**: https://discourse.canceridc.dev/
- **idc-index GitHub**: https://github.com/ImagingDataCommons/idc-index
- **Citation**: Fedorov, A., et al. "National Cancer Institute Imaging Data Commons: Toward Transparency, Reproducibility, and Scalability in Imaging Artificial Intelligence." RadioGraphics 43.12 (2023). https://doi.org/10.1148/rg.230180

### Skill Updates

此 skill version 可在 skill metadata 中找到。检查 updates：
- 访问 [releases page](https://github.com/ImagingDataCommons/idc-claude-skill/releases)
- 在 GitHub 上 watch repository（Watch → Custom → Releases）
