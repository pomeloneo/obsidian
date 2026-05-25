---
name: diffdock
description: 基于 diffusion 的分子对接。根据 PDB/SMILES 预测 protein-ligand 结合构象、confidence scores、virtual screening，用于 structure-based drug design。不用于亲和力预测。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# DiffDock：使用 Diffusion Models 进行分子对接

## 概述

DiffDock 是一个基于 diffusion 的深度学习分子对接工具，用于预测小分子 ligand 与 protein target 的 3D 结合构象。它代表了计算对接领域的前沿能力，对 structure-based drug discovery 和 chemical biology 很关键。

**核心能力：**
- 使用深度学习高精度预测 ligand binding poses
- 支持 protein structures（PDB 文件）或 sequences（通过 ESMFold）
- 处理单个复合物或批量 virtual screening 活动
- 生成 confidence scores 来评估预测可靠性
- 处理多种 ligand 输入（SMILES、SDF、MOL2）

**关键区别：** DiffDock 预测的是**结合构象**（3D 结构）和**置信度**（预测确定性），不是 binding affinity（ΔG、Kd）。做亲和力评估时，始终要结合 scoring functions（GNINA、MM/GBSA）。

## 何时使用此 Skill

以下情况应使用此 skill：

- “Dock this ligand to a protein” 或 “predict binding pose”
- “Run molecular docking” 或 “perform protein-ligand docking”
- “Virtual screening” 或 “screen compound library”
- “Where does this molecule bind?” 或 “predict binding site”
- Structure-based drug design 或 lead optimization 任务
- 涉及 PDB 文件 + SMILES 字符串或 ligand structures 的任务
- 多个 protein-ligand 对的批量 docking

## 安装和环境设置

### 检查环境状态

在继续 DiffDock 任务前，先验证环境设置：

```bash
# Use the provided setup checker
python scripts/setup_check.py
```

此脚本会验证 Python 版本、带 CUDA 的 PyTorch、PyTorch Geometric、RDKit、ESM 和其他依赖项。

### 安装选项

**选项 1：Conda（推荐）**
```bash
git clone https://github.com/gcorso/DiffDock.git
cd DiffDock
conda env create --file environment.yml
conda activate diffdock
```

**选项 2：Docker**
```bash
docker pull rbgcsail/diffdock
docker run -it --gpus all --entrypoint /bin/bash rbgcsail/diffdock
micromamba activate diffdock
```

**重要说明：**
- 强烈建议使用 GPU（相比 CPU 加速 10-100 倍）
- 首次运行会预计算 SO(2)/SO(3) lookup tables（约 2-5 分钟）
- 如果模型 checkpoints（约 500MB）不存在，会自动下载

## 核心工作流

### Workflow 1：单个 Protein-Ligand Docking

**使用场景：** 将一个 ligand dock 到一个 protein target

**输入要求：**
- Protein：PDB 文件或氨基酸序列
- Ligand：SMILES 字符串或结构文件（SDF/MOL2）

**命令：**
```bash
python -m inference \
  --config default_inference_args.yaml \
  --protein_path protein.pdb \
  --ligand "CC(=O)Oc1ccccc1C(=O)O" \
  --out_dir results/single_docking/
```

**替代方式（protein sequence）：**
```bash
python -m inference \
  --config default_inference_args.yaml \
  --protein_sequence "MSKGEELFTGVVPILVELDGDVNGHKF..." \
  --ligand ligand.sdf \
  --out_dir results/sequence_docking/
```

**输出结构：**
```
results/single_docking/
├── rank_1.sdf          # Top-ranked pose
├── rank_2.sdf          # Second-ranked pose
├── ...
├── rank_10.sdf         # 10th pose (default: 10 samples)
└── confidence_scores.txt
```

### Workflow 2：批量处理多个复合物

**使用场景：** 将多个 ligands dock 到 proteins，virtual screening campaigns

**Step 1：准备 Batch CSV**

使用提供的脚本创建或验证批量输入：

