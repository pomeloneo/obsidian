---
name: pydeseq2
description: Differential gene expression analysis（Python DESeq2）。从 bulk RNA-seq counts 识别 DE genes，支持 Wald tests、FDR correction、volcano/MA plots，用于 RNA-seq analysis。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# PyDESeq2

## 概览

PyDESeq2 是 DESeq2 的 Python implementation，用于对 bulk RNA-seq data 进行 differential expression analysis。它可设计并执行从 data loading 到 result interpretation 的完整 workflows，包括 single-factor 和 multi-factor designs、带 multiple testing correction 的 Wald tests、可选 apeGLM shrinkage，以及与 pandas 和 AnnData 的集成。

## 何时使用此 Skill

此 skill 应用于：
- 分析 bulk RNA-seq count data 以进行 differential expression
- 比较 experimental conditions 之间的 gene expression（例如 treated vs control）
- 执行考虑 batch effects 或 covariates 的 multi-factor designs
- 将 R-based DESeq2 workflows 转换为 Python
- 将 differential expression analysis 集成到 Python-based pipelines
- 用户提到 "DESeq2"、"differential expression"、"RNA-seq analysis" 或 "PyDESeq2"

## Quick Start Workflow

对于想执行标准 differential expression analysis 的用户：

```python
import pandas as pd
from pydeseq2.dds import DeseqDataSet
from pydeseq2.ds import DeseqStats

# 1. Load data
counts_df = pd.read_csv("counts.csv", index_col=0).T  # Transpose to samples × genes
metadata = pd.read_csv("metadata.csv", index_col=0)

# 2. Filter low-count genes
genes_to_keep = counts_df.columns[counts_df.sum(axis=0) >= 10]
counts_df = counts_df[genes_to_keep]

# 3. Initialize and fit DESeq2
dds = DeseqDataSet(
    counts=counts_df,
    metadata=metadata,
    design="~condition",
    refit_cooks=True
)
dds.deseq2()

# 4. Perform statistical testing
ds = DeseqStats(dds, contrast=["condition", "treated", "control"])
ds.summary()

# 5. Access results
results = ds.results_df
significant = results[results.padj < 0.05]
print(f"Found {len(significant)} significant genes")
```

## 核心 Workflow Steps

### Step 1：Data Preparation

**Input requirements：**
- **Count matrix：** Samples × genes DataFrame，包含非负整数 read counts
- **Metadata：** Samples × variables DataFrame，包含 experimental factors

**常见 data loading patterns：**

```python
# From CSV (typical format: genes × samples, needs transpose)
counts_df = pd.read_csv("counts.csv", index_col=0).T
metadata = pd.read_csv("metadata.csv", index_col=0)

# From TSV
counts_df = pd.read_csv("counts.tsv", sep="\t", index_col=0).T

# From AnnData
import anndata as ad
adata = ad.read_h5ad("data.h5ad")
counts_df = pd.DataFrame(adata.X, index=adata.obs_names, columns=adata.var_names)
metadata = adata.obs
```

**Data filtering：**

```python
# Remove low-count genes
genes_to_keep = counts_df.columns[counts_df.sum(axis=0) >= 10]
counts_df = counts_df[genes_to_keep]

# Remove samples with missing metadata
samples_to_keep = ~metadata.condition.isna()
counts_df = counts_df.loc[samples_to_keep]
metadata = metadata.loc[samples_to_keep]
```

### Step 2：Design Specification

design formula 指定如何建模 gene expression。

**Single-factor designs：**
```python
design = "~condition"  # Simple two-group comparison
```

**Multi-factor designs：**
```python
design = "~batch + condition"  # Control for batch effects
design = "~age + condition"     # Include continuous covariate
design = "~group + condition + group:condition"  # Interaction effects
```

**Design formula guidelines：**
- 使用 Wilkinson formula notation（R-style）
- 将 adjustment variables（例如 batch）放在主要 variable of interest 之前
- 确保 variables 作为 columns 存在于 metadata DataFrame 中
- 使用合适 data types（discrete variables 使用 categorical）

### Step 3：DESeq2 Fitting

初始化 DeseqDataSet 并运行完整 pipeline：

```python
from pydeseq2.dds import DeseqDataSet

dds = DeseqDataSet(
    counts=counts_df,
    metadata=metadata,
    design="~condition",
    refit_cooks=True,  # Refit after removing outliers
    n_cpus=1           # Parallel processing (adjust as needed)
)

# Run the complete DESeq2 pipeline
dds.deseq2()
```

