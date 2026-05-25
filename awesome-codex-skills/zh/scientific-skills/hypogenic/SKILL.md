---
name: hypogenic
description: 在 tabular datasets 上进行 automated LLM-driven hypothesis generation and testing。当你想系统探索 empirical data 中 patterns 的 hypotheses（例如 deception detection、content analysis）时使用。结合 literature insights 和 data-driven hypothesis testing。手动 hypothesis formulation 使用 hypothesis-generation；creative ideation 使用 scientific-brainstorming。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Hypogenic

## 概述

Hypogenic 使用 large language models 提供 automated hypothesis generation and testing，以加速 scientific discovery。该 framework 支持三种方法：HypoGeniC（data-driven hypothesis generation）、HypoRefine（literature 和 data 的协同整合）以及 Union methods（literature 和 data-driven hypotheses 的机械组合）。

## Quick Start

几分钟内开始使用 Hypogenic：

```bash
# Install the package
uv pip install hypogenic

# Clone example datasets
git clone https://github.com/ChicagoHAI/HypoGeniC-datasets.git ./data

# Run basic hypothesis generation
hypogenic_generation --config ./data/your_task/config.yaml --method hypogenic --num_hypotheses 20

# Run inference on generated hypotheses
hypogenic_inference --config ./data/your_task/config.yaml --hypotheses output/hypotheses.json
```

**或使用 Python API：**

```python
from hypogenic import BaseTask

# Create task with your configuration
task = BaseTask(config_path="./data/your_task/config.yaml")

# Generate hypotheses
task.generate_hypotheses(method="hypogenic", num_hypotheses=20)

# Run inference
results = task.inference(hypothesis_bank="./output/hypotheses.json")
```

## 何时使用此 Skill

处理以下任务时使用此 skill：
- 从 observational datasets 生成 scientific hypotheses
- 系统测试多个 competing hypotheses
- 将 literature insights 与 empirical patterns 结合
- 通过 automated hypothesis ideation 加速 research discovery
- 需要 hypothesis-driven analysis 的领域：deception detection、AI-generated content identification、mental health indicators、predictive modeling 或其他 empirical research

## 关键特性

**Automated Hypothesis Generation**
- 几分钟内从数据生成 10-20+ 个可测试 hypotheses
- 基于 validation performance 进行 iterative refinement
- 支持 API-based（OpenAI、Anthropic）和 local LLMs

**Literature Integration**
- 通过 PDF processing 从 research papers 提取 insights
- 将 theoretical foundations 与 empirical patterns 结合
- 使用 GROBID 的系统化 literature-to-hypothesis pipeline

**Performance Optimization**
- Redis caching 减少重复 experiments 的 API costs
- Parallel processing 支持大规模 hypothesis testing
- Adaptive refinement 聚焦 challenging examples

**Flexible Configuration**
- 基于 templates 的 prompt engineering，支持 variable injection
- 面向 domain-specific tasks 的 custom label extraction
- Modular architecture，便于扩展

**Proven Results**
- 相比 few-shot baselines 提升 8.97%
- 相比 literature-only approaches 提升 15.75%
- 80-84% hypothesis diversity（non-redundant insights）
- Human evaluators 报告显著 decision-making improvements

## 核心能力

### 1. HypoGeniC：Data-Driven Hypothesis Generation

仅从 observational data 中通过 iterative refinement 生成 hypotheses。

**过程：**
1. 用小型 data subset 初始化，生成 candidate hypotheses
2. 基于 performance 迭代细化 hypotheses
3. 使用 challenging examples 生成新 hypotheses，替换表现较差的 hypotheses

**最适合：** 没有 existing literature 的 exploratory research，新颖 datasets 中的 pattern discovery

### 2. HypoRefine：Literature and Data Integration

通过 agentic framework 协同结合 existing literature 和 empirical data。

**过程：**
1. 从相关 research papers（通常 10 篇）提取 insights
2. 从 literature 生成 theory-grounded hypotheses
3. 从 observational patterns 生成 data-driven hypotheses
4. 通过 iterative improvement 细化两个 hypothesis banks

**最适合：** 有既有 theoretical foundations 的 research，验证或扩展 existing theories

### 3. Union Methods

将 literature-only hypotheses 与 framework outputs 机械组合。

**Variants：**
- **Literature ∪ HypoGeniC**：将 literature hypotheses 与 data-driven generation 结合
- **Literature ∪ HypoRefine**：将 literature hypotheses 与 integrated approach 结合

