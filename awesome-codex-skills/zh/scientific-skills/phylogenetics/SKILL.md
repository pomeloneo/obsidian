---
name: phylogenetics
description: 使用 MAFFT（multiple alignment）、IQ-TREE 2（maximum likelihood）和 FastTree（fast NJ/ML）构建并分析 phylogenetic trees。使用 ETE3 或 FigTree 可视化。用于 evolutionary analysis、microbial genomics、viral phylodynamics、protein family analysis 和 molecular clock studies。
license: Unknown
metadata:
    skill-author: Kuan-lin Huang
---

# 系统发育学

## 概览

Phylogenetic analysis 通过推断谱系分支模式来重建 biological sequences（genes、proteins、genomes）的 evolutionary history。此 skill 覆盖标准 pipeline：

1. **MAFFT** — Multiple sequence alignment
2. **IQ-TREE 2** — Maximum likelihood tree inference with model selection
3. **FastTree** — Fast approximate maximum likelihood (for large datasets)
4. **ETE3** — Python library for tree manipulation and visualization

**安装：**
```bash
# Conda (recommended for CLI tools)
conda install -c bioconda mafft iqtree fasttree
pip install ete3
```

## 何时使用此 Skill

在以下场景使用 phylogenetics：

- **Evolutionary relationships**：哪个 organism/gene 与我的 sequence 关系最近？
- **Viral phylodynamics**：追踪 outbreak spread 并估计 transmission dates
- **Protein family analysis**：推断 gene family 内的 evolutionary relationships
- **Horizontal gene transfer detection**：识别 species/gene trees 不一致的 genes
- **Ancestral sequence reconstruction**：推断 ancestral protein sequences
- **Molecular clock analysis**：使用 temporal sampling 估计 divergence dates
- **GWAS companion**：将 variants 放入 evolutionary context（例如 SARS-CoV-2 variants）
- **Microbiology**：从 16S rRNA 或 core genome phylogeny 得到 species phylogeny

## 标准 Workflow

### 1. 使用 MAFFT 进行 Multiple Sequence Alignment

```python
import subprocess
import os

def run_mafft(input_fasta: str, output_fasta: str, method: str = "auto",
               n_threads: int = 4) -> str:
    """
    Align sequences with MAFFT.

    Args:
        input_fasta: Path to unaligned FASTA file
        output_fasta: Path for aligned output
        method: 'auto' (auto-select), 'einsi' (accurate), 'linsi' (accurate, slow),
                'fftnsi' (medium), 'fftns' (fast), 'retree2' (fast)
        n_threads: Number of CPU threads

    Returns:
        Path to aligned FASTA file
    """
    methods = {
        "auto": ["mafft", "--auto"],
        "einsi": ["mafft", "--genafpair", "--maxiterate", "1000"],
        "linsi": ["mafft", "--localpair", "--maxiterate", "1000"],
        "fftnsi": ["mafft", "--fftnsi"],
        "fftns": ["mafft", "--fftns"],
        "retree2": ["mafft", "--retree", "2"],
    }

    cmd = methods.get(method, methods["auto"])
    cmd += ["--thread", str(n_threads), "--inputorder", input_fasta]

    with open(output_fasta, 'w') as out:
        result = subprocess.run(cmd, stdout=out, stderr=subprocess.PIPE, text=True)

    if result.returncode != 0:
        raise RuntimeError(f"MAFFT failed:\n{result.stderr}")

    # Count aligned sequences
    with open(output_fasta) as f:
        n_seqs = sum(1 for line in f if line.startswith('>'))
    print(f"MAFFT: aligned {n_seqs} sequences → {output_fasta}")

    return output_fasta

# MAFFT method selection guide:
# Few sequences (<200), accurate: linsi or einsi
# Many sequences (<1000), moderate: fftnsi
# Large datasets (>1000): fftns or auto
# Ultra-fast (>10000): mafft --retree 1
```

