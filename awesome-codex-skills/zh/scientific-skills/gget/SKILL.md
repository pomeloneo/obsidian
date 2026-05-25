---
name: gget
description: "面向 20+ bioinformatics databases 的快速 CLI/Python queries。用于 quick lookups：gene info、BLAST searches、AlphaFold structures、enrichment analysis。最适合 interactive exploration 和 simple queries。Batch processing 或 advanced BLAST 使用 biopython；multi-database Python workflows 使用 bioservices。"
license: BSD-2-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# gget

## 概述

gget 是一个 command-line bioinformatics tool 和 Python package，提供对 20+ genomic databases 和 analysis methods 的统一访问。通过一致接口查询 gene information、sequence analysis、protein structures、expression data 和 disease associations。所有 gget modules 既可作为 command-line tools，也可作为 Python functions 使用。

**重要**：gget 查询的 databases 会持续更新，有时会改变其结构。gget modules 每两周自动测试一次，并在必要时更新以匹配新的 database structures。

## 安装

在干净 virtual environment 中安装 gget，以避免冲突：

```bash
# Using uv (recommended)
uv uv pip install gget

# Or using pip
uv pip install --upgrade gget

# In Python/Jupyter
import gget
```

## Quick Start

所有 modules 的基本使用模式：

```bash
# Command-line
gget <module> [arguments] [options]

# Python
gget.module(arguments, options)
```

大多数 modules 返回：
- **Command-line**：JSON（默认）或带 `-csv` flag 的 CSV
- **Python**：DataFrame 或 dictionary

跨 modules 的常见 flags：
- `-o/--out`：保存结果到文件
- `-q/--quiet`：抑制 progress information
- `-csv`：返回 CSV format（仅 command-line）

## Module Categories

### 1. Reference & Gene Information

#### gget ref - Reference Genome Downloads

检索 Ensembl reference genomes 的 download links 和 metadata。

**Parameters**：
- `species`：Genus_species format（例如 'homo_sapiens'、'mus_musculus'）。Shortcuts：'human'、'mouse'
- `-w/--which`：指定 return types（gtf、cdna、dna、cds、cdrna、pep）。默认：all
- `-r/--release`：Ensembl release number（默认：latest）
- `-l/--list_species`：列出可用 vertebrate species
- `-liv/--list_iv_species`：列出可用 invertebrate species
- `-ftp`：仅返回 FTP links
- `-d/--download`：下载文件（需要 curl）

**Examples**：
```bash
# List available species
gget ref --list_species

# Get all reference files for human
gget ref homo_sapiens

# Download only GTF annotation for mouse
gget ref -w gtf -d mouse
```

```python
# Python
gget.ref("homo_sapiens")
gget.ref("mus_musculus", which="gtf", download=True)
```

#### gget search - Gene Search

按名称或描述在不同 species 中定位 genes。

**Parameters**：
- `searchwords`：一个或多个 search terms（case-insensitive）
- `-s/--species`：Target species（例如 'homo_sapiens'、'mouse'）
- `-r/--release`：Ensembl release number
- `-t/--id_type`：返回 'gene'（默认）或 'transcript'
- `-ao/--andor`：'or'（默认）查找任意 searchword；'and' 要求全部匹配
- `-l/--limit`：返回最大结果数

**Returns**：ensembl_id、gene_name、ensembl_description、ext_ref_description、biotype、URL

**Examples**：
```bash
# Search for GABA-related genes in human
gget search -s human gaba gamma-aminobutyric

# Find specific gene, require all terms
gget search -s mouse -ao and pax7 transcription
```

```python
# Python
gget.search(["gaba", "gamma-aminobutyric"], species="homo_sapiens")
```

#### gget info - Gene/Transcript Information

从 Ensembl、UniProt 和 NCBI 检索综合 gene 和 transcript metadata。

**Parameters**：
- `ens_ids`：一个或多个 Ensembl IDs（也支持 WormBase、Flybase IDs）。Limit：约 1000 IDs
- `-n/--ncbi`：禁用 NCBI data retrieval
- `-u/--uniprot`：禁用 UniProt data retrieval
- `-pdb`：包含 PDB identifiers（会增加 runtime）

