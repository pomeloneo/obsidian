---
name: open-notebook
description: Google NotebookLM 的自托管开源替代方案，用于 AI 驱动的研究和文档分析。适用于将研究资料组织到笔记本中、摄取多样化内容源（PDFs、视频、音频、网页、Office 文档）、生成 AI 驱动的笔记和摘要、基于研究创建多说话人 podcasts、使用上下文感知 AI 与文档聊天、通过全文和向量搜索跨资料检索，或运行自定义内容转换。通过自托管实现完整数据隐私，支持 16+ AI providers，包括 OpenAI、Anthropic、Google、Ollama、Groq 和 Mistral。
license: MIT
metadata:
    skill-author: K-Dense Inc.
---

# Open Notebook

## 概述

Open Notebook 是 Google NotebookLM 的开源自托管替代方案，使研究人员能够组织资料、生成 AI 驱动的洞察、创建 podcasts，并与自己的文档进行上下文感知对话，同时保持完整数据隐私。

与 Google 的 Notebook LM 不同，后者在 Enterprise 版本之外没有公开可用的 API；Open Notebook 提供完整的 REST API，支持 16+ AI providers，并完全运行在你自己的基础设施上。

**相较 NotebookLM 的主要优势：**
- 用于编程访问和自动化的完整 REST API
- 可选择 16+ AI providers（不锁定到 Google models）
- 可自定义 1-4 位说话人的多说话人 podcast 生成（相比 2-speaker 限制）
- 通过自托管实现完整数据主权
- 开源且完全可扩展（MIT license）

**仓库：** https://github.com/lfnovo/open-notebook

## 快速开始

### 前置条件

- 已安装 Docker Desktop
- 至少一个 AI provider 的 API key（或使用本地 Ollama 进行免费的本地推理）

### 安装

使用 Docker Compose 部署 Open Notebook：

```bash
# Download the docker-compose file
curl -o docker-compose.yml https://raw.githubusercontent.com/lfnovo/open-notebook/main/docker-compose.yml

# Set the required encryption key
export OPEN_NOTEBOOK_ENCRYPTION_KEY="your-secret-key-here"

# Launch the services
docker-compose up -d
```

访问应用：
- **前端 UI：** http://localhost:8502
- **REST API：** http://localhost:5055
- **API 文档：** http://localhost:5055/docs

### 配置 AI Provider

启动后，配置至少一个 AI provider：

1. 在 UI 中导航到 **Settings > API Keys**
2. 为首选 provider（OpenAI、Anthropic 等）添加凭据
3. 测试连接并发现可用 models
4. 注册 models 以供整个平台使用

或通过 REST API 配置：

```python
import requests

BASE_URL = "http://localhost:5055/api"

# Add a credential for an AI provider
response = requests.post(f"{BASE_URL}/credentials", json={
    "provider": "openai",
    "name": "My OpenAI Key",
    "api_key": "sk-..."
})
credential = response.json()

# Discover available models
response = requests.post(
    f"{BASE_URL}/credentials/{credential['id']}/discover"
)
discovered = response.json()

# Register discovered models
requests.post(
    f"{BASE_URL}/credentials/{credential['id']}/register-models",
    json={"model_ids": [m["id"] for m in discovered["models"]]}
)
```

## 核心功能

### 笔记本
将研究组织到独立笔记本中，每个笔记本包含来源、笔记和聊天会话。

```python
import requests

BASE_URL = "http://localhost:5055/api"

# Create a notebook
response = requests.post(f"{BASE_URL}/notebooks", json={
    "name": "Cancer Genomics Research",
    "description": "Literature review on tumor mutational burden"
})
notebook = response.json()
notebook_id = notebook["id"]
```

### 来源
摄取多种内容类型，包括 PDFs、视频、音频文件、网页和 Office 文档。来源会经过处理以支持全文和向量搜索。

```python
# Add a web URL source
response = requests.post(f"{BASE_URL}/sources", data={
    "url": "https://arxiv.org/abs/2301.00001",
    "notebook_id": notebook_id,
    "process_async": "true"
})
source = response.json()

# Upload a PDF file
with open("paper.pdf", "rb") as f:
    response = requests.post(
        f"{BASE_URL}/sources",
        data={"notebook_id": notebook_id},
        files={"file": ("paper.pdf", f, "application/pdf")}
    )
```

### 笔记
创建并管理与笔记本关联的笔记（人工或 AI 生成）。

```python
# Create a human note
response = requests.post(f"{BASE_URL}/notes", json={
    "title": "Key Findings",
    "content": "TMB correlates with immunotherapy response in NSCLC...",
    "note_type": "human",
    "notebook_id": notebook_id
})
```

### 上下文感知聊天
使用会引用来源的 AI 与你的研究资料聊天。

```python
# Create a chat session
session = requests.post(f"{BASE_URL}/chat/sessions", json={
    "notebook_id": notebook_id,
    "title": "TMB Discussion"
}).json()

# Send a message with context from sources
response = requests.post(f"{BASE_URL}/chat/execute", json={
    "session_id": session["id"],
    "message": "What are the key biomarkers for immunotherapy response?",
    "context": {"include_sources": True, "include_notes": True}
})
```

