---
name: scikit-bio
description: Biological data toolkit。Sequence analysis、alignments、phylogenetic trees、diversity metrics（alpha/beta、UniFrac）、ordination（PCoA）、PERMANOVA、FASTA/Newick I/O，用于 microbiome analysis。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# scikit-bio

## 概述

scikit-bio 是一个用于处理 biological data 的综合 Python library。将此 skill 用于 bioinformatics analyses，覆盖 sequence manipulation、alignment、phylogenetics、microbial ecology 和 multivariate statistics。

## 何时使用此 Skill

当用户有以下需求时，应使用此 skill：
- 处理 biological sequences（DNA、RNA、protein）
- 读写 biological file formats（FASTA、FASTQ、GenBank、Newick、BIOM 等）
- 执行 sequence alignments 或搜索 motifs
- 构建或分析 phylogenetic trees
- 计算 diversity metrics（alpha/beta diversity、UniFrac distances）
- 执行 ordination analysis（PCoA、CCA、RDA）
- 对 biological/ecological data 运行 statistical tests（PERMANOVA、ANOSIM、Mantel）
- 分析 microbiome 或 community ecology data
- 处理来自 language models 的 protein embeddings
- 操作 biological data tables

## 核心能力

### 1. Sequence Manipulation

使用面向 DNA、RNA 和 protein data 的专用 classes 处理 biological sequences。

**Key operations：**
- 从 FASTA、FASTQ、GenBank、EMBL formats 读写 sequences
- Sequence slicing、concatenation 和 searching
- Reverse complement、transcription（DNA→RNA）和 translation（RNA→protein）
- 使用 regex 查找 motifs 和 patterns
- 计算 distances（Hamming、k-mer based）
- 处理 sequence quality scores 和 metadata

**Common patterns：**
```python
import skbio

# Read sequences from file
seq = skbio.DNA.read('input.fasta')

# Sequence operations
rc = seq.reverse_complement()
rna = seq.transcribe()
protein = rna.translate()

# Find motifs
motif_positions = seq.find_with_regex('ATG[ACGT]{3}')

# Check for properties
has_degens = seq.has_degenerates()
seq_no_gaps = seq.degap()
```

**重要说明：**
- 对带 grammar 且需要 validation 的 sequences 使用 `DNA`、`RNA`、`Protein` classes
- 对无 alphabet restrictions 的通用 sequences 使用 `Sequence` class
- FASTQ files 中的 quality scores 会自动加载到 positional metadata
- Metadata types：sequence-level（ID、description）、positional（per-base）、interval（regions/features）

### 2. Sequence Alignment

使用 dynamic programming algorithms 执行 pairwise 和 multiple sequence alignments。

**Key capabilities：**
- Global alignment（Needleman-Wunsch，含 semi-global variant）
- Local alignment（Smith-Waterman）
- 可配置 scoring schemes（match/mismatch、gap penalties、substitution matrices）
- CIGAR string conversion
- 用 `TabularMSA` 存储和操作 multiple sequence alignment

**Common patterns：**
```python
from skbio.alignment import local_pairwise_align_ssw, TabularMSA

# Pairwise alignment
alignment = local_pairwise_align_ssw(seq1, seq2)

# Access aligned sequences
msa = alignment.aligned_sequences

# Read multiple alignment from file
msa = TabularMSA.read('alignment.fasta', constructor=skbio.DNA)

# Calculate consensus
consensus = msa.consensus()
```

**重要说明：**
- Local alignments 使用 `local_pairwise_align_ssw`（更快，基于 SSW）
- Protein alignments 使用 `StripedSmithWaterman`
- Biological sequences 推荐使用 affine gap penalties
- 可在 scikit-bio、BioPython 和 Biotite alignment formats 之间转换

### 3. Phylogenetic Trees

构建、操作并分析表示 evolutionary relationships 的 phylogenetic trees。

