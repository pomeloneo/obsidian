---
name: etetoolkit
description: Phylogenetic tree toolkit (ETE)。Tree manipulation（Newick/NHX）、evolutionary event detection、orthology/paralogy、NCBI taxonomy、visualization（PDF/SVG），用于 phylogenomics。
license: GPL-3.0 license
metadata:
    skill-author: K-Dense Inc.
---

# ETE Toolkit Skill

## 概述

ETE（Environment for Tree Exploration）是用于 phylogenetic 和 hierarchical tree analysis 的工具包。可操作 trees、分析 evolutionary events、可视化结果，并与 biological databases 集成，用于 phylogenomic research 和 clustering analysis。

## 核心能力

### 1. Tree Manipulation and Analysis

加载、操作和分析 hierarchical tree structures，支持：

- **Tree I/O**：读写 Newick、NHX、PhyloXML 和 NeXML formats
- **Tree traversal**：使用 preorder、postorder 或 levelorder 策略遍历 trees
- **Topology modification**：Prune、root、collapse nodes、resolve polytomies
- **Distance calculations**：计算 nodes 之间的 branch lengths 和 topological distances
- **Tree comparison**：计算 Robinson-Foulds distances 并识别 topological differences

**常见模式：**

```python
from ete3 import Tree

# Load tree from file
tree = Tree("tree.nw", format=1)

# Basic statistics
print(f"Leaves: {len(tree)}")
print(f"Total nodes: {len(list(tree.traverse()))}")

# Prune to taxa of interest
taxa_to_keep = ["species1", "species2", "species3"]
tree.prune(taxa_to_keep, preserve_branch_length=True)

# Midpoint root
midpoint = tree.get_midpoint_outgroup()
tree.set_outgroup(midpoint)

# Save modified tree
tree.write(outfile="rooted_tree.nw")
```

使用 `scripts/tree_operations.py` 进行命令行 tree manipulation：

```bash
# Display tree statistics
python scripts/tree_operations.py stats tree.nw

# Convert format
python scripts/tree_operations.py convert tree.nw output.nw --in-format 0 --out-format 1

# Reroot tree
python scripts/tree_operations.py reroot tree.nw rooted.nw --midpoint

# Prune to specific taxa
python scripts/tree_operations.py prune tree.nw pruned.nw --keep-taxa "sp1,sp2,sp3"

# Show ASCII visualization
python scripts/tree_operations.py ascii tree.nw
```

### 2. Phylogenetic Analysis

通过 evolutionary event detection 分析 gene trees：

- **Sequence alignment integration**：将 trees 链接到 multiple sequence alignments（FASTA、Phylip）
- **Species naming**：从 gene names 自动或自定义提取 species
- **Evolutionary events**：使用 Species Overlap 或 tree reconciliation 检测 duplication 和 speciation events
- **Orthology detection**：基于 evolutionary events 识别 orthologs 和 paralogs
- **Gene family analysis**：按 duplications 拆分 trees，折叠 lineage-specific expansions

**Gene tree analysis 工作流：**

```python
from ete3 import PhyloTree

# Load gene tree with alignment
tree = PhyloTree("gene_tree.nw", alignment="alignment.fasta")

# Set species naming function
def get_species(gene_name):
    return gene_name.split("_")[0]

tree.set_species_naming_function(get_species)

# Detect evolutionary events
events = tree.get_descendant_evol_events()

# Analyze events
for node in tree.traverse():
    if hasattr(node, "evoltype"):
        if node.evoltype == "D":
            print(f"Duplication at {node.name}")
        elif node.evoltype == "S":
            print(f"Speciation at {node.name}")

# Extract ortholog groups
ortho_groups = tree.get_speciation_trees()
for i, ortho_tree in enumerate(ortho_groups):
    ortho_tree.write(outfile=f"ortholog_group_{i}.nw")
```

**查找 orthologs 和 paralogs：**