```bash
# Create template
python scripts/prepare_batch_csv.py --create --output batch_input.csv

# Validate existing CSV
python scripts/prepare_batch_csv.py my_input.csv --validate
```

**CSV 格式：**
```csv
complex_name,protein_path,ligand_description,protein_sequence
complex1,protein1.pdb,CC(=O)Oc1ccccc1C(=O)O,
complex2,,COc1ccc(C#N)cc1,MSKGEELFT...
complex3,protein3.pdb,ligand3.sdf,
```

**必需列：**
- `complex_name`：唯一标识符
- `protein_path`：PDB 文件路径（如果使用 sequence，则留空）
- `ligand_description`：SMILES 字符串或 ligand 文件路径
- `protein_sequence`：氨基酸序列（如果使用 PDB，则留空）

**Step 2：运行 Batch Docking**

```bash
python -m inference \
  --config default_inference_args.yaml \
  --protein_ligand_csv batch_input.csv \
  --out_dir results/batch/ \
  --batch_size 10
```

**对于大型 Virtual Screening（>100 个 compounds）：**

预计算 protein embeddings 以加快处理：
```bash
# Pre-compute embeddings
python datasets/esm_embedding_preparation.py \
  --protein_ligand_csv screening_input.csv \
  --out_file protein_embeddings.pt

# Run with pre-computed embeddings
python -m inference \
  --config default_inference_args.yaml \
  --protein_ligand_csv screening_input.csv \
  --esm_embeddings_path protein_embeddings.pt \
  --out_dir results/screening/
```

### Workflow 3：分析结果

Docking 完成后，分析 confidence scores 并对预测排序：

```bash
# Analyze all results
python scripts/analyze_results.py results/batch/

# Show top 5 per complex
python scripts/analyze_results.py results/batch/ --top 5

# Filter by confidence threshold
python scripts/analyze_results.py results/batch/ --threshold 0.0

# Export to CSV
python scripts/analyze_results.py results/batch/ --export summary.csv

# Show top 20 predictions across all complexes
python scripts/analyze_results.py results/batch/ --best 20
```

分析脚本会：
- 从所有预测中解析 confidence scores
- 分类为 High（>0）、Moderate（-1.5 到 0）或 Low（<-1.5）
- 在复合物内部和跨复合物对预测排序
- 生成统计摘要
- 导出结果到 CSV 供下游分析

## Confidence Score 解读

**理解分数：**

| Score Range | Confidence Level | Interpretation |
|------------|------------------|----------------|
| **> 0** | High | 强预测，可能准确 |
| **-1.5 to 0** | Moderate | 合理预测，需要仔细验证 |
| **< -1.5** | Low | 不确定预测，需要验证 |

**关键说明：**
1. **Confidence ≠ Affinity**：高置信度表示模型对结构的确定性，不代表强结合
2. **上下文很重要**：针对以下情况调整预期：
   - 大 ligands（>500 Da）：预期置信度更低
   - 多条 protein chains：可能降低置信度
   - 新颖 protein families：表现可能较弱
3. **多个样本**：查看前 3-5 个预测，寻找共识

**详细指南：** 使用 Read 工具阅读 `references/confidence_and_limitations.md`

## 参数定制

### 使用自定义配置

为特定使用场景创建自定义配置：

```bash
# Copy template
cp assets/custom_inference_config.yaml my_config.yaml

# Edit parameters (see template for presets)
# Then run with custom config
python -m inference \
  --config my_config.yaml \
  --protein_ligand_csv input.csv \
  --out_dir results/
```

### 需要调整的关键参数

**采样密度：**
- `samples_per_complex: 10` → 困难案例可增加到 20-40
- 更多 samples = 覆盖更好，但运行时间更长

**推理步数：**
- `inference_steps: 20` → 为提高准确性可增加到 25-30
- 更多 steps = 潜在质量更好，但更慢

**Temperature 参数（控制多样性）：**
- `temp_sampling_tor: 7.04` → 对柔性 ligands 增加（8-10）
- `temp_sampling_tor: 7.04` → 对刚性 ligands 降低（5-6）
- 更高 temperature = 更多样的 poses