**最适合：** 全面 hypothesis coverage，在保持多样 perspectives 的同时消除 redundancy

## 安装

通过 pip 安装：
```bash
uv pip install hypogenic
```

**Optional dependencies：**
- **Redis server**（port 6832）：启用 LLM responses caching，在 iterative hypothesis generation 中显著降低 API costs
- **s2orc-doc2json**：HypoRefine workflows 中处理 literature PDFs 所需
- **GROBID**：PDF preprocessing 所需（见 Literature Processing 部分）

**Clone example datasets：**
```bash
# For HypoGeniC examples
git clone https://github.com/ChicagoHAI/HypoGeniC-datasets.git ./data

# For HypoRefine/Union examples
git clone https://github.com/ChicagoHAI/Hypothesis-agent-datasets.git ./data
```

## Dataset Format

Datasets 必须遵循 HuggingFace datasets format，并使用特定 naming conventions：

**Required files：**
- `<TASK>_train.json`：Training data
- `<TASK>_val.json`：Validation data  
- `<TASK>_test.json`：Test data

**JSON 中的 required keys：**
- `text_features_1` through `text_features_n`：包含 feature values 的 string lists
- `label`：包含 ground truth labels 的 string list

**示例（headline click prediction）：**
```json
{
  "headline_1": [
    "What Up, Comet? You Just Got *PROBED*",
    "Scientists Made a Breakthrough in Quantum Computing"
  ],
  "headline_2": [
    "Scientists Everywhere Were Holding Their Breath Today. Here's Why.",
    "New Quantum Computer Achieves Milestone"
  ],
  "label": [
    "Headline 2 has more clicks than Headline 1",
    "Headline 1 has more clicks than Headline 2"
  ]
}
```

**重要说明：**
- 所有 lists 必须长度相同
- Label format 必须匹配你的 `extract_label()` function output format
- Feature keys 可自定义以匹配你的 domain（例如 `review_text`、`post_content` 等）

## Configuration

每个 task 都需要 `config.yaml` 文件，指定：

**Required elements：**
- Dataset paths（train/val/test）
- Prompt templates，用于：
  - Observations generation
  - Batched hypothesis generation
  - Hypothesis inference
  - Relevance checking
  - Adaptive methods（用于 HypoRefine）

**Template capabilities：**
- Dataset placeholders，用于 dynamic variable injection（例如 `${text_features_1}`、`${num_hypotheses}`）
- Custom label extraction functions，用于 domain-specific parsing
- Role-based prompt structure（system、user、assistant roles）

**Configuration structure：**
```yaml
task_name: your_task_name

train_data_path: ./your_task_train.json
val_data_path: ./your_task_val.json
test_data_path: ./your_task_test.json

prompt_templates:
  # Extra keys for reusable prompt components
  observations: |
    Feature 1: ${text_features_1}
    Feature 2: ${text_features_2}
    Observation: ${label}
  
  # Required templates
  batched_generation:
    system: "Your system prompt here"
    user: "Your user prompt with ${num_hypotheses} placeholder"
  
  inference:
    system: "Your inference system prompt"
    user: "Your inference user prompt"
  
  # Optional templates for advanced features
  few_shot_baseline: {...}
  is_relevant: {...}
  adaptive_inference: {...}
  adaptive_selection: {...}
```

完整 example configuration 见 `references/config_template.yaml`。

## Literature Processing（HypoRefine/Union Methods）

要使用 literature-based hypothesis generation，必须预处理 PDF papers。