**Returns**：UniProt ID、NCBI gene ID、primary gene name、synonyms、protein names、descriptions、biotype、canonical transcript

**Examples**：
```bash
# Get info for multiple genes
gget info ENSG00000034713 ENSG00000104853 ENSG00000170296

# Include PDB IDs
gget info ENSG00000034713 -pdb
```

```python
# Python
gget.info(["ENSG00000034713", "ENSG00000104853"], pdb=True)
```

#### gget seq - Sequence Retrieval

获取 genes 和 transcripts 的 nucleotide 或 amino acid sequences。

**Parameters**：
- `ens_ids`：一个或多个 Ensembl identifiers
- `-t/--translate`：获取 amino acid sequences 而不是 nucleotide
- `-iso/--isoforms`：返回所有 transcript variants（仅 gene IDs）

**Returns**：FASTA format sequences

**Examples**：
```bash
# Get nucleotide sequences
gget seq ENSG00000034713 ENSG00000104853

# Get all protein isoforms
gget seq -t -iso ENSG00000034713
```

```python
# Python
gget.seq(["ENSG00000034713"], translate=True, isoforms=True)
```

### 2. Sequence Analysis & Alignment

#### gget blast - BLAST Searches

针对标准 databases 对 nucleotide 或 amino acid sequences 执行 BLAST。

**Parameters**：
- `sequence`：Sequence string 或 FASTA/.txt file path
- `-p/--program`：blastn、blastp、blastx、tblastn、tblastx（auto-detected）
- `-db/--database`：
  - Nucleotide：nt、refseq_rna、pdbnt
  - Protein：nr、swissprot、pdbaa、refseq_protein
- `-l/--limit`：Max hits（默认：50）
- `-e/--expect`：E-value cutoff（默认：10.0）
- `-lcf/--low_comp_filt`：启用 low complexity filtering
- `-mbo/--megablast_off`：禁用 MegaBLAST（仅 blastn）

**Examples**：
```bash
# BLAST protein sequence
gget blast MKWMFKEDHSLEHRCVESAKIRAKYPDRVPVIVEKVSGSQIVDIDKRKYLVPSDITVAQFMWIIRKRIQLPSEKAIFLFVDKTVPQSR

# BLAST from file with specific database
gget blast sequence.fasta -db swissprot -l 10
```

```python
# Python
gget.blast("MKWMFK...", database="swissprot", limit=10)
```

#### gget blat - BLAT Searches

使用 UCSC BLAT 定位 sequences 的 genomic positions。

**Parameters**：
- `sequence`：Sequence string 或 FASTA/.txt file path
- `-st/--seqtype`：'DNA'、'protein'、'translated%20RNA'、'translated%20DNA'（auto-detected）
- `-a/--assembly`：Target assembly（默认：'human'/hg38；options：'mouse'/mm39、'zebrafinch'/taeGut2 等）

**Returns**：genome、query size、alignment positions、matches、mismatches、alignment percentage

**Examples**：
```bash
# Find genomic location in human
gget blat ATCGATCGATCGATCG

# Search in different assembly
gget blat -a mm39 ATCGATCGATCGATCG
```

```python
# Python
gget.blat("ATCGATCGATCGATCG", assembly="mouse")
```

#### gget muscle - Multiple Sequence Alignment

使用 Muscle5 对多个 nucleotide 或 amino acid sequences 进行 alignment。

**Parameters**：
- `fasta`：Sequences 或 FASTA/.txt file path
- `-s5/--super5`：使用 Super5 algorithm 加快 processing（large datasets）

**Returns**：ClustalW format 的 aligned sequences 或 aligned FASTA（.afa）

**Examples**：
```bash
# Align sequences from file
gget muscle sequences.fasta -o aligned.afa

# Use Super5 for large dataset
gget muscle large_dataset.fasta -s5
```

```python
# Python
gget.muscle("sequences.fasta", save=True)
```

#### gget diamond - Local Sequence Alignment

使用 DIAMOND 执行快速 local protein 或 translated DNA alignment。

