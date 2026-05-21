## 中文翻译

[Model Context Protocol (MCP)](https://modelcontextprotocol.io/) 是一个连接 AI 智能体与外部系统的开放标准。传统方法需要为每个配对进行自定义集成，造成碎片化和重复劳动。MCP 提供通用协议——开发者只需实现一次即可解锁整个集成生态系统。

自 2024 年 11 月推出以来，社区已构建了数千个 [MCP 服务器](https://github.com/modelcontextprotocol/servers)，各主要编程语言都有 [SDK](https://modelcontextprotocol.io/docs/sdk)。然而随着连接工具数量增长，预先加载所有工具定义并通过上下文窗口传递中间结果会**拖慢智能体速度并增加成本**。

本文探讨代码执行如何使智能体与 MCP 服务器更高效地交互——处理更多工具同时使用更少 token。

---

### 工具导致的过度 token 消耗

随着 MCP 使用规模扩大，两种常见模式增加成本和延迟：

1. **工具定义使上下文窗口过载**——工具描述占据更多上下文空间，在有数千个工具时需要处理数十万 token

1. **中间工具结果消耗额外 token**——每个中间结果必须通过模型传递，如 2 小时销售会议的完整转录可能需要处理额外 50,000 token

`[此处有一张图片：MCP 客户端与 MCP 服务器和 LLM 的工作方式示意图]`

---

### 通过 MCP 代码执行提升上下文效率

解决方案是将 MCP 服务器呈现为**代码 API** 而非直接工具调用。智能体可以编写代码与 MCP 服务器交互。

一种方法是从连接的 MCP 服务器生成所有可用工具的文件树：

```jsx
servers
├── google-drive
│   ├── getDocument.ts
│   └── index.ts
├── salesforce
│   ├── updateRecord.ts
│   └── index.ts
└── ...
```

之前的 Google Drive 到 Salesforce 示例变成：

```tsx
import * as gdrive from './servers/google-drive';
import * as salesforce from './servers/salesforce';

const transcript = (await gdrive.getDocument({ documentId: 'abc123' })).content;
await salesforce.updateRecord({
  objectType: 'SalesMeeting',
  recordId: '00Q5f000001abcXYZ',
  data: { Notes: transcript }
});
```

> [!important]
> 
> 智能体通过浏览文件系统按需发现工具，仅加载当前任务需要的定义。这将 token 使用从 **150,000 减少到 2,000**——节省时间和成本 **98.7%**。

---

### 代码执行与 MCP 的优势

#### 渐进式披露

模型擅长导航文件系统。将工具呈现为文件系统上的代码，模型可按需读取工具定义。也可添加 `search_tools` 工具，包含 detail level 参数让智能体选择所需的细节级别。

#### 上下文高效的工具结果

处理大型数据集时，智能体可以在代码中过滤和转换结果后再返回：

```tsx
const allRows = await gdrive.getSheet({ sheetId: 'abc123' });
const pendingOrders = allRows.filter(row => row["Status"] === 'pending');
console.log(`Found ${pendingOrders.length} pending orders`);
console.log(pendingOrders.slice(0, 5)); // 只记录前 5 条供审查
```

智能体看到 5 行而非 10,000 行。

#### 更强大且上下文高效的控制流

循环、条件和错误处理可以用熟悉的代码模式完成，而非链接单个工具调用。

#### 隐私保护操作

中间结果默认留在执行环境中。MCP 客户端可以自动对敏感数据进行标记化——真实的电子邮件、电话和姓名从源流向目标，但**永远不通过模型**。

#### 状态持久化与技能

智能体可以将中间结果写入文件，实现跨操作的状态维护。还可以将自己的代码持久化为可复用函数，结合 [Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) 概念构建随时间增长的能力工具箱。

> [!important]
> 
> 代码执行引入自身的复杂性——运行智能体生成的代码需要安全的执行环境，包括适当的[沙盒化](https://www.anthropic.com/engineering/claude-code-sandboxing)、资源限制和监控。这些基础设施需求需要与代码执行的好处（减少 token 成本、降低延迟、改进工具组合）权衡。

---

### 总结

MCP 为智能体连接工具和系统提供了基础协议。代码执行将成熟的软件工程模式应用于智能体，让它们使用熟悉的编程结构更高效地与 MCP 服务器交互。

---

_致谢：由 Adam Jones 和 Conor Kelly 撰写。_

---

## 📝 英文原文 / English Original

[The Model Context Protocol (MCP)](https://modelcontextprotocol.io/) is an open standard for connecting AI agents to external systems. As the number of connected tools grows, loading all tool definitions upfront and passing intermediate results through the context window slows down agents and increases costs.

Code execution can enable agents to interact with MCP servers more efficiently, handling more tools while using fewer tokens.

### Excessive token consumption from tools

1. Tool definitions overload the context window

1. Intermediate tool results consume additional tokens

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F9ecf165020005c09a22a9472cee6309555485619-1920x1080.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F9ecf165020005c09a22a9472cee6309555485619-1920x1080.png&w=3840&q=75)

### Code execution with MCP improves context efficiency

Present MCP servers as code APIs rather than direct tool calls. Generate a file tree of all available tools. The agent discovers tools by exploring the filesystem, loading only what it needs. Token usage drops from 150,000 to 2,000—a 98.7% saving.

### Benefits

**Progressive disclosure:** Models navigate filesystems to read tool definitions on-demand.

**Context efficient tool results:** Filter and transform results in code before returning them. Agent sees 5 rows instead of 10,000.

**More powerful control flow:** Loops, conditionals, and error handling in code rather than chaining tool calls.

**Privacy-preserving operations:** Intermediate results stay in the execution environment. MCP client can tokenize PII automatically.

**State persistence and skills:** Write intermediate results to files. Persist code as reusable functions tied to Skills.

Note: Code execution introduces complexity—sandboxing, resource limits, monitoring. Weigh benefits against implementation costs.

_Written by Adam Jones and Conor Kelly._