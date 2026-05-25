---
name: rowan
description: Rowan 是一个 cloud-native molecular modeling 和 medicinal-chemistry workflow platform，提供 Python API。用于 pKa 和 macropKa prediction、conformer 和 tautomer ensembles、docking 和 analogue docking、protein-ligand cofolding、MSA generation、molecular dynamics、permeability、descriptor workflows，以及相关 small-molecule 或 protein modeling tasks。适合 programmatic batch screening、multi-step chemistry pipelines，以及原本需要维护本地 HPC/GPU infrastructure 的 workflows。
license: Proprietary (API key required)
compatibility: Python 3.12+, API key required
metadata:
  skill-author: Rowan Science
  trigger-keywords: ["pKa prediction", "molecular docking", "conformer search", "chemistry workflow", "drug discovery", "SMILES", "protein structure", "batch molecular modeling", "cloud chemistry"]
---

# Rowan: Cloud-Native Molecular-Modeling and Drug-Design Workflows

## 概述

Rowan 是一个用于 molecular simulation、medicinal chemistry 和 structure-based design 的 cloud-native workflow platform。其 Python API 为 small-molecule modeling、property prediction、docking、molecular dynamics 和 AI structure workflows 提供统一接口。

当你希望以编程方式运行 medicinal-chemistry 或 molecular-design workflows，而不想维护本地 HPC infrastructure、GPU provisioning 或一组独立 modeling tools 时，使用 Rowan。Rowan 负责所有 infrastructure、result management 和 computation scaling。

## 何时使用 Rowan

**Rowan 适合：**

- Quantum chemistry、semiempirical methods 或 neural network potentials
- Batch property prediction（pKa、descriptors、permeability、solubility）
- Conformer 和 tautomer ensemble generation
- Docking workflows（single-ligand、analogue series、pose refinement）
- Protein-ligand cofolding 和 MSA generation
- Multi-step chemistry pipelines（例如 tautomer search → docking → pose analysis）
- 需要一致、可扩展 infrastructure 的 batch medicinal-chemistry campaigns

**Rowan 不适合：**
- 简单 molecular I/O（直接使用 RDKit）
- Post-HF *ab initio* quantum chemistry 或 relativistic calculations

## Access and pricing model

Rowan 使用 credit-based usage model。所有用户（包括 free-tier users）都可以创建 API keys 并使用 Python API。

### Free-tier access

- 访问所有 Rowan core workflows
- 每周 20 credits
- 500 signup credits

### Pricing and credit consumption

Credits 按 compute type 消耗：

- **CPU**：每分钟 1 credit
- **GPU**：每分钟 3 credits
- **H100/H200 GPU**：每分钟 7 credits

购买的 credits 按 credit 计价，并从购买起最长一年内有效。

### Typical cost estimates

| Workflow | Typical Runtime | Estimated Credits | Notes |
|----------|----------------|-------------------|-------|
| Descriptors | <1 min | 0.5–2 | 轻量，适合 triage |
| pKa (single transition) | 2–5 min | 2–5 | 取决于 molecule size |
| MacropKa (pH 0–14) | 5–15 min | 5–15 | 采样更广，成本更高 |
| Conformer search | 3–10 min | 3–10 | Ensemble quality 很重要 |
| Tautomer search | 2–5 min | 2–5 | Heterocyclic systems |
| Docking (single ligand) | 5–20 min | 5–20 | 取决于 pocket size 和 refinement |
| Analogue docking series (10–50 ligands) | 30–120 min | 30–100+ | Shared reference frame |
| MSA generation | 5–30 min | 5–30 | 取决于 sequence length |
| Protein-ligand cofolding | 15–60 min | 20–50+ | AI structure prediction，GPU-heavy |

## 快速开始

```bash
uv pip install rowan-python
```

```python
import rowan
rowan.api_key = "your_api_key_here"  # or set ROWAN_API_KEY env var

# Submit a descriptors workflow — completes in under a minute
wf = rowan.submit_descriptors_workflow("CC(=O)Oc1ccccc1C(=O)O", name="aspirin")
result = wf.result()

print(result.descriptors['MW'])    # 180.16
print(result.descriptors['SLogP']) # 1.19
print(result.descriptors['TPSA'])  # 59.44
```

如果能够无错误打印结果，说明已正确设置。

## 安装

```bash
uv pip install rowan-python
# or: pip install rowan-python
```

## User and webhook management

### Authentication

通过环境变量设置 API key（推荐）：

```bash
export ROWAN_API_KEY="your_api_key_here"
```

或在 Python 中直接设置：

```python
import rowan
rowan.api_key = "your_api_key_here"
```

验证 authentication：

```python
import rowan
user = rowan.whoami()  # Returns user info if authenticated
print(f"User: {user.email}")
print(f"Credits available: {user.credits_available_string}")
```

### Webhook secret management

如需 webhook signature verification，通过用户账户管理 secrets：

