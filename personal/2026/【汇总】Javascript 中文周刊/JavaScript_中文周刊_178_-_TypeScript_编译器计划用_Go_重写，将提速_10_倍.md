# JavaScript 中文周刊 #178 - TypeScript 编译器计划用 Go 重写，将提速 10 倍

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540629&idx=1&sn=c21657f857d30ef0a74fa0c6549b25f7&chksm=e9211477de569d61139d1a97d6f3835692b6a32b7226478044531f17e0ed0f35e6ba33ab8adb\#rd  
> 抓取时间: 2026/2/2 23:50:15

---

> 本期看点：微软宣布将 TypeScript 编译器移植到 Go 语言以提升性能，Node.js v20.19.0 向后移植 require(esm) 支持并默认启用，Chrome 等浏览器新增 command 和 commandfor HTML 属性，Next.js 发布官方 API 构建指南，ECMAScript 引擎如何优化你的变量。

> 编辑：TimLi

🔥 本周热点

**TypeScript 编译器将提速 10 倍** —— 近年来，TypeScript 凭借其强类型和增强的结构化功能，彻底改变了 JavaScript 生态系统，越来越多的开发者开始依赖它。然而，TypeScript 的编译器并不特别快，但 Microsoft 的 TypeScript 团队正在通过将其移植到 Go 语言来改变这一现状！

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/typescript-native-port/

Anders Hejlsberg (Microsoft)

💡 Dr. Axel Rauschmayer 深入探讨了这次移植的细节。

**长按识别二维码查看原文**

https://2ality.com/2025/03/typescript-in-go.html

**令人困惑的 JavaScript 解析谜题** —— 看起来非常简单——仅仅 14 个字符的 JavaScript 代码——但即使我已经使用 JavaScript 29 年了，我还是答错了。提示：这与 30 年前的一个浏览器相关怪癖有关。

**长按识别二维码查看原文**

https://www.hillelwayne.com/post/javascript-puzzle/

Hillel Wayne

**快讯：**

- Node.js v20.19.0 (LTS) 是 Node 维护分支的一个重要版本，因为它对维护政策做了特例处理，向后移植了 `require(esm)` 支持，并默认启用此功能。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v20.19.0
    

- 最新版本的 Chrome（以及 Firefox 和 Safari 的预览版）支持两个新的 HTML 属性：`command` 和 `commandfor`，可以为 HTML 按钮添加声明式操作，而无需直接使用 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/command-and-commandfor
    

📒 教程与趣事

**使用 Next.js 构建 API** —— 一篇详细的官方介绍，讲解了使用 Next.js 的 App Router 和路由处理程序构建公共 API 的概念，这些 API 可以暴露给网页、移动应用程序和第三方客户端。

**长按识别二维码查看原文**

https://nextjs.org/blog/building-apis-with-nextjs

Lee Robinson

**《纽约时报》如何从 Enzyme 迁移到 React Testing Library** —— 深入探讨了《纽约时报》在不影响最终用户和其他开发者的情况下，逐步升级其 React 测试方法所面临的技术挑战和采用的策略。

**长按识别二维码查看原文**

https://open.nytimes.com/how-the-new-york-times-systematically-migrated-from-enzyme-into-react-testing-library-b3ea538d001c?gi=fc59bcc85852

Felipe Buenaño (NYT Open Team)

**ECMAScript 引擎如何优化你的变量** —— 来自 Boa JS 这个基于 Rust 的 JavaScript 引擎的作者们。

**长按识别二维码查看原文**

https://boajs.dev/blog/2025/03/05/local-variables

Boa Developers

**📄 Document Picture-in-Picture API 的使用场景** —— 一种打开浮动、始终置顶窗口（“画中画”）的方法，可以显示任意 HTML 内容。不过仅限 Chrome 支持。Jad Joubran

**长按识别二维码查看原文**

https://developer.chrome.com/blog/document-pip-use-case

**📄 使用** `**Intl.DurationFormat**` **格式化具有区域支持的时间段** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/intl-durationformat-javascript-time-durations-with-locale-support

