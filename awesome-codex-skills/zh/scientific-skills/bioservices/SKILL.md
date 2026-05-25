---
name: bioservices
description: 与 40 多个生物信息学服务的统一 Python 接口。在单个工作流中查询多个数据库（UniProt、KEGG、ChEMBL、Reactome）且API一致时使用。最适合跨数据库分析，ID 跨服务映射。对于快速单数据库查找，请使用 gget；对于sequence/file操作使用biopython。
license: GPLv3 license
metadata:
    skill-author: K-Dense Inc.
---

# BioServices

## 概述

BioServices 是一个 Python 软件包，提供对大约 40 个生物信息学 Web 服务和数据库的编程访问。在Python工作流程中检索生物数据、执行跨数据库查询、映射标识符、分析序列以及集成多种生物资源。该软件包透明地处理 REST 和 SOAP/WSDL 协议。

## 何时使用此技能

该技能应该在以下情况下使用：
- 从UniProt、PDB、Pfam 检索蛋白质序列、注释或结构
- 通过KEGG或Reactome分析代谢途径和基因功能
- 搜索化合物数据库（ChEBI、ChEMBL、PubChem）以获取化学信息
- 在不同生物数据库之间转换标识符（KEGG↔UniProt，化合物IDs）
- 运行序列相似性搜索（BLAST、MUSCLE 比对）
- 查询基因本体术语（QuickGO、GO注释）
- 访问蛋白质-蛋白质相互作用数据（PSICQUIC、IntactComplex）
- 挖掘基因组数据（BioMart，ArrayExpress，ENA）
- 在单个工作流程中集成来自多个生物信息学资源的数据

## 核心能力

### 1. 蛋白质分析

检索蛋白质信息、序列和功能注释：

```python
from bioservices import UniProt

u = UniProt(verbose=False)

# Search for protein by name
results = u.search("ZAP70_HUMAN", frmt="tab", columns="id,genes,organism")

# Retrieve FASTA sequence
sequence = u.retrieve("P43403", "fasta")

# Map identifiers between databases
kegg_ids = u.mapping(fr="UniProtKB_AC-ID", to="KEGG", query="P43403")
```

**关键方法**：
- `search()`：使用灵活的搜索词查询UniProt
- `retrieve()`：获取各种格式的蛋白质条目（FASTA、XML、制表符）
- `mapping()`：在数据库之间转换标识符

参考：`references/services_reference.md` 了解完整的UniProt API 详细信息。

### 2. 通路发现与分析

获取基因和生物体的KEGG途径信息：

```python
from bioservices import KEGG

k = KEGG()
k.organism = "hsa"  # Set to human

# Search for organisms
k.lookfor_organism("droso")  # Find Drosophila species

# Find pathways by name
k.lookfor_pathway("B cell")  # Returns matching pathway IDs

# Get pathways containing specific genes
pathways = k.get_pathway_by_gene("7535", "hsa")  # ZAP70 gene

# Retrieve and parse pathway data
data = k.get("hsa04660")
parsed = k.parse(data)

# Extract pathway interactions
interactions = k.parse_kgml_pathway("hsa04660")
relations = interactions['relations']  # Protein-protein interactions

# Convert to Simple Interaction Format
sif_data = k.pathway2sif("hsa04660")
```

**关键方法**：
- `lookfor_organism()`、`lookfor_pathway()`：按名称搜索
- `get_pathway_by_gene()`：查找包含基因的通路
- `parse_kgml_pathway()`：提取结构化路径数据
- `pathway2sif()`：获取蛋白质相互作用网络

参考：`references/workflow_patterns.md` 完整的通路分析工作流程。

### 3. 化合物数据库搜索

在多个数据库中搜索和交叉引用化合物：

```python
from bioservices import KEGG, UniChem

k = KEGG()

# Search compounds by name
results = k.find("compound", "Geldanamycin")  # Returns cpd:C11222

# Get compound information with database links
compound_info = k.get("cpd:C11222")  # Includes ChEBI links

# Cross-reference KEGG → ChEMBL using UniChem
u = UniChem()
chembl_id = u.get_compound_id_from_kegg("C11222")  # Returns CHEMBL278315
```

**通用工作流程**：
1. 在 KEGG 中按名称搜索化合物
2. 提取物KEGG化合物ID
3. 使用 UniChem 进行 KEGG → ChEMBL 映射
4. ChEBI IDs 通常在 KEGG 条目中提供

参考：`references/identifier_mapping.md` 完整的跨数据库映射指南。

### 4. 序列分析

运行 BLAST 搜索和序列比对：

```python
from bioservices import NCBIblast

s = NCBIblast(verbose=False)

# Run BLASTP against UniProtKB
jobid = s.run(
    program="blastp",
    sequence=protein_sequence,
    stype="protein",
    database="uniprotkb",
    email="your.email@example.com"  # Required by NCBI
)

# Check job status and retrieve results
s.getStatus(jobid)
results = s.getResult(jobid, "out")
```

**注意**： BLAST 作业是异步的。在检索结果之前检查状态。

### 5. 标识符映射

在不同生物数据库之间转换标识符：