```python
import rowan

# Get your current webhook secret (returns None if none exists)
secret = rowan.get_webhook_secret()
if secret is None:
    secret = rowan.create_webhook_secret()
print(f"Secret key: {secret.secret}")

# Rotate your secret (invalidates old, creates new)
# Use this periodically for security
new_secret = rowan.rotate_webhook_secret()
print(f"New secret created (old secret disabled): {new_secret.secret}")

# Verify incoming webhook signatures
is_valid = rowan.verify_webhook_secret(
    request_body=b"...",           # Raw request body (bytes)
    signature="X-Rowan-Signature", # From request header
    secret=secret.secret
)
```

## Molecule input formats

Rowan 接受以下格式的 molecules：

- **SMILES**（首选）：`"CCO"`、`"c1ccccc1O"`
- **SMARTS patterns**（用于部分 workflows）：用于 substructure matching 的 SMARTS 子集
- **InChI**（如果你的 API version 支持）：`"InChI=1S/C2H6O/c1-2-3/h3H,2H2,1H3"`

API 会验证输入，并在 molecule 无法解析时抛出 `rowan.ValidationError`。始终使用 canonicalized SMILES 以保证 reproducibility。

**提示：** 提交前使用 RDKit 验证 SMILES：

```python
from rdkit import Chem
smiles = "CCO"
mol = Chem.MolFromSmiles(smiles)
if mol is None:
    raise ValueError(f"Invalid SMILES: {smiles}")
```

## Core usage pattern

大多数 Rowan tasks 遵循相同的三步模式：

1. **Submit** 一个 workflow
2. **Wait** 到完成（可选 streaming）
3. **Retrieve** 带 convenience properties 的 typed results

```python
import rowan

# 1. Submit — use the specific workflow function (not the generic submit_workflow)
workflow = rowan.submit_descriptors_workflow(
    "CC(=O)Oc1ccccc1C(=O)O",
    name="aspirin descriptors",
)

# 2. & 3. Wait and retrieve
result = workflow.result()  # Blocks until done (default: wait=True, poll_interval=5)
print(result.data)              # Raw dict
print(result.descriptors['MW']) # 180.16 — use result.descriptors dict, not result.molecular_weight
```

对于 long-running workflows，使用 streaming：

```python
for partial in workflow.stream_result(poll_interval=5):
    print(f"Progress: {partial.complete}%")
    print(partial.data)
```

### result() vs. stream_result()

| Pattern | Use When | Duration |
|---------|----------|----------|
| `result()` | 可以等待完整 result | 通常 <5 min |
| `stream_result()` | 需要 progress feedback 或 early partial results | >5 min，或 interactive use |

**指南：** descriptors、pKa 使用 `result()`。conformer search、docking、cofolding 使用 `stream_result()`。

## Working with results

Rowan 的 API 包含带 convenience properties 的 **typed workflow result objects**。

### 使用 typed properties 和 .data

Results 有两种访问模式：

1. **Convenience properties**（优先推荐）：`result.descriptors`、`result.best_pose`、`result.conformer_energies`
2. **Raw fallback**：`result.data` — API 返回的原始 dictionary

示例：

```python
result = rowan.submit_descriptors_workflow(
    "CCO",
    name="ethanol",
).result()

# Convenience property (returns dict of all descriptors):
print(result.descriptors['MW'])   # 46.042
print(result.descriptors['SLogP'])  # -0.001
print(result.descriptors['TPSA'])   # 57.96

# Raw data fallback (descriptors are nested under 'descriptors' key):
print(result.data['descriptors'])
# {'MW': 46.042, 'SLogP': -0.001, 'TPSA': 57.96, 'nHBDon': 1.0, 'nHBAcc': 1.0, ...}
```

**注意：** `DescriptorsResult` 没有 `molecular_weight` property。Descriptor keys 使用 short names（`MW`、`SLogP`、`nHBDon`），不是 verbose names。

### Cache invalidation

部分 result properties 会 lazy loaded（例如 conformer geometries、protein structures）。刷新方式：

```python
result.clear_cache()
new_structures = result.conformer_molecules  # Refetched
```

## Projects, folders, and organization

对于非平凡 campaigns，使用 projects 和 folders 保持工作有序。

### Projects

```python
import rowan

# Create a project
project = rowan.create_project(name="CDK2 lead optimization")
rowan.set_project("CDK2 lead optimization")

# All subsequent workflows go into this project
wf = rowan.submit_descriptors_workflow("CCO", name="test compound")

# Retrieve later
project = rowan.retrieve_project("CDK2 lead optimization")
workflows = rowan.list_workflows(project=project, size=50)
```

### Folders

```python
# Create a hierarchical folder structure
folder = rowan.create_folder(name="docking/batch_1/screening")

wf = rowan.submit_docking_workflow(
    # ... docking params ...
    folder=folder,
    name="compound_001",
)

# List workflows in a folder
results = rowan.list_workflows(folder=folder)
```

## Workflow decision trees

### pKa vs. MacropKa

**在以下情况使用 microscopic pKa：**

