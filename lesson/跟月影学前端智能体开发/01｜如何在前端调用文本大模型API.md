> [!important]
>
> 原文链接：[极客时间](https://time.geekbang.org/column/article/868006)

---

[![](https://static001.geekbang.org/resource/image/ff/yy/ffc5666607f1de1ee4de43fa97df92yy.png)](https://static001.geekbang.org/resource/image/ff/yy/ffc5666607f1de1ee4de43fa97df92yy.png)

01｜如何在前端调用文本大模型API

你好，我是月影。

这一节课，我们先来了解如何通过调用 API 的方式来使用最基础的文本大模型。

由于几乎所有开放给用户使用的大模型服务都提供 HTTP 协议的 API，所以对于前端工程师来说，使用大模型最简单的入门方式其实就是直接调用由服务平台提供的 API。

由于各种不同类型的大模型和不同服务平台的 API 略有差异，我们也无法穷尽，所以这节课我们主要了解 **DeepSeek** 和 **Coze** 这两个通用文本大模型服务的前端使用方法，以及不同的调用方式。

因为是课程的第一部分，所以内容不会太过于深入细节，但是在这一讲中，我们将通过实战操作，来熟悉大模型的 API 调用方法、数据协议和格式，为后续深入学习打下基础。

---

## 使用 DeepSeek Platform

要说最近国内哪个大模型得到最多人关注，那毫无疑问应该是 DeepSeek，它不仅以极低的成本实现了和行业巨头相媲美的推理能力和性能，而且最近发布的深度推理 R1 模型在性能和效果上都表现极其优越，它的团队还将模型训练中的技术创新全部公开，促进了技术社区之间的深入交流与协同创新。

实际上在 DeepSeek v3 和 R1 推出的近一年之前，我的业务中就在部分使用它，因为它极低廉的价格和不错的推理能力，也因为它提供了非常好用的官方 API 平台，所以它对我们这些 AI 应用创业者非常友好。

好，让我们言归正传，来看看作为前端工程师，应当如何使用 DeepSeek 官方 API。

### 注册与获取 API Key

DeepSeek 官方 API 平台是 [platform.deepseek.com](http://platform.deepseek.com)，我们可以用手机号注册或者微信登录。登录后，就能进入 API 后台：

[![](https://static001.geekbang.org/resource/image/92/b5/92a04cd74ac5fdc1e97d74584cc304b5.jpg?wh=935x524)](https://static001.geekbang.org/resource/image/92/b5/92a04cd74ac5fdc1e97d74584cc304b5.jpg?wh=935x524)

DeepSeek API 后台主页

在这里，我们需要注意两个信息：

**① 余额信息**：决定了还有多少 token 剩余量。根据文档，DeepSeek 目前的价格如下：

[![](https://static001.geekbang.org/resource/image/02/c0/024bf73db0f81cba81b9a809f3d983c0.png?wh=915x343)](https://static001.geekbang.org/resource/image/02/c0/024bf73db0f81cba81b9a809f3d983c0.png?wh=915x343)

DeepSeek 模型定价

> [!important]
>
> **什么是 Token？** Token 是模型用来表示自然语言文本的基本单位，通常一个中文词语或一个英文单词、数字或符号计为一个 token。在每次 API 调用成功后，我们可以通过返回结果的 `usage` 得到 token 的消耗量。

**② API Keys**：应用调用 API 的许可凭证。我们可以点击左侧菜单来创建、查看和管理它。

[![](https://static001.geekbang.org/resource/image/37/76/37f21446fb88aa303cc2daafbc03c876.png?wh=991x379)](https://static001.geekbang.org/resource/image/37/76/37f21446fb88aa303cc2daafbc03c876.png?wh=991x379)

API Keys 管理页面

### 创建项目并调用 API

接下来我们就从最简单的做起，从浏览器端调用 DeepSeek API。因为它支持 HTTPS 协议的接口，API 调用 URL 是 `[https://api.deepseek.com/chat/completions](https://api.deepseek.com/chat/completions)`。

让我们用 Trae 创建一个项目，写一个简单的页面。

[![](https://static001.geekbang.org/resource/image/fe/b4/fef70136bd945f38e036e2f21f104eb4.png?wh=893x734)](https://static001.geekbang.org/resource/image/fe/b4/fef70136bd945f38e036e2f21f104eb4.png?wh=893x734)

Trae 创建项目

Trae 的 AI Builder 自动创建的项目结构如下：

[![](https://static001.geekbang.org/resource/image/67/9b/67e903370b489f157ef1284884ff619b.png?wh=1246x656)](https://static001.geekbang.org/resource/image/67/9b/67e903370b489f157ef1284884ff619b.png?wh=1246x656)

项目结构

项目创建完毕后，别忘了分别修改项目目录下的 `index.html` 文件以及 `script.js` 文件：

**index.html**

```html
<h1>Hello Deepseek!</h1>
<div id="reply">thinking…</div>
<script type="module" src="script.js"></script>
```

**script.js**

```jsx
const endpoint = 'https://api.deepseek.com/chat/completions';

const headers = {
  'Content-Type': 'application/json',
  Authorization: `Bearer ${import.meta.env.VITE_DEEPSEEK_API_KEY}`
};

const payload = {
  model: 'deepseek-chat',
  messages: [
    { role: "system", content: "You are a helpful assistant." },
    { role: "user", content: "你好 Deepseek" }
  ],
  stream: false,
};

const response = await fetch(endpoint, {
  method: 'POST',
  headers: headers,
  body: JSON.stringify(payload)
});

const data = await response.json();
document.getElementById('reply').textContent = data.choices[0].message.content;
```

同时在项目目录下创建 `.env.local` 文件，其中 `sk-xxxxxxxx` 为你在 DeepSeek Platform 中创建的 API Key：

```jsx
VITE_DEEPSEEK_API_KEY=sk-xxxxxxxxx
```

运行代码，等待几秒，你大概会得到如下输出：

[![](https://static001.geekbang.org/resource/image/da/07/da0dc5e2b0ccb3411e812b7da06ca607.png?wh=445x341)](https://static001.geekbang.org/resource/image/da/07/da0dc5e2b0ccb3411e812b7da06ca607.png?wh=445x341)

运行结果

> [!important]
>
> 如果你没有看到如上图的结果，请检查项目目录下是否有 `vite.config.ts` 文件。如果没有，你在 Trae 中用 `Command+U`（macOS）或 `Ctrl+U`（Windows）唤起 Builder 对话框，输入"帮我初始化 vite 配置"，然后再重启服务运行代码。

### 代码解析

来看一下 `script.js` 这个文件的关键部分。

**1. Endpoint 与 Headers**

我们声明 `endpoint` 变量为 `[https://api.deepseek.com/chat/completions](https://api.deepseek.com/chat/completions)`，这是 DeepSeek 的 API 调用 URL。通过 `headers` 变量设置 HTTP Headers。

根据 API 鉴权规范，我们需要将 API Key 放在 `Authorization` 请求头字段中传给服务器以完成权限验证。由于请求是通过 HTTPS 加密传输的，所以不用担心 API Key 被第三方窃取。

**2. 请求体（Payload）**

```json
{
  "model": "deepseek-chat",
  "messages": [
    { "role": "system", "content": "You are a helpful assistant." },
    { "role": "user", "content": "你好 Deepseek" }
  ],
  "stream": false
}
```

- `**model**`：指定要调用的模型类型。DeepSeek Platform 支持两个模型：

    - `deepseek-chat`：基础模型（目前版本 v3）

    - `deepseek-reasoner`：深度思考模型（目前版本 r1），推理能力更强，响应速度较慢，价格更贵

- `**messages**`：发送给大模型的具体消息，每条消息包含：

    - `role`：枚举值 `system`（系统提示词）、`user`（用户消息）、`assistant`（AI 应答）

    - `content`：具体的消息文本内容

    - `user` 和 `assistant` 消息必须成对，最后一条消息必须是 `user` 消息

- `**stream**`：`false` 表示标准 HTTP 方式传输而非流式传输（下节课详细展开）

**3. 发送请求与处理响应**

```jsx
const response = await fetch(endpoint, {
  method: 'POST',
  headers: headers,
  body: JSON.stringify(payload)
});
const data = await response.json();
```

当数据从大模型 API 服务返回后，完整的 API 响应数据大致如下：

```json
{
  "id": "91e192ff-5adf-4955-92bb-5ac8fe9d3c22",
  "object": "chat.completion",
  "created": 1739870580,
  "model": "deepseek-chat",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "你好！有什么我可以帮助你的吗？"
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 12,
    "completion_tokens": 8,
    "total_tokens": 20,
    "prompt_tokens_details": {
      "cached_tokens": 0
    },
    "prompt_cache_hit_tokens": 0,
    "prompt_cache_miss_tokens": 12
  },
  "system_fingerprint": "fp_3a5770e1b4"
}
```

我们关注的数据主要是 `choices` 字段，其中 `choices.message.content` 就是 AI 返回的文本响应内容：

```jsx
document.getElementById('reply').textContent
  = data.choices[0].message.content;
```

此外，还可以通过 `usage` 字段得到消耗的 token 数量，从而计算调用费用。

这样我们就完成了一次最简单的 DeepSeek 大模型 API 调用。是不是很简单呢？

---

## 使用 Coze

接下来，我们介绍另一个平台——**Coze**。

Coze（扣子）是由字节跳动推出的一款 AI 机器人和智能体创建平台，旨在帮助用户快速构建、调试和优化 AI 聊天机器人应用程序。

> 严格来说，Coze 不同于 DeepSeek Platform，因为它不仅提供 API，更重要的是集成了创建智能体和 AI 应用机器人的能力。API 是底层，智能体和 AI 机器人可以理解为上层应用，在后续的课程里，我们会详细了解它们的区别。

但是在这一节课中，我们先不用管这些区别，重点来看一下如何使用 Coze 的 API 来生成文本。

### 创建智能体

首先在 [coze.cn](http://coze.cn) 完成注册，进入 Coze 控制台，选择 **工作空间 > 个人空间 > 项目开发**，然后点击创建，选择创建智能体。

[![](https://static001.geekbang.org/resource/image/ab/d7/ab5931564386c2cdb89ca628906e71d7.png?wh=719x427)](https://static001.geekbang.org/resource/image/ab/d7/ab5931564386c2cdb89ca628906e71d7.png?wh=719x427)

创建 Coze 智能体

智能体名称中，我们输入"通用智能体 for API"，点击确认按钮完成创建。

[![](https://static001.geekbang.org/resource/image/83/1d/83319fc0663a008037432c9744edb21d.png?wh=480x530)](https://static001.geekbang.org/resource/image/83/1d/83319fc0663a008037432c9744edb21d.png?wh=480x530)

命名智能体

Coze 智能体的系统提示词支持模板变量，我们在人设与回复逻辑中只输入一个变量 `prompt`，模型选择 **豆包 1.5 Pro 32k**。

[![](https://static001.geekbang.org/resource/image/b8/d6/b865214958b9c59d1b366f44ebcae0d6.png?wh=1111x652)](https://static001.geekbang.org/resource/image/b8/d6/b865214958b9c59d1b366f44ebcae0d6.png?wh=1111x652)

设置人设与模型

### 发布为 API

接着点发布按钮，选择发布平台只勾选 **发布为 API**。

[![](https://static001.geekbang.org/resource/image/8b/c7/8bc55934a551c4f9d400b8d7d232b0c7.png?wh=1032x539)](https://static001.geekbang.org/resource/image/8b/c7/8bc55934a551c4f9d400b8d7d232b0c7.png?wh=1032x539)

发布配置

继续点发布按钮完成发布。

> [!important]
>
> **获取 bot_id**：发布完成后，从浏览器地址栏获取。地址栏类似于 `[https://www.coze.cn/space/.../bot/7473317995184865307](https://www.coze.cn/space/.../bot/7473317995184865307)`，其中最后一串数字 `7473317995184865307` 就是 `bot_id`。

### 创建个人访问令牌

选择左侧菜单中的 **扣子 API > 授权**，切换到"个人访问令牌"，点击添加新令牌：

[![](https://static001.geekbang.org/resource/image/85/74/85ec255b99ed8ef0b07ce6ce1f79b174.png?wh=561x413)](https://static001.geekbang.org/resource/image/85/74/85ec255b99ed8ef0b07ce6ce1f79b174.png?wh=561x413)

创建个人访问令牌

### 调用 Coze API

在 Trae 中创建一个新的 Web 项目 Coze API。添加 `.env.local` 文件：

```jsx
VITE_API_KEY=pat_kTWhBZtBNYhE2xdGshu2Ukeq7z71**********
VITE_BOT_ID=7473317995184865307
```

**index.html**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Coze API</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
  <h1>Hello Coze!</h1>
  <div id="reply">thinking…</div>
  <script type="module" src="script.js"></script>
</body>
</html>
```

**script.js**

```jsx
const endpoint = 'https://api.coze.cn/open_api/v2/chat';

const payload = {
  bot_id: import.meta.env.VITE_BOT_ID,
  user: 'yvo',
  query: '你好',
  chat_history: [],
  stream: false,
  custom_variables: {
    prompt: "你是一个AI助手"
  }
};

const response = await fetch(endpoint, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${import.meta.env.VITE_API_KEY}`,
  },
  body: JSON.stringify(payload),
});

const data = await response.json();
document.getElementById('reply').textContent = data.messages[0].content;
```

### Coze API 与 DeepSeek 的差异

Coze API 和 DeepSeek Platform 的调用逻辑基本类似，主要差异在于参数和返回结果：

|参数|说明|与 DeepSeek 的区别|
|---|---|---|
|`bot_id` / `user`|`bot_id` 是创建的智能体 ID，`user` 为任意标识字符串|DeepSeek 无需 bot_id|
|`query` / `chat_history`|当前输入以 `query` 传入，历史消息以 `chat_history` 传入（数组格式类似 DeepSeek 的 `messages`）|DeepSeek 统一使用 `messages` 数组|
|`custom_variables`|Coze 没有 `system` 消息，提示词在人设与回复逻辑中设置，通过模板变量传入|DeepSeek 直接使用 `system` role|

点击运行代码，等待几秒钟，就可以在网页上看到推理结果：

[![](https://static001.geekbang.org/resource/image/a9/79/a9fe25f019930b31faa41a0906bf6679.png?wh=548x217)](https://static001.geekbang.org/resource/image/a9/79/a9fe25f019930b31faa41a0906bf6679.png?wh=548x217)

Coze API 运行结果

---

## 要点总结

> [!important]
>
> - 以 **DeepSeek Platform** 和 **Coze** 为例，介绍了如何在浏览器端调用文本大模型 API
>
> - 除了 DeepSeek 和 Coze 外，包括月之暗面、智谱清言在内的大部分文本大模型 API 都**兼容 OpenAI 的 API 参数格式**
>
> - 基本上都可以用同样的方式调用，只需要变更 **API Key** 和 **Endpoint** 即可

---

## 课后练习

### 练习一：探索 DeepSeek 参数

DeepSeek API 还有一些配置参数会影响大模型内容的生成，比较常用的参数比如 `temperature`，它的设定会影响内容输出的随机性。你可以在 DeepSeek Platform 中详细浏览文档，并通过修改上面的例子动手实践，学习这些参数的作用和效果。

### 练习二：尝试 Moonshot API

常用的文本大模型除了 DeepSeek 和 Coze 外还有很多选择。比如月之暗面的大模型 Moonshot，在多模态（支持视觉模型）和处理长文本方面表现比较不错。月之暗面也提供了 [Moonshot AI 开放平台](https://platform.moonshot.cn/)，你可以完成注册并根据文档练习调用 Moonshot API，体验它和 DeepSeek 有哪些不同。


课程二维码
