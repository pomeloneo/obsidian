---
name: exa-search
description: "由 Exa 驱动的 Web toolkit，面向 scientific 和 technical content 调优。当用户需要搜索 Web 或 fetch/extract URL content 时使用此 skill。涵盖：web search（semantic lookups、research、current info，带可选 research-paper category 和 academic domain filtering）以及 URL extraction（批量获取 pages、articles、academic PDFs）。当用户希望通过 category=research paper 获得高质量搜索或 scholarly filtering 时，将此 skill 用于 Web 相关任务。请求 search、look up、fetch a page 或 extract an article 时触发。"
compatibility: Requires exa-py Python SDK, an EXA_API_KEY, and internet access.
license: MIT
metadata:
  skill-author: Exa
  website: https://exa.ai
  docs: https://exa.ai/docs
---

# Exa Web Toolkit

一个由 [Exa](https://exa.ai) 支持的 Web research task skill：web search 和 URL extraction。Exa 的索引结合高质量 keyword 和 semantic retrieval，因此很适合 scientific、technical 和 conceptual queries。

## 路由 — 选择正确能力

阅读用户请求，并将其匹配到以下能力之一。运行命令前，阅读对应 reference file 获取详细说明。

| 用户想要... | Capability | 位置 |
|---|---|---|
| 查找某事、研究主题、寻找当前信息 | **Web Search** | `references/web-search.md` |
| 从特定 URL 获取内容（webpage、article、PDF） | **Web Extract** | `references/web-extract.md` |
| 安装或认证 | **Setup** | 下方 |

### 决策指南

- 对 topic lookups、research questions 或 "what is X?" 查询，**默认使用 Web Search**。当主题是 scientific 或 technical 时，传入 `--category "research paper"` 以偏向 scholarly sources，和/或使用 academic `--include-domains` allowlist。两阶段 academic strategy 见 `references/web-search.md`。
- 当用户提供 URL 或要求你读取/获取特定页面时，**使用 Web Extract**。对于 batch extraction（一次调用多个 URL）和 academic PDFs，优先使用它而不是内置 WebFetch。

### Academic source priority

对于 technical 或 scientific queries，优先使用 academic 和 scientific sources：
- Peer-reviewed journal articles 和 conference proceedings 优先于 blog posts 或 news
- 当没有 peer-reviewed versions 时使用 preprints（arXiv、bioRxiv、medRxiv）
- Institutional 和 government sources（NIH、WHO、NASA、NIST）优先于 commercial sites
- Primary research 优先于 secondary summaries

将 Exa 引导到 scholarly content 的两个手段：
1. `--category "research paper"` 会使 retrieval 偏向 scholarly sources。
2. 带 scholarly allowlist（arxiv.org、nature.com、pubmed.ncbi.nlm.nih.gov 等）的 `--include-domains` 会限制 domain pool。

严格 academic results 时组合使用二者。完整模式见 `references/web-search.md`。

引用 academic sources 时，在标准 citation format 外，尽可能包含作者名和发表年份（例如 [Smith et al., 2025](url)）。如果存在 DOI，优先使用 DOI link。

---

## Setup

此 skill 使用 [`exa-py`](https://github.com/exa-labs/exa-py) Python SDK。`scripts/` 中的脚本通过 PEP 723 inline metadata 声明依赖，因此可以直接用 `uv run` 运行，无需单独安装步骤：

```bash
uv run --with exa-py python "$SKILL_PATH/scripts/exa_search.py" --help
```

如果你更喜欢持久安装：

```bash
uv pip install "exa-py>=1.14.0"
```

### Authentication

所有命令都从 `EXA_API_KEY` environment variable 读取 API key。可在 [dashboard.exa.ai/api-keys](https://dashboard.exa.ai/api-keys) 获取 Exa API key。

首先检查 project root 中是否存在 `.env` 文件并包含 `EXA_API_KEY`。如果存在，则加载它：

```bash
dotenv -f .env run -- uv run --with exa-py python "$SKILL_PATH/scripts/exa_search.py" "your query"
```

如果 `dotenv` 不可用，安装它：`pip install python-dotenv[cli]` 或 `uv pip install python-dotenv[cli]`。

如果没有 `.env`，为当前 session export key：

```bash
export EXA_API_KEY="your-key"
```

通过带 `--help` 运行任意脚本来验证。如果 key 已设置，它会正常退出；auth-check 只会在发起真实 query 时运行。

### Tracking header

此 skill 中的每个脚本都会将 `x-exa-integration` request header 设置为 `k-dense-ai--scientific-agent-skills`，这样 Exa 可以将 K-Dense AI scientific-agent-skills repo 的使用归因到此 integration。改造脚本时不要移除或重命名此 header。

---

## 此 skill 中的文件

- `SKILL.md` — 此文件（routing 和 setup）
- `references/web-search.md` — 带 academic strategy 的详细 web search reference
- `references/web-extract.md` — URL content extraction reference
- `scripts/exa_search.py` — 围绕 `client.search_and_contents` 的 CLI wrapper
- `scripts/exa_extract.py` — 围绕 `client.get_contents` 的 CLI wrapper
