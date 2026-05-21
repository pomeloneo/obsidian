# JavaScript 中文周刊 #161 - Svelte 5 正式发布；Next.js 15 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247536018&idx=1&sn=9cc02923d5704580047921a170d85dfe&chksm=e9210670de568f6652fce22b4368c3a83e15e1ab4a9628219f8ad2faa7e357199dcd8e813f51\#rd  
> 抓取时间: 2026/2/2 23:50:36

---

> 本期看点：Svelte 5 正式发布；Next.js 15 发布；GenAIScript：微软的生成式 AI 脚本环境；WebStorm 对非商业用途免费。

> 编辑：TimLi

🔥 本周热点

**Svelte 5 正式发布** —— 备受期待的 Svelte 主要版本更新终于到来，这是”该项目历史上最重要的一次发布”，同时保持了较高的向后兼容性。一个重大新增功能是用于显式声明响应式状态的 runes，此外还有许多其他改进。官方网站 svelte.dev 也进行了大规模重建，成为了 Svelte 相关内容的”全能站点”。

**长按识别二维码查看原文**

https://svelte.dev/blog/svelte-5-is-alive

Svelte 团队

📺 如果你想了解如何使用 Svelte 5，Syntax 的 Scott Tolinski 在 YouTube 上发布了一个▶️ 2 小时的 Svelte 5 基础课程。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=8DQailPy3q8

**GenAIScript：微软的生成式 AI 脚本环境** —— 微软正在从各个角度探索 AI。TypeChat 引入了一种与 LLM 进行类型安全对话的方式；现在 GenAIScript 提供了一种基于 JavaScript 的方法来以编程方式组装提示并处理响应。他们声称它”将基本的 LLM 提示工具整合到一个连贯的脚本环境中”。

**长按识别二维码查看原文**

https://microsoft.github.io/genaiscript/

微软

**Next.js 15 发布** —— 这是流行的（有人甚至认为是默认的）React 框架的重要一周，Next.js Conf 今天开始，同时发布了这个新版本。它包括用于更轻松升级的 codemod CLI、异步请求 API、与 React 19 的对齐等。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15

Vercel

**快讯：**

- 开发者 IDE 公司 JetBrains 宣布其 WebStorm JavaScript/TypeScript IDE 现在对非商业用途免费，值得注意的是，这也包括付费内容创作者。
    
    **长按识别二维码查看原文**
    
    https://www.jetbrains.com/webstorm/
    

- 流行的 `shadcn/ui` 组件库推出了一套用于构建侧边栏的新组件。
    
    **长按识别二维码查看原文**
    
    https://ui.shadcn.com/docs/components/sidebar
    

- ⌚ Spectra 是一款正在 Kickstarter 上寻求资金的可编程智能手表（但它已经超过了初始目标）。基于 ESP32-S3，从”开发体验”截图来看，它似乎能够运行 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://www.kickstarter.com/projects/pocuter/spectra
    

- 🙋 今年的 React 社区调查现已开启，截止日期为 11 月 19 日。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-react/2024
    

📒 教程与趣事

**▶ 使用 Kaplay 构建索尼克无尽跑酷游戏** —— 这是一个两小时的教程，介绍如何使用 Kaplay 游戏库（前身为 Kaboom.js）构建一个完整但简单的索尼克品牌游戏。你还可以在这里玩这个游戏。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=EmMO0yQ7eeY

JSLegendDev

**为什么我对用”更快”的语言重写 JavaScript 工具持怀疑态度** —— 近年来，用 Rust、Zig 或 Go 等”更快”的语言重写常见的 JS 基础设施/构建工具变得流行，但 Nolan 质疑这是否有必要。

**长按识别二维码查看原文**

https://nolanlawson.com/2024/10/20/why-im-skeptical-of-rewriting-javascript-tools-in-faster-languages/

Nolan Lawson

**如何用 Django 和 Vue 创建现代单页应用程序** —— 如果你能接受一些 Python，Django 是一个强大的后端 Web 框架，它可以很好地与 Vue.js 前端配对，GraphQL 提供了粘合剂。

**长按识别二维码查看原文**

https://www.thedevspace.io/community/django-vue

The Dev Space

**📄 使用网络摄像头、MediaPipe 和 Three.js 创建 3D 手势控制器** Caio Bassetti

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/10/24/creating-a-3d-hand-controller-using-a-webcam-with-mediapipe-and-three-js/