**`deseq2()` 做什么：**
1. 计算 size factors（normalization）
2. 拟合 genewise dispersions
3. 拟合 dispersion trend curve
4. 计算 dispersion priors
5. 拟合 MAP dispersions（shrinkage）
6. 拟合 log fold changes
7. 计算 Cook's distances（outlier detection）
8. 如果检测到 outliers，则 refit（可选）

### Step 4：Statistical Testing

执行 Wald tests 以识别 differentially expressed genes：

```python
from pydeseq2.ds import DeseqStats

ds = DeseqStats(
    dds,
    contrast=["condition", "treated", "control"],  # Test treated vs control
    alpha=0.05,                # Significance threshold
    cooks_filter=True,         # Filter outliers
    independent_filter=True    # Filter low-power tests
)

ds.summary()
```

**Contrast specification：**
- 格式：`[variable, test_level, reference_level]`
- 示例：`["condition", "treated", "control"]` 测试 treated vs control
- 如果为 `None`，则使用 design 中的最后一个 coefficient

**Result DataFrame columns：**
- `baseMean`：samples 间 mean normalized count
- `log2FoldChange`：conditions 之间的 Log2 fold change
- `lfcSE`：LFC 的 standard error
- `stat`：Wald test statistic
- `pvalue`：Raw p-value
- `padj`：Adjusted p-value（通过 Benjamini-Hochberg 进行 FDR-corrected）

### Step 5：Optional LFC Shrinkage

应用 shrinkage，以减少 fold change estimates 中的 noise：

```python
ds.lfc_shrink()  # Applies apeGLM shrinkage
```

**何时使用 LFC shrinkage：**
- 用于 visualization（volcano plots、heatmaps）
- 按 effect size 排序 genes
- 为 follow-up experiments 优先排序 genes

**重要：** Shrinkage 只影响 log2FoldChange values，不影响 statistical test results（p-values 保持不变）。使用 shrunk values 进行 visualization，但报告 unshrunken p-values 作为 significance。

### Step 6：Result Export

保存 results 和 intermediate objects：

```python
import pickle

# Export results as CSV
ds.results_df.to_csv("deseq2_results.csv")

# Save significant genes only
significant = ds.results_df[ds.results_df.padj < 0.05]
significant.to_csv("significant_genes.csv")

# Save DeseqDataSet for later use
with open("dds_result.pkl", "wb") as f:
    pickle.dump(dds.to_picklable_anndata(), f)
```

## 常见 Analysis Patterns

### Two-Group Comparison

标准 case-control comparison：

```python
dds = DeseqDataSet(counts=counts_df, metadata=metadata, design="~condition")
dds.deseq2()

ds = DeseqStats(dds, contrast=["condition", "treated", "control"])
ds.summary()

results = ds.results_df
significant = results[results.padj < 0.05]
```

### Multiple Comparisons

将多个 treatment groups 与 control 进行测试：

```python
dds = DeseqDataSet(counts=counts_df, metadata=metadata, design="~condition")
dds.deseq2()

treatments = ["treatment_A", "treatment_B", "treatment_C"]
all_results = {}

for treatment in treatments:
    ds = DeseqStats(dds, contrast=["condition", treatment, "control"])
    ds.summary()
    all_results[treatment] = ds.results_df

    sig_count = len(ds.results_df[ds.results_df.padj < 0.05])
    print(f"{treatment}: {sig_count} significant genes")
```

### Accounting for Batch Effects

控制 technical variation：

```python
# Include batch in design
dds = DeseqDataSet(counts=counts_df, metadata=metadata, design="~batch + condition")
dds.deseq2()

# Test condition while controlling for batch
ds = DeseqStats(dds, contrast=["condition", "treated", "control"])
ds.summary()
```

### Continuous Covariates

包含 age 或 dosage 等 continuous variables：

```python
# Ensure continuous variable is numeric
metadata["age"] = pd.to_numeric(metadata["age"])

dds = DeseqDataSet(counts=counts_df, metadata=metadata, design="~age + condition")
dds.deseq2()

ds = DeseqStats(dds, contrast=["condition", "treated", "control"])
ds.summary()
```

## 使用 Analysis Script

此 skill 包含用于 standard analyses 的完整 command-line script：

