> [!important]
> 
> 原文链接：[极客时间](https://time.geekbang.org/column/article/874518)

---

[![](https://static001.geekbang.org/resource/image/48/9e/4848bd5bf3cd0628eab554667c65e09e.png)](https://static001.geekbang.org/resource/image/48/9e/4848bd5bf3cd0628eab554667c65e09e.png)

09｜用户体验：如何解决流式传输与JSON结构化的矛盾

你好，我是月影。

在前面的内容里，我们讨论了让大模型输出 JSON 格式数据是一个非常有效的方法。但当我们希望通过**流式传输**减少等待时间时，就会遇到一个问题：

JSON 是一种**封闭的数据结构**，通常以 `{` 开头、`}` 结尾。前端对 JSON 的解析必须等待数据全部传输完成，否则会因数据不完整而报错。这就让流式数据快速响应的特性失效了。

那么有没有办法解决这个问题呢？

---

## JSON 的流式解析

### 现有方案的不足

- **NDJSON 方案**：要求大模型每行输出一个独立 JSON，对输出限制太大，可能影响推理准确性

- **JSONStream 库**：必须事先针对特定结构处理，只能在 Server 端使用，不够通用

### 更好的方案：动态 JSON Parser

我们可以写一个**动态解析 JSON 数据流的 parser**。作者在开源 AI 工作流框架 **Ling** 中实现了这个 JSON parser，可以单独用在项目中。

### 实战：客户端流式 JSON 解析

用 Trae 创建 Vue 项目 `JSON Streaming`，配置 `.env.local`：

```jsx
VITE_API_KEY=sk-qi2**********xbp4
VITE_END_POINT=https://api.moonshot.cn/v1/chat/completions
```

**引入 JSON Parser：** 从 Ling 仓库的 `/src/parser/index.ts` 复制到项目 `/src/lib/json-parser.ts`。

由于 json-parser 依赖 `node:events`，前端需要替换为自定义实现：

```tsx
class EventEmitter {
  private listeners: { [key: string]: ((...args: any[]) => void)[] } = {};

  on(event: string, listener: (...args: any[]) => void) {
    if (!this.listeners[event]) {
      this.listeners[event] = [];
    }
    this.listeners[event].push(listener);
  }

  emit(event: string, ...args: any[]) {
    if (this.listeners[event]) {
      this.listeners[event].forEach(listener => {
        listener(...args);
      });
    }
  }
}
```

json-parser 通过 `data` 事件将增量数据以 `{uri, delta}` 格式传输，需要用 **jsonuri** 库将 uri 解析回 JSON 对象：

```bash
pnpm i jsonuri
```

**App.vue：**

```jsx
<script setup lang="ts">
import { ref } from 'vue';
import { JSONParser } from './lib/json-parser';
import { set, get } from 'jsonuri';

const question = ref('狼来了');
const content = ref('');
const contentParsed = ref({
  story_instruction: '',
  the_whole_story_content: '',
  the_whole_story_translate_to_en: '',
  lessons: []
});

const systemPrompt = `
根据用户输入的主题，用**中文**输出以下JSON格式内容：
{
  "story_instruction": "",
  "the_whole_story_content": "",
  "the_whole_story_translate_to_en": "",
  "lessons": []
}
`;

const update = async () => {
  if (!question) return;
  content.value = "思考中…";

  const endpoint = import.meta.env.VITE_END_POINT;
  const headers = {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${import.meta.env.VITE_API_KEY}`
  };

  const response = await fetch(endpoint, {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
      model: 'moonshot-v1-8k',
      messages: [
        { role: 'system', content: systemPrompt },
        { role: 'user', content: question.value }
      ],
      stream: true,
    })
  });

  const reader = response.body?.getReader();
  const decoder = new TextDecoder();

  const jsonParser = new JSONParser();
  jsonParser.on('data', ({uri, delta}) => {
    console.log(uri, delta);
    const content = get(contentParsed.value, uri);
    set(contentParsed.value, uri, (content || '') + delta);
  });

  let done = false;
  let buffer = '';
  content.value = '';

  while (!done) {
    const { value, done: doneReading } = await (reader?.read() as Promise<{ value: any; done: boolean }>);
    done = doneReading;
    const chunkValue = buffer + decoder.decode(value);
    buffer = '';

    const lines = chunkValue.split('\n').filter((line) => line.startsWith('data:'));
    for (const line of lines) {
      const incoming = line.slice(6);
      if (incoming === '[DONE]') {
        done = true;
        break;
      }
      try {
        const data = JSON.parse(incoming);
        const delta = data.choices[0].delta.content;
        if (delta) {
          content.value += delta;
          jsonParser.trace(delta);
        }
      } catch (ex) {
        buffer += incoming;
      }
    }
  }
}
</script>

