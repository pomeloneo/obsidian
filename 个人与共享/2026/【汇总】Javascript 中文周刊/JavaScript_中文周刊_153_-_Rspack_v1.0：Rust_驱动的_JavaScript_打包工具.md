# JavaScript 中文周刊 #153 - Rspack v1.0：Rust 驱动的 JavaScript 打包工具

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534608&idx=1&sn=52ef58deaaeb6daa74f837ba6fb3892c&chksm=e92103f2de568ae439ed544e218ae3b6a60bbc2333a28ff87ded234776e906ac512825c3b13d\#rd  
> 抓取时间: 2026/2/2 23:50:47

---

> 本期看点：Rspack 是由字节 Web Infra 团队开发的一个打包工具，它的特点是兼容 webpack API 和生态系统，同时性能是 webpack 的数倍。团队现在认为它已经可以用于生产环境，并鼓励用户在基于 webpack 的项目中尝试使用它。

> 编辑：TimLi

🔥 本周热点

**Rspack v1.0：Rust 驱动的 JavaScript 打包工具** —— Rspack 并非仅仅是”又一个打包工具”，它的特点是兼容 webpack API 和生态系统，同时性能是 webpack 的数倍。团队现在认为它已经可以用于生产环境，并鼓励用户在基于 webpack 的项目中尝试使用它。

**长按识别二维码查看原文**

https://rspack.dev/blog/announcing-1-0

Rspack 贡献者

💡 Rspack 还有一系列值得关注的辅助工具，比如 Rsdoctor，这是一个用于分析和可视化构建过程的工具（适用于 Rspack 和 webpack！）

**长按识别二维码查看原文**

https://rspack.dev/blog/announcing-1-0\#rspack-stack

**2024 年如何创建 NPM 包** —— 听起来很简单，但如果你想遵循最佳实践、引入有用的工具并做到恰到好处，其中涉及很多步骤。Matt Pocock 在这里详细介绍了整个过程，如果你更喜欢看视频，还有一个 14 分钟的屏幕录像。

**长按识别二维码查看原文**

https://www.totaltypescript.com/how-to-create-an-npm-package

Matt Pocock

**快讯：**

- 🤖 v0 是 Vercel 推出的一个 AI 驱动工具，最初用于根据你提供的提示生成基于 `shadcn/ui` 的 React 组件。现在，它还支持 Vue.js。
    
    **长按识别二维码查看原文**
    
    https://v0.dev/
    

- Deno 1.46 已经发布，这可能是 1.x 系列的最后一个版本，下一步就是备受期待的 Deno 2.0。Deno 的 Node 兼容性进一步提高（现在支持 Playwright 和更多功能），并搭载了 V8 12.9。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v1.46
    

- 📊 IEEE 发布了最新的年度热门编程语言列表。JavaScript 排名第三，但 TypeScript 跃升几个名次，位列第四。
    
    **长按识别二维码查看原文**
    
    https://spectrum.ieee.org/top-programming-languages-2024
    

📒 教程与趣事

**JS 日期问题即将得到解决** —— 处理日期和时间一直是程序员头疼的问题，而 JavaScript 在这方面并没有做出太多改进。像 Moment.js 这样的库帮了大忙，但 Iago 介绍了 Temporal 提案及其功能将如何随着时间的推移开始提供更多帮助。

**长按识别二维码查看原文**

https://docs.timetime.in/blog/js-dates-finally-fixed/

Iago Lastra

**JavaScript 生成器详解** —— Jan 对解释 JavaScript 生成器的文档和文章质量感到沮丧，于是决定以更高级开发者能理解的方式来解释这个概念。

**长按识别二维码查看原文**

https://www.reactsquad.io/blog/understanding-generators-in-javascript

Jan Hesters

**从头实现一个类 React 框架** —— 虽然你可能不会真的想这么做，但至少思考这个过程可以让你更好地理解 React 引擎的工作原理。

**长按识别二维码查看原文**

https://www.rob.directory/blog/react-from-scratch

Robby Pruzan

**▶ 如何用 JavaScript 实现 2048 游戏** —— Ania 又带来了她惯常的易于理解的 JavaScript 完整游戏实现教程。这次是滑动拼图游戏 2048。（两周前她还做了井字游戏。）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=RC_SglXG4Y8