```bash
# Basic usage
python scripts/run_deseq2_analysis.py \
  --counts counts.csv \
  --metadata metadata.csv \
  --design "~condition" \
  --contrast condition treated control \
  --output results/

# With additional options
python scripts/run_deseq2_analysis.py \
  --counts counts.csv \
  --metadata metadata.csv \
  --design "~batch + condition" \
  --contrast condition treated control \
  --output results/ \
  --min-counts 10 \
  --alpha 0.05 \
  --n-cpus 4 \
  --plots
```

**Script features：**
- 自动 data loading 和 validation
- Gene 和 sample filtering
- 完整 DESeq2 pipeline execution
- 带 customizable parameters 的 statistical testing
- Result export（CSV、pickle）
- 可选 visualization（volcano 和 MA plots）

当用户需要 standalone analysis tool 或想 batch process multiple datasets 时，引导他们使用 `scripts/run_deseq2_analysis.py`。

## Result Interpretation

### 识别 Significant Genes

```python
# Filter by adjusted p-value
significant = ds.results_df[ds.results_df.padj < 0.05]

# Filter by both significance and effect size
sig_and_large = ds.results_df[
    (ds.results_df.padj < 0.05) &
    (abs(ds.results_df.log2FoldChange) > 1)
]

# Separate up- and down-regulated
upregulated = significant[significant.log2FoldChange > 0]
downregulated = significant[significant.log2FoldChange < 0]

print(f"Upregulated: {len(upregulated)}")
print(f"Downregulated: {len(downregulated)}")
```

### Ranking and Sorting

```python
# Sort by adjusted p-value
top_by_padj = ds.results_df.sort_values("padj").head(20)

# Sort by absolute fold change (use shrunk values)
ds.lfc_shrink()
ds.results_df["abs_lfc"] = abs(ds.results_df.log2FoldChange)
top_by_lfc = ds.results_df.sort_values("abs_lfc", ascending=False).head(20)

# Sort by a combined metric
ds.results_df["score"] = -np.log10(ds.results_df.padj) * abs(ds.results_df.log2FoldChange)
top_combined = ds.results_df.sort_values("score", ascending=False).head(20)
```

### Quality Metrics

```python
# Check normalization (size factors should be close to 1)
print("Size factors:", dds.obsm["size_factors"])

# Examine dispersion estimates
import matplotlib.pyplot as plt
plt.hist(dds.varm["dispersions"], bins=50)
plt.xlabel("Dispersion")
plt.ylabel("Frequency")
plt.title("Dispersion Distribution")
plt.show()

# Check p-value distribution (should be mostly flat with peak near 0)
plt.hist(ds.results_df.pvalue.dropna(), bins=50)
plt.xlabel("P-value")
plt.ylabel("Frequency")
plt.title("P-value Distribution")
plt.show()
```

## Visualization Guidelines

### Volcano Plot

可视化 significance vs effect size：

```python
import matplotlib.pyplot as plt
import numpy as np

results = ds.results_df.copy()
results["-log10(padj)"] = -np.log10(results.padj)

plt.figure(figsize=(10, 6))
significant = results.padj < 0.05

plt.scatter(
    results.loc[~significant, "log2FoldChange"],
    results.loc[~significant, "-log10(padj)"],
    alpha=0.3, s=10, c='gray', label='Not significant'
)
plt.scatter(
    results.loc[significant, "log2FoldChange"],
    results.loc[significant, "-log10(padj)"],
    alpha=0.6, s=10, c='red', label='padj < 0.05'
)

plt.axhline(-np.log10(0.05), color='blue', linestyle='--', alpha=0.5)
plt.xlabel("Log2 Fold Change")
plt.ylabel("-Log10(Adjusted P-value)")
plt.title("Volcano Plot")
plt.legend()
plt.savefig("volcano_plot.png", dpi=300)
```

### MA Plot

展示 fold change vs mean expression：

```python
plt.figure(figsize=(10, 6))

plt.scatter(
    np.log10(results.loc[~significant, "baseMean"] + 1),
    results.loc[~significant, "log2FoldChange"],
    alpha=0.3, s=10, c='gray'
)
plt.scatter(
    np.log10(results.loc[significant, "baseMean"] + 1),
    results.loc[significant, "log2FoldChange"],
    alpha=0.6, s=10, c='red'
)

plt.axhline(0, color='blue', linestyle='--', alpha=0.5)
plt.xlabel("Log10(Base Mean + 1)")
plt.ylabel("Log2 Fold Change")
plt.title("MA Plot")
plt.savefig("ma_plot.png", dpi=300)
```

