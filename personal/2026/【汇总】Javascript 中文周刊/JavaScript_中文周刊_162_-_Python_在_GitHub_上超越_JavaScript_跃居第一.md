# JavaScript 中文周刊 #162 - Python 在 GitHub 上超越 JavaScript 跃居第一

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537012&idx=1&sn=85158232be66d9880c5248623d7663c6&chksm=e9211a96de5693802f5242a3088af2a30a2a4d9c2adffad7f8fd9816611785d40d142d7ab15e\#rd  
> 抓取时间: 2026/2/2 23:50:35

---

> 本期看点：Python 在 GitHub 上超越 JavaScript 跃居第一，但是有人说 TypeScript 影响了结果；JavaScript 是否应该分成两种语言？微软如何将 JavaScript Monorepo Git 大小缩减了 94%；

> 编辑：TimLi

🔥 本周热点

**Python 在 GitHub 上超越 JavaScript 跃居第一，但是…** —— 本周 GitHub Universe 大会带来了大量平台使用数据。引起社交媒体关注的是 Python 已经超越 JavaScript 成为第一大编程语言，不过很多人认为 TypeScript（现在排第三）在这方面产生了影响。好消息是，**在代码提交量方面，JavaScript 仍然排名第一**，而且过去一年 npm 包的使用量增长了 15%。

**长按识别二维码查看原文**

https://github.blog/news-insights/octoverse/octoverse-2024/

GitHub

🎉 其他 GitHub 新闻：他们的 Copilot AI 编程工具现在可以使用 Gemini 和 Claude 等其他 LLM 模型，此外，GitHub Spark 是一个新的 AI 驱动工具，用于快速创建和部署小型应用程序。

**长按识别二维码查看原文**

https://github.blog/news-insights/product-news/bringing-developer-choice-to-copilot/

**JavaScript 是否应该分成两种语言？** —— 两周前我们分享了一份有趣的演示文稿，在 TC39 会议上有人提议将 JavaScript 分成两种语言：一个基础核心版本和一个需要工具编译的完整功能版本。这篇文章深入探讨了这个话题，并在 Hacker News 上引发了广泛讨论。

**长按识别二维码查看原文**

https://devclass.com/2024/10/22/should-javascript-be-split-into-two-languages-new-google-driven-proposal-divides-opinion/

Dev Class

> 🤔 有没有可能… TypeScript 已经是那第二种语言了…？

**快讯：**

- ✂️ 最新版本的 VS Code 增加了一个实验性功能，可以在 JS/TS 文件之间复制粘贴时自动更新导入语句。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_95\#_update-imports-on-paste-for-javascript-and-typescript
    

- Lee Robinson 和 Delba de Oliveira 简要回顾了上周的 Next.js Conf 2024 及其主要公告。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/recap-next-js-conf-2024
    

- 🤖 Anthropic 的 Claude AI 系统推出了一个”analysis”工具，可以在沙箱环境中编写和运行 JavaScript，使 Claude 能够在返回答案前进行各种计算和分析。
    
    **长按识别二维码查看原文**
    
    https://www.anthropic.com/news/analysis-tool
    

- 🙋 Angular 团队正在考虑实施新的 Angular 风格指南，以适应 2024 年的标准，并希望得到你的意见。现有的风格指南写于 2016 年。
    
    **长按识别二维码查看原文**
    
    https://github.com/angular/angular/discussions/58412
    

📒 教程与趣事

**我们如何将 JavaScript Monorepo Git 大小缩减了 94%** —— 这里的”我们”指的是微软，他们有一个极其庞大的 178GB JavaScript monorepo，大到许多员工在克隆时都会遇到问题。Jonathan 在这里分享了完整的解决过程。

**长按识别二维码查看原文**

https://www.jonathancreamer.com/how-we-shrunk-our-git-repo-size-by-94-percent/

Jonathan Creamer

**如何在 JavaScript 和 TypeScript 中实现自己的身份认证** —— 一个简明的教程，介绍如何构建基于会话的身份认证系统。正如 Robin 所说，“这并不需要很复杂”。

**长按识别二维码查看原文**

https://www.robinwieruch.de/how-to-roll-your-own-auth/

Robin Wieruch

**在 React 19（和 Next.js 15）中使用 shadcn/ui** —— 来自 shadcn/ui 项目的最新文档，详细介绍了如何在 React 19 中使用这个流行的组件库，特别关注了 Next.js 15。

**长按识别二维码查看原文**

https://ui.shadcn.com/docs/react-19

shadcn

**用 JavaScript 重新实现 JavaScript 的** `**==**` **运算符** —— 这真是一次奇妙的旅程。无论你是否了解 JavaScript 的 `==` 运算符的”怪癖”，这都会让你大开眼界。

