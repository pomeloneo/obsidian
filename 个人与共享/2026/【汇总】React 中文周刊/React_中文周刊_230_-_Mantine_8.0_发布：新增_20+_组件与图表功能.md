# React 中文周刊 #230 - Mantine 8.0 发布：新增 20+ 组件与图表功能

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541499&idx=1&sn=866e0d3f1886d258a069b2307b81a058&chksm=e9216919de56e00f608aeaf7b8ae8ba079100b67087b2813247195c51b90e5b89e790c876590\#rd  
> 抓取时间: 2026/2/2 23:42:17

---

> 本期看点：Mantine 8.0 发布并集成 Recharts 增强图表功能，写给 Astro 开发者的 RSC 指南，Relay v19 发布并兼容 React 19，react-sounds 为 React 应用程序添加音效，Redis 8.0 重新开源。

> 编辑：TimLi

🔥 本周热门

**Mantine 8.0：功能丰富的 React 组件库** —— Mantine 是最受欢迎的 React 组件库之一，这绝非偶然：它功能齐全、现代化，而且界面美观。v8.0 版本通过集成 Recharts 增强了图表功能，新增了超过 20 个组件（包括 GitHub 风格的 Heatmap、Tree 和 SemiCircleProgress），还添加了子菜单等众多新特性。

**长按识别二维码查看原文**

https://mantine.dev/changelog/8-0-0/

Vitaly Rtishchev 等

**写给 Astro 开发者的 React Server Components 指南** —— Astro 的”孤岛”架构与 React Server Components 在思维模型上有着惊人的相似之处。Dan 对这两者进行了比较，深入探讨了一些特性，并建议如果你对 RSC 感到困惑，不妨先从 Astro 入手，它可能是一个更温和的切入点。

**长按识别二维码查看原文**

https://overreacted.io/rsc-for-astro-developers/

Dan Abramov

**复杂 React/Next.js 应用程序的可靠数据获取架构** —— “我在 React 和 Next.js 应用程序中如何使用’三层数据’架构模式来避免常见陷阱、技术债务，并提升性能。”

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/fetching-data-for-complex-next-and-react-apps

Trevor I. Lasn

**📺 三分钟解释 React Compiler** Better Stack

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=40osg7LoShc

**📄 在 Clojure 中实现 React Server Components** Roman Liutikov

**长按识别二维码查看原文**

https://romanliutikov.com/blog/towards-react-server-components-in-clojure-part-1

**📄 将 React 渲染视为 OCaml 模式** Nick Yang

**长按识别二维码查看原文**

https://uptointerpretation.com/posts/ocaml-modes-for-react/

**快讯：**

- 一位匿名 Reddit 用户分享了某大型科技公司招聘 React 开发者的具体流程。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/reactjs/comments/1k5ft9d/a_real_example_of_a_big_tech_react_tech_screen/?rdt=64983
    

- 🇺🇸 React Conf 2025 将于今年 10 月在拉斯维加斯郊外举行，地点与去年相同。
    
    **长按识别二维码查看原文**
    
    https://conf.react.dev/
    

- Tiptap 3.0 Beta —— 这款无头富文本编辑器框架的最新版本已发布 beta 版。
    
    **长按识别二维码查看原文**
    
    https://tiptap.dev/tiptap-editor-v3
    

🛠 代码与工具

**react-sounds：为 React 应用程序添加音效** —— 在网页中添加音效可能听起来像是一场噩梦，但这个项目做得相当出色，提供了精心设计的示例，音效恰到好处。

**长按识别二维码查看原文**

https://www.reactsounds.com/

Aedilic Inc.

**Relay v19：Facebook 的声明式 React/GraphQL 框架** —— Relay 很有趣，它来自 Facebook 但不是 React 团队开发的，最初是为 Facebook 应用程序中的 React Native 部分创建的。Relay v19 现已兼容 React 19。

**长按识别二维码查看原文**

https://github.com/facebook/relay/releases/tag/v19.0.0

Meta

**mono-jsx：将** `**<html>**` **作为** `**Response**` —— 一个服务端 JSX 运行时，可以将 `<html>` 渲染为 `Response`，无需构建步骤，并且支持多种服务端 JS 运行时（如 Node、Deno、Bun、Cloudflare Workers 等）。

**长按识别二维码查看原文**

https://github.com/ije/mono-jsx

Je Xia

**PptxGenJS 4.0：使用 JavaScript 构建 PowerPoint 演示文稿** —— 这是一个成熟的库，可以输出符合标准的 Open Office XML 文件，兼容 PowerPoint、Apple Keynote 和其他常见演示工具。支持图形、文本、表格等典型幻灯片对象。提供了大量演示示例。

**长按识别二维码查看原文**

https://github.com/gitbrent/PptxGenJS

Brent Ely

📢 其他 JavaScript 相关内容

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- 🤖 Google 更新了 Gemini 2.5 Pro 模型 —— 他们声称现在在构建前端应用程序方面有了显著提升，特别是在美观的网页开发方面。
    
    **长按识别二维码查看原文**
    
    https://developers.googleblog.com/en/gemini-2-5-pro-io-improved-coding-performance/
    

- Node v24.0.0（当前版本）昨天发布，包含 V8 13.6、npm 11、Undici 7，并将 `URLPattern` 作为全局对象暴露出来用于 URL 模式匹配。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v24.0.0
    

- Bun v1.2.12 发布，进一步增强了 Node.js 兼容性。作为 Bun 新的全栈重点，你现在可以将浏览器控制台日志通过 Bun 流式传输到终端。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.12
    

- Dr. Axel Rauschmayer 深入探讨了 JavaScript 中的值转字符串以及可能遇到的一些陷阱。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/04/stringification-javascript.html
    

- 目前处于 TC39 第 3 阶段的 ECMAScript 显式资源管理提案已在 Chrome 134+ 和 Node 24 中实现。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-explicit-resource-management
    

- 如果你因为 2024 年的许可证争议而避免使用 Redis，那么好消息来了：Redis 从 8.0 版本开始重新开源。
    
    **长按识别二维码查看原文**
    
    https://antirez.com/news/151
    

**版本发布：**

- **DOCX v9.5** —— 使用 JavaScript 生成 Word 文档。这里有一个示例展示了如何将其集成到 React 应用程序中。

- **Material UI v7.1** —— 使用 Material Design 的独立 React 组件。现在可以与 Tailwind CSS 4 配合使用。

- **React Modal Sheet v4.4** —— 使用 Framer Motion 构建的灵活底部弹出层组件，提供流畅的过渡效果（查看演示）。

- **react-resizable-panels v3.0** —— 用于可调整大小的面板组/布局的组件。

- **React Stripe.js v3.7** —— Stripe.js 和 Stripe Elements 的 React 组件。

- **motion v12.10** —— 一个现代化的 React 和 JavaScript 动画库。

- **virtua v0.41** —— 快速、轻量的虚拟列表（和网格）组件。

- **React Chrono v2.7** —— 现代化时间线组件。

- **MUI X v8.2** —— 流行的 React 组件套件。