Ania Kubów

**📄 JavaScript 中唯一被广泛认可的已弃用特性** – 剧透：是 `with`。Trevor Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/the-only-javascript-feature-that-was-deprecated

**📄 使用 Set 在 JavaScript 中生成唯一随机数** Amejimaobari

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2024/08/generating-unique-random-numbers-javascript-using-sets/

**📺 Chain React 2024 大会的 21 场演讲** – 一个 React Native 活动。YouTube

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLE7tQUdRKcyb81ybEVsrk6PfxXu7pJs1i\#chainreact2024

**📄 在 Vue 自定义元素中暴露内部方法** Jaime Jones

**长按识别二维码查看原文**

https://jai.me/blog/2024-08-21-vue-custom-element-internal-methods/

**📄 React 中的接口隔离原则** Alex Kondov

**长按识别二维码查看原文**

https://alexkondov.com/interface-segregation-principle-in-react/

🛠 代码与工具

**TypeScript v5.6 发布候选版** —— 一如既往，Daniel 提供了一个史诗级的新特性综述。不过我们下周会更多地关注它，因为最终版本预计将于下周二（9 月 3 日）发布。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-6-rc/

Daniel Rosenwasser (Microsoft)

**Vuestic UI v1.10：Vue.js 3.0 UI 框架** —— 提供 60 个可定制和响应式组件，v1.10 版本实现了显著的包大小优化，引入了一个可以提高构建时性能的自定义编译器，以及其他一些小改进。GitHub 仓库在此。

**长按识别二维码查看原文**

https://ui.vuestic.dev/

Vuestic UI

**Material UI v6：流行的 React UI 设计/组件系统** —— 在十周年之际，这个流行的设计系统发布了最新的主要版本。重点改进了主题、颜色方案管理、容器查询和 React 19 支持。还有一些重新设计的模板可供参考。

**长按识别二维码查看原文**

https://mui.com/blog/material-ui-v6-is-out/

García, Bittu, Andai 等人

**npm-check-updates v17.0：将** `**package.json**` **依赖更新到最新版本** —— 这与指定版本不同。它包含一个方便的 `-i` 交互模式，让你可以查看潜在的升级，然后逐个选择是否升级。

**长按识别二维码查看原文**

https://github.com/raineorshine/npm-check-updates

Raine Revere

**Code Hike v1.0：将 Markdown 转换为丰富的交互式体验** —— 针对代码演练和交互式文档等用例，Code Hike 在创建充分利用现代 Web 的技术内容时，弥补了 Markdown 和 React 之间的差距。

**长按识别二维码查看原文**

https://codehike.org/blog/v1

Rodrigo Pombo

**Calendar.js：支持拖放的日历控件** —— 一个响应式的日历，无依赖，完全支持拖放（甚至在日历之间），并且有多种方式来管理事件，包括重复事件、导出、假期等。

**长按识别二维码查看原文**

https://github.com/williamtroup/Calendar.js

William Troup

**版本发布：**

- **Prisma v5.19** – 这个流行的 Node.js 和 TypeScript ORM 添加了”TypedSQL”，一种以类型安全的方式编写原始 SQL 查询的方法。

- **📈 billboard.js v3.13** – 流行的 D3 图表库添加了区域阶梯范围图。

- **pnpm v9.9** – 快速、节省空间的包管理器。

- React Email v3.0, Ember v5.11, Bun v1.1.26

- **📊 Perspective v3.0** – 数据可视化和分析组件。核心用 C++ 编写并编译为 WebAssembly，可以从 JavaScript 中使用。他们的主页通过一个实时示例很好地展示了它。

- **json-viewer v3.5** – 以可读、用户友好的方式显示 JSON 数据。

- **♟️ Stockfish.js v16.1** – JavaScript 国际象棋引擎。

- **jest-dom v6.5** – 用于测试 DOM 状态的 Jest 匹配器。

- **Marked v14.1** – 快速 Markdown 编译器 / 解析器。

- **Javet v3.1.5** – Java + V8。将 JS 嵌入 Java。

- **Pixi.js v8.3.4** – 快速的 WebGL 2D 引擎。

🙋🏻‍♀️