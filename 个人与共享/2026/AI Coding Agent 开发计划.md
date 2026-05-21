## 项目概述

构建一个能够理解编程需求、生成代码、执行验证并迭代优化的 AI 编程助手。

> [!important]
> 
> **核心目标**：打造一个可以接收自然语言指令，自动生成、运行和调试代码的智能 Agent

---

## 技术架构

```jsx
┌─────────────────────────────────────────────────┐
│                   用户界面层                      │
│         (CLI / Web UI / IDE 插件)                │
├─────────────────────────────────────────────────┤
│                   Agent 核心层                    │
│  ┌───────────┐  ┌───────────┐  ┌───────────┐   │
│  │  规划器    │  │  执行器    │  │  记忆管理  │   │
│  │ (Planner) │  │ (Executor)│  │ (Memory)  │   │
│  └───────────┘  └───────────┘  └───────────┘   │
├─────────────────────────────────────────────────┤
│                   工具层 (Tools)                  │
│   文件读写 │ 代码执行 │ 搜索 │ Git 操作 │ API    │
├─────────────────────────────────────────────────┤
│                   LLM 层                         │
│      OpenAI / Claude / Gemini / 本地模型         │
└─────────────────────────────────────────────────┘
```

---

## 开发路线图

### Phase 1：基础框架搭建 `预计 1-2 周`

- [ ] 项目初始化与环境配置

- [ ] 选择并集成 LLM API（推荐先用 OpenAI）

- [ ] 实现基础的对话循环

- [ ] 搭建简单的 CLI 界面

**里程碑**：能够与 LLM 进行基础对话，输入问题返回回答

### Phase 2：工具系统开发 `预计 2-3 周`

- [ ] 设计工具调用协议（Function Calling）

- [ ] 实现文件系统工具（读/写/列出文件）

- [ ] 实现代码执行工具（安全沙箱环境）

- [ ] 实现搜索工具（本地代码库搜索）

**里程碑**：Agent 能够读取文件、生成代码并执行

### Phase 3：推理能力增强 `预计 2-3 周`

- [ ] 实现 ReAct 思考框架（推理-行动循环）

- [ ] 添加 Plan-and-Execute 模式

- [ ] 错误处理与自我修复机制

- [ ] 上下文窗口管理与压缩

**里程碑**：Agent 能够自主规划任务、执行并处理错误

### Phase 4：完善与优化 `预计 2-4 周`

- [ ] 多轮对话记忆管理

- [ ] 支持多文件项目理解

- [ ] 添加 Git 集成

- [ ] 性能优化与 Token 节省

- [ ] 可选：Web UI 开发

**里程碑**：功能完整、可日常使用的 Coding Agent

---

## 技术选型

|组件|推荐方案|备选方案|
|---|---|---|
|**编程语言**|Python 3.11+|TypeScript / Go|
|**LLM 框架**|LangChain|LlamaIndex / 直接调 API|
|**LLM 模型**|GPT-4o / Claude 3.5|Gemini Pro / 本地 Ollama|
|**代码执行**|Docker 沙箱|subprocess + 安全限制|
|**向量数据库**|ChromaDB|Pinecone / Qdrant|
|**CLI 框架**|Rich + Typer|Click|

---

## 核心代码结构

```jsx
ai-coding-agent/
├── src/
│   ├── agent/
│   │   ├── __init__.py
│   │   ├── core.py          # Agent 主循环
│   │   ├── planner.py       # 任务规划
│   │   └── executor.py      # 任务执行
│   ├── tools/
│   │   ├── __init__.py
│   │   ├── file_tools.py    # 文件操作
│   │   ├── code_runner.py   # 代码执行
│   │   └── search.py        # 搜索工具
│   ├── llm/
│   │   ├── __init__.py
│   │   └── client.py        # LLM 调用封装
│   ├── memory/
│   │   ├── __init__.py
│   │   └── context.py       # 上下文管理
│   └── cli.py               # 命令行入口
├── tests/
├── config.yaml
├── requirements.txt
└── README.md
```

---

## 学习资源

- **ReAct 论文**：理解推理-行动框架的核心思想

- **LangChain Agents 文档**：官方 Agent 开发指南

- **OpenAI Function Calling**：工具调用的最佳实践

- **Anthropic Claude Tool Use**：Claude 模型的工具使用

---

## 下一步行动

> [!important]
> 
> **立即开始**：从 Phase 1 的第一个任务开始——创建项目并配置开发环境

1. 创建 GitHub 仓库

1. 设置 Python 虚拟环境

1. 申请 OpenAI API Key

1. 写第一个 "Hello World" 级别的 LLM 调用

[[Step 1- 环境配置与第一个 LLM 调用]]