**长按识别二维码查看原文**

https://evanhahn.com/re-implementing-javascript-double-equals-in-javascript/

Evan Hahn

**HTML 表单验证被严重低估了** —— 探讨了 HTML 表单的”强大验证机制”，认为它们被低估了，并分析了为什么会出现这种情况。

**长按识别二维码查看原文**

https://expressionstatement.com/html-form-validation-is-heavily-underused

everdimension

**📄 Node.js、管道和消失的字节** —— 当将 Node 应用程序的输出通过管道传输到其他命令时，可能会出现神秘的问题。Sam Lijin

**长按识别二维码查看原文**

https://sxlijin.github.io/2024-10-09-node-stdout-disappearing-bytes

**📄 介绍新的 Svelte CLI 工具：**`**sv**` Ben McCann

**长按识别二维码查看原文**

https://svelte.dev/blog/sv-the-svelte-cli

🛠 代码与工具

**Faker v9.1：按需生成逼真的假数据** —— 可以生成姓名、简介、地址、邮编、日期、金额、交易等各种数据。我特别喜欢基于 DevTools 控制台的引导式演示，其他项目也应该考虑采用这种方式。GitHub 仓库。

**长按识别二维码查看原文**

https://fakerjs.dev/

Faker.js Team

**Fraction.js：用于处理有理数的库** —— 浮点数的不精确表示可能会导致各种问题，所以如果你需要处理分数运算，Fraction.js 能提供更高的精确度。

**长按识别二维码查看原文**

https://github.com/rawify/Fraction.js

Robert Eisele

**Fedify：构建 ActivityPub 服务器的框架** —— 如果你想用自己的应用程序加入联邦宇宙（而不是依赖 Mastodon），这个框架为你提供了所需的基础构建模块。

**长按识别二维码查看原文**

https://fedify.dev/

Hong Minhee

**Yantra：.NET Standard 的 JavaScript 引擎** —— 一个用 C# 编写的适用于 .NET Standard 的 JS 引擎，同时支持 CommonJS 和 ES 模块。

**长按识别二维码查看原文**

https://github.com/yantrajs/yantra

Yantra Team

**SVG.js：SVG 操作和动画库** —— 一个轻量级且无依赖的方案。你可以在 JSFiddle 上尝试演示。GitHub 仓库。

**长按识别二维码查看原文**

https://svgjs.dev/docs/3.2/

Various Authors

**Dependency Cruiser 16.5：依赖关系可视化工具** —— 如果你想看看输出效果，这里有一整页真实项目的依赖图示例，包括 Chalk、Yarn 和 React。

**长按识别二维码查看原文**

https://github.com/sverweij/dependency-cruiser

Sander Verweij

**🔊 WebAssembly 音频解码器** —— 针对浏览器和 Node.js 用例，这是一个基于 WASM 的音频解码库集合，支持 MPEG I/II/III、FLAC、Ogg Opus、Ogg FLAC、Opus 和 Ogg Vorbis 等格式。

**长按识别二维码查看原文**

https://github.com/eshaz/wasm-audio-decoders

Ethan Halsall

**版本发布：**

- **Node.js v22.11.0 (LTS)** —— 代号 Jod，标志着 Node v22 成为活跃的 LTS 版本，这个状态将持续到 2025 年底。

- **Node.js v23.1.0 (Current)** —— 最新的 Node 发布版本将 JSON 模块、导入属性和 `MockTimers` 测试运行器 API 标记为稳定特性。

- **📊 ApexCharts v4.0** —— 流行的 JS 图表库更新了其 SVG.js 依赖。

- **Chakra UI v3** —— 这个综合性 React 组件套件进行了完整重写。

- **jQuery UI v1.14.1**

- **📺 YouTube.js v11.0** —— YouTube 私有 API 的非官方 JS 客户端。

- **Serverless Express v4.16** —— 在 AWS Lambda、API Gateway、Lambda@Edge 等平台上运行 Express.js。现在也支持 Express 5。

- **Execa v9.5** —— Node 的强大进程执行库。现在在重定向 `stdout` 或 `stderr` 到文件时，可以选择追加而不是替换内容。

- **MUI X v7.22** —— 流行的 React 组件套件。现在支持数据网格行分组的服务器端功能。

- **🗓️ react-calendar v5.1** —— React 应用程序的”终极”日历组件。

- **📷 VisionCamera v4.6** —— React Native 的高级相机控制库。

- **Elliptic v6.6** —— 纯 JS 实现的椭圆曲线加密库。

- **Acorn v8.14** —— 小巧快速的基于 JavaScript 的 JavaScript 解析器。

- **Strapi v5.2** —— 流行的 Node.js 无头 CMS。