```python
# Find orthologs to query gene
query = tree & "species1_gene1"

orthologs = []
paralogs = []

for event in events:
    if query in event.in_seqs:
        if event.etype == "S":
            orthologs.extend([s for s in event.out_seqs if s != query])
        elif event.etype == "D":
            paralogs.extend([s for s in event.out_seqs if s != query])
```

### 3. NCBI Taxonomy Integration

集成 NCBI Taxonomy database 的 taxonomic information：

- **Database access**：自动下载并本地缓存 NCBI taxonomy（约 300MB）
- **Taxid/name translation**：在 taxonomic IDs 和 scientific names 之间转换
- **Lineage retrieval**：获取完整 evolutionary lineages
- **Taxonomy trees**：构建连接指定 taxa 的 species trees
- **Tree annotation**：用 taxonomic information 自动注释 trees

**构建基于 taxonomy 的 trees：**

```python
from ete3 import NCBITaxa

ncbi = NCBITaxa()

# Build tree from species names
species = ["Homo sapiens", "Pan troglodytes", "Mus musculus"]
name2taxid = ncbi.get_name_translator(species)
taxids = [name2taxid[sp][0] for sp in species]

# Get minimal tree connecting taxa
tree = ncbi.get_topology(taxids)

# Annotate nodes with taxonomy info
for node in tree.traverse():
    if hasattr(node, "sci_name"):
        print(f"{node.sci_name} - Rank: {node.rank} - TaxID: {node.taxid}")
```

**注释现有 trees：**

```python
# Get taxonomy info for tree leaves
for leaf in tree:
    species = extract_species_from_name(leaf.name)
    taxid = ncbi.get_name_translator([species])[species][0]

    # Get lineage
    lineage = ncbi.get_lineage(taxid)
    ranks = ncbi.get_rank(lineage)
    names = ncbi.get_taxid_translator(lineage)

    # Add to node
    leaf.add_feature("taxid", taxid)
    leaf.add_feature("lineage", [names[t] for t in lineage])
```

### 4. Tree Visualization

创建 publication-quality tree visualizations：

- **Output formats**：用于 publications 的 PNG（raster）、PDF 和 SVG（vector）
- **Layout modes**：Rectangular 和 circular tree layouts
- **Interactive GUI**：通过 zoom、pan 和 search 交互式探索 trees
- **Custom styling**：使用 NodeStyle 设置 node appearance（colors、shapes、sizes）
- **Faces**：向 nodes 添加 graphical elements（text、images、charts、heatmaps）
- **Layout functions**：基于 node properties 动态 styling

**基础可视化工作流：**

```python
from ete3 import Tree, TreeStyle, NodeStyle

tree = Tree("tree.nw")

# Configure tree style
ts = TreeStyle()
ts.show_leaf_name = True
ts.show_branch_support = True
ts.scale = 50  # pixels per branch length unit

# Style nodes
for node in tree.traverse():
    nstyle = NodeStyle()

    if node.is_leaf():
        nstyle["fgcolor"] = "blue"
        nstyle["size"] = 8
    else:
        # Color by support
        if node.support > 0.9:
            nstyle["fgcolor"] = "darkgreen"
        else:
            nstyle["fgcolor"] = "red"
        nstyle["size"] = 5

    node.set_style(nstyle)

# Render to file
tree.render("tree.pdf", tree_style=ts)
tree.render("tree.png", w=800, h=600, units="px", dpi=300)
```

使用 `scripts/quick_visualize.py` 快速可视化：

```bash
# Basic visualization
python scripts/quick_visualize.py tree.nw output.pdf

# Circular layout with custom styling
python scripts/quick_visualize.py tree.nw output.pdf --mode c --color-by-support

# High-resolution PNG
python scripts/quick_visualize.py tree.nw output.png --width 1200 --height 800 --units px --dpi 300

# Custom title and styling
python scripts/quick_visualize.py tree.nw output.pdf --title "Species Phylogeny" --show-support
```

