> 📚 **原文链接:** [极客时间专栏](https://time.geekbang.org/column/article/889985)

> [!important]
>
> **写在前面:** 最近我在极客时间上线了一门新课《MCP & A2A 前沿实战》,其中第 14 节课我用 LangGraph 和 A2A 实现了一个货币兑换 Agent。刚好有二刷课程的小伙伴提到,希望我分享一些 LangGraph 的相关内容,于是我就把这节内容也加到了我们这门课里。
>
> 前面两次直播,我分别讲了 LCEL、LangSmith,刚好再加上 LangGraph,LangChain 的版图就更完整了。

你好,我是黄佳。

这一课中,我带着你详细看一看 A2A Demo 系统中的另一个 Agent:用 LangGraph 搭建的"货币兑换"Agent(位于 `a2a-in-action` 代码库的 `agents/langgraph_zh` 目录)。

---

## 从 LangChain 到 LangGraph

LangChain 是最早出现的一批大模型应用开发的主流框架。我对这个框架可以说是充满了感情。2023 年的时候也推出过《LangChain 实战课》。时至今日,虽然 LangChain 早已不能代表 LLM 应用开发的全部,但是,我依然认为,LangChain 的文档组织体系,非常有利于初学者对大模型应用开发建立一个概述性的了解。

[![](https://static001.geekbang.org/resource/image/af/33/af03986dcdb3eb0d71ed8458a8db0c33.jpg?wh=2380x2500)](https://static001.geekbang.org/resource/image/af/33/af03986dcdb3eb0d71ed8458a8db0c33.jpg?wh=2380x2500)

LangChain 生态系统

LangChain 作为早期的大模型开发框架,曾经扮演了"打通任督二脉"的重要角色——它把提示词、模型、工具调用、记忆管理、检索增强(RAG)等模块组织成链式结构。

然而,随着项目越来越复杂,LangChain 的链式结构开始暴露出几个明显的局限:

1. **流程不透明、调试困难:** 链条中间没有明确的状态表达,出错时难以定位

1. **缺乏并发与分支控制能力:** 只能"从左到右"执行,面对多轮对话、并行任务力不从心

1. **Agent 系统复杂难控:** LangChain Agent 的"反复推理 + 工具调用"机制在实际工程中不稳定

### LCEL → LangGraph 的演进

于是,LangChain 团队在 2024 年推出了 **LCEL**(LangChain Expression Language),一种基于组合子的新语言,用更明确的语法组织调用逻辑。但即使有了 LCEL,复杂流程仍需要状态管理、任务调度、失败重试等机制。

于是,**LangGraph** 诞生了——一个基于有向图(DAG)思想的 LLM 应用编排框架。

> [!important]
>
> **LCEL:** 描述单个"图节点"的调用逻辑(比如一个子任务、一个 API 调用)
>
> **LangGraph:** 编排多个节点,负责整个工作流的调度、状态跳转与生命周期控制

[![](https://static001.geekbang.org/resource/image/a9/21/a987de86f69e4c08641b077ce4b6e221.png?wh=1091x716)](https://static001.geekbang.org/resource/image/a9/21/a987de86f69e4c08641b077ce4b6e221.png?wh=1091x716)

LangChain 整个生态系统

LangGraph 的典型优势包括:

- 支持**状态机驱动**的流程控制,每个节点根据当前状态决定是否触发

- 支持**并行与条件分支**,天然适配多智能体(Multi-Agent)交互场景

- 内置**缓存、持久化、观测接口**,便于运维与监控

- 可与 **LangSmith** 配合使用,实现可视化追踪、错误调试与性能分析

[![](https://static001.geekbang.org/resource/image/86/61/8687ddd2e3635cbe7yy8c20203da5361.png?wh=1738x793)](https://static001.geekbang.org/resource/image/86/61/8687ddd2e3635cbe7yy8c20203da5361.png?wh=1738x793)

用 LangSmith Tracing LLM 应用开发

---

## 基于 LangGraph 构建货币兑换智能体

下面,我们来构建一个"极简版 LangGraph 汇率 Agent"。目标非常明确:理解用户输入中的货币转换需求,调用汇率 API 获取最新数据,最后给出自然语言的回应。

[![](https://static001.geekbang.org/resource/image/c1/76/c1e3bf7f90c4f67645bccaefec51ed76.jpg?wh=4847x3897)](https://static001.geekbang.org/resource/image/c1/76/c1e3bf7f90c4f67645bccaefec51ed76.jpg?wh=4847x3897)

LangGraph_Currency-v1 的 Graph 工作流

### 导入库和配置工具

```python
import os
import httpx
from typing import TypedDict, Annotated
from dotenv import load_dotenv
from langchain_core.messages import HumanMessage, AIMessage
from langchain_core.tools import tool
from langchain_google_genai import ChatGoogleGenerativeAI
from langgraph.graph import StateGraph, END
from langgraph.checkpoint.memory import MemorySaver

load_dotenv()
```

### 定义状态和工具

```python
class CurrencyState(TypedDict):
    """汇率转换状态"""
    messages: Annotated[list, "对话消息列表"]
    exchange_data: Annotated[dict, "汇率数据"]

@tool
def get_exchange_rate(currency_from: str = 'USD', currency_to: str = 'CNY') -> dict:
    """获取汇率信息"""
    try:
        response = httpx.get(
            f'https://api.frankfurter.app/latest',
            params={'from': currency_from, 'to': currency_to},
            timeout=10.0
        )
        response.raise_for_status()
        return response.json()
    except Exception as e:
        return {'error': f'获取汇率失败: {e}'}
```

### Agent 类的核心实现

Agent 由三部分构成:**用户意图解析**、**汇率调用**、**回应生成**。分别映射为 LangGraph 中的三个节点:`process_query`、`get_rate` 和 `respond`。

```python
class SimpleCurrencyAgent:
    """极简汇率Agent"""
    def __init__(self):
        self.llm = ChatGoogleGenerativeAI(
            model='gemini-2.0-flash',
            api_key=os.getenv('GOOGLE_API_KEY')
        )
        self.graph = self._create_graph()

    def _process_query(self, state: CurrencyState) -> CurrencyState:
        """处理用户查询 - 从用户输入中提取币种代码"""
        user_message = state["messages"][-1].content
        currencies = {
            '美元': 'USD', '人民币': 'CNY', '欧元': 'EUR', '日元': 'JPY',
            '英镑': 'GBP', '澳元': 'AUD', '港币': 'HKD', '韩元': 'KRW'
        }
        # ... 关键词匹配识别币种逻辑 ...
        return state

    def _get_rate(self, state: CurrencyState) -> CurrencyState:
        """获取汇率数据"""
        exchange_data = state["exchange_data"]
        if "error" in exchange_data:
            return state
        rate_data = get_exchange_rate.invoke({
            "currency_from": exchange_data["from_currency"],
            "currency_to": exchange_data["to_currency"]
        })
        exchange_data.update(rate_data)
        return state

    def _respond(self, state: CurrencyState) -> CurrencyState:
        """生成响应"""
        exchange_data = state["exchange_data"]
        # ... 根据汇率数据生成自然语言回复 ...
        return state
```

### 构建工作流图

```python
def _create_graph(self):
    """创建LangGraph工作流"""
    memory = MemorySaver()
    workflow = StateGraph(CurrencyState)

    # 添加节点
    workflow.add_node("process_query", self._process_query)
    workflow.add_node("get_rate", self._get_rate)
    workflow.add_node("respond", self._respond)

    # 设置入口点
    workflow.set_entry_point("process_query")

    # 添加边
    workflow.add_edge("process_query", "get_rate")
    workflow.add_edge("get_rate", "respond")
    workflow.add_edge("respond", END)

    return workflow.compile(checkpointer=memory)
```

> [!important]
>
> **关键组件说明:**
>
> - `MemorySaver()` — 内存型检查点,记录每一步的状态数据
>
> - `StateGraph(CurrencyState)` — 创建有状态的图,每一步处理时读写状态
>
> - `add_node()` — 加入处理节点
>
> - `set_entry_point()` — 设置流程起始点
>
> - `add_edge()` — 定义节点间的转移路径
>
> - `compile()` — 编译成可运行的工作流对象

---

## 为智能体增加意图识别条件分支

上面的工作流虽然清晰,但未体现出 LangGraph 在 Agentic Workflow 方面的灵活性。下面,我们要增加条件分支:用 LLM 来判断,如果是相关问题进入汇率计算;如果不相关,直接输出说明。

[![](https://static001.geekbang.org/resource/image/d1/10/d1f31614dbcbc586c89776e1a00c2110.jpg?wh=2027x1676)](https://static001.geekbang.org/resource/image/d1/10/d1f31614dbcbc586c89776e1a00c2110.jpg?wh=2027x1676)

V2 版本的 Graph 工作流

### V2 版本工作流架构增强

```python
workflow = StateGraph(CurrencyState)
workflow.add_node("process_query", self._process_query)
workflow.add_node("get_rate", self._get_rate)
workflow.add_node("respond", self._respond)
workflow.add_node("respond_irrelevant", self._respond_irrelevant)

workflow.set_entry_point("process_query")

# 条件分支：根据意图识别结果选择路径
workflow.add_conditional_edges(
    "process_query",
    self._should_get_rate,
    {
        "get_rate": "get_rate",
        "respond_irrelevant": "respond_irrelevant"
    }
)
workflow.add_edge("get_rate", "respond")
workflow.add_edge("respond", END)
workflow.add_edge("respond_irrelevant", END)

return workflow.compile(checkpointer=memory)
```

### V1 vs V2 对比

> [!important]
>
> **V1(线性工作流):** `process_query → get_rate → respond`,所有查询经过相同流程,使用 `add_edge()` 添加简单边
>
> **V2(条件分支工作流):** `process_query → [get_rate | respond_irrelevant]`,根据查询意图分叉到不同路径,使用 `add_conditional_edges()` 添加条件边

### 意图识别方式对比

V1 使用基于关键词的静态判断:

```python
currency_keywords = ['汇率', '兑', '换', '美元', '人民币', ...]
is_currency_query = any(keyword in user_message for keyword in currency_keywords)
```

V2 使用 **LLM 智能意图识别**:

```python
prompt = f"""
请判断以下用户查询是否与货币转换、汇率查询相关。
用户查询: "{user_message}"
请只回答 "是" 或 "否"。
"""
response = self.llm.invoke(prompt)
is_currency_query = "是" in response.content.strip()
```

### V2 新增函数

```python
def _should_get_rate(self, state: CurrencyState) -> str:
    """判断是否应该获取汇率"""
    exchange_data = state["exchange_data"]
    return "get_rate" if exchange_data.get("is_currency_query", False) else "respond_irrelevant"

def _respond_irrelevant(self, state: CurrencyState) -> CurrencyState:
    """生成不相关查询的响应"""
    exchange_data = state["exchange_data"]
    response_content = exchange_data.get("error", "抱歉，我只能协助货币转换和汇率查询。")
    ai_message = AIMessage(content=response_content)
    state["messages"].append(ai_message)
    return state
```

---

## LangGraph Agent 和 A2A 的集成

掌握了 LangGraph 的核心设计思想,最后来看如何把 LangGraph 构建的货币转换 Agent 集成到 A2A 协议架构中。

### Agent 封装与 ReAct 模式

A2A 代码库中的 LangGraph Agent 采用了 **ReAct**(Reasoning + Acting)模式:

```python
class CurrencyAgent:
    SYSTEM_INSTRUCTION = (
        '你是专门进行货币转换的助手。'
        "你的唯一目的是使用'get_exchange_rate'工具来回答有关汇率的问题。"
        '如果用户询问除货币转换或汇率之外的任何内容，'
        '请礼貌地说明你无法帮助该主题。'
    )

    def __init__(self):
        self.model = ChatGoogleGenerativeAI(model='gemini-2.0-flash')
        self.tools = [get_exchange_rate]
        self.graph = create_react_agent(
            self.model,
            tools=self.tools,
            checkpointer=memory,
            prompt=self.SYSTEM_INSTRUCTION,
            response_format=ResponseFormat,
        )
```

### 流式响应处理

LangGraph 的 `.stream()` 方法支持输出过程的每一步,实现 A2A 所需的流式交互:

```python
async def stream(self, query, sessionId) -> AsyncIterable[dict[str, Any]]:
    inputs = {'messages': [('user', query)]}
    config = {'configurable': {'thread_id': sessionId}}

    for item in self.graph.stream(inputs, config, stream_mode='values'):
        message = item['messages'][-1]
        if isinstance(message, AIMessage) and message.tool_calls:
            yield {
                'is_task_complete': False,
                'require_user_input': False,
                'content': '正在查询汇率…',
            }
        elif isinstance(message, ToolMessage):
            yield {
                'is_task_complete': False,
                'require_user_input': False,
                'content': '正在处理汇率数据…',
            }
    yield self.get_agent_response(config)
```

> [!important]
>
> **流式处理特点:**
>
> - **状态识别:** 根据消息类型判断处理阶段
>
> - **进度反馈:** 实时返回处理状态
>
> - **最终结果:** 流式结束后返回完整响应

### 任务调度与生命周期管理

通过 A2A `TaskManager` 实现异步任务调度:

```python
class AgentTaskManager(InMemoryTaskManager):
    def __init__(self, agent: CurrencyAgent, notification_sender_auth):
        super().__init__()
        self.agent = agent
        self.notification_sender_auth = notification_sender_auth
```

整条闭环:**LangGraph Agent 构建 → A2A 异步调度 → SSE 推送 → UI 状态同步**。

---

## 总结一下

> [!important]
>
> **前半部分:** 介绍了 LangChain → LCEL → LangGraph 的演进过程,并构建了简单的 LangGraph Agent(V1 线性流程 + V2 条件分支)
>
> **后半部分:** 从单体 Agent 到 A2A Agent 架构的演进。从 LangGraph Agent 到 A2A TaskManager,再到 SSE/Webhook 推送和 UI 状态更新,构成了一个高度解耦、异步驱动、任务可追踪的现代化 AI Agent 架构。

---

## 思考题

1. 目前 V2 版本使用简单的模板化回复。你可否改造一下,使用 LLM 生成智能回复,让响应内容更加个性化和友好?

> [!important]
>
> **提示:** 参考 A2A Repo 中的 `agents/langgraph_zh/02_LangGraph_``[Currency-v3.py](http://Currency-v3.py)`

1. LangGraph Agent 的 V2 版本和 A2A Sample 中的 `[Agent.py](http://Agent.py)` 从工作流程控制方面有哪些差异?在你的工作场景中,你比较倾向于选择哪种实现方式,为什么?

期待你在留言区分享你的思考或者疑问,如果这节课对你有启发,别忘了分享给身边更多朋友!


课程封面
