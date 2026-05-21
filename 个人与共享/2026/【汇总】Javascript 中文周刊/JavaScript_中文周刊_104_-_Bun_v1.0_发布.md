# JavaScript 中文周刊 #104 - Bun v1.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523897&idx=1&sn=a6da417a5a918a480d4cc7e2eff0a4f7&chksm=e921d5dbde565ccd2f27b0aaf86333ca6953ae53dc7989965f0b9ee48852f4b8c26a49d6b4cc\#rd  
> 抓取时间: 2026/2/2 23:51:45

---

> 本期看点：你应该已经使用过 Node，也许也见过 Deno，而现在 Bun 也成长起来了。它是一个性能导向的服务器端 JavaScript 运行时，构建在 JavaScriptCore 之上，并具有独特的特点，它是“Node.js 的一种可插拔替代品。”它还包括了诸如转译、打包、包管理和与 Jest 兼容的测试运行器等额外功能。这篇文章深入探讨了很多细节，而 Bun 团队制作的 ▶️ 10 分钟入门视频 同样值得关注。

> 编辑：Yucohny

## 🔥 本周热门

**Bun v1.0：Bun 既是一个工具包也是一个运行时** —— 你应该已经使用过 **Node**，也许也见过 **Deno**，而现在 **Bun** 也成长起来了。它是一个性能导向的服务器端 JavaScript 运行时，构建在 JavaScriptCore 之上，并具有独特的特点，它是“Node.js 的一种可插拔替代品。”它还包括了诸如转译、打包、包管理和与 Jest 兼容的测试运行器等额外功能。这篇文章深入探讨了很多细节，而 Bun 团队制作的 ▶️ **10 分钟入门视频** 同样值得关注。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.0

Jarred Sumner et al.

**为什么对空数组调用 `every()` 方法是返回 `true`？** —— 这篇文章深入研究了语言规范以了解这个逻辑。

**长按识别二维码查看原文**

https://humanwhocodes.com/blog/2023/09/javascript-wtf-why-does-every-return-true-for-empty-array/

Nicholas C. Zakas

**首次了解 TypeScript v5.3** —— **TypeScript v5.2**于几周前发布，这意味着 TypeScript v5.3 已经在筹备中（最终版本将于 **11 月份发布**），可能包括导入属性、抛出表达式和孤立声明等功能。

**长按识别二维码查看原文**

https://www.totaltypescript.com/typescript-5-3

Matt Pocock

**⚡️ 快讯：**

- **📅 ViteConf** 将于今年 10 月 5 日至 6 日举行，免费在线参加。

**长按识别二维码查看原文**

https://viteconf.org/23/

- **VS Code 2023 年 8 月版本** 已发布，其中包括了对 JavaScript 调试器的改进、WebAssembly 模块反编译，以及“移动到文件”和“内联变量”重构功能。

**长按识别二维码查看原文**

https://code.visualstudio.com/updates/v1_82

- Linus Groh 正在使用 Zig 开发名为 **Kiesel** 的 JavaScript 引擎，主要是作为学习项目，但在四个月的努力后，它已经通过了 25% 的 test262 测试。

**长按识别二维码查看原文**

https://codeberg.org/kiesel-js/kiesel

- 在搜索其他内容时，偶然发现了 **这篇 1996 年的 JavaScript 教程**，令人惊讶的是，其中大部分至今仍然正常运行。

**长按识别二维码查看原文**

http://home.ubalt.edu/abento/js-tutor/javascr.htm

- 微软代码考古学家 Raymond Chen **探讨了使用** `**this**` **的独立 JavaScript 函数如何被 VS Code 的静态分析器误认为构造函数**。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/oldnewthing/20230907-00/?p=108734

## 📒 教程与趣事

**JavaScript 的新数组分组方法** —— 这篇文章介绍了 `Object.groupBy` 和 `Map.groupBy`。**包含这些方法的提案** 目前在 TC39 处于第 3 阶段，但初始支持已逐渐进入浏览器的开发版本。

**长按识别二维码查看原文**

https://philna.sh/blog/2023/09/14/javascript-array-grouping-methods/

Phil Nash

**▶ 构建一个包含身份验证和分数保存功能的马里奥游戏** —— Ania 以她一贯的详细、逐步方式来实现游戏。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=1CVSI3MZNNg

Ania Kubów

**在 AWS Lambda 上运行 Playwright 脚本** —— 如果你也曾苦苦挣扎，无法让它正常运行，Matt 有一些建议。

**长按识别二维码查看原文**

https://steele.blue/playwright-on-lambda/

Matt Steele

**验证 URL 的新方法** —— `URL.canParse` **尚未广泛支持**，但可以轻松进行 polyfill。

**长按识别二维码查看原文**

https://www.stefanjudis.com/blog/validate-urls-in-javascript/

Stefan Judis

## 🛠 代码与工具

