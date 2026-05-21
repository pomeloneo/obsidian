# JavaScript 中文周刊 #59 - 使用默认的导出语法会让 JavaScript 的代码变得难以阅读！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511407&idx=1&sn=f92126c6ad325c2d2b5d04e1b7426512&chksm=e921e68dde566f9b83ab09f5cbfb78fab40002bffcbb51a71b8b318913dfc5367f9ed1ae1df6\#rd  
> 抓取时间: 2026/2/2 23:52:45

---

> 本期看点：上周，Upstart 基于 JavaScriptCore runtime Bun 推出了一个新版本，Storybook v7.0 也将对 Vite 提供支持，GraphQL 开发人员状态调查的结果终于公布… 更多热门文章资讯请点击本期周刊查看！

> 编辑：liu-jin-yi、Matrixbirds、Levi、Yucohny

## 🔥 本周热门

**`Intl` Explorer：一种学习和试验 ECMAScript 国际化 API 的方法** — 目前所有主流浏览器都支持 **Intl object**，使用它可以对 _ECMAScript Internationalization API_ 进行调用，这是一套用于语言敏感字符串比较、数字格式化等的函数。该站点提供了一种交互式方式来了解其运作方式。

**长按识别二维码查看原文**

https://www.intl-explorer.com/

Jesper Orb

**▶  使用 V8 创建你自己的 JavaScript Runtime** — Erick 深入的介绍了如何使用 V8 创建一个 JavaScript Runtime 的步骤。虽然你可能不会为自己编写下一个 Deno 或 Bun，但这视频包含了有很多关于 JS Runtime 的知识。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ynNDmp7hBdo

Erick Wendel

**Node v18.11.0 发布** — Node 的最新版本虽然并没有更新很多功能，但却实验性的支持了 `--watch` 功能。当导入的文件发生变化时，会自动重新启动运行中的进程（这个功能让人想起了 **nodemon**） – 这个功能最近被 **详细讨论过**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.11.0/

Danielle Adams (Node.js Project)

**Lerna Reborn：第六个版本更新了什么？** — 使用 Nrwl 管理，面向 Lerna monorepo 的 JavaScript 构建系统并没有过时或弃用，它正在向前迈进一大步。v6 在默认情况下通过高效的任务调度和缓存、VS Code 扩展、Prettier 支持等获得了很大的速度。**GitHub  仓库地址**。

**长按识别二维码查看原文**

https://blog.nrwl.io/lerna-reborn-whats-new-in-v6-10aec6e9091c?gi=ba929beec06d

Juri Strumpflohner

**快讯：**

- Upstart 基于 _JavaScriptCore_ runtime **Bun** 推出了 **一个新版本**，它在 HTTP 服务器的性能上有很大的提升，也有零延迟的热重载。
    
    **长按识别二维码查看原文**
    
    https://github.com/oven-sh/bun/releases/tag/bun-v0.2.0
    

- 💄 **javascript.makeup** 是一个新的小巧的在线 JavaScript Playground， _（替代品:_ **JSBin**_,_ **JSFiddle**_）_
    
    **长按识别二维码查看原文**
    
    https://javascript.makeup/file/default
    

- Storybook v7.0 将对 **Vite 提供支持**。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/first-class-vite-support-in-storybook/
    

- 📊 有史以来第一次 GraphQL 开发人员状态调查的 **结果** 出来了。
    
    **长按识别二维码查看原文**
    
    https://2022.stateofgraphql.com/en-us/
    

**版本发布：**

- **Volar v1.0** – 对 Vue.js 的官方 IDE 工具支持。

- **Ant Design v5.0 Alpha** – 流行的 React UI 库。

- **Rollup v3.1** – ES 模块打包器。

- **RxDB v13.5** – JS 应用程序的离线优先反应式数据库。

- **Qwik v.11** – ‘No hydration’，HTML 优先的框架。

- **Jest v29.2 & Cypress 10.10** – 测试框架。

- **SlickGrid v3.0** - 快速的 JavaScript 网格/电子表格控件。

- **Faker v7.6** – 假数据生成库。

- **React Tooltip v4.4**

- **Mineflayer v4.5** – 用 JS 构建 Minecraft 机器人。

- **CsvToMarkdownTable v1.2** – 将 CSV 转换为 Markdown 表。

## 📒 教程与趣事

**如何挑选最适合的 Node.js Docker 镜像** — 当你在编写 DockerFile 时会忽略`FROM node`的含义，作者分享了一些对于版本选择上的考虑。

**长按识别二维码查看原文**