**Key capabilities：**
- 从 distance matrices 构建 tree（UPGMA、WPGMA、Neighbor Joining、GME、BME）
- Tree manipulation（pruning、rerooting、traversal）
- Distance calculations（patristic、cophenetic、Robinson-Foulds）
- ASCII visualization
- Newick format I/O

**Common patterns：**
```python
from skbio import TreeNode
from skbio.tree import nj

# Read tree from file
tree = TreeNode.read('tree.nwk')

# Construct tree from distance matrix
tree = nj(distance_matrix)

# Tree operations
subtree = tree.shear(['taxon1', 'taxon2', 'taxon3'])
tips = [node for node in tree.tips()]
lca = tree.lowest_common_ancestor(['taxon1', 'taxon2'])

# Calculate distances
patristic_dist = tree.find('taxon1').distance(tree.find('taxon2'))
cophenetic_matrix = tree.cophenetic_matrix()

# Compare trees
rf_distance = tree.robinson_foulds(other_tree)
```

**重要说明：**
- Neighbor joining 使用 `nj()`（经典 phylogenetic method）
- UPGMA 使用 `upgma()`（假设 molecular clock）
- GME 和 BME 对 large trees 高度可扩展
- Trees 可 rooted 或 unrooted；某些 metrics 需要特定 rooting

### 4. Diversity Analysis

为 microbial ecology 和 community analysis 计算 alpha 与 beta diversity metrics。

**Key capabilities：**
- Alpha diversity：richness、Shannon entropy、Simpson index、Faith's PD、Pielou's evenness
- Beta diversity：Bray-Curtis、Jaccard、weighted/unweighted UniFrac、Euclidean distances
- Phylogenetic diversity metrics（需要 tree input）
- Rarefaction 和 subsampling
- 与 ordination 和 statistical tests 集成

**Common patterns：**
```python
from skbio.diversity import alpha_diversity, beta_diversity
import skbio

# Alpha diversity
alpha = alpha_diversity('shannon', counts_matrix, ids=sample_ids)
faith_pd = alpha_diversity('faith_pd', counts_matrix, ids=sample_ids,
                          tree=tree, otu_ids=feature_ids)

# Beta diversity
bc_dm = beta_diversity('braycurtis', counts_matrix, ids=sample_ids)
unifrac_dm = beta_diversity('unweighted_unifrac', counts_matrix,
                           ids=sample_ids, tree=tree, otu_ids=feature_ids)

# Get available metrics
from skbio.diversity import get_alpha_diversity_metrics
print(get_alpha_diversity_metrics())
```

**重要说明：**
- Counts 必须是表示 abundances 的 integers，而不是 relative frequencies
- Phylogenetic metrics（Faith's PD、UniFrac）需要 tree 和 OTU ID mapping
- 仅计算特定 sample pairs 时使用 `partial_beta_diversity()`
- Alpha diversity 返回 Series，beta diversity 返回 DistanceMatrix

### 5. Ordination Methods

将 high-dimensional biological data 降维到可视化的 lower-dimensional spaces。

**Key capabilities：**
- 基于 distance matrices 的 PCoA（Principal Coordinate Analysis）
- Contingency tables 的 CA（Correspondence Analysis）
- 带 environmental constraints 的 CCA（Canonical Correspondence Analysis）
- Linear relationships 的 RDA（Redundancy Analysis）
- 用于 feature interpretation 的 biplot projection

**Common patterns：**
```python
from skbio.stats.ordination import pcoa, cca

# PCoA from distance matrix
pcoa_results = pcoa(distance_matrix)
pc1 = pcoa_results.samples['PC1']
pc2 = pcoa_results.samples['PC2']

# CCA with environmental variables
cca_results = cca(species_matrix, environmental_matrix)

# Save/load ordination results
pcoa_results.write('ordination.txt')
results = skbio.OrdinationResults.read('ordination.txt')
```

**重要说明：**
- PCoA 可处理任意 distance/dissimilarity matrix
- CCA 揭示 community composition 的 environmental drivers
- Ordination results 包含 eigenvalues、proportion explained 和 sample/feature coordinates
- Results 可与 plotting libraries（matplotlib、seaborn、plotly）集成