### 2. Trim Alignment（可选但推荐）

```python
def trim_alignment_trimal(aligned_fasta: str, output_fasta: str,
                            method: str = "automated1") -> str:
    """
    Trim poorly aligned columns with TrimAl.

    Methods:
    - 'automated1': Automatic heuristic (recommended)
    - 'gappyout': Remove gappy columns
    - 'strict': Strict gap threshold
    """
    cmd = ["trimal", f"-{method}", "-in", aligned_fasta, "-out", output_fasta, "-fasta"]
    result = subprocess.run(cmd, capture_output=True, text=True)
    if result.returncode != 0:
        print(f"TrimAl warning: {result.stderr}")
        # Fall back to using the untrimmed alignment
        import shutil
        shutil.copy(aligned_fasta, output_fasta)
    return output_fasta
```

### 3. IQ-TREE 2 — Maximum Likelihood Tree

```python
def run_iqtree(aligned_fasta: str, output_prefix: str,
                model: str = "TEST", bootstrap: int = 1000,
                n_threads: int = 4, extra_args: list = None) -> dict:
    """
    Build a maximum likelihood tree with IQ-TREE 2.

    Args:
        aligned_fasta: Aligned FASTA file
        output_prefix: Prefix for output files
        model: 'TEST' for automatic model selection, or specify (e.g., 'GTR+G' for DNA,
               'LG+G4' for proteins, 'JTT+G' for proteins)
        bootstrap: Number of ultrafast bootstrap replicates (1000 recommended)
        n_threads: Number of threads ('AUTO' to auto-detect)
        extra_args: Additional IQ-TREE arguments

    Returns:
        Dict with paths to output files
    """
    cmd = [
        "iqtree2",
        "-s", aligned_fasta,
        "--prefix", output_prefix,
        "-m", model,
        "-B", str(bootstrap),   # Ultrafast bootstrap
        "-T", str(n_threads),
        "--redo"                # Overwrite existing results
    ]

    if extra_args:
        cmd.extend(extra_args)

    result = subprocess.run(cmd, capture_output=True, text=True)

    if result.returncode != 0:
        raise RuntimeError(f"IQ-TREE failed:\n{result.stderr}")

    # Print model selection result
    log_file = f"{output_prefix}.log"
    if os.path.exists(log_file):
        with open(log_file) as f:
            for line in f:
                if "Best-fit model" in line:
                    print(f"IQ-TREE: {line.strip()}")

    output_files = {
        "tree": f"{output_prefix}.treefile",
        "log": f"{output_prefix}.log",
        "iqtree": f"{output_prefix}.iqtree",  # Full report
        "model": f"{output_prefix}.model.gz",
    }

    print(f"IQ-TREE: Tree saved to {output_files['tree']}")
    return output_files

# IQ-TREE model selection guide:
# DNA:     TEST → GTR+G, HKY+G, TrN+G
# Protein: TEST → LG+G4, WAG+G, JTT+G, Q.pfam+G
# Codon:   TEST → MG+F3X4

# For temporal (molecular clock) analysis, add:
# extra_args = ["--date", "dates.txt", "--clock-test", "--date-CI", "95"]
```

### 4. FastTree — Fast Approximate ML

对于 IQ-TREE 太慢的大型 datasets（>1000 sequences）：

```python
def run_fasttree(aligned_fasta: str, output_tree: str,
                  sequence_type: str = "nt", model: str = "gtr",
                  n_threads: int = 4) -> str:
    """
    Build a fast approximate ML tree with FastTree.

    Args:
        sequence_type: 'nt' for nucleotide or 'aa' for amino acid
        model: For nt: 'gtr' (recommended) or 'jc'; for aa: 'lg', 'wag', 'jtt'
    """
    if sequence_type == "nt":
        cmd = ["FastTree", "-nt", "-gtr"]
    else:
        cmd = ["FastTree", f"-{model}"]

    cmd += [aligned_fasta]

    with open(output_tree, 'w') as out:
        result = subprocess.run(cmd, stdout=out, stderr=subprocess.PIPE, text=True)

    if result.returncode != 0:
        raise RuntimeError(f"FastTree failed:\n{result.stderr}")

    print(f"FastTree: Tree saved to {output_tree}")
    return output_tree
```