**📄 如何通过服务器端渲染加速你的 Vue 应用程序** Jakub Andrzejewski

**长按识别二维码查看原文**

https://www.debugbear.com/blog/vue-ssr

**📄 Angular 的部分水合方法** Loraine Lawson (The New Stack)

**长按识别二维码查看原文**

https://thenewstack.io/angulars-approach-to-partial-hydration/

**📄 理解** `**npm audit**` **并修复漏洞** Niraj Chauhan

**长按识别二维码查看原文**

https://www.niraj.life/blog/understanding-npm-audit-fixing-vulnerabilities-nodejs/

**📄 构建 Node.js 流的心智模型** Pavel Romanov

**长按识别二维码查看原文**

https://pavel-romanov.com/building-a-mental-model-of-nodejs-streams

🛠 代码与工具

**match-sorter v7.0：确定性最佳匹配数组排序** —— 如果你有一个需要”智能”和确定性过滤和排序的项目数组，这个库提供了一个描述清晰、可预测的算法。可以在 CodeSandbox 演示中试用。

**长按识别二维码查看原文**

https://github.com/kentcdodds/match-sorter

Kent C. Dodds

**🤖 Transformers.js v3：在浏览器中运行 Transformers** —— 这是 Hugging Face 的 `transformers` Python 库的 JS 移植版，可以直接在浏览器中运行自然语言、视觉和音频机器学习模型。v3 增加了 WebGPU 支持以提升性能，现在还支持 Node、Deno 和 Bun。

**长按识别二维码查看原文**

https://huggingface.co/blog/transformersjs-v3

Hugging Face

**Fetch Mock v12.0：模拟** `**fetch**` **API 的请求** —— 这是一个灵活的 API，用于模拟 `fetch` 或模仿 fetch 的库发出的 HTTP 请求。支持浏览器、Node 和 web/service workers。

**长按识别二维码查看原文**

https://www.wheresrhys.co.uk/fetch-mock/

Rhys Evans

**📊 Vizzu v0.14：动画数据可视化库** —— 制作可视化是一回事，让它们动起来则更难。Vizzu 帮助你创建动画数据故事和交互式探索器，还提供了各种展示示例供参考。

**长按识别二维码查看原文**

https://lib.vizzuhq.com/latest/

Vizzu Inc.

**eslint-plugin-functional：促进函数式编程的规则** —— 这可能不适合我，但如果你想在代码库中鼓励（甚至强制）不可变性和使用函数式编程技术，这可能适合你。

**长按识别二维码查看原文**

https://github.com/eslint-functional/eslint-plugin-functional

Jonas Kello

**Radix Vue：Vue.js 的无样式、可访问组件** —— 这是流行的 Radix UI 组件库的非官方 Vue 移植版。GitHub 仓库。

**长按识别二维码查看原文**

https://www.radix-vue.com/

zernonia 等

**版本发布：**

- **⚛️ React Native v0.76** —— 这是一个重大版本。所谓的”新架构”现在默认使用（所以你现在也可以在 RN 中使用所有现代 React 功能），React Native DevTools 已经稳定，构建时间比以往更快。

- **🥖 Bun** 正在快速发展，过去一周发布了三个版本。v1.1.31 增加了对 `node:http2` 服务器和 gRPC 的支持，v1.1.32 添加了 Node 的 `crypto.hash` 方法，v1.1.33 是一个 bug 修复版本。

- **Express.js v5.0** —— 几周前发布，现在有了一篇官方文章解释项目状态，该项目现已通过全面的第三方安全审计。

- **Medusa v2.0** —— 一个基于 Node.js 的电子商务平台。

- **React Compiler Beta**、**Turborepo v2.2**、**ESLint v9.13.0**、**Deno v2.0.2**

- **Edge.js v23** —— 在 Windows、macOS 和 Linux 上的一个进程中运行 .NET 和 Node.js 代码。

- **✂️ Knip v5.34.0** —— 一种查找和整理项目中未使用内容的巧妙方法。

- **🧊 PlayCanvas glTF Viewer v5.0** —— 支持 glTF 2.0 和 PLY 的 3D 模型查看器。

- **🗓️ React Date Picker v7.5** —— 简单的日期选择器组件。（演示）

- **🤖 ml.js v8.0** —— JavaScript 中的机器学习工具。

- **MDX v3.1** —— 在 Markdown 文档中编写 JSX。

🙋🏻‍♀️