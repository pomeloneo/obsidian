# JavaScript 中文周刊 #138 - 从愚人节项目中学习酷炫的多人合作戈德堡机械模拟器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531835&idx=1&sn=b175efcff610d4cac08b012d132701a7&chksm=e92136d9de56bfcf9454a6443ea657fddf6d2228f99eece85f5843ec799f661219a1e8c65aa3\#rd  
> 抓取时间: 2026/2/2 23:51:05

---

> 本期看点：xkcd 今年又制作了一个酷炫的愚人节项目，一个巨大的、带物理引擎的合作戈德堡机械模拟器。Figma 团队也介绍了如何从 Skew 平滑迁移到 TypeScript。

> 编辑：Yucohny、TimLi、Zhper

🔥 本周热门

**来自 xkcd 的“机器”开发笔记** —— 为了今年的愚人节笑话，他们发布了 “机器”，一种巨大的戈德堡机械模拟器。在技术上，它主要使用了大量的 TypeScript 和 Haskell。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://chromakode.com/post/xkcd-machine/

Max Goodhart

**Figma 迁移到 TypeScript 的历程** —— Figma 团队介绍了他们是如何将自己编写的 Skew 编程语言 的代码自动迁移到 TypeScript 的，而不会中断任何一天的开发。

**长按识别二维码查看原文**

https://www.figma.com/blog/figmas-journey-to-typescript-compiling-away-our-custom-programming-language/

Brandon Lin（Figma）

**Gulp 从未消失；参与 Gulp 开发者调查** —— 许多在多年前引起轰动的优秀工具现在虽然被很少提到，但是仍然运作良好。这也包括 Gulp，一个最初于 2013 年发布的构建系统和工具包。Gulp v5.0 在上月发布，他们团队正在致力于使其变得更好。如果你想帮忙，可以 在这里参与他们的调查。

**长按识别二维码查看原文**

https://medium.com/gulpjs/introducing-the-gulp-developer-survey-cc227fc2fb6d

Clarissa Abidog

**快讯：**

- Ben Hong 为我们收集了一些 2024 年 Vue 生态系统的优秀工具和库。
    
    **长按识别二维码查看原文**
    
    https://frontendmasters.com/blog/the-vue-ecosystem-in-2024/
    

- Node.js 核心团队邀请你 参与最新的 Node.js Next 10 调查，帮助他们决定 Node 接下来的发展方向。
    
    **长按识别二维码查看原文**
    
    https://linuxfoundation.surveymonkey.com/r/nodenext10survey24
    

- 上周我们推荐了一个有趣的 ▶️ 关于使用 `let` vs `const` 的讨论，但 Jack Herrington 对这种方法不太感兴趣，所以他 ▶️ 花了 10 分钟分析了这次讨论及其观点。
    
    **长按识别二维码查看原文**
    
    https://www.epicweb.dev/talks/let-me-be
    

- Bun 团队正在 寻找一名系统工程师 加入他们的团队，作为他们推动 Bun 更加适用于生产环境的一部分。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/
    

📒 教程与趣事

**▶  无缝拖放应用程序间的交互** —— 这是一个使用浏览器 API 创建更优雅的拖放体验的绝佳演示，甚至可以在不同的浏览器窗口或 IFRAMEs 之间工作，由 Atlassian 的 Pragmatic Drag and Drop 库进行重度支持。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=E4l4MBO-Bwg

Alex Reardon

**为何全局补丁是有害的** —— 修改全局 API 以扩展其功能是常见的，但如果你喜欢可读性、维护性和可预测性，那么这并不可取。

**长按识别二维码查看原文**

https://kettanaito.com/blog/why-patching-globals-is-harmful

Artem Zakharchenko

**“在某个时刻，JavaScript 变得很好”** —— 作者指出 JavaScript 在 ES6 中得到了“大提升”，并赞扬了自那时以来的持续改进。或许并不令人惊讶，在 Hacker News 上的一场热烈讨论 强调了一些持续存在的总体不满。