### 5. 使用 ETE3 进行 Tree Analysis 与 Visualization

```python
from ete3 import Tree, TreeStyle, NodeStyle, TextFace, PhyloTree
import matplotlib.pyplot as plt

def load_tree(tree_file: str) -> Tree:
    """Load a Newick tree file."""
    t = Tree(tree_file)
    print(f"Tree: {len(t)} leaves, {len(list(t.traverse()))} nodes")
    return t

def basic_tree_stats(t: Tree) -> dict:
    """Compute basic tree statistics."""
    leaves = t.get_leaves()
    distances = [t.get_distance(l1, l2) for l1 in leaves[:min(50, len(leaves))]
                 for l2 in leaves[:min(50, len(leaves))] if l1 != l2]

    stats = {
        "n_leaves": len(leaves),
        "n_internal_nodes": len(t) - len(leaves),
        "total_branch_length": sum(n.dist for n in t.traverse()),
        "max_leaf_distance": max(distances) if distances else 0,
        "mean_leaf_distance": sum(distances)/len(distances) if distances else 0,
    }
    return stats

def find_mrca(t: Tree, leaf_names: list) -> Tree:
    """Find the most recent common ancestor of a set of leaves."""
    return t.get_common_ancestor(*leaf_names)

def visualize_tree(t: Tree, output_file: str = "tree.png",
                    show_branch_support: bool = True,
                    color_groups: dict = None,
                    width: int = 800) -> None:
    """
    Render phylogenetic tree to image.

    Args:
        t: ETE3 Tree object
        color_groups: Dict mapping leaf_name → color (for coloring taxa)
        show_branch_support: Show bootstrap values
    """
    ts = TreeStyle()
    ts.show_leaf_name = True
    ts.show_branch_support = show_branch_support
    ts.mode = "r"  # 'r' = rectangular, 'c' = circular

    if color_groups:
        for node in t.traverse():
            if node.is_leaf() and node.name in color_groups:
                nstyle = NodeStyle()
                nstyle["fgcolor"] = color_groups[node.name]
                nstyle["size"] = 8
                node.set_style(nstyle)

    t.render(output_file, tree_style=ts, w=width, units="px")
    print(f"Tree saved to: {output_file}")

def midpoint_root(t: Tree) -> Tree:
    """Root tree at midpoint (use when outgroup unknown)."""
    t.set_outgroup(t.get_midpoint_outgroup())
    return t

def prune_tree(t: Tree, keep_leaves: list) -> Tree:
    """Prune tree to keep only specified leaves."""
    t.prune(keep_leaves, preserve_branch_length=True)
    return t
```

### 6. 完整 Analysis Script

