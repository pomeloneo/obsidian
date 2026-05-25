---
name: research-lookup
description: '使用 parallel-cli search（主要、快速 web search）、Parallel Chat API（deep research）或 Perplexity sonar-pro-search（academic paper searches）查找当前研究信息。自动将查询路由到最佳 backend。用于查找 papers、收集 research data 和验证 scientific information。注意：query text 会传输到 api.parallel.ai（PARALLEL_API_KEY），academic searches 会传输到 openrouter.ai（OPENROUTER_API_KEY）。'
allowed-tools: Read Write Edit Bash
license: MIT license
compatibility: parallel-cli required (primary); PARALLEL_API_KEY and OPENROUTER_API_KEY optional for deep/academic backends
metadata:
    skill-author: K-Dense Inc.
---

# Research Information Lookup

## 概述

此 skill 提供带有 **intelligent backend routing** 的实时 research information lookup：

- **parallel-cli search**（parallel-web skill）：所有 research queries 的**主要和默认 backend**。快速、成本有效的 web search，并优先考虑 academic sources。使用 `parallel-cli search` 和 `--include-domains` 搜索 scholarly sources。
- **Parallel Chat API**（`core` model）：用于复杂、多源 deep research 的 secondary backend，需要 extended synthesis（60 秒-5 分钟 latency）。仅在明确需要时使用。
- **Perplexity sonar-pro-search**（via OpenRouter）：仅用于对 scholarly database access 要求关键的 academic-specific paper searches。

此 skill 会自动检测 query type，并路由到最佳 backend。

## 何时使用此 Skill

当你需要以下内容时使用此 skill：

- **Current Research Information**：最新 studies、papers 和 findings
- **Literature Verification**：根据当前研究检查 facts、statistics 或 claims
- **Background Research**：为 scientific writing 收集 context 和 supporting evidence
- **Citation Sources**：查找可引用的 relevant papers 和 studies
- **Technical Documentation**：查找 specifications、protocols 或 methodologies
- **Market/Industry Data**：当前 statistics、trends、competitive intelligence
- **Recent Developments**：emerging trends、breakthroughs、announcements

## 使用 Scientific Schematics 增强视觉表达

**使用此 skill 创建文档时，应始终考虑添加 scientific diagrams 和 schematics，以增强 visual communication。**

如果你的文档尚未包含 schematics 或 diagrams：
- 使用 **scientific-schematics** skill 生成 AI-powered publication-quality diagrams
- 只需用自然语言描述所需 diagram

```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

---

## Automatic Backend Selection

此 skill 会根据内容自动将 queries 路由到最佳 backend：

### Routing Logic

```
Query arrives
    |
    +-- Contains academic keywords? (papers, DOI, journal, peer-reviewed, etc.)
    |       YES --> Perplexity sonar-pro-search (academic search mode)
    |
    +-- Needs deep multi-source synthesis? (user says "deep research", "exhaustive")
    |       YES --> Parallel Chat API (core model, 60s-5min)
    |
    +-- Everything else (general research, market data, technical info, analysis)
            --> parallel-cli search (fast, default)
```

### Default: parallel-cli search（parallel-web skill）

**所有标准 research queries 的主要 backend。** 快速、成本有效，并支持 academic source prioritization。

对于 scientific/technical queries，运行两次搜索以确保 academic coverage：

```bash
# 1. Academic-focused search
parallel-cli search "your research query" -q "keyword1" -q "keyword2" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --include-domains "scholar.google.com,arxiv.org,pubmed.ncbi.nlm.nih.gov,semanticscholar.org,biorxiv.org,medrxiv.org,ncbi.nlm.nih.gov,nature.com,science.org,ieee.org,acm.org,springer.com,wiley.com,cell.com,pnas.org,nih.gov" \
  -o sources/research_<topic>-academic.json

