---
name: exploratory-data-analysis
description: 对 200+ 文件格式的 scientific data files 执行综合 exploratory data analysis。当分析任何 scientific data file 以理解其结构、内容、质量和特征时，应使用此 skill。自动检测文件类型，并生成带 format-specific analysis、quality metrics 和 downstream analysis recommendations 的详细 markdown reports。涵盖 chemistry、bioinformatics、microscopy、spectroscopy、proteomics、metabolomics 和 general scientific data formats。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Exploratory Data Analysis

## 概述

跨多个领域对 scientific data files 执行综合 exploratory data analysis (EDA)。此 skill 提供自动文件类型检测、format-specific analysis、data quality assessment，并生成适合 documentation 和 downstream analysis planning 的详细 markdown reports。

**关键能力：**
- 自动检测并分析 200+ scientific file formats
- 全面的 format-specific metadata extraction
- Data quality 和 integrity assessment
- Statistical summaries 和 distributions
- Visualization recommendations
- Downstream analysis suggestions
- Markdown report generation

## 何时使用此 Skill

以下情况使用此 skill：
- 用户提供 scientific data file 路径用于分析
- 用户要求 "explore"、"analyze" 或 "summarize" 数据文件
- 用户想理解 scientific data 的结构和内容
- 用户在分析前需要 dataset 的综合报告
- 用户想评估 data quality 或 completeness
- 用户询问某个文件适合什么类型的 analysis

## 支持的文件类别

此 skill 对 scientific file formats 有全面覆盖，分为六大类：

### 1. Chemistry and Molecular Formats（60+ extensions）
Structure files、computational chemistry outputs、molecular dynamics trajectories 和 chemical databases。

**文件类型包括：** `.pdb`、`.cif`、`.mol`、`.mol2`、`.sdf`、`.xyz`、`.smi`、`.gro`、`.log`、`.fchk`、`.cube`、`.dcd`、`.xtc`、`.trr`、`.prmtop`、`.psf` 等。

**Reference file：** `references/chemistry_molecular_formats.md`

### 2. Bioinformatics and Genomics Formats（50+ extensions）
Sequence data、alignments、annotations、variants 和 expression data。

**文件类型包括：** `.fasta`、`.fastq`、`.sam`、`.bam`、`.vcf`、`.bed`、`.gff`、`.gtf`、`.bigwig`、`.h5ad`、`.loom`、`.counts`、`.mtx` 等。

**Reference file：** `references/bioinformatics_genomics_formats.md`

### 3. Microscopy and Imaging Formats（45+ extensions）
Microscopy images、medical imaging、whole slide imaging 和 electron microscopy。

**文件类型包括：** `.tif`、`.nd2`、`.lif`、`.czi`、`.ims`、`.dcm`、`.nii`、`.mrc`、`.dm3`、`.vsi`、`.svs`、`.ome.tiff` 等。

**Reference file：** `references/microscopy_imaging_formats.md`

### 4. Spectroscopy and Analytical Chemistry Formats（35+ extensions）
NMR、mass spectrometry、IR/Raman、UV-Vis、X-ray、chromatography 和其他 analytical techniques。

**文件类型包括：** `.fid`、`.mzML`、`.mzXML`、`.raw`、`.mgf`、`.spc`、`.jdx`、`.xy`、`.cif`（crystallography）、`.wdf` 等。

**Reference file：** `references/spectroscopy_analytical_formats.md`

### 5. Proteomics and Metabolomics Formats（30+ extensions）
Mass spec proteomics、metabolomics、lipidomics 和 multi-omics data。

**文件类型包括：** `.mzML`、`.pepXML`、`.protXML`、`.mzid`、`.mzTab`、`.sky`、`.mgf`、`.msp`、`.h5ad` 等。

**Reference file：** `references/proteomics_metabolomics_formats.md`

### 6. General Scientific Data Formats（30+ extensions）
Arrays、tables、hierarchical data、compressed archives 和 common scientific formats。

**文件类型包括：** `.npy`、`.npz`、`.csv`、`.xlsx`、`.json`、`.hdf5`、`.zarr`、`.parquet`、`.mat`、`.fits`、`.nc`、`.xml` 等。

**Reference file：** `references/general_scientific_formats.md`

## 工作流

### Step 1：文件类型检测

当用户提供文件路径时，先识别文件类型：

1. 提取 file extension
2. 在对应 reference file 中查找 extension
3. 识别 file category 和 format description
4. 加载 format-specific information

**示例：**
```
User: "Analyze data.fastq"
→ Extension: .fastq
→ Category: bioinformatics_genomics
→ Format: FASTQ Format (sequence data with quality scores)
→ Reference: references/bioinformatics_genomics_formats.md
```

### Step 2：加载 Format-Specific Information

