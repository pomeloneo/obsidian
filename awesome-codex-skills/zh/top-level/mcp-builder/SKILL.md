---
name: mcp-builder
description: 用于创建高质量 MCP (Model Context Protocol) servers 的指南，使 LLMs 能通过设计良好的 tools 与外部服务交互。构建 MCP servers 来集成外部 APIs 或 services 时使用，适用于 Python (FastMCP) 或 Node/TypeScript (MCP SDK)。
license: Complete terms in LICENSE.txt
---

# MCP Server 开发指南

## 概览

使用此技能来创建高质量 MCP (Model Context Protocol) servers，使 LLMs 能够有效地与外部服务交互。MCP server 提供 tools，让 LLMs 可以访问外部服务和 APIs。MCP server 的质量取决于它能多好地帮助 LLMs 使用所提供的 tools 完成真实世界任务。

---

# 流程

## 🚀 高层工作流

创建高质量 MCP server 包含四个主要阶段：

### Phase 1: 深度研究与规划

#### 1.1 理解以 Agent 为中心的设计原则

在进入实现前，先通过这些原则理解如何为 AI agents 设计 tools：

**为工作流构建，而不只是 API Endpoints：**
- 不要只是简单包装现有 API endpoints - 要构建经过思考、影响力高的 workflow tools
- 合并相关操作（例如 `schedule_event` 同时检查可用性并创建 event）
- 聚焦能完成完整任务的 tools，而不只是单个 API calls
- 考虑 agents 实际需要完成哪些工作流

**针对有限上下文优化：**
- Agents 的 context windows 有限制 - 让每个 token 都有价值
- 返回高信号信息，而不是详尽的数据倾倒
- 提供 "concise" 与 "detailed" response format options
- 默认使用人类可读标识符，而不是技术代码（优先 names 而非 IDs）
- 将 agent 的 context budget 视为稀缺资源

**设计可执行的错误消息：**
- 错误消息应引导 agents 使用正确模式
- 建议具体下一步："Try using filter='active_only' to reduce results"
- 让错误具有教育意义，而不仅是诊断
- 通过清晰反馈帮助 agents 学会正确使用 tool

**遵循自然任务划分：**
- Tool names 应反映人类理解任务的方式
- 用一致前缀组织相关 tools，便于发现
- 围绕自然工作流设计 tools，而不是只围绕 API 结构

**使用 Evaluation-Driven Development：**
- 尽早创建真实的 evaluation scenarios
- 让 agent feedback 驱动 tool 改进
- 快速原型，并基于实际 agent performance 迭代

#### 1.3 学习 MCP Protocol Documentation

**获取最新 MCP protocol documentation：**

使用 WebFetch 加载：`https://modelcontextprotocol.io/llms-full.txt`

这个综合文档包含完整 MCP specification 和 guidelines。

#### 1.4 学习 Framework Documentation

**加载并阅读以下参考文件：**

- **MCP Best Practices**: [📋 查看最佳实践](./reference/mcp_best_practices.md) - 适用于所有 MCP servers 的核心 guidelines

**对于 Python implementations，还要加载：**
- **Python SDK Documentation**: 使用 WebFetch 加载 `https://raw.githubusercontent.com/modelcontextprotocol/python-sdk/main/README.md`
- [🐍 Python Implementation Guide](./reference/python_mcp_server.md) - Python-specific best practices 和 examples

**对于 Node/TypeScript implementations，还要加载：**
- **TypeScript SDK Documentation**: 使用 WebFetch 加载 `https://raw.githubusercontent.com/modelcontextprotocol/typescript-sdk/main/README.md`
- [⚡ TypeScript Implementation Guide](./reference/node_mcp_server.md) - Node/TypeScript-specific best practices 和 examples

#### 1.5 详尽学习 API Documentation

要集成某项服务，请通读**所有**可用 API documentation：
- Official API reference documentation
- Authentication and authorization requirements
- Rate limiting and pagination patterns
- Error responses and status codes
- Available endpoints and their parameters
- Data models and schemas

**为了收集全面信息，按需使用 web search 和 WebFetch tool。**

#### 1.6 创建全面的 Implementation Plan

基于你的研究，创建一份详细计划，包含：

**Tool Selection：**
- 列出最有价值的 endpoints/operations
- 优先实现能支持最常见、最重要 use cases 的 tools
- 考虑哪些 tools 能协同支持复杂工作流

**Shared Utilities and Helpers：**
- 识别常见 API request patterns
- 规划 pagination helpers
- 设计 filtering 和 formatting utilities
- 规划 error handling strategies

