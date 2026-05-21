这是一份面向实战的 LangChain 和 LangGraph 开发教程，你可以跟着每个步骤动手操作，从零开始构建自己的 Agent 应用。

## 核心概念速览

**LangChain** 是高层框架，提供预构建的 Agent 架构和模型集成，适合快速开发简单 Agent 应用。

**LangGraph** 是低层编排框架，专注于复杂的状态管理、持久化执行和工作流控制，适合构建生产级的长运行 Agent 系统。

**选择建议：**

- 快速原型 & 简单应用 → LangChain

- 复杂工作流 & 生产部署 → LangGraph

- 最佳实践：LangChain 的 Agent 底层使用 LangGraph 构建

---

## 第一步：环境准备

### 1.1 安装依赖

```bash
# 创建项目目录
mkdir my-agent-project
cd my-agent-project
npm init -y

# 安装核心包
npm install langchain @langchain/langgraph @langchain/core

# 安装模型提供商（选择一个或多个）
npm install @langchain/anthropic  # Claude
npm install @langchain/openai     # GPT
npm install @langchain/google-genai  # Gemini

# 安装辅助工具
npm install zod  # 用于工具参数验证
npm install dotenv  # 环境变量管理
```

### 1.2 配置 API Key

创建 `.env` 文件：

```bash
# 根据你选择的模型提供商配置对应的 Key
ANTHROPIC_API_KEY=your_anthropic_key_here
OPENAI_API_KEY=your_openai_key_here
GOOGLE_API_KEY=your_google_key_here
```

### 1.3 项目结构

```jsx
my-agent-project/
├── package.json
├── .env
├── src/
│   ├── langchain-demo.ts    # LangChain 示例
│   ├── langgraph-demo.ts    # LangGraph 示例
│   └── tools.ts             # 自定义工具
└── tsconfig.json
```

配置 TypeScript（可选但推荐）：

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "commonjs",
    "outDir": "./dist",
    "rootDir": "./src",
    "strict": true,
    "esModuleInterop": true
  }
}
```

---

## 第二步：LangChain 快速入门

### 2.1 最简单的 Agent（10 行代码）

创建 `src/langchain-demo.ts`：

```tsx
import { createAgent, tool } from "langchain";
import * as z from "zod";
import "dotenv/config";

// 定义一个简单的工具
const getWeather = tool(
  ({ city }) => `${city} 当前天气：晴天，25°C`,
  {
    name: "get_weather",
    description: "获取指定城市的天气信息",
    schema: z.object({
      city: z.string().describe("城市名称"),
    }),
  }
);

// 创建 Agent
const agent = createAgent({
  model: "claude-sonnet-4-5-20250929", // 或 "gpt-4o" 等
  tools: [getWeather],
});

// 运行 Agent
async function main() {
  const result = await agent.invoke({
    messages: [
      { role: "user", content: "北京的天气怎么样？" }
    ],
  });
  
  console.log(result.messages[result.messages.length - 1].content);
}

main();
```

**运行：**

```bash
npx tsx src/langchain-demo.ts
```

### 2.2 添加多个工具

创建 `src/tools.ts`：

```tsx
import { tool } from "langchain";
import * as z from "zod";

// 天气工具
export const getWeather = tool(
  ({ city }) => {
    const weatherData = {
      "北京": "晴天 25°C",
      "上海": "多云 28°C",
      "深圳": "雨天 22°C",
    };
    return weatherData[city] || `${city} 天气信息未知`;
  },
  {
    name: "get_weather",
    description: "获取城市天气",
    schema: z.object({ city: z.string() }),
  }
);

// 计算工具
export const calculator = tool(
  ({ expression }) => {
    try {
      // 注意：生产环境应使用安全的计算库
      return String(eval(expression));
    } catch (e) {
      return "计算错误";
    }
  },
  {
    name: "calculator",
    description: "执行数学计算",
    schema: z.object({
      expression: z.string().describe("数学表达式，如 '2+2' 或 '10*5'"),
    }),
  }
);

// 搜索工具（模拟）
export const search = tool(
  ({ query }) => {
    return `关于 "${query}" 的搜索结果：这是一个模拟的搜索结果...`;
  },
  {
    name: "search",
    description: "搜索信息",
    schema: z.object({ query: z.string() }),
  }
);
```

更新 Agent：

```tsx
import { createAgent } from "langchain";
import { getWeather, calculator, search } from "./tools";
import "dotenv/config";

