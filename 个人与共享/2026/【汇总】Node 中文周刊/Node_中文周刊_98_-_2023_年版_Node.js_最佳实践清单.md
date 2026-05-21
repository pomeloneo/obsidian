# Node 中文周刊 #98 - 2023 年版 Node.js 最佳实践清单

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522859&idx=1&sn=ff06272bce3eca3ba6feea8301a2672c&chksm=e921d1c9de5658df5bd39c71f883e644062e05c8e3d87bf2e4cf208132d6c039350714e1bfae\#rd  
> 抓取时间: 2026/2/2 23:53:15

---

> 本期看点：“Node.js 最佳实践”这一已经长期存在的有价值的资源已经“现代化到 2023 年标准”。“Node.js 最佳实践”系列由创建者 Yoni 及日益壮大的贡献者团队共同努力完成了大量工作。文章主题仍然相同，涵盖了代码风格、项目架构以及将应用程序投入生产等领域。

> 编辑：Yucohny

## 🔥 本周热门

**2023 年版 Node.js 最佳实践清单** —— “Node.js 最佳实践”这一已经长期存在的有价值的资源已经“现代化到 2023 年标准”。“Node.js 最佳实践”系列由创建者 Yoni 及日益壮大的贡献者团队共同努力完成了大量工作。文章主题仍然相同，涵盖了代码风格、项目架构以及将应用程序投入生产等领域。**如果你已经熟悉了这个列表，可以在页面上浏览 \#new 和 \#updated 标签所对应的内容**。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodebestpractices

Yoni Goldberg et al.

**Microsoft TypeChat：一种类型安全的 LLM 响应方法** —— 很高兴看到微软与众多知名人士合作推出一个新项目，这表现了微软对机器学习和大型语言模型的巨大兴趣。**TypeChat** 的目标是解决 LLM 中输出非结构化自然语言的问题，实现将这种输出引导到可预测的、**具有类型** 的形式中。

**长按识别二维码查看原文**

https://microsoft.github.io/TypeChat/blog/introducing-typechat/

Hejlsberg, Lucco, Rosenwasser et al.

**Node v18.17.0（LTS）发布** —— 这并非 LTS 版本的一次大更新，其更像是一个“跟进时代”的发布。Node 18 新增 Ada v2.0（符合 WHATWG 标准的 URL 解析器），并改进了对 Web Crypto API 的支持。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.17.0

Danielle Adams

**📣 Node v20.5.0（Current）**也已发布，但是并无巨大更新，也没有添加新功能。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.5.0

**使用 Cypress 测试 Content-Security-Policy（CSP）**

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/csp-testing-using-cypress/

Gleb Bahmutov

**在 Docker 中使用 npm workspace**

**长按识别二维码查看原文**

https://nathanfries.com/posts/docker-npm-workspaces/

Nathan Fries

**快讯：**

- 与使用 V8 的 Deno 和 Node 不同，**Bun** 是一个基于 WebKit 的 **JavaScriptCore** 构建的 JavaScript 运行时替代方案。然而，与 Deno 一样，Bun 对 Node 的兼容性非常重要，**Bun v0.7** 提高了对 Node 的兼容性，并增加了对 Vite 的支持，实现了 Web Workers，并引入了一个新的 `-smol` 选项，以在内存受限的环境中运行（在一个基准测试中，它使用的内存只有六分之一）。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v0.7.0

- 去年首次提出了在 Node 中 **原生支持 .env 文件** 的想法，现在 **有一个 PR 正在推进这个问题**。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/48890

- 如果你是一个使用 VS Code 和 TypeScript 的用户，又厌倦了冗长、难以理解的错误信息，那么值得试试 VS Code 扩展程序的 **Pretty TypeScript Errors**。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors\#prettytserrors

## 🛠 代码与工具

**Ink v4.3：使用 React 构建交互式 CLI 应用程序** —— 这是一个基于终端的 React 渲染器，你可以使用 React 风格的组件构建命令行应用程序。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

Necord：用于创建 Discord 机器人的框架 —— Necord 使用 Nest 和 Discord.js 构建，这里有一些示例应用展示了部署机器人功能 **有多么简单**。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://github.com/necordjs/necord

Necord

**MailDev：测试电子邮件的 SMTP 服务器和 Web 界面** —— 如果应用程序需要发送电子邮件，而不是发送到实际账户，可以将其发送到这个应用程序，它可以让你在本地预览，而无需考虑垃圾邮件过滤器等问题。

**长按识别二维码查看原文**

https://maildev.github.io/maildev/

Dan Farrelly

## 📰 实用推荐

**fast-png v6.2：使用原生 JavaScript 事件解码编码 PNG 图片** —— 通过 TypedArray 或 Buffer 传递一个 PNG 图片并对其进行解码，或者通过 Canvas ImageData（或兼容对象）传递一个对象并将其编码为 PNG 图片。

**长按识别二维码查看原文**

https://github.com/image-js/fast-png

Michaël Zasso

**brotli-wasm v2.0：Brotli 压缩器和解压器** —— 通过 WebAssembly 覆盖了 Node 和浏览器两个平台。

**长按识别二维码查看原文**

https://github.com/httptoolkit/brotli-wasm

HTTP Toolkit

**版本发布：**

- **Jasmine v5.1**
    
    ↳ JavaScript 测试框架。
    

- **better-sqlite3 v8.5**
    
    ↳ 更友好地与 SQLite3 一起工作。
    

- **BullMQ v4.6**
    
    ↳ 用于 Node 的消息队列和作业处理。
    

- **adminJS v7.1**
    
    ↳ 用于 Node Web 应用程序的管理面板。
    

- **Mongoose v7.4**
    
    ↳ 用于 MongoDB 对象建模的工具。
    

- **Typegoose v11.4**
    
    ↳ 使用 TypeScript 类定义 Mongoose 模型。
    

- **LDAPts v5.0**
    
    ↳ TypeScript LDAP 客户端。
    

- **oclif v3.10.0**
    
    ↳ CLI 框架。
    

- **pnpm v8.6.10**

## 🙋🏻‍♀️