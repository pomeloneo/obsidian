# JavaScript 中文周刊 #136 - Node、Deno 的作者详细介绍了 JSR 的诞生理念和目标

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531404&idx=1&sn=728aecd23caffed3e6c3429869eea280&chksm=e921306ede56b978863e1420509dcdac583ac34a2c7f09ad712275eab9582f899ec6105e32cf\#rd  
> 抓取时间: 2026/2/2 23:51:08

---

> 本期看点：Node、Deno 的作者不久之前发布了 JSR ，并写了篇文章详细介绍了它的诞生理念和目标。Node 在这周发布了 v22，带来了一些重要的增强功能。pnpm 也发布了 v9.0，放弃了对 Node 16 和 17 的兼容性。

> 编辑：TimLi、loveloki

🔥 本周热门

**JSR 不是另一个包管理器** —— 当 Ryan 创建 Node 时，JavaScript 还没有包或标准模块系统。随着 npm 和 CommonJS 的流行，又诞生了像 Yarn 或 pnpm 这样在某些领域扩展了 npm 的工具，但在今天的 ES 模块时代，是时候进行转变了。JSR 不是一个新的 npm，而是 npm 的一种补充，使之更加安全且为现代开发量身定制。

**长按识别二维码查看原文**

https://deno.com/blog/jsr-is-not-another-package-manager

Ryan Dahl

**Node.js v22（Current）发布** —— 最新的、尖端的、主要版本的 Node 带来了一些关键的增强功能。v22 成为新的 ‘Current’ 发布版本（在 10 月份成为活跃的 LTS）。它增加了对 `require`-ing ESM 的支持，获得了一个内置的 WebSocket 客户端，升级到 V8 12.4，并包括了 一个任务运行器（例如 `node --run task_name`）。这篇博客文章 对此进行了更深入的探讨。

**长按识别二维码查看原文**

https://openjsf.org/blog/nodejs-22-available

Rafael Gonzaga

**pnpm v9.0：以效率为中心的包管理器** —— pnpm 长期以来一直是那些希望节省磁盘空间和 CPU 周期（或者因为它的优秀的 monorepo 支持）的人们的一个绝佳选择，同时保持了 npm 的大部分优点。v9.0 放弃了对 Node 16 和 17 的兼容性、尊重 `package.json` 中的 `packageManager` 字段、做了一些默认配置的更改以及采用了 Lockfile v9。

**长按识别二维码查看原文**

https://github.com/pnpm/pnpm/releases/tag/v9.0.0

**快讯：**

- 🙈 4 月 24 日是 无 JavaScript 日，这是一个完全没有 JavaScript 的日子。目的是测试下你的网站能不能脱离 JavaScript 运行。
    
    **长按识别二维码查看原文**
    
    https://js-naked-day.org/
    

- 🇫🇷 dotJS 2024 是一个将于 6 月 27 日在法国巴黎举行的 JavaScript 会议。到目前为止，演讲者名单相当吸引人。
    
    **长按识别二维码查看原文**
    
    https://www.dotjs.io/
    

- rcompat 是一个有趣的 JS 互操作性和运行时兼容性层，用于服务器，这样你就可以避免 Node、Deno 和 Bun 之间的差异。
    
    **长按识别二维码查看原文**
    
    https://primatejs.com/blog/introducing-rcompat
    

📒  教程与趣事

**迁移项目到 Bun 的故事** —— Render 的一位工程师 Eric，详细介绍了他如何将他的 Sveld 项目迁移到 Bun（在过程中替换了 Yarn 和 Vitest），包括他遇到的一些小问题，以及最后的性能提升测试结果。

**长按识别二维码查看原文**

https://render.com/blog/hello-bun-deploy-2x-faster-on-github-render

Eric Liu

**2024 年前端开发者/工程师手册** —— 一份关于当前 webdev 景观的指南，涵盖了如何快速掌握编辑器、CSS、UX、UI、命令行、工具和框架、性能、可访问性等主题。

**长按识别二维码查看原文**

https://frontendmasters.com/guides/front-end-handbook/2024/

Cody Lindley

**HTML 属性 vs DOM 属性** —— 它们是不同的，但经常被捆绑在一起。Jake 描述了它们的区别，以及为什么这很重要。

**长按识别二维码查看原文**

https://jakearchibald.com/2024/attributes-vs-properties/

Jake Archibald

**📄 使用** `**new URL()**` **的问题，以及** `**URL.parse()**` **如何解决这个问题**

**长按识别二维码查看原文**

https://kilianvalkhof.com/2024/javascript/the-problem-with-new-url-and-how-url-parse-fixes-that/