https://snyk.io/blog/choosing-the-best-node-js-docker-image/

Liran Tal (Snyk)

**为什么我们在 2022 年选择使用 Babylon.js 主导开发而没有使用 Three.js** — Babylon 的高级审查工具、以及对 Blender Addon 的支持，还有来自微软公司的技术支持，赢得了 Gordon Hempton 团队的极大肯定。

**长按识别二维码查看原文**

https://www.spotvirtual.com/blog/why-we-use-babylonjs-instead-of-threejs-in-2022

Gordon Hempton

**我是如何在 js13KGames 比赛中编写一款 GameBoyd 风格的游戏** — 一个开发者阐述了自己参加 2022 年的 js13KGames 入选赛的经历 (我们上周贴了获奖名单地址)。

**长按识别二维码查看原文**

https://medium.com/hypersphere-codes/how-i-created-a-gameboy-like-game-in-13kb-5905bf6166b2

Kacper Kula

**▶  为前端开发者提供的全栈开发指南: 基于 AWS Amplify 服务构建你的 React 应用程序** — 这是亚马逊的开发者倡导师 Ali Spittel，她负责亚马逊的Amplify方向的业务，当下已经颁布了一系列使用 Amplify 平台进行端到端开发的免费课程的第一章节。点击这里可以查看▶️ **预告片**。

**长按识别二维码查看原文**

https://amplify.aws/learn/

Ali Spittel (AWS Amplify)

**TypeScript 类型守卫实践**

**长按识别二维码查看原文**

https://www.robinwieruch.de/typescript-type-guard/

Robin Wieruch

**Wix 是如何通过使用线程技术，降低 Node.js K8s pod 的消耗。**

**长按识别二维码查看原文**

https://thenewstack.io/wix-multithreaded-node-js-to-cut-kubernetes-pod-costs/

Jessica Wachtel (The New Stack)

**使用默认的导出语法会让 JavaScript 的代码变得难以阅读！**

**长按识别二维码查看原文**

https://cichocinski.dev/blog/using-default-exports-makes-javascript-harder

Tomasz Cichociński

## 🛠 代码与工具

**Javet v2.0.0：在 Java 应用中嵌入 Node 和 V8** — Javet 可以让你在基于 JVM 的应用中运行 V8 解释器或完整的 Node.js 运行时。这里有一些**演示幻灯片**来向你介绍这个想法并演示集成工作。Javet 这个名字来自 Java、V 和 8（Eight）。

**长按识别二维码查看原文**

https://www.caoccao.com/Javet/

Sam Cao

**Knip：在 TypeScript 项目中查找未使用的文件、依赖项和导出项** — Knip 是荷兰语中 “修剪” 的意思，适用于修剪掉项目中未使用的东西的工具。如果要将它与类似的现有工具进行比较，可以查看**这个图表**。

**长按识别二维码查看原文**

https://github.com/webpro/knip

Lars Kappert

**Editly v0.14.0：声明式视频编辑工具** — 该库将 Node 和 FFmpeg 结合在一起，让您可以用编程的方式编辑和构建视频，而不是苦恼于深奥的 ffmpeg 命令行选项。

**长按识别二维码查看原文**

https://github.com/mifi/editly

Mikael Finstad

**Sortable：通过拖动来创建和重排列表** — 这个库支持所有现代浏览器和触摸设备，通过自动滚动、CSS 动画、多指拖动支持等处理列表到列表的拖动，同时包含大量的演示。

**长按识别二维码查看原文**

http://sortablejs.github.io/Sortable/

SortableJS

**melonJS v14.0：轻量级 2D 游戏引擎** — 这个库已有十多年的历史，但仍然很强大。虽然它是 2D 的，但它会使用 WebGL 来提高性能（如果可用的话）。此外它还提供 Web Audio API 支持、基于多边形的碰撞检测、输入设备支持等。这里有个**游戏示例**。

**长按识别二维码查看原文**

https://melonjs.org/

melonJS Team

## ♟ 来玩个游戏吧

**Betafish：国际象棋引擎和 AI 行为查看器** — **作者解释了其中使用的算法**，如果您喜欢“好看的国际象棋游戏”，这里提供了一个**在线试玩版本**。

**长按识别二维码查看原文**

https://github.com/Strryke/betafish

Gavin Ong

你可以通过仅十行 JavaScript 代码**构建自己的井字棋游戏**。

**长按识别二维码查看原文**

https://lyty.dev/blog/tic-tac-toe-game-javascript/

## 🙋🏻‍♀️