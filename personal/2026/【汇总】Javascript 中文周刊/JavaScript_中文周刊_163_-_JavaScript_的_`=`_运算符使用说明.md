# JavaScript 中文周刊 #163 - JavaScript 的 `??=` 运算符使用说明

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537289&idx=1&sn=b39c4646016da5ac198890a3f0555b1c&chksm=e921196bde56907d80eedabe6e0fc8a0bba9a8f0f7b88fee157a7751e07af2af7870ffeaf7e3\#rd  
> 抓取时间: 2026/2/2 23:50:34

---

> 本期看点：`??=` 空值合并赋值运算符应该如何使用；Rspack v1.1 发布；Wasmer 新增 Node.js 和 Bun 支持；如何改进核心网页指标；

> 编辑：TimLi

🔥 本周热点

**JavaScript 的** `**??=**` **运算符：简化默认值设置** —— `??=` 空值合并赋值运算符是在几年前通过 ECMAScript 2021 悄然进入 JavaScript 的，现在已经得到广泛支持。Trevor 在这里展示了如何用它来简化赋值操作。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/javascript-nullish-coalescing-assignment-operator

Trevor I. Lasn

💡 他还写了一篇关于管道运算符 `|>` 的文章，不过这个特性目前还只是一个提案。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/javascript-pipeline-operator

**🇺🇸 JSConf 回归，这是详细信息** —— 两个月前，OpenJS Foundation 宣布知名的 JSConf 品牌加入该基金会，并将举办新的北美 JSConf 活动。现在你可以在日历上标记 2025 年 10 月 14-16 日，这场活动将在美国马里兰州切萨皮克湾地区举行。

**长按识别二维码查看原文**

https://openjsf.org/blog/why-attend-jsconf-na-2025

OpenJS Foundation

**Rspack v1.1 发布** —— Rspack 是一个基于 Rust 的高速 Webpack 替代品，保持相同的 API。v1.1 比 v1.0 快了 10%，并改进了增量构建功能（仍处于实验阶段）。如果你追求超快的构建速度，这个工具值得关注。

**长按识别二维码查看原文**

https://rspack.dev/blog/announcing-1-1

The Rspack Team

**快讯：**

- 🏆 OpenJS Foundation 在”无名英雄”和”教育先锋”等类别中表彰了六位 JavaScript 开发者。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/2024-javascriptlandia-community-award-categories-a
    

- JSR 包注册表的工作组召开会议制定计划，讨论开放治理模式和改进 JS 包管理的路线图。
    
    **长按识别二维码查看原文**
    
    https://jsr.io/
    

- ⚠️ Phylum 分析了一个正在进行的域名欺骗活动，该活动试图诱骗 JavaScript 开发者安装恶意包。
    
    **长按识别二维码查看原文**
    
    https://blog.phylum.io/supply-chain-security-typosquat-campaign-targeting-puppeteer-users/
    

- 距离 State of React 2024 调查结束还有不到两周时间。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-react/2024
    

- Storybook 预览了他们的快速 UI 测试工具 Storybook Test。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/storybook-test-sneak-peek/
    

📒 教程与趣事

**Wasmer 新增 Node.js 和 Bun 支持** —— Wasmer 是一个基于 Rust 的 WebAssembly 运行时。Wasmer 5.0 增加了 V8 和 JavaScriptCore 后端支持，这意味着你可以尝试各种有趣的操作，比如在你的 JavaScript 应用程序中运行 Clang、Python，甚至是编译后的 JavaScript 应用程序。

**长按识别二维码查看原文**

https://wasmer.io/posts/wasmer-js-sdk-now-supports-node-and-bun

Syrus Akbary

**为什么会有人需要生成器函数？** —— 这是一篇经典好文，我很喜欢重读它，因为它讲解了一个经常被误解且不太常见的 JavaScript 特性。

**长按识别二维码查看原文**

https://jrsinclair.com/articles/2022/why-would-anyone-need-javascript-generator-functions/

James Sinclair

**改进核心网页指标的最有效方法** —— 每个人都希望自己的网站性能尽可能好，特别是当 Google 将性能作为排名因素时。Google 在这里分享了多种实用技巧来改善你的 INP、LCP 和 CLS 指标。

**长按识别二维码查看原文**

https://web.dev/articles/top-cwv

Google

**为什么代码安全很重要——即使在加固环境中** —— 一篇图文并茂的文章，深入探讨了恶意方如何将 Node.js 应用程序中的文件写入漏洞转变为远程代码执行漏洞，即使在只读文件系统中也是如此。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/why-code-security-matters-even-in-hardened-environments/

Stefan Schiller (Sonar)

**用 JavaScript 生成随机迷宫** —— 一个有趣且讲解清晰的基础迷宫生成过程教程。

**长按识别二维码查看原文**

https://cloudfour.com/thinks/generating-random-mazes-with-javascript/

Paul Hebert

类似有趣的内容还有 Chris MMO 的生成杠杆门谜题。

