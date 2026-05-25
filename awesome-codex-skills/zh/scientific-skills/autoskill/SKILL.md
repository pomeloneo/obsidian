---
name: autoskill
description: 通过 screenpipe 观察用户的屏幕，检测重复的研究工作流程，将其与现有 scientific agent skills 匹配，并为尚未覆盖的模式起草新技能（或链接现有技能的组合配方）。当用户要求分析最近的工作并根据实际工作提出技能时使用。需要在端口 3030 上本地运行 screenpipe 守护进程 (https://github.com/screenpipe/screenpipe)；该技能没有其他数据源，如果无法访问 screenpipe，将拒绝运行。所有检测都在本地运行；只有经过编辑的集群摘要会发送给 LLM。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
    requires: screenpipe
---

# 自动技能

> **需要一个正在运行的 [screenpipe](https://github.com/screenpipe/screenpipe) 守护进程。** 该技能没有备用数据源 - 它专门从本地 screenpipe HTTP API（默认`http://localhost:3030`）读取。如果守护进程未运行，`run()` 会通过安装指令引发 `ScreenpipeUnreachable`。

> **网络访问和环境变量。** 此技能向 (a) 用户本机 loopback 上的 screenpipe 守护进程和 (b) 用户配置的 LLM 后端发出经过身份验证的 HTTP 请求 - `http://localhost:1234/v1`（LM Studio，默认）、`https://api.anthropic.com` 之一（选择加入 Claude），或用户提供的 BYOK Foundry 网关。该技能读取三个环境变量 - `SCREENPIPE_TOKEN`、`ANTHROPIC_API_KEY`、`FOUNDRY_API_KEY` - 并且每个变量只用于向其名称对应的单一端点进行身份验证。没有其他网络目的地，没有遥测，也不会向任何第三方传出数据。

## 概述

将用户自己的工作流程历史记录（由本地 [screenpipe](https://github.com/screenpipe/screenpipe) 守护进程被动捕获）转化为新技能。该技能是按需的：用户使用时间窗口调用它，它查询 screenpipe 的本地 HTTP API，对重复的工作流模式进行聚类，将每个模式与此存储库中的现有技能进行比较，并生成用户可以查看、编辑和推广的提案的暂存文件夹。

## 何时使用此技能

当用户要求执行以下操作时调用此技能：
- “分析我过去 4 小时/天/周的情况并提出新技能。”
- “看看我一直在做什么，并告诉我哪些内容尚未涵盖。”
- “从我最近的工作流程中起草一项技能。”
- “查找我重复的工作流程的合成配方。”

请**不要**在关于 screenpipe 本身的一次性问题、实时屏幕查询或没有明确用户请求的情况下调用它 - 该技能会分析敏感的本地内容，必须保持明确的用户触发。

## 隐私姿势

- **Screenpipe 在捕获时处理 app/window 过滤。** 通过将 `references/screenpipe-config.yaml` 复制到用户的 screenpipe 配置中来安装启动器拒绝列表。敏感应用程序（密码管理器、消息传递、银行业务）从一开始就不会被 OCR 处理。
- **原始 OCR 永远不会离开机器。** `scripts/fetch_window.py` 通过本地主机 HTTP 提取数据。 `scripts/cluster.py` 将时间线缩短为 app/duration/title 摘要。在任何集群摘要到达 LLM 之前，`scripts/redact.py` 剥离电子邮件、API 密钥、不记名token和电话号码作为纵深防御。
- **LLM 后端默认为 `local`。** 建议的设置是 [LM Studio](https://lmstudio.ai/) 运行 `Gemma-4-31B-it` — 强大的推理能力，大小适合大多数工作站 GPUs，并且没有数据离开您的计算机。云后端（`claude`、`foundry`）可供明确需要的用户选择加入并记录在`config.yaml`中。无论后端选择如何，检测和嵌入始终在本地运行。
- **试运行模式** (`--plan`) 打印在任何 LLM 调用之前将进行分析的确切时间线。
- **TLS 对于本地主机**（可选，用于公司策略）：请参阅 `references/https-proxy.md` 了解 Caddy 模式。

## 前提条件

### 1. Screenpipe 守护进程

安装官方版本或从源代码构建。无论哪种方式，默认情况下，守护进程都会将 HTTP 绑定到 `localhost:3030` 上。

**来自源代码**（如果您想要 CLI 守护进程而不需要桌面 GUI，建议使用）：

```bash
git clone --depth 1 https://github.com/mediar-ai/screenpipe.git
cd screenpipe
cargo build -p screenpipe-engine --release
# System deps (macOS): cmake + full Xcode.app (not just Command Line Tools).
#   brew install cmake
#   # if xcodebuild plug-ins error: sudo xcodebuild -runFirstLaunch
./target/release/screenpipe doctor   # confirm permissions + ffmpeg
./target/release/screenpipe record --disable-audio --use-pii-removal
```

第一次运行会提示macOS屏幕录制权限。授予它并重新启动。

### 2. Screenpipe API 代币

本地API现在需要承载身份验证。检索您的token并将其导出：

```bash
export SCREENPIPE_TOKEN=$(screenpipe auth token)
```

（或者直接设置 `screenpipe.token` 到 `config.yaml` 中 — env var 是首选，因为它使秘密不受版本控制。）

### 3. Python environment

通过 `pipenv` 从仓库根目录：

```bash
pipenv install httpx pyyaml sentence-transformers
```

嵌入模型（`sentence-transformers/all-MiniLM-L6-v2`，~80 MB）在首次运行时下载。

### 4.本地LLM（默认路径）—LM Studio

- 安装[LMStudio](https://lmstudio.ai/)。
- 下载 `Gemma-4-31B-it`（或其他强推理模型；调整 `local.model`，位置在 `config.yaml` 中）。
- 通过CLI加载它以进行无头使用（不需要GUI）：

```bash
lms load gemma-4-31b-it --context-length 131072 --gpu max -y
lms status   # confirm server running on :1234
```

### 5. 云LLM后端（可选，选择加入）

仅当您明确选择退出本地时：
- `claude`：设置`ANTHROPIC_API_KEY`，将`backend: claude`翻转到`config.yaml`。
- `foundry`：设置 `FOUNDRY_API_KEY`，切换 `backend: foundry`，并将 `foundry.endpoint` 设置为您的公司网关 URL。

## 架构

```
screenpipe daemon (user-installed)
        │  HTTP on localhost:3030
        ▼
scripts/fetch_window.py    → normalized timeline events
scripts/redact.py          → regex scrub (defense-in-depth)
scripts/cluster.py         → sessions + clusters (local only)
scripts/match_skills.py    → top-k vs existing 135 skills (local embeddings)
scripts/synthesize.py      → LLM judge: reuse / compose / novel
        │
        ▼
~/.autoskill/proposed/<timestamp>/        (default; override with --out)
  ├── report.md
  ├── composition-recipes/<name>/SKILL.md
  └── new-skills/<name>/SKILL.md

scripts/promote.py         → user-approved proposal → scientific-skills/<name>/
```

## 工作流程

该技能在 `scripts/autoskill.py` 处发布了一个统一的 CLI，并包含三个子命令：

```bash
python scripts/autoskill.py doctor   --config config.yaml --skills-dir ../
python scripts/autoskill.py run      --start ... --end ... --config config.yaml
python scripts/autoskill.py promote  --proposed ~/.autoskill/proposed/<ts> --skills-dir ../ --name <skill>
```

### 0. Preflight with `doctor`

在完整运行之前，一次性验证每个依赖项：

```bash
python scripts/autoskill.py doctor \
  --config scientific-skills/autoskill/config.yaml \
  --skills-dir scientific-skills
```

该报告涵盖`config`（后端选择有效）、`skills_dir`（存在）、`screenpipe`（可访问+已验证）和`llm`（LM Studio 服务或API 密钥存在）。任何失败均非零退出，违规行标记为`error`。

### 1. 运行管道

```bash
export SCREENPIPE_TOKEN=$(screenpipe auth token)
python scripts/autoskill.py run \
  --start "2026-04-17T00:00:00Z" \
  --end   "2026-04-17T23:59:59Z" \
  --config scientific-skills/autoskill/config.yaml \
  --skills-dir scientific-skills
```

提案默认落在`~/.autoskill/proposed/<timestamp>/`，将实验输出保留在技能存储库之外。通过 `--out PATH` 进行覆盖。

内部：
1. **获取** — `fetch_window` 对 screenpipe 的 `/search` 端点进行分页，将事件标准化为 `{ts, app, window_title, text, content_type}`。
2. **编辑** — `redact` 擦除来自 OCR 文本和窗口标题的电子邮件、API 密钥、不记名token、电话，作为对 screenpipe 自己的 PII 删除的纵深防御。
3. **Cluster** — `segment_sessions` 在空闲间隙（默认 10 分钟）进行分割并丢弃短会话； `cluster_sessions` 按应用程序签名对会话进行分组，并保留大小为 `min_cluster_size` 的集群（默认为 2）。
4. **匹配** — `load_skill_descriptions` 从每个 `SKILL.md` 读取 frontmatter，这些文件位于 `scientific-skills/` 中；`top_k_matches` 使用本地 `sentence-transformers` 嵌入（余弦相似度）针对所有技能对每个集群进行排名。
5. **Synthesize** — `synthesize` 提示配置的 LLM 后端将每个集群分类为 `reuse`、`compose` 或 `novel`，并在适当的情况下发出 SKILL.md 主体。
6. **报告** — 为每个提案写入 `<out_dir>/<ts>/report.md`，加上 `new-skills/<name>/SKILL.md` 或 `composition-recipes/<name>/SKILL.md`。

添加 `--dry-run` 聚类后停止；这会跳过LLM（以及句子转换器加载），只写入`plan.md`进行检查。

### 2.审核和推广

打开`~/.autoskill/proposed/<ts>/report.md`，就地编辑草稿，删除任何你不想要的内容。然后：

```bash
python scripts/autoskill.py promote \
  --proposed ~/.autoskill/proposed/2026-04-17T14-30-00 \
  --skills-dir scientific-skills \
  --name zotero-pubmed-helper
```

`promote` 将目录移至`scientific-skills/<name>/`，拒绝覆盖现有技能。如果未找到提案或目标已存在，则以非零值退出并出现友好错误。

## 配置

完整形状请参见`config.yaml`。默认值（本地优先）：

```yaml
backend: local
local:
  endpoint: http://localhost:1234/v1   # LM Studio's Developer server
  model: Gemma-4-31B-it

screenpipe:
  url: http://localhost:3030           # or https://screenpipe.local via Caddy

cluster:
  min_session_minutes: 5
  idle_gap_minutes: 10
  min_cluster_size: 2
```

选择云后端：

```yaml
backend: claude                         # or foundry
claude:
  model: claude-opus-4-7
```

## 作文配方与新技能

- **compose**：LLM判断链接现有技能涵盖了工作流程。发出的 SKILL.md 是故意精简的 — frontmatter + 按顺序调用现有技能的“工作流程”部分。发现该技能的同一代理运行时可以端到端地调用它。
- **新颖**：现有技能的组合无法涵盖它。起草了更完整的SKILL.md，仍然遵循存储库约定（frontmatter、概述、何时使用、工作流程）。用户在升级之前应始终查看新技能草稿。

## 测试

`tests/` 的一个小型 pytest 套件涵盖了该技能。每个脚本都通过依赖项注入进行隔离单元测试（模拟 HTTP 传输、存根后端、存根嵌入器）：

```bash
cd scientific-skills/autoskill
python -m pytest tests/ -v
```

## 与此存储库中的其他技能组合

自动技能的嵌入索引涵盖了所有 135 个同级技能。看起来像科学写作的工作流程将匹配 `scientific-writing` / `literature-review` / `citation-management`；图形工作将匹配 `scientific-schematics` / `generate-image` / `infographics`；幻灯片准备匹配 `scientific-slides` / `pptx`；当集群对两个或三个同级技能得分较高时，发出的组合配方会明确命名它们，因此用户未来的代理调用将使用此存储库中已记录的优化路径。
