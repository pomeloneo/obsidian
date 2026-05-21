# JavaScript 中文周刊 #172 - Electron 维护者揭秘：那些你对 Electron 的误解

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539559&idx=1&sn=00161b3d8f07e01f99334256cc8b6e6d&chksm=e9211085de56999313a6651fb27e54e0a18578559e942fb19e295b078a702dedb2542a331fb0\#rd  
> 抓取时间: 2026/2/2 23:50:22

---

> 本期看点：Electron 维护者详解框架技术选择及常见误解，Zod、Valibot 等知名库联合推出 Standard Schema 统一接口标准，TypeScript 5.8 Beta 发布支持 Node 22+ ES 模块 require()，docxtemplater 发布支持从模板生成 Word 和 PowerPoint 文档，Astro v5.2 发布并添加 Tailwind CSS 4 支持。

> 编辑：TimLi

🔥 本周热点

**人们对 Electron 的误解** —— 作为广受欢迎的跨平台应用程序框架 Electron 的长期维护者，作者为其多年来的技术选择进行了辩护，并回应了一些常见的批评。

**长按识别二维码查看原文**

https://felixrieseberg.com/things-people-get-wrong-about-electron/

Felix Rieseberg

**Standard Schema：统一的 Schema/验证库接口** —— 来自 Zod、Valibot 和 ArkType 的创作者们展开了一次出色的合作，为 JavaScript 和 TypeScript schema 库定义了一个通用接口。

**长按识别二维码查看原文**

https://standardschema.dev/

McDonnell、Hiller 和 Blass

**一个能装进推文的 WebAssembly 编译器** —— 如果你更喜欢用字节来衡量的话，它只有 192 字节。这是一个非常巧妙的 JavaScript 技术展示，可以将算术表达式编译成易于运行的 WebAssembly。在短短几分钟内你就能学到很多东西。

**长按识别二维码查看原文**

https://wasmgroundup.com/blog/wasm-compiler-in-a-tweet/

Mariano Guerra 和 Patrick Dubroy

**TypeScript v5.8 Beta 即将发布** —— TypeScript 的新版本即将到来。有哪些新特性？支持在 Node 22+ 中对 ES 模块使用 `require()`、条件类型和索引访问类型的返回值检查、启动和构建性能优化等。虽然总体来说不是一个重大版本更新，但对 Node.js 开发者来说特别有价值。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-8-beta/

Daniel Rosenwasser

💡 5.8 中一个很棒的特性是 `--erasableSyntaxOnly`，它可以确保”类型擦除”技术仍然能产生可运行的代码，方法是禁用像枚举这样的 TypeScript 独有特性。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-8-beta/?ck_subscriber_id=887809557\#the—erasablesyntaxonly-option

**快讯：**

- 🎬 还记得 Honeypot 制作的那部广受好评的 Node.js 纪录片吗？（如果没看过，快去看！）现在他们即将推出 Angular 纪录片，预告片已经发布。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=LB8KwiiUGy0
    

- 最近有很多人在讨论 Create React App 因为缺乏来自 Meta 的更新而实际上被”废弃”了。事实证明，它确实被废弃了，但这个过程现在正在得到妥善处理，并且会合并一些基本的 React 19 支持。
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/create-react-app/pull/17003
    

- 一位开发者提出了一个让 npm 包体积减小 5% 的方案，使用 Zopfli 压缩，并请 npm 团队考虑采用。最终由于多种原因被否决了。
    
    **长按识别二维码查看原文**
    
    https://evanhahn.com/my-failed-attempt-to-shrink-all-npm-packages-by-5-percent/
    

- ⭐ Syntax YouTube 频道制作了一个▶️ GitHub 上最受欢迎的 15 个 JavaScript 项目倒计时视频。制作非常精良。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=NBDnS9UQg5w
    

📒 教程与趣事

**编写 JavaScript 服务器的现代化方案** —— 有趣的是，虽然 Node.js 让 JavaScript 在服务器端流行起来（尽管 Netscape 在 90 年代就开始这么做），但这种基于标准化的跨运行时（cross-runtime）方案在 Node.js 上还不能使用……暂时还不能 ;-)

**长按识别二维码查看原文**

https://marvinh.dev/blog/modern-way-to-write-javascript-servers/

Marvin Hagemeister

**介绍 Mentoss：**`**fetch**` **模拟器** —— 一种模拟全局 `fetch()` 调用的新方法（适用于浏览器和服务器端运行时），灵感来自 Nock 和 MSW 等前辈。

**长按识别二维码查看原文**

https://humanwhocodes.com/blog/2025/01/introducing-mentoss-fetch-mocker/

Nicholas C. Zakas