**模板中可用的 Presets：**
1. High Accuracy：更多 samples + steps，更低 temperature
2. Fast Screening：更少 samples，更快
3. Flexible Ligands：提高 torsion temperature
4. Rigid Ligands：降低 torsion temperature

**完整参数参考：** 使用 Read 工具阅读 `references/parameters_reference.md`

## 高级技术

### Ensemble Docking（Protein Flexibility）

对于已知具有柔性的 proteins，对多个 conformations 进行 docking：

```python
# Create ensemble CSV
import pandas as pd

conformations = ["conf1.pdb", "conf2.pdb", "conf3.pdb"]
ligand = "CC(=O)Oc1ccccc1C(=O)O"

data = {
    "complex_name": [f"ensemble_{i}" for i in range(len(conformations))],
    "protein_path": conformations,
    "ligand_description": [ligand] * len(conformations),
    "protein_sequence": [""] * len(conformations)
}

pd.DataFrame(data).to_csv("ensemble_input.csv", index=False)
```

使用增加的采样运行 docking：
```bash
python -m inference \
  --config default_inference_args.yaml \
  --protein_ligand_csv ensemble_input.csv \
  --samples_per_complex 20 \
  --out_dir results/ensemble/
```

### 与 Scoring Functions 集成

DiffDock 生成 poses；结合其他工具评估 affinity：

**GNINA（快速 neural network scoring）：**
```bash
for pose in results/*.sdf; do
    gnina -r protein.pdb -l "$pose" --score_only
done
```

**MM/GBSA（更准确，更慢）：**
能量最小化后使用 AmberTools MMPBSA.py 或 gmx_MMPBSA

**Free Energy Calculations（最准确）：**
使用 OpenMM + OpenFE 或 GROMACS 进行 FEP/TI calculations

**推荐工作流：**
1. DiffDock → 生成带 confidence scores 的 poses
2. 视觉检查 → 检查结构合理性
3. GNINA 或 MM/GBSA → 重新打分并按 affinity 排序
4. 实验验证 → 生化 assays

## 局限性和适用范围

**DiffDock 适用于：**
- 小分子 ligands（通常 100-1000 Da）
- Drug-like organic compounds
- 小 peptides（<20 residues）
- 单链或多链 proteins

**DiffDock 不适用于：**
- 大 biomolecules（protein-protein docking）→ 使用 DiffDock-PP 或 AlphaFold-Multimer
- 大 peptides（>20 residues）→ 使用替代方法
- Covalent docking → 使用专门的 covalent docking 工具
- Binding affinity prediction → 与 scoring functions 结合
- Membrane proteins → 未专门训练，谨慎使用

**完整局限性：** 使用 Read 工具阅读 `references/confidence_and_limitations.md`

## 故障排除

### 常见问题

**问题：所有预测的 confidence scores 都很低**
- 原因：ligands 很大或不常见、binding site 不清楚、protein flexibility
- 解决方案：增加 `samples_per_complex`（20-40），尝试 ensemble docking，验证 protein structure

**问题：Out of memory 错误**
- 原因：GPU 显存不足以支持 batch size
- 解决方案：降低 `--batch_size 2`，或一次处理更少 complexes

**问题：性能很慢**
- 原因：在 CPU 而非 GPU 上运行
- 解决方案：用 `python -c "import torch; print(torch.cuda.is_available())"` 验证 CUDA，并使用 GPU

**问题：不现实的 binding poses**
- 原因：protein preparation 差、ligand 过大、binding site 错误
- 解决方案：检查 protein 是否缺失 residues，移除远离位点的 waters，考虑指定 binding site

**问题："Module not found" 错误**
- 原因：缺少依赖项或环境错误
- 解决方案：运行 `python scripts/setup_check.py` 诊断

### 性能优化

**为了获得最佳结果：**
1. 使用 GPU（实际使用时基本必需）
2. 对重复使用的 protein 预计算 ESM embeddings
3. 将多个 complexes 一起批量处理
4. 从默认参数开始，然后按需要调优
5. 验证 protein structures（解决缺失 residues）
6. 对 ligands 使用 canonical SMILES

