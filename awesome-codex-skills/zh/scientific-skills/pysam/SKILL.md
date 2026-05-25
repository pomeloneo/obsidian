---
name: pysam
description: Genomic file toolkit。读写 SAM/BAM/CRAM alignment、VCF/BCF variant、FASTA/FASTQ sequence，提取区域并计算覆盖度，用于 NGS 数据处理流水线。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Pysam

## 概述

Pysam 是一个用于读取、操作和写入基因组数据集的 Python 模块。它通过面向 Python 的 htslib 接口读写 SAM/BAM/CRAM alignment 文件、VCF/BCF variant 文件以及 FASTA/FASTQ sequence。可查询 tabix-indexed 文件，执行用于覆盖度分析的 pileup analysis，并运行 samtools/bcftools 命令。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 处理 sequencing alignment 文件（BAM/CRAM）
- 分析 genetic variant（VCF/BCF）
- 提取 reference sequence 或 gene region
- 处理原始 sequencing data（FASTQ）
- 计算 coverage 或 read depth
- 实现 bioinformatics analysis pipeline
- 对 sequencing data 做质量控制
- variant calling 和 annotation workflow

## 快速开始

### 安装
```bash
uv pip install pysam
```

### 基础示例

**读取 alignment file：**
```python
import pysam

# Open BAM file and fetch reads in region
samfile = pysam.AlignmentFile("example.bam", "rb")
for read in samfile.fetch("chr1", 1000, 2000):
    print(f"{read.query_name}: {read.reference_start}")
samfile.close()
```

**读取 variant file：**
```python
# Open VCF file and iterate variants
vcf = pysam.VariantFile("variants.vcf")
for variant in vcf:
    print(f"{variant.chrom}:{variant.pos} {variant.ref}>{variant.alts}")
vcf.close()
```

**查询 reference sequence：**
```python
# Open FASTA and extract sequence
fasta = pysam.FastaFile("reference.fasta")
sequence = fasta.fetch("chr1", 1000, 2000)
print(sequence)
fasta.close()
```

## 核心能力

### 1. Alignment File 操作（SAM/BAM/CRAM）

使用 `AlignmentFile` class 处理已比对的 sequencing reads。它适用于分析 mapping 结果、计算 coverage、提取 reads 或质量控制。

**常见操作：**
- 打开并读取 BAM/SAM/CRAM 文件
- 从特定 genomic region 获取 reads
- 按 mapping quality、flags 或其他条件过滤 reads
- 写入过滤后或修改后的 alignment
- 计算 coverage statistics
- 执行 pileup analysis（逐碱基覆盖度）
- 访问 read sequence、quality score 和 alignment information

**参考：** 查看 `references/alignment_files.md`，其中包含以下详细文档：
- 打开并读取 alignment file
- AlignedSegment 属性和方法
- 使用 `fetch()` 按 region 获取数据
- 用于 coverage 的 pileup analysis
- 写入并创建 BAM 文件
- 坐标系统和 indexing
- 性能优化建议

### 2. Variant File 操作（VCF/BCF）

使用 `VariantFile` class 处理 variant calling pipeline 生成的 genetic variant。它适用于 variant analysis、filtering、annotation 或 population genetics。

**常见操作：**
- 读取和写入 VCF/BCF 文件
- 查询特定区域内的 variant
- 访问 variant 信息（位置、allele、quality）
- 为样本提取 genotype data
- 按 quality、allele frequency 或其他条件过滤 variant
- 使用额外信息注释 variant
- 对样本或区域取子集

**参考：** 查看 `references/variant_files.md`，其中包含以下详细文档：
- 打开并读取 variant file
- VariantRecord 属性和方法
- 访问 INFO 和 FORMAT 字段
- 处理 genotype 和 sample
- 创建并写入 VCF 文件
- 过滤和取子集 variant
- Multi-sample VCF 操作

### 3. Sequence File 操作（FASTA/FASTQ）

使用 `FastaFile` 随机访问 reference sequence，使用 `FastxFile` 读取原始 sequencing data。它适用于提取 gene sequence、根据 reference 验证 variant，或处理原始 reads。

**常见操作：**
- 按 genomic coordinate 查询 reference sequence
- 为感兴趣的 gene 或 region 提取 sequence
- 读取带 quality score 的 FASTQ 文件
- 验证 variant 的 reference allele
- 计算 sequence statistics
- 按 quality 或 length 过滤 reads
- 在 FASTA 和 FASTQ 格式之间转换

**参考：** 查看 `references/sequence_files.md`，其中包含以下详细文档：
- FASTA 文件访问和 indexing
- 按 region 提取 sequence
- 处理 gene 的 reverse complement
- 顺序读取 FASTQ 文件
- Quality score 转换和过滤
- 处理 tabix-indexed 文件（BED、GTF、GFF）
- 常见 sequence processing 模式

### 4. 集成式 Bioinformatics Workflow

Pysam 擅长整合多种文件类型，用于全面的 genomic analysis。常见 workflow 会组合 alignment file、variant file 和 reference sequence。

**常见 workflow：**
- 计算特定 region 的 coverage statistics
- 根据 aligned reads 验证 variant
- 使用 coverage information 注释 variant
- 提取 variant position 周边的 sequence
- 基于多个条件过滤 alignment 或 variant
- 生成用于 visualization 的 coverage track
- 跨多种数据类型进行质量控制