**Parameters**：
- Query：Sequences（string/list）或 FASTA file path
- `--reference`：Reference sequences（string/list）或 FASTA file path（必需）
- `--sensitivity`：fast、mid-sensitive、sensitive、more-sensitive、very-sensitive（默认）、ultra-sensitive
- `--threads`：CPU threads（默认：1）
- `--diamond_db`：保存 database 以复用
- `--translated`：启用 nucleotide-to-amino acid alignment

**Returns**：Identity percentage、sequence lengths、match positions、gap openings、E-values、bit scores

**Examples**：
```bash
# Align against reference
gget diamond GGETISAWESQME -ref reference.fasta --threads 4

# Save database for reuse
gget diamond query.fasta -ref ref.fasta --diamond_db my_db.dmnd
```

```python
# Python
gget.diamond("GGETISAWESQME", reference="reference.fasta", threads=4)
```

### 3. Structural & Protein Analysis

#### gget pdb - Protein Structures

查询 RCSB Protein Data Bank 的 structure 和 metadata。

**Parameters**：
- `pdb_id`：PDB identifier（例如 '7S7U'）
- `-r/--resource`：Data type（pdb、entry、pubmed、assembly、entity types）
- `-i/--identifier`：Assembly、entity 或 chain ID

**Returns**：PDB format（structures）或 JSON（metadata）

**Examples**：
```bash
# Download PDB structure
gget pdb 7S7U -o 7S7U.pdb

# Get metadata
gget pdb 7S7U -r entry
```

```python
# Python
gget.pdb("7S7U", save=True)
```

#### gget alphafold - Protein Structure Prediction

使用简化 AlphaFold2 预测 3D protein structures。

**Setup Required**：
```bash
# Install OpenMM first
uv pip install openmm

# Then setup AlphaFold
gget setup alphafold
```

**Parameters**：
- `sequence`：Amino acid sequence（string）、multiple sequences（list）或 FASTA file。Multiple sequences 会触发 multimer modeling
- `-mr/--multimer_recycles`：Recycling iterations（默认：3；推荐 20 以提高 accuracy）
- `-mfm/--multimer_for_monomer`：将 multimer model 应用于 single proteins
- `-r/--relax`：对 top-ranked model 执行 AMBER relaxation
- `plot`：仅 Python；生成 interactive 3D visualization（默认：True）
- `show_sidechains`：仅 Python；包含 side chains（默认：True）

**Returns**：PDB structure file、JSON alignment error data、可选 3D visualization

**Examples**：
```bash
# Predict single protein structure
gget alphafold MKWMFKEDHSLEHRCVESAKIRAKYPDRVPVIVEKVSGSQIVDIDKRKYLVPSDITVAQFMWIIRKRIQLPSEKAIFLFVDKTVPQSR

# Predict multimer with higher accuracy
gget alphafold sequence1.fasta -mr 20 -r
```

```python
# Python with visualization
gget.alphafold("MKWMFK...", plot=True, show_sidechains=True)

# Multimer prediction
gget.alphafold(["sequence1", "sequence2"], multimer_recycles=20)
```

#### gget elm - Eukaryotic Linear Motifs

预测 protein sequences 中的 Eukaryotic Linear Motifs。

**Setup Required**：
```bash
gget setup elm
```

**Parameters**：
- `sequence`：Amino acid sequence 或 UniProt Acc
- `-u/--uniprot`：表示 sequence 是 UniProt Acc
- `-e/--expand`：包含 protein names、organisms、references
- `-s/--sensitivity`：DIAMOND alignment sensitivity（默认："very-sensitive"）
- `-t/--threads`：Number of threads（默认：1）

**Returns**：两个 outputs：
1. **ortholog_df**：来自 orthologous proteins 的 linear motifs
2. **regex_df**：input sequence 中直接匹配的 motifs

**Examples**：
```bash
# Predict motifs from sequence
gget elm LIAQSIGQASFV -o results

# Use UniProt accession with expanded info
gget elm --uniprot Q02410 -e
```

```python
# Python
ortholog_df, regex_df = gget.elm("LIAQSIGQASFV")
```

### 4. Expression & Disease Data

#### gget archs4 - Gene Correlation & Tissue Expression

查询 ARCHS4 database，获取 correlated genes 或 tissue expression data。