<template>
  <div class="container">
    <div>
      <label>输入：</label><input class="input" v-model="question" />
      <button @click="update">提交</button>
    </div>
    <div class="output">
      <textarea>107</textarea>
      <textarea>108</textarea>
    </div>
  </div>
</template>
```

### 核心代码解析

**1. 构建业务数据结构：**

```tsx
const contentParsed = ref({
  story_instruction: '',
  the_whole_story_content: '',
  the_whole_story_translate_to_en: '',
  lessons: []
});
```

**2. 创建 JSONParser 并监听数据：**

```tsx
const jsonParser = new JSONParser();
jsonParser.on('data', ({uri, delta}) => {
  const content = get(contentParsed.value, uri);
  set(contentParsed.value, uri, (content || '') + delta);
});
```

**3. 在流中调用** `**trace**` **动态解析：**

```tsx
const delta = data.choices[0].delta.content;
if (delta) {
  content.value += delta;
  jsonParser.trace(delta);
}
```

### 效果

[![](https://static001.geekbang.org/resource/image/c4/58/c44e3581897feaa9543b495c394ac658.gif?wh=536x736)](https://static001.geekbang.org/resource/image/c4/58/c44e3581897feaa9543b495c394ac658.gif?wh=536x736)

客户端流式 JSON 解析效果

上面的输出框是原始的不完整 JSON 数据，下面的输出框始终保持着**完整的 JSON 格式**，随时可以用来更新 UI。

---

## 流式 JSON 的 SSE 服务

客户端 JSON 动态解析虽然方便，但不够灵活强大。在服务端执行有以下优势：

- 工作流可以直接配置在 Node.js 端

- JSONParser 提供 `string-resolve` 事件，能在 JSON 某个属性解析完成时立即获取完整数据并进行下一步处理

- 可以将数据以 **SSE** 方式返回给前端

### 项目配置

创建项目 `JSON Streaming SSE`，配置 `.env.local`：

```jsx
VITE_API_KEY=sk-qi2oJ**********txbp4
VITE_END_POINT=https://api.moonshot.cn/v1/chat/completions
VITE_AUDIO_APP_ID=5934290469
VITE_AUDIO_ACCESS_TOKEN=c-LRysB**********Ln4N
VITE_AUDIO_CLUSTER_ID=volcano_tts
VITE_AUDIO_VOICE_NAME=en_female_anna_mars_bigtts
```

安装依赖：

```bash
pnpm i dotenv express jsonuri jiti
```

### server.js

```jsx
import * as dotenv from 'dotenv'
import express from 'express';
import { JSONParser } from './lib/json-parser.ts';

dotenv.config({ path: ['.env.local', '.env'] })

const openaiApiKey = process.env.VITE_API_KEY;
const app = express();
const port = 3000;
const endpoint = process.env.VITE_END_POINT;

const systemPrompt = `
你是一位亲子英语启蒙老师，负责设计家庭英语亲子英语例句。
根据用户输入的主题，生成不少于10句英文例句。
输出以下JSON格式内容：
{
  "example_sentences": [
    { "english": "example sentence", "chinese": "例句的中文翻译" },
    ...
  ]
}
`;