- 需要单个 ionizable group 的 pKa
- 关注 acid–base transitions 和 protonation thermodynamics
- Molecule 有一个或两个 ionizable sites
- Speed 很关键（更快、credits 更少）

**在以下情况使用 macropKa：**

- 需要跨 physiologically relevant range（例如 0–14）的 pH-dependent behavior
- 希望获得跨 pH 的 aggregated charge 和 protonation-state populations
- Molecule 有多个 coupled protonation 的 ionizable groups
- 需要不同 pH 下的 aqueous solubility 等 downstream properties

**Example decision：**

```text
Phenol (pKa ~10): Use microscopic pKa
Amine (pKa ~9–10): Use microscopic pKa
Multi-ionizable drug (N, O, acidic group): Use macropKa
ADME assessment across GI pH: Use macropKa
```

### Conformer search vs. tautomer search

**在以下情况使用 conformer search：**

- 已知 single tautomeric form
- 需要用于 docking、MD 或 SAR analysis 的 diverse 3D ensemble
- Rotatable bonds 主导 chemical space

**在以下情况使用 tautomer search：**

- Tautomeric equilibrium 不确定（例如 heterocycles、keto–enol systems）
- 需要模拟所有相关 protonation isomers
- Downstream calculations（docking、pKa）依赖 tautomeric form

**Combined workflow：**

```python
# Step 1: Find best tautomer
taut_wf = rowan.submit_tautomer_search_workflow(
    initial_molecule="O=c1[nH]ccnc1",
    name="imidazole tautomers",
)
best_taut = taut_wf.result().best_tautomer

# Step 2: Generate conformers from best tautomer
conf_wf = rowan.submit_conformer_search_workflow(
    initial_molecule=best_taut,
    name="imidazole conformers",
)
```

### Docking vs. analogue docking vs. cofolding

| Workflow | Use When | Input | Output |
|----------|----------|-------|--------|
| Docking | Single ligand，known pocket | Protein + SMILES + pocket coords | Pose, score, dG |
| Analogue docking | 5–100+ related compounds | Protein + SMILES list + reference ligand | All poses, reference-aligned |
| Protein-ligand cofolding | Sequence + ligand，无 crystal structure | Protein sequence + SMILES | ML-predicted bound complex |

## 常见 workflow categories

### 1. Descriptors

用于 batch triage、SAR 或 exploratory scripts 的轻量入口点。

```python
wf = rowan.submit_descriptors_workflow(
    "CC(=O)Oc1ccccc1C(=O)O",  # positional arg, accepts SMILES string
    name="aspirin descriptors",
)

result = wf.result()
print(result.descriptors['MW'])    # 180.16
print(result.descriptors['SLogP']) # 1.19
print(result.descriptors['TPSA'])  # 59.44
print(result.data['descriptors'])
# {'MW': 180.16, 'SLogP': 1.19, 'TPSA': 59.44, 'nHBDon': 1.0, 'nHBAcc': 4.0, ...}
```

**Common descriptor keys：**

| Key | Description | Typical drug range |
|-----|-------------|-------------------|
| `MW` | Molecular weight (Da) | <500 (Lipinski) |
| `SLogP` | Calculated LogP (lipophilicity) | -2 to +5 |
| `TPSA` | Topological polar surface area (Å²) | <140 for oral bioavailability |
| `nHBDon` | H-bond donor count | ≤5 (Lipinski) |
| `nHBAcc` | H-bond acceptor count | ≤10 (Lipinski) |
| `nRot` | Rotatable bond count | <10 for oral drugs |
| `nRing` | Ring count | — |
| `nHeavyAtom` | Heavy atom count | — |
| `FilterItLogS` | Estimated aqueous solubility (LogS) | >-4 preferred |
| `Lipinski` | Lipinski Ro5 pass (1.0) or fail (0.0) | — |

Result 包含数百个 additional molecular descriptors（BCUT、GETAWAY、WHIM 等）；通过 `result.descriptors['key']` 访问任意 descriptor。

### 2. Microscopic pKa

用于特定结构的 protonation-state energetics 和 acid/base behavior。

可用两种方法：

| Method | Input | Speed | Covers | Use when |
|--------|-------|-------|--------|----------|
| `chemprop_nevolianis2025` | SMILES string | Fast | Deprotonation only (anionic conjugate bases) | 仅 acidic groups；quick screening |
| `starling` | SMILES string | Fast | Acid + base (full protonation/deprotonation) | 大多数 drug-like molecules；首选 SMILES method |
| `aimnet2_wagen2024` (default) | 3D molecule object | Slower, higher accuracy | Acid + base | 已有 3D structure（例如来自 conformer search） |

```python
# Fast path: SMILES input with full acid+base coverage (use starling method when available)
wf = rowan.submit_pka_workflow(
    initial_molecule="c1ccccc1O",       # phenol SMILES; param is initial_molecule, not initial_smiles
    method="starling",   # fast SMILES method, covers acid+base; chemprop_nevolianis2025 is deprotonation-only
    name="phenol pKa",
)

result = wf.result()
print(result.strongest_acid)    # 9.81 (pKa of the most acidic site)
print(result.conjugate_bases)   # list of {pka, smiles, atom_index, ...} per deprotonatable site
```