**Parameters**：
- `gene`：Gene symbol 或 Ensembl ID（带 `--ensembl` flag）
- `-w/--which`：'correlation'（默认，返回 100 个最相关 genes）或 'tissue'（expression atlas）
- `-s/--species`：'human'（默认）或 'mouse'（仅 tissue data）
- `-e/--ensembl`：Input 是 Ensembl ID

**Returns**：
- **Correlation mode**：Gene symbols、Pearson correlation coefficients
- **Tissue mode**：Tissue identifiers、min/Q1/median/Q3/max expression values

**Examples**：
```bash
# Get correlated genes
gget archs4 ACE2

# Get tissue expression
gget archs4 -w tissue ACE2
```

```python
# Python
gget.archs4("ACE2", which="tissue")
```

#### gget cellxgene - Single-Cell RNA-seq Data

查询 CZ CELLxGENE Discover Census 获取 single-cell data。

**Setup Required**：
```bash
gget setup cellxgene
```

**Parameters**：
- `--gene` (-g)：Gene names 或 Ensembl IDs（case-sensitive！human 用 'PAX7'，mouse 用 'Pax7'）
- `--tissue`：Tissue type(s)
- `--cell_type`：Specific cell type(s)
- `--species` (-s)：'homo_sapiens'（默认）或 'mus_musculus'
- `--census_version` (-cv)：Version（"stable"、"latest" 或 dated）
- `--ensembl` (-e)：使用 Ensembl IDs
- `--meta_only` (-mo)：仅返回 metadata
- Additional filters：disease、development_stage、sex、assay、dataset_id、donor_id、ethnicity、suspension_type

**Returns**：带 count matrices 和 metadata 的 AnnData object（或 metadata-only dataframes）

**Examples**：
```bash
# Get single-cell data for specific genes and cell types
gget cellxgene --gene ACE2 ABCA1 --tissue lung --cell_type "mucus secreting cell" -o lung_data.h5ad

# Metadata only
gget cellxgene --gene PAX7 --tissue muscle --meta_only -o metadata.csv
```

```python
# Python
adata = gget.cellxgene(gene=["ACE2", "ABCA1"], tissue="lung", cell_type="mucus secreting cell")
```

#### gget enrichr - Enrichment Analysis

使用 Enrichr 对 gene lists 执行 ontology enrichment analysis。

**Parameters**：
- `genes`：Gene symbols 或 Ensembl IDs
- `-db/--database`：Reference database（支持 shortcuts：'pathway'、'transcription'、'ontology'、'diseases_drugs'、'celltypes'）
- `-s/--species`：human（默认）、mouse、fly、yeast、worm、fish
- `-bkg_l/--background_list`：用于 comparison 的 background genes
- `-ko/--kegg_out`：保存带 highlighted genes 的 KEGG pathway images
- `plot`：仅 Python；生成 graphical results

**Database Shortcuts**：
- 'pathway' → KEGG_2021_Human
- 'transcription' → ChEA_2016
- 'ontology' → GO_Biological_Process_2021
- 'diseases_drugs' → GWAS_Catalog_2019
- 'celltypes' → PanglaoDB_Augmented_2021

**Examples**：
```bash
# Enrichment analysis for ontology
gget enrichr -db ontology ACE2 AGT AGTR1

# Save KEGG pathways
gget enrichr -db pathway ACE2 AGT AGTR1 -ko ./kegg_images/
```

```python
# Python with plot
gget.enrichr(["ACE2", "AGT", "AGTR1"], database="ontology", plot=True)
```

#### gget bgee - Orthology & Expression

从 Bgee database 检索 orthology 和 gene expression data。

**Parameters**：
- `ens_id`：Ensembl gene ID 或 NCBI gene ID（用于 non-Ensembl species）。当 `type=expression` 时支持多个 IDs
- `-t/--type`：'orthologs'（默认）或 'expression'

**Returns**：
- **Orthologs mode**：跨 species 的 matching genes，带 IDs、names、taxonomic info
- **Expression mode**：Anatomical entities、confidence scores、expression status

**Examples**：
```bash
# Get orthologs
gget bgee ENSG00000169194

# Get expression data
gget bgee ENSG00000169194 -t expression

# Multiple genes
gget bgee ENSBTAG00000047356 ENSBTAG00000018317 -t expression
```

