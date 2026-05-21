# Node 中文周刊 #167 - TypeScript 5.8 Beta 发布：Node 开发者的重大更新

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539652&idx=1&sn=817e150e3044c5815243801ec885a2dc&chksm=e9211026de5699307722478128c54567c55602d79450cdb760a48473088f6042d19933e26f60\#rd  
> 抓取时间: 2026/2/2 23:51:52

---

> 本期看点：TypeScript 5.8 Beta 带来 Node.js 相关重要更新，包括 nodenext 模式支持 require() 导入 ES 模块；Mentoss 发布全新的 fetch 模拟工具，支持浏览器和服务器端；Standard Schema 推出统一的模式验证库接口标准；Vercel 收购 Tremor 图表库团队；Bun v1.2.2 发布并优化内存使用。

> 编辑：TimLi

🔥 本周热门

**TypeScript 5.8 Beta 发布：Node 开发者的重大更新** —— TypeScript 的 beta 版本很少会让 Node 开发者如此兴奋。虽然 TypeScript 5.8 的新功能不多，但它主要聚焦于 Node，包括在 `nodenext` 模式下支持 `require()` 导入 ES 模块、稳定的 `--module node18`，以及最值得注意的是新增了 `--erasableSyntaxOnly` 选项，确保使用的 TypeScript 代码能够被 Node 22.6+ 的类型擦除功能正确处理。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-8-beta/

Daniel Rosenwasser

**Mentoss：新一代** `**fetch**` **模拟工具** —— 这是一个全新的全局 `fetch()` 调用模拟方案（同时支持浏览器和服务器端运行时），其灵感来自 Nock 和 MSW 等前辈工具。

**长按识别二维码查看原文**

https://humanwhocodes.com/blog/2025/01/introducing-mentoss-fetch-mocker/

Nicholas C. Zakas

**Standard Schema：统一的模式/验证库接口** —— 由 Zod、Valibot 和 ArkType 的创建者联合推出，这是一次出色的合作，旨在为 JavaScript 和 TypeScript 模式库定义统一的接口。

**长按识别二维码查看原文**

https://standardschema.dev/

McDonnell、Hiller 和 Blass

**编写 JavaScript 服务器的现代方式？** —— 有趣的是，虽然 Node 让 JavaScript 在服务器端流行起来（如果我们忽略 90 年代 Netscape 的尝试），但这种现代化的、标准化的跨运行时方法在原生 Node 上还不能直接使用（不过你可以通过 polyfill 实现）。

**长按识别二维码查看原文**

https://marvinh.dev/blog/modern-way-to-write-javascript-servers/

Marvin Hagemeister

**📄 远程创业公司如何共享密钥** —— 有趣的是，这个方案用到了 Node。Dmitry Sagalovskiy

**长按识别二维码查看原文**

https://mill.plainopen.com/how-we-share-secrets-at-a-fully-remote-startup

**📄 使用** `**npx is-my-node-vulnerable**` **确保你的 Node 应用程序安全** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/is-my-node-vulnerable

**📄 如何在浏览器中使用 Node 的** `**fs**` **模块来创建自定义代码操场** Ivan Chebykin

**长按识别二维码查看原文**

https://typeconf.dev/blog/using-fs-in-browser

**📄 使用 OpenTelemetry 在 Node.js 中实现分布式追踪** Ayooluwa Isaiah

**长按识别二维码查看原文**

https://betterstack.com/community/guides/observability/opentelemetry-nodejs-tracing/

**快讯：**

- Node.js v23.7.0（当前版本）已发布，包含多个 bug 修复和改进。现在你可以在 glob 函数的 `exclude` 选项中使用 glob 模式，并且新增了一个错误提示，用于提醒 TypeScript 用户代码中存在不支持的 TypeScript 特性。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v23.7.0
    

- Josh Goldberg 解释了 ESLint 和 TypeScript 的区别，超出了表面的认知。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/01/differences-between-eslint-and-typescript/
    

- Publican 是一个新兴的 Node.js 静态站点生成器。
    
    **长按识别二维码查看原文**
    
    https://publican.dev/
    

- 来自 Bit 的 Harmony 自称是”可组合架构的极简粘合层”——可以理解为介于单体架构和微服务之间的方案，避免了两者的缺点。
    
    **长按识别二维码查看原文**
    
    https://bit.dev/
    