### 6. Statistical Testing

执行生态学和 biological data 特有的 hypothesis tests。

**Key capabilities：**
- PERMANOVA：使用 distance matrices 测试 group differences
- ANOSIM：group differences 的替代测试
- PERMDISP：测试 group dispersions 的 homogeneity
- Mantel test：distance matrices 之间的 correlation
- Bioenv：寻找与 distances 相关的 environmental variables

**Common patterns：**
```python
from skbio.stats.distance import permanova, anosim, mantel

# Test if groups differ significantly
permanova_results = permanova(distance_matrix, grouping, permutations=999)
print(f"p-value: {permanova_results['p-value']}")

# ANOSIM test
anosim_results = anosim(distance_matrix, grouping, permutations=999)

# Mantel test between two distance matrices
mantel_results = mantel(dm1, dm2, method='pearson', permutations=999)
print(f"Correlation: {mantel_results[0]}, p-value: {mantel_results[1]}")
```

**重要说明：**
- Permutation tests 提供 non-parametric significance testing
- 使用 999+ permutations 以获得 robust p-values
- PERMANOVA 对 dispersion differences 敏感；应配合 PERMDISP
- Mantel tests 评估 matrix correlation（例如 geographic vs genetic distance）

### 7. File I/O and Format Conversion

读取和写入 19+ biological file formats，并支持 automatic format detection。

**Supported formats：**
- Sequences：FASTA、FASTQ、GenBank、EMBL、QSeq
- Alignments：Clustal、PHYLIP、Stockholm
- Trees：Newick
- Tables：BIOM（HDF5 和 JSON）
- Distances：delimited square matrices
- Analysis：BLAST+6/7、GFF3、Ordination results
- Metadata：TSV/CSV with validation

**Common patterns：**
```python
import skbio

# Read with automatic format detection
seq = skbio.DNA.read('file.fasta', format='fasta')
tree = skbio.TreeNode.read('tree.nwk')

# Write to file
seq.write('output.fasta', format='fasta')

# Generator for large files (memory efficient)
for seq in skbio.io.read('large.fasta', format='fasta', constructor=skbio.DNA):
    process(seq)

# Convert formats
seqs = list(skbio.io.read('input.fastq', format='fastq', constructor=skbio.DNA))
skbio.io.write(seqs, format='fasta', into='output.fasta')
```

**重要说明：**
- 大文件使用 generators，避免 memory issues
- 指定 `into` parameter 时可自动检测 format
- 部分 objects 可写入多个 formats
- 支持 stdin/stdout piping，配合 `verify=False`

### 8. Distance Matrices

创建并操作带 statistical methods 的 distance/dissimilarity matrices。

**Key capabilities：**
- 存储 symmetric（DistanceMatrix）或 asymmetric（DissimilarityMatrix）data
- 基于 ID 的 indexing 和 slicing
- 与 diversity、ordination 和 statistical tests 集成
- 读写 delimited text format

**Common patterns：**
```python
from skbio import DistanceMatrix
import numpy as np

# Create from array
data = np.array([[0, 1, 2], [1, 0, 3], [2, 3, 0]])
dm = DistanceMatrix(data, ids=['A', 'B', 'C'])

# Access distances
dist_ab = dm['A', 'B']
row_a = dm['A']

# Read from file
dm = DistanceMatrix.read('distances.txt')

# Use in downstream analyses
pcoa_results = pcoa(dm)
permanova_results = permanova(dm, grouping)
```

**重要说明：**
- DistanceMatrix 强制 symmetry 和 zero diagonal
- DissimilarityMatrix 允许 asymmetric values
- IDs 支持与 metadata 和 biological knowledge 集成
- 与 pandas、numpy 和 scikit-learn 兼容

### 9. Biological Tables

处理 microbiome research 中常见的 feature tables（OTU/ASV tables）。

