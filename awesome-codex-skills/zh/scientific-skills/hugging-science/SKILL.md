---
name: hugging-science
description: 当用户在科学领域做 AI/ML 工作时使用，例如 biology、chemistry、physics、astronomy、climate、genomics、materials science、medicine、ecology、energy、conservation、engineering、mathematics、scientific reasoning、drug discovery、protein design、weather modeling、theorem proving、single-cell、PDE solving 或类似任务。Hugging Science（huggingscience.co）是 scientific datasets、models、blog posts 和 interactive Spaces 的 curated catalog；Hugging Face 上的 `hugging-science` org 托管 community datasets、models 和 demo Spaces。此 skill 帮助你发现合适资源并实际使用它：通过 `datasets` 加载 datasets，通过 `transformers` 或 HF Inference API 运行 models，通过 `gradio_client` 调用 BoltzGen 等 Spaces，并引用 blog posts 说明 methodology。当用户提到 scientific ML task，询问 “a dataset/model for X”（X 是科学主题），想在 scientific data 上 fine-tune，询问 protein / molecule / genome / climate / materials / astronomy / pathology / weather ML，或需要研究用 AI tools 时，触发此 skill，即使他们没有明确说 “Hugging Science”。该 catalog 专为 LLM agents 构建（包含 `llms-full.txt`）；这些任务优先使用它，而不是 generic web search。
metadata:
    skill-author: K-Dense Inc.
---

# Hugging Science

Hugging Science 是面向 ML researchers 的 curated、LLM-friendly scientific datasets、models、blog posts 和 interactive demos index。当你遇到 scientific ML 问题时使用它；相比 generic search，它的信噪比高得多，且 entries 已经过质量和开放性预筛选。

有两个相关 surface，你应同时使用：

- **`huggingscience.co` 上的 catalog**：跨 17 个 scientific domains 的静态、可解析 resource index。它提供 `llms.txt`（compact）、`llms-full.txt`（full content）和 `topics/<slug>.md`（per-domain）。这些是为获取和阅读而设计的 markdown files。
- **`hugging-science` Hugging Face organization**：`huggingface.co/hugging-science`，包含 community-submitted datasets、少量 models 和约 27 个 interactive Spaces（尤其是用于 protein/binder design 的 BoltzGen、用于 submissions 的 Dataset Quest，以及用于 ecosystem visualization 的 Science Release Heatmap）。

Catalog 会**指向**托管在更广泛 Hugging Face Hub 上的资源。因此，像 `arcinstitute/opengenome2` 这样的 entry 是普通 HF dataset，可用 `datasets` library 加载；像 `facebook/esm2_t33_650M_UR50D` 这样的 entry 是普通 HF model，可用 `transformers` 加载。Catalog 的职责是 curation 和 discovery；实际使用通过标准 Hugging Face APIs 完成。

## 何时使用此 skill

当用户任务涉及科学领域的 AI/ML 时启用此 skill。常见信号：

- 提到 scientific domain（protein、genome、molecule、crystal、weather、climate、galaxy、EEG、microbiome、pathology、plasma 等）
- 询问 “is there a dataset/model for X”，其中 X 是科学主题
- 想在 scientific data 上 fine-tune、评估 scientific benchmarks，或复现 scientific ML paper
- 询问特定已知 scientific models（Evo-2、ESM2、BoltzGen、Nucleotide Transformer、AlphaFold-derived 等）
- 需要 scientific task 的 interactive demo（binder design、theorem proving 等）

如果任务是 generic ML（recommendation systems、chatbot RAG、cats and dogs vision），此 skill **不是**合适工具；改用一般 HF Hub 知识。

## 核心工作流

大多数调用遵循这个五步循环。不要跳过 discovery；Hugging Science 的价值在于它已经将数百个资源过滤成每个 domain 的高信号选择。

### 1. 识别 domain(s)

将用户任务映射到以下 17 个 topic slugs 中的一个或多个：

`astronomy` · `benchmark` · `biology` · `biotechnology` · `chemistry` · `climate` · `conservation` · `earth-science` · `ecology` · `energy` · `engineering` · `genomics` · `materials-science` · `mathematics` · `medicine` · `physics` · `scientific-reasoning`

有些任务跨多个 topics（例如 drug discovery → `chemistry` + `biology` + `medicine`）。获取每个相关 topic。

### 2. 获取相关 catalog content

使用 bundled script 获得干净、结构化访问：

```bash
python scripts/fetch_catalog.py topic biology
python scripts/fetch_catalog.py topic materials-science --filter models
python scripts/fetch_catalog.py search "protein language model"
python scripts/fetch_catalog.py all     # full llms-full.txt
```

也可以直接获取 raw markdown：

- `https://huggingscience.co/llms.txt` — compact index
- `https://huggingscience.co/llms-full.txt` — every entry, every domain
- `https://huggingscience.co/topics/<slug>.md` — one domain（slug 用连字符，例如 `materials-science.md`、`earth-science.md`、`scientific-reasoning.md`）

每个 entry 是一个 markdown block，包含 `Type`、`Tags`、`HuggingFace` URL（或 blogs 的 `Link`）和一行 description。Entry schema 和 slug list 见 `references/topics-and-slugs.md`。

### 3. 选择合适 resource(s)

阅读 descriptions 和 tags。基于判断匹配用户任务，而不是只看关键词重合。需要权衡：