**长按识别二维码查看原文**

https://blog.reconquer.online/generating-lever-door-puzzles

📄 **Bun 如何在不使用 V8 的情况下支持 V8 API（第二部分）** Ben Grant (Bun)

**长按识别二维码查看原文**

https://bun.sh/blog/how-bun-supports-v8-apis-without-using-v8-part-2

📄 **如何创建带无限滚动的有机文本变形效果** —— 这里有一个在线演示，效果很惊艳，但可能会让人眼花。Jorge Toloza

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/11/06/how-to-create-an-organic-text-distortion-effect-with-infinite-scrolling/

📄 **Vercel 对 Next.js 进行修改以简化自托管** Loraine Lawson (The New Stack)

**长按识别二维码查看原文**

https://thenewstack.io/vercel-makes-changes-to-next-js-to-simplify-self-hosting/

📄 **Angular 变更检测的最新进展——你需要知道的一切** Krzysztof Skorupka

**长按识别二维码查看原文**

https://angular.love/the-latest-in-angular-change-detection-zoneless-signals/

🛠 代码与工具

**npmpackage.info：在单页查看详细包信息** —— 给这个在线工具输入一个 npm 包的名称，你就能获得该项目的主要统计数据的”仪表板”视图，包括质量评分、提交记录、未解决问题、发布版本、包大小等信息。

**长按识别二维码查看原文**

https://npmpackage.info/

Shrinath Nayak

**📊 NPM Chart** 是另一个很酷的新网站，专注于展示 npm 包的下载统计数据。

**长按识别二维码查看原文**

https://npm.chart.dev/

**Docusaurus v3.6：面向文档的静态站点生成器** —— Meta 的 Docusaurus 是一个流行的文档站点构建工具（看这些示例）。v3.6 专注于性能提升，现在使用 Rspack 和 SWC 等工具使构建速度超快。

**长按识别二维码查看原文**

https://docusaurus.io/blog/releases/3.6

Meta

**Immutable.js v5.0：JavaScript 的不可变集合** —— 提供多种持久性不可变数据结构，包括列表、栈、映射、有序映射、集合、有序集合和记录。

**长按识别二维码查看原文**

https://immutable-js.com/

Lee Byron and Contributors

**Sonner v1.7：React Toast 通知组件** —— 主页上有实时演示，也可以查看 GitHub 仓库。v1.7 主要改进了动画、浏览器支持和 React 19 兼容性。

**长按识别二维码查看原文**

https://sonner.emilkowal.ski/

Emil Kowalski

**Quaternion.js：JavaScript 四元数库** —— 上周我们介绍了作者的 Fraction.js 库，现在我们更进一步，提供了一种使用四元数处理 3D 旋转的方法。

**长按识别二维码查看原文**

https://github.com/rawify/Quaternion.js

Robert Eisele

**版本发布：**

- **VitePress v1.5** —— Evan You 开发的基于 Vite 和 Vue 的静态站点生成器。

- **create-vue v3.12** —— 推荐的 Vite 驱动的 Vue 项目启动方式。现在带有实验性的 Oxlint 集成。

- **ESLint v9.14.0** —— 现在支持导入属性和正则表达式修饰符。

- **Mermaid v11.4** —— 这个流行的图表工具新增了看板图。

- **React Navigation 7**、**Electron 33.1**、**TinyMCE 7.5.0**、**Bun v1.1.34**

- **BlockNote v0.19** —— 类 Notion 的基于块的编辑器。现在支持列布局和客户端导出为 `.docx` 和 PDF。项目主页有演示。

- **🔐 OpenPGP.js v6.0** —— JavaScript 的 OpenPGP 实现，现在支持新版 OpenPGP 规范 RFC 9580。

- **Fastify v5.1** —— 快速、低开销的 Node.js Web 框架。

- **xr v6.4** —— 为 React Three Fiber 应用程序带来 VR/AR 功能。

📗 课外读物

这里还有一些不是专门关于 JavaScript 的有趣文章：

🫣 **奇怪的词法语法** 作者：Justine Tunney —— Justine 正在构建一个语法高亮器，她在一个月内学习了 42 种编程语言来找出边界情况。她讲述了在各种语言（包括 JavaScript）的语法中发现的令人惊讶的特点。

**长按识别二维码查看原文**

https://justine.lol/lex/

👻 **购买域名前，先检查它是否”闹鬼”** 作者：Bryan Braun —— 为副项目购买域名总是很有趣，但如果该域名之前被用于不良目的并带来了负面影响，那就不那么有趣了。

**长按识别二维码查看原文**

https://www.bryanbraun.com/2024/10/25/before-you-buy-a-domain-name-first-check-to-see-if-its-haunted/

🤔 **什么有大小写区分但既不是大写也不是小写？** 作者：Raymond Chen —— 这听起来像个谜语，但实际上确实存在一些 Unicode 字符，它们有大小写区分，但本身既不是大写也不是小写。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/oldnewthing/20241031-00/?p=110443