```python
# Python
gget.bgee("ENSG00000169194", type="orthologs")
```

#### gget opentargets - Disease & Drug Associations

从 OpenTargets 检索 disease 和 drug associations。

**Parameters**：
- Ensembl gene ID（必需）
- `-r/--resource`：diseases（默认）、drugs、tractability、pharmacogenetics、expression、depmap、interactions
- `-l/--limit`：限制 results count
- Filter arguments（随 resource 变化）：
  - drugs：`--filter_disease`
  - pharmacogenetics：`--filter_drug`
  - expression/depmap：`--filter_tissue`、`--filter_anat_sys`、`--filter_organ`
  - interactions：`--filter_protein_a`、`--filter_protein_b`、`--filter_gene_b`

**Examples**：
```bash
# Get associated diseases
gget opentargets ENSG00000169194 -r diseases -l 5

# Get associated drugs
gget opentargets ENSG00000169194 -r drugs -l 10

# Get tissue expression
gget opentargets ENSG00000169194 -r expression --filter_tissue brain
```

```python
# Python
gget.opentargets("ENSG00000169194", resource="diseases", limit=5)
```

#### gget cbio - cBioPortal Cancer Genomics

使用 cBioPortal data 绘制 cancer genomics heatmaps。

**两个 subcommands**：

**search** - 查找 study IDs：
```bash
gget cbio search breast lung
```

**plot** - 生成 heatmaps：

**Parameters**：
- `-s/--study_ids`：空格分隔的 cBioPortal study IDs（必需）
- `-g/--genes`：空格分隔的 gene names 或 Ensembl IDs（必需）
- `-st/--stratification`：用于组织 data 的 column（tissue、cancer_type、cancer_type_detailed、study_id、sample）
- `-vt/--variation_type`：Data type（mutation_occurrences、cna_nonbinary、sv_occurrences、cna_occurrences、Consequence）
- `-f/--filter`：按 column value 过滤（例如 'study_id:msk_impact_2017'）
- `-dd/--data_dir`：Cache directory（默认：./gget_cbio_cache）
- `-fd/--figure_dir`：Output directory（默认：./gget_cbio_figures）
- `-dpi`：Resolution（默认：100）
- `-sh/--show`：在窗口中显示 plot
- `-nc/--no_confirm`：跳过 download confirmations

**Examples**：
```bash
# Search for studies
gget cbio search esophag ovary

# Create heatmap
gget cbio plot -s msk_impact_2017 -g AKT1 ALK BRAF -st tissue -vt mutation_occurrences
```

```python
# Python
gget.cbio_search(["esophag", "ovary"])
gget.cbio_plot(["msk_impact_2017"], ["AKT1", "ALK"], stratification="tissue")
```

#### gget cosmic - COSMIC Database

搜索 COSMIC（Catalogue Of Somatic Mutations In Cancer）database。

**重要**：商业使用需要支付 license fees。需要 COSMIC account credentials。

**Parameters**：
- `searchterm`：Gene name、Ensembl ID、mutation notation 或 sample ID
- `-ctp/--cosmic_tsv_path`：已下载 COSMIC TSV file 的路径（查询必需）
- `-l/--limit`：Maximum results（默认：100）

**Database download flags**：
- `-d/--download_cosmic`：激活 download mode
- `-gm/--gget_mutate`：创建用于 gget mutate 的版本
- `-cp/--cosmic_project`：Database type（cancer、census、cell_line、resistance、genome_screen、targeted_screen）
- `-cv/--cosmic_version`：COSMIC version
- `-gv/--grch_version`：Human reference genome（37 或 38）
- `--email`、`--password`：COSMIC credentials

**Examples**：
```bash
# First download database
gget cosmic -d --email user@example.com --password xxx -cp cancer

# Then query
gget cosmic EGFR -ctp cosmic_data.tsv -l 10
```

```python
# Python
gget.cosmic("EGFR", cosmic_tsv_path="cosmic_data.tsv", limit=10)
```

### 5. Additional Tools

#### gget mutate - Generate Mutated Sequences

根据 mutation annotations 生成 mutated nucleotide sequences。