const agent = createAgent({
  model: "claude-sonnet-4-5-20250929",
  tools: [getWeather, calculator, search],
});

async function main() {
  const queries = [
    "北京天气如何？",
    "125 乘以 47 等于多少？",
    "搜索 LangGraph 的最新特性",
  ];
  
  for (const query of queries) {
    console.log(`\n\n用户: ${query}`);
    const result = await agent.invoke({
      messages: [{ role: "user", content: query }],
    });
    console.log(`Agent: ${result.messages[result.messages.length - 1].content}`);
  }
}

main();
```

### 2.3 添加上下文和记忆

```tsx
import { createAgent } from "langchain";
import { getWeather, calculator } from "./tools";

const agent = createAgent({
  model: "claude-sonnet-4-5-20250929",
  tools: [getWeather, calculator],
});

// 维护对话历史
const messages = [];

async function chat(userMessage: string) {
  messages.push({ role: "user", content: userMessage });
  
  const result = await agent.invoke({ messages });
  
  // 更新历史记录
  messages.push(...result.messages.slice(messages.length));
  
  return result.messages[result.messages.length - 1].content;
}

async function main() {
  console.log(await chat("北京天气怎么样？"));
  console.log(await chat("那上海呢？"));  // Agent 能理解上下文
  console.log(await chat("帮我算一下 99 * 88"));
}

main();
```

---

## 第三步：LangGraph 深入实战

### 3.1 理解核心概念

**State（状态）：** 工作流在节点间传递的数据结构

**Node（节点）：** 执行具体逻辑的函数

**Edge（边）：** 连接节点，定义执行流程

**Graph（图）：** 节点和边的组合，代表完整工作流

### 3.2 第一个 LangGraph 应用

创建 `src/langgraph-demo.ts`：

```tsx
import {
  StateSchema,
  MessagesValue,
  GraphNode,
  StateGraph,
  START,
  END,
} from "@langchain/langgraph";
import { ChatAnthropic } from "@langchain/anthropic";
import "dotenv/config";

// 定义状态结构
const State = new StateSchema({
  messages: MessagesValue,
});

// 定义节点：调用 LLM
const llmNode: GraphNode<typeof State> = async (state) => {
  const model = new ChatAnthropic({
    modelName: "claude-sonnet-4-5-20250929",
  });
  
  const response = await model.invoke(state.messages);
  
  return {
    messages: [response],
  };
};

// 构建图
const graph = new StateGraph(State)
  .addNode("llm", llmNode)
  .addEdge(START, "llm")
  .addEdge("llm", END)
  .compile();

// 运行
async function main() {
  const result = await graph.invoke({
    messages: [{ role: "user", content: "你好！" }],
  });
  
  console.log(result.messages[result.messages.length - 1].content);
}

main();
```

### 3.3 添加工具调用节点

```tsx
import {
  StateSchema,
  MessagesValue,
  GraphNode,
  StateGraph,
  START,
  END,
} from "@langchain/langgraph";
import { ChatAnthropic } from "@langchain/anthropic";
import { tool } from "langchain";
import * as z from "zod";
import "dotenv/config";

// 定义状态
const State = new StateSchema({
  messages: MessagesValue,
});

// 定义工具
const getWeather = tool(
  ({ city }) => `${city}: 晴天 25°C`,
  {
    name: "get_weather",
    description: "获取天气",
    schema: z.object({ city: z.string() }),
  }
);

const tools = [getWeather];

// LLM 节点（支持工具调用）
const llmNode: GraphNode<typeof State> = async (state) => {
  const model = new ChatAnthropic({
    modelName: "claude-sonnet-4-5-20250929",
  }).bindTools(tools);
  
  const response = await model.invoke(state.messages);
  return { messages: [response] };
};

// 工具执行节点
const toolNode: GraphNode<typeof State> = async (state) => {
  const lastMessage = state.messages[state.messages.length - 1];
  
  if (!lastMessage.tool_calls || lastMessage.tool_calls.length === 0) {
    return { messages: [] };
  }
  
  const toolResults = [];
  
  for (const toolCall of lastMessage.tool_calls) {
    const tool = tools.find(t => t.name === toolCall.name);
    if (tool) {
      const result = await tool.invoke(toolCall.args);
      toolResults.push({
        role: "tool",
        content: result,
        tool_call_id: toolCall.id,
      });
    }
  }
  
  return { messages: toolResults };
};