**📄 学习 Zod 以信任你的数据和类型** Diana MacDonald

**长按识别二维码查看原文**

https://didoesdigital.com/blog/zod-overview/

**📄 你应该使用的 10 个 Angular 隐藏宝石** IE 33

**长按识别二维码查看原文**

https://medium.com/@ie33/10-hidden-gems-in-angular-that-you-should-use-152fcffde7d3

**📄 被低估的 Angular 功能** Armen Vardanyan

**长按识别二维码查看原文**

https://www.angularspace.com/underrated-angular-features/

🛠 代码与工具

**Refractor 5.0：使用 Prism 的强大虚拟语法高亮** —— 封装了强大的 Prism 语法高亮器，输出对象而不是 HTML 字符串，这样你就可以按需操作和渲染（例如在虚拟 DOM 或终端中）。同一作者的 Lowlight 提供了相同的功能，但基于 highlight.js。

**长按识别二维码查看原文**

https://github.com/wooorm/refractor

Titus Wormer

**svg2pdf.js：在浏览器中将 SVG 转换为 PDF** —— 有一个在线演示场地可以让你体验它的功能。

**长按识别二维码查看原文**

https://github.com/yWorks/svg2pdf.js

yWorks GmbH

**⌘K：快速、可组合、无样式的”命令菜单”控件** —— 主页包含了各种样式的精美示例。GitHub 仓库。需要 React 18+。

**长按识别二维码查看原文**

https://cmdk.paco.me/

Paco Coursey

**🔎 Node Modules 检查器** —— 一个在浏览器中运行 pnpm、“安装”包然后分析其依赖关系的工具。这对于分析你已经使用的包很有用，也可以用来简化你自己的项目，就像 11ty 的 Zach Leatherman 在这里做的那样。

**长按识别二维码查看原文**

https://node-modules.dev/

Anthony Fu

**PGlite：在 WebAssembly 中运行 Postgres** —— PGlite 将 Postgres 的 WASM 构建打包成一个 TypeScript 库，可以直接从 Node.js（或 Bun、Deno，甚至浏览器）运行，而且只有几兆字节大小。

**长按识别二维码查看原文**

https://github.com/electric-sql/pglite

ElectricSQL / Neon

📢 其他

以下是开发者生态圈中一些其他有趣的更新或实用资源：

- ⭐ PlanetScale 博客上有一篇关于 IO 设备和延迟的精彩介绍，配有用 JavaScript 构建的非常实用的交互式图表。
    
    **长按识别二维码查看原文**
    
    https://planetscale.com/blog/io-devices-and-latency
    

- Evil Martians 解释了如何让你的开源项目更受欢迎的考虑因素。
    
    **长按识别二维码查看原文**
    
    https://evilmartians.com/chronicles/how-to-make-your-open-source-popular
    

- 🤖 备受尊敬的 LLM 专家 Simon Willison 分享了大量见解和技巧，讲述他如何使用 LLM 帮助编写代码。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/Mar/11/using-llms-for-code/
    

**版本发布：**

- **Nuxt v3.16** —— 流行的 Vue 元框架。现在有了新的 `create-nuxt` 工具来启动项目。

- **Bun v1.2.5** —— 现在具有更好的 Node-API 兼容性，CSRF 生成和验证功能，以及众多性能改进和修复。

- **Melange v5** —— 一个 OCaml 到 JavaScript 的编译器。

- **Astro v5.5**、**Transformers.js v3.4**、**Capacitor v7.1**、**Nuxt UI v3**

- **Gleam v1.9** —— 类型安全的函数式编程语言，同时面向 Erlang VM 和 JavaScript 运行时。

- **v0.42** —— 用于使用 CSS 绘制图案的 Web 组件。

- **Faker v9.6** —— 随心所欲地生成虚构数据。

- **Choices v11.1** —— 可配置的选择框/文本输入插件。

- **🕒 Spacetime v7.8** —— 轻量级时区库。

- **Ink v5.2** —— 使用 React 构建命令行应用程序。