### 3. MacropKa

用于一定范围内的 pH-dependent protonation behavior。

```python
wf = rowan.submit_macropka_workflow(
    initial_smiles="CN1CCN(CC1)C2=NC=NC3=CC=CC=C32",  # imidazole
    min_pH=0,
    max_pH=14,
    min_charge=-2,  # default
    max_charge=2,   # default
    compute_aqueous_solubility=True,  # default
    name="imidazole macropKa",
)

result = wf.result()
print(result.pka_values)               # list of pKa values
print(result.logd_by_ph)               # dict of {pH: logD}
print(result.aqueous_solubility_by_ph) # dict of {pH: solubility}
print(result.isoelectric_point)        # isoelectric point
print(result.data)
# {'pKa_values': [...], 'logD_by_pH': {...}, 'aqueous_solubility_by_pH': {...}, ...}
```

### 4. Conformer search

用于 ensemble quality 重要时的 3D ensemble generation。

```python
wf = rowan.submit_conformer_search_workflow(
    initial_molecule="CCOC(=O)N1CCC(CC1)Oc1ncnc2ccccc12",
    num_conformers=50,  # Optional: override default
    name="conformer search",
)

result = wf.result()
print(result.conformer_energies)  # [0.0, 1.2, 2.5, ...]
print(result.conformer_molecules)  # List of 3D molecules
print(result.best_conformer)  # Lowest-energy conformer
```

### 5. Tautomer search

用于 tautomer state 会影响 downstream modeling 的 heterocycles 和系统。

```python
wf = rowan.submit_tautomer_search_workflow(
    initial_molecule="O=c1[nH]ccnc1",  # or keto tautomer
    name="imidazolone tautomers",
)

result = wf.result()
print(result.best_tautomer)  # Most stable SMILES string
print(result.tautomers)      # List of tautomeric SMILES
print(result.molecules)      # List of molecule objects
```

### 6. Docking

用于 protein-ligand docking，可选 pose refinement 和 conformer generation。

```python
# Upload protein once, reuse in multiple workflows
protein = rowan.upload_protein(
    name="CDK2",
    file_path="cdk2.pdb",
)

# Define binding pocket
pocket = {
    "center": [10.5, 24.2, 31.8],
    "size": [18.0, 18.0, 18.0],
}

# Submit docking
wf = rowan.submit_docking_workflow(
    protein=protein,
    pocket=pocket,
    initial_molecule="CCNc1ncc(c(Nc2ccc(F)cc2)n1)-c1cccnc1",
    do_pose_refinement=True,
    do_conformer_search=True,
    name="lead docking",
)

result = wf.result()
print(result.scores)  # Docking scores (kcal/mol)
print(result.best_pose)  # Mol object with 3D coordinates
print(result.data)  # Raw result dict
```

**Protein preparation tips：**

- PDB files 应相当干净（除非有意保留，否则移除 water/heteroatoms）
- 在 docking series 中复用同一 protein object 以保持一致
- 如果有 PDB ID，改用 `rowan.create_protein_from_pdb_id()`

### 7. Analogue docking

用于将 compound series 放入共享 binding context。

```python
# Analogue series (e.g., SAR campaign)
analogues = [
    "CCNc1ncc(c(Nc2ccc(F)cc2)n1)-c1cccnc1",    # reference
    "CCNc1ncc(c(Nc2ccc(Cl)cc2)n1)-c1cccnc1",   # chloro
    "CCNc1ncc(c(Nc2ccc(OC)cc2)n1)-c1cccnc1",   # methoxy
    "CCNc1ncc(c(Nc2cc(C)c(F)cc2)n1)-c1cccnc1", # methyl, fluoro
]

wf = rowan.submit_analogue_docking_workflow(
    analogues=analogues,
    initial_molecule=analogues[0],  # Reference ligand
    protein=protein,
    pocket=pocket,
    name="SAR series docking",
)

result = wf.result()
print(result.analogue_scores)  # List of scores for each analogue
print(result.best_poses)  # List of poses
```

### 8. MSA generation

用于 multiple-sequence alignment（对 downstream cofolding 有用）。

```python
wf = rowan.submit_msa_workflow(
    initial_protein_sequences=[
        "MENFQKVEKIGEGTYGVVYKARNKLTGEVVALKKIRLDTETEGVP"
    ],
    output_formats=["colabfold", "chai", "boltz"],
    name="target MSA",
)

result = wf.result()
result.download_files()  # Downloads alignments to disk
```

### 9. Protein-ligand cofolding

用于没有 crystal structure 时基于 AI 的 bound-complex prediction。