**Key capabilities：**
- BIOM format I/O（HDF5 和 JSON）
- 与 pandas、polars、AnnData、numpy 集成
- Data augmentation techniques（phylomix、mixup、compositional methods）
- Sample/feature filtering 和 normalization
- Metadata integration

**Common patterns：**
```python
from skbio import Table

# Read BIOM table
table = Table.read('table.biom')

# Access data
sample_ids = table.ids(axis='sample')
feature_ids = table.ids(axis='observation')
counts = table.matrix_data

# Filter
filtered = table.filter(sample_ids_to_keep, axis='sample')

# Convert to/from pandas
df = table.to_dataframe()
table = Table.from_dataframe(df)
```

**重要说明：**
- BIOM tables 是 QIIME 2 workflows 的标准
- Rows 通常表示 samples，columns 表示 features（OTUs/ASVs）
- 支持 sparse 和 dense representations
- Output format 可配置（pandas/polars/numpy）

### 10. Protein Embeddings

处理 downstream analysis 中的 protein language model embeddings。

**Key capabilities：**
- 存储来自 protein language models（ESM、ProtTrans 等）的 embeddings
- 将 embeddings 转换为 distance matrices
- 生成用于 visualization 的 ordination objects
- 导出到 numpy/pandas 以用于 ML workflows

**Common patterns：**
```python
from skbio.embedding import ProteinEmbedding, ProteinVector

# Create embedding from array
embedding = ProteinEmbedding(embedding_array, sequence_ids)

# Convert to distance matrix for analysis
dm = embedding.to_distances(metric='euclidean')

# PCoA visualization of embedding space
pcoa_results = embedding.to_ordination(metric='euclidean', method='pcoa')

# Export for machine learning
array = embedding.to_array()
df = embedding.to_dataframe()
```

**重要说明：**
- Embeddings 将 protein language models 与 traditional bioinformatics 连接起来
- 与 scikit-bio 的 distance/ordination/statistics ecosystem 兼容
- SequenceEmbedding 和 ProteinEmbedding 提供 specialized functionality
- 对 sequence clustering、classification 和 visualization 有用

## Best Practices

### Installation
```bash
uv pip install scikit-bio
```

### Performance Considerations
- 大型 sequence files 使用 generators 以最小化 memory usage
- Massive phylogenetic trees 优先使用 GME 或 BME，而不是 NJ
- Beta diversity calculations 可用 `partial_beta_diversity()` 并行
- 大型 tables 用 BIOM format（HDF5）比 JSON 更高效

### Integration with Ecosystem
- Sequences 可通过 standard formats 与 Biopython 互操作
- Tables 与 pandas、polars 和 AnnData 集成
- Distance matrices 与 scikit-learn 兼容
- Ordination results 可用 matplotlib/seaborn/plotly 可视化
- 与 QIIME 2 artifacts（BIOM、trees、distance matrices）无缝配合

### Common Workflows
1. **Microbiome diversity analysis**：Read BIOM table → Calculate alpha/beta diversity → Ordination（PCoA）→ Statistical testing（PERMANOVA）
2. **Phylogenetic analysis**：Read sequences → Align → Build distance matrix → Construct tree → Calculate phylogenetic distances
3. **Sequence processing**：Read FASTQ → Quality filter → Trim/clean → Find motifs → Translate → Write FASTA
4. **Comparative genomics**：Read sequences → Pairwise alignment → Calculate distances → Build tree → Analyze clades

## Reference Documentation

详细 API information、parameter specifications 和 advanced usage examples 请参考 `references/api_reference.md`，其中包含：
- 所有 capabilities 的完整 method signatures 和 parameters
- Complex workflows 的 extended code examples
- 常见 issues 的 troubleshooting
- Performance optimization tips
- 与其他 libraries 的 integration patterns

## Additional Resources

- Official documentation: https://scikit.bio/docs/latest/
- GitHub repository: https://github.com/scikit-bio/scikit-bio
- Forum support: https://forum.qiime2.org（scikit-bio 是 QIIME 2 ecosystem 的一部分）
