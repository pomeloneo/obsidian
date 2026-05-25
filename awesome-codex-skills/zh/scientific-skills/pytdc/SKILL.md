---
name: pytdc
description: Therapeutics Data Commons。面向 AI 的 drug discovery 数据集（ADME、toxicity、DTI）、benchmark、scaffold split、molecular oracle，用于 therapeutic ML 和 pharmacological prediction。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# PyTDC (Therapeutics Data Commons)

## 概述

PyTDC 是一个 open-science 平台，为 drug discovery 和 development 提供面向 AI 的数据集和 benchmark。它提供覆盖整个 therapeutics pipeline 的 curated datasets，配有标准化 evaluation metrics 和有意义的 data splits，并组织为三类：single-instance prediction（molecular/protein properties）、multi-instance prediction（drug-target interactions、DDI）和 generation（molecule generation、retrosynthesis）。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 处理 drug discovery 或 therapeutic ML 数据集
- 在标准化 pharmaceutical task 上 benchmark machine learning model
- 预测 molecular properties（ADME、toxicity、bioactivity）
- 预测 drug-target 或 drug-drug interaction
- 生成具有期望性质的新 molecule
- 访问带有适当 train/test split（scaffold、cold-split）的 curated datasets
- 使用 molecular oracle 进行 property optimization

## 安装与设置

使用 pip 安装 PyTDC：

```bash
uv pip install PyTDC
```

升级到最新版本：

```bash
uv pip install PyTDC --upgrade
```

核心依赖（自动安装）：
- numpy, pandas, tqdm, seaborn, scikit_learn, fuzzywuzzy

特定功能所需的额外包会按需自动安装。

## 快速开始

访问任意 TDC dataset 的基本模式如下：

```python
from tdc.<problem> import <Task>
data = <Task>(name='<Dataset>')
split = data.get_split(method='scaffold', seed=1, frac=[0.7, 0.1, 0.2])
df = data.get_data(format='df')
```

其中：
- `<problem>`：`single_pred`、`multi_pred` 或 `generation` 之一
- `<Task>`：具体 task category（例如 ADME、DTI、MolGen）
- `<Dataset>`：该 task 中的数据集名称

**示例 - 加载 ADME 数据：**

```python
from tdc.single_pred import ADME
data = ADME(name='Caco2_Wang')
split = data.get_split(method='scaffold')
# Returns dict with 'train', 'valid', 'test' DataFrames
```

## Single-Instance Prediction Tasks

Single-instance prediction 指预测单个 biomedical entity（molecule、protein 等）的性质。

### 可用 Task Categories

#### 1. ADME (Absorption, Distribution, Metabolism, Excretion)

预测 drug molecule 的 pharmacokinetic properties。

```python
from tdc.single_pred import ADME
data = ADME(name='Caco2_Wang')  # Intestinal permeability
# Other datasets: HIA_Hou, Bioavailability_Ma, Lipophilicity_AstraZeneca, etc.
```

**常见 ADME 数据集：**
- Caco2 - Intestinal permeability
- HIA - Human intestinal absorption
- Bioavailability - Oral bioavailability
- Lipophilicity - Octanol-water partition coefficient
- Solubility - Aqueous solubility
- BBB - Blood-brain barrier penetration
- CYP - Cytochrome P450 metabolism

#### 2. Toxicity (Tox)

预测 compound 的 toxicity 和 adverse effects。

```python
from tdc.single_pred import Tox
data = Tox(name='hERG')  # Cardiotoxicity
# Other datasets: AMES, DILI, Carcinogens_Lagunin, etc.
```

**常见 toxicity 数据集：**
- hERG - Cardiac toxicity
- AMES - Mutagenicity
- DILI - Drug-induced liver injury
- Carcinogens - Carcinogenicity
- ClinTox - Clinical trial toxicity

#### 3. HTS (High-Throughput Screening)

来自 screening data 的 bioactivity prediction。

```python
from tdc.single_pred import HTS
data = HTS(name='SARSCoV2_Vitro_Touret')
```

#### 4. QM (Quantum Mechanics)

Molecule 的 quantum mechanical properties。

```python
from tdc.single_pred import QM
data = QM(name='QM7')
```

#### 5. 其他 Single Prediction Tasks

- **Yields**：化学反应 yield prediction
- **Epitope**：biologics 的 epitope prediction
- **Develop**：development-stage prediction
- **CRISPROutcome**：gene editing outcome prediction

### 数据格式

Single prediction dataset 通常返回包含以下列的 DataFrame：
- `Drug_ID` 或 `Compound_ID`：唯一标识符
- `Drug` 或 `X`：SMILES string 或 molecular representation
- `Y`：目标 label（continuous 或 binary）