### 搜索
使用全文或向量（语义）搜索跨所有资料检索。

```python
# Vector search across the knowledge base
results = requests.post(f"{BASE_URL}/search", json={
    "query": "tumor mutational burden immunotherapy",
    "search_type": "vector",
    "limit": 10
}).json()

# Ask a question with AI-powered answer
answer = requests.post(f"{BASE_URL}/search/ask/simple", json={
    "query": "How does TMB predict checkpoint inhibitor response?"
}).json()
```

### Podcast 生成
从研究资料生成专业的多说话人 podcasts，支持 1-4 位可自定义说话人。

```python
# Generate a podcast episode
job = requests.post(f"{BASE_URL}/podcasts/generate", json={
    "notebook_id": notebook_id,
    "episode_profile_id": episode_profile_id,
    "speaker_profile_ids": [speaker1_id, speaker2_id]
}).json()

# Check generation status
status = requests.get(f"{BASE_URL}/podcasts/jobs/{job['job_id']}").json()

# Download audio when ready
audio = requests.get(
    f"{BASE_URL}/podcasts/episodes/{status['episode_id']}/audio"
)
```

### 内容转换
对内容应用自定义 AI 驱动转换，用于摘要、提取和分析。

```python
# Create a custom transformation
transform = requests.post(f"{BASE_URL}/transformations", json={
    "name": "extract_methods",
    "title": "Extract Methods",
    "description": "Extract methodology details from papers",
    "prompt": "Extract and summarize the methodology section...",
    "apply_default": False
}).json()

# Execute transformation on text
result = requests.post(f"{BASE_URL}/transformations/execute", json={
    "transformation_id": transform["id"],
    "input_text": "...",
    "model_id": "model_id_here"
}).json()
```

## 支持的 AI Providers

Open Notebook 通过 Esperanto library 支持 16+ AI providers：

| 提供商 | LLM | Embedding | 语音转文本 | 文本转语音 |
|----------|-----|-----------|----------------|----------------|
| OpenAI | 是 | 是 | 是 | 是 |
| Anthropic | 是 | 否 | 否 | 否 |
| Google GenAI | 是 | 是 | 否 | 是 |
| Vertex AI | 是 | 是 | 否 | 是 |
| Ollama | 是 | 是 | 否 | 否 |
| Groq | 是 | 否 | 是 | 否 |
| Mistral | 是 | 是 | 否 | 否 |
| Azure OpenAI | 是 | 是 | 否 | 否 |
| DeepSeek | 是 | 否 | 否 | 否 |
| xAI | 是 | 否 | 否 | 否 |
| OpenRouter | 是 | 否 | 否 | 否 |
| ElevenLabs | 否 | 否 | 是 | 是 |
| Perplexity | 是 | 否 | 否 | 否 |
| Voyage | 否 | 是 | 否 | 否 |

## 环境变量

Docker 部署的关键配置变量：

| 变量 | 说明 | 默认值 |
|----------|-------------|---------|
| `OPEN_NOTEBOOK_ENCRYPTION_KEY` | **必需。** 用于加密已存储凭据的密钥 | 无 |
| `SURREAL_URL` | SurrealDB 连接 URL | `ws://surrealdb:8000/rpc` |
| `SURREAL_NAMESPACE` | 数据库 namespace | `open_notebook` |
| `SURREAL_DATABASE` | 数据库名称 | `open_notebook` |
| `OPEN_NOTEBOOK_PASSWORD` | UI 的可选密码保护 | 无 |

## API 参考

REST API 可在 `http://localhost:5055/api` 使用，交互式文档位于 `/docs`。

核心 endpoint 分组：
- `/api/notebooks` - Notebook CRUD 和来源关联
- `/api/sources` - 来源摄取、处理和检索
- `/api/notes` - 笔记管理
- `/api/chat/sessions` - Chat session 管理
- `/api/chat/execute` - Chat message 执行
- `/api/search` - 全文和向量搜索
- `/api/podcasts` - Podcast 生成和管理
- `/api/transformations` - 内容转换流水线
- `/api/models` - AI model 配置和发现
- `/api/credentials` - Provider credential 管理

完整 API 参考（包含所有 endpoints 以及 request/response formats）见 `references/api_reference.md`。

## 架构

Open Notebook 使用现代技术栈：
- **后端：** Python 与 FastAPI
- **数据库：** SurrealDB（document + relational）
- **AI 集成：** LangChain 与 Esperanto multi-provider library
- **前端：** Next.js 与 React
- **部署：** Docker Compose 与 persistent volumes

## 重要注意事项

- Open Notebook 需要 Docker 才能部署
- 必须配置至少一个 AI provider，AI 功能才能工作
- 若要无需 API 成本进行免费的本地推理，请使用 Ollama
- `OPEN_NOTEBOOK_ENCRYPTION_KEY` 必须在首次启动前设置，并在重启之间保持一致
- 所有数据都本地存储在 Docker volumes 中，以实现完整数据主权
