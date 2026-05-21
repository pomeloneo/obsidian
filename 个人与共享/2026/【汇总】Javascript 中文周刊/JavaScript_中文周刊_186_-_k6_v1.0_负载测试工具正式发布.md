# JavaScript 中文周刊 #186 - k6 v1.0 负载测试工具正式发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541531&idx=1&sn=925daaccaad235108df6e07606bbb6d8&chksm=e92168f9de56e1efa64f6d1dc4f5ae2c20c6e0fd66cd4faaac1081a7df9cbbf3d530a92b1378\#rd  
> 抓取时间: 2026/2/2 23:50:05

---

> 本期看点：k6 v1.0 正式发布，提供基于 Go 的 JavaScript 负载测试能力，展开运算符和剩余参数语法的威力，VS Code 1.100 版本发布并增强 JavaScript 开发体验，Biome 提供 Prettier 和 ESLint 的一站式替代方案。

> 编辑：TimLi

🔥 本周热点

**k6 1.0：基于 Go 的 JavaScript 负载测试工具** —— 这是一个功能齐全、可配置的负载生成工具，使用基于 Go 的 Sobek JavaScript 引擎来支持用 JavaScript 编写测试脚本。v1.0 版本承诺提供稳定性、一流的 TypeScript 支持和更好的扩展性。

**长按识别二维码查看原文**

https://github.com/grafana/k6

Grafana Labs

**Node 24（当前版本）发布** —— Node 的发布线路最近有些变化：v18 已经结束生命周期，现在 v23 让位给 v24 成为”当前”版本，适合那些需要最新特性的开发者。它带来了 npm 11、V8 13.6（新增 `RegExp.escape`、`Float16Array` 和 `Error.isError`）、默认启用的 `URLPattern` API，以及 Undici 7。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.0.0

Node.js 团队

💡 需要注意的是，Node v24.0.1 是最新版本，它暂时重新引入了一个已结束生命周期的功能，因为一些流行的依赖包出现了兼容性问题。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.0.1

**Visual Studio Code 1.100 版本发布** —— 这个版本不要和 1.1 版本混淆。此次更新为 JavaScript 开发者带来了许多好东西：改进的”下一步编辑建议”功能可以提示添加缺失的导入，支持 Node 的增强网络调试功能，改进了类型信息的可见性，支持远程 MCP 服务器，并将 GPT 4.1 设为新的默认基础模型等等。

**长按识别二维码查看原文**

https://code.visualstudio.com/updates/v1_100

Microsoft

**快讯：**

- Node.js 团队希望你能参与最新的 Node.js **Next 10** 调查，帮助指导 Node 的未来发展方向。
    
    **长按识别二维码查看原文**
    
    https://linuxfoundation.research.net/r/2025nodenext10
    

- Polycompiler 使用了一个巧妙的技巧，让你可以在同一个源文件中混合使用 Python 和 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://github.com/EvanZhouDev/polycompiler
    

- OpenJS 基金会宣布了新一届董事会成员。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/openjs-board-directors-2025
    

📖 文章

**展开运算符和剩余参数语法的威力** —— 快速了解三个小点 `...` 能带来的各种可能性。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/05/05/the-power-of-spread-and-rest-patterns-in-javascript.md/

Matt Smith

**面向 Astro 开发者的 React Server Components 指南** —— Astro 的”孤岛”架构和 React Server Components 有着惊人相似的心智模型。Dan 比较了这两者，深入探讨了一些特性，并建议如果你觉得 RSC 难以理解，Astro 可能是一个更温和的入门方式。

**长按识别二维码查看原文**

https://overreacted.io/rsc-for-astro-developers/

Dan Abramov

**从 Prettier 和 ESLint 迁移到 Biome** —— Prettier 和 ESLint 是许多 JavaScript 构建流程中的必备工具，但 Biome 提供了一个有趣的”一站式”替代方案。

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/05/07/migrating-a-javascript-project-from-prettier-and-eslint-to-biomejs.html

Damilola Olatunji

**📄 “其实 Electron 没那么糟”** —— 下次看到对 Electron 的陈词滥调式批评时，值得重读这篇文章。Vaxry

**长按识别二维码查看原文**

https://blog.vaxry.net/articles/2025-electronAintBad

**📺 三分钟解释 React 编译器** Better Stack

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=40osg7LoShc

**📄 你对 Angular 中的 DDD 理解有误** Tomasz Ducin

**长按识别二维码查看原文**

https://www.angularspace.com/youre-misunderstanding-ddd-in-angular-and-frontend/

**📄 Fastify + Vue 的故事** Jonas Galvez

**长按识别二维码查看原文**

https://hire.jonasgalvez.com.br/2025/apr/30/fastify-vue/

🛠 代码 & 工具

**HelloCSV：JavaScript 应用程序的即插即用 CSV 导入工作流** —— 如果你或你的用户需要导入 CSV 文件，这里有一个完整的前端 CSV 导入工作流，可以直接集成到你的应用程序中。基础文档在这里。

**长按识别二维码查看原文**

https://hellocsv.github.io/HelloCSV/

HelloCSV