**JavaScript 应用程序中扩展 WebSocket 的经验教训** —— 为实时应用程序扩展 WebSocket 存在着一些隐藏的复杂性。Compose 分享了一些来之不易的经验。

**长按识别二维码查看原文**

https://composehq.com/blog/scaling-websockets-1-23-25

Atul Jalan

**📄 在 TypeScript 中使用元组进行计算** —— 一种比键值对象更轻量级的方式来组合不同类型的对象。Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/01/typescript-tuples.html

**📄 JavaScript 中的一秒到底有多长？** —— 看似简单的问题背后其实蕴含着令人惊讶的复杂性。Iago Lastra

**长按识别二维码查看原文**

https://docs.timetime.in/blog/how-long-is-a-second-in-js/

**📄 使用 Leaflet.js 为你的页面添加地图** —— 快速、简单，而且是开源的。Raymond Camden

**长按识别二维码查看原文**

https://frontendmasters.com/blog/mapping-with-leaflet/

**📄 如何在浏览器中使用 Node 的** `**fs**` **模块来创建自定义 Playground** —— Ivan Chebykin

**长按识别二维码查看原文**

https://typeconf.dev/blog/using-fs-in-browser

**📄 构建一个 QR 码 HTML Web 组件** —— Scott Jehl

**长按识别二维码查看原文**

https://scottjehl.com/posts/q-r/

**📄 如何使用 React Admin 构建 CMS** —— Thibault Barrat

**长按识别二维码查看原文**

https://marmelab.com/blog/2025/01/24/how-to-build-a-cms-with-react-admin.html

🛠 代码与工具

**docxtemplater：从模板生成** `**docx**` **和** `**pptx**` **文档** —— 通过合并模板动态生成 Word 和 PowerPoint 文件（特别适合生成发票、合同、证书等）。它是开源的（MIT 或 GPLv3 协议），但创建者还提供了一个带有更多扩展的商业版本（例如可以处理 Excel）。GitHub 仓库和功能演示。

**长按识别二维码查看原文**

https://docxtemplater.com/

Edgar Hipp

**📊 Plotly v3.0：JavaScript 图表库** —— 一个基于 D3 和 stack.gl 构建的高级声明式图表库，提供超过 40 种图表类型，包括 3D 图表、统计图表和 SVG 地图。v3 主要是移除了废弃功能、修复 bug，并切换到了 esbuild。

**长按识别二维码查看原文**

https://plotly.com/javascript/

Plotly, Inc.

**Emittery v1.1：简单现代的异步事件发射器** —— 一个适用于 Node 和浏览器的小型异步事件发射器，现在支持 `AbortController`。

**长按识别二维码查看原文**

https://github.com/sindresorhus/emittery

Sindre Sorhus

**jsontr.ee：将 JSON 结构可视化为动态 SVG 图表** —— 你可以在这个 playground 上试用，它提供了将图表下载为 PNG 的选项，或者在应用程序中使用自定义样式。

**长按识别二维码查看原文**

https://github.com/xzitlou/jsontr.ee

Lou Alcalá

**DBOS Transact v2：TypeScript 中的持久化执行框架** —— 持久化执行是指在程序运行时持续保存执行状态，这样当程序中断或崩溃时，可以从上次中断的位置恢复执行——这对长时间运行的任务或业务关键型工作流特别重要。详细文档

**长按识别二维码查看原文**

https://github.com/dbos-inc/dbos-transact-ts

DBOS, Inc.

**jscanify v1.3：JavaScript 文档扫描库** —— 给定文档的原始照片，它可以进行纸张检测（以及眩光抑制）、失真校正、高亮显示和提取。查看一些视觉示例或在这里试用。

**长按识别二维码查看原文**

https://github.com/puffinsoft/jscanify

ColonelParrot

**Ruck v9.0：Deno 的 React Web 应用程序框架** —— 一个精简的基于 React 的方式，使用 ESM、动态导入、HTTP 导入和导入映射等功能构建现代 React 应用程序，无需转译或打包。

**长按识别二维码查看原文**

https://ruck.tech/

Jayden Seric

**版本发布：**

- **Astro v5.2** —— 这个流行的框架增加了 Tailwind CSS 4 支持和更多便利功能。

- **pnpm v10.1** —— 高效的替代包管理器。

- **Prisma v6.3** —— 流行的 Node.js 和 TypeScript ORM。

- **⭐ Phaser v4 Beta 5**、**Node.js v23.7**、**npm v11.1**、**Neutralinojs v5.6**

- **OpenPGP.js v6.1** —— JavaScript 的 OpenPGP 实现。

- **wavesurfer.js v7.9** —— 波形渲染和播放。

- **Poku v3.0** —— 跨平台 JavaScript 测试运行器。