**Parameters**：
- `sequences`：FASTA file path 或直接 sequence input（string/list）
- `-m/--mutations`：带 mutation data 的 CSV/TSV file 或 DataFrame（必需）
- `-mc/--mut_column`：Mutation column name（默认：'mutation'）
- `-sic/--seq_id_column`：Sequence ID column（默认：'seq_ID'）
- `-mic/--mut_id_column`：Mutation ID column
- `-k/--k`：Flanking sequences 长度（默认：30 nucleotides）

**Returns**：FASTA format 的 mutated sequences

**Examples**：
```bash
# Single mutation
gget mutate ATCGCTAAGCT -m "c.4G>T"

# Multiple sequences with mutations from file
gget mutate sequences.fasta -m mutations.csv -o mutated.fasta
```

```python
# Python
import pandas as pd
mutations_df = pd.DataFrame({"seq_ID": ["seq1"], "mutation": ["c.4G>T"]})
gget.mutate(["ATCGCTAAGCT"], mutations=mutations_df)
```

#### gget gpt - OpenAI Text Generation

使用 OpenAI's API 生成 natural language text。

**Setup Required**：
```bash
gget setup gpt
```

**重要**：Free tier 仅限 account creation 后 3 个月。请设置 monthly billing limits。

**Parameters**：
- `prompt`：用于 generation 的 text input（必需）
- `api_key`：OpenAI authentication（必需）
- Model configuration：temperature、top_p、max_tokens、frequency_penalty、presence_penalty
- Default model：gpt-3.5-turbo（可配置）

**Examples**：
```bash
gget gpt "Explain CRISPR" --api_key your_key_here
```

```python
# Python
gget.gpt("Explain CRISPR", api_key="your_key_here")
```

#### gget setup - Install Dependencies

为特定 modules 安装/下载 third-party dependencies。

**Parameters**：
- `module`：需要 dependency installation 的 module name
- `-o/--out`：Output folder path（仅 elm module）

**需要 setup 的 modules**：
- `alphafold` - 下载约 4GB model parameters
- `cellxgene` - 安装 cellxgene-census（可能不支持最新 Python）
- `elm` - 下载本地 ELM database
- `gpt` - 配置 OpenAI integration

**Examples**：
```bash
# Setup AlphaFold
gget setup alphafold

# Setup ELM with custom directory
gget setup elm -o /path/to/elm_data
```

```python
# Python
gget.setup("alphafold")
```

## 常见工作流

### Workflow 1：Gene Discovery to Sequence Analysis

查找并分析目标 genes：

```python
# 1. Search for genes
results = gget.search(["GABA", "receptor"], species="homo_sapiens")

# 2. Get detailed information
gene_ids = results["ensembl_id"].tolist()
info = gget.info(gene_ids[:5])

# 3. Retrieve sequences
sequences = gget.seq(gene_ids[:5], translate=True)
```

### Workflow 2：Sequence Alignment and Structure

对 sequences 进行 alignment 并预测 structures：

```python
# 1. Align multiple sequences
alignment = gget.muscle("sequences.fasta")

# 2. Find similar sequences
blast_results = gget.blast(my_sequence, database="swissprot", limit=10)

# 3. Predict structure
structure = gget.alphafold(my_sequence, plot=True)

# 4. Find linear motifs
ortholog_df, regex_df = gget.elm(my_sequence)
```

### Workflow 3：Gene Expression and Enrichment

分析 expression patterns 和 functional enrichment：

```python
# 1. Get tissue expression
tissue_expr = gget.archs4("ACE2", which="tissue")

# 2. Find correlated genes
correlated = gget.archs4("ACE2", which="correlation")

# 3. Get single-cell data
adata = gget.cellxgene(gene=["ACE2"], tissue="lung", cell_type="epithelial cell")

# 4. Perform enrichment analysis
gene_list = correlated["gene_symbol"].tolist()[:50]
enrichment = gget.enrichr(gene_list, database="ontology", plot=True)
```

### Workflow 4：Disease and Drug Analysis

研究 disease associations 和 therapeutic targets：

