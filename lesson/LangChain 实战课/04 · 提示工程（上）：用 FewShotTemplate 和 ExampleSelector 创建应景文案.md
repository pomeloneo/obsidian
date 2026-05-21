原文链接：[极客时间](https://time.geekbang.org/column/article/700699)

---

[![](https://static001.geekbang.org/resource/image/26/y5/266ed4afyyb1c1d9fe4d6378557b2yy5.jpg)](https://static001.geekbang.org/resource/image/26/y5/266ed4afyyb1c1d9fe4d6378557b2yy5.jpg)

你好，我是黄佳，欢迎来到 LangChain 实战课！

上节课我给你留了一个思考题：在提示模板的构建过程中加入了 `partial_variables`，也就是输出解析器指定的 `format_instructions` 之后，为什么能够让模型生成结构化的输出？

当你用 `print` 语句打印出最终传递给大模型的提示时，一切就变得非常明了。

```
您是一位专业的鲜花店文案撰写员。
对于售价为 50 元的 玫瑰 ，您能提供一个吸引人的简短描述吗？
The output should be a markdown code snippet formatted in the following schema,
including the leading and trailing "```json" and "```":

{
  "description": string
  "reason": string
}
```

> [!important]
>
> **核心原理**：LangChain 的输出解析器在提示中自动添加了 `{format_instructions}` 的内容，清楚地指示模型需要根据 schema 来格式化输出文本。

这就是在告诉模型：你就 follow 这个 schema（对数据结构的描述）的格式就行！

这就是一个很棒、很典型的**提示工程**。有了这样清晰的提示，智能程度比较高的模型（比如 GPT3.5 及以上版本），肯定能够输出可以被解析的数据结构，如 JSON 格式的数据。

那么这节课我就带着你进一步深究，如何利用 LangChain 中的提示模板，做好提示工程。

---

## 提示工程：模型 I/O 的输入部分

[![](https://static001.geekbang.org/resource/image/3b/fe/3b5584552720f22ac10e1ab1430f61fe.jpg?wh=4000x1536)](https://static001.geekbang.org/resource/image/3b/fe/3b5584552720f22ac10e1ab1430f61fe.jpg?wh=4000x1536)

上节课我说过，针对大模型的提示工程该如何做，吴恩达老师在他的 _ChatGPT Prompt Engineering for Developers_ 公开课中，给出了两个大的原则：

1. **写出清晰而具体的指示**

1. **给模型思考的时间**

在 OpenAI 的官方文档 _GPT 最佳实践_ 中，也给出了和上面这两大原则一脉相承的 **6 大策略**：

1. 写清晰的指示

1. 给模型提供参考（也就是示例）

1. 将复杂任务拆分成子任务

1. 给 GPT 时间思考

1. 使用外部工具

1. 反复迭代问题

这些原则不仅能够指导大语言模型，也完全能够指导你的思维过程。大模型的思维过程和我们人类的思维过程，还是蛮相通的。

---

## 提示的结构

从大原则到实践，还是有一些具体工作需要说明，下面我们先看一个实用的提示框架。

[![](https://static001.geekbang.org/resource/image/b7/16/b77a15cd83b66bba55032d711bcf3c16.png?wh=1920x801)](https://static001.geekbang.org/resource/image/b7/16/b77a15cd83b66bba55032d711bcf3c16.png?wh=1920x801)

在这个提示框架中：

### 指令（Instruction）

告诉模型这个任务大概要做什么、怎么做，比如如何使用提供的外部信息、如何处理查询以及如何构造输出。这通常是一个提示模板中比较固定的部分。

> 一个常见用例是告诉模型"你是一个有用的 XX 助手"，这会让他更认真地对待自己的角色。

### 上下文（Context）

充当模型的额外知识来源。这些信息可以：

- 手动插入到提示中

- 通过矢量数据库检索得来

- 通过其他方式（如调用 API、计算器等工具）拉入

> 一个常见用例是把从向量数据库查询到的知识作为上下文传递给模型。

### 提示输入（Prompt Input）

通常就是具体的问题或者需要大模型做的具体事情。这个部分和"指令"部分可以合二为一，但拆分出来成为独立组件，便于复用模板。

> 这通常是作为变量，在调用模型之前传递给提示模板，以形成具体的提示。

### 输出指示器（Output Indicator）

标记要生成的文本的开始。这就像小时候的数学考卷，先写一个"解"，就代表你要开始答题了。

> 如果生成 Python 代码，可以使用 `import` 向模型表明它必须开始编写 Python 代码。LangChain 中的代理在构建提示模板时，经常性的会用一个 `Thought:` 作为引导词，指示模型开始输出自己的推理。

---

## LangChain 提示模板的类型

LangChain 中提供 **String**（`StringPromptTemplate`）和 **Chat**（`BaseChatPromptTemplate`）两种基本类型的模板，并基于它们构建了不同类型的提示模板：

[![](https://static001.geekbang.org/resource/image/fe/yy/feefbb0a166f53f14f647b88e1025cyy.jpg?wh=2240x812)](https://static001.geekbang.org/resource/image/fe/yy/feefbb0a166f53f14f647b88e1025cyy.jpg?wh=2240x812)

这些模板的导入方式如下：

```python
from langchain.prompts.prompt import PromptTemplate
from langchain.prompts import FewShotPromptTemplate
from langchain.prompts.pipeline import PipelinePromptTemplate
from langchain.prompts import ChatPromptTemplate
from langchain.prompts import (
    ChatMessagePromptTemplate,
    SystemMessagePromptTemplate,
    AIMessagePromptTemplate,
    HumanMessagePromptTemplate,
)
```

> [!important]
>
> 有时候不指定 `.prompts`，直接从 LangChain 包也能导入模板：`from langchain import PromptTemplate`

---

## 使用 PromptTemplate

下面通过示例简单说明一下 `PromptTemplate` 的使用：

```python
from langchain import PromptTemplate

template = """\
你是业务咨询顾问。
你给一个销售{product}的电商公司，起一个好的名字？
"""
prompt = PromptTemplate.from_template(template)
print(prompt.format(product="鲜花"))
```

**输出：**

```
你是业务咨询顾问。
你给一个销售鲜花的电商公司，起一个好的名字？
```

这个程序的主要功能是生成适用于不同场景的提示，对用户定义的一种产品或服务提供公司命名建议。

- `{product}` 是占位符

- 通过 `PromptTemplate` 的 `from_template` 方法创建提示模板对象

- 通过 `prompt.format` 方法将模板中的 `{product}` 替换为具体值

> [!important]
>
> **便捷之处**：`from_template` 方法可以从传入的字符串中自动提取变量名称（如 `product`），而无需刻意指定。

也可以通过提示模板类的构造函数，在创建模板时手工指定 `input_variables`：

```python
prompt = PromptTemplate(
    input_variables=["product", "market"],
    template="你是业务咨询顾问。对于一个面向{market}市场的，专注于销售{product}的公司，你会推荐哪个名字？"
)
print(prompt.format(product="鲜花", market="高端"))
```

**输出：**

```
你是业务咨询顾问。对于一个面向高端市场的，专注于销售鲜花的公司，你会推荐哪个名字？
```

---

## 使用 ChatPromptTemplate

对于 OpenAI 推出的 ChatGPT 这一类的聊天模型，LangChain 也提供了一系列的模板，这些模板的不同之处是它们有对应的**角色**。

下面代码展示了 OpenAI 的 Chat Model 中的各种消息角色：

```python
import openai

openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Who won the world series in 2020?"},
        {"role": "assistant", "content": "The Los Angeles Dodgers won the World Series in 2020."},
        {"role": "user", "content": "Where was it played?"}
    ]
)
```

### OpenAI 消息格式说明

> [!important]
>
> 消息必须是消息对象的数组，其中每个对象都有一个角色和内容。对话可以短至一条消息，也可以来回多次。

LangChain 的 `ChatPromptTemplate` 这一系列的模板，就是跟着这一系列角色而设计的。

### 示例代码

```python
from langchain.prompts import (
    ChatPromptTemplate,
    SystemMessagePromptTemplate,
    HumanMessagePromptTemplate,
)

template = "你是一位专业顾问，负责为专注于{product}的公司起名。"
system_message_prompt = SystemMessagePromptTemplate.from_template(template)

human_template = "公司主打产品是{product_detail}。"
human_message_prompt = HumanMessagePromptTemplate.from_template(human_template)

prompt_template = ChatPromptTemplate.from_messages([system_message_prompt, human_message_prompt])
prompt = prompt_template.format_prompt(product="鲜花装饰", product_detail="创新的鲜花设计。").to_messages()

import os
os.environ["OPENAI_API_KEY"] = '你的OpenAI Key'

from langchain.chat_models import ChatOpenAI
chat = ChatOpenAI()
result = chat(prompt)
print(result)
```

**输出：**

```
content='1. 花语创意\n2. 花韵设计\n3. 花艺创新\n4. 花漾装饰\n5. 花语装点\n6. 花翩翩\n7. 花语之美\n8. 花馥馥\n9. 花语时尚\n10. 花之魅力'
additional_kwargs={}
example=False
```

---

## FewShot 的思想起源

讲解概念之前，我先分享个事儿帮助你理解。

> 今天我下楼跑步时，一个老爷爷教孙子学骑车，小孩总掌握不了平衡，蹬一两下就下车。

> 孙子说：“爷爷，什么是毅力？”

> 爷爷说："宝贝，你得有毅力！"

> 这老爷爷就是给孙子做了一个 One-Shot 学习。如果他的孙子第一次听说却上来就明白什么是毅力，那就神了，这就叫 Zero-Shot，表明这孩子的语言天赋不是一般的高，从知识积累和当前语境中就能够推知新词的涵义。有时候我们把 Zero-Shot 翻译为“顿悟”，聪明的大模型，某些情况下也是能够做到的。

> 孙子说："爷爷，什么是毅力？"

> 这几个重要概念并非在某一篇特定的论文中首次提出，而是在机器学习和深度学习的研究中逐渐形成和发展的。

> 爷爷说："你看这个叔叔，绕着楼跑了 10 多圈了，这就是毅力，你也得至少蹬个 10 几趟才能骑起来。"

这老爷爷就是给孙子做了一个 **One-Shot 学习**。

### 核心概念对比

### 学术背景

**Few-Shot Learning** 的重要参考文献是 2016 年 Vinyals, O. 的论文《小样本学习的匹配网络》，提出了**匹配网络（Matching Networks）**，专门针对 One-Shot Learning 问题设计。

**Zero-Shot Learning** 的代表性参考文献是 Palatucci, M. 在 2009 年提出的《基于语义输出编码的零样本学习》，学习系统可以根据类的语义描述来识别之前未见过的类。

> [!important]
>
> **重要论文**：OpenAI 在介绍 GPT-3 模型的论文《Language models are Few-Shot learners》中指出：GPT-3 通过提升模型规模，实现了出色的 Few-Shot 学习性能。

[![](https://static001.geekbang.org/resource/image/48/bc/481yy45346cc28ec48269c752c3647bc.png?wh=659x786)](https://static001.geekbang.org/resource/image/48/bc/481yy45346cc28ec48269c752c3647bc.png?wh=659x786)

下图是 OpenAI 的 GPT-3 论文给出的 GPT-3 在翻译任务中，通过 FewShot 提示完成翻译的例子：

[![](https://static001.geekbang.org/resource/image/35/ca/357e9ca0ce2b4699a24e3fe512c047ca.png?wh=1632x1465)](https://static001.geekbang.org/resource/image/35/ca/357e9ca0ce2b4699a24e3fe512c047ca.png?wh=1632x1465)

---

## 使用 FewShotPromptTemplate

下面，让我们通过 LangChain 中的 `FewShotPromptTemplate` 构建出最合适的鲜花文案。

### 步骤 1：创建示例样本

首先，创建一些示例作为提示的样本。每个示例都是一个字典，键是输入变量，值是这些输入变量的值。

```python
samples = [
    {
        "flower_type": "玫瑰",
        "occasion": "爱情",
        "ad_copy": "玫瑰，浪漫的象征，是你向心爱的人表达爱意的最佳选择。"
    },
    {
        "flower_type": "康乃馨",
        "occasion": "母亲节",
        "ad_copy": "康乃馨代表着母爱的纯洁与伟大，是母亲节赠送给母亲的完美礼物。"
    },
    {
        "flower_type": "百合",
        "occasion": "庆祝",
        "ad_copy": "百合象征着纯洁与高雅，是你庆祝特殊时刻的理想选择。"
    },
    {
        "flower_type": "向日葵",
        "occasion": "鼓励",
        "ad_copy": "向日葵象征着坚韧和乐观，是你鼓励亲朋好友的最好方式。"
    }
]
```

`samples` 列表包含四个字典，每个字典代表了一种花的类型、适合的场合，以及对应的广告文案——这些就是构建 FewShotPrompt 时传递给模型的参考信息。

### 步骤 2：创建提示模板

配置一个提示模板，将一个示例格式化为字符串：

```python
from langchain.prompts.prompt import PromptTemplate

template = "鲜花类型: {flower_type}\n场合: {occasion}\n文案: {ad_copy}"
prompt_sample = PromptTemplate(
    input_variables=["flower_type", "occasion", "ad_copy"],
    template=template
)
print(prompt_sample.format(**samples[0]))
```

**输出：**

```
鲜花类型: 玫瑰
场合: 爱情
文案: 玫瑰，浪漫的象征，是你向心爱的人表达爱意的最佳选择。
```

### 步骤 3：创建 FewShotPromptTemplate 对象

使用 `prompt_sample` 和 `samples` 列表中的所有示例，创建 `FewShotPromptTemplate` 对象：

```python
from langchain.prompts.few_shot import FewShotPromptTemplate

prompt = FewShotPromptTemplate(
    examples=samples,
    example_prompt=prompt_sample,
    suffix="鲜花类型: {flower_type}\n场合: {occasion}",
    input_variables=["flower_type", "occasion"]
)
print(prompt.format(flower_type="野玫瑰", occasion="爱情"))
```

**输出：**

```
鲜花类型: 玫瑰
场合: 爱情
文案: 玫瑰，浪漫的象征，是你向心爱的人表达爱意的最佳选择。

鲜花类型: 康乃馨
场合: 母亲节
文案: 康乃馨代表着母爱的纯洁与伟大，是母亲节赠送给母亲的完美礼物。

鲜花类型: 百合
场合: 庆祝
文案: 百合象征着纯洁与高雅，是你庆祝特殊时刻的理想选择。

鲜花类型: 向日葵
场合: 鼓励
文案: 向日葵象征着坚韧和乐观，是你鼓励亲朋好友的最好方式。

鲜花类型: 野玫瑰
场合: 爱情
```

`FewShotPromptTemplate` 是一个更复杂的提示模板，它包含了多个示例和一个提示，可以使用多个示例来指导模型生成对应的输出。

### 步骤 4：调用大模型创建新文案

把这个对象输出给大模型，就可以根据提示得到所需要的文案：

```python
import os
os.environ["OPENAI_API_KEY"] = '你的Open AI Key'

from langchain.llms import OpenAI
model = OpenAI(model_name='gpt-3.5-turbo-instruct')
result = model(prompt.format(flower_type="野玫瑰", occasion="爱情"))
print(result)
```

**输出：**

```
文案: 野玫瑰代表着爱情的坚贞，是你向心爱的人表达爱意的最佳礼物。
```

> [!important]
>
> 模型成功地模仿了我们的示例，写出了新文案，从结构到语气都蛮相似的！

---

## 使用示例选择器

如果示例很多，一次性把所有示例发送给模型是不现实而且低效的。另外，每次都包含太多的 Token 也会浪费流量（OpenAI 是按照 Token 数来收取费用）。

LangChain 提供了**示例选择器**，来选择最合适的样本。

> [!important]
>
> 因为示例选择器使用向量相似度比较的功能，需要安装向量数据库（这里使用开源的 Chroma，也可以选择 Qdrant）。

### 示例代码

```python
from langchain.prompts.example_selector import SemanticSimilarityExampleSelector
from langchain.vectorstores import Chroma
from langchain.embeddings import OpenAIEmbeddings

# 创建示例选择器
example_selector = SemanticSimilarityExampleSelector.from_examples(
    samples,
    OpenAIEmbeddings(),
    Chroma,
    k=1
)

# 使用选择器创建 FewShotPromptTemplate
prompt = FewShotPromptTemplate(
    example_selector=example_selector,
    example_prompt=prompt_sample,
    suffix="鲜花类型: {flower_type}\n场合: {occasion}",
    input_variables=["flower_type", "occasion"]
)

print(prompt.format(flower_type="红玫瑰", occasion="爱情"))
```

**输出：**

```
鲜花类型: 玫瑰
场合: 爱情
文案: 玫瑰，浪漫的象征，是你向心爱的人表达爱意的最佳选择。

鲜花类型: 红玫瑰
场合: 爱情
```

`SemanticSimilarityExampleSelector` 对象可以根据**语义相似性**（余弦相似度）选择最相关的示例。因为我们的提示中需要创建的是"红玫瑰"的文案，选择器自动找到了最相似的示例"玫瑰"，并用这个示例构建了 FewShot 模板。

> [!important]
>
> 这样就避免了把过多的无关模板传递给大模型，以节省 Token 的用量。

---

## 总结

本节课我们介绍了：

- **提示工程的原理** - 清晰指示 + 给模型思考时间

- **几种提示模板的用法** - PromptTemplate、ChatPromptTemplate

- **最重要的 FewShot 思路** - 给模型一些示例做参考，模型才能明白你要什么

[![](https://static001.geekbang.org/resource/image/f4/0d/f46817a7ed56c6fef64a6aeee4c1yy0d.png?wh=955x970)](https://static001.geekbang.org/resource/image/f4/0d/f46817a7ed56c6fef64a6aeee4c1yy0d.png?wh=955x970)

> [!important]
>
> **关键点**：提供示例对于解决某些任务至关重要，通常情况下，FewShot 的方式能够显著提高模型回答的质量。不过，当少样本提示的效果不佳时，可能表示模型在任务上的学习不足，建议对模型进行微调或尝试更高级的提示技术。

下一节课，我们将在探讨输出解析的同时，讲解另一种备受关注的提示技术——**思维链提示**（Chain of Thought，简称 CoT）。

---

## 思考题

1. **探索 PromptTemplate 参数**

    如果你观察 LangChain 中 `[prompt.py](http://prompt.py)` 的 `PromptTemplate` 实现代码，你会发现除了 `input_variables`、`template` 等参数之外，还有 `template_format`、`validate_template` 等参数。

    ```python

```text
template_format: str = "f-string"
"""The format of the prompt template. Options are: 'f-string', 'jinja2'."""
validate_template: bool = True
"""Whether or not to try validating the template."""
```
```

    请查看 LangChain 文档，并尝试使用这些参数（如 jinja2 格式模板）。

1. **尝试 PipelinePromptTemplate**

    请尝试使用 `PipelinePromptTemplate` 和自定义 Template。

1. **构建客户服务对话的少样本学习任务**

    构想一个关于鲜花店运营场景中客户服务对话的少样本学习任务。模型需要根据提供的示例，学习如何解答客户的各种问题，包括询问花的价格、推荐鲜花、了解鲜花的保养方法等。最好用 ChatModel 完成：

    ```python

```python
from langchain.chat_models import ChatOpenAI
from langchain import PromptTemplate
from langchain.prompts.chat import (
ChatPromptTemplate,
SystemMessagePromptTemplate,
AIMessagePromptTemplate,
HumanMessagePromptTemplate
)
```
---
```

## 延伸阅读

---

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)
