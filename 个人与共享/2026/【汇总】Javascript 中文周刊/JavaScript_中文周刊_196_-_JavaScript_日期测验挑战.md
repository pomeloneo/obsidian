# JavaScript 中文周刊 #196 - JavaScript 日期测验挑战

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542713&idx=1&sn=38c033be6b0df1597e63e0e82206b6ca&chksm=e9216c5bde56e54d2f6db76839b7ab01ab982a0b0d4500796dddd40f853d543b30ede32aaec3\#rd  
> 抓取时间: 2026/2/2 23:49:52

---

> 本期看点：你对 JavaScript 日期了解多少？来试试这个测验吧，Next.js v15.4 发布并预告 v16 新特性，2025 年如何创建一个 NPM 包，WebAssembly 应用场景讨论，Vue 3.6 Alpha 和 Nuxt v4.0 发布。

> 编辑：TimLi

🔥 本周热点

**JavaScript 日期测验** —— 准备好被惹恼了吗？JavaScript 原生的日期解析功能以其晦涩难懂而闻名，稍不注意就会带来意想不到的结果。在我们等待 Temporal API 广泛可用之前，不妨来测试一下你对 JavaScript 日期处理的认知和假设吧，这个测验很有教育意义。

**长按识别二维码查看原文**

https://jsdate.wtf/

Sam Rose

**Next.js v15.4 发布（以及 Next.js 16 即将带来的新特性）** —— 这是一个相对较小的版本更新，主要改进了性能、稳定性和 Turbopack 兼容性。文章还很好地总结了 Next.js 16 即将推出的新功能。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15-4

Jimmy Lai 和 Zack Tanner

**WebAssembly：是的，但用在哪里？** —— 在 ACM Queue 上，一位参与过多个 JavaScript 和 WebAssembly（WASM）实现的贡献者分享了 WebAssembly 目前的应用场景，包括浏览器端和服务器端。文章还介绍了它是如何逐渐渗透到各个领域的。

**长按识别二维码查看原文**

https://queue.acm.org/detail.cfm?id=3746171

Andy Wingo / ACM

**快讯：**

- Vue 3.6 Alpha 版本已发布，预览了即将推出的新特性。其中最重要的是 **Vapor Mode**，它可以将单文件组件编译成更高效的形式。
    
    **长按识别二维码查看原文**
    
    https://github.com/vuejs/core/releases/tag/v3.6.0-alpha.1
    

- React Native 正在添加 Node-API 支持，这将为代码共享、构建优化以及将现有包引入 React Native 生态系统带来更多可能性。
    
    **长按识别二维码查看原文**
    
    https://www.callstack.com/blog/announcing-node-api-support-for-react-native
    

- Node.js 团队正在讨论是否将 Node 改为每年发布一个主要版本（目前是每年两次）。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/Release/issues/1113
    

- 现在你可以在 Node.js 中运行 Laravel（PHP）应用程序了。
    
    **长按识别二维码查看原文**
    
    https://blog.platformatic.dev/laravel-nodejs-php-in-watt-runtime
    

📖 文章和视频

**2025 年如何创建一个 NPM 包** —— 这是 JavaScript 开发中最基本的任务之一，但如果你想遵循最佳实践、集成有用的工具并把一切都做对，就需要完成很多步骤。Matt Pocock 在这里总结了整个过程。

**长按识别二维码查看原文**

https://www.totaltypescript.com/how-to-create-an-npm-package

Matt Pocock

**从代码看 React 的历史** —— 这是一篇史诗级文章，追溯了 React 从 Facebook 诞生到现在的演变历程。它阐明了 React 的核心理念以及重大决策背后的动机。这是一个很好的方式来加深你对 React 整体故事的理解。

**长按识别二维码查看原文**

https://playfulprogramming.com/posts/react-history-through-code

Corbin Crutchley

**▶ JavaScript 的不为人知的故事** —— 两个月前，Deno 团队分享了 JavaScript 简史，详细介绍了从 1994 年到现在 JavaScript 每年的发展历程。这个视频用 8 分钟的时间涵盖了相同的内容。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=TYsPrXWgNS8

Deno

**更好的** `**Promise.all()**` **—— 实用类型和函数** —— 介绍了一些实用的类型和函数，可以让深层 Promise 处理变得更加符合人体工程学且类型安全。

**长按识别二维码查看原文**

https://spin.atomicobject.com/better-promise-all/

Nick Keuning

**📄 使用 Web Speech API 让你的网站开口说话** —— 一个简单直接的教程。Andrew Magill

**长按识别二维码查看原文**

https://magill.dev/post/make-your-website-talk-with-the-javascript-web-speech-api