// 路由函数：判断是否需要调用工具
function shouldContinue(state: typeof State.State) {
  const lastMessage = state.messages[state.messages.length - 1];
  if (lastMessage.tool_calls && lastMessage.tool_calls.length > 0) {
    return "tools";  // 需要执行工具
  }
  return END;  // 直接结束
}

// 构建带条件路由的图
const graph = new StateGraph(State)
  .addNode("llm", llmNode)
  .addNode("tools", toolNode)
  .addEdge(START, "llm")
  .addConditionalEdges("llm", shouldContinue, {
    tools: "tools",
    [END]: END,
  })
  .addEdge("tools", "llm")  // 执行工具后回到 LLM
  .compile();

async function main() {
  const result = await graph.invoke({
    messages: [{ role: "user", content: "北京天气如何？" }],
  });
  
  console.log("\n完整对话历史：");
  result.messages.forEach((msg, i) => {
    console.log(`${i + 1}. [${msg.role}]: ${msg.content || JSON.stringify(msg.tool_calls)}`);
  });
}

main();
```

### 3.4 添加持久化和检查点

```tsx
import { MemorySaver } from "@langchain/langgraph";

// 创建内存持久化存储
const memory = new MemorySaver();

// 编译时添加检查点
const graph = new StateGraph(State)
  .addNode("llm", llmNode)
  .addNode("tools", toolNode)
  .addEdge(START, "llm")
  .addConditionalEdges("llm", shouldContinue)
  .addEdge("tools", "llm")
  .compile({ checkpointer: memory });

// 使用线程 ID 维护会话
async function main() {
  const threadId = "user-123";
  
  // 第一轮对话
  let result = await graph.invoke(
    { messages: [{ role: "user", content: "北京天气？" }] },
    { configurable: { thread_id: threadId } }
  );
  console.log(result.messages[result.messages.length - 1].content);
  
  // 第二轮对话（会记住上下文）
  result = await graph.invoke(
    { messages: [{ role: "user", content: "上海呢？" }] },
    { configurable: { thread_id: threadId } }
  );
  console.log(result.messages[result.messages.length - 1].content);
}

main();
```

### 3.5 人机交互（Human-in-the-Loop）

```tsx
import { interrupt } from "@langchain/langgraph";

// 添加需要人工确认的节点
const confirmationNode: GraphNode<typeof State> = async (state) => {
  const lastMessage = state.messages[state.messages.length - 1];
  
  // 模拟需要人工确认的场景
  if (lastMessage.content?.includes("删除")) {
    // 中断执行，等待人工确认
    await interrupt("需要确认删除操作");
  }
  
  return { messages: [] };
};

const graph = new StateGraph(State)
  .addNode("llm", llmNode)
  .addNode("confirmation", confirmationNode)
  .addNode("tools", toolNode)
  .addEdge(START, "llm")
  .addEdge("llm", "confirmation")
  .addEdge("confirmation", "tools")
  .addEdge("tools", END)
  .compile({ checkpointer: new MemorySaver() });

// 运行并处理中断
async function main() {
  const threadId = "session-456";
  
  try {
    const result = await graph.invoke(
      { messages: [{ role: "user", content: "删除所有文件" }] },
      { configurable: { thread_id: threadId } }
    );
  } catch (error) {
    if (error.message.includes("中断")) {
      console.log("检测到敏感操作，等待人工确认...");
      
      // 人工确认后继续执行
      const confirmed = true;  // 实际应用中从用户输入获取
      
      if (confirmed) {
        const result = await graph.invoke(
          null,  // 从中断点继续
          { configurable: { thread_id: threadId } }
        );
        console.log("操作已执行");
      }
    }
  }
}
```

---

## 第四步：实战案例 - 研究助手 Agent

### 4.1 功能需求

构建一个能够：

1. 搜索信息

1. 总结内容

1. 生成研究报告

的研究助手。

### 4.2 完整实现

```tsx
import {
  StateSchema,
  MessagesValue,
  GraphNode,
  StateGraph,
  START,
  END,
  MemorySaver,
} from "@langchain/langgraph";
import { ChatAnthropic } from "@langchain/anthropic";
import { tool } from "langchain";
import * as z from "zod";