```python
wf = rowan.submit_protein_cofolding_workflow(
    initial_protein_sequences=[
        "MENFQKVEKIGEGTYGVVYKARNKLTGEVVALKKIRLDTETEGVP"
    ],
    initial_smiles_list=[
        "CCNc1ncc(c(Nc2ccc(F)cc2)n1)-c1cccnc1"
    ],
    name="protein-ligand cofolding",
)

result = wf.result()
print(result.predictions)  # List of predicted structures
print(result.messages)  # Model metadata/warnings

predicted_structure = result.get_predicted_structure()
predicted_structure.write("predicted_complex.pdb")
```

## All supported workflow types

所有 workflows 都遵循 submit → wait → retrieve 模式，并支持 webhooks 和 project/folder organization。

### Core molecular modeling workflows

| Workflow | Function | When to use |
|----------|----------|-------------|
| Descriptors | `submit_descriptors_workflow` | First-pass triage：MW、LogP、TPSA、HBA/HBD、Lipinski filter |
| pKa | `submit_pka_workflow` | Single ionizable group；需要 protonation thermodynamics |
| MacropKa | `submit_macropka_workflow` | Multi-ionizable drugs；pH-dependent charge/LogD/solubility |
| Conformer Search | `submit_conformer_search_workflow` | 用于 docking、MD 或 SAR 的 3D ensemble；known tautomer |
| Tautomer Search | `submit_tautomer_search_workflow` | Heterocycles、keto–enol；tautomeric form 不确定 |
| Solubility | `submit_solubility_workflow` | Aqueous 或 solvent-specific solubility prediction |
| Membrane Permeability | `submit_membrane_permeability_workflow` | Caco-2、PAMPA、BBB、plasma permeability |
| ADMET | `submit_admet_workflow` | Broad drug-likeness 和 ADMET property sweep |

### Structure-based design workflows

| Workflow | Function | When to use |
|----------|----------|-------------|
| Docking | `submit_docking_workflow` | Single ligand，known binding pocket |
| Analogue Docking | `submit_analogue_docking_workflow` | Shared pocket 中的 SAR series（5–100+ compounds） |
| Batch Docking | `submit_batch_docking_workflow` | Fast library screening；large compound sets |
| Protein MD | `submit_protein_md_workflow` | Long-timescale dynamics；conformational sampling |
| Pose Analysis MD | `submit_pose_analysis_md_workflow` | Docking pose 的 MD refinement |
| Protein Cofolding | `submit_protein_cofolding_workflow` | 无 crystal structure；AI-predicted bound complex |
| Protein Binder Design | `submit_protein_binder_design_workflow` | 针对 protein target 的 de novo binder generation |

### Advanced computational chemistry

| Workflow | Function | When to use |
|----------|----------|-------------|
| Basic Calculation | `submit_basic_calculation_workflow` | QM/ML geometry optimization 或 single-point energy |
| Electronic Properties | `submit_electronic_properties_workflow` | Dipole、partial charges、HOMO-LUMO、ESP |
| BDE | `submit_bde_workflow` | Bond dissociation energies；metabolic soft-spot prediction |
| Redox Potential | `submit_redox_potential_workflow` | Oxidation/reduction potentials |
| Spin States | `submit_spin_states_workflow` | Organometallics/radicals 的 spin-state energy ordering |
| Strain | `submit_strain_workflow` | 相对于 global minimum 的 conformational strain |
| Scan | `submit_scan_workflow` | PES scans；torsion profiles |
| Multistage Optimization | `submit_multistage_opt_workflow` | 跨 levels of theory 的 progressive optimization |

### Reaction chemistry

| Workflow | Function | When to use |
|----------|----------|-------------|
| Double-Ended TS Search | `submit_double_ended_ts_search_workflow` | 两个已知 structures 之间的 transition state |
| IRC | `submit_irc_workflow` | 确认 TS connectivity；intrinsic reaction coordinate |

### Advanced properties

| Workflow | Function | When to use |
|----------|----------|-------------|
| NMR | `submit_nmr_workflow` | 用于 structure verification 的 predicted 1H/13C chemical shifts |
| Ion Mobility | `submit_ion_mobility_workflow` | MS method development 的 collision cross-section（CCS） |
| Hydrogen Bond Strength | `submit_hydrogen_bond_basicity_workflow` | Formulation/solubility 的 H-bond donor/acceptor strength |
| Fukui | `submit_fukui_workflow` | Electrophilic/nucleophilic attack 的 site reactivity indices |
| Interaction Energy Decomposition | `submit_interaction_energy_decomposition_workflow` | Fragment-level interaction analysis |

### Binding free energy

| Workflow | Function | When to use |
|----------|----------|-------------|
| RBFE/FEP | `submit_relative_binding_free_energy_perturbation_workflow` | Congeneric series 的 relative ΔΔG |
| RBFE Graph | `submit_rbfe_graph_workflow` | 构建并优化 RBFE perturbation network |

### Sequence and structural biology

| Workflow | Function | When to use |
|----------|----------|-------------|
| MSA | `submit_msa_workflow` | 用于 cofolding 的 multiple sequence alignment（ColabFold、Chai、Boltz） |
| Solvent-Dependent Conformers | `submit_solvent_dependent_conformers_workflow` | Solvation-aware conformer ensembles |