**Input/Output Design：**
- 定义 input validation models（Python 用 Pydantic，TypeScript 用 Zod）
- 设计一致的 response formats（例如 JSON 或 Markdown），以及可配置的 detail levels（例如 Detailed 或 Concise）
- 规划大规模使用场景（数千 users/resources）
- 实现 character limits 和 truncation strategies（例如 25,000 tokens）

**Error Handling Strategy：**
- 规划 graceful failure modes
- 设计清晰、可执行、LLM-friendly、自然语言的错误消息，引导后续动作
- 考虑 rate limiting 和 timeout scenarios
- 处理 authentication 和 authorization errors

---

### Phase 2: 实现

有了全面计划后，开始按照特定语言的 best practices 实现。

#### 2.1 设置项目结构

**For Python：**
- 创建单个 `.py` 文件，或在复杂时组织成模块（见 [🐍 Python Guide](./reference/python_mcp_server.md)）
- 使用 MCP Python SDK 注册 tools
- 定义 Pydantic models 进行 input validation

**For Node/TypeScript：**
- 创建正确的 project structure（见 [⚡ TypeScript Guide](./reference/node_mcp_server.md)）
- 设置 `package.json` 和 `tsconfig.json`
- 使用 MCP TypeScript SDK
- 定义 Zod schemas 进行 input validation

#### 2.2 先实现核心基础设施

**开始实现时，先创建 shared utilities，再实现 tools：**
- API request helper functions
- Error handling utilities
- Response formatting functions（JSON 和 Markdown）
- Pagination helpers
- Authentication/token management

#### 2.3 系统化实现 Tools

对计划中的每个 tool：

**定义 Input Schema：**
- 使用 Pydantic（Python）或 Zod（TypeScript）进行 validation
- 包含适当 constraints（min/max length、regex patterns、min/max values、ranges）
- 提供清晰、有描述性的 field descriptions
- 在 field descriptions 中包含多样化 examples

**编写全面的 Docstrings/Descriptions：**
- 用一行概括 tool 的作用
- 详细解释 purpose 和 functionality
- 明确 parameter types 并给出 examples
- 完整的 return type schema
- Usage examples（何时使用、何时不要使用）
- Error handling documentation，说明遇到特定 errors 时如何继续

**实现 Tool Logic：**
- 使用 shared utilities 避免 code duplication
- 所有 I/O 遵循 async/await patterns
- 实现适当 error handling
- 支持多种 response formats（JSON 和 Markdown）
- 尊重 pagination parameters
- 检查 character limits 并适当 truncate

**添加 Tool Annotations：**
- `readOnlyHint`: true（用于 read-only operations）
- `destructiveHint`: false（用于 non-destructive operations）
- `idempotentHint`: true（如果重复调用效果相同）
- `openWorldHint`: true（如果与 external systems 交互）

#### 2.4 遵循特定语言的 Best Practices

**此时，加载合适的语言指南：**

**对于 Python：加载 [🐍 Python Implementation Guide](./reference/python_mcp_server.md)，并确保以下事项：**
- 使用 MCP Python SDK 并正确注册 tools
- Pydantic v2 models 使用 `model_config`
- 全面使用 type hints
- 所有 I/O operations 使用 async/await
- 正确组织 imports
- Module-level constants（CHARACTER_LIMIT, API_BASE_URL）

**对于 Node/TypeScript：加载 [⚡ TypeScript Implementation Guide](./reference/node_mcp_server.md)，并确保以下事项：**
- 正确使用 `server.registerTool`
- Zod schemas 使用 `.strict()`
- 启用 TypeScript strict mode
- 不使用 `any` types - 使用适当 types
- 显式 Promise<T> return types
- 配置 build process（`npm run build`）

---

### Phase 3: Review and Refine

完成初始实现后：

#### 3.1 Code Quality Review

为确保质量，检查代码是否满足：
- **DRY Principle**：tools 之间没有 duplicated code
- **Composability**：shared logic 提取到 functions
- **Consistency**：类似操作返回类似格式
- **Error Handling**：所有 external calls 都有 error handling
- **Type Safety**：完整类型覆盖（Python type hints、TypeScript types）
- **Documentation**：每个 tool 都有全面 docstrings/descriptions

#### 3.2 Test and Build

**重要：** MCP servers 是长期运行的 processes，会通过 stdio/stdin 或 sse/http 等待请求。直接在主进程中运行它们（例如 `python server.py` 或 `node dist/index.js`）会导致你的进程无限挂起。