# 2. General search (catches non-academic sources)
parallel-cli search "your research query" -q "keyword1" -q "keyword2" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/research_<topic>-general.json
```

Options：
- `--after-date YYYY-MM-DD` 用于 time-sensitive queries
- `--include-domains domain1.com,domain2.com` 用于限制到特定 sources

合并结果，并优先展示 academic sources。对于 non-scientific queries，一次 general search 通常足够。

所有其他 queries 默认路由到这里，包括：

- General research questions
- Market and industry analysis
- Technical information and documentation
- Current events and recent developments
- Comparative analysis
- Statistical data retrieval
- Fact-checking and verification

### Academic Keywords（路由到 Perplexity）

包含以下术语的 queries 会路由到 Perplexity 进行 academic-focused search：

- Paper finding：`find papers`, `find articles`, `research papers on`, `published studies`
- Citations：`cite`, `citation`, `doi`, `pubmed`, `pmid`
- Academic sources：`peer-reviewed`, `journal article`, `scholarly`, `arxiv`, `preprint`
- Review types：`systematic review`, `meta-analysis`, `literature search`
- Paper quality：`foundational papers`, `seminal papers`, `landmark papers`, `highly cited`

### Deep Research（路由到 Parallel Chat API）

仅在用户明确要求 deep、exhaustive 或 comprehensive research 时使用。它比 parallel-cli search 慢得多且成本更高。

### Manual Override

你可以强制使用特定 backend：

```bash
# Force parallel-cli search (fast web search)
parallel-cli search "your query" -q "keyword" --json --max-results 10 -o sources/research_<topic>.json

# Force Parallel Deep Research (slow, exhaustive)
python research_lookup.py "your query" --force-backend parallel

# Force Perplexity academic search
python research_lookup.py "your query" --force-backend perplexity
```

---

## 核心能力

### 1. General Research Queries（parallel-cli search — DEFAULT）

**主要 backend。** 通过 parallel-web skill 提供快速、成本有效的 web search，并优先考虑 academic sources。

```
Query Examples:
- "Recent advances in CRISPR gene editing 2025"
- "Compare mRNA vaccines vs traditional vaccines for cancer treatment"
- "AI adoption in healthcare industry statistics"
- "Global renewable energy market trends and projections"
- "Explain the mechanism underlying gut microbiome and depression"
```

```bash
# Example: research on CRISPR advances
parallel-cli search "Recent advances in CRISPR gene editing 2025" \
  -q "CRISPR" -q "gene editing" -q "2025" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --include-domains "scholar.google.com,arxiv.org,pubmed.ncbi.nlm.nih.gov,nature.com,science.org,cell.com,pnas.org,nih.gov" \
  -o sources/research_crispr_advances-academic.json

parallel-cli search "Recent advances in CRISPR gene editing 2025" \
  -q "CRISPR" -q "gene editing" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/research_crispr_advances-general.json
```

**Response includes：**
- 来自 search results 的带 inline citations 的 synthesized findings
- 优先展示 academic sources（peer-reviewed、preprints）
- 具体 facts、numbers 和 dates
- Sources section，按类型列出所有 referenced URLs

### 2. Academic Paper Search（Perplexity sonar-pro-search）

**用于 academic-specific queries。** 优先考虑 scholarly databases 和 peer-reviewed sources。当 queries 明确要求 papers、citations 或 DOIs 时使用。

```
Query Examples:
- "Find papers on transformer attention mechanisms in NeurIPS 2024"
- "Foundational papers on quantum error correction"
- "Systematic review of immunotherapy in non-small cell lung cancer"
- "Cite the original BERT paper and its most influential follow-ups"
- "Published studies on CRISPR off-target effects in clinical trials"
```

**Response includes：**
- Academic literature 中 key findings 的 summary
- 5-8 条 high-quality citations，含 authors、titles、journals、years、DOIs
- Citation counts 和 venue tier indicators
- Key statistics 和 methodology highlights
- Research gaps 和 future directions

### 3. Deep Research（Parallel Chat API — only on request）

**仅当用户明确要求 deep/exhaustive research 时使用。** 通过 Chat API（`core` model）提供 comprehensive、multi-source synthesis。Latency 为 60 秒-5 分钟。

```
Query Examples:
- "Deep research on the current state of quantum computing error correction"
- "Exhaustive analysis of mRNA vaccine platforms for cancer immunotherapy"
```

### 4. Technical and Methodological Information

使用 parallel-cli search（默认）进行快速查找：

```bash
parallel-cli search "Western blot protocol for protein detection" \
  -q "western blot" -q "protocol" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/research_western_blot.json
```

### 5. Statistical and Market Data

使用 parallel-cli search（默认）获取当前数据：

```bash
parallel-cli search "Global AI market size and growth projections 2025" \
  -q "AI market" -q "statistics" -q "growth" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --after-date 2024-01-01 \
  -o sources/research_ai_market.json
