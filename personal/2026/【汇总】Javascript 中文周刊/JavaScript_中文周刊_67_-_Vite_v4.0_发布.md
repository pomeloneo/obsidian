# JavaScript 中文周刊 #67 - Vite v4.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512885&idx=1&sn=d2550aab8c53d0a10df570e6b3057a7d&chksm=e921f8d7de5671c16ed5aae4f5225da1f63b791ca940ff6c5f1fb919dd36df84964d6d104898\#rd  
> 抓取时间: 2026/2/2 23:52:35

---

> 本期看点：上周，Vite v4.0 发布、在 Next.js 会议上 Lee Robinson 提出了关于使用 Rust 优化 JavaScript 的说法…..更多热门文章资讯请点击本期周刊查看！

> 编辑：山鬼、Yucohny

## 🔥 本周热门

**Vite v4.0 发布** — Vite 与 Vue.js 出自同一作者，是一款令人兴奋的前端工具。Vite 提供了许多开箱即用的好东西：快速热更新、即时服务器启动、使用 Rollup、TypeScript 和 JSX 支持的优化构建。你可以在 **这里** 进行快速尝试。**点击链接了解更多**。

**长按识别二维码查看原文**

https://vitejs.dev/blog/announcing-vite4.html

Evan You and Vite Contributors

**Console Ninja：将 `console.log` 的输出结果打印在代码旁** — 这是一个在代码旁展示了 `console.log` 输出结果和运行错误的 VS Code 插件。Jack Herrington 录制了 **▶️ 6 分钟的简洁介绍**。

**长按识别二维码查看原文**

https://console-ninja.com/

Wallaby.js Team

**快讯：**

- 关于 React 的 **纪录片** 目前正在制作中 – ▶️ **这是预告片**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=gmp0istg5xo
    

- AWS 公布了 **Step Functions Distributed Map**，这是一种可以对存储在 S3 上的数据和文档进行高度并行（最多 10,000 个同时执行）操作（可能是用 JavaScript 编写）的方法。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/aws/step-functions-distributed-map-a-serverless-solution-for-large-scale-parallel-data-processing
    

- 快速回顾 27 年前 **1995 年 JavaScript 的发布**。
    
    **长按识别二维码查看原文**
    
    https://www.webdesignmuseum.org/web-design-history/javascript-1-0-1995
    

- 📊 **D3 v7.7**，流行的数据可视化框架的最新版本。如果你想获得使用 D3 的灵感，或者看看新功能，推荐你看看这篇它的共同创建者 **Mike Bostock 的笔记本**。
    
    **长按识别二维码查看原文**
    
    https://observablehq.com/@mbostock?tab=notebooks&type=public
    

- **最新 VS Code 版本** 中的 JS 调试器现在支持用于 CPU 分析代码的“console.profile”以及嵌套源映射。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_74
    

**版本发布：**

- **Rome v11**新的 lint 规则、可选的分号支持、新的排序导入功能和改进的抑制注释。

- **Storybook v7.0 beta 0**

- **Rollup v3.7**
    
    ↳ ES 模块打包器。
    

- **xv v2.0**
    
    ↳ 零配置 Node 测试运行器。
    

- **Nx v15.3**

- **Ember v4.9**

- **Bun v0.3**
    
    ↳ JS 运行时。
    

- **Spacetime v7.3**
    
    ↳ 轻量级 JavaScript 时区库。
    

- **Partytown v0.7.3**
    
    ↳ 在 worker 中运行密集的第三方脚本。
    

- **Splitter v1.4**
    
    ↳ 拆分视图的 React 组件。
    

- **reveal-md v5.4**
    
    ↳ 来自 Markdown 文件的 Reveal.js 演示文稿。
    

- **Mongoose v6.8**
    
    ↳ MongoDB 对象建模库。
    

- **React Tooltip v5.0**

## 📒 教程与趣事

**Partytown 沙盒？** — Partytown提供了一种在 Web Worker 中而不是在主线程上运行第三方脚本的方法。这可以用于实现沙盒吗？作者就这个问题展开的实践，详情请点击文章了解。

**长按识别二维码查看原文**

https://weston.ruter.net/2022/11/30/sandboxing-with-partytown/

Weston Ruter

**何时使用 gRPC 与 GraphQL** - 本篇文章比较了两个流行的 API 协议，以了解每个协议在哪些方面最有效。

**长按识别二维码查看原文**

https://stackoverflow.blog/2022/11/28/when-to-use-grpc-vs-graphql/

Loren Sands-Ramshaw

**▶ 关于使用 Rust 优化 JavaScript 的讨论** — 在最近的 Next.js 会议上与 Vercel 的 Lee Robinson 交谈。

**长按识别二维码查看原文**

https://stackoverflow.blog/2022/12/09/ready-to-optimize-your-javascript-with-rust/

Ben Popper podcast

## 🛠 代码与工具

**Harlem v3.0：Vue 3 的简单可扩展状态管理** — 提供用于创建、读取和改变状态的简单功能 API。

**长按识别二维码查看原文**

https://harlemjs.com/

Andrew Courtice

**JS Image Carver：内容感知图像缩放器和对象移除器** - 使用接缝雕刻方法实现（如果你在 Photoshop 中使用过“Content Aware Scale”，那么会更容易理解）。这个 **现场演示** 很有趣。

**长按识别二维码查看原文**

https://github.com/trekhleb/js-image-carver

Oleksii Trekhleb

**Civet：TypeScript 中的 CoffeeScript？** — 如果你以前喜欢 CoffeeScript，那么这个库可以让你用 CoffeeScript 的语法写 TypeScript。

**长按识别二维码查看原文**

https://github.com/DanielXMoore/Civet

Daniel Moore

**Maska v2.1：零依赖输入掩码** — 在很多情况下都可以发挥很好的作用，并且也可以与 Vue 2/3 一起使用。这里是它的 **GitHub 仓库**。

**长按识别二维码查看原文**

https://beholdr.github.io/maska/\#/

Alexander Shabunevich

**reduced.to：使用 Qwik 构建的开源 URL 缩短应用程序** — 该应用程序本身位于 **reduced.to**，但是如果将其作为使用 Qwik 框架构建的前端示例，可能会发现它很有趣。

**长按识别二维码查看原文**

https://github.com/origranot/reduced.to

Ori Granot

📺  Dot Media 发布了 Qwik 的创建者 Misko Hevery 关于 ▶️ **Qwik 的实时编码介绍** – 一种快速上手的有用方法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=DxJgXw91cCQ

## 🙋🏻‍♀️