app.get('/stream', async (req, res) => {
  res.setHeader('Content-Type', 'text/event-stream');
  res.setHeader('Cache-Control', 'no-cache');
  res.setHeader('Connection', 'keep-alive');
  res.flushHeaders();

  try {
    const response = await fetch(endpoint, {
      method: 'POST',
      headers: { 'Authorization': `Bearer ${openaiApiKey}` },
      body: JSON.stringify({
        model: 'moonshot-v1-8k',
        messages: [
          { role: 'system', content: systemPrompt },
          { role: 'user', content: req.query.question }
        ],
        response_format: { type: "json_object" },
        stream: true,
      })
    });

    if (!response.ok) throw new Error('Failed to fetch from OpenAI');

    const reader = response.body.getReader();
    const decoder = new TextDecoder();
    const jsonParser = new JSONParser({
      autoFix: true,
      onError: (error) => { console.error('JSON Parser Error:', error); }
    });

    jsonParser.on('data', (data) => {
      if (data.uri) res.write(`data: ${JSON.stringify(data)}\n\n`);
    });

    let done = false;
    let buffer = '';

    while (!done) {
      const { value, done: doneReading } = await reader.read();
      done = doneReading;
      const chunkValue = buffer + decoder.decode(value, { stream: true });
      buffer = '';

      const lines = chunkValue.split('\n').filter(line => line.trim() && line.startsWith('data:'));
      for (const line of lines) {
        const incoming = line.slice(6);
        if (incoming === '[DONE]') { done = true; break; }
        try {
          const data = JSON.parse(incoming);
          const delta = data.choices[0].delta.content;
          jsonParser.trace(delta);
        } catch (ex) {
          buffer += incoming;
        }
      }
    }

    res.write('event: end\n');
    res.write('data: [DONE]\n\n');
    res.end();
  } catch (error) {
    console.error('Error fetching from OpenAI:', error);
    res.write('data: Error fetching from OpenAI\n\n');
    res.end();
  }
});

app.listen(port, () => {
  console.log(`Server running on http://localhost:${port}`);
});
```

> [!important]
> 
> JSONParser 是 TypeScript 写的，server.js 是 JS，所以安装了 **jiti** 库，它可以混合运行 TS 和 JS 的服务，用 `jiti server` 启动即可。

配置 `vite.config.js` 转发 server 接口：

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
  },
},
```

### 客户端 App.vue（SSE 版）

```jsx
<script setup lang="ts">
import { ref } from 'vue';
import { set, get } from 'jsonuri';

const question = ref('起床');
const content = ref({
  example_sentences: [],
});

const update = async () => {
  if (!question) return;
  const endpoint = '/api/stream';
  const eventSource = new EventSource(`${endpoint}?question=${question.value}`);

  eventSource.addEventListener("message", function (e: any) {
    const { uri, delta } = JSON.parse(e.data);
    const str = get(content.value, uri);
    set(content.value, uri, (str || '') + delta);
  });

  eventSource.addEventListener('end', () => {
    console.log('传输完成');
    eventSource.close();
  });
}
</script>

<template>
  <div class="container">
    <div>
      <label>输入：</label><input class="input" v-model="question" />
      <button @click="update">提交</button>
    </div>
    <div class="output">
      <div v-for="sentence in content.example_sentences as any" :key="sentence.english">
        <h3>109</h3>
        <p>110</p>
      </div>
    </div>
  </div>
</template>
```

效果：

