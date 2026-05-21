# JavaScript 中文周刊 #55 - 如何将 Rails 应用程序从 Webpack 迁移到 esbuild

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510305&idx=1&sn=4a39c368030713724b49615c3b24a95c&chksm=e921e2c3de566bd53e1c74bc46ce952128bd852e689ebefea8a9145cb40bda6e1f5a4c750062\#rd  
> 抓取时间: 2026/2/2 23:52:50

---

> 本期看点：本期为大家带来了如何将 Rails 应用程序从 Webpack 迁移到 esbuild与如何构建基于 Canvas 的绘图工具等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Jojo、Yucohny、山鬼

## 🔥 本周热门

**Ryan Dahl 要求 Oracle 释放 “JavaScript” 商标** — 众所周知，“JavaScript” 的商标目前归 Oracle 所有。这也是为什么 JS 的标准被称为 ECMAScript 的原因。这一切都源于 Netscape 公司与 Sun Microsystems 公司的交易，后来 Sun Microsystems 又被 Oracle 收购，致使 JS 的商标落入了 Oracle 的囊中。

**长按识别二维码查看原文**

https://tinyclouds.org/trademark

Ryan Dahl

**Introducing Signals：快速响应的状态管理库** - Signals 提供了一种非常自然的表达状态的反应方式，这样无论复杂性如何，应用程序都能保持快速。Signals 针对的是 Preact（React 的更轻薄的替代品），但可以通过猴子补丁与常规 React 一起使用。

**长按识别二维码查看原文**

https://preactjs.com/blog/introducing-signals/

Preact Team

**快讯：**

- 从 1994 年到现在的 **JavaScript 历史时间线**。
    
    **长按识别二维码查看原文**
    
    https://blog.risingstack.com/history-of-javascript-on-a-timeline/
    

- 📆 **Next.js Conf 2022** 将于今年 10 月在线举行，因而无需注册。现在，Next.js 也有 **一个新徽标**。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/nextjs-conf-2022
    

**版本发布：**

- **Node.js v18.9.0** – 一个非常小的版本。

- **Next.js v12.3** – 流行的 React 框架。

- **Jasmine v4.4** – 浏览器和 Node.js 的简单测试框架。

- **Ember.js v4.7** – 长期存在的框架。

- **sql.js v1.8** – 将 SQLite 编译为 JavaScript。

- **React Calendar v3.8** – React 应用程序的日历组件。

- **Fresh v1.1** – Deno 的全栈 Web 框架。

- **size-limit v8.1** — 绩效预算工具。

- **Serverless Offline v10.0** – 在本地模拟 AWS Lambda 和 API Gateway。

- **react-cytoscapejs v2.0** – 用于网络可视化的 React 组件。

- **Discordeno v14.0** – 用于 Deno 的 Discord API 库。

- **HotKeys v3.10** – Long-standing low footprint input capture.

- **Binary Parser v2.2** – 以声明方式编写快速二进制数据解析器。

## 📒 教程与趣事

**The Temporal API：一种管理日期和时间的新方式？** — 我们在过去的几年已经多次提及 (Dr. Axel 在 2021 攥写了这份完全指南） 但它仍然只在“开发阶段” 还没有得到广泛的支持。不过，他有一个 polyfill 方案并且非常便捷，所以你也可能想复习一下。

**长按识别二维码查看原文**

https://refine.dev/blog/temporal-date-api/

Muhammed Arslan Sarwar

**如何构建基于 Canvas 的绘图工具** — 内容广泛且完善的四部曲教程。

**长按识别二维码查看原文**

https://www.vector-logic.com/blog/posts/tutorial-build-html-canvas-drawing-tool-part-i

**如何将 Rails 应用程序从 Webpack 迁移到 esbuild** — 一个包含超过 30 万行 JS 的应用程序。

**长按识别二维码查看原文**

https://blog.arkency.com/how-i-migrated-a-rails-app-from-webpack-to-esbuild-and-got-smaller-and-faster-js-builds/

**将 Node 应用程序部署到 Fly.io** — 目前我们最喜欢的“挑战者”托管平台之一。

**长按识别二维码查看原文**

https://simonplend.com/deploying-a-node-app-and-postgres-database-to-fly-io/

**TIL 您可以仅使用 HTML 访问用户的相机** — 尽管浏览器支持相当有限。

**长按识别二维码查看原文**

https://austingil.com/html-capture-attribute/

**“将迭代****器的访问方式转换为函数”** — Axel Rauschmayer 博士下周在 TC39 演讲用的 PPT。

**长按识别二维码查看原文**

https://speakerdeck.com/rauschma/iteration-helper-functions

## 🛠 代码与工具

🔍 **GradeJS：扫描网站以获取该网站使用的模块包** — 即使您无权访问一个网站，这个工具可以尝试找出使用了哪些 npm 包，即使是压缩包或 tree-shaken 包（如果使用了 webpack 3-5）。

**长按识别二维码查看原文**

https://gradejs.com/

Konstantin Darutkin

**El：一个基于 Web Component 的微型UI框架** — 简短而甜蜜的定义。你在 150 行中得到了很多，包括一个内置的可观察存储和具有单向绑定的反应模板。想想一个非常轻量级的 React/Vue 与 Lit 混合。这是一个 一个文件示例 在其上创建待办事项列表应用程序。

**长按识别二维码查看原文**

https://github.com/frameable/el

Frameable

📪 **ZIPMonster：美国邮政编码数据与功能库** — 将美国邮政编码系统整合到一个库中，如果您愿意，可以进行各种查询，包括在整个美国导航。

**长按识别二维码查看原文**

https://github.com/russo-programmisto/zip-monster

Igor M.

**Shumani：使用Bun+Flashlight的快速机器学习库** — 有趣的是看到 Facebook 的研究部门使用Bun——这个实验性项目的早期阶段。

**长按识别二维码查看原文**

https://github.com/facebookresearch/shumai

Meta Research

**JSON Hero: 一个漂亮的 JSON 查看器** — 粘贴一些 JSON 或输入 JSON 文件的 URL，此工具提供简洁美观的用户界面，包含各种功能。

**长按识别二维码查看原文**

https://jsonhero.io/

API Hero

**DgrmJS：用于创建 SVG 图表的库** — 特别适用于流程图/流程图。

**长按识别二维码查看原文**

https://github.com/AlexeyBoiko/DgrmJS

Alexey Boyko

## 🙋🏻‍♀️