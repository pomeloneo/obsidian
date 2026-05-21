原文链接：https://time.geekbang.org/column/article/699400

---

[![](https://static001.geekbang.org/resource/image/34/17/34c42af86fdd2f1c3f3b5086c9ae8517.jpg)](https://static001.geekbang.org/resource/image/34/17/34c42af86fdd2f1c3f3b5086c9ae8517.jpg)

你好，我是黄佳，欢迎来到 LangChain 实战课！

在我们开始正式的学习之前，先做一些基本知识储备。虽然大语言模型的使用非常简单，但是如果我们通过 API 来进行应用开发，那么还是有些基础知识应该先了解了解，比如什么是大模型，怎么安装 LangChain，OpenAI 的 API 有哪些类型，以及常用的开源大模型从哪里下载等等。

---

## 什么是大语言模型

大语言模型是一种人工智能模型，通常使用深度学习技术，比如神经网络，来理解和生成人类语言。这些模型的"大"在于它们的参数数量非常多，可以达到数十亿甚至更多，这使得它们能够理解和生成高度复杂的语言模式。

你可以将大语言模型想象成一个巨大的预测机器，其训练过程主要基于"猜词"：给定一段文本的开头，它的任务就是预测下一个词是什么。模型会根据大量的训练数据（例如在互联网上爬取的文本），试图理解词语和词组在语言中的用法和含义，以及它们如何组合形成意义。它会通过不断地学习和调整参数，使得自己的预测越来越准确。

[![](https://static001.geekbang.org/resource/image/57/e5/5730e6debb8c1a0876f79814c0fb78e5.png?wh=744x478)](https://static001.geekbang.org/resource/image/57/e5/5730e6debb8c1a0876f79814c0fb78e5.png?wh=744x478)

语言模型预测下一个词的示意图

比如我们给模型一个句子："今天的天气真"，模型可能会预测出"好"作为下一个词，因为在它看过的大量训练数据中，"今天的天气真好"是一个常见的句子。这种预测并不只基于词语的统计关系，还包括对上下文的理解，甚至有时能体现出对世界常识的认知，比如它会理解到，人们通常会在天气好的时候进行户外活动。因此也就能够继续生成或者说推理出相关的内容。

> [!important]
> 
> **注意**：大语言模型并不完全理解语言，它们没有人类的情感、意识或理解力。它们只是通过复杂的数学函数学习到的语言模式，一个概率模型来做预测，所以有时候它们会犯错误，或者生成不合理甚至偏离主题的内容。

咱们当然还是主说 LangChain。LangChain 是一个全方位的、基于大语言模型这种预测能力的应用开发工具，它的灵活性和模块化特性使得处理语言模型变得极其简便。不论你在何时何地，都能利用它流畅地调用语言模型，并基于语言模型的"预测"或者说"推理"能力开发新的应用。

[![](https://static001.geekbang.org/resource/image/62/0c/6259a17134fd5a080fc3d9856a08050c.png?wh=813x226)](https://static001.geekbang.org/resource/image/62/0c/6259a17134fd5a080fc3d9856a08050c.png?wh=813x226)

LangChain 的 Logo：会说话的鹦鹉 + 链条

LangChain 的预构建链功能，就像乐高积木一样，无论你是新手还是经验丰富的开发者，都可以选择适合自己的部分快速构建项目。对于希望进行更深入工作的开发者，LangChain 提供的模块化组件则允许你根据自己的需求定制和创建应用中的功能链条。

> [!important]
> 
> LangChain 支持 **Python** 和 **JavaScript** 两个开发版本，我们这个教程中全部使用 Python 版本进行讲解。

---

## 安装 LangChain

LangChain 的基本安装特别简单：

```bash
pip install langchain
```

这是安装 LangChain 的最低要求。这里我要提醒你一点，LangChain 要与各种模型、数据存储库集成，比如说最重要的 OpenAI 的 API 接口，比如说开源大模型库 HuggingFace Hub，再比如说对各种向量数据库的支持。默认情况下，是没有同时安装所需的依赖项。

也就是说，当你 `pip install langchain` 之后，可能还需要 `pip install openai`、`pip install chroma`（一种向量数据库）……

> [!important]
> 
> **安装 LangChain 时包括常用的开源 LLM（大语言模型）库：**
> 
> ```bash
> pip install langchain[llms]
> ```
> 
> 安装完成之后，还需要更新到 LangChain 的最新版本，这样才能使用较新的工具：
> 
> ```bash
> pip install --upgrade langchain
> ```

如果你想从源代码安装，可以克隆存储库并运行：

```bash
pip install -e .
```

### 📚 学习资源推荐

我个人觉得非常好的学习渠道也在这儿分享给你：

- **LangChain 的 GitHub 社区**非常活跃，你可以在这里找到大量的教程和最佳实践，也可以和其他开发者分享自己的经验和观点。

- **LangChain 也提供了详尽的 API 文档**，这是你在遇到问题时的重要参考。不过呢，我觉得因为 LangChain 太新了，有时你可能会发现文档中有一些错误。在这种情况下，你可以考虑更新你的版本，或者在官方平台上提交一个问题反馈。

当我遇到问题，我通常会在 LangChain 的 GitHub 开一个 Issue，很快就可以得到解答。

[![](https://static001.geekbang.org/resource/image/ff/a8/ff014c517a428cc970e26a34b700c2a8.png?wh=2072x1678)](https://static001.geekbang.org/resource/image/ff/a8/ff014c517a428cc970e26a34b700c2a8.png?wh=2072x1678)

在 LangChain GitHub 提交的 Issue 得到解答

跟着 LangChain 其快速的更新步伐，你就能在这个领域取得显著的进步。

---

## OpenAI API

下面我想说一说 OpenAI 的 API。

关于 ChatGPT 和 GPT-4，我想就没有必要赘言了，网上已经有太多资料了。但是要继续咱们的 LangChain 实战课，你需要对 OpenAI 的 API 有进一步的了解。因为，**LangChain 本质上就是对各种大模型提供的 API 的套壳**，是为了方便我们使用这些 API，搭建起来的一些框架、模块和接口。

因此，要了解 LangChain 的底层逻辑，需要了解大模型的 API 的基本设计思路。而目前接口最完备的、同时也是最强大的大语言模型，当然是 OpenAI 提供的 GPT 家族模型。

[![](https://static001.geekbang.org/resource/image/41/e4/413abcbb7c08bd0a2655a15368b980e4.png?wh=3840x2093)](https://static001.geekbang.org/resource/image/41/e4/413abcbb7c08bd0a2655a15368b980e4.png?wh=3840x2093)

OpenAI API 概览

当然，要使用 OpenAI API，你需要先用科学的方法进行注册，并得到一个 API Key。

[![](https://static001.geekbang.org/resource/image/20/bf/205151183f71bdd86c25c01f99e248bf.png?wh=1429x737)](https://static001.geekbang.org/resource/image/20/bf/205151183f71bdd86c25c01f99e248bf.png?wh=1429x737)

OpenAI API Key 获取界面

有了 OpenAI 的账号和 Key，你就可以在面板中看到各种信息，比如模型的费用、使用情况等。下面的图片显示了各种模型的访问数量限制信息。其中，**TPM** 和 **RPM** 分别代表 tokens-per-minute、requests-per-minute。也就是说，对于 GPT-4，你通过 API 最多每分钟调用 200 次、传输 40000 个字节。

[![](https://static001.geekbang.org/resource/image/66/f3/66e055f3c48b4bc3e11ffe0e85a5c7f3.png?wh=2229x1576)](https://static001.geekbang.org/resource/image/66/f3/66e055f3c48b4bc3e11ffe0e85a5c7f3.png?wh=2229x1576)

OpenAI 各模型的访问限制信息

### 🔑 两类核心模型

这里，我们需要重点说明的两类模型，就是图中的 **Chat Model** 和 **Text Model**。这两类 Model，是大语言模型的代表。当然，OpenAI 还提供 Image、Audio 和其它类型的模型，目前它们不是 LangChain 所支持的重点，模型数量也比较少。

> **补充说明**：gpt-3.5-turbo-0613 代表 ChatGPT 在 2023 年 6 月 13 号的一个快照，而 gpt-3.5-turbo-16k 则代表这个模型可以接收 16K 长度的 Token，而不是通常的 4K。（注意：传输的字节越多，花钱也越多）

上面这两种模型，提供的功能类似，都是接收对话输入（input，也叫 prompt），返回回答文本（output，也叫 response）。但是，它们的调用方式和要求的输入格式是有区别的，这个我们等下还会进一步说明。

---

### 📝 调用 Text 模型

下面我们用简单的代码段说明 Text 模型（GPT3.5 之前的版本）的调用方式。

**第 1 步**：先注册好你的 API Key。

**第 2 步**：用 `pip install openai` 命令来安装 OpenAI 库。

**第 3 步**：导入 OpenAI API Key。

导入 API Key 有多种方式，其中之一是通过下面的代码：

```python
import os
os.environ["OPENAI_API_KEY"] = '你的Open API Key'
```

OpenAI 库就会查看名为 `OPENAI_API_KEY` 的环境变量，并使用它的值作为 API 密钥。

也可以像下面这样先导入 OpenAI 库，然后指定 `api_key` 的值：

```python
import openai
openai.api_key = '你的Open API Key'
```

> [!important]
> 
> **安全提醒**：把 Key 直接放在代码里面的方法最不可取，因为你一不小心共享了代码，密钥就被别人看到了，他就可以使用你的 GPT-4 资源！建议你给自己的 OpenAI 账户设个上限，比如每月 10 美元。

**更好的方法**是在操作系统中定义环境变量，比如在 Linux 系统的命令行中使用：

```bash
export OPENAI_API_KEY='你的Open API Key'
```

或者，你也可以考虑把环境变量保存在 `.env` 文件中，使用 `python-dotenv` 库从文件中读取它，这样也可以降低 API 密钥暴露在代码中的风险。

**第 4 步**：导入 OpenAI 库，并创建一个 Client。

```python
from openai import OpenAI
client = OpenAI()
```

**第 5 步**：指定 gpt-3.5-turbo-instruct（也就是 Text 模型）并调用 completions 方法，返回结果。

```python
response = client.completions.create(
    model="gpt-3.5-turbo-instruct",
    temperature=0.5,
    max_tokens=100,
    prompt="请给我的花店起个名"
)
```

在使用 OpenAI 的文本生成模型时，你可以通过一些参数来控制输出的内容和样式。这里我总结为了一些常见的参数：

[![](https://static001.geekbang.org/resource/image/34/c3/34aaeaff93368c3c3596c12523c1ccc3.jpg?wh=3434x3607)](https://static001.geekbang.org/resource/image/34/c3/34aaeaff93368c3c3596c12523c1ccc3.jpg?wh=3434x3607)

OpenAI Text 模型常见参数说明

**第 6 步**：打印输出大模型返回的文字。

```python
print(response.choices[0].text.strip())
```

当你调用 OpenAI 的 `Completion.create` 方法时，它会返回一个响应对象，该对象包含了模型生成的输出和其他一些信息。这个响应对象是一个字典结构，包含了多个字段。

在使用 Text 模型（如 text-davinci-003）的情况下，响应对象的主要字段包括：

[![](https://static001.geekbang.org/resource/image/4c/ce/4cb717e0258971c7e92dace9c4d8f2ce.jpg?wh=1406x634)](https://static001.geekbang.org/resource/image/4c/ce/4cb717e0258971c7e92dace9c4d8f2ce.jpg?wh=1406x634)

Text 模型响应对象字段说明

`choices` 字段是一个列表，因为在某些情况下，你可以要求模型生成多个可能的输出。每个选择都是一个字典，其中包含以下字段：

- **text**：模型生成的文本

- **finish_reason**：模型停止生成的原因，可能的值包括 `stop`（遇到了停止标记）、`length`（达到了最大长度）或 `temperature`（根据设定的温度参数决定停止）

所以，`response.choices[0].text.strip()` 这行代码的含义是：从响应中获取第一个（如果在调用大模型时，没有指定 n 参数，那么就只有唯一的一个响应）选择，然后获取该选择的文本，并移除其前后的空白字符。这通常是你想要的模型的输出。

**输出结果：**

```jsx
心动花庄、芳华花楼、轩辕花舍、簇烂花街、满园春色
```

不错。下面，让我们再来调用 Chat 模型（GPT-3.5 和 GPT-4）。

---

### 💬 调用 Chat 模型

整体流程上，Chat 模型和 Text 模型的调用是类似的，只是前面加了一个 `chat`，然后输入（prompt）和输出（response）的数据格式有所不同。

**示例代码：**

```python
response = client.chat.completions.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": "You are a creative AI."},
        {"role": "user", "content": "请给我的花店起个名"},
    ],
    temperature=0.8,
    max_tokens=60
)
```

这段代码中，除去刚才已经介绍过的 `temperature`、`max_tokens` 等参数之外，有两个专属于 Chat 模型的概念：**消息** 和 **角色**！

#### 消息 (Messages)

消息就是传入模型的提示。此处的 `messages` 参数是一个列表，包含了多个消息。每个消息都有一个 `role`（可以是 system、user 或 assistant）和 `content`（消息的内容）。系统消息设定了对话的背景（你是一个很棒的智能助手），然后用户消息提出了具体请求（请给我的花店起个名）。模型的任务是基于这些消息来生成回复。

#### 角色 (Roles)

在 OpenAI 的 Chat 模型中，`system`、`user` 和 `assistant` 都是消息的角色。每一种角色都有不同的含义和作用：

在使用 Chat 模型生成内容后，返回的响应（response）会包含一个或多个 `choices`，每个 `choices` 都包含一个 `message`。每个 `message` 也都包含一个 `role` 和 `content`。

**一个典型的 response 对象：**

```json
{
  "id": "chatcmpl-2nZI6v1cW9E3Jg4w2Xtoql0M3XHfH",
  "object": "chat.completion",
  "created": 1677649420,
  "model": "gpt-4",
  "usage": {"prompt_tokens": 56, "completion_tokens": 31, "total_tokens": 87},
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "你的花店可以叫做\"花香四溢\"。"
      },
      "finish_reason": "stop",
      "index": 0
    }
  ]
}
```

**各字段含义：**

[![](https://static001.geekbang.org/resource/image/93/bd/934aaf3e187de074348198e0b0d307bd.jpg?wh=1408x927)](https://static001.geekbang.org/resource/image/93/bd/934aaf3e187de074348198e0b0d307bd.jpg?wh=1408x927)

Chat 模型响应对象字段说明

这就是 response 的基本结构，其实它和 Text 模型返回的响应结构也是很相似，只是 `choices` 字段中的 `Text` 换成了 `Message`。你可以通过解析这个对象来获取你需要的信息。例如，要获取模型的回复，可使用 `response['choices'][0]['message']['content']`。

---

### ⚖️ Chat 模型 vs Text 模型

Chat 模型和 Text 模型都有各自的优点，其适用性取决于具体的应用场景。

相较于 Text 模型，Chat 模型的设计更适合处理对话或者多轮次交互的情况。这是因为它可以接受一个消息列表作为输入，而不仅仅是一个字符串。这个消息列表可以包含 system、user 和 assistant 的历史信息，从而在处理交互式对话时提供更多的上下文信息。

**Chat 模型的主要优点：**

- **对话历史的管理**：通过使用 Chat 模型，你可以更方便地管理对话的历史，并在需要时向模型提供这些历史信息。例如，你可以将过去的用户输入和模型的回复都包含在消息列表中，这样模型在生成新的回复时就可以考虑到这些历史信息。

- **角色模拟**：通过 system 角色，你可以设定对话的背景，给模型提供额外的指导信息，从而更好地控制输出的结果。当然在 Text 模型中，你在提示中也可以为 AI 设定角色，作为输入的一部分。

然而，对于简单的单轮文本生成任务，使用 Text 模型可能会更简单、更直接。例如，如果你只需要模型根据一个简单的提示生成一段文本，那么 Text 模型可能更适合。从上面的结果看，Chat 模型给我们输出的文本更完善，是一句完整的话，而 Text 模型输出的是几个名字。这是因为 ChatGPT 经过了对齐（基于人类反馈的强化学习），输出的答案更像是真实聊天场景。

好了，我们对 OpenAI 的 API 调用，理解到这个程度就可以了。毕竟我们主要是通过 LangChain 这个高级封装的框架来访问 OpenAI。

---

## 通过 LangChain 调用 Text 和 Chat 模型

最后，让我们来使用 LangChain 来调用 OpenAI 的 Text 和 Chat 模型，完成了这两个任务，我们今天的课程就可以结束了！

### 🔷 调用 Text 模型

```python
import os
os.environ["OPENAI_API_KEY"] = '你的Open API Key'

from langchain.llms import OpenAI

llm = OpenAI(
    model="gpt-3.5-turbo-instruct",
    temperature=0.8,
    max_tokens=60,
)

response = llm.predict("请给我的花店起个名")
print(response)
```

**输出：**

```jsx
花之缘、芳华花店、花语心意、花风旖旎、芳草世界、芳色年华
```

这只是一个对 OpenAI API 的简单封装：先导入 LangChain 的 OpenAI 类，创建一个 LLM（大语言模型）对象，指定使用的模型和一些生成参数。使用创建的 LLM 对象和消息列表调用 OpenAI 类的 `__call__` 方法，进行文本生成。生成的结果被存储在 response 变量中。没有什么需要特别解释之处。

---

### 🔶 调用 Chat 模型

```python
import os
os.environ["OPENAI_API_KEY"] = '你的Open API Key'

from langchain.chat_models import ChatOpenAI

chat = ChatOpenAI(
    model="gpt-4",
    temperature=0.8,
    max_tokens=60
)

from langchain.schema import (
    HumanMessage,
    SystemMessage
)

messages = [
    SystemMessage(content="你是一个很棒的智能助手"),
    HumanMessage(content="请给我的花店起个名")
]

response = chat(messages)
print(response)
```

这段代码也不难理解，主要是通过导入 LangChain 的 `ChatOpenAI` 类，创建一个 Chat 模型对象，指定使用的模型和一些生成参数。然后从 LangChain 的 schema 模块中导入 LangChain 的 `SystemMessage` 和 `HumanMessage` 类，创建一个消息列表。消息列表中包含了一个系统消息和一个人类消息。你已经知道系统消息通常用来设置一些上下文或者指导 AI 的行为，人类消息则是要求 AI 回应的内容。之后，使用创建的 chat 对象和消息列表调用 ChatOpenAI 类的 `__call__` 方法，进行文本生成。生成的结果被存储在 response 变量中。

**输出：**

```jsx
content='当然可以，叫做"花语秘境"怎么样？'
additional_kwargs={} example=False
```

> [!important]
> 
> 从响应内容"当然可以，叫做'花语秘境'怎么样？"不难看出，**GPT-4 的创造力真的是胜过 GPT-3**，她给了我们这么有意境的一个店名，比我自己起的"易速鲜花"好多了。

另外，无论是 `langchain.llms` 中的 OpenAI（Text 模型），还是 `[langchain.chat](http://langchain.chat)``_models` 中的 ChatOpenAI（Chat 模型），其返回的结果 response 变量的结构，都比直接调用 OpenAI API 来得简单一些。这是因为，LangChain 已经对大语言模型的 output 进行了解析，只保留了响应中最重要的文字部分。

---

## 总结时刻

好了，今天课程的内容不少，我希望你理解 OpenAI 从 Text 模型到 Chat 模型的进化，以及什么时候你会选用 Chat 模型，什么时候会选用 Text 模型。另外就是这两种模型的最基本调用流程，掌握了这些内容，我们就可以继续后面的学习。

另外，大语言模型可不是 OpenAI 一家独大，知名的大模型开源社群 HuggingFace 网站上面提供了很多开源模型供你尝试使用。就在我写这节课的时候，Meta 的 Llama-2 最受热捧，而且通义千问（Qwen）则刚刚开源。这些趋势，你点击下面的图片就看得到。

[![](https://static001.geekbang.org/resource/image/05/0e/05f5c16f3d908b4b0a16958e28842e0e.png?wh=3885x1981)](https://static001.geekbang.org/resource/image/05/0e/05f5c16f3d908b4b0a16958e28842e0e.png?wh=3885x1981)

HuggingFace 上当前下载较多的开源大语言模型

> [!important]
> 
> **两点提醒**
> 
> 1. 这个领域进展太快，当你学这门课程的时候，流行的开源模型肯定变成别的了
> 
> 1. 这些新的开源模型，LangChain 还不一定提供很好的接口，因此通过 LangChain 来使用最新的开源模型可能不容易
> 
> 不过 LangChain 作为最流行的 LLM 框架，新的开源模型被封装进来是迟早的事情。而且，LangChain 的框架也已经定型，各个组件的设计都基本固定了。

---

## 思考题

最后给你留几个有难度的思考题，有些题目你可能现在没有答案，但是我希望你带着这些问题去继续学习后续课程。

### 思考题 1

从今天的两个例子看起来，使用 LangChain 并不比直接调用 OpenAI API 来得省事？而且也仍然需要 OpenAI API 才能调用 GPT 家族模型。那么 LangChain 的核心价值在哪里？至少从这两个示例中没看出来。针对这个问题，你仔细思考思考。

> **提示**：这个问题没有标准答案，仁者见仁智者见智，等学完了课程，我们可以再回过头来回答一次。

### 思考题 2

LangChain 支持的可绝不只有 OpenAI 模型，那么你能否试一试 HuggingFace 开源社区中的其它模型，看看能不能用。

> **提示**：你要选择 Text-Generation、Text-Text Generation 和 Question-Answer 这一类的文本生成式模型。

```python
from langchain import HuggingFaceHub
llm = HuggingFaceHub(model_id="bigscience/bloom-1b7")
```

### 思考题 3

上面我提到了生成式模型，那么，大语言模型除了文本生成式模型，还有哪些类别的模型？比如说有名的 Bert 模型，是不是文本生成式的模型？

> **提示**：如果你没有太多 NLP 基础知识，建议你可以看一下我的专栏《零基础实战机器学习》和公开课《ChatGPT 和预训练模型实战课》。

期待在留言区看到你的思考，如果你觉得内容对你有帮助，也欢迎分享给有需要的朋友！最后如果你学有余力，可以进一步学习下面的延伸阅读。

---

## 延伸阅读

- **LangChain 官方文档**（[Python 版](https://python.langchain.com/)）（[JavaScript 版](https://js.langchain.com/)），这是你学习专栏的过程中，有任何疑惑都可以随时去探索的知识大本营。我个人觉得，目前 LangChain 的文档还不够体系化，有些杂乱，讲解也不大清楚。但是，这是官方文档，会维护得越来越好。

- **OpenAI API 官方文档**，深入学习 OpenAI API 的地方。

- **HuggingFace 官方网站**，玩开源大模型的好地方。

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)