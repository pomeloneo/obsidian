# JavaScript 中文周刊 #165 - 如何不使用构建系统导入前端 JavaScript 库

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538171&idx=1&sn=4c63db2c9e81e75542d4b3a1a10db9c1&chksm=e9211e19de56970f21bf30a26c86218c672c786128bfb433ddfa949fd4a00b2d90eb2166e41c\#rd  
> 抓取时间: 2026/2/2 23:50:31

---

> 本期看点：如何不使用构建系统导入前端 JavaScript 库；Angular v19 发布，引入增量水合预览版和新的响应式原语；Vercel 推出开源 AI 聊天机器人启动模板；新一代 JavaScript 引擎 Nova 问世，采用面向数据的创新方法。

> 编辑：TimLi

🔥 本周热点

**如何不使用构建系统导入前端 JavaScript 库** —— 许多开发者更倾向于避开复杂的现代构建流程，而是以更传统的方式使用 JavaScript。你完全可以不使用构建系统，Julia 探讨了在这种情况下导入库的几种方法。

**长按识别二维码查看原文**

https://jvns.ca/blog/2024/11/18/how-to-import-a-javascript-library/

Julia Evans

**Angular v19 发布** —— 这款流行的企业级应用程序框架的最新版本已经发布，附带一个 ▶️ 22 分钟的介绍视频，详细介绍了变化和新功能，包括增量水合（预览版）、两个新的核心响应式原语、事件重放，以及指定哪些路由在服务器端或客户端渲染的功能。

**长按识别二维码查看原文**

https://blog.angular.dev/meet-angular-v19-7b29dfd05b84

Minko Gechev

**快讯：**

- 🗳️ 最新的 State of JS 调查现已开放接受回答，截止日期为 12 月 3 日。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-js/2024
    

- 🇫🇷 dotJS 2025 将于明年 4 月在法国巴黎举行。如果你想发言，可以在 11 月 29 日前提交演讲提案。
    
    **长按识别二维码查看原文**
    
    https://www.dotjs.io/
    

- 无服务器函数平台 AWS Lambda 本周迎来十周年。它的第一个运行时就是基于 JavaScript 的。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/aws/aws-lambda-turns-ten-the-first-decade-of-serverless-innovation/
    

- Nova 是一个有趣的新 JavaScript 引擎，采用了 CPU 缓存友好的面向数据的方法。
    
    **长按识别二维码查看原文**
    
    https://trynova.dev/blog/what-is-the-nova-javascript-engine
    

📒 教程与趣事

**探索 JavaScript Symbols** —— Symbols 是十年前随 ES6 一起推出的一个”独特的小原始类型”（用 Trevor 的话说），但它们仍然没有被充分理解。Trevor 对它们进行了很好的解析，包括对可能被弃用的”species”的简要探讨。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/symbols-in-javascript

Trevor I. Lasn

**使用 Deno 构建独立可执行程序** —— Deno 的一个引人注目的特性是其 `deno compile` 命令，可以将 JavaScript 和 TypeScript 程序转换为单个、易于分发的跨平台二进制文件。这里介绍了它的工作原理。

**长按识别二维码查看原文**

https://deno.com/blog/deno-compile-executable-programs

Ryan Dahl 和 Andy Jiang

**JavaScript 中的 Promise 映射** —— 快速了解三种方法：`for..of`、`Promise.all` 和 `p-map`。

**长按识别二维码查看原文**

https://www.telerik.com/blogs/mapping-promises-javascript

Peter Mbanugo

**📄 从 VuePress 迁移到 VitePress** Henry Bley-Vroman

**长按识别二维码查看原文**

https://olets.dev/posts/migrate-from-vuepress-to-vitepress/

**📄 为什么 Alpine 是”新 jQuery”，为什么这很棒** Raymond Camden

**长按识别二维码查看原文**

https://frontendmasters.com/blog/why-alpine-is-the-new-jquery-and-why-that-is-an-awesome-thing/

**📄 如何预发布 npm 包** Scott Vandehey

**长按识别二维码查看原文**

https://cloudfour.com/thinks/how-to-prerelease-an-npm-package/

**📄 使用 Fraction.js 在 JavaScript 中进行精确的小数计算** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/fraction-numbers-in-javascript

