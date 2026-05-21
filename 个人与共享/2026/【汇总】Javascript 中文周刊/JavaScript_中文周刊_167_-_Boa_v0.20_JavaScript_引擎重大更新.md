# JavaScript 中文周刊 #167 - Boa v0.20 JavaScript 引擎重大更新

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538688&idx=1&sn=9e2b8a82a3e9c0407c8c9b8a8e1e5fab&chksm=e92113e2de569af47331935e221a4d8f60bf8e36de9a1de4c15bc36c90049be104b0d4129b9c\#rd  
> 抓取时间: 2026/2/2 23:50:29

---

> 本期看点：Boa v0.20 JavaScript 引擎在 Test262 测试中合规性提升至 89.92%，React v19 经过 8 个月 beta 测试后正式发布，Node.js 性能测试报告显示从 v18 到 v22 有显著提升，Safari 18.2 发布并新增多项 JavaScript 特性，Next.js v15.1 完整支持 React 19。

> 编辑：TimLi

🔥 本周热点

**Boa v0.20：另一款 JavaScript 编译器** —— 经过多年开发，Boa 有几个主要目标：成为一个 Rust 实现的 ECMAScript 引擎，方便嵌入到 Rust 项目中，并且整体上成为一个快速、安全的 JS 引擎。v0.20 版本在 Test262 测试套件中的合规性提升到了 89.92%，改进了 Temporal 支持，添加了 `Atomics.pause` 等功能。这绝不是一个玩具项目。

**长按识别二维码查看原文**

https://boajs.dev/blog/2024/12/05/boa-release-020

Boa 开发团队

**React v19 正式发布** —— 在2024 年 2 月的更新中首次预告后，React 19 经过 8 个月的 beta 测试终于发布。目前已有大量相关内容，包括 React v19 升级指南、编译器说明、速查表以及 Vercel 整理的 React v19 新特性汇总。

**长按识别二维码查看原文**

https://react.dev/blog/2024/12/05/react-19

React 团队

**快讯：**

- 🎮 如果你从事 JavaScript 游戏开发，现在是时候参与 2024 年 Gamedev.JS 调查了。如果你不是游戏开发者，也可以去 JS13KGames 欣赏其他人的创意作品。
    
    **长按识别二维码查看原文**
    
    https://gamedevjs.com/survey/2024/
    

- Apple 发布了 Safari v18.2，新增了一些 JavaScript 支持特性，包括 `Float16Array`、更多 `Uint8Array` 方法、`Promise.try`、`RegExp.escape` 等。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/16301/webkit-features-in-safari-18-2/
    

📒 教程与趣事

**2024 年 Node.js 性能现状** —— 一份全面的基准测试报告，涵盖了 Node.js 最近的性能改进。从 Node 18 到 20 再到 22 版本的性能提升可能会让你大吃一惊——很明显团队在这方面投入了大量工作。

**长按识别二维码查看原文**

https://nodesource.com/blog/State-of-Nodejs-Performance-2024

Gonzaga 和 Parody（NodeSource）

**使用 GitHub Actions 发布简单的客户端 JS 包到 npm** —— 在开发 Prompts.js 的过程中（这是一个为 `alert()`、`confirm()` 和 `prompt()` 提供简单 `await` 替代方案的库），Simon 想要让发布 npm 包变得更简单。

**长按识别二维码查看原文**

https://til.simonwillison.net/npm/npm-publish-github-actions

Simon Willison

**如何用 Deno 构建 SolidJS 应用程序** —— SolidJS 是一个强调细粒度响应式和最小开销的声明式 UI 库，它与 Deno 配合得很好。

**长按识别二维码查看原文**

https://deno.com/blog/build-solidjs-with-deno

Andy Jiang

**📄 构建你自己的** `**npm create**` **包** —— 你可能见过（或用过）这种脚手架工具。（另一个）Alex Chan

**长按识别二维码查看原文**

https://www.alexchantastic.com/building-an-npm-create-package

**📄 从 Webpack 迁移到 Vite 的经验总结** Roman Zaynetdinov

**长按识别二维码查看原文**

https://neon.tech/blog/from-webpack-to-vite