## Multi-Instance Prediction Tasks

Multi-instance prediction 指预测多个 biomedical entity 之间 interaction 的性质。

### 可用 Task Categories

#### 1. DTI (Drug-Target Interaction)

预测 drug 与 protein target 之间的 binding affinity。

```python
from tdc.multi_pred import DTI
data = DTI(name='BindingDB_Kd')
split = data.get_split()
```

**可用数据集：**
- BindingDB_Kd - Dissociation constant（52,284 pairs）
- BindingDB_IC50 - Half-maximal inhibitory concentration（991,486 pairs）
- BindingDB_Ki - Inhibition constant（375,032 pairs）
- DAVIS, KIBA - Kinase binding datasets

**数据格式：** Drug_ID, Target_ID, Drug (SMILES), Target (sequence), Y (binding affinity)

#### 2. DDI (Drug-Drug Interaction)

预测 drug pair 之间的 interaction。

```python
from tdc.multi_pred import DDI
data = DDI(name='DrugBank')
split = data.get_split()
```

这是一个 multi-class classification task，用于预测 interaction type。数据集包含 191,808 个 DDI pairs 和 1,706 种 drugs。

#### 3. PPI (Protein-Protein Interaction)

预测 protein-protein interaction。

```python
from tdc.multi_pred import PPI
data = PPI(name='HuRI')
```

#### 4. 其他 Multi-Prediction Tasks

- **GDA**：Gene-disease associations
- **DrugRes**：Drug resistance prediction
- **DrugSyn**：Drug synergy prediction
- **PeptideMHC**：Peptide-MHC binding
- **AntibodyAff**：Antibody affinity prediction
- **MTI**：miRNA-target interactions
- **Catalyst**：Catalyst prediction
- **TrialOutcome**：Clinical trial outcome prediction

## Generation Tasks

Generation task 指创建具有期望性质的新 biomedical entity。

### 1. Molecular Generation (MolGen)

生成多样、新颖且具有理想化学性质的 molecule。

```python
from tdc.generation import MolGen
data = MolGen(name='ChEMBL_V29')
split = data.get_split()
```

结合 oracle 可针对特定性质进行优化：

```python
from tdc import Oracle
oracle = Oracle(name='GSK3B')
score = oracle('CC(C)Cc1ccc(cc1)C(C)C(O)=O')  # Evaluate SMILES
```

所有可用 oracle function 见 `references/oracles.md`。

### 2. Retrosynthesis (RetroSyn)

预测合成 target molecule 所需的 reactants。

```python
from tdc.generation import RetroSyn
data = RetroSyn(name='USPTO')
split = data.get_split()
```

数据集包含来自 USPTO database 的 1,939,253 个 reactions。

### 3. Paired Molecule Generation

生成 molecule pair（例如 prodrug-drug pair）。

```python
from tdc.generation import PairMolGen
data = PairMolGen(name='Prodrug')
```

关于 oracle 的详细文档和 molecular generation workflow，请参考 `references/oracles.md` 和 `scripts/molecular_generation.py`。

## Benchmark Groups

Benchmark group 提供相关数据集的 curated collections，用于系统化 model evaluation。

### ADMET Benchmark Group

```python
from tdc.benchmark_group import admet_group
group = admet_group(path='data/')

# Get benchmark datasets
benchmark = group.get('Caco2_Wang')
predictions = {}

for seed in [1, 2, 3, 4, 5]:
    train, valid = benchmark['train'], benchmark['valid']
    # Train model here
    predictions[seed] = model.predict(benchmark['test'])

# Evaluate with required 5 seeds
results = group.evaluate(predictions)
```

**ADMET Group 包含 22 个数据集**，覆盖 absorption、distribution、metabolism、excretion 和 toxicity。

### 其他 Benchmark Groups

可用 benchmark group 包括以下集合：
- ADMET properties
- Drug-target interactions
- Drug combination prediction
- 以及更专门的 therapeutic tasks

Benchmark evaluation workflow 见 `scripts/benchmark_evaluation.py`。

## Data Functions

TDC 提供全面的数据处理工具，分为四类。

### 1. Dataset Splits

使用多种策略获取 train/validation/test partitions：

```python
# Scaffold split (default for most tasks)
split = data.get_split(method='scaffold', seed=1, frac=[0.7, 0.1, 0.2])

# Random split
split = data.get_split(method='random', seed=42, frac=[0.8, 0.1, 0.1])

# Cold split (for DTI/DDI tasks)
split = data.get_split(method='cold_drug', seed=1)  # Unseen drugs in test
split = data.get_split(method='cold_target', seed=1)  # Unseen targets in test
```

