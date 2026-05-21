# JavaScript 中文周刊 #131 - 介绍 Vlt (/vōlt/) 团队

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529709&idx=1&sn=aa998996e599caf741d19224aa6aaf12&chksm=e9213f0fde56b619f88457f6cf053b568dbb2b5552133bda0ccbcf88ccf2bdc9470bed3c45d0\#rd  
> 抓取时间: 2026/2/2 23:51:14

---

> 本期看点：去年夏天，曾在 `npm` CLI 团队工作的 Darcy Clarke 写了一篇涉及 manifest 安全性的文章《npm 生态系统中心的一个巨大漏洞》。而现在他与 npm 的创始人 Isaac Z. Schlueter 和另一位 npm CLI 团队的前成员 Ruy Adorno 结成了新的团队，致力于打造一个新的包管理器和注册表。

> 编辑：Yucohny

## 🔥 本周热门

**可视化 JavaScript 运行时的兼容性** —— 几位开发者联合创建了这个方便的工具，用于可视化不断增加的不同运行时（例如 Bun、Deno、Node、LLRT 等）之间的 Web API 和 JavaScript 功能的兼容性。

**长按识别二维码查看原文**

https://runtime-compat.unjs.io/

Tom Lienard 等

**介绍 Vlt (/vōlt/) 团队** —— 去年夏天，曾在 `npm` CLI 团队工作的 Darcy Clarke 写了一篇涉及 manifest 安全性的文章 **《npm 生态系统中心的一个巨大漏洞》**。而现在他与 npm 的创始人 Isaac Z. Schlueter 和另一位 npm CLI 团队的前成员 Ruy Adorno 结成了新的团队，致力于打造一个新的包管理器和注册表。

**长按识别二维码查看原文**

https://blog.vlt.sh/blog/the-team

vlt /vōlt/

**快讯：**

- Angular 的 **ngConf 2024** 正在进行中，一些有趣的公告已经发布，包括 **一些 AI 整合** 和 **与另一个 Google 框架的合并**，名为 Wiz。

**长按识别二维码查看原文**

https://ng-conf.org/

- 截至 Chrome 123，**WebAssembly JSPI 进入原始试验阶段**。JSPI（JavaScript Promise Integration）允许 WebAssembly 代码通过 Promise 直接使用异步 Web API。

**长按识别二维码查看原文**

https://v8.dev/blog/jspi-ot

- **sh.mhs / 简写 JavaScript** 是一个有趣的示例，展示了一些经过深思熟虑但仍然可读的 JavaScript golfing。

**长按识别二维码查看原文**

https://gist.github.com/tangentstorm/4f271600fc20404150e05c373109551d

- 在我们出版后，▶️ **Honeypot 的 Node.js 纪录片** 将在今天晚些时候在 YouTube 上首映。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=LB8KwiiUGy0

- 上周我们介绍了基于 SpiderMonkey 的 JavaScript 运行时的 **WinterJS v1.0 发布**，不过我想大家会好奇：**它与其他替代品相比有多快**？

**长按识别二维码查看原文**

https://wasmer.io/posts/winterjs-vs-alternatives-is-blazing-fast

- 🤖 W3C 正在开发一个 **Web 神经网络 API**。

**长按识别二维码查看原文**

https://www.w3.org/TR/webnn/

## 📒 教程与趣事

**📉 为了乐趣和利润优化 JavaScript** —— 浏览一些要避免的事情，以保持代码运行快速顺畅，配有示例。虽然我们行走的性能领域经常在变化，但其中许多都是好的、常识性的做法。

**长按识别二维码查看原文**

https://romgrk.com/posts/optimizing-javascript

Rom Grk

**Figma 如何构建自定义权限 DSL** —— Figma 有一个复杂的权限设置，其实现导致了技术债务、错误和延迟。在找不到任何开源答案后，他们构建了一个 DSL，该 DSL 隔离了策略和数据，同时也是跨平台的（Ruby 和 TypeScript）。

**长按识别二维码查看原文**

https://www.figma.com/blog/how-we-rolled-out-our-own-permissions-dsl-at-figma/

Jorge Silva（Figma）

**类型断言推理：无人预料的 TypeScript v5.5 特性** —— Matt 又有一个新作品了，他对 TypeScript v5.5 中将要包含的从函数体中推断类型断言的功能感到兴奋。

**长按识别二维码查看原文**

https://www.totaltypescript.com/type-predicate-inference

Matt Pocock

**WebSockets vs 服务器发送事件 vs 长轮询 vs WebRTC vs WebTransport**

**长按识别二维码查看原文**

https://rxdb.info/articles/websockets-sse-polling-webrtc-webtransport.html

RxDB 文档

## 🛠 代码与工具

**Atrament v4.0：用于平滑绘制和手写的库** —— 一个用于在画布元素上进行美观绘制和手写的小型库。它已经存在了好几年了，但 **v4.0** 几乎是完全重写的。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.fiala.space/atrament/demo/

Jakub Fiala

**MicroDiff：无依赖的对象和数组比较库** —— 给定两个对象或数组，然后会返回它们之间的差异。拥有高性能和 TypeScript 支持。还有一篇来自 2022 年的关于 **它如何工作的文章**。

**长按识别二维码查看原文**

https://github.com/AsyncBanana/microdiff

AsyncBanana

**oneRepo v1.0：团队使用的新型单仓库工具套件** —— 当讨论 JavaScript 单仓库管理工具时，似乎总是有不满，但也许 **Paul 的方法能够说服你**？

**长按识别二维码查看原文**

https://onerepo.tools/

Paul Armstrong

**TanStack Virtual v3.2：用于虚拟化大型元素列表的无头 UI** —— 支持 TypeScript/JavaScript、React、Solid、Svelte 和 Vue，这是一种在拥有大量元素的情况下构建 60 fps 体验的方式，同时保持对标记和样式的完全控制。

**长按识别二维码查看原文**

https://tanstack.com/virtual/latest

Tanner Linsley

**版本发布：**

- **Nuxt v3.11** – 全栈 Vue 框架，也是 v4.0 发布之前的最后一个版本，但仍然是一个重要的发布。

- **Angular v17.3** — 这里是更新内容。

- **Preact v10.20.0**

- **Express.js v4.19.0**

- **VanJS v1.5** – 小巧而可爱的响应式 UI 框架。欢迎查看 **主页**。

- **Mercurius v14.0** – 在 Fastify 上实现 GraphQL 服务器和网关。

- **Happy DOM v14.2** – 无界面的 Web 浏览器的 JavaScript 实现。

- **Encoding.js v2.1** – 字符编码转换和检测。

## 🙋🏻‍♀️