**📄 理解浏览器的主线程** Amrik Malhans

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2024/understanding-the-main-thread-in-the-browser/

**📺 TanStack Start vs Next.js 的真实评测** Ankita Kulkarni

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=D27AfH0pSp8

**📄 React 编译器在实际代码中的表现** Nadia Makarevich

**长按识别二维码查看原文**

https://www.developerway.com/posts/how-react-compiler-performs-on-real-code

🛠 代码与工具

**Termo：易用的网站终端控件** —— 如果你想在网站上提供终端模拟器功能（可能用于高级用户、增强文档体验，或者只是作为彩蛋），Termo 在 Xterm.js 的基础上提供了流畅的使用体验。

**长按识别二维码查看原文**

https://termo.rajnandan.com/

Raj Nandan Sharma

**🖼️ wasm-vips：基于 WebAssembly 的** `**libvips**` **图像处理** —— libvips 是一个用 C 语言编写的高效图像处理库。这个构建通过 WebAssembly 提供了在浏览器、Node 和 Deno 中使用它的同构方案。（这里有一个交互式演示。）

**长按识别二维码查看原文**

https://github.com/kleisauke/wasm-vips

Kleis Auke Wolthuizen

**Civet v0.9：用更少的代码做更多事的 TypeScript 超集** —— 这个项目已有两年历史且维护良好，提供了一种有趣的编程方式。它像 JavaScript 但采用 Python 风格的缩进、链式比较、内置 JSX 等特性。这个示例就展示了它在编写更简洁代码方面的潜力。

**长按识别二维码查看原文**

https://civet.dev/

Daniel X Moore 和贡献者们

**Rockpack v5.0：另一个 React 应用程序启动器** —— 这是一个类似 Create React App 的工具，旨在尽可能缩短 React 项目的设置时间，包含服务器端渲染支持、打包、代码检查和测试功能。GitHub 仓库。

**长按识别二维码查看原文**

https://alexsergey.github.io/rockpack/

Alex Sergey

**jsesc：获取任何数据的 ASCII 安全字符串表示** —— 类似 `JSON.stringify()`，但它返回 JavaScript 代码，因此可以支持 Map、Set 和 `BigInt` 等类型。

**长按识别二维码查看原文**

https://github.com/mathiasbynens/jsesc

Mathias Bynens

**版本发布：**

- **📊 Perspective v3.2（上图）** —— 数据可视化和分析组件。核心用 C++ 编写并编译为 WebAssembly，可以通过 JavaScript 使用。他们的主页通过实时示例很好地展示了功能。现在支持换行分隔的 JSON（ndjson）。

- **VS Code 11 月更新** —— 现在复制粘贴 JS/TS 代码时，VS Code 可以自动添加导入语句。

- **Next.js v15.1** —— 这个流行的 React 框架现在完全支持 React 19。

- **Node v23.4.0（当前版本）** —— 新增 `assert.partialDeepStrictEqual` 和用于跟踪环境变量使用的 `-trace-env`。

- **Sheriff v25** —— 一个偏好性的 TypeScript 优先的 ESLint 配置。现在支持 ESLint v9。

- **Undici v7.1** —— Node.js HTTP 库的 HTTP/2 支持现已标记为稳定。

- **pnpm v9.15**、**Dependency Cruiser v16.8**、**Redux Toolkit v2.5**、**YouTube.js v12.2**

- **☎︎ International Telephone Input v25.2** —— 用于输入和验证国际电话号码的组件。支持 Vue、React 和原生 JS。

- **debug v4.4** —— 仿照 Node.js 核心调试方法的轻量级调试工具（也支持浏览器）。

- **ExpressoTS v3.0** —— 用于服务器端 Node.js 应用程序的 TypeScript 框架。

- **InversifyJS v6.2** —— JavaScript 的控制反转容器。

- **📊 ApexCharts v4.2** —— 流行的 JS 图表库。（演示）

- **Vue3-Carousel v0.9** —— 可定制的轻量级 Vue 3 轮播组件。

- **html-react-parser v5.2** —— 同构的 HTML 到 React 解析器。

- **AlaSQL.js v4.6** —— 同构的 JavaScript SQL 数据库。