基于文件类型，阅读对应 reference file 以理解：
- **Typical Data：** 此格式包含哪类数据
- **Use Cases：** 此格式的常见应用
- **Python Libraries：** 如何在 Python 中读取该文件
- **EDA Approach：** 哪些分析适合此数据类型

在 reference file 中搜索特定 extension（例如，在 `bioinformatics_genomics_formats.md` 中搜索 "### .fastq"）。

### Step 3：执行数据分析

使用 `scripts/eda_analyzer.py` 脚本，或实现自定义分析：

**Option A：使用 analyzer script**
```python
# The script automatically:
# 1. Detects file type
# 2. Loads reference information
# 3. Performs format-specific analysis
# 4. Generates markdown report

python scripts/eda_analyzer.py <filepath> [output.md]
```

**Option B：在对话中进行自定义分析**
基于 reference file 中的 format information，执行合适的分析：

对于 tabular data（CSV、TSV、Excel）：
- 用 pandas 加载
- 检查 dimensions、data types
- 分析 missing values
- 计算 summary statistics
- 识别 outliers
- 检查 duplicates

对于 sequence data（FASTA、FASTQ）：
- 统计 sequences
- 分析 length distributions
- 计算 GC content
- 评估 quality scores（FASTQ）

对于 images（TIFF、ND2、CZI）：
- 检查 dimensions（X、Y、Z、C、T）
- 分析 bit depth 和 value range
- 提取 metadata（channels、timestamps、spatial calibration）
- 计算 intensity statistics

对于 arrays（NPY、HDF5）：
- 检查 shape 和 dimensions
- 分析 data type
- 计算 statistical summaries
- 检查 missing/invalid values

### Step 4：生成综合报告

创建包含以下 sections 的 markdown report：

#### 必需 Sections：
1. **Title and Metadata**
   - Filename 和 timestamp
   - File size 和 location

2. **Basic Information**
   - File properties
   - Format identification

3. **File Type Details**
   - 来自 reference 的 format description
   - Typical data content
   - Common use cases
   - 用于读取的 Python libraries

4. **Data Analysis**
   - Structure 和 dimensions
   - Statistical summaries
   - Quality assessment
   - Data characteristics

5. **Key Findings**
   - Notable patterns
   - Potential issues
   - Quality metrics

6. **Recommendations**
   - Preprocessing steps
   - Appropriate analyses
   - Tools 和 methods
   - Visualization approaches

#### Template 位置
使用 `assets/report_template.md` 作为 report structure 的指南。

### Step 5：保存报告

用描述性文件名保存 markdown report：
- Pattern：`{original_filename}_eda_report.md`
- 示例：`experiment_data.fastq` → `experiment_data_eda_report.md`

## 详细 Format References

每个 reference file 都包含数十种 file types 的全面信息。要查找特定 format 的信息：

1. 根据 extension 识别 category
2. 阅读合适的 reference file
3. 搜索匹配 extension 的 section heading（例如 "### .pdb"）
4. 提取 format information

### Reference File Structure

每个 format entry 包含：
- **Description：** 该格式是什么
- **Typical Data：** 它包含什么
- **Use Cases：** 常见应用
- **Python Libraries：** 如何读取它（带 code examples）
- **EDA Approach：** 要执行的具体分析

**示例 lookup：**
```markdown
### .pdb - Protein Data Bank
**Description:** Standard format for 3D structures of biological macromolecules
**Typical Data:** Atomic coordinates, residue information, secondary structure
**Use Cases:** Protein structure analysis, molecular visualization, docking
**Python Libraries:**
- `Biopython`: `Bio.PDB`
- `MDAnalysis`: `MDAnalysis.Universe('file.pdb')`
**EDA Approach:**
- Structure validation (bond lengths, angles)
- B-factor distribution
- Missing residues detection
- Ramachandran plots
```

## 最佳实践

### 阅读 Reference Files

Reference files 很大（每个 10,000+ words）。为高效使用它们：

1. **按 extension 搜索：** 使用 grep 找到特定 format
   ```python
   import re
   with open('references/chemistry_molecular_formats.md', 'r') as f:
       content = f.read()
       pattern = r'### \.pdb[^#]*?(?=###|\Z)'
       match = re.search(pattern, content, re.IGNORECASE | re.DOTALL)
   ```

2. **提取相关 sections：** 不要不必要地将整个 reference files 加载到上下文

3. **缓存 format info：** 如果分析多个相同类型文件，复用 format information

### Data Analysis

1. **采样大文件：** 对有数百万条 records 的文件，分析代表性 sample
2. **优雅处理错误：** 许多 scientific formats 需要特定 libraries；提供清晰安装说明
3. **验证 metadata：** 交叉检查 metadata consistency（例如 stated dimensions vs actual data）
4. **考虑 data provenance：** 记录 instrument、software versions、processing steps

### Report Generation

1. **全面：** 包含 downstream analysis 所需的所有相关信息
2. **具体：** 基于 file type 提供具体 recommendations
3. **可执行：** 建议具体 next steps 和 tools
4. **包含 code examples：** 展示如何加载并处理数据

