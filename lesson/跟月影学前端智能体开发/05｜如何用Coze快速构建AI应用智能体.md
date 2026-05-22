> [!important]
>
> 原文链接：[极客时间](https://time.geekbang.org/column/article/870510)

---

[![](https://static001.geekbang.org/resource/image/ef/7d/ef79610ac7b01a1f3e7f0f0348d07a7d.jpg)](https://static001.geekbang.org/resource/image/ef/7d/ef79610ac7b01a1f3e7f0f0348d07a7d.jpg)

05｜如何用Coze快速构建AI应用智能体

你好，我是月影。

通过之前的学习，我们已经了解了常用类型的大模型 API 如何调用。然而除了大模型 API 调用，我想你一定也经常听到一个名词，叫做"**智能体**"，对应的英文叫做 **Agent**。

那么，究竟大模型和智能体有什么区别呢？

今天这节课，我们就来聊聊智能体的基本概念，看看智能体对于 AI 应用意味着什么，掌握什么时候需要构建智能体，以及如何快速构建 AI 应用智能体。

---

## 什么是智能体和智能体工作流

顾名思义，**智能体（Agent）**是指能够感知环境、做出决策并根据决策采取行动的系统。在 AI 大模型应用中，智能体可以理解为利用大模型核心能力，通过适当的流程编排，构成能够感知、理解、分析环境信息，并根据环境信息（通常是用户输入）和指导信息（通常是提示词）进行综合处理，得到用户需要反馈的独立应用单元。

在这其中，构成智能体主要功能的流程，就叫**智能体的核心工作流**。

### 一个具体的例子

假设我们要设计一个给 6～8 岁孩子讲睡前故事的 AI 应用，需求如下：

- 设定一个故事主题，让 AI 尽可能讲述经典民间故事

- 如果该主题的经典民间故事不存在，让 AI 根据主题编撰

- 内容和语言风格适合 6～8 岁孩子的年龄和认知

- 采用比较亲切的语音将故事念出来

这个智能体需要具备：**搜索引擎能力**、**语音合成能力**、**内容改写和润色能力**。这些能力必须通过合理的工作流编排，才可以最终实现智能体的功能。

[![](https://static001.geekbang.org/resource/image/e7/12/e7286yy8eb5d54137dc7b4281abba612.jpg?wh=4575x585)](https://static001.geekbang.org/resource/image/e7/12/e7286yy8eb5d54137dc7b4281abba612.jpg?wh=4575x585)

睡前故事智能体核心工作流

工作流程：

1. 根据用户输入的主题**分析用户意图**，生成搜索 query

1. 用生成的搜索 query **调用搜索 API**（即 RAG，检索增强生成）

1. 对返回内容进行**整理**，利用整理的内容**编写草稿**

1. 对语言和文字风格进行**检查和润色**

1. 根据输出的文本内容进行**语音合成**

1. 将文本和语音**最终输出**

这个智能体的整体工作流是串行的，还是比较简单的。实际的业务中，还会遇到更复杂的智能体，有可能有多个任务并行处理，后续课程会进一步探索。

---

## 使用 Coze 编排工作流

字节跳动的**扣子（Coze）**平台提供了低代码方式，通过编排工作流来创建智能体的能力。

### 步骤一：创建工作流

进入 Coze 管理后台，选择 **工作空间 > 个人空间 > 资源库**，点击右上角新建资源，选择"工作流"。

[![](https://static001.geekbang.org/resource/image/ff/8b/ff16fa52d19e30cfb7bf4f59fd30068b.png?wh=902x707)](https://static001.geekbang.org/resource/image/ff/8b/ff16fa52d19e30cfb7bf4f59fd30068b.png?wh=902x707)

新建工作流

创建一个工作流 `bedtime_story`，描述为"让 AI 给 6-8 岁孩子讲睡前故事"。点击确认后进入工作流主界面，此时只有"开始"和"结束"两个节点。

[![](https://static001.geekbang.org/resource/image/25/y2/256aff4c4fa8961a4814bc1e2d67ayy2.png?wh=992x818)](https://static001.geekbang.org/resource/image/25/y2/256aff4c4fa8961a4814bc1e2d67ayy2.png?wh=992x818)

工作流初始界面

### 步骤二：添加"改写 query"节点

点击添加节点，选择**大模型节点**：

[![](https://static001.geekbang.org/resource/image/17/38/17d351960fca8de71d8bb35b2dcb9538.png?wh=1032x701)](https://static001.geekbang.org/resource/image/17/38/17d351960fca8de71d8bb35b2dcb9538.png?wh=1032x701)

添加大模型节点

将开始节点的输出接入大模型节点的输入，模型选择"豆包 1.5 Pro"：

[![](https://static001.geekbang.org/resource/image/5e/bb/5ee1973b20886c5166ee8yyb9609ccbb.gif?wh=1140x558)](https://static001.geekbang.org/resource/image/5e/bb/5ee1973b20886c5166ee8yyb9609ccbb.gif?wh=1140x558)

配置大模型节点

配置系统提示词和用户提示词：

[![](https://static001.geekbang.org/resource/image/97/61/974f46yyec77a5d380c1836a4232f361.png?wh=361x581)](https://static001.geekbang.org/resource/image/97/61/974f46yyec77a5d380c1836a4232f361.png?wh=361x581)

提示词配置面板

**系统提示词：**

> 你根据用户输入，分析并拆解出用于搜索的提示词，方便用户搜索需要的原文内容，这些内容用于后续为用户创作儿童故事。

> 分析方法：如果用户原始输入是常见的民间故事主题或者经典预言故事，如三只小猪，狼来了，那么你的目的是查找这些故事的原文，生成方便查找故事原文的query。

> 否则，你应当结合中国历史、文化或者神话传说，生成一些有助于根据原始输入信息搜索到参考资料的query。

> 根据用户输入的提示词，分析用户的意图，输出一组搜索query词，以便让用户更好地搜索内容。

**用户提示词：**

```jsx
98
```

这里用双花括号表示模板变量，`input` 对应模块的输入参数名。

**输出配置：**

[![](https://static001.geekbang.org/resource/image/99/85/99399e98060765da89eyyc367e591f85.png?wh=475x229)](https://static001.geekbang.org/resource/image/99/85/99399e98060765da89eyyc367e591f85.png?wh=475x229)

输出项配置

配置两个输出项：

- `querys`：字符串数组，表示生成的多个搜索项

- `intent`：表示用户意图

> [!important]
>
> `intent` 并不是后续模块要用到的内容，但我们仍然让 AI 输出。这是一个小技巧——让 AI 输出对生成内容有参考价值的字段，实际上是**强化了推理过程中的思考**，有助于生成更高质量的内容。

### 测试第一步

将该节点的输出和结束节点的输入连接，点击"试运行"：

[![](https://static001.geekbang.org/resource/image/0e/aa/0e25d5b09da787470a1f46b96b13e6aa.png?wh=1164x333)](https://static001.geekbang.org/resource/image/0e/aa/0e25d5b09da787470a1f46b96b13e6aa.png?wh=1164x333)

连接结束节点

[![](https://static001.geekbang.org/resource/image/70/21/701f930a57deb0495ab21824cc83bf21.png?wh=795x795)](https://static001.geekbang.org/resource/image/70/21/701f930a57deb0495ab21824cc83bf21.png?wh=795x795)

试运行结果

输入"狼来了"，可以看到运行结果返回了用于进一步搜索的 query 内容。

### 步骤三：添加循环搜索节点

搜索 query 是一个数组，可能返回多个内容，所以需要一个**循环模块**。

选择 **添加节点 > 业务逻辑 > 循环**，将"改写 query"节点输出连接到循环节点输入，设置循环数组参数为前一个节点输出的 `querys`。

[![](https://static001.geekbang.org/resource/image/15/43/15020181148b5b3e6e1a67cd9bc84043.png?wh=1139x470)](https://static001.geekbang.org/resource/image/15/43/15020181148b5b3e6e1a67cd9bc84043.png?wh=1139x470)

循环节点配置

选中"循环体"，添加 **插件 > 必应搜索 > bingWebSearch**，将插件的输入输出与循环体连接，设置输入 `query` 值为循环的输入参数 `input`。

[![](https://static001.geekbang.org/resource/image/4b/5d/4be624ab2dda2d27968e7d382650315d.png?wh=964x587)](https://static001.geekbang.org/resource/image/4b/5d/4be624ab2dda2d27968e7d382650315d.png?wh=964x587)

循环体内搜索插件

切换到循环的配置面板，将输出参数 `output` 的值设置为 `response_for_model`。

### 步骤四：添加"撰写草稿"节点

继续添加大模型节点，模型选择"豆包 1.5 Pro"，将循环节点的输出与它的输入连接：

[![](https://static001.geekbang.org/resource/image/16/c3/16afd0ca24c31e5765e064fa877f56c3.png?wh=915x645)](https://static001.geekbang.org/resource/image/16/c3/16afd0ca24c31e5765e064fa877f56c3.png?wh=915x645)

撰写草稿节点配置

**系统提示词：**

> 你根据参考资料进行整理，撰写儿童故事草稿。

> 注意：儿童故事的内容深浅要符合6-8岁儿童的年龄和理解力，如果是经典故事，尽可能忠于原文，否则可适当自由创作。

**用户提示词：**

```jsx
参考资料：98
```

### 步骤五：添加"润色"节点

继续创建大模型节点，依然采用"豆包 1.5 Pro"。

**系统提示词：**

> 你扮演一位知性而有耐心的温柔大姐姐，正在为你6岁的妹妹讲一个睡前故事。根据用户提供的故事材料，用口语的表达方式，使用简短生动的句子，并以温柔、舒适的语气讲述。为了让故事易于孩子理解，你可以加入互动性问题，比如："你觉得接下来会发生什么？"来吸引孩子的注意力。保持故事简短，时间不超过5分钟。

**用户提示词：**

```jsx
故事材料：98
```

### 步骤六：添加语音合成节点

添加插件节点，搜索语音，添加**官方中文文本转语音**，选择柔美女声。

[![](https://static001.geekbang.org/resource/image/a5/70/a54634fb911c3b1b0a1affd9fe55e670.png?wh=982x610)](https://static001.geekbang.org/resource/image/a5/70/a54634fb911c3b1b0a1affd9fe55e670.png?wh=982x610)

语音合成插件

将润色节点的输出连接到语音合成插件输入，再将语音合成和润色的输出都连接到结束节点，设置输出为 `text` 和 `audio`。

[![](https://static001.geekbang.org/resource/image/d9/8d/d9e416ef178cafc52188a6bd1560c88d.png?wh=1173x694)](https://static001.geekbang.org/resource/image/d9/8d/d9e416ef178cafc52188a6bd1560c88d.png?wh=1173x694)

完整工作流

### 试运行完整工作流

点击"试运行"，输入"狼来了"，等待工作流输出结果，可以查询每一个节点运行后的输入输出。

[![](https://static001.geekbang.org/resource/image/8d/y8/8d117e2abd6128yya888b064c4a5cyy8.png?wh=1174x783)](https://static001.geekbang.org/resource/image/8d/y8/8d117e2abd6128yya888b064c4a5cyy8.png?wh=1174x783)

完整工作流试运行结果

试运行成功后，就可以拿到音频和文本了。

---

## 在 Coze 智能体中使用工作流

有了工作流，创建智能体就非常简单了。

### 发布工作流

先将工作流发布——点击右上角发布按钮，填写发布信息，点击确认即可。

### 创建智能体

回到 **个人空间 > 项目开发**，点击创建按钮，创建智能体"儿童睡前故事"。

[![](https://static001.geekbang.org/resource/image/94/03/941a9c718882054764ca17e84028fb03.png?wh=487x533)](https://static001.geekbang.org/resource/image/94/03/941a9c718882054764ca17e84028fb03.png?wh=487x533)

创建智能体

在智能体编排面板中选择 **技能 > 工作流**，将我们的工作流添加进去。

[![](https://static001.geekbang.org/resource/image/82/f6/82342e340f67f703cb7ce61b6c15a8f6.gif?wh=1194x786)](https://static001.geekbang.org/resource/image/82/f6/82342e340f67f703cb7ce61b6c15a8f6.gif?wh=1194x786)

添加工作流到智能体

配置人设与回复逻辑：

> 根据用户输入的主题，调用bedtime_story工作流给孩子讲睡前故事。

### 测试智能体

[![](https://static001.geekbang.org/resource/image/4a/59/4a73384a7a6179bb140aa563e8fbb259.gif?wh=524x534)](https://static001.geekbang.org/resource/image/4a/59/4a73384a7a6179bb140aa563e8fbb259.gif?wh=524x534)

智能体测试效果

最终，你可以选择把这个智能体发布到豆包或者其他平台，或者像前面的课程那样发布成 API，通过代码来进行调用。

---

## Coze 工作流的优缺点

> [!important]
>
> **优点**
>
> - 低代码平台，能**非常快速**地创建复杂工作流和强大智能体
>
> - 支持流式和非流式两种形式，实现对用户快速响应
>
> - 提供丰富的**生态插件和工具**
>
> - 非常适合作为**产品原型设计和验证平台**

> [!important]
>
> **不足**
>
> - 工作流完全集成在 Coze 平台上，**业务隐私和安全性**受限
>
> - 节点内部调用比较**黑盒**，数据结构级别的优化较难实现
>
> - 实际产品开发时，通常还是通过 **Node.js** 实现自己的业务工作流

> 在业务中，通常会在**原型验证阶段**使用 Coze，真正产品开发时，通过 Node.js 实现自己的业务工作流。只要理解了工作流的原理，用 Node.js 来实现编排工作流并不算太复杂。下一节课会通过实战来学习。

---

## 要点总结

> [!important]
>
> - 学习了**智能体**和**工作流**的概念
>
> - 通过 Coze 平台实践了工作流编排：改写 query → 循环搜索 → 撰写草稿 → 润色 → 语音合成
>
> - 利用 Coze 低代码平台实现智能体的关键在于**理清步骤，设定合理的工作流**
>
> - Coze 非常适合项目初期做原型验证

[![](https://static001.geekbang.org/resource/image/e7/12/e7286yy8eb5d54137dc7b4281abba612.jpg?wh=4575x585)](https://static001.geekbang.org/resource/image/e7/12/e7286yy8eb5d54137dc7b4281abba612.jpg?wh=4575x585)

睡前故事智能体工作流回顾

---

## 课后练习

### 练习一：去掉改写 query 节点

在工作流编排时，最开始设计了一个改写 query 的节点。如果不添加这个节点会有什么问题？尝试修改工作流，把这个节点去掉，采用用户的原始输入进行搜索，看看有什么差别。

### 练习二：输出语音文件

工作流最后的节点生成了 mp3 语音文件，本意是让用户可以下载保存。但智能体在回答时并没有将语音文件放到回答内容里。如何让智能体将这个文件输出给用户？

### 练习三：添加插图节点

如果要给每个故事配一张插图，可以给工作流添加一个绘制插图的节点。尝试修改工作流，添加插图节点，给每个故事配置一个插图。
