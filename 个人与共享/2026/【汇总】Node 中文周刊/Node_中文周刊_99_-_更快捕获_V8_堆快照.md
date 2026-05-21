# Node 中文周刊 #99 - 更快捕获 V8 堆快照

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522969&idx=1&sn=b928352b86679a9dd2dc20c56c819edf&chksm=e921d17bde56586d14c3a7156f82fae7200b2e14db7a38b643d36a3d4c4b53699de2a30a8c7f\#rd  
> 抓取时间: 2026/2/2 23:53:13

---

> 本期看点：Bloomberg 的工程师在诊断 JavaScript 应用程序中的内存泄漏时遇到了一些奇怪的性能问题：有时捕获一个完整堆快照的耗时会超过 30 分钟！本期有篇文章就介绍了他们是如何调查和解决这个问题的，他们的研究可能会让我们对 JavaScript 的内存分析比以往更快速。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**PythonMonkey：在 Python 中运行 JavaScript/WASM** —— 刚发布 alpha 版本的 PythonMonkey 是将 Python 与 JavaScript 结合在一起的新方法，原理是将 Mozilla SpiderMonkey 嵌入到 Python VM 中。这篇文章通过示例展示了这个概念、项目的发展方向和一些 Colab 演示。尽管使用的是 SpiderMonkey 而不是 V8，但与 Node 和 npm 的兼容性对于该项目来说仍然很重要，未来也将持续提升对 Node 的集成。这是它的 **GitHub 仓库**。

**长按识别二维码查看原文**

https://medium.com/@willkantorpringle/pythonmonkey-javascript-wasm-interop-in-python-using-spidermonkey-bindings-4a8efce2e598

Will Pringle

**🛠 Node.js Toolbox：查找 Node.js 包** —— 几个月前我们介绍过这个全新的项目，它整理了 **HTTP 框架**、**浏览器测试** 和 **查询构建器** 等领域的 Node 包，而且一直在不断更新。最近他们添加了一个新功能，可以比较每个类别中包的每周下载量。

**长按识别二维码查看原文**

https://nodejstoolbox.com/

Maxim Orlov

**更快捕获 V8 堆快照** —— Bloomberg 的工程师在诊断 JavaScript 应用程序中的内存泄漏时遇到了一些奇怪的性能问题：有时捕获一个完整堆快照的耗时会超过 30 分钟！这篇文章介绍了他们是如何调查和解决这个问题的，他们的研究可能会让我们对 JavaScript 的内存分析比以往更快速。

**长按识别二维码查看原文**

https://v8.dev/blog/speeding-up-v8-heap-snapshots

José Dapena Paz（Igalia）

**将 TypeScript 应用程序从 Node 迁移至 Bun**

**长按识别二维码查看原文**

https://blog.logrocket.com/migrating-typescript-app-node-js-bun/

John Reilly

**快讯：**

- 如果你在 Vercel 上使用的是 Node v14，那么需要注意 **Vercel 将在两周内停止支持 Node v14**；另外还会在明年二月停止支持 Node v16。

**长按识别二维码查看原文**

https://vercel.com/changelog/node-js-14-and-16-are-being-deprecated

- Node.js 团队正在庆祝使用 Next.js 与 Vercel 对 **Node.js 官方网站** 进行了 🐦 **“长期基础型转型”**。值得注意的是，除了可能存在中断的 RSS 订阅，我们几乎看不到任何区别。

**长按识别二维码查看原文**

https://twitter.com/nodejs/status/1686121431560585216

- **Node.js 预计将于 8 月 8 日发布安全更新** 以解决不同严重程度的安全问题。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/august-2023-security-releases

- 来自 Socket 的 Feross Aboukhadijeh 声称一场针对技术员工的社会工程活动 **正在通过 npm 恶意软件传播**。

**长按识别二维码查看原文**

https://socket.dev/blog/social-engineering-campaign-npm-malware

- GitHub 表示 **不再支持** 将私有仓库作为 npm 包的来源。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-07-26-publishing-with-npm-provenance-from-private-source-repositories-is-no-longer-supported/

## 🛠 代码与工具

**Enquirer：时尚、直观和用户友好的 CLI prompt** —— 无论是简单的文本输入、问答、密码还是其他功能，Enquirer 都可以为命令行应用程序提供快速、轻量和实用的提示。**参见更多代码示例**。

**长按识别二维码查看原文**

https://github.com/enquirer/enquirer

Enquirer

**Ora v7.0：优雅的终端加载动画** —— 另一种让命令行应用程序看起来更棒的方式。

**长按识别二维码查看原文**

https://github.com/sindresorhus/ora

Sindre Sorhus

**Crawlee v3.5：网络爬虫和浏览器自动化库** —— Crawlee 是一个成熟的用于网络爬取和抓取任务的库，这里是 **快速入门指南**。

**长按识别二维码查看原文**

https://crawlee.dev/

Apify

**Hackathon Starter v8.0：用于 Node Web 应用程序的样板** —— 当你想要在如 hackathon 中快速开始构建一个 Node 应用程序时可以试试 Hackathon Starter，它支持身份验证、账户管理、电子邮件表单等关键功能，

**长按识别二维码查看原文**

https://github.com/sahat/hackathon-starter

Sahat Yalkabov

**node-tlds：最新的顶级域名列表** —— 在 Node 中轻松获取 **涵盖有效 TLD 的列表**。

**长按识别二维码查看原文**

https://github.com/stephenmathieson/node-tlds

Stephen Mathieson

**版本发布：**

- **Octokit.js v3.1**
    
    ↳ 包含所有常用功能的 GitHub SDK。
    

- **eta（η）v3.1**
    
    ↳ 嵌入式 JavaScript 模板引擎。现在支持 Bun。
    

- **NestJS Telegraf v2.7**
    
    ↳ 使用 NestJS 创建 Telegram 机器人。
    

- **Fastify v4.21**
    
    ↳ 流行的 Node.js web 框架。
    

- **LDAPts v6.0**
    
    ↳ LDAP 客户端库。
    

- **Derby v2.2**
    
    ↳ MVC 框架。
    

- **MQTT.js v5.0**

## 🙋🏻‍♀️