🛠 代码与工具

**parse-duration v2.0：将人类可读的时长转换为毫秒** —— 你可能会好奇为什么一个将 `1hr 20mins` 转换为 `4800000` 的库需要升级到 v2。实际上，它现在支持更多单位（`mo`、`mth`、`microsec` 和 `nanosec`），迁移到了 ESM，并支持本地化。

**长按识别二维码查看原文**

https://github.com/jkroso/parse-duration

Jake Rosoman

**Node File Trace (NFT)：Node 依赖追踪工具** —— 这是一个易于理解的 NFT 实现。

**长按识别二维码查看原文**

https://github.com/vercel/nft

Vercel

**Feluda：依赖许可证分析工具** —— 这是一个基于 Rust 的项目，可用于分析 Node、Go 或 Rust 项目的依赖，并生成报告（或显示 TUI 界面）来展示可能存在的限制性许可证。

**长按识别二维码查看原文**

https://github.com/anistark/feluda

Kumar Anirudha

**📄 docxtemplater：从模板生成** `**docx**` **和** `**pptx**` **文档** —— 通过合并模板文档（如发票、合同、证书）动态生成 Word 和 PowerPoint 文件。它是开源的（MIT/GPLv3），但创建者提供商业扩展（如 Excel 支持）。GitHub 仓库和功能演示。

**长按识别二维码查看原文**

https://docxtemplater.com/

Edgar Hipp

**http-status：处理 HTTP 状态码的另一种方式** —— 例如：`status[418]` 返回 `"I'm a teapot"`，而 `status.IM_A_TEAPOT` 返回 `418`。

**长按识别二维码查看原文**

https://github.com/adaltas/node-http-status

Adaltas

📢 其他 JavaScript 相关

以下是 JavaScript 生态圈中其他一些有趣的新闻，以防你错过：

- 🤣 Deno 与 Oracle 的 JavaScript™ 商标案仍在继续，Oracle 刚好赶在截止日期前提交了驳回案件的动议。Oracle 声称”相关消费者并不认为 JAVASCRIPT 是通用术语”，并暗示由于他们的 Oracle JavaScript Extension Toolkit (JET) 的普及，JavaScript 在公众眼中”显然”属于他们。
    
    **长按识别二维码查看原文**
    
    https://javascript.tm/
    

- 由 Deno 团队创建的开源注册表 JSR 现在有了独立的董事会，采用”开放治理”政策，旨在为整个 JavaScript 社区提供价值。
    
    **长按识别二维码查看原文**
    
    https://jsr.io/
    

- 📊 Vercel 收购了 Tremor 团队，这是一个流行的 React 图表和仪表盘组件套件。计划是用 Tremor 的工作来增强 v0，并开源更多组件。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/vercel-acquires-tremor
    

- SolidJS 的创建者表示，Angular 和 Vue 是 2025 年值得关注的框架，同时也反思了 JS 框架的整体发展。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/solidjs-creator-on-confronting-web-framework-complexity/
    

**版本发布：**

- **Bun v1.2.2** 发布，大幅降低了空闲内存使用。

- **get-value v4.0** —— 使用属性路径（`a.b.c`）从对象中获取嵌套值。

- **🤖 OpenAI Node 4.82** —— OpenAI API 的官方 Node 库增加了对新的 `o3-mini` 模型的支持。

- **sqs-consumer v11.5** —— BBC 的无样板代码 AWS Simple Queue Service (SQS) 应用程序解决方案。

- **exiftool-vendored v29.1** —— 跨平台访问 ExifTool 管理多媒体文件元数据。

- **Wasp v0.16** —— Wasp 是一个使用 Node、React 和 Prisma 的类 Rails 框架。

- **🤖 node-llama-cpp v3.5** —— 通过 `llama.cpp` 绑定在本地运行 LLM。

- **Neutralinojs v5.6** —— 轻量级跨平台桌面应用程序开发方案。

- **MongoDB Node.js Driver v6.13** —— 最新的官方 MongoDB 驱动程序。

- **pnpm v10.2** —— 高效的替代包管理器。

- **Prisma v6.3** —— 流行的 Node.js 和 TypeScript ORM。

- **pino-http v10.4** —— Node 高速 HTTP 日志记录器。