```python
from bioservices import UniProt, KEGG

# UniProt mapping (many database pairs supported)
u = UniProt()
results = u.mapping(
    fr="UniProtKB_AC-ID",  # Source database
    to="KEGG",              # Target database
    query="P43403"          # Identifier(s) to convert
)

# KEGG gene ID → UniProt
kegg_to_uniprot = u.mapping(fr="KEGG", to="UniProtKB_AC-ID", query="hsa:7535")

# For compounds, use UniChem
from bioservices import UniChem
u = UniChem()
chembl_from_kegg = u.get_compound_id_from_kegg("C11222")
```

**支持的映射（UniProt）**：
- UniProtKB ↔ KEGG
- UniProtKB ↔ Ensembl
- UniProtKB ↔ PDB
- UniProtKB ↔ RefSeq
- 还有更多（参见`references/identifier_mapping.md`）

### 6. 基因本体查询

访问GO术语和注释：

```python
from bioservices import QuickGO

g = QuickGO(verbose=False)

# Retrieve GO term information
term_info = g.Term("GO:0003824", frmt="obo")

# Search annotations
annotations = g.Annotation(protein="P43403", format="tsv")
```

### 7. 蛋白质-蛋白质相互作用

通过PSICQUIC查询交互数据库：

```python
from bioservices import PSICQUIC

s = PSICQUIC(verbose=False)

# Query specific database (e.g., MINT)
interactions = s.query("mint", "ZAP70 AND species:9606")

# List available interaction databases
databases = s.activeDBs
```

**可用数据库**： MINT、IntAct、BioGRID、DIP 以及 30 多个其他数据库。

## 多服务集成工作流程

BioServices 擅长结合多种服务进行综合分析。常见的集成模式：

### 完整的蛋白质分析流程

执行完整的蛋白质表征工作流程：

```bash
python scripts/protein_analysis_workflow.py ZAP70_HUMAN your.email@example.com
```

该脚本演示：
1. UniProt 搜索蛋白质条目
2. FASTA 序列检索
3. BLAST 相似度搜索
4. KEGG 通路发现
5. PSICQUIC 交互映射

### 通路网络分析

分析有机体的所有路径：

```bash
python scripts/pathway_analysis.py hsa output_directory/
```

摘录与分析：
- 生物体所有途径IDs
- 每个途径的蛋白质-蛋白质相互作用
- 交互类型分布
- 导出为 CSV/SIF 格式

### 跨数据库化合物搜索

跨数据库映射化合物标识符：

```bash
python scripts/compound_cross_reference.py Geldanamycin
```

检索：
- KEGG 化合物 ID
- ChEBI 标识符
- ChEMBL 标识符
- 基本化合物特性

### 批次标识符转换

一次转换多个标识符：

```bash
python scripts/batch_id_converter.py input_ids.txt --from UniProtKB_AC-ID --to KEGG
```

## 最佳实践

### 输出格式处理

不同的服务以不同的格式返回数据：
- **XML**：使用BeautifulSoup解析（大多数SOAP服务）
- **制表符分隔 (TSV)**：Pandas DataFrames 用于表格数据
- **Dictionary/JSON**：直接Python操作
- **FASTA**：BioPython整合用于序列分析

### 速率限制和冗长

控制API请求行为：

```python
from bioservices import KEGG

k = KEGG(verbose=False)  # Suppress HTTP request details
k.TIMEOUT = 30  # Adjust timeout for slow connections
```

### 错误处理

将服务调用包装在 try- except 块中：

```python
try:
    results = u.search("ambiguous_query")
    if results:
        # Process results
        pass
except Exception as e:
    print(f"Search failed: {e}")
```

### 有机体代码

使用标准生物缩写：
- `hsa`：智人（人类）
- `mmu`：小家鼠（小鼠）
- `dme`: 黑腹果蝇
- `sce`：酿酒酵母（酵母）

列出所有生物：`k.list("organism")` 或 `k.organismIds`

### 与其他工具集成

BioServices 适用于：
- **BioPython**：对检索到的FASTA数据进行序列分析
- **Pandas**：表格数据操作
- **PyMOL**：3D结构可视化（检索PDBIDs）
- **NetworkX**：通路相互作用的网络分析
- **Galaxy**：工作流平台的自定义工具包装器

## 资源

### 脚本/

可执行Python脚本演示完整的工作流程：

- `protein_analysis_workflow.py`：端到端蛋白质表征
- `pathway_analysis.py`: KEGG 路径发现和网络提取
- `compound_cross_reference.py`：多数据库复合搜索
- `batch_id_converter.py`：批量标识符映射实用程序

脚本可以直接执行或针对特定用例进行调整。

### 参考文献/

根据需要加载的详细文档：

- `services_reference.md`：所有 40 多个服务及其方法的综合列表
- `workflow_patterns.md`：详细的多步骤分析工作流程
- `identifier_mapping.md`：跨数据库ID转换完整指南

在处理特定服务或复杂集成任务时加载引用。

## 安装

```bash
uv pip install bioservices
```

依赖关系是自动管理的。包已在 Python 3.9-3.12. 上进行测试

## 附加信息

详细的API文档和高级功能请参考：
- 官方文档：https://bioservices.readthedocs.io/
- 源代码：https://github.com/cokelaer/bioservices
- `references/services_reference.md` 中的服务特定参考

