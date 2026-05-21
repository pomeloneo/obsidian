> [!important]
> 
> 原文链接：[极客时间](https://time.geekbang.org/column/article/868684)

---

[![](https://static001.geekbang.org/resource/image/2f/1f/2f1a72a11fdf5fcb0afe35f7f8befc1f.jpeg)](https://static001.geekbang.org/resource/image/2f/1f/2f1a72a11fdf5fcb0afe35f7f8befc1f.jpeg)

03｜如何在前端调用图像大模型API

你好，我是月影。

在前面的课程中，我们主要学习了文本大模型 API 的使用。文本大模型是最常用的基础大模型，而在我们实际的应用开发中，不仅可以使用 AI 生成文本，还可以绘图、创作视频、处理语音以及识别图像。

在这一节课里，我们主要来探讨一些我自己实践用过的、表现不错的图像大模型产品。

---

## 使用 FLUX 模型

虽然在 AI 绘图领域，最广为人知的是 Stable Diffusion。但是，在我过去的应用实践中，比较了很多易用且经济实惠的图像生成模型，发现由 Black Forest Labs 团队推出的 **FLUX 系列模型**效果比较好，而且它用起来也比较简单。

### 注册与获取 API Key

首先在官网 [api.us1.bfl.ai](http://api.us1.bfl.ai) 注册账号（支持邮箱注册），然后进入后台。后台功能非常简单，直接点击 **Add Key** 创建一个 API Key 就可以了。

[![](https://static001.geekbang.org/resource/image/cb/fc/cb10737fc2b28ffda778c875a14ebcfc.png?wh=700x553)](https://static001.geekbang.org/resource/image/cb/fc/cb10737fc2b28ffda778c875a14ebcfc.png?wh=700x553)

FLUX API 后台

> [!important]
> 
> 图像创建成功需要消耗一定的 **Credits**，使用不同版本模型的价格不同，具体价格可以在 API 文档中查看。

### 创建项目

用 Trae 创建一个 Vue 项目 `[Flux.ai](http://Flux.ai)` `Demo 1`，在项目目录下添加 `.env.local`：

```jsx
VITE_API_KEY=9007ab9a-****-****-****-ec0be19423ba
```

### 实现 App.vue

修改 `App.vue`，代码如下：

```jsx
<script setup lang="ts">
import { ref } from 'vue';

const prompt = ref('A lovely rabbit');
const imgUrl = ref('');
const progress = ref('0%');

const generateImage = async () => {
  const endpoint = `https://api.bfl.ml/v1`;
  const modelName = 'flux-dev';

  const payload = {
    prompt: prompt.value,
    width: 1024,
    height: 1024,
    steps: 40,
    prompt_upsampling: true,
    seed: 42,
    guidance: 3,
    sampler: 'dpmpp_2m',
    safety_tolerance: 2,
  };

  const headers = {
    'Content-Type': 'application/json',
    'x-key': import.meta.env.VITE_API_KEY,
  };

  const res = await fetch(`${endpoint}/${modelName}`, {
    headers,
    method: 'POST',
    body: JSON.stringify(payload),
  });

  const id = (await res.json()).id;
  const resultUrl = `${endpoint}/get_result?id=${id}`;
  imgUrl.value = 'https://res.bearbobo.com/resource/upload/a3IZyOsZ/loading-giaz5ycpd7j.gif';

  do {
    await new Promise((resolve) => setTimeout(resolve, 100));
    const result = await fetch(resultUrl);
    const resultJson = await result.json();

    if (resultJson.status === 'Pending') {
      const progressValue = resultJson.progress;
      if (progressValue) {
        progress.value = `${Math.round(progressValue * 100)}%`;
      }
      continue;
    }

    const sample = resultJson.result?.sample;
    if (sample) {
      imgUrl.value = sample;
    } else {
      imgUrl.value = 'https://res.bearbobo.com/resource/upload/vNg4ALJv/6659895-ox36cbkajrr.png';
    }
    break;
  } while (1);
};
</script>

<template>
  <div class="container">
    <div>
      <label>Prompt </label>
      <button @click="generateImage">Generate</button>
    </div>
    <div class="progress">
      <div :style="{width: progress}"></div>
    </div>
    <div class="output">
      <img :src="imgUrl" />
    </div>
  </div>
</template>

<style scoped>
.input {
  width: 100%;
  height: 2rem;
  font-size: 1rem;
  padding: 0.5rem;
  border: 1px solid \#ccc;
  border-radius: 0.5rem;
}
.progress {
  width: 100%;
  height: 0.1rem;
  margin: .4rem 0;
  background: \#ccc;
}
.progress > div {
  background: \#c00;
  height: 100%;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: start;
  height: 100vh;
}
.output {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 200px;
  border: 1px solid \#ccc;
}
.output > img {
  width: 100%;
}
</style>
```

这样我们就创建好了一个简单的文生图的 AI 应用。你可以输入和修改提示词，给出你想要的 AI 生成的任何风格图片，点击生成按钮，等待图片生成结果就可以了。

[![](https://static001.geekbang.org/resource/image/92/dd/92a91b87c4cb6def8a583459c35c17dd.gif?wh=492x508)](https://static001.geekbang.org/resource/image/92/dd/92a91b87c4cb6def8a583459c35c17dd.gif?wh=492x508)

FLUX 文生图效果演示

### 代码解析

核心逻辑就是 `generateImage` 这个函数。

**1. 设置请求参数**

```jsx
const endpoint = `https://api.bfl.ml/v1`;
const modelName = 'flux-dev';

const payload = {
  prompt: prompt.value,
  width: 1024,
  height: 1024,
  steps: 40,
  prompt_upsampling: true,
  seed: 42,
  guidance: 3,
  sampler: 'dpmpp_2m',
  safety_tolerance: 2,
};
```

常用参数含义：

|参数|说明|
|---|---|
|`prompt`|图片文本描述提示词|
|`width` / `height`|图像宽高，单位像素|
|`steps`|模型"去噪/细化"的迭代步数，步数越多质量越高，但计算时间更长|
|`prompt_upsampling`|是否对输入文本进行上采样以提高分辨率|
|`seed`|随机种子，相同种子 + 相同参数 = 相同图像|
|`guidance`|控制模型遵循文本描述的严格程度，值越高越忠于提示词|
|`sampler`|采样器算法，`dpmpp_2m` 是一种扩散模型采样器，不同采样器影响质量、风格和效率|
|`safety_tolerance`|控制生成内容的安全性容忍度|

除了这些参数外还有其他选项，有兴趣可以查看 Black Forest Labs 的官方文档。

**2. 请求头与鉴权**

```jsx
const headers = {
  'Content-Type': 'application/json',
  'x-key': import.meta.env.VITE_API_KEY,
};
```

FLUX 和前面的文本大模型类似，通过在请求头中发送 API Key 鉴权，不同点在于前面是设置 HTTP 标准的 `Authorization` 字段，而这里是设置 `x-key` 扩展字段。

**3. 异步读写分离**

由于绘图是耗时较长的过程，FLUX 将生成图片请求设计为**读写分离的异步操作**——分为两个接口：一个发起绘图，一个查询状态。

```jsx
// 发起绘图操作，获取任务 ID
const res = await fetch(`${endpoint}/${modelName}`, {
  headers,
  method: 'POST',
  body: JSON.stringify(payload),
});
const id = (await res.json()).id;

// 通过任务 ID 轮询查询状态
const resultUrl = `${endpoint}/get_result?id=${id}`;

do {
  await new Promise((resolve) => setTimeout(resolve, 100));
  const result = await fetch(resultUrl);
  const resultJson = await result.json();

  if (resultJson.status === 'Pending') {
    // 更新进度条
    const progressValue = resultJson.progress;
    if (progressValue) {
      progress.value = `${Math.round(progressValue * 100)}%`;
    }
    continue;
  }

  // 获取生成的图片 URL
  const sample = resultJson.result?.sample;
  if (sample) {
    imgUrl.value = sample;
  }
  break;
} while (1);
```

在每一轮查询中，先等待 100 毫秒，然后查询状态。状态为 `Pending` 时更新进度条；状态完成时读取 `result.sample` 获得生成图片的临时 URL。在实际业务中，应将图片保存到自己的服务器或 CDN。

---

## 使用可灵 AI

除了 FLUX 外，国内也有不错的图像大模型，比如智谱清言的 CogView 模型，以及快手的**可灵 AI**，这些模型在我的 AI 应用产品中也会被使用。

### 注册与密钥管理

首先在 [klingai.kuaishou.com](http://klingai.kuaishou.com) 注册可灵 AI，登录后点击左下角"开发者平台"进入控制台。点击左侧菜单"密钥管理"创建密钥。

> [!important]
> 
> 可灵 AI 的密钥由一对字符串构成：**AccessKey ID** 和 **AccessKey Secret**。它采用 **JSON Web Token** 加密方式，通过这对密钥生成 Token，再利用 Token 进行鉴权，安全性更高。

### 搭建鉴权服务

首先用 Trae 创建一个 Vue 项目，配置 `.env.local`：

```jsx
ACCESS_KEY_ID=8f617**********fcf9
ACCESS_KEY_SECRET=36092**********94c5
```

在终端安装依赖：

```bash
pnpm i dotenv express jsonwebtoken
```

添加 `server.js` 文件：

```jsx
import * as dotenv from 'dotenv'
import express from 'express';
import jwt from 'jsonwebtoken';

dotenv.config({
  path: ['.env.local', '.env']
});

const accessKeyId = process.env.ACCESS_KEY_ID;
const accessKeySecret = process.env.ACCESS_KEY_SECRET;

const app = express();
const port = 3000;

async function authKlingai() {
  const headers = {
    algorithm: 'HS256',
  };
  const now = Math.floor(Date.now() / 1000);
  const payload = {
    iss: accessKeyId,
    exp: now + 1800,
    nbf: now - 5,
  };
  const token = jwt.sign(payload, accessKeySecret, headers);
  return token;
}

app.get('/jwt-auth', async (req, res) => {
  const token = await authKlingai();
  res.send(token);
});

app.listen(port, () => {
  console.log(`Server is running on port ${port}`);
});
```

### 配置 Vite 代理

在 `vite.config.ts` 中添加 server 配置项：

```tsx
server: {
  allowedHosts: true,
  port: 4399,
  proxy: {
    '/api': {
      target: 'http://localhost:3000',
      secure: false,
      rewrite: path => path.replace(/^\/api/, ''),
    },
    '/klingai': {
      target: 'https://api.klingai.com',
      changeOrigin: true,
      rewrite: path => path.replace(/^\/klingai/, ''),
    }
  },
}
```

这样前端可以通过 `/api/jwt-auth` 获得 token。另外由于可灵 AI 不支持前端跨域请求，所以也做了请求转发。

### 实现 App.vue

```jsx
<script setup lang="ts">
import { ref } from 'vue';

const prompt = ref('A lovely rabbit');
const imgUrl = ref('');

const generateImage = async () => {
  const negativeWords = 'Blurry, Bad, Bad anatomy, Bad proportions, Deformed, Disconnected limbs, Disfigured, Extra arms, Extra limbs, Extra hands, Fused fingers, Gross proportions, Long neck, Malformed limbs, Mutated, Mutated hands, Mutated limbs, Missing arms, Missing fingers, Poorly drawn hands, Poorly drawn face.';

  const endpoint = `/klingai/v1/images/generations`;
  const token = await (await fetch('/api/jwt-auth')).text();

  const payload = {
    prompt: prompt.value,
    negative_prompt: negativeWords,
    aspect_ratio: '1:1',
  };

  const headers = {
    'Content-Type': 'application/json',
    'Authorization': `Bearer ${token}`,
  };

  const res = await fetch(endpoint, {
    headers,
    method: 'POST',
    body: JSON.stringify(payload),
  });

  if (res.status >= 400) {
    throw new Error(`Non-200 response: ${await res.text()}`);
  }

  const ret: any = await res.json();
  const id = ret.data.task_id;
  const resultUrl = `${endpoint}/${id}`;
  imgUrl.value = 'https://res.bearbobo.com/resource/upload/a3IZyOsZ/loading-giaz5ycpd7j.gif';

  do {
    await new Promise((resolve) => setTimeout(resolve, 100));
    const result = await fetch(resultUrl, { headers });
    const resultJson = await result.json();
    const taskStatus = resultJson.data.task_status;

    if (taskStatus === 'processing' || taskStatus === 'submitted') {
      continue;
    }

    if (taskStatus === 'failed') {
      throw new Error(`Task failed: ${JSON.stringify(resultJson)}`);
    }

    const sample = resultJson.data?.task_result;
    if (sample) {
      imgUrl.value = sample.images[0].url;
    } else {
      imgUrl.value = 'https://res.bearbobo.com/resource/upload/vNg4ALJv/6659895-ox36cbkajrr.png';
    }
    break;
  } while (1);
};
</script>

<template>
  <div class="container">
    <div>
      <label>Prompt </label>
      <button @click="generateImage">Generate</button>
    </div>
    <div class="output">
      <img :src="imgUrl" />
    </div>
  </div>
</template>

<style scoped>
.input {
  width: 100%;
  height: 2rem;
  font-size: 1rem;
  padding: 0.5rem;
  border: 1px solid \#ccc;
  border-radius: 0.5rem;
}
.progress {
  width: 100%;
  height: 0.1rem;
  margin: .4rem 0;
  background: \#ccc;
}
.progress > div {
  background: \#c00;
  height: 100%;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: start;
  height: 100vh;
}
.output {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 200px;
  border: 1px solid \#ccc;
}
.output > img {
  width: 100%;
  max-width: 600px;
}
</style>
```

这样就可以使用可灵 AI 生成图片了：

[![](https://static001.geekbang.org/resource/image/50/8d/50638697f14772384baa7d1751488b8d.gif?wh=550x606)](https://static001.geekbang.org/resource/image/50/8d/50638697f14772384baa7d1751488b8d.gif?wh=550x606)

可灵 AI 生成效果演示

### 与 FLUX 的差异

整体逻辑和 FLUX 类似，关键差异：

- **鉴权**：需要先从 Node.js 服务获取 JWT Token

- **异步轮询**：同样是读写分离，先请求生成接口获取 `task_id`，再轮询查询状态

- **进度信息**：可灵 AI 的轮询接口只返回状态，没有生成进度条

```jsx
// 从 BFF 获取 JWT Token
const token = await (await fetch('/api/jwt-auth')).text();
```

---

## 要点总结

> [!important]
> 
> - 学习了 **FLUX** 和**可灵 AI** 两个图像生成模型的 API 调用方法
> 
> - **鉴权差异**：FLUX 采用简单的 API Key 鉴权；可灵 AI 采用 JWT（JSON Web Token）鉴权，安全性更高
> 
> - **共同设计**：两者都采用了**读写操作分离的异步设计**，通过接口查询状态，可以更灵活地实现前端交互

---

## 课后练习

FLUX 模型支持不同的**采样器（sampler）**，通过配置可以改变生成算法，获得不同的生成效果。你可以研究 FLUX 官方文档，尝试修改 `sampler` 参数，看看会得到怎样的效果。

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)