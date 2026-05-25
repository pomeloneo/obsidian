---
name: pyopenms
description: 完整的 mass spectrometry analysis platform。用于 proteomics workflows 的 feature detection、peptide identification、protein quantification 和 complex LC-MS/MS pipelines。支持广泛 file formats 和 algorithms。最适合 proteomics 与 comprehensive MS data processing。简单 spectral comparison 和 metabolite ID 请用 matchms。
license: 3 clause BSD license
metadata:
    skill-author: K-Dense Inc.
---

# PyOpenMS

## 概览

PyOpenMS 为 computational mass spectrometry 的 OpenMS library 提供 Python bindings，支持分析 proteomics 和 metabolomics data。用于处理 mass spectrometry file formats、processing spectral data、detecting features、identifying peptides/proteins，以及 performing quantitative analysis。

## 安装

使用 uv 安装：

```bash
uv pip install pyopenms
```

验证安装：

```python
import pyopenms
print(pyopenms.__version__)
```

## 核心能力

PyOpenMS 将功能组织为以下领域：

### 1. File I/O 和 Data Formats

处理 mass spectrometry file formats，并在 representations 之间转换。

**Supported formats**：mzML、mzXML、TraML、mzTab、FASTA、pepXML、protXML、mzIdentML、featureXML、consensusXML、idXML

基础 file reading：

```python
import pyopenms as ms

# Read mzML file
exp = ms.MSExperiment()
ms.MzMLFile().load("data.mzML", exp)

# Access spectra
for spectrum in exp:
    mz, intensity = spectrum.get_peaks()
    print(f"Spectrum: {len(mz)} peaks")
```

**详细 file handling**：参见 `references/file_io.md`

### 2. Signal Processing

使用 smoothing、filtering、centroiding 和 normalization 处理 raw spectral data。

基础 spectrum processing：

```python
# Smooth spectrum with Gaussian filter
gaussian = ms.GaussFilter()
params = gaussian.getParameters()
params.setValue("gaussian_width", 0.1)
gaussian.setParameters(params)
gaussian.filterExperiment(exp)
```

**algorithm details**：参见 `references/signal_processing.md`

### 3. Feature Detection

在 spectra 和 samples 中 detect 并 link features，用于 quantitative analysis。

```python
# Detect features
ff = ms.FeatureFinder()
ff.run("centroided", exp, features, params, ms.FeatureMap())
```

**完整 workflows**：参见 `references/feature_detection.md`

### 4. Peptide and Protein Identification

与 search engines 集成并处理 identification results。

**Supported engines**：Comet、Mascot、MSGFPlus、XTandem、OMSSA、Myrimatch

基础 identification workflow：

```python
# Load identification data
protein_ids = []
peptide_ids = []
ms.IdXMLFile().load("identifications.idXML", protein_ids, peptide_ids)

# Apply FDR filtering
fdr = ms.FalseDiscoveryRate()
fdr.apply(peptide_ids)
```

**详细 workflows**：参见 `references/identification.md`

### 5. Metabolomics Analysis

执行 untargeted metabolomics preprocessing 和 analysis。

典型 workflow：
1. 加载并处理 raw data
2. Detect features
3. 在 samples 间 align retention times
4. 将 features link 到 consensus map
5. 使用 compound databases 进行 annotate

**完整 metabolomics workflows**：参见 `references/metabolomics.md`

## Data Structures

PyOpenMS 使用以下主要 objects：

- **MSExperiment**：spectra 和 chromatograms 的 collection
- **MSSpectrum**：包含 m/z 和 intensity pairs 的 single mass spectrum
- **MSChromatogram**：Chromatographic trace
- **Feature**：带 quality metrics 的 detected chromatographic peak
- **FeatureMap**：features 的 collection
- **PeptideIdentification**：peptides 的 search results
- **ProteinIdentification**：proteins 的 search results

**详细文档**：参见 `references/data_structures.md`

## 常见 Workflows

### 快速开始：Load and Explore Data

```python
import pyopenms as ms

# Load mzML file
exp = ms.MSExperiment()
ms.MzMLFile().load("sample.mzML", exp)

# Get basic statistics
print(f"Number of spectra: {exp.getNrSpectra()}")
print(f"Number of chromatograms: {exp.getNrChromatograms()}")

# Examine first spectrum
spec = exp.getSpectrum(0)
print(f"MS level: {spec.getMSLevel()}")
print(f"Retention time: {spec.getRT()}")
mz, intensity = spec.get_peaks()
print(f"Peaks: {len(mz)}")
```

### Parameter Management

大多数 algorithms 使用 parameter system：

```python
# Get algorithm parameters
algo = ms.GaussFilter()
params = algo.getParameters()

# View available parameters
for param in params.keys():
    print(f"{param}: {params.getValue(param)}")

# Modify parameters
params.setValue("gaussian_width", 0.2)
algo.setParameters(params)
```

### Export to Pandas

将 data 转换为 pandas DataFrames 以便 analysis：

```python
import pyopenms as ms
import pandas as pd

# Load feature map
fm = ms.FeatureMap()
ms.FeatureXMLFile().load("features.featureXML", fm)

# Convert to DataFrame
df = fm.get_df()
print(df.head())
```

## 与其他 Tools 的集成

PyOpenMS 可与以下集成：
- **Pandas**：将 data 导出到 DataFrames
- **NumPy**：处理 peak arrays
- **Scikit-learn**：在 MS data 上进行 machine learning
- **Matplotlib/Seaborn**：Visualization
- **R**：通过 rpy2 bridge

## 资源

- **Official documentation**：https://pyopenms.readthedocs.io
- **OpenMS documentation**：https://www.openms.org
- **GitHub**: https://github.com/OpenMS/OpenMS

## 参考资料

- `references/file_io.md` - Comprehensive file format handling
- `references/signal_processing.md` - Signal processing algorithms
- `references/feature_detection.md` - Feature detection and linking
- `references/identification.md` - Peptide and protein identification
- `references/metabolomics.md` - Metabolomics-specific workflows
- `references/data_structures.md` - Core objects and data structures
