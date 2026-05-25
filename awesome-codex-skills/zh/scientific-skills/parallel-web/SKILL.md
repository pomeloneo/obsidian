---
name: parallel-web
description: "由 parallel-cli 驱动的一体化 web toolkit，重点面向 academic and scientific sources。每当用户需要搜索 web、获取/提取 URL content、用 web-sourced fields 丰富数据，或运行 deep research reports 时使用此 skill。覆盖：web search（快速查询、研究、当前信息，优先考虑 peer-reviewed papers、preprints 和 scholarly databases）、URL extraction（获取网页、文章、academic PDFs）、bulk data enrichment（从 web 向 CSV/lists 添加字段）以及 deep research（基于学术文献的详尽多来源报告）。也处理 setup、status checks 和 result retrieval。对任何 web-related task 都使用此 skill，即使用户没有明确提到 'parallel' 或 'web'。如果他们想查找信息、获取页面、丰富数据集、调查主题、查找学术论文、检查引用或审阅科学文献，就使用此 skill。"
compatibility: 需要 parallel-cli 和 internet access。
metadata:
  author: K-Dense, Inc.
---

# Parallel Web Toolkit

用于所有 web-powered tasks 的统一 skill：搜索、提取、丰富和研究，并默认优先使用 academic and scientific sources。

## 路由 — 选择合适能力

阅读用户请求，并将其匹配到下面的某项能力。对于 web search、extract、enrichment 和 deep research，请阅读对应 reference file 获取详细说明。

| 用户想要... | 能力 | 位置 |
|---|---|---|
| 查找信息、研究主题、查找当前信息 | **Web Search** | `references/web-search.md` |
| 从特定 URL（webpage、article、PDF）获取内容 | **Web Extract** | `references/web-extract.md` |
| 向公司/人物/产品列表添加 web-sourced fields | **Data Enrichment** | `references/data-enrichment.md` |
| 获取详尽的多来源报告（用户说 "deep research"、"exhaustive"、"comprehensive"） | **Deep Research** | `references/deep-research.md` |
| 安装或认证 parallel-cli | **Setup** | 下方 |
| 检查正在运行的 research/enrichment task 状态 | **Status** | 下方 |
| 通过 run ID 取回已完成的 research results | **Result** | 下方 |

### 决策指南

- 对单次查找、研究问题或 "what is X?" 查询，**默认使用 Web Search**。它速度快且成本低。当查询涉及科学或技术主题时，包含 academic domains（见 `references/web-search.md`），以便在常规结果之外呈现 peer-reviewed 和 preprint sources。
- 当用户提供 URL 或要求你阅读/获取特定页面时，**使用 Web Extract**。优先使用它，而不是内置 WebFetch tool。它特别适合从 academic PDFs、preprint servers 和 journal articles 中提取 full text。
- 当用户有 **multiple entities**（CSV、公司/人物/产品列表，甚至简短 inline list）并希望为每一项查找或添加同类信息时，**使用 Data Enrichment**。关键信号是在一组项目上重复查询，例如 "find the CEO for each of these companies" 或 "get the founding year for Apple, Stripe, and Anthropic." 即使用户没有说 "enrich"，只要任务是对多个实体应用同一查询，就使用 `parallel-cli enrich`。不要为此循环使用 Web Search -- enrichment pipeline 会自动处理 batching、parallelism 和 structured output。
- 只有当用户明确要求 deep、exhaustive 或 comprehensive research 时，**才使用 Deep Research**。它比 Web Search 慢 10-100 倍且成本更高，绝不要默认使用。Deep research 尤其适合 literature reviews 和 multi-paper synthesis。
- 如果运行任何命令时找不到 `parallel-cli`，遵循下方 Setup 部分。

### Academic source 优先级

在所有能力中，当查询具有技术或科学性质时，优先使用 academic and scientific sources。这意味着：
- 相比 blog posts 或 news articles，优先使用 peer-reviewed journal articles 和 conference proceedings
- 当没有 peer-reviewed versions 时，使用 preprints（arXiv、bioRxiv、medRxiv）
- 相比商业网站，优先使用机构和政府来源（NIH、WHO、NASA、NIST）
- 相比二级摘要，优先使用 primary research

引用 academic sources 时，除标准引用格式外，在可用时包含作者姓名和发表年份（例如 [Smith et al., 2025](url)）。如果存在 DOI，优先使用 DOI link。

## 上下文串联

若干能力通过 `interaction_id` 支持多轮上下文。当 research 或 enrichment task 完成时，会返回一个 `interaction_id`。如果用户提出与该任务相关的后续问题，传入 `--previous-interaction-id` 来自动延续上下文。这样可以避免重复说明已找到的内容。

---

## Setup

如果未安装 `parallel-cli`，请安装并认证：

```bash
curl -fsSL https://parallel.ai/install.sh | bash
```

如果无法通过这种方式安装，则改用 uv：

```bash
uv tool install "parallel-web-tools[cli]"
```

然后进行认证。首先检查项目根目录中是否存在 `.env` 文件且其中包含 `PARALLEL_API_KEY`。如果有，用 `dotenv` 加载：

```bash
dotenv -f .env run parallel-cli auth
```

如果 `dotenv` 不可用，用 `pip install python-dotenv[cli]` 或 `uv pip install python-dotenv[cli]` 安装。

如果没有 `.env` 文件，或其中不包含该 key，则回退到交互式登录：

```bash
parallel-cli login
```

也可以手动设置 key：`export PARALLEL_API_KEY="your-key"`

使用以下命令验证：

```bash
parallel-cli auth
```

如果安装后仍找不到 `parallel-cli`，将 `~/.local/bin` 加入 PATH。

## 检查任务状态

```bash
parallel-cli research status "$RUN_ID" --json
```

向用户报告当前状态（running、completed、failed 等）。

## 获取已完成结果

```bash
parallel-cli research poll "$RUN_ID" --json
```

以清晰、有组织的格式呈现结果。