```

---

## Paper Quality and Popularity Prioritization

**关键**：搜索 papers 时，始终优先考虑 high-quality、influential papers。

### Citation-Based Ranking

| Paper Age | Citation Threshold | Classification |
|-----------|-------------------|----------------|
| 0-3 years | 20+ citations | Noteworthy |
| 0-3 years | 100+ citations | Highly Influential |
| 3-7 years | 100+ citations | Significant |
| 3-7 years | 500+ citations | Landmark Paper |
| 7+ years | 500+ citations | Seminal Work |
| 7+ years | 1000+ citations | Foundational |

### Venue Quality Tiers

**Tier 1 - Premier Venues**（始终优先）：
- **General Science**：Nature, Science, Cell, PNAS
- **Medicine**：NEJM, Lancet, JAMA, BMJ
- **Field-Specific**：Nature Medicine, Nature Biotechnology, Nature Methods
- **Top CS/AI**：NeurIPS, ICML, ICLR, ACL, CVPR

**Tier 2 - High-Impact Specialized**（强烈优先）：
- Impact Factor > 10 的 journals
- Subfields 中的 top conferences（EMNLP、NAACL、ECCV、MICCAI）

**Tier 3 - Respected Specialized**（相关时纳入）：
- Impact Factor 5-10 的 journals

---

## Technical Integration

### Prerequisites

```bash
# Primary backend (parallel-cli) - REQUIRED
# Install parallel-cli if not already available:
curl -fsSL https://parallel.ai/install.sh | bash
# Or: uv tool install "parallel-web-tools[cli]"

# Authenticate:
parallel-cli auth
# Or: export PARALLEL_API_KEY="your_parallel_api_key"
```

### Environment Variables

```bash
# Primary backend (parallel-cli search) - REQUIRED
export PARALLEL_API_KEY="your_parallel_api_key"

# Deep research backend (Parallel Chat API) - optional, for deep research only
# Uses the same PARALLEL_API_KEY

# Academic search backend (Perplexity) - optional, for academic paper queries
export OPENROUTER_API_KEY="your_openrouter_api_key"
```

### API Specifications

**parallel-cli search（PRIMARY）：**
- Command：带 `--json` output 的 `parallel-cli search`
- Latency：2-10 秒（fast）
- Output：包含 title、URL、publish_date、excerpts 的 JSON
- Academic domains：使用 `--include-domains` 指定 scholarly sources
- Saves results：使用 `-o filename.json` 便于 follow-up 和 reproducibility

**Parallel Chat API（deep research only）：**
- Endpoint：`https://api.parallel.ai`（OpenAI SDK compatible）
- Model：`core`（60 秒-5 分钟 latency，complex multi-source synthesis）
- Output：带 inline citations 的 Markdown text
- Citations：包含 URLs、reasoning 和 confidence levels 的 research basis
- Rate limits：300 req/min
- Python package：`openai`

**Perplexity sonar-pro-search（academic only）：**
- Model：`perplexity/sonar-pro-search`（via OpenRouter）
- Search mode：Academic（优先 peer-reviewed sources）
- Search context：High（comprehensive research）
- Response time：5-15 秒

### Command-Line Usage

```bash
# Fast web search via parallel-cli (DEFAULT — recommended) — ALWAYS save to sources/
parallel-cli search "your query" -q "keyword1" -q "keyword2" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/research_<topic>.json

# Academic-focused search via parallel-cli — ALWAYS save to sources/
parallel-cli search "your query" -q "keyword1" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --include-domains "scholar.google.com,arxiv.org,pubmed.ncbi.nlm.nih.gov,semanticscholar.org,biorxiv.org,medrxiv.org,nature.com,science.org,cell.com,pnas.org,nih.gov" \
  -o sources/research_<topic>-academic.json

# Time-sensitive search via parallel-cli
parallel-cli search "your query" -q "keyword" \
  --json --max-results 10 --after-date 2024-01-01 \
  -o sources/research_<topic>.json

# Extract full content from a specific URL (use parallel-web extract)
parallel-cli extract "https://example.com/paper" --json

# Force Parallel Deep Research (slow, exhaustive) — via research_lookup.py
python research_lookup.py "your query" --force-backend parallel -o sources/research_<topic>.md

# Force Perplexity academic search — via research_lookup.py
python research_lookup.py "your query" --force-backend perplexity -o sources/papers_<topic>.md

# Auto-routed via research_lookup.py (legacy) — ALWAYS save to sources/
python research_lookup.py "your query" -o sources/research_YYYYMMDD_HHMMSS_<topic>.md

# Batch queries via research_lookup.py — ALWAYS save to sources/
python research_lookup.py --batch "query 1" "query 2" "query 3" -o sources/batch_research_<topic>.md
```

---

## 强制要求：将所有结果保存到 Sources 文件夹

**每个 research-lookup result 都必须保存到项目的 `sources/` folder。**

这是不可协商的。Research results 获取成本高，且对 reproducibility 至关重要。

### Saving Rules

