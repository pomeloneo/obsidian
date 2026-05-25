---
name: primekg
description: 查询 Precision Medicine Knowledge Graph（PrimeKG），获取包括 genes、drugs、diseases、phenotypes 等在内的 multiscale biological data。
license: Unknown
metadata:
    skill-author: K-Dense Inc. (PrimeKG original from Harvard MIMS)
---

# PrimeKG Knowledge Graph Skill

## 概览

PrimeKG 是一个 precision medicine knowledge graph，将 20 多个 primary databases 和高质量 scientific literature 集成到单一资源中。它包含超过 100,000 个 nodes 和 400 万条 edges，覆盖 29 种 relationship types，包括 drug-target、disease-gene 和 phenotype-disease associations。

**关键能力：**
- 搜索 nodes（genes、proteins、drugs、diseases、phenotypes）
- 取回 direct neighbors（associated entities 和 clinical evidence）
- 分析 local disease context（related genes、drugs、phenotypes）
- 识别 drug-disease paths（potential repurposing opportunities）

**Data access：** 通过 `query_primekg.py` 进行 programmatic access。Data 存储在 `C:\Users\eamon\Documents\Data\PrimeKG\kg.csv`。

## 何时使用此 Skill

此 skill 应用于：

- **Knowledge-based drug discovery：** 识别 diseases 的 targets 和 mechanisms。
- **Drug repurposing：** 查找可能有证据支持 new indications 的 existing drugs。
- **Phenotype analysis：** 理解 symptoms/phenotypes 如何与 diseases 和 genes 相关。
- **Multiscale biology：** 连接 molecular targets（genes）和 clinical outcomes（diseases）。
- **Network pharmacology：** 研究 drug-target interactions 的 broader network effects。

## 核心 Workflow

### 1. Search for Entities

查找 genes、drugs 或 diseases 的 identifiers。

```python
from scripts.query_primekg import search_nodes

# Search for Alzheimer's disease nodes
results = search_nodes("Alzheimer", node_type="disease")
# Returns: [{"id": "EFO_0000249", "type": "disease", "name": "Alzheimer's disease", ...}]
```

### 2. Get Neighbors（Direct Associations）

取回所有 connected nodes 和 relationship types。

```python
from scripts.query_primekg import get_neighbors

# Get all neighbors of a specific disease ID
neighbors = get_neighbors("EFO_0000249")
# Returns: List of neighbors like {"neighbor_name": "APOE", "relation": "disease_gene", ...}
```

### 3. Analyze Disease Context

用于汇总某个 disease associations 的 high-level function。

```python
from scripts.query_primekg import get_disease_context

# Comprehensive summary for a disease
context = get_disease_context("Alzheimer's disease")
# Access: context['associated_genes'], context['associated_drugs'], context['phenotypes']
```

## PrimeKG 中的 Relationship Types

该 graph 包含若干关键 relationship types，包括：
- `protein_protein`：Physical PPIs
- `drug_protein`：Drug target/mechanism associations
- `disease_gene`：Genetic associations
- `drug_disease`：Indications and contraindications
- `disease_phenotype`：Clinical signs and symptoms
- `gwas`：Genome-wide association studies evidence

## Best Practices

1. **使用具体 IDs：** 使用 `get_neighbors` 时，确保有来自 `search_nodes` 的正确 ID。
2. **Context first：** 在深入具体 genes 或 drugs 之前，先使用 `get_disease_context` 获取 broad overview。
3. **Filter relationships：** 在 `get_neighbors` 中使用 `relation_type` filter，聚焦特定 evidence（例如仅 `drug_protein`）。
4. **Multiscale integration：** 与 `OpenTargets` 结合获取更深入 genetic evidence，或与 `Semantic Scholar` 结合获取最新 literature context。

## 资源

### Scripts
- `scripts/query_primekg.py`：用于搜索和查询 knowledge graph 的 core functions。

### Data Path
- Data: `/mnt/c/Users/eamon/Documents/Data/PrimeKG/kg.csv`
- Total nodes: ~129,000
- Total edges: ~4,000,000
- Database: CSV-based，针对 pandas querying 优化。