**Shadcn for Vue：可以复制粘贴的组件** —— 这是一个由社区推动的 Vue 版本，基于 **面向 React 的 shadcn/ui**，它是一套使用 Tailwind CSS 和 Radix UI 构建的吸引人组件，因此很容易‘复制粘贴’到你自己的应用程序中。

**长按识别二维码查看原文**

https://www.shadcn-vue.com/

Radix Vue Project

**npm-check-updates：将 `package.json` 依赖更新到最新版本** —— 与指定版本相对，它包括一个方便的 `-i` 交互模式，因此可以查看潜在的更新，然后逐个选择是否更新。

**长按识别二维码查看原文**

https://github.com/raineorshine/npm-check-updates

Raine Revere

**Starry Night v3.0：类似 GitHub 的语法高亮** —— GitHub 的语法高亮器不是开源的，而 Starry Night 使用 WebAssembly（以获取对 Oniguruma 正则引擎的访问权限）实现了尽可能接近的效果。

**长按识别二维码查看原文**

https://github.com/wooorm/starry-night

Titus Wormer

**Vuestic v1.8：Vue 3 的开源 UI 库** —— 包含超过 60 个可自定义组件的库。**v1.8** 引入了新的布局和文本区组件。这里是 **官方主页**。

**长按识别二维码查看原文**

https://github.com/epicmaxco/vuestic-ui

Epicmax

**Goxygen v0.7：快速为 JavaScript 项目生成 Go 后端** —— 一个用于在前端使用 Angular、React 或 Vue 建立新的基于 Go 的项目的工具，并提供 Docker 和 Docker Compose 文件以使其正常运行。

**长按识别二维码查看原文**

https://github.com/Shpota/goxygen

Sasha Shpota

**xterm.js v5.3.0：在浏览器中构建终端** —— 它被用于 **许多项目**，如 VS Code、cPanel、Azure Cloud Shell 和其他基于浏览器的 IDE。主页上有一个实时演示可供尝试。

**长按识别二维码查看原文**

https://xtermjs.org/

xterm.js team

**Transformers.js：使用 web 进行机器学习** —— 这是一个设计成与 Hugging Face 的 `transformers` Python 库功能上等效的 JavaScript 库，这意味着可以使用非常相似的 API 运行相同的预训练模型。可以在浏览器中使用 OpenAI 的 Whisper 模型进行 **基于 ML 的语音识别** 等操作。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://huggingface.co/docs/transformers.js/index

Joshua Lochner et al.

**Microsoft TypeChat：类型安全 LLM 响应的一种方法** —— TypeScript 的知名开发者 Anders Hejlsberg 和 Daniel Rosenwasser 仅是参与此项目的众多重要人物中的两位，这展示出 Microsoft 内部对 LLM 的巨大兴趣。TypeChat 的目标是解决 LLM 输出非结构化自然语言的问题，并将输出导向类型化形式。

**长按识别二维码查看原文**

https://microsoft.github.io/TypeChat/blog/introducing-typechat/

Hejlsberg, Lucco, Rosenwasser et al.

**WebLLM：使用 WebGPU 在浏览器中运行 LLM 模型** —— 由于它使用了 WebGPU，并不是直接使用 JavaScript，但这是另一种在浏览器内直接运行 LLM 的方式，而且可以使用 JavaScript 进行控制。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://webllm.mlc.ai/

MLC LLM

**TensorFlow.js：面向 JavaScript 开发者的机器学习** —— 稍微低层次，但是在浏览器或 Node.js 中训练和部署模型的绝佳方式，这里有 **许多演示**。

**长按识别二维码查看原文**

https://www.tensorflow.org/js

TensorFlow

**JavaScript 库允许开发者向 web 添加 AI 功能**

**长按识别二维码查看原文**

https://thenewstack.io/javascript-library-lets-devs-add-ai-capabilities-to-web/

Loraine Lawson (The New Stack)

**▶ 与来自 Latent Space 的 Swyx 一起入门 AI**

**长按识别二维码查看原文**

https://www.svelteradio.com/episodes/a-primer-on-ai-for-developers-with-swyx-from-latent-space

Svelte Radio

**🎉 版本发布：**

- **MikroORM v5.8**
    
    ↳ 强大的 Node.js ORM.
    

- **Reason v3.10**
    
    ↳ 使用 OCaml 编写适用于 JavaScript 生态系统的代码。
    

- **Happy DOM v11.0**
    
    ↳ 无 UI 实现 JavaScript 浏览器。
    

- **Gridstack.js v9.2**
    
    ↳ 在几分钟内构建交互式仪表板，这里是 演示。
    

- **Accessible Astro Starter v3.0**
    
    ↳ Astro 驱动博客的入门主题。
    

- **📊 Reveal.js v4.6**
    
    ↳ 使用 HTML 编写演示文稿。
    

## 🙋🏻‍♀️