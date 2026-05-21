> **课程来源**: [极客时间 - LangChain 实战课](https://time.geekbang.org/column/article/707191)

[![](https://static001.geekbang.org/resource/image/44/f8/447599829a488074d6b9a892e0dd0ef8.jpg)](https://static001.geekbang.org/resource/image/44/f8/447599829a488074d6b9a892e0dd0ef8.jpg)

课程封面

---

# 大模型的固有问题

在之前介绍的**思维链（CoT）**中，我向你展示了 LLMs 执行推理轨迹的能力。在给出答案之前，大模型通过中间推理步骤（尤其是与少样本提示相结合）能够实现复杂的推理，获得更好的结果，以完成更具挑战的任务。

然而，仅仅应用思维链推理并不能解决大模型的固有问题：**无法主动更新自己的知识，导致出现事实幻觉**。

> [!important]
>
> **知识局限性**
>
> 因为缺乏和外部世界的接触，大模型只拥有：
>
> - 训练时见过的知识
>
> - 提示信息中作为上下文提供的附加知识
>
> 如果你问的问题超出它的知识范围，要么大模型向你坦白："我的训练时间截至 XXXX 年 XX 月 XX 日"，要么它就会开始**一本正经地胡说八道**。

[![](https://static001.geekbang.org/resource/image/50/45/50050ee434877dc4617a7cfe49386a45.png?wh=1443x581)](https://static001.geekbang.org/resource/image/50/45/50050ee434877dc4617a7cfe49386a45.png?wh=1443x581)

遇到自己不懂的东西，大模型"一本正经地胡说八道"

## 解决方案

这个问题如何解决呢？也不难。

**方案思路**

你可以让大模型先在本地知识库中进行搜索，检查一下提示中的信息的真实性：

- 如果真实 → 进行输出

- 如果不真实 → 进行修正

- 如果本地知识库找不到相应的信息 → 调用工具进行外部搜索

[![](https://static001.geekbang.org/resource/image/70/1b/7032d003ac36e858cbb53f90bb4f3a1b.jpg?wh=3000x1202)](https://static001.geekbang.org/resource/image/70/1b/7032d003ac36e858cbb53f90bb4f3a1b.jpg?wh=3000x1202)

解决方案示意图

> [!important]
>
> **外部工具**
>
> 无论本地知识库还是搜索引擎，都不是封装在大模型内部的知识，我们把它们称为**"外部工具"**。

---

# 代理的作用

每当你遇到这种需要模型做自主判断、自行调用工具、自行决定下一步行动的时候，**Agent（代理）**就出场了。

[![](https://static001.geekbang.org/resource/image/e2/de/e26993dd3957bfd2947424abb9de7cde.png?wh=1965x1363)](https://static001.geekbang.org/resource/image/e2/de/e26993dd3957bfd2947424abb9de7cde.png?wh=1965x1363)

代理在 LangChain 架构中的位置

> [!important]
>
> **代理的核心能力**
>
> 代理就像一个多功能的接口，它能够接触并使用一套工具。根据用户的输入，代理会决定调用哪些工具。它不仅可以：
>
> - 同时使用多种工具
>
> - 将一个工具的输出数据作为另一个工具的输入数据

## LangChain 中的代理三要素

在 LangChain 中使用代理，我们只需要理解下面三个元素：

|**要素**|**职责**|
|---|---|
|大模型|提供逻辑的引擎，负责生成预测和处理输入|
|外部工具|可能包括数据清洗工具、搜索引擎、应用程序等|
|代理|调用适当的外部工具，并管理整个交互过程的流程|

[![](https://static001.geekbang.org/resource/image/9a/31/9a9550e7df156d15975dc027b3201d31.png?wh=1100x606)](https://static001.geekbang.org/resource/image/9a/31/9a9550e7df156d15975dc027b3201d31.png?wh=1100x606)

代理接收任务后，会自动调用工具，给出答案

## 代理的自主判断能力

上面的思路看似简单，其实很值得我们仔细琢磨。

这个过程有很多地方需要大模型**自主判断下一步行为（也就是操作）**要做什么，如果不加引导，那大模型本身是不具备这个能力的。比如下面这一系列的操作：

- 什么时候开始在本地知识库中搜索（这个比较简单，毕竟是第一个步骤，可以预设）？

- 怎么确定本地知识库的检索已经完成，可以开始下一步？

- 调用哪一种外部搜索工具（比如 Google 引擎）？

- 如何确定外部搜索工具返回了想要找的内容？

- 如何确定信息真实性的检索已经全部完成，可以开始下一步？

> [!important]
>
> **核心问题**
>
> LangChain 中的代理是怎样自主计划、自行判断，并执行行动的呢？

---

# ReAct 框架

## 从现实中获得启发

让我们思考一下：如果你接到一个新任务，你将如何做出决策并完成下一步的行动？

**场景示例：鲜花定价**

你在运营花店的过程中，经常会经历天气变化而导致的鲜花售价变化，那么，每天早上你会如何为你的鲜花定价？

也许你会告诉我：

1. **行动** - 我会去 Google 上面查一查今天的鲜花成本价（也就是我预计的进货价格）

1. **观察** - 然后我会根据这个价格的高低

1. **思考** - 来确定我要加价多少

1. **行动** - 最后计算出一个售价

[![](https://static001.geekbang.org/resource/image/58/12/58bdbe17948a0ed2d52ceb3557194a12.png?wh=2176x706)](https://static001.geekbang.org/resource/image/58/12/58bdbe17948a0ed2d52ceb3557194a12.png?wh=2176x706)

定价过程

> [!important]
>
> **推理与行动的协同**
>
> 在这个简单的例子中，你有**观察**、有**思考**，然后才会具体**行动**。这里的观察和思考，我们统称为**推理（Reasoning）**过程，推理指导着你的**行动（Acting）**。

## ReAct 框架的理论基础

我们今天要讲的 **ReAct 框架**的灵感正是来自"行动"和"推理"之间的协同作用，这种协同作用使得人类能够学习新任务并做出决策或推理。

> [!important]
>
> **学术来源**
>
> 此 ReAct 并非指代流行的前端开发框架 React，它在这里专指如何指导大语言模型推理和行动的一种思维框架。
>
> 这个思维框架是 Shunyu Yao 等人在 ICLR 2023 会议论文《ReAct: Synergizing Reasoning and Acting in Language Models》（ReAct：在语言模型中协同推理和行动）中提出的。

## 核心思想

这篇文章的一个关键启发在于：**大语言模型可以通过生成推理痕迹和任务特定行动来实现更大的协同作用。**

具体来说，就是引导模型生成一个任务解决轨迹：

**观察环境 → 进行思考 → 采取行动**

进一步简化，就变成了：

**推理（Reasoning） → 行动（Acting）**

### Reasoning：推理阶段

- 包括了对当前环境和状态的观察

- 生成推理轨迹

- 使模型能够诱导、跟踪和更新操作计划

- 甚至处理异常情况

### Acting：行动阶段

- 指导大模型采取下一步的行动

- 与外部源（如知识库或环境）进行交互并收集信息

- 或者给出最终答案

> [!important]
>
> **ReAct 的优势**
>
> - 每一个推理过程都会被详细记录在案
>
> - 改善大模型解决问题时的**可解释性**和**可信度**
>
> - 在各种语言和决策任务中都得到了很好的效果

## 实例演示：找到胡椒瓶

让我们用一个具体的示例来说明这一点。

**任务**：在一个虚拟环境中找到一个胡椒瓶并将其放在一个抽屉里。

**没有推理能力的模型**

- 不能够在房间的各个角落中进行寻找

- 或者在找到胡椒瓶之后不能够判断下一步的行动

- 因而无法完成任务

**使用 ReAct**

- 一系列子目标将被具体地捕获在每一个思考过程中

[![](https://static001.geekbang.org/resource/image/63/96/638e1b0098211b1b622283e0f7100596.png?wh=876x689)](https://static001.geekbang.org/resource/image/63/96/638e1b0098211b1b622283e0f7100596.png?wh=876x689)

通过 ReAct 思维框架，大模型成功找到胡椒瓶

## ReAct vs CoT vs Action Only

现在，让我们回到开始的时候我们所面临的问题。

**仅使用 CoT（思维链）**

- LLMs 能够执行推理轨迹

- 可以完成算术和常识推理等问题

- 但因为缺乏和外部世界的接触或无法更新自己的知识

- 会导致幻觉的出现

[![](https://static001.geekbang.org/resource/image/11/c8/1189768e0ae5b6199fd6db301d2401c8.png?wh=3108x867)](https://static001.geekbang.org/resource/image/11/c8/1189768e0ae5b6199fd6db301d2401c8.png?wh=3108x867)

从仅使用 CoT，仅执行 Action，到 ReAct

> [!important]
>
> **ReAct = CoT + External Tools**
>
> 将 ReAct 框架和思维链（CoT）结合使用，能够让大模型在推理过程同时使用：
>
> - **内部知识**
>
> - **获取到的外部信息**
>
> 从而给出更可靠和实际的回应，也提高了 LLMs 的可解释性和可信度。

## LangChain 中的实现

LangChain 正是通过 **Agent 类**，将 ReAct 框架进行了完美封装和实现，这一下子就赋予了大模型极大的**自主性（Autonomy）**。

你的大模型现在从一个仅仅可以通过自己内部知识进行对话聊天的 Bot，**飞升**为了一个有手有脚能使用工具的**智能代理**。

---

# 通过代理实现 ReAct 框架

下面，就让我们用 LangChain 中最为常用的 **ZERO_SHOT_REACT_DESCRIPTION** 这种代理类型，来剖析一下 LLM 是如何在 ReAct 框架的指导之下进行推理的。

## 任务设定

我们要给代理一个任务：

**找到玫瑰的当前市场价格，然后计算出加价 15% 后的新价格。**

## 准备工作

在开始之前，有一个准备工作，就是你需要在 serpapi.com 注册一个账号，并且拿到你的 SERPAPI_API_KEY，这个就是我们要为大模型提供的 Google 搜索工具。

[![](https://static001.geekbang.org/resource/image/18/5b/1841f5d709cd27f1000ee9a5b593325b.png?wh=1877x1053)](https://static001.geekbang.org/resource/image/18/5b/1841f5d709cd27f1000ee9a5b593325b.png?wh=1877x1053)

SerpAPI 注册页面

## 实现步骤

### 第一步：安装 SerpAPI 包

```bash
pip install google-search-results
```

---

### 第二步：设置 API 密钥

```python
import os
os.environ["OPENAI_API_KEY"] = 'Your OpenAI API Key'
os.environ["SERPAPI_API_KEY"] = 'Your SerpAPI API Key'
```

---

### 第三步：导入所需的库

```python
from langchain.agents import load_tools
from langchain.agents import initialize_agent
from langchain.agents import AgentType
from langchain.llms import OpenAI
```

---

### 第四步：加载语言模型

```python
llm = OpenAI(temperature=0)
```

---

### 第五步：加载工具

```python
tools = load_tools(["serpapi", "llm-math"], llm=llm)
```

> [!important]
>
> **工具说明**
>
> - **serpapi** - 调用 Google 搜索引擎的工具
>
> - **llm-math** - 通过 LLM 进行数学计算的工具

---

### 第六步：初始化代理

```python
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)
```

---

### 第七步：运行代理

```python
agent.run("目前市场上玫瑰花的平均价格是多少？如果我在此基础上加价15%卖出，应该如何定价？")
```

## 执行结果

大模型成功遵循了 ReAct 框架，它输出的思考与行动轨迹如下：

```jsx
> Entering new chain...

I need to find the current market price of roses and then calculate the new price with a 15% markup.

Action: Search
Action Input: "Average price of roses"

Observation: According to the study, the average price for a dozen roses in the United States is $80.16. The Empire State hovers closer to that number than its neighbors, with a bouquet setting back your average New Yorker $78.33.

Thought: I need to calculate the new price with a 15% markup.

Action: Calculator
Action Input: 80.16 * 1.15

Observation: Answer: 92.18399999999998

Thought: I now know the final answer.

Final Answer: The new price with a 15% markup would be $92.18.

> Finished chain.
```

[![](https://static001.geekbang.org/resource/image/c9/14/c99893b6d8311d9ac95aeb8d818e1914.png?wh=1037x549)](https://static001.geekbang.org/resource/image/c9/14/c99893b6d8311d9ac95aeb8d818e1914.png?wh=1037x549)

代理执行过程

> [!important]
>
> **执行成功**
>
> 可以看到，ZERO_SHOT_REACT_DESCRIPTION 类型的智能代理在 LangChain 中，自动形成了一个完善的思考与行动链条，而且给出了正确的答案。

## 执行轨迹分析

你可以对照下面这个表格，再巩固一下这个链条中的每一个环节：

|**阶段**|**内容**|**说明**|
|---|---|---|
|Thought 1|I need to find the current market price of roses and then calculate the new price with a 15% markup.|理解任务，明确需要两步操作|
|Action 1|Search|选择搜索工具|
|Action Input 1|"Average price of roses"|构造搜索查询|
|Observation 1|According to the study, the average price for a dozen roses in the United States is $80.16...|获得搜索结果|
|Thought 2|I need to calculate the new price with a 15% markup.|基于搜索结果，规划下一步|
|Action 2|Calculator|选择计算工具|
|Action Input 2|80.16 * 1.15|构造计算表达式|
|Observation 2|Answer: 92.18399999999998|获得计算结果|
|Thought 3|I now know the final answer.|确认任务完成|
|Final Answer|The new price with a 15% markup would be $92.18.|给出最终答案|

> [!important]
>
> **ReAct 轨迹特点**
>
> 这个思维链条中，智能代理有：
>
> - **思考** - 规划和判断
>
> - **观察** - 获取外部信息
>
> - **行动** - 调用工具执行
>
> 成功通过搜索和计算两个操作，完成了任务。

---

# 总结

## 核心概念回顾

这节课我们介绍了什么是 LangChain 中的代理，更重要的是，我们介绍了代理自主行动的驱动力—— **ReAct 框架**。

> [!important]
>
> **ReAct 框架核心**
>
> 通过 ReAct 框架，大模型将被引导生成一个任务解决轨迹：
>
> **观察环境 → 进行思考 → 采取行动**
>
> - 观察和思考阶段被统称为**推理（Reasoning）**
>
> - 实施下一步行动的阶段被称为**行动（Acting）**
>
> - 在每一步推理过程中，都会详细记录下来，这也改善了大模型解决问题时的可解释性和可信度

## 推理阶段（Reasoning）

- 模型对当前环境和状态进行观察

- 生成推理轨迹

- 使模型能够诱导、跟踪和更新操作计划

- 甚至处理异常情况

## 行动阶段（Acting）

- 模型会采取下一步的行动

- 与外部源（如知识库或环境）进行交互并收集信息

- 或给出最终答案

## 未来发展

> [!important]
>
> **ReAct 框架的潜力**
>
> ReAct 框架的这些优点，使得它在未来的发展中具有巨大的潜力。随着技术的进步，我们可以期待：
>
> - **处理更多、更复杂的任务**
>
> - **具身智能的发展** - 智能代理在虚拟或实际环境中进行更复杂的交互
>
> - **虚拟环境导航** - 在虚拟环境中进行导航
>
> - **物理对象操作** - 在实际环境中操作物理对象
>
> 这将大大扩展 AI 的应用范围，使得它们能够更好地服务于我们的生活和工作。

---

# 思考题

> [!important]
>
> **问题 1**
>
> 在 ReAct 框架中，推理和行动各自代表什么？其相互之间的关系如何？

> [!important]
>
> **问题 2**
>
> 为什么说 ReAct 框架能改善大模型解决问题时的可解释性和可信度？

> [!important]
>
> **问题 3**
>
> 你能否说一说 LangChain 中的代理和链的核心差异？

期待在留言区看到你的思考，如果你觉得内容对你有帮助，也欢迎分享给有需要的朋友！

---

# 延伸阅读

- **论文**: ReAct：在语言模型中协同推理和行动 - Yao, S., Zhao, J., Yu, D., Du, N., Shafran, I., Narasimhan, K., & Cao, Y. (2023). ReAct: Synergizing Reasoning and Acting in Language Models. arXiv preprint arXiv:2210.03629

- **论文**: ART：大型语言模型的自动多步推理和工具使用 - Paranjape, B., Lundberg, S., Singh, S., Hajishirzi, H., Zettlemoyer, L., & Ribeiro, M. T. (2023). ART: Automatic multi-step reasoning and tool-use for large language models. arXiv preprint arXiv:2303.09014.

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

课程总结
