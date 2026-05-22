> [!important]
>
> 原文链接：[极客时间](https://time.geekbang.org/column/article/874027)

---

[![](https://static001.geekbang.org/resource/image/5c/74/5c66e4b319674a15b1b4aafe0fa65374.jpg)](https://static001.geekbang.org/resource/image/5c/74/5c66e4b319674a15b1b4aafe0fa65374.jpg)

08｜提示词工程（二）：元提示与动态提示词

你好，我是月影。

在上一节，我们学到了一些基础技巧，来帮助撰写和优化提示词。而在今天这一节课，我们将讨论两个更高级的优化方法：**元提示（Meta-Prompt）**和**动态提示词**。

---

## 如何使用元提示（Meta-Prompt）

"元提示"是一种**让 AI 写提示词**的技巧。顾名思义，就是让一个智能体负责撰写提示词，再将提示词给后续的智能体执行。

这个技巧通常用于不同类型的智能体协作的工作流中。

### 实际案例：AI 生成卡通图标

[![](https://static001.geekbang.org/resource/image/f7/3b/f74e1dfa13c2c8749d5c1a0ed404073b.png?wh=808x1388)](https://static001.geekbang.org/resource/image/f7/3b/f74e1dfa13c2c8749d5c1a0ed404073b.png?wh=808x1388)

波波熊亲子英语小程序界面

这是 AI 产品"波波熊亲子英语"的小程序界面截图。注意每个例句分类目录里都配了一张 AI 生成的图。我们继续使用 [Flux.ai](http://Flux.ai) 来绘图。

### 步骤一：创建 Flux 绘图插件

在 Coze 工作空间中，选择 **资源库 > 添加资源 > 新建插件**。

[![](https://static001.geekbang.org/resource/image/f1/e8/f1f67byyea537yyc2844988a61c805e8.png?wh=1118x1296)](https://static001.geekbang.org/resource/image/f1/e8/f1f67byyea537yyc2844988a61c805e8.png?wh=1118x1296)

新建插件

选择"云侧插件 > 在 Coze IDE 中创建"，进入 IDE 后创建工具。

[![](https://static001.geekbang.org/resource/image/fd/ca/fd6b959acb8d310f171d0c85a7e38aca.png?wh=1116x866)](https://static001.geekbang.org/resource/image/fd/ca/fd6b959acb8d310f171d0c85a7e38aca.png?wh=1116x866)

Coze IDE 创建工具

切换到"元数据"Tab，设置输入参数和输出参数：

[![](https://static001.geekbang.org/resource/image/54/41/54fd5183f44e09b0yye9692d40440e41.png?wh=1842x650)](https://static001.geekbang.org/resource/image/54/41/54fd5183f44e09b0yye9692d40440e41.png?wh=1842x650)

元数据配置

切回"代码"Tab，修改代码：

```tsx
import { Args } from '@/runtime';
import { Input, Output } from "@/typings/flux_http/flux_http";

export async function handler({ input, logger }: Args<Input>): Promise<Output> {
  const endpoint = `https://api.bfl.ml/v1`;
  const modelName = 'flux-dev';

  const headers = {
    'Content-Type': 'application/json',
    'x-key': '<你的flux api key>',
  };

  const payload = {
    prompt: input.prompt,
    width: 1024,
    height: 1024,
    steps: 40,
    prompt_upsampling: true,
    seed: 42,
    guidance: 3,
    sampler: 'dpmpp_2m',
    safety_tolerance: 2,
  };

  const res = await fetch(`${endpoint}/${modelName}`, {
    headers,
    method: 'POST',
    body: JSON.stringify(payload),
  });

  const id = (await res.json()).id;
  const resultUrl = `${endpoint}/get_result?id=${id}`;

  do {
    await new Promise((resolve) => setTimeout(resolve, 100));
    const result = await fetch(resultUrl);
    const resultJson = await result.json();

    if (resultJson.status === 'Pending') {
      continue;
    }

    const sample = resultJson.result?.sample;
    if (sample) {
      return { url: sample };
    } else {
      return { url: 'https://res.bearbobo.com/resource/upload/vNg4ALJv/6659895-ox36cbkajrr.png' };
    }
  } while (1);
};
```

替换 API Key 后点击测试：

[![](https://static001.geekbang.org/resource/image/c3/b2/c3918bb33768a8188770dfd792af50b2.png?wh=762x1270)](https://static001.geekbang.org/resource/image/c3/b2/c3918bb33768a8188770dfd792af50b2.png?wh=762x1270)

测试插件

看到输出结果里的 url，插件功能就完成了，点击发布。

### 步骤二：创建元提示工作流

插件提供了通用的绘图功能，但我们的业务需要**卡通贴纸风格的 icon**，需要类似这样的提示词：

> Cartoon sticker-style icon, pure white background, minimalistic and clean design, showing a cheerful child sitting by a tent or roasting marshmallows over a campfire...

回到资源库，创建工作流：

[![](https://static001.geekbang.org/resource/image/86/8b/86fb96bb2c8b67e26ac193ea7814068b.png?wh=1112x1098)](https://static001.geekbang.org/resource/image/86/8b/86fb96bb2c8b67e26ac193ea7814068b.png?wh=1112x1098)

创建工作流

添加一个**大模型节点**，用来生成绘图提示词：

[![](https://static001.geekbang.org/resource/image/ba/c4/ba774ea862e0ac151ba3baf0c33ee9c4.png?wh=1594x1274)](https://static001.geekbang.org/resource/image/ba/c4/ba774ea862e0ac151ba3baf0c33ee9c4.png?wh=1594x1274)

大模型节点配置

**系统提示词：**

> 这是一个亲子英文学习的平台，教授父母日常家庭亲子英语对话。

> 根据用户输入和背景信息，你的任务是输出适用于midjourney绘图的**英文**提示词。

**用户提示词：**

```jsx
请以"toolu_018FQSWWq9Er5ZnpCvPHStEi"为主题，生成白底、卡通贴纸风格的简单图标。主题是生活场景相关的，比如起床、刷牙、游玩等等。
```

试运行结果：

[![](https://static001.geekbang.org/resource/image/b2/a4/b2byy4ca40c79ca1160f2348170a96a4.png?wh=1492x1076)](https://static001.geekbang.org/resource/image/b2/a4/b2byy4ca40c79ca1160f2348170a96a4.png?wh=1492x1076)

元提示节点试运行

输出的提示词示例：

> A simple white-background cartoon sticker-style icon for the theme of getting up, related to daily life scenes. The icon features a cute child stretching in bed, with a sun peeping through the window, soft colors, and a flat-design style.

### 步骤三：连接 Flux 插件

添加插件节点，选择 **添加节点 > 插件 > 资源库工具**，加入 Flux 绘图插件：

[![](https://static001.geekbang.org/resource/image/a6/07/a6789daf001dd84985b2a1911fcf0107.png?wh=1920x938)](https://static001.geekbang.org/resource/image/a6/07/a6789daf001dd84985b2a1911fcf0107.png?wh=1920x938)

连接 Flux 插件

试运行，输入"起床"，生成的图标：

[![](https://static001.geekbang.org/resource/image/af/25/af1a801e37bc734cfb03405efbaed925.png?wh=1024x1024)](https://static001.geekbang.org/resource/image/af/25/af1a801e37bc734cfb03405efbaed925.png?wh=1024x1024)

生成的卡通图标

> [!important]
>
> 在这个过程中，我们用**豆包模型生成 Flux 模型需要的提示词**，从而让 Flux 模型更好地生成结果。这个模式就是**"元提示"模式**。

---

## 如何使用动态提示词

在有些场景中，我们需要**动态生成提示词**。比如在波波熊亲子英语产品中，生成场景对话时会把当天的日期、节日信息考虑进去。

还有更复杂的场景：针对用户提出的不同问题类型，采用不同的 AI 节点处理，每个节点处理一类特定问题——这种做法叫做**"多专家模型（MoE）"**。

> [!important]
>
> **多专家模型（Mixture of Experts, MoE）** 是一种深度学习架构，通过引入多个专家子模型，根据输入数据选择最合适的专家进行处理。这里我们借鉴了这个叫法，但实际是应用层的技术。

使用动态提示词有多种方法。Coze 智能体支持自定义参数，可以直接传参。而其他平台大部分不提供自定义参数，我们可以用前端熟悉的**模板引擎**技术来实现。

### 实战：About Today

用 Trae 创建 Vue 项目 `About Today`，安装 nunjucks 引擎：

```bash
pnpm i nunjucks
```

配置 `.env.local`：

```jsx
VITE_API_KEY=sk-qi2oJBN**********txbp4
VITE_BASE_URL=https://api.moonshot.cn/v1/chat/completions
VITE_AI_MODEL=moonshot-v1-8k
```

### DatePicker 组件

创建 `src/components/DatePicker.vue`：

```jsx
<script setup lang="ts">
import { ref, onMounted } from "vue";

const selectedDate = ref('');
const props = defineProps({
  value: { type: String, default: '' },
});

onMounted(() => {
  selectedDate.value = props.value;
});

const emit = defineEmits(["dateUpdate"]);
const handleDateChange = () => {
  emit("dateUpdate", selectedDate.value);
};
</script>

<template>
  <div>
    <label for="date">选择日期：</label>
    <input type="date" id="date" v-model="selectedDate" @change="handleDateChange"/>
  </div>
</template>
```

### 提示词模板

创建 `src/tpl/prompt.tpl.ts`：

```tsx
export default `
今天的日期是 toolu_018FQSWWq9Er5ZnpCvPHStEi

针对今天的日期、节日、节气等信息，整理出以下内容：
1. 今天的日期如果是特殊节日，介绍节日的文化和意义，以及节日的历史和背景。
2. 今天的日期如果是特殊节气，介绍节气的文化和意义，以及节气的历史和背景。
3. 今天的日期如果在历史上的重要事件中，介绍该事件的文化和意义，以及该事件的历史和背景。
`;
```

### App.vue

```jsx
<script setup lang="ts">
import DatePicker from "./components/DatePicker.vue";
import { ref } from "vue";
import nunjucks from "nunjucks";
import systemPrompt from "./tpl/prompt.tpl.ts";

const today = ref(new Date().toISOString().split("T")[0]);
const reply = ref("");

const dateUpdate = (date: string) => {
  today.value = date;
};

const submit = async () => {
  const apiKey = import.meta.env.VITE_API_KEY;
  const endpoint = import.meta.env.VITE_BASE_URL;
  const model = import.meta.env.VITE_AI_MODEL;

  const headers = {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${apiKey}`,
  };

  const prompt = nunjucks.renderString(systemPrompt, {
    today: today.value,
  });

  const response = await fetch(endpoint, {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
      model,
      messages: [
        { role: 'system', content: prompt },
        { role: 'user', content: "介绍今天相关的知识" }
      ],
      stream: true,
    })
  });

  const reader = response.body?.getReader();
  const decoder = new TextDecoder();
  let done = false;
  let buffer = '';
  reply.value = '';

  while (!done) {
    const { value, done: doneReading } = await (reader?.read() as Promise<{ value: any; done: boolean }>);
    done = doneReading;
    const chunkValue = buffer + decoder.decode(value);

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
        if (delta) reply.value += delta;
      } catch(ex) {
        buffer += incoming + '\n';
      }
    }
  }
};
</script>

<template>
  <div class="container">
    <h1>About Today</h1>
    <div class="panel">
      <DatePicker @date-update="dateUpdate" :value="today"/>
      <button @click="submit">提交</button>
    </div>
    <div class="output">
      <div>toolu_018FQSWWq9Er5ZnpCvPHStEi</div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: start;
  height: 100vh;
  font-size: .85rem;
}
.panel {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: start;
  width: 100%;
}
.input { width: 200px; }
.output {
  margin-top: 10px;
  min-height: 300px;
  width: 100%;
  text-align: left;
}
button {
  padding: 0 10px;
  margin-left: 6px;
}
</style>
```

### 关键代码解析

核心就是通过 **nunjucks 模板引擎**对系统提示词进行动态编译：

```tsx
const prompt = nunjucks.renderString(systemPrompt, {
  today: today.value,
});
```

模板中的 `toolu_018FQSWWq9Er5ZnpCvPHStEi` 会被替换为用户选择的日期值，从而实现动态提示词。

### 运行效果

[![](https://static001.geekbang.org/resource/image/1d/30/1d9688a19db5347eedd1ff5157c6bc30.gif?wh=544x524)](https://static001.geekbang.org/resource/image/1d/30/1d9688a19db5347eedd1ff5157c6bc30.gif?wh=544x524)

About Today 运行效果

---

## 要点总结

> [!important]
>
> - **元提示（Meta-Prompt）**：让一个智能体负责撰写提示词，再将提示词给后续智能体执行。适用于不同类型模型协作的场景
>
> - **动态提示词**：通过模板引擎（如 nunjucks）动态编译提示词，将运行时信息（日期、用户数据等）注入提示词中
>
> - 这两种方法在实际 AI 应用中非常常用且有效

---

## 课后练习

### 练习一：批量生成图片

元提示例子一次输入只能生成一张图片。能否修改代码或流程，让我们能够输入多个主题，同时生成多张图片？

### 练习二：替换模板引擎

在第二个例子里使用了 nunjucks 模板引擎。除了 nunjucks 外，你还使用过哪些模板引擎？尝试替换为其他模板引擎，试试效果。