```python
# 1. Search for genes
genes = gget.search(["breast cancer"], species="homo_sapiens")

# 2. Get disease associations
diseases = gget.opentargets("ENSG00000169194", resource="diseases")

# 3. Get drug associations
drugs = gget.opentargets("ENSG00000169194", resource="drugs")

# 4. Query cancer genomics data
study_ids = gget.cbio_search(["breast"])
gget.cbio_plot(study_ids[:2], ["BRCA1", "BRCA2"], stratification="cancer_type")

# 5. Search COSMIC for mutations
cosmic_results = gget.cosmic("BRCA1", cosmic_tsv_path="cosmic.tsv")
```

### Workflow 5：Comparative Genomics

比较不同 species 的 proteins：

```python
# 1. Get orthologs
orthologs = gget.bgee("ENSG00000169194", type="orthologs")

# 2. Get sequences for comparison
human_seq = gget.seq("ENSG00000169194", translate=True)
mouse_seq = gget.seq("ENSMUSG00000026091", translate=True)

# 3. Align sequences
alignment = gget.muscle([human_seq, mouse_seq])

# 4. Compare structures
human_structure = gget.pdb("7S7U")
mouse_structure = gget.alphafold(mouse_seq)
```

### Workflow 6：Building Reference Indices

为 downstream analysis（例如 kallisto|bustools）准备 reference data：

```bash
# 1. List available species
gget ref --list_species

# 2. Download reference files
gget ref -w gtf -w cdna -d homo_sapiens

# 3. Build kallisto index
kallisto index -i transcriptome.idx transcriptome.fasta

# 4. Download genome for alignment
gget ref -w dna -d homo_sapiens
```

## 最佳实践

### Data Retrieval
- 对 large queries 使用 `--limit` 控制 result sizes
- 使用 `-o/--out` 保存结果，保证 reproducibility
- 检查 database versions/releases，保持 analyses 一致
- 在 production scripts 中使用 `--quiet` 减少 output

### Sequence Analysis
- 对 BLAST/BLAT，从默认参数开始，再调整 sensitivity
- 使用带 `--threads` 的 `gget diamond` 获得更快 local alignment
- 用 `--diamond_db` 保存 DIAMOND databases 以便重复 queries
- 对 multiple sequence alignment，大 datasets 使用 `-s5/--super5`

### Expression and Disease Data
- cellxgene 中 gene symbols 区分大小写（例如 'PAX7' vs 'Pax7'）
- 首次使用 alphafold、cellxgene、elm、gpt 前运行 `gget setup`
- Enrichment analysis 使用 database shortcuts 更方便
- 用 `-dd` 缓存 cBioPortal data，避免重复 downloads

### Structure Prediction
- AlphaFold multimer predictions：使用 `-mr 20` 获得更高 accuracy
- 对 final structures 使用 `-r` flag 进行 AMBER relaxation
- 在 Python 中用 `plot=True` 可视化结果
- 运行 AlphaFold predictions 前先检查 PDB database

### Error Handling
- Database structures 会变化；定期更新 gget：`uv pip install --upgrade gget`
- gget info 一次最多处理约 1000 个 Ensembl IDs
- 对 large-scale analyses，为 API queries 实现 rate limiting
- 使用 virtual environments 避免 dependency conflicts

## Output Formats

### Command-line
- 默认：JSON
- CSV：添加 `-csv` flag
- FASTA：gget seq、gget mutate
- PDB：gget pdb、gget alphafold
- PNG：gget cbio plot

### Python
- 默认：DataFrame 或 dictionary
- JSON：添加 `json=True` parameter
- 保存到文件：添加 `save=True` 或指定 `out="filename"`
- AnnData：gget cellxgene

## 资源

此 skill 包含详细 module information 的 reference documentation：

### references/
- `module_reference.md` - 所有 modules 的综合 parameter reference
- `database_info.md` - 被查询 databases 及其 update frequencies 的信息
- `workflows.md` - 扩展 workflow examples 和 use cases

更多帮助：
- Official documentation: https://pachterlab.github.io/gget/
- GitHub issues: https://github.com/pachterlab/gget/issues
- Citation: Luebbert, L. & Pachter, L. (2023). Efficient querying of genomic reference databases with gget. Bioinformatics. https://doi.org/10.1093/bioinformatics/btac836
