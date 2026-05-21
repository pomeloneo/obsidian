# JavaScript 中文周刊 #158 - VoidZero ： 尤雨溪的最新创业项目，一个前端工具链

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535588&idx=1&sn=6d3b81fcc2d531036a98fa97050e3cb5&chksm=e9210006de5689104742defd3513de2418b6520ac7392bc41688091932b73a0922a2ff9afe13\#rd  
> 抓取时间: 2026/2/2 23:50:40

---

> 本期看点：尤雨溪在 Vite 开发的过程中受到启发，于是就有了这个新的创业项目，一个下一代前端工具链，目前已经获得了 460 万美元的融资。另外，对标 Electron 的 Tauri 2.0 也发布了，带来了多项新特性。

> 编辑：TimLi

🔥 本周热点

**VoidZero：JavaScript 的下一代工具链** —— 不满足于仅仅创造了 Vue.js 和 Vite，JavaScript 大神尤雨溪揭晓了他的最新冒险：一家获得 460 万美元融资的公司，致力于为 JavaScript 生态系统构建开源统一开发工具链。

**长按识别二维码查看原文**

https://voidzero.dev/posts/announcing-voidzero-inc

尤雨溪

**ESLint 现在正式支持 JSON 和 Markdown 的代码检查** —— ESLint 一直在采取措施成为更通用的代码检查工具，这一努力开始结出硕果，达成了这一里程碑。

**长按识别二维码查看原文**

https://eslint.org/blog/2024/10/eslint-json-markdown-support/

Nicholas C. Zakas

**Tauri 2.0：使用 Web 技术构建小巧快速的桌面应用程序** —— Tauri 是一个基于 Rust 的 Electron 替代品，用于将 HTML、JavaScript 和 CSS 代码整合在一起创建跨平台桌面应用程序。它不使用 V8，而是使用本地可用的 webview 来运行你的代码。

**长按识别二维码查看原文**

https://v2.tauri.app/blog/tauri-20/

Tillmann Weidinger

**快讯：**

- 😍 构建工具 Vite 有了一个漂亮的新主页，正好赶上 ViteConf。
    
    **长按识别二维码查看原文**
    
    https://vite.dev/
    

- Svelte 团队分享了最近 Svelte 的所有新特性。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-october-2024
    

- 🕹️ OneJS 试图将 JavaScript 脚本引入 Unity 游戏引擎。▶️ 这里有一个演示视频展示了它的功能。
    
    **长按识别二维码查看原文**
    
    https://onejs.com/
    

- 🎂 代码精简工具 Knip 庆祝两周年，发布了新版本，包含改进的自动修复机制，可以自动删除代码中未使用的导出和文件。
    
    **长按识别二维码查看原文**
    
    https://knip.dev/
    

- 恭喜 Ulises Gascón 成为最新的 TC39 代表。
    
    **长按识别二维码查看原文**
    
    https://x.com/kom_256/status/1841428908660359244
    

📒 教程与趣事

**打包：过去、现在和未来** —— 一堂关于打包工具的历史课，讲述了它们的用途、解决的问题、当前生态系统，以及对这些工具潜在未来的展望。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=JUS6EPMbk0U

Devon Govett

**用函数式编程释放 JavaScript 的潜力** —— 这篇文章更关注”如何做”而不是”为什么做”，但仍是一个很好的入门指南，特别是如果你从未尝试过学习函数式编程。

**长按识别二维码查看原文**

https://janhesters.com/blog/unleash-javascripts-potential-with-functional-programming

Jan Hesters

**SVG 编码示例：手写矢量图的实用技巧** —— 探讨了手工编码 SVG 的基础知识，如何在过程中使用 JavaScript，以及实际例子来揭示常见 SVG 元素的内部工作原理。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2024/09/svg-coding-examples-recipes-writing-vectors-by-hand/

Myriam Frisano

**📄 Web Components 不是框架组件，这没什么问题** Lea Verou

