> **课程来源**: [极客时间 - LangChain 实战课](https://time.geekbang.org/column/article/702846)

[![](https://static001.geekbang.org/resource/image/51/5d/51f54ba51c8d6bf347yyb5a596312d5d.jpg)](https://static001.geekbang.org/resource/image/51/5d/51f54ba51c8d6bf347yyb5a596312d5d.jpg)

课程封面

---

## 课程概述

本节课深入研究 **LangChain 中的输出解析器**，并使用 **Pydantic 解析器**重构第 4 课中的程序。这是模型 I/O 框架的最后一讲。

[![](https://static001.geekbang.org/resource/image/62/2d/6215fdd31373523a46bb02f86283522d.jpg?wh=4000x1536)](https://static001.geekbang.org/resource/image/62/2d/6215fdd31373523a46bb02f86283522d.jpg?wh=4000x1536)

模型 I/O Pipeline 架构图

---

## 输出解析器概述

### 为什么需要输出解析器？

语言模型输出的是**文本**，适合人类阅读。但在实际应用中，我们往往需要获得**程序能够处理的结构化信息**。这就是输出解析器发挥作用的地方。

### 核心方法

一个基本的输出解析器类通常需要实现以下方法：

**必需方法：**

- `get_format_instructions`：返回一个字符串，指导如何格式化语言模型的输出

- `parse`：接收字符串（模型输出）并解析为特定的数据结构

**可选方法：**

- `parse_with_prompt`：接收字符串和提示，根据原始提示修正或重新解析输出

### 基础代码结构

```python
class OutputParser:
    def __init__(self):
        pass

    def get_format_instructions(self):
        pass

    def parse(self, model_output):
        pass

    def parse_with_prompt(self, model_output, prompt):
        pass
```

---

## 解析器类型

### 基础解析器

- **列表解析器（List Parser）**：处理列表格式的输出

- **日期时间解析器（Datetime Parser）**：处理日期和时间格式

- **枚举解析器（Enum Parser）**：处理预定义的一组值

### 高级解析器

- **结构化输出解析器（Structured Output Parser）**：处理复杂的结构化输出

- **Pydantic（JSON）解析器**：处理符合特定格式的 JSON 对象

- **自动修复解析器（Auto-Fixing Parser）**：自动修复常见的输出错误

- **重试解析器（RetryWithErrorOutputParser）**：输出不符合预期时尝试重新生成

---

## Pydantic 解析器实战

### 什么是 Pydantic？

**Pydantic** 是一个 Python 数据验证和设置管理库，基于 Python 类型提示，在处理和验证 JSON 数据时特别有用。

**核心特点：**

- **数据验证**：自动验证输入数据类型

- **数据转换**：自动进行类型转换（如 "42" → 42）

- **易于使用**：像定义普通 Python 类一样简单

- **JSON 支持**：轻松与 JSON 数据互转

### 实战步骤

#### 第一步：创建模型实例

```python
import os
os.environ["OPENAI_API_KEY"] = '你的OpenAI API Key'

from langchain import OpenAI
model = OpenAI(model_name='gpt-3.5-turbo-instruct')
```

#### 第二步：定义输出数据格式

```python
import pandas as pd

# 创建空 DataFrame
df = pd.DataFrame(columns=["flower_type", "price", "description", "reason"])
flowers = ["玫瑰", "百合", "康乃馨"]
prices = ["50", "30", "20"]

# 定义 Pydantic 数据模型
from pydantic import BaseModel, Field

class FlowerDescription(BaseModel):
    flower_type: str = Field(description="鲜花的种类")
    price: int = Field(description="鲜花的价格")
    description: str = Field(description="鲜花的描述文案")
    reason: str = Field(description="为什么要这样写这个文案")
```

#### 第三步：创建输出解析器

```python
from langchain.output_parsers import PydanticOutputParser

output_parser = PydanticOutputParser(pydantic_object=FlowerDescription)
format_instructions = output_parser.get_format_instructions()
print("输出格式：", format_instructions)
```

**输出示例：**

```jsx
The output should be formatted as a JSON instance that conforms to the JSON schema below.

As an example, for the schema {"properties": {"foo": {"title": "Foo", "description": "a list of strings", "type": "array", "items": {"type": "string"}}}, "required": ["foo"]}
the object {"foo": ["bar", "baz"]} is a well-formatted instance of the schema. The object {"properties": {"foo": ["bar", "baz"]}} is not well-formatted.

Here is the output schema:
{"properties": {"flower_type": {"title": "Flower Type", "description": "\u9c9c\u82b1\u7684\u79cd\u7c7b", "type": "string"}, "price": {"title": "Price", "description": "\u9c9c\u82b1\u7684\u4ef7\u683c", "type": "integer"}, "description": {"title": "Description", "description": "\u9c9c\u82b1\u7684\u63cf\u8ff0\u6587\u6848", "type": "string"}, "reason": {"title": "Reason", "description": "\u4e3a\u4ec0\u4e48\u8981\u8fd9\u6837\u5199\u8fd9\u4e2a\u6587\u6848", "type": "string"}}, "required": ["flower_type", "price", "description", "reason"]}
```

> [!important]
>
> **核心价值**：`get_format_instructions()` 方法生成的指令是 Pydantic 解析器的核心，它为模型提供清晰的 JSON Schema 格式指导。

#### 第四步：创建提示模板

```python
from langchain import PromptTemplate

prompt_template = """您是一位专业的鲜花店文案撰写员。
对于售价为 {price} 元的 {flower} ，您能提供一个吸引人的简短中文描述吗？
{format_instructions}"""

prompt = PromptTemplate.from_template(
    prompt_template,
    partial_variables={"format_instructions": format_instructions}
)
```

**提示模板关键参数说明：**

- `input_variables=['flower', 'price']`：模板中使用的输入变量

- `output_parser=None`：在模型外部进行输出解析

- `partial_variables`：包含格式说明的部分变量

- `template_format='f-string'`：使用 f-string 格式

- `validate_template=True`：创建时检查模板有效性

#### 第五步：生成提示并解析输出

```python
for flower, price in zip(flowers, prices):
    # 生成具体提示
    input = prompt.format(flower=flower, price=price)
    print("提示：", input)

    # 调用模型
    output = model(input)

    # 解析输出
    parsed_output = output_parser.parse(output)
    parsed_output_dict = parsed_output.dict()

    # 添加到 DataFrame
    df.loc[len(df)] = parsed_output_dict

print("输出的数据：", df.to_dict(orient='records'))
```

**最终输出示例：**

```json
[
  {
    "flower_type": "Rose",
    "price": 50,
    "description": "玫瑰是最浪漫的花，它具有柔和的粉红色，有着浓浓的爱意，价格实惠，50元就可以拥有一束玫瑰。",
    "reason": "玫瑰代表着爱情，是最浪漫的礼物，以实惠的价格，可以让您尽情体验爱的浪漫。"
  },
  {
    "flower_type": "百合",
    "price": 30,
    "description": "这支百合，柔美的花蕾，在你的手中摇曳，仿佛在与你深情的交谈",
    "reason": "营造浪漫氛围"
  },
  {
    "flower_type": "Carnation",
    "price": 20,
    "description": "艳丽缤纷的康乃馨，带给你温馨、浪漫的气氛，是最佳的礼物选择！",
    "reason": "康乃馨是一种颜色鲜艳、芬芳淡雅、具有浪漫寓意的鲜花，非常适合作为礼物，而且20元的价格比较实惠。"
  }
]
```

> [!important]
>
> **Pydantic 的优势**：解析后的字典格式在数据分析、处理和存储时非常方便，每个字段对应一列，每个字典就是一行，适合以 DataFrame 的形式表示和处理。

---

## 自动修复解析器实战

### 设计一个解析错误

```python
from langchain.output_parsers import PydanticOutputParser
from pydantic import BaseModel, Field
from typing import List

class Flower(BaseModel):
    name: str = Field(description="name of a flower")
    colors: List[str] = Field(description="the colors of this flower")

flower_query = "Generate the charaters for a random flower."

# 错误格式：使用单引号而非双引号
misformatted = "{'name': '康乃馨', 'colors': ['粉红色','白色','红色','紫色','黄色']}"

parser = PydanticOutputParser(pydantic_object=Flower)
parser.parse(misformatted)
```

**错误信息：**

```jsx
langchain.schema.output_parser.OutputParserException: Failed to parse Flower from completion {'name': '康乃馨', 'colors': ['粉红色','白色']}. Got: Expecting property name enclosed in double quotes: line 1 column 2 (char 1)
```

> [!important]
>
> **问题原因**：JSON 格式要求属性名称使用双引号，但输入字符串使用了单引号。

### 使用 OutputFixingParser 解决

```python
from langchain.chat_models import ChatOpenAI
from langchain.output_parsers import OutputFixingParser
import os

os.environ["OPENAI_API_KEY"] = '你的OpenAI API Key'

new_parser = OutputFixingParser.from_llm(parser=parser, llm=ChatOpenAI())
result = new_parser.parse(misformatted)
print(result)
```

**输出：**

```jsx
name='Rose' colors=['red', 'pink', 'white']
```

> [!important]
>
> **工作原理**：OutputFixingParser 内部调用原有的 PydanticOutputParser，如果失败，会将格式错误的输出和格式化指令传递给大模型，要求 LLM 进行修复。

---

## 重试解析器实战

### OutputFixingParser 的局限性

OutputFixingParser 只能做简单的格式修复。如果输出内容不完整或有缺失，仅凭输出和格式本身无法修复。

此时，**RetryWithErrorOutputParser** 通过 `parse_with_prompt` 方法，利用大模型的推理能力根据原始提示找回相关信息。

### 设计一个内容缺失的错误

```python
template = """Based on the user question, provide an Action and Action Input for what step should be taken.
{format_instructions}
Question: {query}
Response:"""

from pydantic import BaseModel, Field

class Action(BaseModel):
    action: str = Field(description="action to take")
    action_input: str = Field(description="input to the action")

from langchain.output_parsers import PydanticOutputParser

parser = PydanticOutputParser(pydantic_object=Action)

from langchain.prompts import PromptTemplate

prompt = PromptTemplate(
    template="Answer the user query.\n{format_instructions}\n{query}\n",
    input_variables=["query"],
    partial_variables={"format_instructions": parser.get_format_instructions()},
)

prompt_value = prompt.format_prompt(query="What are the colors of Orchid?")

# 缺失 action_input 字段
bad_response = '{"action": "search"}'
parser.parse(bad_response)  # 会失败
```

### 尝试用 OutputFixingParser 解决

```python
from langchain.output_parsers import OutputFixingParser
from langchain.chat_models import ChatOpenAI

fix_parser = OutputFixingParser.from_llm(parser=parser, llm=ChatOpenAI())
parse_result = fix_parser.parse(bad_response)
print('OutputFixingParser的parse结果:', parse_result)
```

**输出：**

```jsx
action='search' action_input='query'
```

**问题分析：**

✅ **解决的问题**：填补了缺失的 `action_input` 字段

❌ **未解决的问题**：

- 缺乏具体性：`'query'` 是通用值，而非真正的查询 "Orchid 的颜色是什么？"

- 可能误导：`'query'` 可能被误解为要求进一步查询

### 使用 RetryWithErrorOutputParser 完美解决

```python
from langchain.output_parsers import RetryWithErrorOutputParser
from langchain.llms import OpenAI

retry_parser = RetryWithErrorOutputParser.from_llm(
    parser=parser, llm=OpenAI(temperature=0)
)

parse_result = retry_parser.parse_with_prompt(bad_response, prompt_value)
print('RetryWithErrorOutputParser的parse结果:', parse_result)
```

**输出：**

```jsx
action='search' action_input='colors of Orchid'
```

> [!important]
>
> **完美解决**：不仅还原了格式，还根据原始提示还原了 `action_input` 字段的正确内容。

---

## 总结

### 解析器选择指南

|解析器类型|适用场景|能力特点|
|---|---|---|
|**结构化解析器**|简单文本响应|基础格式化|
|**Pydantic 解析器**|复杂数据结构|类型验证、JSON 支持|
|**自动修复解析器**|小的格式错误|被动修复、格式纠正|
|**重试解析器**|内容缺失、复杂问题|主动重试、内容补全|

### 核心要点

- **Pydantic 解析器**提供对复杂数据结构和类型的完整支持

- **自动修复解析器**适用于纠正格式错误，较为"被动"

- **重试解析器**可处理更复杂问题，通过重新与模型交互确保输出完整准确

选择解析器时需考虑具体应用场景：

- 仅面临格式问题 → 自动修复解析器

- 输出完整性和准确性至关重要 → 重试解析器

---

## 思考题

1. 到目前为止，我们已经使用了哪些 LangChain 输出解析器？请说说它们的用法和异同。同时也请尝试使用其他类型的输出解析器。

1. 为什么大模型能够返回 JSON 格式的数据？输出解析器用了什么魔法让大模型做到这一点？

1. 自动修复解析器的"修复"功能具体是怎样实现的？请 debug 研究一下 LangChain 在调用大模型之前如何设计"提示"。

1. 重试解析器的原理是什么？它主要实现了解析器类的哪个可选方法？

---

## 延伸阅读

- **工具**：[Pydantic 官方文档](https://docs.pydantic.dev/) - Python 数据验证库

- **文档**：[LangChain Output Parsers](https://python.langchain.com/docs/modules/model_io/output_parsers/) - 各种输出解析器详解

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

课程总结