**长按识别二维码查看原文**

https://jonbeebe.net/2024/05/javascript-got-good/

Jonathan Beebe

**📄 如何在关闭标签页时安全地发送请求** —— 经常被遗忘的 `sendBeacon()` 来拯救。

**长按识别二维码查看原文**

https://webdeveloper.beehiiv.com/p/securely-send-request-closing-tabs

Zachary Lee

**📄 使用 React Three Fiber 探索 3D 文本扭曲效果**

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/05/08/exploring-a-3d-text-distortion-effect-with-react-three-fiber/

Nine / Codrops

**📄 使用 yt-dlp、Whisper.cpp 和 Node 自动生成播客节目笔记**

**长按识别二维码查看原文**

https://ajcwebdev.com/autogen-shownotes/

Anthony Campolo

**📄 React 开发者学习 SolidJS 的指南**

**长按识别二维码查看原文**

https://www.stashpad.com/blog/react-developer-guide-to-solid-js

Tristan Dyer

**📄 为什么选择 React Query？**

**长按识别二维码查看原文**

https://ui.dev/why-react-query

UI․dev

🛠 代码与工具

**Pintora：一个可扩展的文本-图表渲染库** —— 和 Mermaid 的想法类似，但对待扩展性的态度不同，同时不需要无头浏览器的服务端。介绍文档 同时有可视化示例和代码示例。

**长按识别二维码查看原文**

https://pintorajs.vercel.app/

Hikerpig

**jQuery 到 JavaScript 的转换器** —— 一个基于浏览器的工具，可以快速地将 jQuery 脚本转换为非 jQuery 代码。这里是 GitHub 仓库。

**长按识别二维码查看原文**

https://www.lightgalleryjs.com/jquery-to-js-converter/

lightGallery

**DerbyJS 4：成熟的 MVC Web 框架** —— Derby 经历了 Node.js 的大部分历史，并且在某些情况下依然是 **构建实施性、交互性应用程序** 可行选择。这里是 GitHub 仓库。

**长按识别二维码查看原文**

https://derbyjs.com/

Nate Smith et al.

**graphql-request v7.0：极小的 GraphQL 客户端** —— 现在是完全的 ESM 包，对客户端和服务端都有一流的 TypeScript 支持。

**长按识别二维码查看原文**

https://github.com/jasonkuhrt/graphql-request

Jason Kuhrt

**Fabric.js：SVG-to-Canvas 和 Canvas-to-SVG 的库** —— 在 HTML 画布之上提供了一个交互式对象模型，以便更容易地处理多个可视化元素。这是一个长期存在的项目，v6 已经筹备了一段时间，并且最近发布了 第一个候选版本。

**长按识别二维码查看原文**

https://github.com/fabricjs/fabric.js

Fabric.js

**版本发布：**

- ⭐ **esbuild v0.21.0** – 这个版本的发布比版本号所暗示的更为重要，因为它引入了对 decorators 提案 的支持（所以建议你在升级时进行额外的测试）。

- **Ionic v8.1** – 用于构建原生质量应用的跨平台 UI 工具包。

- **pnpm v9.1**

- **AdonisJS v6.9**

- **Playwright v1.44.0**

- **Bunv 1.1.7**

- **MSW (Mock Service Worker) v2.3** – API 模拟库。

- **Mantine v7.9** – 流行的 React 组件库。

- **node-oracledb v6.5** – Oracle 自家的官方 Node.js 数据库驱动，现在支持 Oracle 最新的向量搜索功能。

- **js-bson v6.7** – 适用于 Node 和浏览器的 MongoDB BSON 解析器。

- **d3-graphviz v5.4** – 从 Graphviz DOT 图形渲染 SVG。

- **validator.js v13.12.0** – 字符串验证函数。

🙋🏻‍♀️