## 图形用户界面

如需交互式使用，启动 Web 界面：

```bash
python app/main.py
# Navigate to http://localhost:7860
```

也可以使用无需安装的在线 demo：
- https://huggingface.co/spaces/reginabarzilaygroup/DiffDock-Web

## 资源

### Helper Scripts (`scripts/`)

**`prepare_batch_csv.py`**：创建并验证 batch input CSV 文件
- 创建带示例条目的模板
- 验证文件路径和 SMILES 字符串
- 检查必需列和格式问题

**`analyze_results.py`**：分析 confidence scores 并对预测排序
- 解析单次或批量运行的结果
- 生成统计摘要
- 导出到 CSV 供下游分析
- 识别跨 complexes 的 top predictions

**`setup_check.py`**：验证 DiffDock 环境设置
- 检查 Python 版本和依赖项
- 验证 PyTorch 和 CUDA 可用性
- 测试 RDKit 和 PyTorch Geometric 安装
- 必要时提供安装说明

### 参考文档 (`references/`)

**`parameters_reference.md`**：完整参数文档
- 所有命令行选项和配置参数
- 默认值和可接受范围
- 用于控制多样性的 temperature 参数
- 模型 checkpoint 位置和版本 flags

当用户需要以下内容时阅读此文件：
- 详细参数说明
- 面向特定系统的 fine-tuning 指南
- 替代采样策略

**`confidence_and_limitations.md`**：Confidence score 解读和工具局限性
- 详细 confidence score 解读
- 何时信任预测
- DiffDock 的适用范围和局限性
- 与互补工具集成
- 预测质量故障排除

当用户需要以下内容时阅读此文件：
- 解读 confidence scores 的帮助
- 理解何时不应使用 DiffDock
- 与其他工具结合的指导
- 验证策略

**`workflows_examples.md`**：全面工作流示例
- 详细安装说明
- 所有工作流的分步示例
- 高级集成模式
- 常见问题故障排除
- 最佳实践和优化提示

当用户需要以下内容时阅读此文件：
- 带代码的完整工作流示例
- 与 GNINA、OpenMM 或其他工具集成
- Virtual screening workflows
- Ensemble docking procedures

### Assets (`assets/`)

**`batch_template.csv`**：批量处理模板
- 带必需列的预格式化 CSV
- 展示不同输入类型的示例条目
- 可直接用实际数据定制

**`custom_inference_config.yaml`**：配置模板
- 带所有参数注释的 YAML
- 四个常见使用场景的 preset configurations
- 解释每个参数的详细注释
- 可直接定制和使用

## 最佳实践

1. 开始大型任务前，始终用 `setup_check.py` **验证环境**
2. 用 `prepare_batch_csv.py` **验证 batch CSVs**，及早捕获错误
3. **从默认值开始**，再根据系统特定需要调优参数
4. **生成多个 samples**（10-40）以获得稳健预测
5. 下游分析前，对 top poses 做**视觉检查**
6. 结合 **scoring functions** 做 affinity assessment
7. 将 **confidence scores** 用于初始排序，而不是最终决策
8. 为 virtual screening campaigns **预计算 embeddings**
9. **记录使用的参数**以保证可复现性
10. 可能时进行**实验验证**

## 引用

使用 DiffDock 时，请引用相应论文：

**DiffDock-L（当前默认模型）：**
```
Stärk et al. (2024) "DiffDock-L: Improving Molecular Docking with Diffusion Models"
arXiv:2402.18396
```

**原始 DiffDock：**
```
Corso et al. (2023) "DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking"
ICLR 2023, arXiv:2210.01776
```

## 其他资源

- **GitHub Repository**: https://github.com/gcorso/DiffDock
- **Online Demo**: https://huggingface.co/spaces/reginabarzilaygroup/DiffDock-Web
- **DiffDock-L Paper**: https://arxiv.org/abs/2402.18396
- **Original Paper**: https://arxiv.org/abs/2210.01776