## Batch submission and retrieval

对于 libraries 或 analogue series，使用具体 workflow function 在 loop 中提交。通用的 `rowan.batch_submit_workflow()` 和 `rowan.submit_workflow()` functions 当前会从 API 返回 422 errors；请改用 named functions（`submit_descriptors_workflow`、`submit_pka_workflow` 等）。

### Submit a batch

```python
smileses = ["CCO", "CC(=O)O", "c1ccccc1O"]
names = ["ethanol", "acetic acid", "phenol"]

workflows = [
    rowan.submit_descriptors_workflow(smi, name=name)
    for smi, name in zip(smileses, names)
]

print(f"Submitted {len(workflows)} workflows")
```

### Poll batch status

```python
statuses = rowan.batch_poll_status([wf.uuid for wf in workflows])
# Returns aggregate counts — not per-UUID:
# {'queued': 0, 'running': 1, 'complete': 2, 'failed': 0, 'total': 3, ...}

if statuses["complete"] == statuses["total"]:
    print("All workflows done")
elif statuses["failed"] > 0:
    print(f"{statuses['failed']} workflows failed")
```

### Retrieve and collect results

```python
results = []
for wf in workflows:
    try:
        result = wf.result()
        results.append(result.data)
    except rowan.WorkflowError as e:
        print(f"Workflow {wf.uuid} failed: {e}")

# Optionally aggregate into DataFrame
import pandas as pd
df = pd.DataFrame(results)
```

### Non-blocking / fire-and-check pattern

对于不想保持进程开启的 long-running workflows，提交 workflows、保存 UUIDs，并稍后在单独进程中检查。

**Session 1 — submit and save UUIDs：**

```python
import rowan, json

rowan.api_key = "..."
smileses = ["CCO", "CC(=O)O", "c1ccccc1O"]

workflows = [
    rowan.submit_descriptors_workflow(smi, name=f"compound_{i}")
    for i, smi in enumerate(smileses)
]

# Save UUIDs to disk (or a database)
uuids = [wf.uuid for wf in workflows]
with open("workflow_uuids.json", "w") as f:
    json.dump(uuids, f)

print("Submitted. Check back later.")
```

**Session 2 — check status and collect results when ready：**

```python
import rowan, json

rowan.api_key = "..."

with open("workflow_uuids.json") as f:
    uuids = json.load(f)

results = []
for uuid in uuids:
    wf = rowan.retrieve_workflow(uuid)
    if wf.done():
        result = wf.result(wait=False)
        results.append({"uuid": uuid, "data": result.data})
    else:
        print(f"{uuid}: still running ({wf.status})")

print(f"Collected {len(results)} completed results")
```

## Webhooks and asynchronous workflows

对于 long-running campaigns 或不想保持进程存活的场景，使用 webhooks 在 workflows 完成时通知你的 backend。

### Setting up webhooks

每个 workflow submission function 都接受 `webhook_url` 参数：

```python
wf = rowan.submit_docking_workflow(
    protein=protein,
    pocket=pocket,
    initial_molecule="CCO",
    webhook_url="https://myserver.com/rowan_callback",
    name="docking with webhook",
)

print(f"Workflow submitted. Result will be POSTed to webhook when complete.")
```

Webhook URLs 可传给任何 specific workflow function（`submit_docking_workflow()`、`submit_pka_workflow()`、`submit_descriptors_workflow()` 等）。

### Webhook authentication with secrets

Rowan 支持 webhook signature verification 以确保请求真实。你需要：

1. **创建或检索 webhook secret：**

```python
import rowan

# Create a new webhook secret
secret = rowan.create_webhook_secret()
print(f"Your webhook secret: {secret.secret}")

# Or retrieve an existing secret
secret = rowan.get_webhook_secret()

# Rotate your secret (invalidates old one, creates new)
new_secret = rowan.rotate_webhook_secret()
```

2. **验证 incoming webhook requests：**

```python
import rowan
import hmac
import json

def verify_webhook(request_body: bytes, signature: str, secret: str) -> bool:
    """Verify the HMAC-SHA256 signature of a webhook request."""
    return rowan.verify_webhook_secret(request_body, signature, secret)
```

### Webhook payload and signature

当 workflow 完成时，Rowan 会向你的 webhook URL POST 一个 JSON payload，并带有以下 header：

```text
X-Rowan-Signature: <HMAC-SHA256 signature>
```

Request body 包含完整 workflow result：

```json
{
  "workflow_uuid": "wf_12345abc",
  "workflow_type": "docking",
  "workflow_name": "lead docking",
  "status": "COMPLETED_OK",
  "created_at": "2025-04-01T12:00:00Z",
  "completed_at": "2025-04-01T12:15:30Z",
  "data": {
    "scores": [-8.2, -8.0, -7.9],
    "best_pose": {...},
    "metadata": {...}
  }
}
```

### 带 signature verification 的 webhook handler 示例（FastAPI）