[![](https://static001.geekbang.org/resource/image/0a/e1/0abe5a8a724c5274bf45916cd50991e1.gif?wh=512x730)](https://static001.geekbang.org/resource/image/0a/e1/0abe5a8a724c5274bf45916cd50991e1.gif?wh=512x730)

SSE 流式 JSON 效果

---

## 并行处理语音合成

接下来为英文内容合成语音，利用 JSONParser 的 `string-resolve` 事件**及时并行处理**语音转换。

### 添加 audio.js

在 `lib` 目录下创建 `audio.js`（语音合成逻辑与前面课程相同）。

### 修改 server.js

引入 `generateAudio` 并添加 `string-resolve` 事件处理：

```jsx
import { generateAudio } from './lib/audio.js';

// ...

const audioPromises = [];

jsonParser.on('string-resolve', ({ uri, delta }) => {
  if (uri.includes('english')) {
    const task = generateAudio(delta);
    audioPromises.push(task);
    task.then((base64data) => {
      const audioUri = uri.replace('english', 'audio');
      res.write(`data: ${JSON.stringify({ uri: audioUri, delta: base64data })}\n\n`)
    });
  }
});

// ... 在流处理完成后

await Promise.all(audioPromises); // 等待音频数据结束
res.write('event: end\n');
res.write('data: [DONE]\n\n');
res.end();
```

> [!important]
> 
> 在 `string-resolve` 事件中，判断 uri 是否包含 `english`，若是则说明当前 delta 是**完整的英文例句**，立即发送给 `generateAudio` 异步处理。由于是异步过程，通过 `Promise.all(audioPromises)` 等待所有音频处理结束后才关闭连接。

### 修改客户端（添加音频播放）

```jsx
<script setup lang="ts">
// ... 添加音频处理函数
function playAudio(audio: string) {
  const audioElement = new Audio(audio);
  audioElement.play();
}

function createBlobURL(base64AudioData: string): string {
  var byteArrays = [];
  var byteCharacters = atob(base64AudioData);
  for (var offset = 0; offset < byteCharacters.length; offset++) {
    var byteArray = byteCharacters.charCodeAt(offset);
    byteArrays.push(byteArray);
  }
  var blob = new Blob([new Uint8Array(byteArrays)], { type: 'audio/mp3' });
  return URL.createObjectURL(blob);
}

// ... 在 message 事件处理中
eventSource.addEventListener("message", function (e: any) {
  let { uri, delta } = JSON.parse(e.data);
  if (uri.includes('audio')) {
    delta = createBlobURL(delta);
  }
  const str = get(content.value, uri);
  set(content.value, uri, (str || '') + delta);
});
</script>

<template>
  <!-- ... 添加播放按钮 -->
  <div v-for="sentence in (content.example_sentences as any)" :key="sentence.english">
    <h3>111
      <img v-if="sentence.audio" width="20px"
        @click="playAudio(sentence.audio)"
        src="https://res.bearbobo.com/resource/upload/9nZenvln/playAudio-l42l4687b8j.png" alt="play" />
    </h3>
    <p>112</p>
  </div>
</template>
```

### 最终效果

[![](https://static001.geekbang.org/resource/image/86/94/86efeab2dcc50bb1538386b2c47a6e94.gif?wh=512x730)](https://static001.geekbang.org/resource/image/86/94/86efeab2dcc50bb1538386b2c47a6e94.gif?wh=512x730)

流式 JSON + 并行语音合成效果

内容生成的同时动态生成音频，点击播放图标即可播放对应语音。

> [!important]
> 
> GitHub 完整代码：[json_streaming_sse](https://github.com/akira-cn/frontend-dev-large-model-era/tree/main/json_streaming_sse)

---

## 要点总结

> [!important]
> 
> - **核心问题**：JSON 是封闭数据结构，流式传输时无法中途解析
> 
> - **解决方案**：使用动态 JSON Parser（来自 Ling 框架），支持增量解析
> 
> - **客户端**：通过 `data` 事件获取 `{uri, delta}` 增量数据，配合 jsonuri 库更新 UI
> 
> - **服务端**：通过 SSE 将解析结果推送给前端，同时利用 `string-resolve` 事件**并行处理**语音合成等异步任务
> 
> - 结构化 JSON 数据的流式处理是实现快速实时响应的 AI 应用的**重要基础**

---

## 课后练习

### 练习一：autoFix 参数

第二个例子中，server 端创建 JSONParser 时传入了 `autoFix` 参数，它的作用是什么？自己实验一下。

### 练习二：data 与 string-resolve 的区别

仔细阅读 JSONParser 代码，理解 `data` 和 `string-resolve` 事件的区别。为什么语音合成要在 `string-resolve` 事件里处理？

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)