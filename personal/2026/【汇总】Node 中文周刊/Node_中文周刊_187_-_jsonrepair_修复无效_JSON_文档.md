# Node 中文周刊 #187 - jsonrepair 修复无效 JSON 文档

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542529&idx=1&sn=53dad11f58ad5e97784cc86f146787c4&chksm=e9216ce3de56e5f50973d360f21157558de1744e7235a60ab077f127d147bb18c3de735740b3#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542529&idx=1&sn=53dad11f58ad5e97784cc86f146787c4&chksm=e9216ce3de56e5f50973d360f21157558de1744e7235a60ab077f127d147bb18c3de735740b3#rd): 2026/2/2 23:51:28

---

> 本期看点：jsonrepair 工具支持修复无效 JSON 文档，Node.js 团队重构 API 文档并发布 api-docs-tooling，Bruno 推出基于 Node 的 HTTP API 测试 IDE，Poolifier v5.0 支持可中止任务，Deno 2.4 发布并增强 Node 兼容性。

> 编辑：TimLi

🔥 本周热门

**jsonrepair：修复无效的 JSON 文档** —— 这个工具有很多潜在的使用场景，包括处理来自 LLM 的奇怪 JSON 或由糟糕软件生成的不规范 JSON。你可以在 Node 中使用它，也可以用它作为命令行工具，或者试试在线版本。

**长按识别二维码查看原文**

https://github.com/josdejong/jsonrepair

Jos de Jong

**代码点安全截断：修复 Node 中的表情符号切片问题** —— 一个应用程序的 CSV 导入器在处理包含表情符号的行时不断出错。James 演示了如何用支持代码点的展开运算符替换 slice 来解决这个问题。

**长按识别二维码查看原文**

https://attio.com/engineering/blog/javascript-string-slice-considered-harmful

James Mulholland

**如何构建你自己的颜色搜索引擎** —— 这是一篇直观且实用的教程，介绍了如何结合多种技术和技能来创建一个 AI 驱动的颜色推荐工具（你可以在这里试用）。文中介绍的技术可以用于许多不同的实际应用。

**长按识别二维码查看原文**

https://lui.ie/guides/semantic-search-colors

Lúí Smyth

**📺 如何构建你的第一个 MCP 服务器** —— 构建你的第一个 Model Context Protocol（MCP）服务器，将 GitHub Copilot 等 AI 助手连接到实时天气数据。Debbie O’Brien

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=egVm_z1nnnQ

**📄 普通函数和箭头函数有什么区别？** James Sinclair

**长按识别二维码查看原文**

https://jrsinclair.com/articles/2025/whats-the-difference-between-named-functions-and-arrow-functions/

**📄 我在线吗？** —— 通过检查特定的 Google URL 来判断你的应用程序是否真正在线的有趣方法。Anton Zhiyanov

**长按识别二维码查看原文**

https://antonz.org/is-online/

**快讯：**

- Node.js 团队正在重新设计和构建 API 文档 —— api-docs-tooling 是实现这个魔法的工具，这里有一张截图 展示了目前的样子。你也可以在这里关注项目进展。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/api/
    

- 数据出口成本比较，涵盖了约 40 个流行的提供商和云服务，包括 Vercel、AWS、Fly 和 Linode。
    
    **长按识别二维码查看原文**
    
    https://getdeploying.com/reference/data-egress
    

- 🗣️ `/r/node` 上有一个关于 Node 应用程序文件结构的有趣讨论。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/171449/web
    

🛠 代码与工具

**Bruno：用于探索和测试 HTTP API 的 IDE** —— 这是一个基于 Node 和 Electron 的开源桌面应用程序（也有商业版本），用于创建和测试简单或复杂的 HTTP 请求。可以将其视为 Postman 的轻量级替代品。

**长按识别二维码查看原文**

https://github.com/usebruno/bruno

Anoop M D、Anusree P S 及贡献者

**Poolifier v5.0：Worker Threads 和 Cluster Worker 池** —— 使用 `worker_threads` 和 `cluster` 实现工作线程池。现在支持可中止任务。

**长按识别二维码查看原文**

https://github.com/poolifier/poolifier

Alessandro Pio Ardizio

**grammY：一个最新的 Telegram 机器人框架** —— 声称”让创建 Telegram 机器人变得如此简单，你已经知道该怎么做了”，并支持最新的 Telegram Bot API。GitHub 仓库。

**长按识别二维码查看原文**

https://grammy.dev/

KnorpelSenf

**🔥 0x 6.0：Node 单命令火焰图分析工具** —— 一个工具，可以通过单个命令为 Node 进程生成交互式火焰图。

**长按识别二维码查看原文**

https://github.com/davidmarkclements/0x

David Mark Clements

📢 其他

以下是 JavaScript 生态圈中一些其他有趣的故事，以防你错过：

- Deno 2.4 已发布，重新引入了 `deno bundle` 打包器，改进了对某些 Node 全局变量的支持，并总体上改进了 Node.js API 支持。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v2.4
    

- JS1024 是一年一度的 JavaScript 代码高尔夫比赛。你可以在 7 月 19 日之前提交一个 1024 字节或更少的 JavaScript 程序，主题是”恐怖”。
    
    **长按识别二维码查看原文**
    
    https://js1024.fun/
    

- Oliver Stenbom 探讨了”JavaScript 正在用 Rust 重写”的观点，或者至少，很多 JavaScript 工具正在用 Rust 重写。
    
    **长按识别二维码查看原文**
    
    https://endform.dev/blog/js-is-being-rewritten-in-rust/
    

- Loren Stewart 向我们展示了如何使用 ES6 代理构建轻量级响应式状态管理器。
    
    **长按识别二维码查看原文**
    
    https://www.lorenstew.art/blog/reactive-state-manager-with-proxies
    

- Rspack 1.4，这个基于 Rust 的高性能 Web 打包器（兼容 webpack）的最新版本已经发布，现在还可以在浏览器中运行，这要归功于 WebAssembly。
    
    **长按识别二维码查看原文**
    
    https://rspack.rs/blog/announcing-1-4
    

- 微软已经开源了其 VS Code 的 GitHub Copilot Chat 扩展。即使你对 AI 不感兴趣，它也提供了一个很好的视角来了解微软如何构建自己的扩展。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone
    

**版本发布：**

- **Babel v7.28.0** —— 这个流行的转译器获得了原生 TS 配置支持（需要 Node 24+）、ES2026 显式资源管理支持，以及 CommonJS `sourceType` 模式。

- **Inquirer.js v12.7** —— 常用交互式命令行 UI 工具集合（提示、密码输入、选择列表等）。

- **Repomix v1.1** —— 将整个仓库打包成单个 AI 友好的文件。

- **Secretlint v10.2** —— 防止提交凭证/密钥的工具。

- **Faker v9.9** —— 随心所欲地生成虚拟数据。

- **Oxlint v1.6** —— 由 Rust 驱动的 JS 和 TS 代码检查工具。