**使用 faces 的高级可视化：**

```python
from ete3 import Tree, TreeStyle, TextFace, CircleFace

tree = Tree("tree.nw")

# Add features to nodes
for leaf in tree:
    leaf.add_feature("habitat", "marine" if "fish" in leaf.name else "land")

# Layout function
def layout(node):
    if node.is_leaf():
        # Add colored circle
        color = "blue" if node.habitat == "marine" else "green"
        circle = CircleFace(radius=5, color=color)
        node.add_face(circle, column=0, position="aligned")

        # Add label
        label = TextFace(node.name, fsize=10)
        node.add_face(label, column=1, position="aligned")

ts = TreeStyle()
ts.layout_fn = layout
ts.show_leaf_name = False

tree.render("annotated_tree.pdf", tree_style=ts)
```

### 5. Clustering Analysis

结合数据集成分析 hierarchical clustering results：

- **ClusterTree**：用于 clustering dendrograms 的专用 class
- **Data matrix linking**：将 tree leaves 连接到 numerical profiles
- **Cluster metrics**：Silhouette coefficient、Dunn index、inter/intra-cluster distances
- **Validation**：用不同 distance metrics 测试 cluster quality
- **Heatmap visualization**：在 trees 旁显示 data matrices

**Clustering 工作流：**

```python
from ete3 import ClusterTree

# Load tree with data matrix
matrix = """#Names\tSample1\tSample2\tSample3
Gene1\t1.5\t2.3\t0.8
Gene2\t0.9\t1.1\t1.8
Gene3\t2.1\t2.5\t0.5"""

tree = ClusterTree("((Gene1,Gene2),Gene3);", text_array=matrix)

# Evaluate cluster quality
for node in tree.traverse():
    if not node.is_leaf():
        silhouette = node.get_silhouette()
        dunn = node.get_dunn()

        print(f"Cluster: {node.name}")
        print(f"  Silhouette: {silhouette:.3f}")
        print(f"  Dunn index: {dunn:.3f}")

# Visualize with heatmap
tree.show("heatmap")
```

### 6. Tree Comparison

量化 trees 之间的 topological differences：

- **Robinson-Foulds distance**：tree comparison 的标准 metric
- **Normalized RF**：尺度不变距离（0.0 到 1.0）
- **Partition analysis**：识别 unique 和 shared bipartitions
- **Consensus trees**：分析 multiple trees 的支持度
- **Batch comparison**：对 multiple trees 进行 pairwise comparison

**比较两个 trees：**

```python
from ete3 import Tree

tree1 = Tree("tree1.nw")
tree2 = Tree("tree2.nw")

# Calculate RF distance
rf, max_rf, common_leaves, parts_t1, parts_t2 = tree1.robinson_foulds(tree2)

print(f"RF distance: {rf}/{max_rf}")
print(f"Normalized RF: {rf/max_rf:.3f}")
print(f"Common leaves: {len(common_leaves)}")

# Find unique partitions
unique_t1 = parts_t1 - parts_t2
unique_t2 = parts_t2 - parts_t1

print(f"Unique to tree1: {len(unique_t1)}")
print(f"Unique to tree2: {len(unique_t2)}")
```

**比较多个 trees：**

```python
import numpy as np

trees = [Tree(f"tree{i}.nw") for i in range(4)]

# Create distance matrix
n = len(trees)
dist_matrix = np.zeros((n, n))

for i in range(n):
    for j in range(i+1, n):
        rf, max_rf, _, _, _ = trees[i].robinson_foulds(trees[j])
        norm_rf = rf / max_rf if max_rf > 0 else 0
        dist_matrix[i, j] = norm_rf
        dist_matrix[j, i] = norm_rf
```

## 安装和设置

安装 ETE toolkit：