// 扩展状态：添加研究主题和收集的信息
const State = new StateSchema({
  messages: MessagesValue,
  topic: z.string().optional(),
  research_data: z.array(z.string()).default([]),
  report: z.string().optional(),
});

// 工具定义
const searchWeb = tool(
  ({ query }) => {
    // 模拟搜索结果
    return `关于 "${query}" 的搜索结果：
1. 定义和核心概念...
2. 最新发展趋势...
3. 实际应用案例...`;
  },
  {
    name: "search_web",
    description: "搜索互联网信息",
    schema: z.object({ query: z.string() }),
  }
);

const tools = [searchWeb];

// 节点1：理解研究主题
const parseTopicNode: GraphNode<typeof State> = async (state) => {
  const userMessage = state.messages.find(m => m.role === "user");
  const topic = userMessage?.content || "";
  
  return {
    topic,
    messages: [{
      role: "assistant",
      content: `开始研究主题：${topic}`,
    }],
  };
};

// 节点2：信息收集（调用搜索工具）
const researchNode: GraphNode<typeof State> = async (state) => {
  const model = new ChatAnthropic({
    modelName: "claude-sonnet-4-5-20250929",
  }).bindTools(tools);
  
  const response = await model.invoke([
    { role: "user", content: `搜索关于 "${state.topic}" 的详细信息` },
  ]);
  
  return { messages: [response] };
};

// 节点3：执行工具
const executeToolsNode: GraphNode<typeof State> = async (state) => {
  const lastMessage = state.messages[state.messages.length - 1];
  
  if (!lastMessage.tool_calls?.length) {
    return { messages: [] };
  }
  
  const results = [];
  const researchData = [...state.research_data];
  
  for (const toolCall of lastMessage.tool_calls) {
    const tool = tools.find(t => t.name === toolCall.name);
    if (tool) {
      const result = await tool.invoke(toolCall.args);
      results.push({
        role: "tool",
        content: result,
        tool_call_id: toolCall.id,
      });
      researchData.push(result);  // 收集研究数据
    }
  }
  
  return {
    messages: results,
    research_data: researchData,
  };
};

// 节点4：生成报告
const generateReportNode: GraphNode<typeof State> = async (state) => {
  const model = new ChatAnthropic({
    modelName: "claude-sonnet-4-5-20250929",
  });
  
  const prompt = `基于以下研究数据，生成一份关于 "${state.topic}" 的简明报告：

${state.research_data.join("\n\n")}

请生成结构化报告，包含：
1. 概述
2. 关键发现
3. 结论`;
  
  const response = await model.invoke([{ role: "user", content: prompt }]);
  
  return {
    report: response.content,
    messages: [response],
  };
};

// 路由逻辑
function shouldContinue(state: typeof State.State) {
  const lastMessage = state.messages[state.messages.length - 1];
  
  if (lastMessage.tool_calls?.length) {
    return "execute_tools";
  }
  
  if (state.research_data.length > 0 && !state.report) {
    return "generate_report";
  }
  
  return END;
}

// 构建工作流图
const graph = new StateGraph(State)
  .addNode("parse_topic", parseTopicNode)
  .addNode("research", researchNode)
  .addNode("execute_tools", executeToolsNode)
  .addNode("generate_report", generateReportNode)
  .addEdge(START, "parse_topic")
  .addEdge("parse_topic", "research")
  .addConditionalEdges("research", shouldContinue, {
    execute_tools: "execute_tools",
    generate_report: "generate_report",
    [END]: END,
  })
  .addEdge("execute_tools", "research")  // 执行工具后可能需要更多搜索
  .addEdge("generate_report", END)
  .compile({ checkpointer: new MemorySaver() });

// 运行研究助手
async function main() {
  const result = await graph.invoke(
    {
      messages: [{
        role: "user",
        content: "研究 LangGraph 在生产环境中的应用",
      }],
    },
    { configurable: { thread_id: "research-session-1" } }
  );
  
  console.log("\n=== 研究报告 ===");
  console.log(result.report);
  
  console.log("\n=== 收集的数据 ===");
  result.research_data.forEach((data, i) => {
    console.log(`\n数据源 ${i + 1}:\n${data}`);
  });
}

