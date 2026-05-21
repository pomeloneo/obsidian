# Node 中文周刊 #87 - 基于 Node 的论坛系统

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519946&idx=1&sn=be47fb1873d780bd87296fbef84d9b26&chksm=e921c528de564c3e6c12cfd3b1c5464ef74130e15d696e97b8cd56dcb7d61ab281787124f788\#rd  
> 抓取时间: 2026/2/2 23:53:31

---

> 本期看点：随着某些类型的社交媒体进入动荡时期，我们认为论坛可能正处于回归的良机… 所以很高兴看到长期存在的 NodeBB 的最新主要版本 v3.0 出现。

> 编辑：gaao、Yucohny

## 🔥 本周热门

**NodeBB v3.0：基于 Node 的论坛系统** — 随着某些类型的社交媒体进入动荡时期，我们认为论坛可能正处于回归的良机… 所以很高兴看到长期存在的 NodeBB 的最新主要版本出现。v3.0 包括新的默认主题，改进的推送通知，以及 **一些严重的技术债务的减少**。如果你已经在使用 NodeBB，则可以 **查看 v3 迁移指南**，或者访问 **NodeBB 社区网站** 获取更多信息。

**长按识别二维码查看原文**

https://community.nodebb.org/topic/17115/nodebb-v3-0-0-it-s-here

Julian Lam (NodeBB)

**现在 Node.js 可以在每个主要的浏览器引擎上运行** — 实际的故事是，_WebContainers_ 现在可以像在 Firefox 或 Chrome 上一样，在 Safari、iOS 和 iPadOS 上运行，这意味着 Node.js 也可以直接在所有这些浏览器中运行，如果你这样选择的话。本文深入探讨了在这样的环境中使 Node 工作的具体挑战，或者，如果你喜欢，还有 **一个实时演示**。

**长按识别二维码查看原文**

https://blog.stackblitz.com/posts/webcontainers-are-now-supported-on-safari/

Sylwia Vargas (StackBlitz)

**使用 NAPI-RS 将 Rust 库暴露给 Node** — 上周，我们介绍了 **一篇关于使用 Rust 处理 CSV 数据的教程**，出自 NAPI-RS 框架，用于在 Rust 中构建 Node 插件。本文将更深入地尝试说服你，倾向于使用 Rust 而不是 C 或 C++ 来构建 Node 插件。

**长按识别二维码查看原文**

https://johns.codes/blog/exposing-a-rust-library-to-node-with-napirs

John Murray

**Mongoose v7.1 中的新功能：支持 `BigInt` 以及 `createCollections()`** — **Mongoose** 是由人气 MongoDB 对象建模工具的主要维护者更新。

**长按识别二维码查看原文**

https://thecodebarbarian.com/whats-new-in-mongoose-7-1-bigint-support-createcollections.html

Valeri Karpov

**开始在 Node.js 中使用 Fastify**

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/04/26/getting-started-with-fastify-for-nodejs.html

Damilola Olatunji

**使用 Jest 在 Node.js 中编写单元测试** — 非常入门的一篇文章介绍。

**长按识别二维码查看原文**

https://semaphoreci.com/blog/unit-tests-nodejs-jest

David Ekete 和 Tomas Fernandez

**快讯：**

- Lizz Parody 有一篇 **Node 版本管理器的比较**，即 nvm、Volta 和 asdf。

**长按识别二维码查看原文**

https://stateful.com/blog/nodejs-version-managers-nvm-volta-asdf

- Vercel 已推出 **新的存储选项**，用于运行在其平台上的应用，包括 Postgres 提供的、Redis 兼容的键值存储以及由 Cloudflare 提供的文件存储解决方案，值得注意的是，这三者均由其他公司在幕后提供。

**长按识别二维码查看原文**

https://vercel.com/blog/vercel-storage

- 新式托管平台 Fly․io 编写了一篇 **关于他们对 JavaScript 的热爱的博客文章**，以及他们（不断改善的）托管各类 JS 应用的支持。

**长按识别二维码查看原文**

https://fly.io/blog/flydotio-heart-js/

## 🛠 代码与工具

**Inquirer.js：通用终端 UI 输入接口** — _Inquirer.js_ 是一套长期用于接受文本、密码、提供选择等终端应用的文本“控件”。经过 10 年的初创，它已经被更新到 2023 年的标准，更加高效，并且现在也支持 TypeScript。

**长按识别二维码查看原文**

https://github.com/SBoudrias/Inquirer.js/discussions/1214

Simon Boudrias

**Marked.js v5.0：一个快速的 Markdown 解析器和编译器** — 一个低级别的 Markdown 编译器，专为性能而构建，可以作为客户端库、服务端库甚至 CLI 使用。**v5.0** 弃用了一些选项，改用外部插件。这里有 **一个在线演示**。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

**Axios v1.4：基于 Promise 的浏览器和 Node HTTP 客户端** — 一个长期存在的项目，尽管越来越被视为“HTTP 请求库的 jQuery”，但仍然获得频繁的更新。如果你需要它，你就会知道。

**长按识别二维码查看原文**

https://github.com/axios/axios

Matt Zabriskie

**Multi-Line INI Parser：支持多行字符串的 INI 解析器** — 解析众所周知的非标准化配置格式的另一种选择。

**长按识别二维码查看原文**

https://github.com/HeyPuter/multiline-ini

Puter

**ssh2 v1.12：Node 的纯 JS SSH2 客户端和服务器** — README 中 **有很多示例**。

**长按识别二维码查看原文**

https://github.com/mscdex/ssh2

Brian White

**patch-package v7.0：立即修复破损的 Node 模块** — 以临时方式对 npm 依赖进行修复和维护。它将自己描述为“对于我们这些生活在最前沿的人来说，这是一个至关重要的创可贴”。

**长按识别二维码查看原文**

https://github.com/ds300/patch-package

David Sheldrick

**版本发布：**

- **Middy v4.4**
    
    ↳ 用于 AWS Lambda 无服务平台的 Node 中间件引擎。v4.4 改进了 **对流式响应的支持**。
    

- **Mercurius v13.0**
    
    ↳ 使用 Fastify 实现 GraphQL 服务器和网关。
    

- **Fastify v4.17**
    
    ↳ 快速、低开销的 Web 框架。
    

- **Sharp v0.32.1**
    
    ↳ 高性能图像处理。
    

- **swagger-markdown v2.3**
    
    ↳ 将 Swagger YAML 转换为 Markdown。
    

- **easy-soap-request v5.3**

## 🙋🏻‍♀️