**PptxGenJS v4.0：用 JavaScript 构建 PowerPoint 演示文稿** —— 这是一个成熟的库，可以输出符合标准的 Open Office XML 文件，兼容 PowerPoint、Apple Keynote 和其他常见演示工具。支持图形、文本、表格和其他典型的幻灯片对象。这里有很多演示示例。

**长按识别二维码查看原文**

https://github.com/gitbrent/PptxGenJS

Brent Ely

**Mantine v8.0：功能齐全的 React 组件库** —— Mantine 是最受欢迎的 React 组件库之一，这是有原因的：它功能齐全、现代化，而且外观出色。v8.0 通过集成 **Recharts** 增强了图表功能，新增了超过二十个组件（包括 GitHub 风格的热力图、树形控件和半圆进度条），还添加了子菜单等更多功能。

**长按识别二维码查看原文**

https://mantine.dev/changelog/8-0-0/

Vitaly Rtishchev 等

**Hyparquet：JavaScript 的 Parquet 文件解析器** —— Parquet 是一种流行的面向列的数据文件格式，常用于存储大型数据集进行分析。Hyparquet 是一个无依赖的 JavaScript 库，用于处理 Parquet 文件，甚至可以在浏览器中使用（看这个演示）。

**长按识别二维码查看原文**

https://github.com/hyparam/hyparquet

Hyperparam

**🔊 react-sounds：为 React 应用程序添加音效** —— 在网页中添加音效可能听起来像是噩梦，但这个项目做得很好，有精心设计的示例，找到了恰到好处的**基调**。

**长按识别二维码查看原文**

https://www.reactsounds.com/

Aedilic Inc.

**mono-jsx：将** `**<html>**` **作为** `**Response**` —— 这是一个服务器端 JSX 运行时，可以将 `<html>` 渲染为 `Response`，无需构建步骤，并且可以在多个服务器端 JS 运行时中使用。

**长按识别二维码查看原文**

https://github.com/ije/mono-jsx

Je Xia

👀 其他

以下是我们本周注意到的生态系统中的一些有趣内容：

- CSS Overflow 5 规范使得在网页上创建纯 CSS 滚动和”轮播”体验成为可能，Sara Soueidan 深入研究并进行了可访问性和可用性分析。现在是放弃基于 JavaScript 的方案的时候了吗？Sara 说还不是时候。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/carousels-with-css
    

- Sam Rose 带来了另一篇精彩的可视化文章——这次讲解”蓄水池抽样”。除了通过可视化方式学习这个有用的编程技术外，你还可以查看他为这篇文章编写的所有 JavaScript 代码。
    
    **长按识别二维码查看原文**
    
    https://samwho.dev/reservoir-sampling/
    

- 一个团队决定放弃 Next.js 转而使用 Ruby on Rails，同时保留 React 前端——这是他们讲述为什么以及如何做到这一点的故事。
    
    **长按识别二维码查看原文**
    
    https://hardcover.app/blog/part-1-how-we-fell-out-of-love-with-next-js-and-back-in-love-with-ruby-on-rails-inertia-js
    

- Postgres 18 Beta 1 已发布。Linux 上的 IO 性能是这次更新的重点。最终版本预计在 9 月或 10 月发布。
    
    **长按识别二维码查看原文**
    
    https://www.postgresql.org/about/news/postgresql-18-beta-1-released-3070/
    

- 🤖 Google 更新了其 Gemini 2.5 Pro 模型——他们声称现在在构建前端应用程序方面表现更好，特别是在”美观的网页开发”方面。
    
    **长按识别二维码查看原文**
    
    https://developers.googleblog.com/en/gemini-2-5-pro-io-improved-coding-performance/
    

附：如果你对 React 或 Node.js 感兴趣，我们在 React Status 和 Node Weekly 中有更专门的内容，也欢迎查看这些周刊的最新一期 :-)

**长按识别二维码查看原文**

https://react.statuscode.com/

**版本发布：**

- **🤖 ESLint v9.26.0** —— 这个流行的静态分析工具的一个有趣版本，它增加了对 MCP 的支持，使 ESLint 可以直接被 AI 模型和编码代理使用。

- **🗾 Mapbox GL JS v3.12** —— 在浏览器中使用 WebGL 渲染的交互式、可自定义矢量地图。

- **Relay v19** —— Facebook 的声明式 React/GraphQL 框架。

- **Material UI v7.1** —— 使用 Material Design 的 React 组件。现在兼容 Tailwind CSS 4。

- **Rspack v1.3.9**、**Babylon.js v8.7**、**Electron v36**（官方博文）

- **Prisma v6.7** —— 这个流行的 ORM 从 Rust 转向 TypeScript 的尝试正在加速。

- **Slack Send GitHub Action v2.1** —— 从 GitHub Actions 向 Slack 发送数据。

- **openid-client v6.5** —— 适用于 JS 运行时的 OAuth 2/OpenID Connect 客户端 API。

- **📄 DOCX v9.5** —— 用 JavaScript 生成 Word 文档。

- **eslint-plugin-prettier v5.4** —— 将 Prettier 作为 ESLint 规则运行。