**📄 我是如何找到绕过 Google 最新反广告屏蔽更新的方法的** —— 一个巧妙的 JavaScript 技巧（现在已在 Chrome 中修复）。Derin Eryilmaz

**长按识别二维码查看原文**

https://0x44.xyz/blog/web-request-blocking/

**📄 使用 Babylon.js 构建 3D 产品配置器** —— 如何在网页上实现可配置的 3D 模型。Josh Sanderson

**长按识别二维码查看原文**

https://spin.atomicobject.com/3d-product-babylon-js/

**📄 使用** `**Array.fromAsync()**` **实现现代异步迭代** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/07/14/modern-async-iteration-in-javascript-with-array-fromasync/

🛠 代码和工具

**Tiptap v3：无头富文本编辑器框架** —— Tiptap 为构建强大的富文本编辑体验提供了出色的基础，v3 版本包含了许多开发体验改进，比如能够卸载和重新挂载编辑器（非常适合动态 UI）、用于使用自己的组件创建文本段（标记）自定义视图的”Markviews”、SSR 模式等。GitHub 仓库。

**长按识别二维码查看原文**

https://tiptap.dev/docs/resources/whats-new

Tiptap GmbH

**✉️ Upyo：一个简单的跨运行时邮件发送库** —— 这是一个跨运行时的邮件库，为 SMTP 和基于 HTTP 的提供商（如 SendGrid 或 Amazon SES）提供了统一的、类型安全的 API。**今天我才知道”upyo”（우표）在韩语中是”邮票”的意思。**

**长按识别二维码查看原文**

https://upyo.org/

Hong Minhee

**Hyper Fetch：用于处理远程 API 的”涡轮增压”Fetch 库** —— 这是一个框架无关的、受 Axios 和 TanStack Query 启发的类型安全数据获取框架，可用于浏览器和服务器环境，具有请求生命周期管理、实时通信、进度跟踪和 Swagger/OpenAPI 代码生成功能。GitHub 仓库。

**长按识别二维码查看原文**

https://hyperfetch.bettertyped.com/

Maciej Pyrc 等

**GrowField：用于使文本区域元素自动增长的小型无依赖模块** —— 非常简单。当你有一个 `textarea` 输入框，并且希望它随着内容的增加而增长时可以使用它。

**长按识别二维码查看原文**

https://growfield.js.org/

Five Fifteen

🎁 小彩蛋

- 🔎 git-quick-stats.sh 是一个基于 shell 的工具，可以获取当前 Git 仓库的大量统计信息。
    
    **长按识别二维码查看原文**
    
    https://git-quick-stats.sh/
    

- 一位开发者分享了他在 24 小时内爬取十亿个网页的经历。
    
    **长按识别二维码查看原文**
    
    https://andrewkchan.dev/posts/crawler.html
    

- 🤖 Burke Holland 为我们首次展示了 GitHub 的 Copilot Coding Agent，这基本上是一个更独立的 AI 代理，你可以让它处理仓库中的 issue 和 PR。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2025/07/17/copilot-coding-agent
    

- AWS 推出了 Amazon S3 Vectors，这是其 S3 对象存储服务的一个附加功能，允许你存储和查询向量。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/aws/introducing-amazon-s3-vectors-first-cloud-storage-with-native-vector-support-at-scale/
    

**版本发布：**

- **Nuxt v4.0** —— 这个流行的全栈 Vue.js 框架的重大更新，主要关注开发体验。

- **Node.js v24.4.1、v22.17.1 和 v20.19.4** —— 修复了安全漏洞。

- **ESLint v9.31.0** —— 四个核心规则已更新以支持显式资源管理。

- **Astro v5.12**、**Neutralinojs v6.2**、**OpenPGP.js v6.2**

- **ESLint Markdown Language Plugin v7.0** —— 使用 ESLint 检查 Markdown，以及 Markdown 中的 JS、JSX、TypeScript 等代码。

- **🖊️ Atrament v5.0** —— 一个小型 JS 库，用于在 `canvas` 元素上实现自然的绘图和手写效果。

- **xo v1.2** —— JavaScript/TypeScript 代码检查工具（ESLint 封装），具有出色的默认配置。

- **Wasp v0.17** —— Wasp 是一个类似 Rails 的框架，使用 Node、React 和 Prisma。

- **Tinybase v6.4** —— 为本地优先应用程序设计的强大响应式数据存储。

- **express-rate-limit v8.0** —— Express 的速率限制中间件。

- **TWGL.js v7.0** —— 极简的 WebGL 辅助库。（文档）

- **Bladewind v3.1** —— 为 Laravel 应用程序设计的 JavaScript UI 组件。

- **Concaveman v2.0** —— 一个快速的 2D 凹包算法。

- **MUI X v8.8** —— 流行的 React 组件套件。