## 示例

### Example 1：分析 FASTQ 文件

```python
# User provides: "Analyze reads.fastq"

# 1. Detect file type
extension = '.fastq'
category = 'bioinformatics_genomics'

# 2. Read reference info
# Search references/bioinformatics_genomics_formats.md for "### .fastq"

# 3. Perform analysis
from Bio import SeqIO
sequences = list(SeqIO.parse('reads.fastq', 'fastq'))
# Calculate: read count, length distribution, quality scores, GC content

# 4. Generate report
# Include: format description, analysis results, QC recommendations

# 5. Save as: reads_eda_report.md
```

### Example 2：分析 CSV dataset

```python
# User provides: "Explore experiment_results.csv"

# 1. Detect: .csv → general_scientific

# 2. Load reference for CSV format

# 3. Analyze
import pandas as pd
df = pd.read_csv('experiment_results.csv')
# Dimensions, dtypes, missing values, statistics, correlations

# 4. Generate report with:
# - Data structure
# - Missing value patterns
# - Statistical summaries
# - Correlation matrix
# - Outlier detection results

# 5. Save report
```

### Example 3：分析 microscopy data

```python
# User provides: "Analyze cells.nd2"

# 1. Detect: .nd2 → microscopy_imaging (Nikon format)

# 2. Read reference for ND2 format
# Learn: multi-dimensional (XYZCT), requires nd2reader

# 3. Analyze
from nd2reader import ND2Reader
with ND2Reader('cells.nd2') as images:
    # Extract: dimensions, channels, timepoints, metadata
    # Calculate: intensity statistics, frame info

# 4. Generate report with:
# - Image dimensions (XY, Z-stacks, time, channels)
# - Channel wavelengths
# - Pixel size and calibration
# - Recommendations for image analysis

# 5. Save report
```

## 故障排除

### 缺失 Libraries

许多 scientific formats 需要 specialized libraries：

**问题：** 读取文件时发生 import error

**解决方案：** 提供清晰安装说明
```python
try:
    from Bio import SeqIO
except ImportError:
    print("Install Biopython: uv pip install biopython")
```

按类别的常见 requirements：
- **Bioinformatics：** `biopython`、`pysam`、`pyBigWig`
- **Chemistry：** `rdkit`、`mdanalysis`、`cclib`
- **Microscopy：** `tifffile`、`nd2reader`、`aicsimageio`、`pydicom`
- **Spectroscopy：** `nmrglue`、`pymzml`、`pyteomics`
- **General：** `pandas`、`numpy`、`h5py`、`scipy`

### Unknown File Types

如果 file extension 不在 references 中：

1. 询问用户该文件格式
2. 检查它是否为 vendor-specific variant
3. 根据文件结构（text vs binary）尝试 generic analysis
4. 提供一般 recommendations

### 大文件

对于非常大的文件：

1. 使用 sampling strategies（前 N 条 records）
2. 使用 memory-mapped access（用于 HDF5、NPY）
3. 分 chunks 处理（用于 CSV、FASTQ）
4. 基于 samples 提供估计

## Script Usage

`scripts/eda_analyzer.py` 可直接使用：

```bash
# Basic usage
python scripts/eda_analyzer.py data.csv

# Specify output file
python scripts/eda_analyzer.py data.csv output_report.md

# The script will:
# 1. Auto-detect file type
# 2. Load format references
# 3. Perform appropriate analysis
# 4. Generate markdown report
```

该脚本支持对许多常见 formats 进行自动分析，但在对话中做 custom analysis 能提供更高灵活性和 domain-specific insights。

## 高级用法

### Multi-File Analysis

分析多个相关文件时：
1. 对每个文件执行 individual EDA
2. 创建 summary comparison report
3. 识别 relationships 和 dependencies
4. 建议 integration strategies

### Quality Control

进行 data quality assessment 时：
1. 检查 format compliance
2. 验证 metadata consistency
3. 评估 completeness
4. 识别 outliers 和 anomalies
5. 与 expected ranges/distributions 比较

### Preprocessing Recommendations

基于 data characteristics，推荐：
1. Normalization strategies
2. Missing value imputation
3. Outlier handling
4. Batch correction
5. Format conversions

## 资源

### scripts/
- `eda_analyzer.py`：可直接运行或导入的综合 analysis script

### references/
- `chemistry_molecular_formats.md`：60+ chemistry/molecular file formats
- `bioinformatics_genomics_formats.md`：50+ bioinformatics formats
- `microscopy_imaging_formats.md`：45+ imaging formats
- `spectroscopy_analytical_formats.md`：35+ spectroscopy formats
- `proteomics_metabolomics_formats.md`：30+ omics formats
- `general_scientific_formats.md`：30+ general formats

### assets/
- `report_template.md`：用于 EDA reports 的综合 markdown template
