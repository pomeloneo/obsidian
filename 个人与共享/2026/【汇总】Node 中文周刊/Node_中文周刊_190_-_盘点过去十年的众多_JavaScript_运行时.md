# Node 中文周刊 #190 - 盘点过去十年的众多 JavaScript 运行时

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542940&idx=1&sn=43fb99e1e78a320192a99351189356e6&chksm=e921637ede56ea6893ca36cebf0c8894ac9cc8f7f8c95b6c0cd34c08ee50d45d5d68cb5b2a3b#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542940&idx=1&sn=43fb99e1e78a320192a99351189356e6&chksm=e921637ede56ea6893ca36cebf0c8894ac9cc8f7f8c95b6c0cd34c08ee50d45d5d68cb5b2a3b#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542940&idx=1&sn=43fb99e1e78a320192a99351189356e6&chksm=e921637ede56ea6893ca36cebf0c8894ac9cc8f7f8c95b6c0cd34c08ee50d45d5d68cb5b2a3b#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542940&idx=1&sn=43fb99e1e78a320192a99351189356e6&chksm=e921637ede56ea6893ca36cebf0c8894ac9cc8f7f8c95b6c0cd34c08ee50d45d5d68cb5b2a3b#rd)

---

> 本期看点：过去十年的众多 JavaScript 运行时生态系统全面回顾，Node 开发者的 Unix Domain Sockets 指南，Bun 创始人谈 Bun 开发和 Node.js 兼容性策略，Transformers.js v3.7 新增 Voxtral 语音转录支持，AudioTee.js 提供 Node.js 的 macOS 系统音频捕获功能。

> 编辑：TimLi

🔥 本周热门

**过去十年的众多 JavaScript 运行时** —— 这是一篇内容丰富的文章（花了一年时间完成），涵盖了过去和现在的众多 JavaScript 运行时和引擎，从众所周知的 Node.js 到云平台，以及一些鲜为人知的”值得一提”的项目。这是一篇很好的文章，可以帮助你全面了解 JS 生态系统。

**长按识别二维码查看原文**

https://buttondown.com/whatever_jamie/archive/the-many-many-many-javascript-runtimes-of-the-last-decade/

Whatever, Jamie

**Node 开发者的 Unix Domain Sockets 指南** —— 简单来说：在 Node.js IPC 通信中，Unix domain sockets 比 TCP loopback 的延迟低约 50%。

**长按识别二维码查看原文**

https://nodevibe.substack.com/p/the-nodejs-developers-guide-to-unix

Pavel Romanovw

**▶ Bun 创始人谈 Bun 开发和 Node.js 兼容性** —— 这是一段大约半小时的对话，Patrick Akil 与 Bun 的创始人 Jarred Sumner 进行交谈。“我们希望 Bun 能够无缝替代现有的 Node.js 生态系统。我们的大部分工程时间其实并不是花在新功能上，而是花在 Node.js 兼容性上。”

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VGjJWXFYyQo

React Conferences by GitNation

**📄 如何构建向 LLM 暴露数据资源的 Node.js MCP 服务器** Liran Tal

**长按识别二维码查看原文**

https://snyk.io/articles/how-to-build-node-js-mcp-servers-that-expose-data-resources-to-llms/

**📄 多仓库 TypeScript 问题** —— 解决跨仓库类型安全问题。David Moores

**长按识别二维码查看原文**

https://www.carrick.tools/blog/the-multi-repository-typescript-problem

**📄 JavaScript 中的逻辑赋值运算符：小语法，大收益** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/07/28/logical-assignment-operators-in-javascript-small-syntax-big-wins/

快讯：

- TypeScript 5.9 RC 已发布，最终版本将于本周晚些时候发布。主要亮点包括对 `import defer` 和新的 `-module node20` 特性的支持。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-9-rc/
    

- 虽然还处于早期阶段，但 Google 已推出 OSS Rebuild，这是一项通过允许比较包与上游制品来提高开源生态系统（如 npm）安全性的尝试。
    
    **长按识别二维码查看原文**
    
    https://security.googleblog.com/2025/07/introducing-oss-rebuild-open-source.html
    

- npm 生态系统遭受的攻击仍在继续，`is` 包被劫持，攻击者通过使用与 npm 相关的域名钓鱼来窃取登录信息。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/172337/web
    

🛠 代码 & 工具

**AudioTee.js：Node.js 的 macOS 系统音频捕获工具** —— 这个工具封装了一个（内置的）基于 Swift 的二进制文件，可以捕获 Mac 系统音频输出，并定期以 PCM 编码的数据块形式发送。GitHub 仓库。

**长按识别二维码查看原文**

https://stronglytyped.uk/articles/audioteejs-macos-system-audio-capture-nodejs

Nick Payne

**Transformers.js v3.7：Web 端机器学习和模型** —— 通过 ONNX 在浏览器中运行强大的预训练模型，同时也支持在 Node.js 中进行服务器端推理。v3.7 新增了 Voxtral（语音转录和音频理解）、LFM2 和 ModernBERT 支持。

**长按识别二维码查看原文**

https://github.com/huggingface/transformers.js/releases/tag/3.7.0

Hugging Face

**match-sorter v8.1：确定性最佳匹配数组排序** —— 如果你需要以确定性方式过滤和排序数组项，match-sorter 提供了一个明确的、可预测的算法。你可以在这里体验在线演示。

**长按识别二维码查看原文**

https://github.com/kentcdodds/match-sorter

Kent C. Dodds

📢 其他生态

以下是生态系统中其他一些有趣的故事：

- 一位开发者分享了如何使用 Node.js 和 Postmark 构建邮件控制的 Game Boy 模拟器。这里有更多信息，包括代码链接。
    
    **长按识别二维码查看原文**
    
    https://postmarkapp.com/blog/how-a-developer-built-an-email-controlled-game-boy-emulator-with-postmark-because-why-not
    

- es-toolkit 现在已经成为 100% 兼容的 Lodash 替代品。
    
    **长按识别二维码查看原文**
    
    https://es-toolkit.dev/
    

- 2025 年 HTML 现状调查现已开放参与——这不仅仅是一个调查，你还能在参与过程中学到一些新知识。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-html/2025
    

- 一位开发者声称 tabs vs spaces 之争已经结束，大多数编程语言倾向于使用空格。
    
    **长按识别二维码查看原文**
    
    https://xn–gckvb8fzb.com/tabs-vs-spaces-the-war-is-over/
    

**版本发布：**

- **Inquirer v12.9** —— 常用的交互式终端应用程序输入提示集合。

- **Node File Trace v0.30** —— 依赖追踪工具，用于精确确定应用程序运行所需的文件。

- **MongoDB Node.js Driver v6.18** —— 最新的官方 MongoDB 驱动发布，附带详尽的发布说明。

- **node-rate-limiter-flexible v7.2** —— 原子计数器和速率限制工具。现在支持 Drizzle ORM。

- **Ghost v6.0 RC** —— 这个流行的博客/发布平台即将发布下一个主要版本。

- **@google-cloud/bigtable v6.2** —— Google Cloud Bigtable 的 Node 客户端。

- **Axios v1.11** —— 长期存在的基于 Promise 的同构 HTTP 客户端。

- **TIFF v7.1** —— 纯 JS 的 TIFF 图像解码库。

- **ESLint v9.32.0**