**📄 如何避免 Playwright 中的不稳定测试** Zanini 和 Ackerson

**长按识别二维码查看原文**

https://semaphoreci.com/blog/flaky-tests-playwright

**📄 在 Astro 中添加交互式图表** Pavlin BG

**长按识别二维码查看原文**

https://www.pavlinbg.com/posts/adding-interactive-charts-in-astro

🛠 代码与工具

**Viselect：让用户可视化选择 DOM 元素** —— 如果你有各种元素，并且想让用户能够分组、单独或多组选择它们，这个工具可以轻松实现该功能。可以原生使用，也可以与 P/React 或 Vue.js 集成。

**长按识别二维码查看原文**

https://simonwep.github.io/selection/

Simon Reinisch

**Perfectionist v4：用于代码排序的 ESLint 插件** —— 无论你想排序什么（属性、导入、类型、装饰器、模块等），只要你想用 ESLint 强制执行排序，这个插件就是为你准备的。它支持字母顺序和自然排序，还支持按行长度排序，可以实现这种美观效果。

**长按识别二维码查看原文**

https://github.com/azat-io/eslint-plugin-perfectionist

Azat S.

**React Scan：检测应用程序中的性能问题** —— 一个纯 JavaScript 工具，你可以将其添加到应用程序中，无需大量集成工作就能自动”扫描”有问题的渲染。主页上有一个简单的演示，你也可以看看 Aiden 的 Twitter/X 扫描视图。GitHub 仓库。

**长按识别二维码查看原文**

https://react-scan.million.dev/

Aiden Bai

**💬 Discordeno v19：强大的 Discord API 库** —— 一个用于处理和构建 Discord 聊天系统机器人的长期解决方案。v19 是一个包含重大更改的大更新。GitHub 仓库。

**长按识别二维码查看原文**

https://discordeno.js.org/

Discordeno Team

**🤖 Vercel 的 AI 聊天机器人启动模板** —— 使用 Next.js 构建的开源 AI 聊天机器人应用程序模板。它使用 Vercel 的 AI SDK 和其他 Vercel API 来处理复杂的工作。

**长按识别二维码查看原文**

https://github.com/vercel/ai-chatbot

Vercel

**Glide.js v3.7：无依赖的滑块和轮播控件** —— 创建者说：“专为滑动而设计。不多不少。” MIT 许可证，已经相当成熟。

**长按识别二维码查看原文**

https://glidejs.com/

Jędrzej Chałubek

**版本发布：**

- **Bun v1.1.35** —— 这个快速的 JavaScriptCore 运行时增加了对 Musl 和 Alpine Linux 的原生支持，Bun 二进制文件变得更小，现在支持 `console.group` 和 `groupEnd`，并且 `fs.readFile` 在小文件上更快。

- **Payload v3.0** —— 无头 Next.js 原生 CMS 平台。

- **📊 Mantine v7.14.0** —— 这个流行的 React 组件套件添加了新的”角度滑块”、径向条形图、漏斗图和堆叠模态框/抽屉组件。

- **Node.js v23.3.0（当前版本）** 和 **v20.18.1（LTS）**

- **Ionic v8.4**、**ESLint v9.15.0**、**Turborepo v2.3**、**Deno v2.1**、**QuickJS v0.7**

- 🤞 在我们发送时还未发布，但我们预计 TypeScript 5.7 将在今天晚些时候发布 —— 你可以在 TypeScript 博客上查看。

- **pretty-ms v9.2** —— 将毫秒转换为人类可读的字符串。现在可以根据需要隐藏年、秒和天。

- **☕ Javet v4.1** —— 将 Node.js 和 V8 嵌入 Java。更新到 Node v22.11.0 并添加 Float16 支持。

- **Embla Carousel v8.5** —— 具有流畅动效的轻量级轮播库。

- **Sortable v4.0** —— 使用 `class="sortable"` 使表格可排序。

- **📊 Vue Data UI v2.4** —— Vue 3 数据可视化组件。

- **Capacitor v6.2** —— 使用 JS 构建跨平台原生应用程序。

- **Peggy v4.2** —— JavaScript 的解析器生成器。