**参考：** 查看 `references/common_workflows.md`，其中包含以下详细示例：
- 质量控制 workflow（BAM 统计、reference 一致性）
- Coverage analysis（per-base coverage、low coverage 检测）
- Variant analysis（annotation、按 read support 过滤）
- Sequence extraction（variant context、gene sequence）
- Read filtering 和 subsetting
- Integration pattern（BAM+VCF、VCF+BED 等）
- 复杂 workflow 的性能优化

## 关键概念

### 坐标系统

**关键：** Pysam 使用 **0-based, half-open** 坐标（Python 约定）：
- 起始位置是 0-based（第一个碱基的位置为 0）
- 结束位置是 exclusive（不包含在范围内）
- Region 1000-2000 包含 bases 1000-1999（共 1000 个 bases）

**例外：** `fetch()` 中的 region string 遵循 samtools 约定（1-based）：
```python
samfile.fetch("chr1", 999, 2000)      # 0-based: positions 999-1999
samfile.fetch("chr1:1000-2000")       # 1-based string: positions 1000-2000
```

**VCF 文件：** 文件格式中使用 1-based coordinates，但 `VariantRecord.start` 是 0-based。

### Indexing 要求

随机访问特定 genomic region 需要 index 文件：
- **BAM 文件**：需要 `.bai` index（用 `pysam.index()` 创建）
- **CRAM 文件**：需要 `.crai` index
- **FASTA 文件**：需要 `.fai` index（用 `pysam.faidx()` 创建）
- **VCF.gz 文件**：需要 `.tbi` tabix index（用 `pysam.tabix_index()` 创建）
- **BCF 文件**：需要 `.csi` index

没有 index 时，使用 `fetch(until_eof=True)` 进行顺序读取。

### 文件模式

打开文件时指定格式：
- `"rb"` - 读取 BAM（二进制）
- `"r"` - 读取 SAM（文本）
- `"rc"` - 读取 CRAM
- `"wb"` - 写入 BAM
- `"w"` - 写入 SAM
- `"wc"` - 写入 CRAM

### 性能注意事项

1. 对随机访问操作，**始终使用带 index 的文件**
2. **使用 `pileup()` 进行按列分析**，避免反复 fetch
3. **使用 `count()` 计数**，避免手动迭代后计数
4. 分析独立 genomic region 时，**并行处理 region**
5. **显式关闭文件**以释放资源
6. 对无 index 的顺序处理，**使用 `until_eof=True`**
7. 除非必要，**避免多个 iterator**（需要时使用 `multiple_iterators=True`）

## 常见陷阱

1. **坐标混淆：** 记住不同上下文中的 0-based 与 1-based 系统
2. **缺少 index：** 许多操作需要 index 文件，应先创建
3. **部分重叠：** `fetch()` 会返回与 region 边界重叠的 reads，不只返回完全包含在 region 内的 reads
4. **Iterator 作用域：** 保持 pileup iterator 引用存活，避免出现 "PileupProxy accessed after iterator finished" 错误
5. **Quality score 编辑：** 修改 `query_sequence` 后不能原地修改 `query_qualities`，应先创建副本
6. **Stream 限制：** streaming 只支持 stdin/stdout，不支持任意 Python file object
7. **线程安全：** I/O 期间会释放 GIL，但全面的 thread-safety 尚未完全验证

## 命令行工具

Pysam 提供对 samtools 和 bcftools 命令的访问：

```python
# Sort BAM file
pysam.samtools.sort("-o", "sorted.bam", "input.bam")

# Index BAM
pysam.samtools.index("sorted.bam")

# View specific region
pysam.samtools.view("-b", "-o", "region.bam", "input.bam", "chr1:1000-2000")

# BCF tools
pysam.bcftools.view("-O", "z", "-o", "output.vcf.gz", "input.vcf")
```

**错误处理：**
```python
try:
    pysam.samtools.sort("-o", "output.bam", "input.bam")
except pysam.SamtoolsError as e:
    print(f"Error: {e}")
```

## 资源

### references/

每个主要能力的详细文档：

- **alignment_files.md** - SAM/BAM/CRAM 操作完整指南，包括 AlignmentFile class、AlignedSegment 属性、fetch 操作、pileup analysis 和写入 alignment

- **variant_files.md** - VCF/BCF 操作完整指南，包括 VariantFile class、VariantRecord 属性、genotype handling、INFO/FORMAT 字段和 multi-sample 操作

- **sequence_files.md** - FASTA/FASTQ 操作完整指南，包括 FastaFile 和 FastxFile class、sequence extraction、quality score handling 和 tabix-indexed 文件访问

- **common_workflows.md** - 组合多种文件类型的集成式 bioinformatics workflow 实践示例，包括质量控制、coverage analysis、variant validation 和 sequence extraction

## 获取帮助

有关特定操作的详细信息，请参考相应 reference document：

- 处理 BAM 文件或计算 coverage → `alignment_files.md`
- 分析 variant 或 genotype → `variant_files.md`
- 提取 sequence 或处理 FASTQ → `sequence_files.md`
- 集成多种文件类型的复杂 workflow → `common_workflows.md`

官方文档：https://pysam.readthedocs.io/
