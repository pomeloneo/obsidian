# 课程概述

本讲介绍 **Context Engineering**（上下文工程）的核心概念，这是让 AI Agent 成功运行的关键技术。与 Prompt Engineering 相比，Context Engineering 更关注如何**自动化管理**输入内容，避免上下文过载。

> [!important]
> 
> **核心理念**：当语言模型输出不如预期时，我们应该优化输入（Context），而不是试图改变模型本身。因为模型训练是复杂的，但优化输入是每个人都可以做的事。

---

# 一、Context Engineering 与 Prompt Engineering 的区别

## 1.1 概念对比

虽然两者本质相同，都是优化语言模型的输入，但关注点不同：

**Prompt Engineering** 侧重于：

- 输入格式的设计

- 寻找"神奇咒语"（特殊提示词）

**Context Engineering** 侧重于：

- 使用语言模型自动化管理上下文

- 动态选择和压缩内容

- 避免上下文过载

## 1.2 关于"神奇咒语"

早期研究发现一些有趣的现象：

**案例1：让模型回答更长**

- 直接要求"答案越长越好"：回应长度 23.76

- 使用神奇咒语"ways ways ways..."：回应长度 34.31

- 但随着模型进化，这种技巧越来越不神奇了

**案例2：Chain of Thought（思维链）**

- GPT-3.5 在 2023年6月：无咒语 72%，"Let's think step by step" 88%

- GPT-3.5 在 2024年2月：无咒语 85%，"Let's think step by step" 89%

> [!important]
> 
> **重要提醒**：请注意，在这堂课中**没有任何模型被训练**——这堂课只训练人类！所有技术都是通过优化输入来提升效果，而不改变模型参数。

---

# 二、Context 里面需要有什么？

一个完整的 Context 通常包含以下七个部分：

## 2.1 User Prompt（用户提示）

包含四个要素：

|要素|说明|示例|
|---|---|---|
|**任务说明**|明确要做什么|"写一封信跟老师说 meeting 要请假"|
|**详细指引**|具体步骤（可选）|"开头先道歉，然后说明理由，最后说之后再找时间更新进度"|
|**额外条件**|限制条件|"100 字以内"|
|**输出风格**|期望的风格|"非常严肃"|

> [!important]
> 
> **关键原则**：语言模型不会读心术！你需要提供充分的前提和背景信息。

**提供前提的重要性示例**：

- ❌ 直接问："水中的动物是什么？"

- ✅ 提供背景："这是在泰国曼谷的运河上拍的照片，水中的动物是什么？"

## 2.2 给范例（In-context Learning）

通过提供示例让模型理解任务模式。

**经典案例：GPT-3 翻译任务**

```jsx
Translate English to French:
sea otter => loutre de mer
peppermint => menthe poivrée
plush girafe => girafe peluche
cheese => ?
```

**重要发现**：

- Gemini 1.5 能够从整本语法书中学习翻译一个濒危语言（Kalamang）

- 研究表明："几乎所有改进都来自书中的平行例子，而非语法解释"

- 这个过程称为 **In-context Learning**（模型参数并未改变）

## 2.3 System Prompt（系统提示）

定义 AI 的基本人格和行为规范。

**Claude Opus 4.1 的 System Prompt（长达 2516 词！）包含：**

- **基本身份与产品资讯**："The assistant is Claude, created by Anthropic"

- **使用说明与限制**：如何使用 API、功能边界

- **互动态度与用户回馈**：如何处理用户不满

- **安全与禁止事项**：不提供制造武器的信息

- **回应风格与格式**："Claude never starts its response with 'good question'"

- **知识与事实性**：知识截止日期

- **自我定位与哲学原则**：不声称自己是人类或有意识

- **错误处理与互动细节**：被纠正时如何反应

## 2.4 Dialogue History（短期记忆）

对话历史会被加入 context，使模型能够记住之前的对话内容。

**示例对话**：

- 用户："你知道隔壁老王是谁吗？"

- AI："隔壁老王是中文网络文化中的一个常见幽默角色..."

- 用户："他是法老王，别忘了"

- AI："收到，隔壁老王 = 法老王，记住了 😎"

- 用户："你知道隔壁老王是谁吗？"（新问题）

- AI："隔壁老王，法老王，天下无敌王 😎"

**注意**：以上对话**并没有训练模型**，只是将历史加入了输入。

## 2.5 Long-term Memory（长期记忆）

2024年9月后，ChatGPT 等服务推出了跨对话的长期记忆功能。

**功能特点**：

- 系统会记住你在不同对话中提到的个人信息