```bash
# Basic installation
uv pip install ete3

# With external dependencies for rendering (optional but recommended)
# On macOS:
brew install qt@5

# On Ubuntu/Debian:
sudo apt-get install python3-pyqt5 python3-pyqt5.qtsvg

# For full features including GUI
uv pip install ete3[gui]
```

**首次 NCBI Taxonomy 设置：**

第一次实例化 NCBITaxa 时，它会自动将 NCBI taxonomy database（约 300MB）下载到 `~/.etetoolkit/taxa.sqlite`。这只发生一次：

```python
from ete3 import NCBITaxa
ncbi = NCBITaxa()  # Downloads database on first run
```

更新 taxonomy database：

```python
ncbi.update_taxonomy_database()  # Download latest NCBI data
```

## 常见使用场景

### Use Case 1：Phylogenomic Pipeline

从 gene tree 到 ortholog identification 的完整工作流：

```python
from ete3 import PhyloTree, NCBITaxa

# 1. Load gene tree with alignment
tree = PhyloTree("gene_tree.nw", alignment="alignment.fasta")

# 2. Configure species naming
tree.set_species_naming_function(lambda x: x.split("_")[0])

# 3. Detect evolutionary events
tree.get_descendant_evol_events()

# 4. Annotate with taxonomy
ncbi = NCBITaxa()
for leaf in tree:
    if leaf.species in species_to_taxid:
        taxid = species_to_taxid[leaf.species]
        lineage = ncbi.get_lineage(taxid)
        leaf.add_feature("lineage", lineage)

# 5. Extract ortholog groups
ortho_groups = tree.get_speciation_trees()

# 6. Save and visualize
for i, ortho in enumerate(ortho_groups):
    ortho.write(outfile=f"ortho_{i}.nw")
```

### Use Case 2：Tree Preprocessing and Formatting

批量处理 trees 以供分析：

```bash
# Convert format
python scripts/tree_operations.py convert input.nw output.nw --in-format 0 --out-format 1

# Root at midpoint
python scripts/tree_operations.py reroot input.nw rooted.nw --midpoint

# Prune to focal taxa
python scripts/tree_operations.py prune rooted.nw pruned.nw --keep-taxa taxa_list.txt

# Get statistics
python scripts/tree_operations.py stats pruned.nw
```

### Use Case 3：Publication-Quality Figures

创建带样式的 visualizations：

```python
from ete3 import Tree, TreeStyle, NodeStyle, TextFace

tree = Tree("tree.nw")

# Define clade colors
clade_colors = {
    "Mammals": "red",
    "Birds": "blue",
    "Fish": "green"
}

def layout(node):
    # Highlight clades
    if node.is_leaf():
        for clade, color in clade_colors.items():
            if clade in node.name:
                nstyle = NodeStyle()
                nstyle["fgcolor"] = color
                nstyle["size"] = 8
                node.set_style(nstyle)
    else:
        # Add support values
        if node.support > 0.95:
            support = TextFace(f"{node.support:.2f}", fsize=8)
            node.add_face(support, column=0, position="branch-top")

ts = TreeStyle()
ts.layout_fn = layout
ts.show_scale = True

# Render for publication
tree.render("figure.pdf", w=200, units="mm", tree_style=ts)
tree.render("figure.svg", tree_style=ts)  # Editable vector
```

### Use Case 4：Automated Tree Analysis

系统化处理多个 trees：

```python
from ete3 import Tree
import os

input_dir = "trees"
output_dir = "processed"

for filename in os.listdir(input_dir):
    if filename.endswith(".nw"):
        tree = Tree(os.path.join(input_dir, filename))

        # Standardize: midpoint root, resolve polytomies
        midpoint = tree.get_midpoint_outgroup()
        tree.set_outgroup(midpoint)
        tree.resolve_polytomy(recursive=True)

        # Filter low support branches
        for node in tree.traverse():
            if hasattr(node, 'support') and node.support < 0.5:
                if not node.is_leaf() and not node.is_root():
                    node.delete()

        # Save processed tree
        output_file = os.path.join(output_dir, f"processed_{filename}")
        tree.write(outfile=output_file)
```

