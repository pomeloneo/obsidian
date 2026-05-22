> **课程来源**: [极客时间 - LangChain 实战课](https://time.geekbang.org/column/article/703296)

[![](https://static001.geekbang.org/resource/image/d6/91/d60ec886bbfcfa772920fc353e48f291.jpg)](https://static001.geekbang.org/resource/image/d6/91/d60ec886bbfcfa772920fc353e48f291.jpg)

课程封面

---

## 为什么需要 Chain？

对于简单的应用程序，直接调用 LLM 就已经足够。但如果要开发更复杂的应用程序，就需要通过 **"Chain"** 来链接 LangChain 的各个组件和功能。

> [!important]
>
> **Chain 的核心价值**：将多个组件相互链接，组合成一个链。这种设计简化了复杂应用程序的实现，使之更加模块化，能够创建出单一、连贯的应用程序，从而使调试、维护和改进变得容易。

[![](https://static001.geekbang.org/resource/image/e2/de/e26993dd3957bfd2947424abb9de7cde.png?wh=1965x1363)](https://static001.geekbang.org/resource/image/e2/de/e26993dd3957bfd2947424abb9de7cde.png?wh=1965x1363)

Chain 架构示意图

---

## Chain 的工作原理

### 实现机制

**内部封装**：Chain 内部封装一系列功能

**外部组合**：Chain 之间可以组合串联

**基本单元**：Chain 可以被视为 LangChain 中的一种基本功能单元

### Chain 的类型

LangChain 提供了多种预置链，使各种任务实现更加方便、规范：

[![](https://static001.geekbang.org/resource/image/8b/c3/8b580b2b8e0fc8515d271165a46101c3.jpg?wh=1702x861)](https://static001.geekbang.org/resource/image/8b/c3/8b580b2b8e0fc8515d271165a46101c3.jpg?wh=1702x861)

LangChain 中的各种链类型

---

## LLMChain：最简单的链

### 核心功能

LLMChain 整合了三个核心组件：

- **PromptTemplate**：提示模板

- **LLM/Chat Model**：语言模型

- **Output Parser**：输出解析器

相当于把 **Model I/O** 放在一个链中整体操作。

### 对比：不使用链 vs 使用链

**不使用链的代码：**

```python
from langchain import PromptTemplate

template = "{flower}的花语是?"
prompt_temp = PromptTemplate.from_template(template)
prompt = prompt_temp.format(flower='玫瑰')
print(prompt)

from langchain import OpenAI
model = OpenAI(temperature=0)
result = model(prompt)
print(result)
```

**输出：**

```jsx
玫瑰的花语是?
爱情、浪漫、美丽、永恒、誓言、坚贞不渝。
```

**使用链的代码：**

```python
from langchain import PromptTemplate, OpenAI, LLMChain

template = "{flower}的花语是?"
llm = OpenAI(temperature=0)
llm_chain = LLMChain(
    llm=llm,
    prompt=PromptTemplate.from_template(template)
)
result = llm_chain("玫瑰")
print(result)
```

**输出：**

```python
{'flower': '玫瑰', 'text': '\n\n爱情、浪漫、美丽、永恒、誓言、坚贞不渝。'}
```

> [!important]
>
> **优势**：使用链将提示模板的构建和模型的调用封装在一起，代码结构更简洁。

---

## 链的调用方式

### 1. 直接调用（`__call__` 方法）

当像函数一样调用链对象时，会调用内部实现的 `__call__` 方法。

**单变量输入：**

```python
llm_chain("玫瑰")
```

**多变量输入（使用字典）：**

```python
prompt = PromptTemplate(
    input_variables=["flower", "season"],
    template="{flower}在{season}的花语是?",
)
llm_chain = LLMChain(llm=llm, prompt=prompt)
print(llm_chain({
    'flower': "玫瑰",
    'season': "夏季"
}))
```

**输出：**

```python
{'flower': '玫瑰', 'season': '夏季', 'text': '\n\n玫瑰在夏季的花语是爱的誓言，热情，美丽，坚定的爱情。'}
```

### 2. 通过 `run` 方法

```python
llm_chain.run("玫瑰")  # 等价于 llm_chain("玫瑰")
```

### 3. 通过 `predict` 方法

使用关键字参数而不是 Python 字典：

```python
result = llm_chain.predict(flower="玫瑰")
print(result)
```

### 4. 通过 `apply` 方法

针对输入列表运行链，一次处理多个输入：

```python
input_list = [
    {"flower": "玫瑰", 'season': "夏季"},
    {"flower": "百合", 'season': "春季"},
    {"flower": "郁金香", 'season': "秋季"}
]
result = llm_chain.apply(input_list)
print(result)
```

**输出：**

```python
[
    {'text': '\n\n玫瑰在夏季的花语是"恋爱"、"热情"和"浪漫"。'},
    {'text': '\n\n百合在春季的花语是"爱情"和"友谊"。'},
    {'text': '\n\n郁金香在秋季的花语表达的是"热情"、"思念"、"爱恋"、"回忆"和"持久的爱"。'}
]
```

### 5. 通过 `generate` 方法

类似于 `apply`，但返回 **LLMResult** 对象，包含更多生成信息：

```python
result = llm_chain.generate(input_list)
print(result)
```

**输出：**

```python
generations=[
    [Generation(text='\n\n玫瑰在夏季的花语是"热情"、"爱情"和"幸福"。',
                generation_info={'finish_reason': 'stop', 'logprobs': None})],
    [Generation(text='\n\n春季的花语是爱情、幸福、美满、坚贞不渝。',
                generation_info={'finish_reason': 'stop', 'logprobs': None})],
    [Generation(text='\n\n秋季的花语是"思念"。银色的百合象征着"真爱"，而淡紫色的郁金香则象征着"思念"，因为它们在秋天里绽放的时候，犹如在思念着夏天的温暖。',
                generation_info={'finish_reason': 'stop', 'logprobs': None})]
]
llm_output={'token_usage': {'completion_tokens': 243, 'total_tokens': 301, 'prompt_tokens': 58},
            'model_name': 'gpt-3.5-turbo-instruct'}
run=[RunInfo(run_id=UUID('13058cca-881d-4b76-b0cf-0f9c831af6c4')),
     RunInfo(run_id=UUID('7f38e33e-bab5-4d03-b77c-f50cd195affb')),
     RunInfo(run_id=UUID('7a1e45fd-77ee-4133-aab0-431147186db8'))]
```

> [!important]
>
> **LLMResult 包含的信息**：令牌数量、模型名称、完成原因、运行 ID 等详细元数据。

---

## Sequential Chain：顺序链

顺序链可以将多个 LLMChain 串联起来，形成一个按顺序执行的链。

[![](https://static001.geekbang.org/resource/image/48/36/48f3f524ecf2d2yyeb11fd54yyf99f36.png?wh=665x360)](https://static001.geekbang.org/resource/image/48/36/48f3f524ecf2d2yyeb11fd54yyf99f36.png?wh=665x360)

顺序链示意图

### 实战案例：生成鲜花营销文案

**目标：**

1. 植物学家 → 给出鲜花的知识介绍

1. 鲜花评论者 → 参考介绍，撰写评论

1. 社交媒体经理 → 参考介绍和评论，撰写营销文案

### 实现步骤

#### 第一步：导入所有需要的库

```python
import os
os.environ["OPENAI_API_KEY"] = '你的OpenAI API Key'

from langchain.llms import OpenAI
from langchain.chains import LLMChain
from langchain.prompts import PromptTemplate
from langchain.chains import SequentialChain
```

#### 第二步：创建第一个链 - 植物学家介绍

```python
llm = OpenAI(temperature=.7)

template = """
你是一个植物学家。给定花的名称和类型，你需要为这种花写一个200字左右的介绍。

花名: {name}
颜色: {color}
植物学家: 这是关于上述花的介绍:"""

prompt_template = PromptTemplate(
    input_variables=["name", "color"],
    template=template
)
introduction_chain = LLMChain(
    llm=llm,
    prompt=prompt_template,
    output_key="introduction"
)
```

#### 第三步：创建第二个链 - 鲜花评论

```python
llm = OpenAI(temperature=.7)

template = """
你是一位鲜花评论家。给定一种花的介绍，你需要为这种花写一篇200字左右的评论。

鲜花介绍:
{introduction}
花评人对上述花的评论:"""

prompt_template = PromptTemplate(
    input_variables=["introduction"],
    template=template
)
review_chain = LLMChain(
    llm=llm,
    prompt=prompt_template,
    output_key="review"
)
```

#### 第四步：创建第三个链 - 社交媒体文案

```python
template = """
你是一家花店的社交媒体经理。给定一种花的介绍和评论，你需要为这种花写一篇社交媒体的帖子，300字左右。

鲜花介绍:
{introduction}
花评人对上述花的评论:
{review}

社交媒体帖子:
"""

prompt_template = PromptTemplate(
    input_variables=["introduction", "review"],
    template=template
)
social_post_chain = LLMChain(
    llm=llm,
    prompt=prompt_template,
    output_key="social_post_text"
)
```

#### 第五步：组装 SequentialChain

```python
overall_chain = SequentialChain(
    chains=[introduction_chain, review_chain, social_post_chain],
    input_variables=["name", "color"],
    output_variables=["introduction", "review", "social_post_text"],
    verbose=True
)

result = overall_chain({"name": "玫瑰", "color": "黑色"})
print(result)
```

### 最终输出

```jsx
> Entering new chain…
> Finished chain.

{
  'name': '玫瑰',
  'color': '黑色',
  'introduction': '\n\n黑色玫瑰，这是一种对传统玫瑰花的独特颠覆，它的出现挑战了我们对玫瑰颜色的固有认知。它的花瓣如煤炭般黑亮，反射出独特的微光，而花蕊则是金黄色的，宛如夜空中的一颗星，强烈的颜色对比营造出一种前所未有的视觉效果。在植物学中，黑色玫瑰的出现无疑提供了一种新的研究方向，对于我们理解花朵色彩形成的机制有着重要的科学价值。',

  'review': '\n\n黑色玫瑰，这不仅仅是一种花朵，更是一种完全颠覆传统的艺术表现形式。黑色的花瓣仿佛在诉说一种不可言喻的悲伤与神秘，而黄色的蕊瓣犹如漆黑夜空中的一抹亮色，给人带来无尽的想象。它将悲伤与欢乐，神秘与明亮完美地结合在一起，这是一种全新的视觉享受，也是一种对生活理解的深度表达。',

  'social_post_text': '\n欢迎来到我们的自媒体平台，今天，我们要向您展示的是我们的全新产品——黑色玫瑰。这不仅仅是一种花，这是一种对传统观念的挑战，一种视觉艺术的革新，更是一种生活态度的象征。

这种别样的玫瑰花，其黑色花瓣宛如漆黑夜空中闪烁的繁星，富有神秘的深度感，给人一种前所未有的视觉冲击力。这种黑色，它不是冷酷、不是绝望，而是充满着独特的魅力和力量。而位于黑色花瓣之中的金黄色花蕊，则犹如星星中的灵魂，默默闪烁，给人带来无尽的遐想，充满活力与生机。

黑色玫瑰的存在，不仅挑战了我们对于玫瑰传统颜色的认知，它更是一种生动的生命象征，象征着那些坚韧、独特、勇敢面对生活的人们。黑色的花瓣中透露出一种坚韧的力量，而金黄的花蕊则是生活中的希望，二者的结合恰好象征了生活中的喜怒哀乐，体现了人生的百态。'
}
```

> [!important]
>
> **成功**：通过三个 LLMChain 和一个 SequentialChain，生成了一篇完美的营销文案！

---

## 总结

### 核心概念

LangChain 提供的"链"帮助我们把多个组件像链条一样连接起来：

- **链条**：一系列组件的调用顺序

- **嵌套**：链条里还可以包括其他链条

- **灵活调用**：多种调用方法满足不同需求

- **类型丰富**：各种预置链封装了不同功能

[![](https://static001.geekbang.org/resource/image/5f/38/5fe2366c3e8294a61cb44d33b9d79638.png?wh=1741x1327)](https://static001.geekbang.org/resource/image/5f/38/5fe2366c3e8294a61cb44d33b9d79638.png?wh=1741x1327)

LangChain 链的体系结构

### 常用链类型

|链类型|功能描述|
|---|---|
|**LLMChain**|最基础的链，整合提示模板、模型和输出解析器|
|**SequentialChain**|顺序链，按顺序执行多个链|
|**RouterChain**|路由链（下节课介绍）|

> [!important]
>
> **扩展学习**：LangChain 还自带大量其他类型的链，可以查看这些链的实现细节并尝试使用。

---

## 思考题

1. **基础重构**：在第 3 课中，我们用提示模板生成过鲜花描述。请使用 LLMChain 重构以下代码：

```python
for flower, price in zip(flowers, prices):
    input = prompt.format(flower_name=flower, price=price)
    output = model(input)
    parsed_output = output_parser.parse(output)
```

**提示：**

```python
llm_chain = LLMChain(
    llm=model,
    prompt=prompt
)
```

1. **进阶整合**：进一步把 `output_parser` 也整合到 LLMChain 中，让程序结构更简化：

```python
llm_chain = LLMChain(
    llm=model,
    prompt=prompt,
    output_parser=output_parser
)
```

1. **探索实践**：选择一个我们没用到的 LangChain 链类型，尝试使用它解决一个问题，并分享你的用例和代码。

---

## 延伸阅读

- **GitHub**：[LangChain 中的各种链](https://github.com/langchain-ai/langchain/tree/master/libs/langchain/langchain/chains)

- **代码**：[LLMChain 的实现细节](https://github.com/langchain-ai/langchain/blob/master/libs/langchain/langchain/chains/llm.py)


课程总结
