# Node 中文周刊 #170 - TypeScript v5.8 正式发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540471&idx=1&sn=cf6a472ad457386ab94fa7666fd8aa6f&chksm=e9211515de569c0314d3f6798933b89c31281d4962f8bda3636a7a2f9c7c4c2dba6a5c9bc8fe\#rd  
> 抓取时间: 2026/2/2 23:51:49

---

> 本期看点：TypeScript v5.8 发布并增强 Node 相关特性，V8 引擎通过可变堆数字实现性能优化，Next.js v15.2 新增对 Node.js 中间件的支持，Node.js 引入基于 JSON 的实验性配置选项，Electron 应用程序模板集成 React 19 和 Tailwind CSS 4。

> 编辑：TimLi

🔥 本周热门

**TypeScript v5.8 发布** —— 经过四个月的开发，TypeScript 5.8 终于发布了，这次更新主要聚焦于 Node 相关特性。现在你可以在 `nodenext` 模块中使用 `require()` 导入 ES 模块，还新增了`node18` 模块供想继续使用 Node 18 的开发者使用。最值得注意的是新增了 `--erasableSyntaxOnly` 选项，确保不会使用任何 TypeScript 特有的运行时语义（如果你正在使用 Node 的类型擦除功能直接运行 TypeScript 代码，这个选项会很有用）。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-8/

Microsoft

**使用可变堆数字加速 V8 引擎** —— V8 团队使用 JetStream2 基准测试套件来调查性能问题，并实现了一项新的优化。这不仅让 `async-fs` 基准测试性能提升了 2.5 倍，其他方面也有所改进。这证明不仅是 Node 团队在让 Node 变得更快，V8 团队也在为此努力。

**长按识别二维码查看原文**

https://v8.dev/blog/mutable-heap-number

Victor Gomes (V8)

**使用 Playwright 进行网页爬虫** —— 虽然这种方式爬取 YouTube 可能坚持不了太久（毕竟 Google 不太喜欢这种做法），但文章展示的技术在其他场景下也很有用。

**长按识别二维码查看原文**

https://wanago.io/2025/02/24/web-scraping-playwright/

Marcin Wanago

**📄 使用 LangChain 和 OpenAI 创建命令行聊天机器人** Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/langchain-node-js-openai/

**📄 Node.js 可写流：实用指南** Pavel Romanov

**长按识别二维码查看原文**

https://pavel-romanov.com/writable-streams-in-nodejs-a-practical-guide

**📄 使用** `**node --watch**` **创建简单的 TypeScript 演练场** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/02/node-watch-typescript-playground.html

**快讯：**

- Node v23.9.0（当前版本）已发布——这是一个非常小的版本更新，主要集中在 bug 修复和渐进式改进上。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v23.9.0
    

- Next.js v15.2 已发布，新增了在 Next.js 中间件中使用 Node.js 的支持。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/next-15-2\#nodejs-middleware-experimental
    

- Node 正在引入一个实验性的基于 JSON 的配置选项，以简化那些通常需要大量配置标志的功能（如测试运行器）的使用。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/pull/57016
    

- 关于 Node.js 中 QUIC 支持的一个不太好的消息。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/issues/57281
    

🛠 代码与工具

**使用现代依赖的 Electron 应用程序模板** —— 一个基础模板应用程序，使用了 React 19、Tailwind CSS 4、shadcn/ui、Electron Vite、Biome，并包含了 GitHub Actions 发布工作流。

**长按识别二维码查看原文**

https://github.com/daltonmenezes/electron-app

Dalton Menezes

**fast-png v6.3：纯 JS 实现的 PNG 图像编解码器** —— 可以通过 TypedArray 或 Buffer 解码 PNG，或者将 Canvas ImageData（或兼容对象）编码为 PNG。

**长按识别二维码查看原文**

https://github.com/image-js/fast-png

Michaël Zasso

**Jira.js v4.1：Atlassian Jira Cloud API 的封装** —— 你有幸在使用 Jira 吗？现在可以通过代码与它交互，让你的工作更加愉快。查看更多文档和示例。

**长按识别二维码查看原文**

https://github.com/MrRefactoring/jira.js

Vladislav Tupikin

**InversifyJS v7.0：控制反转容器** —— 一个轻量级的控制反转（IoC）容器，帮助你遵循面向对象的最佳实践。

**长按识别二维码查看原文**

https://inversify.io/

Remo H. Jansen

**Malibu：框架无关的 CSRF 中间件** —— 仅支持 ESM，零依赖，包含 TypeScript 类型定义。兼容 Express、Tinyhttp 和大多数基于核心 HTTP 包的现代框架。

**长按识别二维码查看原文**

https://github.com/tinyhttp/malibu

Reinaldy Rafli

**wacat v1.4：测试你的网页应用程序应对”猫咪混乱”的能力** —— 使用虚拟的”猫咪在键盘上乱走”方式来折磨应用程序，进行随机点击和表单提交。现在更注重使用 AI 生成有效和无效的输入。

**长按识别二维码查看原文**

https://github.com/mikesmallhelp/wacat

Mika Tapanainen

📢 其他 JavaScript 相关

以下是 JavaScript 生态圈中其他一些有趣的新闻，以防你错过：

- “Ajax”这个术语是在这篇文章中首次提出的，至今已有二十年了。
    
    **长按识别二维码查看原文**
    
    https://web.archive.org/web/20080302121152/http://adaptivepath.com/ideas/essays/archives/000385.php
    

- Windows 95 in Electron 不出所料，就是在 Electron 应用程序中运行 Windows 95！v4.0 版本新增了 Office 95 和 IE 5.5，可以（有限地）浏览网页。
    
    **长按识别二维码查看原文**
    
    https://github.com/felixrieseberg/windows95/releases/tag/v4.0.0
    

- 📊 BenchJS 是一个值得尝试的在线 JavaScript 基准测试沙盒。
    
    **长按识别二维码查看原文**
    
    https://benchjs.com/
    

- free-for.dev 是一个方便且庞大（超过 1000 项）的清单，列出了具有免费开发者层级的托管工具和在线服务。
    
    **长按识别二维码查看原文**
    
    https://free-for.dev/\#/
    

**版本发布：**

- **LogTape v0.9.0** —— 适用于 JavaScript 和 TypeScript 的零依赖日志库，支持多种环境。

- **node-oracledb v6.8** —— Node 的 **Oracle Database** 驱动。现在支持区间数据类型和稀疏向量。

- **sqs-consumer v11.6** —— 通过定义异步消息处理函数，构建基于 Amazon SQS 的应用程序，无需样板代码。

- **Typegoose v12.13** —— 使用 TypeScript 类定义 Mongoose 模型。

- **Mongoose v8.12.0** —— MongoDB 对象建模工具。

- **NodeBB v4.1** —— 基于 Node.js 的论坛软件。

- **Nano ID v5.1** —— 唯一字符串 ID 生成器。

- **pnpm v10.5.2**