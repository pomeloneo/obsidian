---
name: esm
description: 面向 protein language models 的综合工具包，包括 ESM3（跨 sequence、structure 和 function 的 generative multimodal protein design）和 ESM C（高效 protein embeddings 与 representations）。当处理 protein sequences、structures 或 function prediction；设计 novel proteins；生成 protein embeddings；执行 inverse folding；或进行 protein engineering 任务时使用此 skill。支持本地模型使用，也支持基于云端 Forge API 的可扩展 inference。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# ESM：Evolutionary Scale Modeling

## 概述

ESM 提供用于理解、生成和设计 proteins 的前沿 protein language models。此 skill 支持两个模型家族：用于跨 sequence、structure 和 function 进行 generative protein design 的 ESM3，以及用于高效 protein representation learning 和 embeddings 的 ESM C。

## 核心能力

### 1. 使用 ESM3 生成 Protein Sequence

使用 multimodal generative modeling 生成具有目标性质的新 protein sequences。

**何时使用：**
- 设计具有特定 functional properties 的 proteins
- 补全部分 protein sequences
- 生成现有 proteins 的 variants
- 创建具有目标 structural characteristics 的 proteins

**基本用法：**

```python
from esm.models.esm3 import ESM3
from esm.sdk.api import ESM3InferenceClient, ESMProtein, GenerationConfig

# Load model locally
model: ESM3InferenceClient = ESM3.from_pretrained("esm3-sm-open-v1").to("cuda")

# Create protein prompt
protein = ESMProtein(sequence="MPRT___KEND")  # '_' represents masked positions

# Generate completion
protein = model.generate(protein, GenerationConfig(track="sequence", num_steps=8))
print(protein.sequence)
```

**通过 Forge API 进行 remote/cloud 使用：**

```python
from esm.sdk.forge import ESM3ForgeInferenceClient
from esm.sdk.api import ESMProtein, GenerationConfig

# Connect to Forge
model = ESM3ForgeInferenceClient(model="esm3-medium-2024-08", url="https://forge.evolutionaryscale.ai", token="<token>")

# Generate
protein = model.generate(protein, GenerationConfig(track="sequence", num_steps=8))
```

详细的 ESM3 model specifications、高级 generation configurations 和 multimodal prompting examples 见 `references/esm3-api.md`。

### 2. Structure Prediction 和 Inverse Folding

使用 ESM3 的 structure track 从 sequence 预测 structure，或执行 inverse folding（从 structure 设计 sequence）。

**Structure prediction：**

```python
from esm.sdk.api import ESM3InferenceClient, ESMProtein, GenerationConfig

# Predict structure from sequence
protein = ESMProtein(sequence="MPRTKEINDAGLIVHSP...")
protein_with_structure = model.generate(
    protein,
    GenerationConfig(track="structure", num_steps=protein.sequence.count("_"))
)

# Access predicted structure
coordinates = protein_with_structure.coordinates  # 3D coordinates
pdb_string = protein_with_structure.to_pdb()
```

**Inverse folding（从 structure 生成 sequence）：**

```python
# Design sequence for a target structure
protein_with_structure = ESMProtein.from_pdb("target_structure.pdb")
protein_with_structure.sequence = None  # Remove sequence

# Generate sequence that folds to this structure
designed_protein = model.generate(
    protein_with_structure,
    GenerationConfig(track="sequence", num_steps=50, temperature=0.7)
)
```

### 3. 使用 ESM C 生成 Protein Embeddings

为 function prediction、classification 或 similarity analysis 等下游任务生成高质量 embeddings。

**何时使用：**
- 为 machine learning 提取 protein representations
- 计算 sequence similarities
- 为 protein classification 做 feature extraction
- 面向 protein 相关任务进行 transfer learning

**基本用法：**

```python
from esm.models.esmc import ESMC
from esm.sdk.api import ESMProtein

# Load ESM C model
model = ESMC.from_pretrained("esmc-300m").to("cuda")

# Get embeddings
protein = ESMProtein(sequence="MPRTKEINDAGLIVHSP...")
protein_tensor = model.encode(protein)

# Generate embeddings
embeddings = model.forward(protein_tensor)
```

**Batch processing：**

```python
# Encode multiple proteins
proteins = [
    ESMProtein(sequence="MPRTKEIND..."),
    ESMProtein(sequence="AGLIVHSPQ..."),
    ESMProtein(sequence="KTEFLNDGR...")
]

embeddings_list = [model.logits(model.forward(model.encode(p))) for p in proteins]
```

ESM C model details、efficiency comparisons 和高级 embedding strategies 见 `references/esm-c-api.md`。

### 4. Function Conditioning 和 Annotation

使用 ESM3 的 function track 生成带特定 functional annotations 的 proteins，或从 sequence 预测 function。

**Function-conditioned generation：**

```python
from esm.sdk.api import ESMProtein, FunctionAnnotation, GenerationConfig

# Create protein with desired function
protein = ESMProtein(
    sequence="_" * 200,  # Generate 200 residue protein
    function_annotations=[
        FunctionAnnotation(label="fluorescent_protein", start=50, end=150)
    ]
)

# Generate sequence with specified function
functional_protein = model.generate(
    protein,
    GenerationConfig(track="sequence", num_steps=200)
)
```

### 5. Chain-of-Thought Generation

使用 ESM3 的 chain-of-thought generation 方法迭代细化 protein designs。

