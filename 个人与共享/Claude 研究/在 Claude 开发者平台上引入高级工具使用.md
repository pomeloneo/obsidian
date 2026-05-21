## 中文翻译

AI 智能体的未来是模型能够跨数百甚至数千个工具无缝协作。IDE 助手集成 git 操作、文件操作、包管理器、测试框架和部署管道；运维协调器连接 Slack、GitHub、Google Drive、Jira、公司数据库和数十个 MCP 服务器。

要[构建高效智能体](https://www.anthropic.com/research/building-effective-agents)，它们需要使用无限的工具库而不是将所有定义预先塞入上下文。智能体还需要从代码中调用工具，以及从示例中学习正确的工具使用方式。

今天我们发布三个功能：

> [!important]
> 
> - **工具搜索工具（Tool Search Tool）**：允许 Claude 使用搜索工具访问数千个工具，而不占用上下文窗口
> 
> - **程序化工具调用（Programmatic Tool Calling）**：允许 Claude 在代码执行环境中调用工具，减少对上下文窗口的影响
> 
> - **工具使用示例（Tool Use Examples）**：提供通用标准来演示如何有效使用给定工具

---

### 工具搜索工具

#### 挑战

MCP 工具定义提供重要上下文，但随着连接更多服务器，token 累积很快。以五服务器为例：GitHub 35 工具（~26K token）、Slack 11 工具（~21K token）、Sentry 5 工具（~3K token）等——58 个工具在对话开始前就消耗约 **55K token**。

#### 解决方案

工具搜索工具按需发现工具，而非预先加载所有定义。Claude 只看到当前任务实际需要的工具。

`[此处有一张图片：工具搜索工具示意图——对比传统方式和使用工具搜索工具的 token 消耗]`

> [!important]
> 
> **效果对比**：
> 
> - 传统方式：50+ MCP 工具预加载约 72K token
> 
> - 工具搜索工具：仅加载搜索工具约 500 token + 按需加载 3-5 个相关工具约 3K token
> 
> - **token 使用减少 85%**
> 
> - Opus 4 准确率从 49% 提升至 74%，Opus 4.5 从 79.5% 提升至 88.1%

标记工具为 `defer_loading: true` 使其可按需发现。Claude 只在需要特定能力时才搜索相关工具。

---

### 程序化工具调用

#### 挑战

传统工具调用有两个根本问题：

1. **中间结果的上下文污染**：分析 10MB 日志文件时，整个文件进入上下文窗口

1. **推理开销**：每次工具调用需要完整的模型推理过程

#### 解决方案

程序化工具调用让 Claude 通过代码编排工具，而非逐个 API 往返。Claude 编写代码调用多个工具、处理输出，并控制哪些信息实际进入上下文窗口。

**示例：预算合规检查**

"哪些团队成员超出了 Q3 差旅预算？"

传统方式需要 20+ 次工具调用，2000+ 条费用明细（50KB+）全部进入上下文。使用程序化工具调用，Claude 编写 Python 脚本编排整个工作流：

```python
team = await get_team_members("engineering")
levels = list(set(m["level"] for m in team))
budget_results = await asyncio.gather(*[
    get_budget_by_level(level) for level in levels
])
budgets = {level: budget for level, budget in zip(levels, budget_results)}
expenses = await asyncio.gather(*[
    get_expenses(m["id"], "Q3") for m in team
])
exceeded = []
for member, exp in zip(team, expenses):
    budget = budgets[member["level"]]
    total = sum(e["amount"] for e in exp)
    if total > budget["travel_limit"]:
        exceeded.append({
            "name": member["name"],
            "spent": total,
            "limit": budget["travel_limit"]
        })
print(json.dumps(exceeded))
```

`[此处有一张图片：程序化工具调用流程图]`

> [!important]
> 
> **效率提升**：
> 
> - **token 节省**：平均从 43,588 降至 27,297 token，**减少 37%**
> 
> - **延迟降低**：消除 19+ 次推理过程
> 
> - **准确率提升**：内部知识检索从 25.6% 提升至 28.5%；GIA 基准从 46.5% 提升至 51.2%

---

### 工具使用示例

#### 挑战

JSON Schema 擅长定义结构，但无法表达使用模式：何时包含可选参数、哪些组合有意义、API 期望什么约定。

#### 解决方案

工具使用示例让你在工具定义中直接提供示例调用。从三个示例中，Claude 可以学会：

- **格式约定**：日期使用 YYYY-MM-DD，用户 ID 遵循 USR-XXXXX，标签使用 kebab-case

- **嵌套结构模式**：如何构建带嵌套联系人对象的报告者对象

- **可选参数关联**：关键 bug 需要完整联系信息 + 紧急升级；功能请求有报告者但无联系信息/升级；内部任务仅需标题

> [!important]
> 
> 在我们的内部测试中，工具使用示例将复杂参数处理的准确率**从 72% 提升至 90%**。

---

### 最佳实践

- **分层策略**：从最大瓶颈开始——上下文膨胀用工具搜索，大量中间结果用程序化调用，参数错误用示例

- **工具搜索设置**：清晰描述性的定义、保留 3-5 个最常用工具始终加载

- **程序化调用设置**：清楚记录返回格式、选择可并行和幂等的工具

- **示例设置**：使用真实数据、展示多样性、1-5 个示例/工具、聚焦模糊之处

---

_致谢：由 Bin Wu 撰写，Claude 开发者平台团队贡献。_

---

## 📝 英文原文 / English Original

The future of AI agents is one where models work seamlessly across hundreds or thousands of tools. Today, we're releasing three features:

- **Tool Search Tool**: allows Claude to discover tools on-demand instead of loading all definitions upfront

- **Programmatic Tool Calling**: allows Claude to orchestrate tools through code rather than individual API round-trips

- **Tool Use Examples**: provides a universal standard for demonstrating how to effectively use a given tool

### Tool Search Tool

MCP tool definitions can consume 55K+ tokens before a conversation starts. Tool Search Tool discovers tools on-demand. With `defer_loading: true`, tools aren't loaded into context initially. Claude searches for relevant tools only when needed.

Results: 85% reduction in token usage. Opus 4 improved from 49% to 74%, Opus 4.5 from 79.5% to 88.1%.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Ff359296f770706608901eadaffbff4ca0b67874c-1999x1125.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Ff359296f770706608901eadaffbff4ca0b67874c-1999x1125.png&w=3840&q=75)

### Programmatic Tool Calling

Traditional tool calling creates context pollution from intermediate results and inference overhead. Programmatic Tool Calling enables Claude to orchestrate tools through code.

Example: "Which team members exceeded their Q3 travel budget?" — Claude writes Python that processes 2,000+ expense items but only returns the 2-3 people who exceeded budget. Token consumption drops from 200KB to 1KB.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F65737d69a3290ed5c1f3c3b8dc873645a9dcc2eb-1999x1491.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F65737d69a3290ed5c1f3c3b8dc873645a9dcc2eb-1999x1491.png&w=3840&q=75)

Results: Average token usage dropped from 43,588 to 27,297 (37% reduction). Internal knowledge retrieval improved from 25.6% to 28.5%.

### Tool Use Examples

JSON Schema can't express usage patterns. Tool Use Examples provide concrete sample tool calls directly in tool definitions. Accuracy improved from 72% to 90% on complex parameter handling.

### Best practices

Layer features strategically: context bloat → Tool Search Tool; large intermediate results → Programmatic Tool Calling; parameter errors → Tool Use Examples.

_Written by Bin Wu, with contributions from the Claude Developer Platform team._