main();
```

---

## 第五步：流式输出与调试

### 5.1 实现流式响应

```tsx
// 使用 stream 替代 invoke
async function streamDemo() {
  const stream = await graph.stream(
    {
      messages: [{ role: "user", content: "介绍一下 LangGraph" }],
    },
    { configurable: { thread_id: "stream-demo" } }
  );
  
  for await (const chunk of stream) {
    console.log("\n--- 节点输出 ---");
    console.log(JSON.stringify(chunk, null, 2));
  }
}
```

### 5.2 集成 LangSmith 调试

```bash
# 安装 LangSmith
npm install langsmith
```

配置环境变量（`.env`）：

```bash
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langsmith_api_key
LANGCHAIN_PROJECT=my-agent-project
```

无需修改代码，所有调用会自动追踪到 LangSmith 平台。

---

## 第六步：部署到生产环境

### 6.1 使用 LangGraph Server

```bash
# 安装 LangGraph CLI
npm install -g @langchain/langgraph-cli

# 创建配置文件
langgraph init
```

创建 `langgraph.json`：

```json
{
  "graphs": {
    "research_agent": "./src/langgraph-demo.ts:graph"
  },
  "env": ".env"
}
```

启动本地服务器：

```bash
langgraph dev
```

### 6.2 Docker 部署

创建 `Dockerfile`：

```docker
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm ci --production

COPY . .

EXPOSE 8000

CMD ["npx", "langgraph", "serve"]
```

构建和运行：

```bash
docker build -t my-agent .
docker run -p 8000:8000 --env-file .env my-agent
```

---

## 学习路径建议

### 短期目标（1-2周）

- [ ] 完成本文档所有示例代码

- [ ] 构建一个自定义工具集（至少 3 个工具）

- [ ] 实现一个完整的对话 Agent

- [ ] 理解 State、Node、Edge 概念

### 中期目标（1个月）

- [ ] 掌握条件路由和多分支逻辑

- [ ] 实现持久化存储和会话管理

- [ ] 添加 Human-in-the-Loop 功能

- [ ] 集成向量数据库（ChromaDB/Pinecone）实现 RAG

- [ ] 使用 LangSmith 进行调试和优化

### 长期目标（2-3个月）

- [ ] 构建生产级 Multi-Agent 系统

- [ ] 实现复杂的工作流编排（Plan-and-Execute）

- [ ] 添加长期记忆和上下文压缩

- [ ] 部署到云平台（AWS/GCP/Azure）

- [ ] 性能优化和错误处理

---

## 常见问题

> **Q: LangChain 和 LangGraph 应该选哪个？**

A: 从 LangChain 开始，它更简单。当你需要复杂状态管理、持久化或多步骤工作流时，迁移到 LangGraph。

> **Q: 如何选择模型提供商？**

A:

- Claude (Anthropic): 推理能力强，适合复杂任务

- GPT-4 (OpenAI): 生态成熟，文档丰富

- Gemini (Google): 性价比高，支持长上下文

> **Q: 工具调用失败怎么办？**

A:

1. 检查工具的 schema 定义是否清晰

1. 在 description 中详细说明使用场景

1. 添加错误处理和重试逻辑

1. 使用 LangSmith 追踪工具调用过程

> **Q: 如何优化 Agent 性能？**

A:

- 使用流式输出减少等待时间

- 添加缓存层避免重复调用

- 优化 prompt 减少 token 消耗

- 并行执行独立的工具调用

---

## 参考资源

**官方文档**

- [LangChain 文档](https://docs.langchain.com/oss/javascript/langchain/overview)

- [LangGraph 文档](https://docs.langchain.com/oss/javascript/langgraph/overview)

- [LangSmith 平台](https://smith.langchain.com)

**进阶主题**

- Context Engineering（上下文工程）

- ReAct 模式

- Plan-and-Execute 架构

- Multi-Agent 协作

- Computer Use（让 Agent 操作计算机）

**社区资源**

- GitHub 示例仓库

- Discord 社区

- YouTube 教程

---

**下一步行动**

1. 按顺序运行每个代码示例

1. 修改参数和工具，观察行为变化

1. 构建一个解决实际问题的 Agent

1. 分享你的成果并获取反馈

**祝你开发顺利！** 🚀