## 参考文档

完整 API documentation、code examples 和详细指南，请参考 `references/` 目录中的以下资源：

- **`api_reference.md`**：所有 ETE classes 和 methods（Tree、PhyloTree、ClusterTree、NCBITaxa）的完整 API documentation，包括 parameters、return types 和 code examples
- **`workflows.md`**：按任务组织的常见 workflow patterns（tree operations、phylogenetic analysis、tree comparison、taxonomy integration、clustering analysis）
- **`visualization.md`**：全面 visualization guide，涵盖 TreeStyle、NodeStyle、Faces、layout functions 和 advanced visualization techniques

需要详细信息时加载这些 references：

```python
# To use API reference
# Read references/api_reference.md for complete method signatures and parameters

# To implement workflows
# Read references/workflows.md for step-by-step workflow examples

# To create visualizations
# Read references/visualization.md for styling and rendering options
```

## 故障排除

**Import errors：**

```bash
# If "ModuleNotFoundError: No module named 'ete3'"
uv pip install ete3

# For GUI and rendering issues
uv pip install ete3[gui]
```

**Rendering issues：**

如果 `tree.render()` 或 `tree.show()` 因 Qt-related errors 失败，请安装系统依赖：

```bash
# macOS
brew install qt@5

# Ubuntu/Debian
sudo apt-get install python3-pyqt5 python3-pyqt5.qtsvg
```

**NCBI Taxonomy database：**

如果 database download 失败或损坏：

```python
from ete3 import NCBITaxa
ncbi = NCBITaxa()
ncbi.update_taxonomy_database()  # Redownload database
```

**大型 trees 的内存问题：**

对于非常大的 trees（>10,000 leaves），使用 iterators 而不是 list comprehensions：

```python
# Memory-efficient iteration
for leaf in tree.iter_leaves():
    process(leaf)

# Instead of
for leaf in tree.get_leaves():  # Loads all into memory
    process(leaf)
```

## Newick Format Reference

ETE 支持多个 Newick format specifications（0-100）：

- **Format 0**：带 branch lengths 的灵活格式（默认）
- **Format 1**：带 internal node names
- **Format 2**：带 bootstrap/support values
- **Format 5**：Internal node names + branch lengths
- **Format 8**：All features（names、distances、support）
- **Format 9**：仅 leaf names
- **Format 100**：仅 topology

读写时指定 format：

```python
tree = Tree("tree.nw", format=1)
tree.write(outfile="output.nw", format=5)
```

NHX（New Hampshire eXtended）format 会保留 custom features：

```python
tree.write(outfile="tree.nhx", features=["habitat", "temperature", "depth"])
```

## 最佳实践

1. **保留 branch lengths**：为 phylogenetic analysis pruning 时使用 `preserve_branch_length=True`
2. **缓存内容**：在 large trees 上重复访问 node contents 时使用 `get_cached_content()`
3. **使用 iterators**：使用 `iter_*` methods 以内存高效地处理 large trees
4. **选择合适的 traversal**：Postorder 用于 bottom-up analysis，preorder 用于 top-down
5. **验证 monophyly**：始终检查返回的 clade type（monophyletic/paraphyletic/polyphyletic）
6. **Publication 使用 vector formats**：publication figures 使用 PDF 或 SVG（可缩放、可编辑）
7. **交互式测试**：渲染到文件前，使用 `tree.show()` 测试 visualizations
8. **PhyloTree 用于 phylogenetics**：对 gene trees 和 evolutionary analysis 使用 PhyloTree class
9. **选择 copy method**："newick" 用于速度，"cpickle" 用于完整保真，"deepcopy" 用于复杂 objects
10. **NCBI query caching**：存储 NCBI taxonomy query results，避免重复 database access
