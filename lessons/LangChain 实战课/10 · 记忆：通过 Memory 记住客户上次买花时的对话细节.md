> **课程来源**: [极客时间 - LangChain 实战课](https://time.geekbang.org/column/article/704183)

[![](https://static001.geekbang.org/resource/image/f6/71/f6b20632b52c5b6f206176bd7c8b7071.jpg)](https://static001.geekbang.org/resource/image/f6/71/f6b20632b52c5b6f206176bd7c8b7071.jpg)

课程封面

---

# 为什么需要记忆机制？

在默认情况下，无论是 LLM 还是代理都是**无状态的**，每次模型的调用都是独立于其他交互的。每次通过 API 开始和大语言模型展开新对话时，它都不知道你曾经和它聊过天。

[![](https://static001.geekbang.org/resource/image/c9/97/c9907bc695521228cdfb5d3f75c13897.png?wh=588x593)](https://static001.geekbang.org/resource/image/c9/97/c9907bc695521228cdfb5d3f75c13897.png?wh=588x593)

ChatGPT 对话示例

> [!important]
> 
> **ChatGPT 的秘密**
> 
> ChatGPT 能够记得你之前说过的话，正是因为它使用了**记忆（Memory）机制**，记录了之前的对话上下文，并将这个上下文作为提示的一部分，在最新的调用中传递给模型。

在聊天机器人的构建中，记忆机制非常重要。

[![](https://static001.geekbang.org/resource/image/e2/de/e26993dd3957bfd2947424abb9de7cde.png?wh=1965x1363)](https://static001.geekbang.org/resource/image/e2/de/e26993dd3957bfd2947424abb9de7cde.png?wh=1965x1363)

记忆机制在 Model I/O 中的位置

---

# ConversationChain 的对话格式

在介绍记忆机制的具体实现之前，先看一下 **ConversationChain** 的特点。

## 核心特点

ConversationChain 提供了包含 **AI 前缀**和**人类前缀**的对话摘要格式，这个对话格式和记忆机制结合得非常紧密。

## 示例代码

```python
from langchain import OpenAI
from langchain.chains import ConversationChain

llm = OpenAI(
    temperature=0.5,
    model_name="gpt-3.5-turbo-instruct"
)

conv_chain = ConversationChain(llm=llm)
print(conv_chain.prompt.template)
```

**输出：**

```jsx
The following is a friendly conversation between a human and an AI. The AI is talkative and provides lots of specific details from its context. If the AI does not know the answer to a question, it truthfully says it does not know.

Current conversation:
{history}
Human: {input}
AI:
```

## 提示模板解析

这个提示模板为人类和 AI 之间的对话设置了基本框架：

**对话基调**

> "这是人类和 AI 之间的友好对话。AI 非常健谈并从其上下文中提供了大量的具体细节。"

**减少幻觉**

> "如果 AI 不知道问题的答案，它就会如实说它不知道。"

**两个关键参数**

- **{history}** - 存储会话记忆的地方，即人类和 AI 之间对话历史的信息

- **{input}** - 新输入的地方，类似于 ChatGPT 对话时文本框中的输入

[![](https://static001.geekbang.org/resource/image/c1/7c/c11b24c318dbd762f13781e3e40f9b7c.png?wh=1592x1066)](https://static001.geekbang.org/resource/image/c1/7c/c11b24c318dbd762f13781e3e40f9b7c.png?wh=1592x1066)

对话格式示意图

> [!important]
> 
> **记忆机制的原理**
> 
> 当有了 `{history}` 参数，以及 Human 和 AI 这两个前缀，我们就能够把历史对话信息存储在提示模板中，并作为新的提示内容在新一轮对话中传递给模型。

---

# ConversationBufferMemory：缓冲记忆

## 概念

**ConversationBufferMemory（缓冲记忆）** 实现了最简单的记忆机制。

## 实现代码

```python
from langchain import OpenAI
from langchain.chains import ConversationChain
from langchain.chains.conversation.memory import ConversationBufferMemory

llm = OpenAI(
    temperature=0.5,
    model_name="gpt-3.5-turbo-instruct"
)

conversation = ConversationChain(
    llm=llm,
    memory=ConversationBufferMemory()
)
```

## 第一轮对话

```python
conversation("我姐姐明天要过生日，我需要一束生日花束。")
print("第一次对话后的记忆:", conversation.memory.buffer)
```

**输出：**

```jsx
第一次对话后的记忆:
Human: 我姐姐明天要过生日，我需要一束生日花束。
AI: 哦，你姐姐明天要过生日，那太棒了！我可以帮你推荐一些生日花束，你想要什么样的？我知道有很多种，比如玫瑰、康乃馨、郁金香等等。
```

## 第二轮对话

```python
conversation("她喜欢粉色玫瑰，颜色是粉色的。")
print("第二次对话后的记忆:", conversation.memory.buffer)
```

**输出：**

```jsx
第二次对话后的记忆:
Human: 我姐姐明天要过生日，我需要一束生日花束。
AI: 哦，你姐姐明天要过生日，那太棒了！我可以帮你推荐一些生日花束，你想要什么样的？我知道有很多种，比如玫瑰、康乃馨、郁金香等等。
Human: 她喜欢粉色玫瑰，颜色是粉色的。
AI: 好的，那我可以推荐一束粉色玫瑰的生日花束给你。你想要多少朵？我可以帮你定制一束，比如说十朵、二十朵或者更多？
```

## 第三轮对话

```python
conversation("我又来了，还记得我昨天为什么要来买花吗？")
print("\n第三次对话后的记忆:\n", conversation.memory.buffer)
```

**输出：**

```jsx
Human: 我姐姐明天要过生日，我需要一束生日花束。
AI: 哦，你姐姐明天要过生日，那太棒了！我可以帮你推荐一些生日花束，你想要什么样的？我知道有很多种，比如玫瑰、康乃馨、郁金香等等。
Human: 她喜欢粉色玫瑰，颜色是粉色的。
AI: 好的，那我可以推荐一束粉色玫瑰的生日花束给你，你想要多少朵？
Human: 我又来了，还记得我昨天为什么要来买花吗？
AI: 是的，我记得你昨天来买花是因为你姐姐明天要过生日，你想要买一束粉色玫瑰的生日花束给她。
```

## 工作原理

这些聊天历史信息都被传入了 ConversationChain 的提示模板中的 `{history}` 参数，构建出了包含聊天记录的新的提示输入。

## 优缺点分析

|**优点**|**缺点**|
|---|---|
|为 LLM 提供最大量的信息  <br>完整保留所有对话内容|包含更多 Token（所有聊天历史记录）  <br>响应时间变慢，成本更高  <br>达到 Token 限制时无法记住太长对话|

> [!important]
> 
> **Token 限制**
> 
> text-davinci-003 和 gpt-3.5-turbo 的最大输入限制是 4096 个 Token，超出此限制的对话内容将无法被记住。

---

# ConversationBufferWindowMemory：缓冲窗口记忆

## 概念

**ConversationBufferWindowMemory（缓冲窗口记忆）** 只保存最新最近的几次人类和 AI 的互动。

## 核心参数

在"缓冲记忆"基础上增加了**窗口值 k**，只保留 k 次过去互动，然后"忘记"之前的互动。

## 实现代码

```python
from langchain import OpenAI
from langchain.chains import ConversationChain
from langchain.chains.conversation.memory import ConversationBufferWindowMemory

llm = OpenAI(
    temperature=0.5,
    model_name="gpt-3.5-turbo-instruct"
)

conversation = ConversationChain(
    llm=llm,
    memory=ConversationBufferWindowMemory(k=1)  # 只保留最近 1 次互动
)
```

## 测试结果

**第一回合输出：**

```python
{
  'input': '我姐姐明天要过生日，我需要一束生日花束。',
  'history': '',
  'response': ' 哦，你姐姐明天要过生日！那太棒了！你想要一束什么样的花束呢？有很多种类可以选择，比如玫瑰花束、康乃馨花束、郁金香花束等等，你有什么喜欢的吗？'
}
```

**第二回合输出：**

```python
{
  'input': '她喜欢粉色玫瑰，颜色是粉色的。',
  'history': 'Human: 我姐姐明天要过生日，我需要一束生日花束。\nAI: 哦，你姐姐明天要过生日！那太棒了！你想要一束什么样的花束呢？有很多种类可以选择，比如玫瑰花束、康乃馨花束、郁金香花束等等，你有什么喜欢的吗？',
  'response': ' 好的，那粉色玫瑰花束怎么样？我可以帮你找到一束非常漂亮的粉色玫瑰花束，你觉得怎么样？'
}
```

**第三回合输出：**

```python
{
  'input': '我又来了，还记得我昨天为什么要来买花吗？',
  'history': 'Human: 她喜欢粉色玫瑰，颜色是粉色的。\nAI: 好的，那粉色玫瑰花束怎么样？我可以帮你找到一束非常漂亮的粉色玫瑰花束，你觉得怎么样？',
  'response': ' 当然记得，你昨天来买花是为了给你喜欢的人送一束粉色玫瑰花束，表达你对TA的爱意。'
}
```

> [!important]
> 
> **问题分析**
> 
> 设置 k=1 时，窗口只记住最新的互动。第三回合询问"还记得我昨天为什么要来买花吗？"时，由于只保留了最近的互动，模型忘记了第一回合提到的**"姐姐"**，只能模糊地说**"喜欢的人"**。

## 适用场景

|**擅长**|**适合**|**不适合**|
|---|---|---|
|限制使用的 Token 数量|只需要记住最近互动的场景|需要混合远期和近期互动信息的场景|

---

# ConversationSummaryMemory：对话总结记忆

## 概念

**ConversationSummaryMemory（对话总结记忆）** 将对话历史进行汇总，然后再传递给 `{history}` 参数。

## 核心特点

- **汇总对话** - 不保存整个对话历史，而是对互动进行汇总

- **使用 LLM 进行汇总** - 汇总功能由另一个 LLM 驱动

- **适合长对话** - 随着对话进展，汇总方法的增长速度会减慢

## 实现代码

```python
from langchain.chains.conversation.memory import ConversationSummaryMemory

conversation = ConversationChain(
    llm=llm,
    memory=ConversationSummaryMemory(llm=llm)
)
```

## 测试结果

**第一回合输出：**

```python
{
  'input': '我姐姐明天要过生日，我需要一束生日花束。',
  'history': '',
  'response': ' 我明白，你需要一束生日花束。我可以为你提供一些建议吗？我可以推荐一些花束给你，比如玫瑰，康乃馨，百合，仙客来，郁金香，满天星等等。挑选一束最适合你姐姐的生日花束吧！'
}
```

**第二回合输出：**

```python
{
  'input': '她喜欢粉色玫瑰，颜色是粉色的。',
  'history': "\nThe human asked what the AI thinks of artificial intelligence. The AI thinks artificial intelligence is a force for good because it will help humans reach their full potential. The human then asked the AI for advice on what type of flower bouquet to get for their sister's birthday, to which the AI provided a variety of suggestions.",
  'response': ' 为了为你的姐姐的生日准备一束花，我建议你搭配粉色玫瑰和白色康乃馨。你可以在玫瑰花束中添加一些紫色的满天星，或者添加一些绿叶以增加颜色对比。这将是一束可爱的花束，让你姐姐的生日更加特别。'
}
```

**第三回合输出：**

```python
{
  'input': '我又来了，还记得我昨天为什么要来买花吗？',
  'history': "\n\nThe human asked what the AI thinks of artificial intelligence. The AI thinks artificial intelligence is a force for good because it will help humans reach their full potential. The human then asked the AI for advice on what type of flower bouquet to get for their sister's birthday, to which the AI suggested pink roses and white carnations with the addition of purple aster flowers and green leaves for contrast. This would make a lovely bouquet to make the sister's birthday extra special.",
  'response': ' 确实，我记得你昨天想买一束花给你的姐姐作为生日礼物。我建议你买粉红色的玫瑰花和白色的康乃馨花，再加上紫色的雏菊花和绿叶，这样可以让你的姐姐的生日更加特别。'
}
```

> [!important]
> 
> **关键特点**
> 
> `history` 不再是简单的复制粘贴，而是经过总结和整理后的综述信息。

## 优缺点分析

|**优点**|**缺点**|
|---|---|
|对于长对话可以减少使用的 Token 数量  <br>可以记录更多轮的对话信息  <br>直观易懂|对于较短的对话可能导致更高的 Token 使用  <br>完全依赖于中间汇总 LLM 的能力  <br>需要为汇总 LLM 使用 Token，增加成本  <br>并不限制对话长度  <br>没有区分近期和长期对话的重要性|

---

# ConversationSummaryBufferMemory：对话总结缓冲记忆

## 概念

**ConversationSummaryBufferMemory（对话总结缓冲记忆）** 是一种混合记忆模型，结合了上述各种记忆机制的特点。

## 工作原理

通过 **max_token_limit** 参数控制：

- 对话文字长度在限制内 → 记忆原始对话内容

- 对话文字超出限制 → 总结超出部分以节省 Token

## 实现代码

```python
from langchain.chains.conversation.memory import ConversationSummaryBufferMemory

conversation = ConversationChain(
    llm=llm,
    memory=ConversationSummaryBufferMemory(
        llm=llm,
        max_token_limit=300
    )
)
```

## 测试结果

**第一回合输出：**

```python
{
  'input': '我姐姐明天要过生日，我需要一束生日花束。',
  'history': '',
  'response': ' 哇，你姐姐要过生日啊！那太棒了！我建议你去买一束色彩鲜艳的花束，因为这样可以代表你给她的祝福和祝愿。你可以去你家附近的花店，或者也可以从网上订购，你可以看看有没有特别的花束，比如彩色玫瑰或者百合花，它们会更有特色。'
}
```

**第二回合输出：**

```python
{
  'input': '她喜欢粉色玫瑰，颜色是粉色的。',
  'history': 'Human: 我姐姐明天要过生日，我需要一束生日花束。\nAI: 哇，你姐姐要过生日啊！那太棒了！我建议你去买一束色彩鲜艳的花束，因为这样可以代表你给她的祝福和祝愿。你可以去你家附近的花店，或者也可以从网上订购，你可以看看有没有特别的花束，比如彩色玫瑰或者百合花，它们会更有特色。',
  'response': ' 好的，那粉色玫瑰就是一个很好的选择！你可以买一束粉色玫瑰花束，这样你姐姐会很开心的！你可以在花店里找到粉色玫瑰，也可以从网上订购，你可以根据你的预算，选择合适的数量。另外，你可以考虑添加一些装饰，比如细绳、彩带或者小礼品'
}
```

**第三回合输出：**

```python
{
  'input': '我又来了，还记得我昨天为什么要来买花吗？',
  'history': "System: \nThe human asked the AI for advice on buying a bouquet for their sister's birthday. The AI suggested buying a vibrant bouquet as a representation of their wishes and blessings, and recommended looking for special bouquets like colorful roses or lilies for something more unique.\nHuman: 她喜欢粉色玫瑰，颜色是粉色的。\nAI: 好的，那粉色玫瑰就是一个很好的选择！你可以买一束粉色玫瑰花束，这样你姐姐会很开心的！你可以在花店里找到粉色玫瑰，也可以从网上订购，你可以根据你的预算，选择合适的数量。另外，你可以考虑添加一些装饰，比如细绳、彩带或者小礼品",
  'response': ' 是的，我记得你昨天来买花是为了给你姐姐的生日。你想买一束粉色玫瑰花束来表达你的祝福和祝愿，你可以在花店里找到粉色玫瑰，也可以从网上订购，你可以根据你的预算，选择合适的数量。另外，你可以考虑添加一些装饰，比如细绳、彩带或者小礼品'
}
```

> [!important]
> 
> **智能机制**
> 
> 第二回合完整记录了第一回合对话，但在第三回合察觉到前两轮对话已超出 300 字节，就把早期对话加以总结（System 部分），以节省 Token 资源。

## 优缺点分析

|**优点**|**缺点**|
|---|---|
|通过总结可以回忆起较早的互动  <br>有缓冲区确保不会错过最近的互动信息  <br>提供大量灵活性  <br>在节省 Token 方面具有竞争力|对于较短的对话会增加 Token 数量|

> [!important]
> 
> **推荐使用**
> 
> ConversationSummaryBufferMemory 是目前唯一可以回忆起较早互动并完整存储最近互动的记忆类型，在大多数场景下是一个很好的选择。

---

# 总结

## 四种记忆机制对比

[![](https://static001.geekbang.org/resource/image/a0/c0/a06b5db35405b74yy317de917eacbdc0.jpg?wh=1660x640)](https://static001.geekbang.org/resource/image/a0/c0/a06b5db35405b74yy317de917eacbdc0.jpg?wh=1660x640)

四种记忆机制对比表

|**记忆类型**|**核心特点**|**适用场景**|
|---|---|---|
|ConversationBufferMemory|完整保存所有对话历史|对话轮次少，需要完整上下文|
|ConversationBufferWindowMemory|只保留最近 k 轮对话|只需要最近上下文，对 Token 敏感|
|ConversationSummaryMemory|总结所有对话历史|长对话，需要压缩历史信息|
|ConversationSummaryBufferMemory|混合模式：近期完整+早期总结|平衡信息完整性和 Token 消耗|

## Token 消耗趋势分析

[![](https://static001.geekbang.org/resource/image/c5/ea/c56yyd7eb61637687de448512yy426ea.png?wh=3676x1478)](https://static001.geekbang.org/resource/image/c5/ea/c56yyd7eb61637687de448512yy426ea.png?wh=3676x1478)

当对话轮次逐渐增加时，各种记忆机制对 Token 的消耗数量（估算）

## 核心观察

> [!important]
> 
> **Token 消耗趋势**
> 
> - **ConversationSummaryBufferMemory** 和 **ConversationSummaryMemory**: 在对话轮次较少时可能浪费一些 Token，但多轮对话后 Token 的节省逐渐体现出来
> 
> - **ConversationBufferWindowMemory**: 对 Token 的节省最为直接，但会完全遗忘 k 轮之前的对话内容
> 
> - **ConversationBufferMemory**: Token 消耗线性增长，长对话成本高

---

# 思考题

> [!important]
> 
> **问题 1**: 场景选择
> 
> 假设你在客服聊天机器人中告知客户："亲，我的记忆能力有限，只能记住和你的最近 10 次对话哦。如果我忘了之前的对话，请你体谅我。" 有了这样的预设，你会为你的 ChatBot 选择哪种记忆机制？

> [!important]
> 
> **问题 2**: 参数调试
> 
> 尝试改变 ConversationBufferWindowMemory 中的 k 值，并增加对话轮次，看看记忆效果。

> [!important]
> 
> **问题 3**: 阈值实验
> 
> 尝试改变 ConversationSummaryBufferMemory 中的 max_token_limit 值，看看记忆效果。

---

# 延伸阅读

- **代码**: [ConversationBufferMemory 的实现细节](https://github.com/langchain-ai/langchain/blob/master/libs/langchain/langchain/memory/buffer.py)

- **代码**: [ConversationSummaryMemory 的实现细节](https://github.com/langchain-ai/langchain/blob/master/libs/langchain/langchain/memory/summary.py)

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

课程总结