- 即使开启新对话，也能记住之前的偏好和背景

- 例如：记住你的职业、研究领域、个人偏好等

## 2.6 来自其他资料源的相关资讯（RAG）

**RAG（Retrieval Augmented Generation，检索增强生成）**

工作流程：

1. 用户提出问题/任务

1. 系统从网络或数据库**搜寻**相关资讯

1. 将搜寻结果作为**额外资讯**加入 Context

1. 语言模型基于这些资讯生成回答

**实际应用**：

- ChatGPT 可以轻易搭配搜索引擎使用

- 查询实时信息、最新资料

- 补充模型训练数据中没有的知识

> [!important]
> 
> **经典翻车案例**：Google AI Overview 曾建议在披萨上加 1/8 杯无毒胶水来增加粘性——这就是检索到错误信息导致的问题！

## 2.7 Tool Use（工具使用）

让语言模型能够调用外部工具获取信息或执行操作。

**基本原理**：

```jsx
用户问："2025年3月10日下午2:00，高雄气温如何？"

→ 模型输出：<tool>Temperature('高雄', '2025.03.10 14:00')</tool>
→ 系统执行工具，返回：<output>摄氏32度</output>
→ 模型继续生成："2025年3月10日下午2:00，高雄的气温为摄氏32度。"
```

**工具使用的关键**：

- System Prompt 中需要说明如何使用所有工具

- 提供每个工具的使用范例

- 模型输出特定格式的指令来调用工具

**高级形态：Computer Use**

语言模型可以直接使用鼠标和键盘操控电脑！

- Anthropic 的 Claude、OpenAI 的 Operator 都支持此功能

- 模型会看到屏幕画面，然后决定：
    
    - 键盘输入什么内容
    
    - 移动鼠标到哪个位置
    
    - 点击鼠标左键或右键
    

- **革命性意义**：人类能用电脑做的事情，语言模型也能做！

## 2.8 Reasoning（推理过程）

模型自己产生的思考过程，用户可以选择看或不看（甚至不能看）。

**运作方式**：

```jsx
问题输入 
→ 【内部思考】
   "我们先看A解法... 验证一下... 恩，不对
    我们再试B解法... 验证一下... 好像是对的
    还可以尝试C解法... 看起来不好"
→ 输出给用户："使用 B 方法来解题，答案是..."
```

**代表产品**：

- ChatGPT o1 系列

- DeepSeek R1 系列

- Gemini Deep Think

**作用**：

- 规划解题步骤

- 尝试多种方案

- 自我验证和纠错

---

# 三、为什么 AI Agent 时代需要 Context Engineering

## 3.1 什么是 AI Agent？

**三种使用 AI 的方式对比**：

|类型|特点|使用场景|
|---|---|---|
|**一般使用**|一问一答，单次交互|日常对话、简单查询|
|**Agentic Workflow**|按照固定 SOP 执行多步骤|批改作业：1.检查相关性 → 2.给予分数 → 3.分数检查|
|**AI Agent**|自己决定解决问题步骤，灵活调整计划|解决复杂研究问题、自主规划任务|

## 3.2 AI Agent 的运作机制

**核心循环**：Goal（目标）→ Action（行动）→ Observation（观察）→ 调整 → 继续...

```jsx
用户目标 → AI Agent → 使用工具 → 观察结果 → 调整策略 → 继续行动
            ↑_______________|（用人类语言提供反馈）
```

**从 LLM 的角度看 Agent**：

实际上 Agent 一直都在做**文字接龙**！

```jsx
[sys prompt] [obs 1] [action 1] [obs 2] [action 2] [obs 3] [action 3] ...
     ↓          ↓         ↓          ↓         ↓          ↓
    LLM  →    LLM   →   LLM   →    LLM   →   LLM   →   LLM
```

AI Agent 倚靠的是语言模型**现有的能力**，没有额外训练。

## 3.3 运行 AI Agent 的核心挑战：输入过长

随着 Agent 执行任务，Context 会不断增长：

```jsx
[sys prompt] [obs 1] [action 1] ... [obs 9999] → ?????
                                                    ↓
                                                  爆了！
```

**问题1：Context Window 的演进**

- GPT-1（2018）：512 tokens

- GPT-3.5（2022）：16K tokens

- Claude 2.1（2023）：200K tokens

- Gemini 1.5 Pro（2024）：2M tokens（可容纳整套哈利波特+魔戒系列！）

**问题2：能读 ≠ 能读懂**

> [!important]
> 
> 能读上百万个 token，并不代表能读"懂"上百万个 token！

**实验证据**：