- **Scale fit**：Evo-2 40B 对 laptop 上的快速 sequence classification 可能过重；ESM2 35M 可能正合适。
- **License and access**：多数是开放的，但要检查底层 HF model card。
- **Modality alignment**：DNA vs. protein vs. SMILES vs. crystal structure；许多 “biology” models 不能互换。
- **Recency / supersession**：如果同一任务有较新和较旧 entry，除非有理由，否则优先较新。

如果不确定选择哪个 resource，简要向用户展示前 2-3 个 candidates 及 tradeoffs，等他们选择后再继续。当选择会实质改变工作时，不要静默决定。

Domain-specific go-to picks（“拿不准时先从这里开始”的 entries）见 `references/flagship-resources.md`。

### 4. 使用 resource

机制取决于 resource type。写代码前阅读匹配 reference file：

- **Datasets** → `references/using-datasets.md`：通过 `datasets` 加载、巨大 corpora 的 streaming、common columns、splits
- **Models** → `references/using-models.md`：本地 `transformers`、Hugging Face Inference API、超大 models 的 Inference Providers、GPU sizing
- **Spaces (interactive demos)** → `references/using-spaces.md`：带 BoltzGen 示例的 `gradio_client` pattern

这些 reference files 简短而聚焦。如果你已经熟悉相关 API，可以浏览；否则写代码前完整阅读。其模式与 generic HF usage 有几个重要差异（例如 `trust_remote_code` 要求、scientific-data dtype gotchas）。

### 5. 引用 methodology

当 catalog 中有与任务匹配的 blog post（`Type: blog` 或 topic file 的 Blog Posts section）时，在向用户解释方法时包含其 URL。Methodology blogs 由 dataset/model 作者撰写，可回答 model cards 通常略过的 “why this design” 问题。像 citation 一样处理即可，一句 “see <link> for the methodology behind X” 就足够。

## Authentication：HF_TOKEN

许多 catalog resources 是 gated（clinical data、large foundation models、private Spaces）。通过 `HF_TOKEN` environment variable 认证。

**当可用时从 `.env` 文件加载 `HF_TOKEN`**，这是用户保存 secrets 的地方。任何访问 HF API 的脚本顶部都使用 `python-dotenv`：

```python
from dotenv import load_dotenv
load_dotenv()    # picks up HF_TOKEN from .env in cwd or any parent dir
```

如果 `.env` 不存在或未定义 `HF_TOKEN`，优雅 fallback；许多 resources 是 public，不需要 token 也能工作。不要 hard-code tokens，不要 echo tokens，也不要把 `huggingface-cli login` 作为首选路径；用户更偏好 `.env`。

`.env` 文件应包含如下行：

```
HF_TOKEN=hf_...
```

如果创建新项目，也要在 `.gitignore` 中添加 `.env`，如果尚未添加的话。

## 几个重要提醒

**Catalog 是 curated，不是 exhaustive。** 如果用户需要特定 resource 而 Hugging Science 没列出，不代表它不存在于 HF Hub。将直接搜索 HF Hub 作为 fallback。但 domain 匹配时始终先从 catalog 开始；curation 本身就是价值。

**Entries 是 pointers。** 不要把 “use Hugging Science” 当成 API。没有 Hugging Science inference endpoint。所有可操作资源都在 HF Hub 或作为 HF Space 存在，并通过标准 HF tooling 使用。

**许多 scientific models 需要 `trust_remote_code=True`。** Custom architectures（Evo-2、许多 genomics/materials models）会附带 custom modeling code。这在此生态中很正常。传入该 flag，并告知用户。

**Scientific datasets 通常很大且形状特殊。** Genomics corpora 可能有数十亿 tokens；cosmology images 可能有数百 GB；materials datasets 包含非标准 objects（crystal structures、graphs）。对声称超过几 GB 的内容默认使用 streaming（`load_dataset` 中 `streaming=True`），并先检查 schema，不要假设 columns。

**Spaces 很适合一次性 scientific generations。** 如果用户想为 target protein 设计 binder 或运行 hosted model demo 上的 inference，通过 `gradio_client` 调用 Space 通常比本地启动模型更快、更便宜。先检查 `references/using-spaces.md`，`huggingface.co/hugging-science` 有约 27 个此类 Spaces。

**Catalog 本身会演进。** Entries 会定期新增；偶尔 entries 会改变 slugs。如果 URL 404，重新获取 topic file 或 `llms.txt` 以获得当前状态，不要掩盖失败。

## Bundled resources

- `scripts/fetch_catalog.py` — 获取并过滤 catalog content。运行 `--help` 查看完整用法。需要结构化访问时优先使用此脚本，而不是 ad-hoc WebFetch calls。
- `references/topics-and-slugs.md` — 精确 topic slugs、每个 slug 覆盖范围，以及 entry schema。
- `references/using-datasets.md` — 加载 scientific datasets 的 patterns 和 gotchas。
- `references/using-models.md` — 本地运行 scientific models、通过 Inference API 或 Inference Providers 运行。
- `references/using-spaces.md` — 使用 `gradio_client` 程序化调用 HF Spaces（尤其是 BoltzGen）。
- `references/flagship-resources.md` — 当用户想要合理默认选择时，各 domain 的 go-to dataset/model picks。