```python
from fastapi import FastAPI, Request, HTTPException
import rowan
import json

app = FastAPI()
_ws = rowan.get_webhook_secret() or rowan.create_webhook_secret()
webhook_secret = _ws.secret

@app.post("/rowan_callback")
async def handle_rowan_webhook(request: Request):
    # Get request body and signature
    body = await request.body()
    signature = request.headers.get("X-Rowan-Signature")

    if not signature:
        raise HTTPException(status_code=400, detail="Missing X-Rowan-Signature header")

    # Verify signature
    if not rowan.verify_webhook_secret(body, signature, webhook_secret):
        raise HTTPException(status_code=401, detail="Invalid webhook signature")

    # Parse and process
    payload = json.loads(body)
    wf_uuid = payload["workflow_uuid"]
    status = payload["status"]

    if status == "COMPLETED_OK":
        print(f"Workflow {wf_uuid} succeeded!")
        result_data = payload["data"]
        # Process result, update database, trigger next workflow, etc.
    elif status == "FAILED":
        print(f"Workflow {wf_uuid} failed!")
        # Handle failure

    # Respond quickly to prevent retries
    return {"status": "received"}
```

### Webhook best practices

- **始终验证 signatures**，使用 `rowan.verify_webhook_secret()` 确保请求来自 Rowan
- **快速响应**（< 5 秒）；将 heavy processing offload 到 async tasks 或 background jobs
- **实现 idempotency**：workflows 可能 retry；使用 `workflow_uuid` 优雅处理 duplicate payloads
- **记录所有 events**，用于 debugging 和 audit trails
- **用于 long campaigns**：webhooks 在 50+ workflows 时优势明显；小 jobs 用 `result()` polling 更简单
- **定期 rotate secrets**，使用 `rowan.rotate_webhook_secret()` 提高安全性
- **返回 2xx status** 确认接收；Rowan 可能在 5xx errors 时 retry

## Protein utilities

### Upload proteins

```python
# From local PDB file
protein = rowan.upload_protein(
    name="egfr_kinase_domain",
    file_path="egfr_kinase.pdb",
)

# From PDB database
protein_from_pdb = rowan.create_protein_from_pdb_id(
    name="CDK2 (1M17)",
    code="1M17",
)

# Retrieve previously uploaded protein
protein = rowan.retrieve_protein("protein-uuid")

# List all proteins
my_proteins = rowan.list_proteins()
```

### Protein preparation guidance

- **File format**：PDB、mmCIF（Rowan 自动检测）
- **Water molecules**：Rowan 通常会保留相关 water；如有需要可预先移除 bulk water
- **Heteroatoms**：Cofactors、ions 和 bound ligands 通常会保留；上传前移除不需要的 heteroatoms
- **Multi-chain proteins**：完全支持
- **Resolution**：可处理 NMR structures、homology models 和 cryo-EM；quality 会影响 downstream predictions
- **Validation**：Rowan 验证 PDB syntax；严重 malformed files 可能被拒绝

## End-to-end example: Lead optimization campaign

此示例展示优化 hit compound 的 realistic workflow：

```python
import rowan
import pandas as pd

# 1. Create a project and folder for organization
project = rowan.create_project(name="CDK2 Hit Optimization")
rowan.set_project("CDK2 Hit Optimization")
folder = rowan.create_folder(name="round_1_tautomers_and_pka")

# 2. Load hit compound and analogues
hit = "CCNc1ncc(c(Nc2ccc(F)cc2)n1)-c1cccnc1"  # Known hit
analogues = [
    "CCNc1ncc(c(Nc2ccccc2)n1)-c1cccnc1",      # Remove F
    "CCNc1ncc(c(Nc2ccc(Cl)cc2)n1)-c1cccnc1",  # Cl instead of F
    "CCC(C)Nc1ncc(c(Nc2ccc(F)cc2)n1)-c1cccnc1",  # Propyl instead of ethyl
]

# 3. Determine best tautomers (just in case)
print("Searching tautomeric forms...")
taut_workflows = [
    rowan.submit_tautomer_search_workflow(
        smi, name=f"analog_{i}", folder=folder,
    )
    for i, smi in enumerate(analogues)
]

best_tautomers = []
for wf in taut_workflows:
    result = wf.result()
    best_tautomers.append(result.best_tautomer)

# 4. Predict pKa and basic properties for all analogues
print("Predicting pKa and properties...")
pka_workflows = [
    rowan.submit_pka_workflow(
        smi, method="chemprop_nevolianis2025", name=f"pka_{i}", folder=folder,
    )
    for i, smi in enumerate(best_tautomers)
]

descriptor_workflows = [
    rowan.submit_descriptors_workflow(smi, name=f"desc_{i}", folder=folder)
    for i, smi in enumerate(best_tautomers)
]

# 5. Collect results
pka_results = []
for wf in pka_workflows:
    try:
        result = wf.result()
        pka_results.append({
            "compound": wf.name,
            "pka": result.strongest_acid,  # pKa of the strongest acid site
            "uuid": wf.uuid,
        })
    except rowan.WorkflowError as e:
        print(f"pKa prediction failed for {wf.name}: {e}")

descriptor_results = []
for wf in descriptor_workflows:
    try:
        result = wf.result()
        desc = result.descriptors
        descriptor_results.append({
            "compound": wf.name,
            "mw": desc.get("MW"),
            "logp": desc.get("SLogP"),
            "hba": desc.get("nHBAcc"),
            "hbd": desc.get("nHBDon"),
            "uuid": wf.uuid,
        })
    except rowan.WorkflowError as e:
        print(f"Descriptor calculation failed for {wf.name}: {e}")

# 6. Merge and summarize
df_pka = pd.DataFrame(pka_results)
df_desc = pd.DataFrame(descriptor_results)
df = df_pka.merge(df_desc, on="compound", how="outer")

print("\n=== Preliminary SAR ===")
print(df.to_string())

# 7. Select promising compound for docking
# compound names are "pka_0", "pka_1", etc. — extract index to look up SMILES
top_idx = int(df.loc[df["pka"].idxmin(), "compound"].split("_")[1])
top_smiles = best_tautomers[top_idx]

print(f"\nProceeding with docking: {top_smiles}")

# 8. Docking campaign
protein = rowan.create_protein_from_pdb_id(name="CDK2_1CKP", code="1CKP")
pocket = {"center": [10.5, 24.2, 31.8], "size": [18.0, 18.0, 18.0]}

docking_wf = rowan.submit_docking_workflow(
    protein=protein,
    pocket=pocket,
    initial_molecule=top_smiles,
    do_pose_refinement=True,
    name=f"docking_{top_compound}",
)

dock_result = docking_wf.result()
print(f"\nDocking score: {dock_result.scores[0]:.2f} kcal/mol")
print(f"Best pose saved to: best_pose.pdb")
dock_result.best_pose.write("best_pose.pdb")
```