1. **RAG 的困境**：搜寻资料越多，效果先提升后下降
    
    - 2K-8K tokens：资料越多结果越好
    
    - 16K+ tokens：资料太多，模型"看不下去"
    

1. **Lost in the Middle**：模型比较记得开头和结尾的内容
    
    - 答案在第1个文档：准确率 ~75%
    
    - 答案在第10个文档：准确率 ~55%
    
    - 答案在第20个文档：准确率 ~63%（稍微回升）
    

1. **Lost in the Conversation**：多轮对话中，模型表现会下降
    
    - 单轮对话：准确率 ~80%
    
    - 多轮对话（模糊需求）：准确率显著下降
    

1. **Context Rot（上下文腐化）**：重复内容会降低性能
    
    - 简单任务"复制以下内容：apple apple apple..."
    
    - 输入越长，准确率越低
    

**结论**：Context Engineering 的核心目标 = **避免塞爆 Context**

---

# 四、Context Engineering 的基本方法

## 4.1 核心思路

> **把需要的放进去，不需要的清出来**

三大常用策略：

1. **Select**（选择）：只放入相关内容

1. **Compress**（压缩）：浓缩信息

1. **Multi-Agent**（多智能体）：任务分工

---

## 4.2 策略一：Select（挑选需要的内容）

### 方法1：RAG with Reranking

**传统 RAG 的问题**：

- 搜索引擎返回大量结果

- 全部放入 Context → 过载

**改进方案：Reranking**

```jsx
用户问题 → 搜索引擎 → 返回20个结果
                         ↓
                    每个结果 → 小型 LLM 评分 → ✓/✗
                         ↓
                    只把 ✓ 的结果放入 Context
```

### 方法2：Tool RAG（挑选工具）

**问题**：如果有上百个工具，把所有工具说明都放入 Context 会爆炸。

**解决方案**：

```jsx
用户问题 → 工具搜索引擎 → 只返回相关的3-5个工具说明 → 放入 Context
```

相关研究：

- ToolRAG（2023）

- 多篇 2025 年的最新研究

### 方法3：Memory RAG（挑选记忆）

**问题**：Agent 运行时间长了，历史记录会非常庞大。

**解决方案**：

```jsx
[obs 1] [action 1] ... [obs 10000] → 不全部放入 Context
                ↓
            存储到外部数据库
                ↓
        当前任务需要时，用 RAG 检索相关历史
```

**经典案例：Generative Agents（生成式智能体）**

25个 AI 在虚拟小镇中生活，每个 Agent 都有自己的记忆流（Memory Stream）：

- 记录每个时刻的观察和行动

- 需要时检索相关记忆

- 不是把一生的经历都塞进 Context

### 方法4：Provence（出处标注）

不是简单地判断整个文档是否相关，而是：

```jsx
长文档 → 拆分成 sentence 1, 2, 3...
           ↓
      每个句子 → 小型 LLM 判断 → 只保留相关句子
```

更精细的粒度，更高的效率。

---

## 4.3 策略二：Compress（压缩内容）

### 场景1：压缩 Agent 历史

**问题**：

```jsx
[obs 100] [act 100] [obs 101] [act 101] [obs 102] → Context 越来越长
```

**解决方案**：定期摘要

```jsx
[obs 1] ... [obs 100] [act 100]
         ↓ 语言模型摘要
    [history 摘要] [obs 101] [act 101] [obs 102]
```

随着时间推移：

```jsx
[history 1] [history 2] [obs 201] [act 201] ...
     ↓          ↓
  遥远的记忆逐渐被更高层次的摘要替代
```

### 场景2：压缩 Computer Use 的琐碎操作

**问题**：Computer Use 会产生大量细节

```jsx
移动鼠标到 [34, 78] → 点击右键 → 弹出广告 → 移动到 [550, 65] → 点击X → ...
```

**解决方案**：任务完成后压缩

```jsx
一大堆操作细节 → 语言模型摘要 → "A餐厅订位成功，9/19 下午6:00，十人"
```

订位成功后，Context 不需要保留订位的详细过程。

### 高级技巧：摘要 + 外部存储

```jsx
详细历史 → 存储到文件 C:\Users\Document\那年夏天的美好回忆.txt
    ↓
Context 中只保留："历史摘要 + 详细内容请开启该文件"
    ↓
需要时可以通过 Tool Use 读取文件
```

---

## 4.4 策略三：Multi-Agent（多智能体协作）

### 核心思想：分工合作，每个 Agent 的 Context 保持简洁

**Single Agent 的问题**：