| Backend | `-o` Flag Target | Filename Pattern |
|---------|-----------------|------------------|
| parallel-cli search (default) | `sources/research_<topic>.json` | `research_<brief_topic>.json` or `research_<brief_topic>-academic.json` |
| Parallel Deep Research | `sources/research_<topic>.md` | `research_YYYYMMDD_HHMMSS_<brief_topic>.md` |
| Perplexity (academic) | `sources/papers_<topic>.md` | `papers_YYYYMMDD_HHMMSS_<brief_topic>.md` |
| Batch queries | `sources/batch_<topic>.md` | `batch_research_YYYYMMDD_HHMMSS_<brief_topic>.md` |

### How to Save

**关键：每次 search 都必须使用 `-o` flag 将 results 保存到 `sources/` folder。**

**关键：Saved files 必须保留所有 citations、source URLs 和 DOIs。**

```bash
# parallel-cli search (DEFAULT) — save JSON to sources/
parallel-cli search "Recent advances in CRISPR gene editing 2025" \
  -q "CRISPR" -q "gene editing" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --include-domains "scholar.google.com,arxiv.org,pubmed.ncbi.nlm.nih.gov,nature.com,science.org,cell.com,pnas.org,nih.gov" \
  -o sources/research_crispr_advances-academic.json

parallel-cli search "Recent advances in CRISPR gene editing 2025" \
  -q "CRISPR" -q "gene editing" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/research_crispr_advances-general.json

# Academic paper search via Perplexity — save to sources/
python research_lookup.py "Find papers on transformer attention mechanisms in NeurIPS 2024" \
  -o sources/papers_20250217_143500_transformer_attention.md

# Deep research via Parallel Chat API — save to sources/
python research_lookup.py "AI regulation landscape" --force-backend parallel \
  -o sources/research_20250217_144000_ai_regulation.md

# Batch queries — save to sources/
python research_lookup.py --batch "mRNA vaccines efficacy" "mRNA vaccines safety" \
  -o sources/batch_research_20250217_144500_mrna_vaccines.md
```

### Saved Files 中的 Citation Preservation

每种 output format 以不同方式保留 citations：

| Format | Citations Included | When to Use |
|--------|-------------------|-------------|
| parallel-cli JSON (default) | Full result objects: `title`, `url`, `publish_date`, `excerpts` | Standard use — structured, parseable, fast |
| Text (research_lookup.py) | `Sources (N):` section with `[title] (date) + URL` + `Additional References (N):` with DOIs and academic URLs | Deep research / Perplexity — human-readable |
| JSON (`--json` via research_lookup.py) | Full citation objects: `url`, `title`, `date`, `snippet`, `doi`, `type` | When you need maximum citation metadata from deep research |

**对于 parallel-cli search**，saved JSON files 包含每条 result 的 title、URL、publish date 和 content excerpts。
**对于 Parallel Chat API backend**，saved files 包含 research report + Sources list（title、URL）+ Additional References（DOIs、academic URLs）。
**对于 Perplexity backend**，saved files 包含 academic summary + Sources list（title、date、URL、snippet）+ Additional References（DOIs、academic URLs）。

**需要以下能力时使用 `--json`：**
- 以编程方式解析 citation metadata
- 为 BibTeX generation 保留完整 DOI 和 URL data
- 保持 structured citation objects 以便 cross-referencing

### 为什么保存所有内容

1. **Reproducibility**：每条 citation 和 claim 都可追溯到原始 research source
2. **Context Window Recovery**：如果 context 被压缩，可重新读取 saved results 而无需重新 query
3. **Audit Trail**：`sources/` folder 记录所有 research information 的收集方式
4. **Reuse Across Sections**：多个 sections 可引用同一 saved research，避免重复 queries
5. **Cost Efficiency**：新 API calls 前先检查 `sources/` 中的 existing results
6. **Peer Review Support**：Reviewers 可验证每条 citation 背后的 research

### 发起新 Query 前，先检查 Sources

调用 `research_lookup.py` 前，检查是否已有相关 result：

```bash
ls sources/  # Check existing saved results
```

如果 prior lookup 已覆盖同一 topic，重新读取 saved file，而不是发起新的 API call。

### Logging

保存 research results 时，始终记录：

```
[HH:MM:SS] SAVED: Research lookup to sources/research_20250217_143000_crispr_advances.md (3,800 words, 8 citations)
[HH:MM:SS] SAVED: Paper search to sources/papers_20250217_143500_transformer_attention.md (6 papers found)
```

---

## 与 Scientific Writing 的集成

此 skill 通过以下方式增强 scientific writing：