```python
import subprocess, os
from ete3 import Tree

def full_phylogenetic_analysis(
    input_fasta: str,
    output_dir: str = "phylo_results",
    sequence_type: str = "nt",
    n_threads: int = 4,
    bootstrap: int = 1000,
    use_fasttree: bool = False
) -> dict:
    """
    Complete phylogenetic pipeline: align → trim → tree → visualize.

    Args:
        input_fasta: Unaligned FASTA
        sequence_type: 'nt' (nucleotide) or 'aa' (amino acid/protein)
        use_fasttree: Use FastTree instead of IQ-TREE (faster for large datasets)
    """
    os.makedirs(output_dir, exist_ok=True)
    prefix = os.path.join(output_dir, "phylo")

    print("=" * 50)
    print("Step 1: Multiple Sequence Alignment (MAFFT)")
    aligned = run_mafft(input_fasta, f"{prefix}_aligned.fasta",
                         method="auto", n_threads=n_threads)

    print("\nStep 2: Tree Inference")
    if use_fasttree:
        tree_file = run_fasttree(
            aligned, f"{prefix}.tree",
            sequence_type=sequence_type,
            model="gtr" if sequence_type == "nt" else "lg"
        )
    else:
        model = "TEST" if sequence_type == "nt" else "TEST"
        iqtree_files = run_iqtree(
            aligned, prefix,
            model=model,
            bootstrap=bootstrap,
            n_threads=n_threads
        )
        tree_file = iqtree_files["tree"]

    print("\nStep 3: Tree Analysis")
    t = Tree(tree_file)
    t = midpoint_root(t)

    stats = basic_tree_stats(t)
    print(f"Tree statistics: {stats}")

    print("\nStep 4: Visualization")
    visualize_tree(t, f"{prefix}_tree.png", show_branch_support=True)

    # Save rooted tree
    rooted_tree_file = f"{prefix}_rooted.nwk"
    t.write(format=1, outfile=rooted_tree_file)

    results = {
        "aligned_fasta": aligned,
        "tree_file": tree_file,
        "rooted_tree": rooted_tree_file,
        "visualization": f"{prefix}_tree.png",
        "stats": stats
    }

    print("\n" + "=" * 50)
    print("Phylogenetic analysis complete!")
    print(f"Results in: {output_dir}/")
    return results
```

## IQ-TREE Model 指南

### DNA Models

| Model | 描述 | 使用场景 |
|-------|-------------|---------|
| `GTR+G4` | General Time Reversible + Gamma | 最灵活的 DNA model |
| `HKY+G4` | Hasegawa-Kishino-Yano + Gamma | Two-rate model（常见） |
| `TrN+G4` | Tamura-Nei | Unequal transitions |
| `JC` | Jukes-Cantor | 最简单；所有 rates 相等 |

### Protein Models

| Model | 描述 | 使用场景 |
|-------|-------------|---------|
| `LG+G4` | Le-Gascuel + Gamma | 最佳平均 protein model |
| `WAG+G4` | Whelan-Goldman | 广泛使用 |
| `JTT+G4` | Jones-Taylor-Thornton | Classical model |
| `Q.pfam+G4` | pfam-trained | 用于 Pfam-like protein families |
| `Q.bird+G4` | Bird-specific | Vertebrate proteins |

**提示：** 使用 `-m TEST` 让 IQ-TREE 自动选择最佳 model。

## Best Practices

- **Alignment quality first**：差的 alignment 会导致不可靠 trees；手动检查 alignment
- **小规模（<200 seq）使用 `linsi`，大规模 alignments 使用 `fftns` 或 `auto`**
- **Model selection**：除非有具体理由，否则 IQ-TREE 始终使用 `-m TEST`
- **Bootstrap**：使用 ≥1000 ultrafast bootstraps（`-B 1000`）评估 branch support
- **Root the tree**：Unrooted trees 可能误导；使用 outgroup 或 midpoint rooting
- **>5000 sequences 使用 FastTree**：IQ-TREE 会变慢；FastTree 快 10–100×
- **Trim long alignments**：TrimAl 移除不可靠 columns；提高 tree accuracy
- **构建 trees 前检查 viral/bacterial sequences 中的 recombination**（`RDP4`、`GARD`）

## 其他资源

- **MAFFT**: https://mafft.cbrc.jp/alignment/software/
- **IQ-TREE 2**: http://www.iqtree.org/ | Tutorial: https://www.iqtree.org/workshop/molevol2022
- **FastTree**: http://www.microbesonline.org/fasttree/
- **ETE3**: http://etetoolkit.org/
- **FigTree** (GUI visualization): https://tree.bio.ed.ac.uk/software/figtree/
- **iTOL** (web visualization): https://itol.embl.de/
- **MUSCLE** (alternative aligner): https://www.drive5.com/muscle/
- **TrimAl** (alignment trimming): https://vicfero.github.io/trimal/
