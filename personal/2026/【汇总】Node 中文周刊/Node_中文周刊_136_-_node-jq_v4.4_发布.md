# Node 中文周刊 #136 - node-jq v4.4 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532164&idx=1&sn=febece5dbf8644ff0a25cb95ad37d410&chksm=e9213566de56bc700b00e085a7989d07e34a888172ab60d148edbe899eaf59b06ac16c272662\#rd  
> 抓取时间: 2026/2/2 23:52:29

---

> 本期看点：jq 是一个流行且强大的命令行 JSON 处理工具，非常值得放在你的工具箱中。它是用 C 编写的，node-jq 简化了从 Node 调用它的流程。

> Yucohny、loveloki、TimLi

🔥 本周热门

**10 个 2024 年应该开始使用的现代 Node.js 功能** —— 如果你觉得我们最近过于聚焦在 Bun 和 Deno 的新功能上，也不用担心 —— Node 也已经取得了很大进步。Liran 帮助我们掌握许多最新的 Node 功能。

**长按识别二维码查看原文**

https://snyk.io/blog/10-modern-node-js-runtime-features/

Liran Tal

**掌握 Node.js 性能 Hook** —— Node 的 性能测量 API 提供了强大的功能，但是理解测量内容和意义的心智模型可能会很棘手。Pavel 在文章中介绍了这些内容。

**长按识别二维码查看原文**

https://pavel-romanov.com/nodejs-performance-hooks-mastering-the-mental-model

Pavel Romanov

**深入探讨** `**Promise.withResolvers()**` **提案** —— Axel 深入研究了处于第四阶段的 `Promise.withResolvers` 提案以及它如何让创建 promise 变得更加优雅。

**长按识别二维码查看原文**

https://2ality.com/2024/05/proposal-promise-with-resolvers.html

Dr. Axel Rauschmayer

**Node.js 测试运行器的初学者指南** —— 现代 Node 内置了测试运行器。

**长按识别二维码查看原文**

https://betterstack.com/community/guides/testing/nodejs-test-runner/

Stanley Ulili

**📄 ECMAScript 提案：正则表达式的重复命名捕获组**

**长按识别二维码查看原文**

https://2ality.com/2024/05/proposal-duplicate-named-capturing-groups.html

Dr. Axel Rauschmayer

**📄 使用 Node 中的 OpenAI 总结 Substack 文章**

**长按识别二维码查看原文**

https://implementing.substack.com/p/summarize-substack-articles-using-chatgpt-nodejs

Marco Moauro

**📄 将自定义 CMS 与 Eleventy 集成**

**长按识别二维码查看原文**

https://coryd.dev/posts/2024/integrating-a-somewhat-custom-cms-with-eleventy/

Cory Dransfeldt

**📄 使用 LLM 总结音频内容** —— 使用 AssemblyAI 平台。

**长按识别二维码查看原文**

https://www.assemblyai.com/blog/summarize-audio-with-llms-nodejs/

Niels Swimberghe（AssemblyAI）

**📄 你不应该将 HTTP 的 API 重定向到 HTTPS**

**长按识别二维码查看原文**

https://jviide.iki.fi/http-redirects

Joachim Viide

**快讯：**

- Node v20.14.0（LTS） 和 v18.20.3（LTS） 已经发布，包含一些小型修复。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v20.14.0
    

- 🎂 Node.js 的 Twitter/X 账号庆祝 15 岁生日。
    
    **长按识别二维码查看原文**
    
    https://x.com/nodejs/status/1795110360510300397
    

- ESLint 批准了 添加对 TypeScript 配置文件支持 的 RFC。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/eslint-approves-rfc-to-add-support-for-typescript-config-files
    

🛠 代码与工具

**Zigar：在 Node 和 Electron 项目中使用 Zig** —— Zig 是一个新的系统语言（本质上是 C/C++ 的超集）。**Zigar** 让在 JavaScript 项目中更轻松地编写和使用 C/C++/Zig 成为可能。

**长按识别二维码查看原文**

https://github.com/chung-leong/zigar

Chung Leong

**Tinypool v1.0：一个更加小巧的 Worker Pool 库** —— Piscina 的一个分支，旨在减少依赖项并减少总体占用空间。这里列出了主要的更新内容。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinypool

Tinylibs

**TypeScriptToLua：使用 TypeScript 编写 Lua** —— Lua 在各种场景下都被使用（游戏、Redis 以及 NGINX 等等），所以能够使用 JavaScript 编写它可以给你带来一些额外的机会。

**长按识别二维码查看原文**

https://typescripttolua.github.io/

TypeScriptToLua Contributors

**🤖 Experts.js：创建并部署 OpenAI 助手，然后把它们链接在一起** —— 使用 OpenAI 的 Assistants API 创建特定的基于 LLM 的代理，随后可以将它们链接在一起以创建一个 “专家小组” 系统。

**长按识别二维码查看原文**

https://github.com/metaskills/experts

Ken Collins

**node-jq v4.4：**`**jq**` **包装器** —— jq 是一个流行且强大的命令行 JSON 处理工具，非常值得放在你的工具箱中。它是用 C 编写的，这个库简化了从 Node 调用它的流程。

**长按识别二维码查看原文**

https://github.com/sanack/node-jq

sanack

**node-usb v2.13.0：改进的 Node USB 库** —— 你可以通过 Node 代码在低级别上使用 USB 吗？毋庸置疑！

**长按识别二维码查看原文**

https://github.com/node-usb/node-usb

Node USB

**版本发布：**

- **Regexper** – 将正则表达式可视化为图表。

- **LightAPI** – 轻量级 Express API 样板。

- **PyMiniRacer** – Python/V8/JS 互操作库。

- **express-openapi-validator v5.2** – 根据 OpenAPI 3.x 规范自动验证 Express 中的 API 请求和响应。

- **MongoDB Node.js Driver v6.7** – 最新的官方 MongoDB 驱动程序。现在支持 MONGODB-OIDC 身份验证。

- **Fast Node Manager（fnm）v1.37** – Rust 编写的 Node.js 版本管理器。

- **Hono v4.4** – 基于网络标准的网络框架。

- **PM2 v5.4** – 生产环境常用的进程管理器。

- **Middy v5.4** – AWS Lambda 的节点中间件引擎。

- **better-sqlite v11.0** – 从 Node.js 中使用 SQLite 的好方法。

- **express-rate-limit v7.3** – 基本的限速中间件。

- **node-hid v3.1** – 访问 USB 和蓝牙 HID 设备。

- **Vine v2.1** – 表单数据验证库。

- **pg-promise v11.8** – 用于 Node 的 Postgres 接口。

- **ESLint v9.4.0**

🙋🏻‍♀️