**📄** `**Intl.Segmenter**` **对象现在是基线的一部分** —— 可互操作的，区域敏感的文本分割。

**长按识别二维码查看原文**

https://web.dev/blog/intl-segmenter

**📄 Angular 中的事件分发** —— 新的事件委托系统的内部运作原理。

**长按识别二维码查看原文**

https://blog.angular.io/event-dispatch-in-angular-89d868d2351c?gi=694e57095c19

**📄 TypeScript 推断类型谓词特性的诞生全过程**

**长按识别二维码查看原文**

https://effectivetypescript.com/2024/04/16/inferring-a-type-predicate/

**📄 向现有的 TypeScript 项目添加 ESLint 和自动修复**

**长按识别二维码查看原文**

https://code.dblock.org/2024/04/23/adding-eslint-and-autofixing-an-existing-typescript-project.html

**📺 在 React 和 Svelte 中使用 TC39 提议的信号**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=HSVcZa5yTKE

**📄 如何对** `**script**` **标签中的 JavaScript 进行转义**

**长按识别二维码查看原文**

https://jameshfisher.com/2024/04/24/how-to-escape-javascript-for-a-script-tag/

🛠  代码与工具

**📊 Unovis：一个模块化的数据可视化框架** —— 适用于 React、Angular、Svelte、Vue 或普通的 JavaScript/TypeScript。处理各种事情，从 Sankey 图到地图、图表、和弦图，以及传统的线/面图。v1.4 版本 增加了以灵活方式注释可视化的支持。如果你想深入了解，这里有 一个示例画廊（带有代码）。

**长按识别二维码查看原文**

https://unovis.dev/

F5, Inc.

**ReScript v11.1 发布，改进了 JSX 支持** —— ReScript 是一个受 OCaml 启发的、类型化的语言，它编译为 JavaScript，并且语言中内置了 JSX 转换。JSX 支持以前仅用于 React 的用例，但现在也适用于 Vue、Preact 和其他方法。

**长按识别二维码查看原文**

https://rescript-lang.org/blog/release-11-1-0

ReScript 项目

**typed-xlsx：功能丰富的类型安全 Excel 报告** —— 定义一个强类型的电子表格模式，然后直接从 JavaScript/TypeScript 填充和处理表格，例如为用户生成报告 - 示例代码。基于 SheetJS 封装。GitHub 仓库。

**长按识别二维码查看原文**

https://typed-xlsx.vercel.app/

Cyprien Thao

**Devalue v5.0：类似于** `**JSON.stringify**`**，但是..** —— “当 JSON.stringify 无法完成任务时，它可以完成任务。” 即，它可以处理循环和重复的引用、正则表达式、`Map` 和 `Set`、自定义类型等等。

**长按识别二维码查看原文**

https://github.com/Rich-Harris/devalue

Rich Harris

**imask.js v7.6.0：一个 Vanilla JavaScript 输入掩码** —— 防止用户输入无效值。根据需要，为 Vue、Angular、React、Svelte 和 Solid 提供插件。

**长按识别二维码查看原文**

https://imask.js.org/

imaskjs

**browser-or-node v3.0：找出你的代码在哪里运行** —— 提供了一种简单的方法来判断你的代码当前是在浏览器中运行、在 Node 中运行、在 Web Worker 中运行，还是在 Deno 中运行。支持 ESM 和 CJS 导入。

**长按识别二维码查看原文**

https://www.npmjs.com/package/browser-or-node

Dinesh Pandiyan

**版本发布：**

- **MistCSS v0.4** —— 仅使用 CSS 创建组件，即 JS-from-CSS。v0.4 添加了 Hono 和 CSS 变量支持。

- **Accessible Autocomplete v3.0** —— 英国政府自己的自动完成输入组件。(示例。)

- **Mercurius v14.1** —— 在 Fastify 上实现 GraphQL 服务器和网关。

- **Vision Camera v4.0** —— 为 React Native 提供高级相机控制。

- **webdav-client v5.6** —— 适用于 Node 和浏览器的 WebDAV 客户端库。

- 🐍 **JSPyBridge v1.2** —— 从 Node 运行 Python 或反之亦然。

- **MUI X v7.3** —— 受欢迎的 React 组件套件。

- **React Native v0.74**

- **Electron v30.0** —— 现在基于 Chromium v124、V8 v12.4 和 Node.js v20.11.1。

- **Hexo v7.2** —— 用于博客的静态站点生成器。

- **Ember v5.8、Ionic v8、SWC v1.5、Knip v5.10.0**

🙋🏻‍♀️