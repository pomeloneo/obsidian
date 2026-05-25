---
name: paper-lookup
description: 通过 REST APIs 搜索 10 个学术论文数据库，查找 research papers、preprints 和 scholarly articles。覆盖 PubMed、PMC（full text）、bioRxiv、medRxiv、arXiv、OpenAlex、Crossref、Semantic Scholar、CORE、Unpaywall。用于搜索论文、引用、DOI/PMID 查询、摘要、full text、open access、preprints、citation graphs、author search，或任何学术文献查询。当提到任何受支持数据库，或出现 "find papers on X"、"look up this DOI" 等请求时触发。
metadata:
  skill-author: K-Dense Inc.
---

# 论文检索

你可以通过 REST APIs 访问 10 个学术论文数据库。你的任务是判断哪些数据库最适合用户查询，调用它们，并返回结果。

## 核心 Workflow

1. **理解查询** -- 用户在找什么？通过 DOI 找特定论文？某个主题的论文？某位作者的出版物？Open access PDFs？Full text？这会决定应查询哪些数据库。

2. **选择数据库** -- 使用下面的数据库选择指南。许多查询适合同时访问多个数据库，例如先在 PubMed 搜索论文，再用 Unpaywall 检查 open access 副本。

3. **阅读参考文件** -- 每个数据库在 `references/` 中都有参考文件，包含 endpoint 细节、查询格式和示例调用。在发起 API 调用前阅读相关文件。

4. **发起 API 调用** -- 关于在你的平台上使用哪种 HTTP fetch tool，请见下方 **发起 API 调用** 部分。

5. **返回结果** -- 始终返回：
   - 每个数据库的 **raw JSON** 响应（或 arXiv 的 parsed XML）
   - **已查询数据库列表**，并列出使用的具体 endpoints
   - 如果某次查询没有结果，明确说明，而不是省略

## 数据库选择指南

将用户意图匹配到合适的数据库。

### 按使用场景

| 用户询问的是... | 主要数据库 | 也可考虑 |
|---|---|---|
| 生物医学主题的论文 | PubMed | Semantic Scholar, OpenAlex |
| 生物医学文章 full text | PMC | CORE |
| 生物学 preprints | bioRxiv | Semantic Scholar, OpenAlex |
| 健康/医学 preprints | medRxiv | Semantic Scholar, OpenAlex |
| 物理、数学或 CS preprints | arXiv | Semantic Scholar, OpenAlex |
| 跨所有领域的论文 | OpenAlex | Semantic Scholar, Crossref |
| 通过 DOI 查找特定论文 | Crossref | Unpaywall, Semantic Scholar |
| 论文的 open access PDF | Unpaywall | CORE, PMC |
| Citation graph（谁引用谁） | Semantic Scholar | OpenAlex |
| 作者的出版物 | Semantic Scholar | OpenAlex |
| 论文推荐 | Semantic Scholar | -- |
| Full text（任意领域） | CORE | PMC（仅生物医学） |
| 期刊/出版商 metadata | Crossref | OpenAlex |
| 资助方信息 | Crossref | OpenAlex |
| 在 PMID/PMCID/DOI 之间转换 | PMC（ID Converter） | Crossref |
| 按日期查找近期 preprints | bioRxiv, medRxiv | arXiv |

### 跨数据库查询

| 用户询问的是... | 要查询的数据库 |
|---|---|
| 某篇论文的所有信息（metadata + citations + OA） | Crossref + Semantic Scholar + Unpaywall |
| 综合性文献检索 | PubMed + OpenAlex + Semantic Scholar |
| 查找并阅读论文 | PubMed（查找）+ Unpaywall（OA link）+ PMC 或 CORE（full text） |
| Preprint 及其已发表版本 | bioRxiv/medRxiv + Crossref |
| 带 citation metrics 的作者概览 | Semantic Scholar + OpenAlex |

当查询跨越多个需求时（例如 "find papers about CRISPR and get me the PDFs"），并行查询相关数据库。

## 常见标识符格式

不同数据库使用不同的标识符系统。如果查询失败，可能是标识符格式错误。

| 标识符 | 格式 | 示例 | 使用方 |
|---|---|---|---|
| DOI | `10.xxxx/xxxxx` | `10.1038/nature12373` | 所有数据库 |
| PMID | 整数 | `34567890` | PubMed, PMC, Semantic Scholar |
| PMCID | `PMC` + 数字 | `PMC7029759` | PMC, Europe PMC |
| arXiv ID | `YYMM.NNNNN` | `2103.15348` | arXiv, Semantic Scholar |
| OpenAlex ID | `W` + 数字 | `W2741809807` | OpenAlex |
| Semantic Scholar ID | 40 字符 hex | `649def34f8be...` | Semantic Scholar |
| ORCID | `0000-XXXX-XXXX-XXXX` | `0000-0001-6187-6610` | OpenAlex, Crossref |
| ISSN | `XXXX-XXXX` | `0028-0836` | Crossref, OpenAlex |

**交叉引用 IDs：** Semantic Scholar 通过前缀接受 DOI、PMID、PMCID 和 arXiv ID（例如 `DOI:10.1038/nature12373`、`PMID:34567890`、`ARXIV:2103.15348`）。OpenAlex 通过前缀接受 DOI 和 PMID（`doi:10.1038/...`、`pmid:34567890`）。使用 PMC ID Converter 在 PMID、PMCID 和 DOI 之间转换。

## API Keys 与访问

这些数据库多数完全开放。少数数据库使用 API keys 后可获得更高 rate limits。

### 需要或受益于 API keys 的数据库