## Error handling and troubleshooting

### Common errors and solutions

```python
import rowan

# Error 1: Invalid SMILES
try:
    wf = rowan.submit_descriptors_workflow("CCCC(CC", name="bad smiles")  # Invalid
except rowan.ValidationError as e:
    print(f"Invalid SMILES: {e}")
    # Solution: Use RDKit to validate before submission
    from rdkit import Chem
    smi = Chem.MolToSmiles(Chem.MolFromSmiles(smi))

# Error 2: API key not set
try:
    wf = rowan.submit_descriptors_workflow("CCO")
except rowan.AuthenticationError:
    print("API key not found. Set ROWAN_API_KEY env var or call rowan.api_key = '...'")

# Error 3: Insufficient credits
try:
    wf = rowan.submit_protein_cofolding_workflow(...)
except rowan.InsufficientCreditsError as e:
    print(f"Not enough credits: {e}. Purchase more or reduce job size.")

# Error 4: Workflow failed (bad molecule, etc.)
try:
    wf = rowan.submit_docking_workflow(...)
    result = wf.result()
except rowan.WorkflowError as e:
    print(f"Workflow failed: {e}")
    # Check wf.status for details
    print(f"Status: {wf.status}")

# Error 5: Workflow not yet done — poll manually
result = wf.result(wait=True, poll_interval=5)  # waits and polls every 5s
# Or check status without blocking:
if not wf.done():
    print("Workflow still running. Call wf.result() again later.")
```

### Debugging tips

- **Check workflow status**：`wf.status`、检查 `wf.done()`，或调用 `wf.get_status()`
- **Inspect raw result**：使用 `result.data` 而不是 convenience properties
- **Re-run failed workflow**：保存 UUIDs，并用 `rowan.retrieve_workflow(uuid)` retry
- **Validate molecules beforehand**：Batch submission 前使用 RDKit 或 Chemaxon

## Recommended usage patterns

- **优先使用 Rowan-native workflows**，如果它们已存在，就不要低层级手工组装
- **使用 projects 和 folders** 管理任何非平凡 campaign（>5 workflows）
- **使用 `result()` block 直到完成**（default：`wait=True, poll_interval=5`）
- **优先使用 typed result properties**，未映射字段再 fallback 到 `.data`
- **使用 batch submission** 处理 compound libraries 或 analogue series
- **串联 workflows** 形成 multi-step chemistry campaigns：
  - `pKa → macropKa → permeability`（ADME assessment）
  - `tautomer search → docking → pose-analysis MD`（pose refinement）
  - `MSA generation → protein-ligand cofolding`（AI structure prediction）
- **使用 webhooks** 处理 long-running campaigns（>50 workflows）或 asynchronous pipelines
- **使用 streaming** 获取大型 conformer/docking searches 的 interactive feedback

## Summary

当 workflow 需要在云端执行 molecular-design tasks，尤其是希望通过一个 unified API 在 small-molecule modeling、proteins、docking、ADME prediction 和 ML structure generation 中保持一致的 result handling 时，使用 Rowan。

Rowan 是 molecular-design workflow platform，而不只是 remote chemistry engine。它处理 infrastructure scaling、result persistence 和 multi-step pipeline orchestration，让你专注于 science。