## 常见问题排查

### Data Format Problems

**Issue：** "Index mismatch between counts and metadata"

**Solution：** 确保 sample names 完全匹配
```python
print("Counts samples:", counts_df.index.tolist())
print("Metadata samples:", metadata.index.tolist())

# Take intersection if needed
common = counts_df.index.intersection(metadata.index)
counts_df = counts_df.loc[common]
metadata = metadata.loc[common]
```

**Issue：** "All genes have zero counts"

**Solution：** 检查 data 是否需要 transposition
```python
print(f"Counts shape: {counts_df.shape}")
# If genes > samples, transpose is needed
if counts_df.shape[1] < counts_df.shape[0]:
    counts_df = counts_df.T
```

### Design Matrix Issues

**Issue：** "Design matrix is not full rank"

**Cause：** Confounded variables（例如所有 treated samples 都在同一个 batch 中）

**Solution：** 移除 confounded variable 或添加 interaction term
```python
# Check confounding
print(pd.crosstab(metadata.condition, metadata.batch))

# Either simplify design or add interaction
design = "~condition"  # Remove batch
# OR
design = "~condition + batch + condition:batch"  # Model interaction
```

### No Significant Genes

**Diagnostics：**
```python
# Check dispersion distribution
plt.hist(dds.varm["dispersions"], bins=50)
plt.show()

# Check size factors
print(dds.obsm["size_factors"])

# Look at top genes by raw p-value
print(ds.results_df.nsmallest(20, "pvalue"))
```

**Possible causes：**
- Small effect sizes
- High biological variability
- Insufficient sample size
- Technical issues（batch effects、outliers）

## Reference Documentation

如需此 workflow-oriented guide 之外的完整细节：

- **API Reference**（`references/api_reference.md`）：PyDESeq2 classes、methods 和 data structures 的完整文档。需要详细 parameter information 或理解 object attributes 时使用。

- **Workflow Guide**（`references/workflow_guide.md`）：深入指南，覆盖 complete analysis workflows、data loading patterns、multi-factor designs、troubleshooting 和 best practices。处理 complex experimental designs 或遇到问题时使用。

当用户需要以下内容时，将这些 references 加载到 context 中：
- Detailed API documentation：`Read references/api_reference.md`
- Comprehensive workflow examples：`Read references/workflow_guide.md`
- Troubleshooting guidance：`Read references/workflow_guide.md`（见 Troubleshooting section）

## Key Reminders

1. **Data orientation matters：** Count matrices 通常加载为 genes × samples，但需要 samples × genes。如有需要，始终用 `.T` 转置。

2. **Sample filtering：** 分析前移除缺少 metadata 的 samples，以避免 errors。

3. **Gene filtering：** 过滤 low-count genes（例如 total reads < 10），以提高 power 并减少 computational time。

4. **Design formula order：** 将 adjustment variables 放在 variable of interest 之前（例如 `"~batch + condition"`，而不是 `"~condition + batch"`）。

5. **LFC shrinkage timing：** 在 statistical testing 后应用 shrinkage，且仅用于 visualization/ranking。P-values 仍基于 unshrunken estimates。

6. **Result interpretation：** 使用 `padj < 0.05` 判断 significance，而不是 raw p-values。Benjamini-Hochberg procedure 控制 false discovery rate。

7. **Contrast specification：** 格式为 `[variable, test_level, reference_level]`，其中 test_level 与 reference_level 比较。

8. **Save intermediate objects：** 使用 pickle 保存 DeseqDataSet objects，便于后续使用或 additional analyses，而无需重新运行昂贵的 fitting step。

## Installation and Requirements

```bash
uv pip install pydeseq2
```

**System requirements：**
- Python 3.10-3.11
- pandas 1.4.3+
- numpy 1.23.0+
- scipy 1.11.0+
- scikit-learn 1.1.1+
- anndata 0.8.0+

**Optional for visualization：**
- matplotlib
- seaborn

## 其他资源

- **Official Documentation：** https://pydeseq2.readthedocs.io
- **GitHub Repository：** https://github.com/owkin/PyDESeq2
- **Publication：** Muzellec et al. (2023) Bioinformatics, DOI: 10.1093/bioinformatics/btad547
- **Original DESeq2 (R)：** Love et al. (2014) Genome Biology, DOI: 10.1186/s13059-014-0550-8