**长按识别二维码查看原文**

https://lea.verou.me/blog/2024/wcs-vs-frameworks/

**📄 如何将 Electron 应用程序提交到 Mac App Store** Liu Liu

**长按识别二维码查看原文**

https://www.dolthub.com/blog/2024-10-02-how-to-submit-an-electron-app-to-mac-app-store/

**📄 为什么 Gumroad 没有选择 htmx** Sahil Lavingia

**长按识别二维码查看原文**

https://htmx.org/essays/why-gumroad-didnt-choose-htmx/

**📄 Bun 如何在不使用 V8 的情况下支持 V8 API** Ben Grant (Bun)

**长按识别二维码查看原文**

https://bun.sh/blog/how-bun-supports-v8-apis-without-using-v8-part-1

**📺 面向 JavaScript 开发者的 Laravel vs Rails 比较** Sam Lewis

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=GjB6UZuKO0

🛠 代码与工具

**🤖 assistant-ui：AI 聊天的 React 组件** —— 它不仅提供了界面组件，还集成了 Vercel AI、Langchain，以及与其他常见 LLM API（如 OpenAI）的通信功能，使你能够快速构建自己的内部 AI 聊天系统。查看示例。

**长按识别二维码查看原文**

https://github.com/Yonom/assistant-ui

Simon Farshid

**qrframe：生成”漂亮” 二维码的库** —— 这个库有点特别，因为它生成的二维码不能保证可靠扫描，但如果你能生成可扫描的二维码，它们看起来很醒目，可用于品牌/有趣的使用场景。在这里体验实时演示。

**长按识别二维码查看原文**

https://github.com/zhengkyl/qrframe

Kyle Zheng

**Superdiff v2.0：比较两个数组或对象并返回差异** —— 有两个相似的对象想看看底层的差异吗？

**长按识别二维码查看原文**

https://github.com/DoneDeal0/superdiff

antoine

**µExpress / Ultimate Express：类似 Express，但更快** —— 想象一下重新实现的 Express，具有完全的 API 兼容性，但基于 µWebSockets 并使用优化的路由器以获得更快的性能。

**长按识别二维码查看原文**

https://github.com/dimdenGD/ultimate-express

dimden

**VueFormify v1.1：Vue 的简单类型安全表单构建工具** —— 自称是”你通往表单构建自主权的门票”。这里有一个入门指南和 GitHub 仓库。

**长按识别二维码查看原文**

https://vue-formify.matenagy.me/

Máté Nagy

**pretty-print：JS 值的可自定义字符串表示** —— 生成任何值的字符串表示。类似于 `util.inspect`，但有许多额外的选项用于树形化、着色、排序、选择显示内容等。

**长按识别二维码查看原文**

https://www.npmjs.com/package/@parischap/pretty-print

Effectful Technologies Inc

**版本发布：**

- **Eleventy / 11ty v3.0** – 基于 Node.js 的静态站点生成器。

- **Tabulator v6.3** – 流行的交互式表格/数据网格控件。

- **Jiti v2.0** – Node.js 的运行时 TypeScript 和 ESM 支持。

- **pnpm v9.12** – 替代性高效包管理器。

- **🗓️ Schedule-X v2.3** – Material Design 风格的事件日历和日期选择器。

- **Summernote v0.9** – 基于 Bootstrap 和 jQuery 的简单所见即所得编辑器。

- **ng-dnd v4.0** – Angular 的拖放解决方案。（演示）

- **Prisma v5.20** – 流行的 Node.js 和 TypeScript ORM。

- **React95 v9.0** – 制作看起来像 Windows 95 的 React 应用程序。

- **Vaul v1.0** – React 的优雅抽屉组件。

- **Eruda v3.4** – 移动浏览器的控制台/开发工具。

- **BlockNote v0.16** – “Notion 风格”的基于块的编辑器。

🙋🏻‍♀️