**安全测试 server 的方式：**
- 使用 evaluation harness（见 Phase 4）- 推荐方式
- 在 tmux 中运行 server，使其位于主进程之外
- 测试时使用 timeout：`timeout 5s python server.py`

**For Python：**
- 验证 Python syntax：`python -m py_compile your_server.py`
- 通过检查文件确认 imports 能正常工作
- 手动测试：在 tmux 中运行 server，然后在主进程中用 evaluation harness 测试
- 或直接使用 evaluation harness（它会为 stdio transport 管理 server）

**For Node/TypeScript：**
- 运行 `npm run build` 并确保无错误完成
- 验证 dist/index.js 已创建
- 手动测试：在 tmux 中运行 server，然后在主进程中用 evaluation harness 测试
- 或直接使用 evaluation harness（它会为 stdio transport 管理 server）

#### 3.3 使用质量检查清单

要验证实现质量，请从特定语言指南中加载对应 checklist：
- Python：见 [🐍 Python Guide](./reference/python_mcp_server.md) 中的 "Quality Checklist"
- Node/TypeScript：见 [⚡ TypeScript Guide](./reference/node_mcp_server.md) 中的 "Quality Checklist"

---

### Phase 4: 创建 Evaluations

实现 MCP server 后，创建全面 evaluations 以测试其有效性。

**加载 [✅ Evaluation Guide](./reference/evaluation.md)，查看完整 evaluation guidelines。**

#### 4.1 理解 Evaluation Purpose

Evaluations 测试 LLMs 是否能有效使用你的 MCP server 回答真实、复杂的问题。

#### 4.2 创建 10 个 Evaluation Questions

要创建有效 evaluations，请遵循 evaluation guide 中的流程：

1. **Tool Inspection**：列出可用 tools 并理解其能力
2. **Content Exploration**：使用 READ-ONLY operations 探索可用数据
3. **Question Generation**：创建 10 个复杂、真实的问题
4. **Answer Verification**：自己解答每个问题以验证答案

#### 4.3 Evaluation Requirements

每个问题必须是：
- **Independent**：不依赖其他问题
- **Read-only**：只需要 non-destructive operations
- **Complex**：需要多次 tool calls 和深入探索
- **Realistic**：基于人们会关心的真实 use cases
- **Verifiable**：有单一、清晰答案，可通过 string comparison 验证
- **Stable**：答案不会随时间改变

#### 4.4 Output Format

创建一个 XML 文件，结构如下：

```xml
<evaluation>
  <qa_pair>
    <question>Find discussions about AI model launches with animal codenames. One model needed a specific safety designation that uses the format ASL-X. What number X was being determined for the model named after a spotted wild cat?</question>
    <answer>3</answer>
  </qa_pair>
<!-- More qa_pairs... -->
</evaluation>
```

---

# 参考文件

## 📚 Documentation Library

开发期间按需加载这些资源：

### Core MCP Documentation（先加载）
- **MCP Protocol**: 从 `https://modelcontextprotocol.io/llms-full.txt` 获取 - 完整 MCP specification
- [📋 MCP Best Practices](./reference/mcp_best_practices.md) - 通用 MCP guidelines，包含：
  - Server and tool naming conventions
  - Response format guidelines（JSON vs Markdown）
  - Pagination best practices
  - Character limits and truncation strategies
  - Tool development guidelines
  - Security and error handling standards

### SDK Documentation（在 Phase 1/2 加载）
- **Python SDK**: 从 `https://raw.githubusercontent.com/modelcontextprotocol/python-sdk/main/README.md` 获取
- **TypeScript SDK**: 从 `https://raw.githubusercontent.com/modelcontextprotocol/typescript-sdk/main/README.md` 获取

### Language-Specific Implementation Guides（在 Phase 2 加载）
- [🐍 Python Implementation Guide](./reference/python_mcp_server.md) - 完整 Python/FastMCP guide，包含：
  - Server initialization patterns
  - Pydantic model examples
  - 使用 `@mcp.tool` 进行 tool registration
  - Complete working examples
  - Quality checklist

- [⚡ TypeScript Implementation Guide](./reference/node_mcp_server.md) - 完整 TypeScript guide，包含：
  - Project structure
  - Zod schema patterns
  - 使用 `server.registerTool` 进行 tool registration
  - Complete working examples
  - Quality checklist

### Evaluation Guide（在 Phase 4 加载）
- [✅ Evaluation Guide](./reference/evaluation.md) - 完整 evaluation creation guide，包含：
  - Question creation guidelines
  - Answer verification strategies
  - XML format specifications
  - Example questions and answers
  - Running an evaluation with the provided scripts