| 数据库 | 环境变量 | 是否必需 | 注册 |
|---|---|---|---|
| NCBI（PubMed, PMC） | `NCBI_API_KEY` | 否（无 key 3 req/s，有 key 10 req/s） | https://www.ncbi.nlm.nih.gov/account/settings/ |
| CORE | `CORE_API_KEY` | full text 需要 | https://core.ac.uk/services/api |
| Semantic Scholar | `S2_API_KEY` | 否（无 key 使用 shared pool） | https://www.semanticscholar.org/product/api#api-key-form |
| OpenAlex | `OPENALEX_API_KEY` | 推荐 | https://openalex.org/settings/api |

### 完全开放的数据库（无需 key）

| 数据库 | 说明 |
|---|---|
| bioRxiv / medRxiv | 无 auth，无记录在案的 rate limits |
| arXiv | 无 auth，最多每 3 秒 1 个请求 |
| Crossref | 无 auth；添加 `mailto` 参数可进入 polite pool（2 倍 rate limit） |
| Unpaywall | 无 auth；需要 `email` 参数 |

### 加载 API keys

1. **先检查环境** -- key 可能已经导出（例如 `$NCBI_API_KEY`）。
2. **回退到 `.env`** -- 检查当前工作目录中的 `.env`。
3. **无 key 也继续** -- 大多数 APIs 仍能以较低 rate limits 工作。告诉用户缺少哪个 key，以及如何获取。

## 发起 API 调用

使用当前环境的 HTTP fetch tool 调用 REST endpoints：

| Platform | HTTP Fetch Tool | Fallback |
|---|---|---|
| Claude Code | `WebFetch` | `curl` via Bash |
| Gemini CLI | `web_fetch` | `curl` via shell |
| Windsurf | `read_url_content` | `curl` via terminal |
| Cursor | No dedicated fetch tool | `curl` via `run_terminal_cmd` |
| Codex CLI | No dedicated fetch tool | `curl` via `shell` |
| Cline | No dedicated fetch tool | `curl` via `execute_command` |

如果 fetch tool 失败，则通过可用的 shell tool 回退到 `curl`。

### 特殊情况

- **arXiv 返回 Atom XML**，不是 JSON。解析它，或使用 `curl` 并提取相关字段。如果有简单 parser，可考虑通过管道传给它。
- **PMC eFetch 对 full text 返回 JATS XML**。这是预期行为 -- full text articles 使用 XML 格式。
- **Crossref 和 Unpaywall** 通过包含 `mailto` 参数或 email 可受益于 polite/fast pool。

### 请求指南

- 对 **NCBI APIs**（PubMed, PMC）：无 key 最多 3 req/sec，有 key 10 req/sec。顺序发起请求。
- 对 **arXiv**：最多每 3 秒 1 个请求。耐心等待。
- 对 **Crossref**：5 req/sec（public），10 req/sec（带 `mailto` 的 polite pool）。
- 对没有严格限制的其他 APIs，可以并行查询多个数据库。
- 如果收到 HTTP 429（rate limit），短暂等待并重试一次。

### 错误恢复

1. **检查标识符格式** -- 使用 Common Identifier Formats 表。PMID 不能用于 arXiv，arXiv ID 也不能直接用于 PubMed。
2. **尝试替代标识符** -- 如果 DOI 在某个数据库失败，改用 title 或 PMID。
3. **尝试其他数据库** -- 如果 PubMed 对 CS paper 没有返回结果，尝试 Semantic Scholar 或 OpenAlex。
4. **报告失败** -- 告诉用户哪个数据库失败、错误是什么，以及你改试了什么。

## 输出格式

按如下结构组织响应：

```
## Databases Queried
- **PubMed** -- esearch + esummary for "CRISPR gene therapy"
- **Unpaywall** -- DOI lookup for 10.1038/...

## Results

### PubMed
[raw JSON response or formatted results]

### Unpaywall
[raw JSON response]
```

如果结果非常大，展示最相关部分，并说明还有更多数据可用。但默认展示完整 raw JSON -- 用户要求的是它。

## 可用数据库

在发起任何 API 调用前阅读相关 reference file。

### 生物医学文献
| 数据库 | Reference File | 覆盖内容 |
|---|---|---|
| PubMed | `references/pubmed.md` | 3700 万+ biomedical citations、abstracts、MeSH terms |
| PMC | `references/pmc.md` | 1000 万+ full-text biomedical articles（JATS XML）、ID conversion |

### Preprint Servers
| 数据库 | Reference File | 覆盖内容 |
|---|---|---|
| bioRxiv | `references/biorxiv.md` | Biology preprints（按日期/DOI 浏览，无关键词搜索） |
| medRxiv | `references/medrxiv.md` | Health sciences preprints（按日期/DOI 浏览，无关键词搜索） |
| arXiv | `references/arxiv.md` | 物理、数学、CS、生物学、经济学 preprints（关键词搜索，Atom XML） |

### 多学科索引
| 数据库 | Reference File | 覆盖内容 |
|---|---|---|
| OpenAlex | `references/openalex.md` | 2.5 亿+ works、authors、institutions、topics、citation data |
| Crossref | `references/crossref.md` | 1.5 亿+ DOI metadata、journals、funders、references |
| Semantic Scholar | `references/semantic-scholar.md` | 2 亿+ papers、citation graphs、AI-generated TLDRs、recommendations |

### Open Access 与 Full Text
| 数据库 | Reference File | 覆盖内容 |
|---|---|---|
| CORE | `references/core.md` | 来自全球 OA repositories 的 3700 万+ full texts |
| Unpaywall | `references/unpaywall.md` | 任意 DOI 的 OA status 和 PDF links |