1. **Literature Review Support**：为 introduction 和 discussion 收集当前研究 — **save to `sources/`**
2. **Methods Validation**：根据当前 standards 验证 protocols — **save to `sources/`**
3. **Results Contextualization**：将 findings 与 recent similar studies 比较 — **save to `sources/`**
4. **Discussion Enhancement**：用 latest evidence 支持 arguments — **save to `sources/`**
5. **Citation Management**：提供 properly formatted citations — **save to `sources/`**

## Complementary Tools

| Task | Tool |
|------|------|
| General web search (fast) | `parallel-cli search` (built into this skill) |
| Academic-focused web search | `parallel-cli search --include-domains` (built into this skill) |
| URL content extraction | `parallel-cli extract` (parallel-web skill) |
| Deep research (exhaustive) | `research-lookup` via Parallel Chat API or `parallel-web` deep research |
| Academic paper search | `research-lookup` (auto-routes to Perplexity) |
| Google Scholar search | `citation-management` skill |
| PubMed search | `citation-management` skill |
| DOI to BibTeX | `citation-management` skill |
| Metadata verification | `parallel-cli extract` (parallel-web skill) |

---

## Error Handling and Limitations

**Known Limitations：**
- parallel-cli search：需要已安装并 authenticated 的 `parallel-cli`
- Parallel Chat API（core model）：complex queries 可能需要最多 5 分钟
- Perplexity：存在 information cutoff，可能无法访问 paywalls 后的 full text
- 所有 backends：无法访问 proprietary 或 restricted databases

**Fallback Behavior：**
- 如果找不到 `parallel-cli`，使用 `curl -fsSL https://parallel.ai/install.sh | bash` 或 `uv tool install "parallel-web-tools[cli]"` 安装
- 如果 parallel-cli search 返回结果不足，则 fallback 到 Perplexity 或 Parallel Chat API
- 如果 selected backend 的 API key 缺失，则尝试另一个 backend
- 如果所有 backends 失败，返回 structured error response
- 如果 initial response 不足，重新表述 query 以获得更好结果

---

## Usage Examples

### Example 1: General Research（路由到 parallel-cli search）

**Query**："Recent advances in transformer attention mechanisms 2025"

**Backend**：parallel-cli search（default, fast）

**Commands**：
```bash
parallel-cli search "Recent advances in transformer attention mechanisms 2025" \
  -q "transformer" -q "attention" -q "2025" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --include-domains "arxiv.org,semanticscholar.org,nature.com,science.org,ieee.org,acm.org" \
  -o sources/research_transformer_attention-academic.json

parallel-cli search "Recent advances in transformer attention mechanisms 2025" \
  -q "transformer" -q "attention" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/research_transformer_attention-general.json
```

**Response**：来自 academic 和 general sources 的 synthesized findings，带 inline citations，覆盖 recent papers、key innovations 和 performance benchmarks。

### Example 2: Academic Paper Search（路由到 Perplexity）

**Query**："Find papers on CRISPR off-target effects in clinical trials"

**Backend**：Perplexity sonar-pro-search（academic mode）

**Response**：5-8 篇 high-impact papers 的 curated list，含完整 citations、DOIs、citation counts 和 venue tier indicators。

### Example 3: Comparative Analysis（路由到 parallel-cli search）

**Query**："Compare and contrast mRNA vaccines vs traditional vaccines for cancer treatment"

**Backend**：parallel-cli search（default, fast）

**Response**：基于多个 web sources 的 synthesized comparison，带 inline citations、structured analysis 和 evidence quality notes。

### Example 4: Market Data（路由到 parallel-cli search）

**Query**："Global AI adoption in healthcare statistics 2025"

**Backend**：parallel-cli search（default, fast）

```bash
parallel-cli search "Global AI adoption in healthcare statistics 2025" \
  -q "AI healthcare" -q "adoption statistics" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --after-date 2024-01-01 \
  -o sources/research_ai_healthcare_adoption.json
```

**Response**：当前 market data、adoption rates、growth projections 和 regional analysis，带 source citations。

---

## Summary

此 skill 是带有 intelligent tri-backend routing 的主要 research interface：

- **parallel-cli search**（default）：通过 parallel-web skill 提供快速、成本有效的 web search，并优先考虑 academic sources
- **Parallel Chat API**（`core` model）：Deep、exhaustive multi-source synthesis（仅在明确请求时）
- **Perplexity sonar-pro-search**：仅用于 academic-specific paper searches
- **Automatic routing**：检测 query type 并路由到最佳 backend
- **Manual override**：需要时可强制任何 backend
- **Academic prioritization**：two-search pattern 确保 scientific queries 能浮现 scholarly sources