**可用 split strategies：**
- `random`：Random shuffling
- `scaffold`：基于 scaffold（用于 chemical diversity）
- `cold_drug`, `cold_target`, `cold_drug_target`：用于 DTI tasks
- `temporal`：temporal dataset 的 time-based splits

### 2. Model Evaluation

使用标准化 metrics 进行 evaluation：

```python
from tdc import Evaluator

# For binary classification
evaluator = Evaluator(name='ROC-AUC')
score = evaluator(y_true, y_pred)

# For regression
evaluator = Evaluator(name='RMSE')
score = evaluator(y_true, y_pred)
```

**可用 metrics：** ROC-AUC, PR-AUC, F1, Accuracy, RMSE, MAE, R2, Spearman, Pearson 等。

### 3. Data Processing

TDC 提供 11 个关键 processing utilities：

```python
from tdc.chem_utils import MolConvert

# Molecule format conversion
converter = MolConvert(src='SMILES', dst='PyG')
pyg_graph = converter('CC(C)Cc1ccc(cc1)C(C)C(O)=O')
```

**Processing utilities 包括：**
- Molecule format conversion（SMILES、SELFIES、PyG、DGL、ECFP 等）
- Molecule filters（PAINS、drug-likeness）
- Label binarization 和 unit conversion
- Data balancing（over/under-sampling）
- Pair data 的 negative sampling
- Graph transformation
- Entity retrieval（CID to SMILES、UniProt to sequence）

完整 utilities 文档见 `references/utilities.md`。

### 4. Molecule Generation Oracles

TDC 提供 17+ 个用于 molecular optimization 的 oracle functions：

```python
from tdc import Oracle

# Single oracle
oracle = Oracle(name='DRD2')
score = oracle('CC(C)Cc1ccc(cc1)C(C)C(O)=O')

# Multiple oracles
oracle = Oracle(name='JNK3')
scores = oracle(['SMILES1', 'SMILES2', 'SMILES3'])
```

完整 oracle 文档见 `references/oracles.md`。

## 高级功能

### 检索可用数据集

```python
from tdc.utils import retrieve_dataset_names

# Get all ADME datasets
adme_datasets = retrieve_dataset_names('ADME')

# Get all DTI datasets
dti_datasets = retrieve_dataset_names('DTI')
```

### Label Transformations

```python
# Get label mapping
label_map = data.get_label_map(name='DrugBank')

# Convert labels
from tdc.chem_utils import label_transform
transformed = label_transform(y, from_unit='nM', to_unit='p')
```

### Database Queries

```python
from tdc.utils import cid2smiles, uniprot2seq

# Convert PubChem CID to SMILES
smiles = cid2smiles(2244)

# Convert UniProt ID to amino acid sequence
sequence = uniprot2seq('P12345')
```

## 常见 Workflow

### Workflow 1：训练 Single Prediction Model

完整示例见 `scripts/load_and_split_data.py`：

```python
from tdc.single_pred import ADME
from tdc import Evaluator

# Load data
data = ADME(name='Caco2_Wang')
split = data.get_split(method='scaffold', seed=42)

train, valid, test = split['train'], split['valid'], split['test']

# Train model (user implements)
# model.fit(train['Drug'], train['Y'])

# Evaluate
evaluator = Evaluator(name='MAE')
# score = evaluator(test['Y'], predictions)
```

### Workflow 2：Benchmark Evaluation

含多个 seeds 和正确 evaluation protocol 的完整示例见 `scripts/benchmark_evaluation.py`。

### Workflow 3：使用 Oracles 进行 Molecular Generation

使用 oracle functions 做 goal-directed generation 的示例见 `scripts/molecular_generation.py`。

## 资源

此 skill 包含常见 TDC workflow 的随附资源：

### scripts/

- `load_and_split_data.py`：使用多种策略加载和切分 TDC dataset 的模板
- `benchmark_evaluation.py`：用正确的 5-seed protocol 运行 benchmark group evaluation 的模板
- `molecular_generation.py`：使用 oracle functions 进行 molecular generation 的模板

### references/

- `datasets.md`：按 task type 组织的所有可用数据集完整目录
- `oracles.md`：全部 17+ 个 molecule generation oracle 的完整文档
- `utilities.md`：data processing、splitting 和 evaluation utilities 的详细指南

## 其他资源

- **Official Website**：https://tdcommons.ai
- **Documentation**：https://tdc.readthedocs.io
- **GitHub**：https://github.com/mims-harvard/TDC
- **Paper**：NeurIPS 2021 - "Therapeutics Data Commons: Machine Learning Datasets and Tasks for Drug Discovery and Development"