> **Note:** 下面命令在 cloned [HypoGenic repository](https://github.com/ChicagoHAI/hypothesis-generation) 内运行，而不是从此 skill directory 运行。

**Step 1：Setup GROBID**（仅首次）
```bash
bash ./modules/setup_grobid.sh
```

**Step 2：添加 PDF files**
将 research papers 放入 `literature/YOUR_TASK_NAME/raw/`

**Step 3：处理 PDFs**
```bash
# Start GROBID service
bash ./modules/run_grobid.sh

# Process PDFs for your task
cd examples
python pdf_preprocess.py --task_name YOUR_TASK_NAME
```

这会将 PDFs 转换为用于 hypothesis extraction 的 structured format。未来 releases 将支持 automated literature search。

## CLI Usage

### Hypothesis Generation

```bash
hypogenic_generation --help
```

**Key parameters：**
- Task configuration file path
- Model selection（API-based 或 local）
- Generation method（HypoGeniC、HypoRefine 或 Union）
- 要生成的 hypotheses 数量
- Hypothesis banks 的 output directory

### Hypothesis Inference

```bash
hypogenic_inference --help
```

**Key parameters：**
- Task configuration file path
- Hypothesis bank file path
- Test dataset path
- Inference method（default 或 multi-hypothesis）
- Results 的 output file

## Python API Usage

如需 programmatic control 和 custom workflows，在 Python code 中直接使用 Hypogenic：

### Basic HypoGeniC Generation

```python
from hypogenic import BaseTask

# Clone example datasets first
# git clone https://github.com/ChicagoHAI/HypoGeniC-datasets.git ./data

# Load your task with custom extract_label function
task = BaseTask(
    config_path="./data/your_task/config.yaml",
    extract_label=lambda text: extract_your_label(text)
)

# Generate hypotheses
task.generate_hypotheses(
    method="hypogenic",
    num_hypotheses=20,
    output_path="./output/hypotheses.json"
)

# Run inference
results = task.inference(
    hypothesis_bank="./output/hypotheses.json",
    test_data="./data/your_task/your_task_test.json"
)
```

### HypoRefine/Union Methods

```python
# For literature-integrated approaches
# git clone https://github.com/ChicagoHAI/Hypothesis-agent-datasets.git ./data

# Generate with HypoRefine
task.generate_hypotheses(
    method="hyporefine",
    num_hypotheses=15,
    literature_path="./literature/your_task/",
    output_path="./output/"
)
# This generates 3 hypothesis banks:
# - HypoRefine (integrated approach)
# - Literature-only hypotheses
# - Literature∪HypoRefine (union)
```

### Multi-Hypothesis Inference

```python
from examples.multi_hyp_inference import run_multi_hypothesis_inference

# Test multiple hypotheses simultaneously
results = run_multi_hypothesis_inference(
    config_path="./data/your_task/config.yaml",
    hypothesis_bank="./output/hypotheses.json",
    test_data="./data/your_task/your_task_test.json"
)
```

### Custom Label Extraction

`extract_label()` function 对解析 LLM outputs 很关键。基于你的 task 实现它：

```python
def extract_label(llm_output: str) -> str:
    """Extract predicted label from LLM inference text.
    
    Default behavior: searches for 'final answer:\s+(.*)' pattern.
    Customize for your domain-specific output format.
    """
    import re
    match = re.search(r'final answer:\s+(.*)', llm_output, re.IGNORECASE)
    if match:
        return match.group(1).strip()
    return llm_output.strip()
```

**重要：** Extracted labels 必须与 dataset 中 `label` values 的 format 匹配，才能正确计算 accuracy。

## Workflow Examples

### Example 1：Data-Driven Hypothesis Generation（HypoGeniC）

**场景：** 没有先验 theoretical framework 的 AI-generated content detection

**Steps：**
1. 准备包含 text samples 和 labels（human vs. AI-generated）的 dataset
2. 创建带合适 prompt templates 的 `config.yaml`
3. 运行 hypothesis generation：
   ```bash
   hypogenic_generation --config config.yaml --method hypogenic --num_hypotheses 20
   ```
4. 在 test set 上运行 inference：
   ```bash
   hypogenic_inference --config config.yaml --hypotheses output/hypotheses.json --test_data data/test.json
   ```
5. 分析 formality、grammatical precision 和 tone differences 等 patterns

### Example 2：Literature-Informed Hypothesis Testing（HypoRefine）

**场景：** 基于 existing research 的 hotel reviews deception detection

**Steps：**
1. 收集 10 篇关于 linguistic deception cues 的相关 papers
2. 准备包含 genuine 和 fraudulent reviews 的 dataset
3. 配置 `config.yaml`，包含 literature processing 和 data generation templates
4. 运行 HypoRefine：
   ```bash
   hypogenic_generation --config config.yaml --method hyporefine --papers papers/ --num_hypotheses 15
   ```
5. 测试 pronoun frequency、detail specificity 和其他 linguistic patterns 相关 hypotheses
6. 比较 literature-based 和 data-driven hypothesis performance

### Example 3：Comprehensive Hypothesis Coverage（Union Method）

**场景：** 最大化 hypothesis diversity 的 mental stress detection

**Steps：**
1. 从 mental health research papers 生成 literature hypotheses
2. 从 social media posts 生成 data-driven hypotheses
3. 运行 Union method 组合并去重：
   ```bash
   hypogenic_generation --config config.yaml --method union --literature_hypotheses lit_hyp.json
   ```
4. Inference 同时捕获 theoretical constructs（posting behavior changes）和 data patterns（emotional language shifts）

## Performance Optimization

**Caching：** 启用 Redis caching，减少重复 LLM calls 的 API costs 和 computation time

**Parallel Processing：** 利用 multiple workers 进行 large-scale hypothesis generation 和 testing

**Adaptive Refinement：** 使用 challenging examples 迭代提升 hypothesis quality

## Expected Outcomes

使用 hypogenic 的研究已展示：
- AI-content detection tasks 中 accuracy 提升 14.19%
- Deception detection tasks 中 accuracy 提升 7.44%
- 80-84% 的 hypothesis pairs 提供 distinct、non-redundant insights
- Human evaluators 在多个 research domains 给出高 helpfulness ratings

## 故障排除

**Issue：** Generated hypotheses 太泛
**Solution：** 细化 `config.yaml` 中的 prompt templates，要求更具体、可测试的 hypotheses

**Issue：** Poor inference performance
**Solution：** 确保 dataset 有足够 training examples，调整 hypothesis generation parameters，或增加 hypotheses 数量

**Issue：** Label extraction failures
**Solution：** 为 domain-specific output parsing 实现 custom `extract_label()` function

**Issue：** GROBID PDF processing fails
**Solution：** 确保 GROBID service 正在运行（从 cloned repo 执行 `bash ./modules/run_grobid.sh`），且 PDFs 是有效 research papers

## 创建 Custom Tasks

要向 Hypogenic 添加新 task 或 dataset：

### Step 1：准备 Dataset

按照必需格式创建三个 JSON files：
- `your_task_train.json`
- `your_task_val.json`
- `your_task_test.json`

每个文件必须包含 text features（`text_features_1` 等）和 `label` 的 keys。

### Step 2：创建 config.yaml

定义你的 task configuration，包含：
- Task name 和 dataset paths
- Observations、generation、inference 的 prompt templates
- 任何用于 reusable prompt components 的 extra keys
- Placeholder variables（例如 `${text_features_1}`、`${num_hypotheses}`）

### Step 3：实现 extract_label Function

创建 custom label extraction function，用于解析你的 domain 中的 LLM outputs：

```python
from hypogenic import BaseTask

def extract_my_label(llm_output: str) -> str:
    """Custom label extraction for your task.
    
    Must return labels in same format as dataset 'label' field.
    """
    # Example: Extract from specific format
    if "Final prediction:" in llm_output:
        return llm_output.split("Final prediction:")[-1].strip()
    
    # Fallback to default pattern
    import re
    match = re.search(r'final answer:\s+(.*)', llm_output, re.IGNORECASE)
    return match.group(1).strip() if match else llm_output.strip()

# Use your custom task
task = BaseTask(
    config_path="./your_task/config.yaml",
    extract_label=extract_my_label
)
```

### Step 4：（可选）处理 Literature

对于 HypoRefine/Union methods：
1. 创建 `literature/your_task_name/raw/` directory
2. 添加相关 research paper PDFs
3. 运行 GROBID preprocessing
4. 用 `pdf_preprocess.py` 处理

### Step 5：生成和测试

使用 CLI 或 Python API 运行 hypothesis generation 和 inference：

```bash
# CLI approach
hypogenic_generation --config your_task/config.yaml --method hypogenic --num_hypotheses 20
hypogenic_inference --config your_task/config.yaml --hypotheses output/hypotheses.json

# Or use Python API (see Python API Usage section)
```

## Repository Structure

理解 repository layout：

```
hypothesis-generation/
├── hypogenic/              # Core package code
├── hypogenic_cmd/          # CLI entry points
├── hypothesis_agent/       # HypoRefine agent framework
├── literature/            # Literature processing utilities
├── modules/               # GROBID and preprocessing modules
├── examples/              # Example scripts
│   ├── generation.py      # Basic HypoGeniC generation
│   ├── union_generation.py # HypoRefine/Union generation
│   ├── inference.py       # Single hypothesis inference
│   ├── multi_hyp_inference.py # Multiple hypothesis inference
│   └── pdf_preprocess.py  # Literature PDF processing
├── data/                  # Example datasets (clone separately)
├── tests/                 # Unit tests
└── IO_prompting/          # Prompt templates and experiments
```

**Key directories：**
- **hypogenic/**：带 BaseTask 和 generation logic 的 main package
- **examples/**：常见 workflows 的 reference implementations
- **literature/**：用于 PDF processing 和 literature extraction 的工具
- **modules/**：External tool integrations（GROBID 等）

## Related Publications

### HypoBench (2025)

Liu, H., Huang, S., Hu, J., Zhou, Y., & Tan, C. (2025). HypoBench: Towards Systematic and Principled Benchmarking for Hypothesis Generation. arXiv preprint arXiv:2504.11524.

- **Paper:** https://arxiv.org/abs/2504.11524
- **Description:** Hypothesis generation methods 系统评估的 benchmarking framework

**BibTeX:**
```bibtex
@misc{liu2025hypobenchsystematicprincipledbenchmarking,
      title={HypoBench: Towards Systematic and Principled Benchmarking for Hypothesis Generation}, 
      author={Haokun Liu and Sicong Huang and Jingyu Hu and Yangqiaoyu Zhou and Chenhao Tan},
      year={2025},
      eprint={2504.11524},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2504.11524}, 
}
```

### Literature Meets Data (2024)

Liu, H., Zhou, Y., Li, M., Yuan, C., & Tan, C. (2024). Literature Meets Data: A Synergistic Approach to Hypothesis Generation. arXiv preprint arXiv:2410.17309.

- **Paper:** https://arxiv.org/abs/2410.17309
- **Code:** https://github.com/ChicagoHAI/hypothesis-generation
- **Description:** 介绍 HypoRefine，并展示 literature-based 和 data-driven hypothesis generation 的协同组合

**BibTeX:**
```bibtex
@misc{liu2024literaturemeetsdatasynergistic,
      title={Literature Meets Data: A Synergistic Approach to Hypothesis Generation}, 
      author={Haokun Liu and Yangqiaoyu Zhou and Mingxuan Li and Chenfei Yuan and Chenhao Tan},
      year={2024},
      eprint={2410.17309},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2410.17309}, 
}
```

### Hypothesis Generation with Large Language Models (2024)

Zhou, Y., Liu, H., Srivastava, T., Mei, H., & Tan, C. (2024). Hypothesis Generation with Large Language Models. In Proceedings of EMNLP Workshop of NLP for Science.

- **Paper:** https://aclanthology.org/2024.nlp4science-1.10/
- **Description:** 用于 data-driven hypothesis generation 的原始 HypoGeniC framework

**BibTeX:**
```bibtex
@inproceedings{zhou2024hypothesisgenerationlargelanguage,
      title={Hypothesis Generation with Large Language Models}, 
      author={Yangqiaoyu Zhou and Haokun Liu and Tejes Srivastava and Hongyuan Mei and Chenhao Tan},
      booktitle = {Proceedings of EMNLP Workshop of NLP for Science},
      year={2024},
      url={https://aclanthology.org/2024.nlp4science-1.10/},
}
```

## 其他资源

### Official Links

- **GitHub Repository:** https://github.com/ChicagoHAI/hypothesis-generation
- **PyPI Package:** https://pypi.org/project/hypogenic/
- **License:** MIT License
- **Issues & Support:** https://github.com/ChicagoHAI/hypothesis-generation/issues

### Example Datasets

Clone these repositories for ready-to-use examples：

```bash
# HypoGeniC examples (data-driven only)
git clone https://github.com/ChicagoHAI/HypoGeniC-datasets.git ./data

# HypoRefine/Union examples (literature + data)
git clone https://github.com/ChicagoHAI/Hypothesis-agent-datasets.git ./data
```

### Community & Contributions

- **Contributors:** 7+ active contributors
- **Stars:** 89+ on GitHub
- **Topics:** research-tool, interpretability, hypothesis-generation, scientific-discovery, llm-application

如需贡献或提问，请访问 GitHub repository 并查看 issues page。

## Local Resources

### references/

`config_template.yaml` - 带所有 required prompt templates 和 parameters 的完整 example configuration file。包括：
- Task configuration 的完整 YAML structure
- 所有 methods 的 example prompt templates
- Placeholder variable documentation
- Role-based prompt examples

### scripts/

Scripts directory 可用于：
- Custom data preparation utilities
- Format conversion tools
- Analysis and evaluation scripts
- 与 external tools 集成

### assets/

Assets directory 可用于：
- Example datasets 和 templates
- Sample hypothesis banks
- Visualization outputs
- Documentation supplements