```jsx
组织出游 → 规划行程 → 订餐厅 → [与餐厅网页各种互动...] 
  → 订旅馆 → [与旅馆网页各种互动...] → 订好了
  
Context 包含所有细节 → 过载！
```

**Multi-Agent 的解决方案**：

```jsx
Lead Agent:
  组织出游 → 规划行程 → 派遣 Agent1(订餐厅) → 收到"订好了" 
    → 派遣 Agent2(订旅馆) → 收到"订好了" → 完成

Agent 1（专门订餐厅）:
  订餐厅 → [与餐厅网页互动...] → 回报"订好了"
  Context 中只有订餐厅，没有其他事情 ✓

Agent 2（专门订旅馆）:
  订旅馆 → [与旅馆网页互动...] → 回报"订好了"
  Context 中只有订旅馆，没有其他事情 ✓
```

**优势**：

- Lead Agent 的 Context 中没有各种订位细节

- 每个子 Agent 专注于单一任务

- 避免 Context 过载

**实际应用：ChatDev**

一个用 Multi-Agent 开发软件的系统：

- CEO Agent：负责设计

- CTO Agent：负责编码

- Programmer Agent：具体实现

- Reviewer Agent：代码审查

- Tester Agent：测试

每个 Agent 只关注自己阶段的任务，Context 保持简洁。

### Multi-Agent 效果实验

以撰写 overview paper 为例：

**方式A**：单一 Agent 读取3篇论文并综合写作 → Context 巨大

**方式B**：

1. Agent 1 读论文1 → 写摘要1

1. Agent 2 读论文2 → 写摘要2

1. Agent 3 读论文3 → 写摘要3

1. Lead Agent 读3个摘要 → 综合成最终报告

**实验结果**（LangChain 研究）：

- Single Agent：任务复杂度提升时性能骤降

- Multi-Agent (Supervisor)：性能较稳定

- Multi-Agent (Swarm)：表现最佳且最稳定

---

# 五、课程总结

## 5.1 Context 的七大组成部分

1. ✅ **User Prompt**：任务说明、指引、条件、风格

1. ✅ **范例**：In-context Learning，示例比解释更有效

1. ✅ **System Prompt**：人格、行为规范、安全限制

1. ✅ **Dialogue History**：短期对话记忆

1. ✅ **Long-term Memory**：跨对话的长期记忆

1. ✅ **RAG**：从外部资料源检索的相关资讯

1. ✅ **Tool Use & Reasoning**：工具使用记录和推理过程

→ **结果**：Context 会非常长！

## 5.2 AI Agent 时代的挑战

- Agent 需要长时间运行，历史记录不断累积

- 工具使用产生大量琐碎操作记录

- 多轮交互导致 Context 膨胀

- 模型虽然能"读"百万 token，但不一定能"读懂"

## 5.3 Context Engineering 三大策略

|策略|方法|应用场景|
|---|---|---|
|**Select**|RAG + Reranking  <br>Tool RAG  <br>Memory RAG  <br>Provence|从大量资料/工具/历史中挑选相关内容|
|**Compress**|摘要历史记录  <br>压缩操作细节  <br>分层摘要|Agent 长时间运行  <br>Computer Use 操作|
|**Multi-Agent**|任务分工  <br>专业化分工  <br>层级管理|复杂任务  <br>需要多领域知识|

## 5.4 关键要点回顾

> [!important]
> 
> **核心目标**：避免塞爆 Context
> 
> **核心理念**：把需要的放进去，不需要的清出来
> 
> **核心原则**：AI Agent 倚靠的是语言模型现有的文字接龙能力

## 5.5 延伸学习资源

- 📺 [让 AI Agent 成功运行的关键技术](https://youtu.be/M2Yg1kwPpts?si=Dw3UvnKQTITxNdci)

- 📺 [深度思考的大型语言模型](https://youtu.be/bJFtcwLSNxI?si=hT-nKkFEEd-zJypH)

- 💻 [Tool Use 概念解说范例程式](https://colab.research.google.com/drive/1t347cQEyMikpHUHV_ap83A-mq9PMSl3O?usp=sharing)

- 🔧 [Gemini CLI](https://github.com/google-gemini/gemini-cli)

- 📊 [StreamBench 项目](https://stream-bench.github.io/)

- 🏢 [ChatDev 开源项目](https://github.com/OpenBMB/ChatDev)

---

**课程金句** 💬

> "请注意：语言模型不会读心术！"

> "模型应该要随时使出全力，怎么可以要求思考才思考……"

> "叫你不要想『白熊』，反而特别容易想『白熊』"