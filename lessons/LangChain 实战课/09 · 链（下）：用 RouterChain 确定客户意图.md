> **课程来源**: [极客时间 - LangChain 实战课](https://time.geekbang.org/column/article/703556)

[![](https://static001.geekbang.org/resource/image/2c/81/2c82292094108ec475aa241aafaec281.jpg)](https://static001.geekbang.org/resource/image/2c/81/2c82292094108ec475aa241aafaec281.jpg)

课程封面

---

# 任务设定

假设鲜花运营智能客服 ChatBot 通常会接到两大类问题：

**鲜花养护类问题**

- 如何保持花的健康

- 如何浇水、施肥等养护技巧

**鲜花装饰类问题**

- 如何搭配花束

- 如何装饰场地等

> [!important]
> 
> **业务需求**
> 
> - 接到第一类问题 → 引导到 ChatBot A（园丁专家）
> 
> - 接到第二类问题 → 引导到 ChatBot B（插花大师）

[![](https://static001.geekbang.org/resource/image/d8/59/d8491e696c03f49a331c94e31d20e559.jpg?wh=1490x1077)](https://static001.geekbang.org/resource/image/d8/59/d8491e696c03f49a331c94e31d20e559.jpg?wh=1490x1077)

RouterChain 工作流程示意图

> [!important]
> 
> **解决方案**
> 
> 根据这两个场景构建不同的目标链，遇到不同类型的问题，LangChain 会通过 **RouterChain** 自动引导大语言模型选择不同的模板。

---

# 整体框架

## 什么是 RouterChain？

**RouterChain（路由链）** 是一种能够动态选择用于给定输入的下一个链的机制。

## 工作流程

1. **分析问题** - 根据用户的问题内容，使用路由器链确定问题更适合哪个处理模板

1. **路由转发** - 将问题发送到该处理模板进行回答

1. **默认处理** - 如果问题不适合任何已定义的处理模板，发送到默认链

## 核心组件

本示例使用 **LLMRouterChain** 和 **MultiPromptChain** 组合实现路由功能：

|**组件**|**职责**|
|---|---|
|MultiPromptChain|调用 LLMRouterChain 选择与给定问题最相关的提示|
|LLMRouterChain|负责决策，选择最适合的目标链|

## 实现步骤概览

1. **构建处理模板** - 为鲜花护理和鲜花装饰定义字符串模板

1. **提示信息** - 组织和存储模板的关键信息（键、描述、内容）

1. **初始化语言模型** - 导入并实例化 LLM

1. **构建目标链** - 根据提示信息构建 LLMChain，存储在字典中

1. **构建 LLM 路由链** - 根据提示信息构建路由模板和 LLMRouterChain

1. **构建默认链** - 输入不适合任何模板时触发的备用链

1. **构建多提示链** - 使用 MultiPromptChain 整合所有链

---

# 具体实现

## 第一步：构建提示信息的模板

针对两种场景，构建提示信息模板：

```python
# 场景 1：鲜花养护
flower_care_template = """你是一个经验丰富的园丁，擅长解答关于养花育花的问题。
下面是需要你来回答的问题:
{input}"""

# 场景 2：鲜花装饰
flower_deco_template = """你是一位网红插花大师，擅长解答关于鲜花装饰的问题。
下面是需要你来回答的问题:
{input}"""

# 组织提示信息
prompt_infos = [
    {
        "key": "flower_care",
        "description": "适合回答关于鲜花护理的问题",
        "template": flower_care_template,
    },
    {
        "key": "flower_decoration",
        "description": "适合回答关于鲜花装饰的问题",
        "template": flower_deco_template,
    }
]
```

> [!important]
> 
> 每个提示信息包含三个字段：
> 
> - **key** - 唯一标识符
> 
> - **description** - 用途描述，帮助路由链做决策
> 
> - **template** - 实际的提示模板

---

## 第二步：初始化语言模型

```python
from langchain.llms import OpenAI
import os

os.environ["OPENAI_API_KEY"] = '你的OpenAI Key'
llm = OpenAI()
```

---

## 第三步：构建目标链

循环 `prompt_infos` 列表，构建两个目标链，分别处理不同的问题：

```python
from langchain.chains.llm import LLMChain
from langchain.prompts import PromptTemplate

chain_map = {}

for info in prompt_infos:
    prompt = PromptTemplate(
        template=info['template'],
        input_variables=["input"]
    )
    print("目标提示:\n", prompt)
    
    chain = LLMChain(llm=llm, prompt=prompt, verbose=True)
    chain_map[info["key"]] = chain
```

**输出示例：**

```jsx
目标提示:
input_variables=['input']
output_parser=None 
partial_variables={}
template='你是一个经验丰富的园丁，擅长解答关于养花育花的问题。\n下面是需要你来回答的问题:\n{input}' 
template_format='f-string'
validate_template=True

目标提示:
input_variables=['input']
output_parser=None 
partial_variables={}
template='你是一位网红插花大师，擅长解答关于鲜花装饰的问题。\n下面是需要你来回答的问题:\n{input}' 
template_format='f-string'
validate_template=True
```

> [!important]
> 
> **工作原理**
> 
> 对于每个场景，我们创建一个 LLMChain。每个链会根据其场景模板生成对应的提示，然后将这个提示送入语言模型获取答案。

---

## 第四步：构建路由链

路由链负责查看用户输入的问题，确定问题的类型：

```python
from langchain.chains.router.llm_router import LLMRouterChain, RouterOutputParser
from langchain.chains.router.multi_prompt_prompt import MULTI_PROMPT_ROUTER_TEMPLATE as RounterTemplate

# 构建目标描述
destinations = [f"{p['key']}: {p['description']}" for p in prompt_infos]

# 构建路由模板
router_template = RounterTemplate.format(destinations="\n".join(destinations))
print("路由模板:\n", router_template)

# 构建路由提示
router_prompt = PromptTemplate(
    template=router_template,
    input_variables=["input"],
    output_parser=RouterOutputParser(),
)
print("路由提示:\n", router_prompt)

# 构建路由链
router_chain = LLMRouterChain.from_llm(llm, router_prompt, verbose=True)
```

**路由模板输出：**

```jsx
Given a raw text input to a language model select the model prompt best suited for the input. 
You will be given the names of the available prompts and a description of what the prompt is best suited for. 
You may also revise the original input if you think that revising it will ultimately lead to a better response from the language model.

<< FORMATTING >>
Return a markdown code snippet with a JSON object formatted to look like:
```

{

"destination": string \ name of the prompt to use or "DEFAULT"

"next_inputs": string \ a potentially modified version of the original input

}

```jsx

REMEMBER: "destination" MUST be one of the candidate prompt names specified below OR it can be "DEFAULT" if the input is not well suited for any of the candidate prompts.
REMEMBER: "next_inputs" can just be the original input if you don't think any modifications are needed.

<< CANDIDATE PROMPTS >>
flower_care: 适合回答关于鲜花护理的问题
flower_decoration: 适合回答关于鲜花装饰的问题

<< INPUT >>
{input}

<< OUTPUT >>
```

### 路由模板详解

#### 1. 引言部分

> [!important]
> 
> **Given a raw text input to a language model select the model prompt best suited for the input.**
> 
> 告诉模型需要根据输入选择最适合的模型提示。

> [!important]
> 
> **You will be given the names of the available prompts and a description of what the prompt is best suited for.**
> 
> 提醒模型将获得各种模型提示的名称和描述。

> [!important]
> 
> **You may also revise the original input if you think that revising it will ultimately lead to a better response from the language model.**
> 
> 可选步骤，允许模型修改原始输入以获得更好的响应。

#### 2. 格式说明（<< FORMATTING >>）

指导模型如何格式化输出，返回包含以下字段的 JSON 对象：

- **destination** - 选择的提示名称（或 "DEFAULT"）

- **next_inputs** - 可能被修订的原始输入

#### 3. 额外说明

- **REMEMBER 1**: `destination` 必须是下面列出的提示之一或 "DEFAULT"

- **REMEMBER 2**: 除非必要，`next_inputs` 可以保持原始输入不变

#### 4. 候选提示（<< CANDIDATE PROMPTS >>）

列出所有可用的目标链及其描述：

- `flower_care`: 适合回答关于鲜花护理的问题

- `flower_decoration`: 适合回答关于鲜花装饰的问题

#### 5. 输入/输出部分

提供格式化框架，接收 `{input}` 并输出结果。

> [!important]
> 
> **核心机制**
> 
> 路由模板引导大模型查看用户输入并确定问题类型，然后以 JSON 格式返回路由决策。这是整个路由链的核心所在。

---

## 第五步：构建默认链

如果路由链没有找到适合的链，使用默认链进行处理：

```python
from langchain.chains import ConversationChain

default_chain = ConversationChain(
    llm=llm,
    output_key="text",
    verbose=True
)
```

---

## 第六步：构建多提示链

使用 **MultiPromptChain** 整合所有链，实现路由功能：

```python
from langchain.chains.router import MultiPromptChain

chain = MultiPromptChain(
    router_chain=router_chain,
    destination_chains=chain_map,
    default_chain=default_chain,
    verbose=True
)
```

### MultiPromptChain 的三个关键元素

|**元素**|**类型**|**说明**|
|---|---|---|
|router_chain|RouterChain|决定目标链和其输入的链|
|destination_chains|Mapping[str, LLMChain]|名称到候选链的映射字典|
|default_chain|LLMChain|路由器无法映射时使用的备用链|

### 工作流程

1. **输入阶段** - 输入首先传递给 `router_chain`

1. **决策阶段** - `router_chain` 根据标准或逻辑决定应该使用哪个 `destination_chain`

1. **执行阶段** - 输入被路由到选定的 `destination_chain`，该链处理并返回结果

1. **兜底阶段** - 如果 `router_chain` 不能决定正确的链，输入传递给 `default_chain`

> [!important]
> 
> **优势**
> 
> MultiPromptChain 提供了在多个处理链之间动态路由输入的机制，以得到最相关或最优的输出。这种设计模式非常适合处理多场景、多专家的业务需求。

---

# 运行路由链

链路已经准备好，现在测试我们的路由链。

## 测试 A：鲜花养护问题

```python
print(chain.run("如何为玫瑰浇水？"))
```

[![](https://static001.geekbang.org/resource/image/89/a2/89d0bfac97b259b93240a10cf777d9a2.png?wh=1097x821)](https://static001.geekbang.org/resource/image/89/a2/89d0bfac97b259b93240a10cf777d9a2.png?wh=1097x821)

测试 A 输出结果

> [!important]
> 
> **路由结果**: 成功路由到 `flower_care` 目标链（园丁专家）

---

## 测试 B：鲜花装饰问题

```python
print(chain.run("如何为婚礼场地装饰花朵？"))
```

[![](https://static001.geekbang.org/resource/image/4f/ed/4f848ca6592476358a25bf91996aa0ed.png?wh=1095x834)](https://static001.geekbang.org/resource/image/4f/ed/4f848ca6592476358a25bf91996aa0ed.png?wh=1095x834)

测试 B 输出结果

> [!important]
> 
> **路由结果**: 成功路由到 `flower_decoration` 目标链（插花大师）

---

## 测试 C：无关问题

```python
print(chain.run("如何考入哈佛大学？"))
```

[![](https://static001.geekbang.org/resource/image/ac/12/acd4a69df2cef81b1f7bcf33f9b4bb12.png?wh=1093x806)](https://static001.geekbang.org/resource/image/ac/12/acd4a69df2cef81b1f7bcf33f9b4bb12.png?wh=1093x806)

测试 C 输出结果

> [!important]
> 
> **路由结果**: 路由到 `default_chain`（ConversationChain）

---

> [!important]
> 
> **测试结果分析**
> 
> 三个测试分别被路由到三个不同的链：
> 
> - 前两个问题被正确识别并路由到预设的"专家类型"目标链
> 
> - 第三个问题被模型识别为不属于鲜花运营业务场景，被路由到默认链处理
> 
> 这充分验证了 RouterChain 的智能路由能力。

---

# 总结

## 核心链类型

本示例使用了以下链：

|**链类型**|**继承关系**|**功能**|
|---|---|---|
|LLMRouterChain|继承自 RouterChain|负责路由决策|
|MultiPromptChain|继承自 MultiRouteChain|组织和整合其他链|

## 整体架构

通过 **MultiPromptChain** 把其他链组织起来，完成路由功能：

```python
chain = MultiPromptChain(
    router_chain=router_chain,          # 路由链
    destination_chains=chain_map,       # 目标链字典
    default_chain=default_chain,        # 默认链
    verbose=True
)
```

## 代码位置

在 LangChain 的 `chains -> router ->` `[base.py](http://base.py)` 文件中，可以看到 RouterChain 和 MultiRouteChain 的代码实现。

---

# 思考题

> [!important]
> 
> **问题 1**: 日志控制
> 
> 通过 `verbose=True` 选项，在输出时显示了链的开始和结束日志，从而得到其相互调用流程。请尝试把该选项设置为 `False`，看看输出结果有何不同。

> [!important]
> 
> **问题 2**: 链替换
> 
> 在这个例子中，我们使用了 `ConversationChain` 作为 `default_chain`，这个 Chain 是 `LLMChain` 的子类。你能否把这个 Chain 替换为 `LLMChain`？

---

# 延伸阅读

- **代码**: [RouterChain 和 MultiRouteChain 的实现细节](https://github.com/langchain-ai/langchain/blob/master/libs/langchain/langchain/chains/router/base.py)

- **代码**: [MultiPromptChain 的实现细节](https://github.com/langchain-ai/langchain/blob/master/libs/langchain/langchain/chains/router/multi_prompt.py)

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

课程总结