```python
from esm.sdk.api import GenerationConfig

# Multi-step refinement
protein = ESMProtein(sequence="MPRT" + "_" * 100 + "KEND")

# Step 1: Generate initial structure
config = GenerationConfig(track="structure", num_steps=50)
protein = model.generate(protein, config)

# Step 2: Refine sequence based on structure
config = GenerationConfig(track="sequence", num_steps=50, temperature=0.5)
protein = model.generate(protein, config)

# Step 3: Predict function
config = GenerationConfig(track="function", num_steps=20)
protein = model.generate(protein, config)
```

### 6. 使用 Forge API 进行 Batch Processing

使用 Forge 的 async executor 高效处理多个 proteins。

```python
from esm.sdk.forge import ESM3ForgeInferenceClient
import asyncio

client = ESM3ForgeInferenceClient(model="esm3-medium-2024-08", token="<token>")

# Async batch processing
async def batch_generate(proteins_list):
    tasks = [
        client.async_generate(protein, GenerationConfig(track="sequence"))
        for protein in proteins_list
    ]
    return await asyncio.gather(*tasks)

# Execute
proteins = [ESMProtein(sequence=f"MPRT{'_' * 50}KEND") for _ in range(10)]
results = asyncio.run(batch_generate(proteins))
```

详细 Forge API documentation、authentication、rate limits 和 batch processing patterns 见 `references/forge-api.md`。

## 模型选择指南

**ESM3 Models（Generative）：**
- `esm3-sm-open-v1` (1.4B) - Open weights，本地使用，适合实验
- `esm3-medium-2024-08` (7B) - 质量和速度的最佳平衡（仅 Forge）
- `esm3-large-2024-03` (98B) - 最高质量，更慢（仅 Forge）

**ESM C Models（Embeddings）：**
- `esmc-300m` (30 layers) - 轻量，快速 inference
- `esmc-600m` (36 layers) - 平衡性能
- `esmc-6b` (80 layers) - 最高 representation quality

**选择标准：**
- **本地开发/测试：** 使用 `esm3-sm-open-v1` 或 `esmc-300m`
- **生产质量：** 通过 Forge 使用 `esm3-medium-2024-08`
- **最高准确性：** 使用 `esm3-large-2024-03` 或 `esmc-6b`
- **高吞吐：** 使用带 batch executor 的 Forge API
- **成本优化：** 使用较小模型，并实现 caching strategies

## 安装

**基础安装：**

```bash
uv pip install esm
```

**带 Flash Attention（推荐用于更快 inference）：**

```bash
uv pip install esm
uv pip install flash-attn --no-build-isolation
```

**用于 Forge API 访问：**

```bash
uv pip install esm  # SDK includes Forge client
```

不需要额外依赖。Forge API token 可在 https://forge.evolutionaryscale.ai 获取。

## 常见工作流

详细示例和完整工作流见 `references/workflows.md`，其中包括：
- 使用 chain-of-thought 设计 novel GFP
- Protein variant generation 和 screening
- 基于 structure 的 sequence optimization
- Function prediction pipelines
- 基于 embedding 的 clustering 和 analysis

## 参考

此 skill 包含完整参考文档：

- `references/esm3-api.md` - ESM3 model architecture、API reference、generation parameters 和 multimodal prompting
- `references/esm-c-api.md` - ESM C model details、embedding strategies 和 performance optimization
- `references/forge-api.md` - Forge platform documentation、authentication、batch processing 和 deployment
- `references/workflows.md` - 完整示例和常见 workflow patterns

这些 references 包含详细 API specifications、parameter descriptions 和高级 usage patterns。针对具体任务按需加载。

## 最佳实践

**对于 generation tasks：**
- 原型设计从较小模型开始（`esm3-sm-open-v1`）
- 使用 temperature 参数控制多样性（0.0 = deterministic，1.0 = diverse）
- 对复杂 designs 使用 chain-of-thought 进行迭代细化
- 用 structure prediction 或 wet-lab experiments 验证生成的 sequences

**对于 embedding tasks：**
- 尽可能 batch process sequences 以提高效率
- 为重复分析缓存 embeddings
- 计算 similarities 时 normalize embeddings
- 根据下游任务需求选择合适的 model size

**对于 production deployment：**
- 使用 Forge API 获得可扩展性和最新模型
- 为 API calls 实现 error handling 和 retry logic
- 监控 token usage 并实现 rate limiting
- 如需专用基础设施，考虑 AWS SageMaker deployment

## 资源和文档

- **GitHub Repository:** https://github.com/evolutionaryscale/esm
- **Forge Platform:** https://forge.evolutionaryscale.ai
- **Scientific Paper:** Hayes et al., Science (2025) - https://www.science.org/doi/10.1126/science.ads0018
- **Blog Posts:**
  - ESM3 Release: https://www.evolutionaryscale.ai/blog/esm3-release
  - ESM C Launch: https://www.evolutionaryscale.ai/blog/esm-cambrian
- **Community:** Slack community at https://bit.ly/3FKwcWd
- **Model Weights:** HuggingFace EvolutionaryScale organization

## 负责任使用

ESM 设计用于 protein engineering、drug discovery 和 scientific research 中的有益应用。设计 novel proteins 时遵循 Responsible Biodesign Framework (https://responsiblebiodesign.ai/)。在实验验证前，考虑 protein designs 的 biosafety 和伦理影响。
