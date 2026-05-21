# Node 中文周刊 #155 - Transformers.js v3 发布：让 AI 模型在 Node.js 中运行

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247536920&idx=1&sn=ff559d7bb89e8283a8ff5da6c80b9df8&chksm=e9211afade5693ecf70b4817514abf387190685769e6e42e46d2ee489e3212746d8914c88392\#rd  
> 抓取时间: 2026/2/2 23:52:06

---

> 本期看点：Hugging Face 发布 Transformers.js v3，支持在 Node.js 环境运行 AI 模型；Node.js v22.11.0 晋升为 LTS 版本，v23.1.0 成为新的当前版本；依赖关系可视化工具 Dependency Cruiser、npm 脚本增强工具 Wireit。

> 编辑：TimLi

🔥 本周热门

**Transformers.js v3：现已支持在 Node.js 中运行 Transformer 模型** — 这是 Hugging Face 的 `transformers` Python 库的 JavaScript 移植版本，让你能够运行自然语言、视觉和音频机器学习模型。v3 版本新增了 WebGPU 支持，并且除了浏览器外，现在还支持 Node（以及 Deno 和 Bun）。目前已有超过 1200 个可用模型，涵盖嵌入、文本生成和语音识别（比如 whisper-small）等领域。

**长按识别二维码查看原文**

https://huggingface.co/blog/transformersjs-v3

**Node v22.11.0 ‘Jod’ 发布，成为活跃的 LTS 版本** — 随着此次发布，Node 22 从”当前”前沿版本转变为具有重要 LTS（长期支持）称号的稳定版本。不过，它与 Node v22.10 基本相同。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.11.0

**Node v23.1.0（当前版本）发布** — 在 Node 22 进入稳定期的同时，Node 23 接过”当前版本”的接力棒，将获得最新特性的更新，直到 2025 年 4/5 月 Node 24 发布。在 v23.1 中，JSON 模块和导入属性已经稳定，`MockTimers` 测试运行器 API 也已稳定，而且从可调整大小的 `ArrayBuffer` 创建的 `Buffer` 对象现在可以正确更新其大小。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.1.0

**理解** `**npm audit**` **和修复安全漏洞** — `npm audit` 通过将项目依赖与已知漏洞数据库进行比对来检查安全问题。

**长按识别二维码查看原文**

https://www.niraj.life/blog/understanding-npm-audit-fixing-vulnerabilities-nodejs/

**使用 Pongo 快速搭建 CRUD** — Pongo 是一个使用 Postgres 作为数据库但提供类似 MongoDB 风格的面向文档 API 的包。

**长按识别二维码查看原文**

https://event-driven.io/en/crud_with_pongo/

**📄 Node.js、管道和消失的字节** — 当将 Node 应用程序的输出通过管道传输到其他命令时，可能会出现一些神秘的问题。

**长按识别二维码查看原文**

https://sxlijin.github.io/2024-10-09-node-stdout-disappearing-bytes

**📄 构建 Node.js Stream 的心智模型**

**长按识别二维码查看原文**

https://pavel-romanov.com/building-a-mental-model-of-nodejs-streams

**📄 在 Node.js 中设置默认时区**

**长按识别二维码查看原文**

https://www.stefanjudis.com/today-i-learned/set-the-default-time-zone-in-node-js/

🛠 代码与工具

**Tinybench v3.0：小巧简单的基准测试库** — 使用可用的精确计时功能（如 `process.hrtime` 或 `performance.now`）。你可以对任何函数进行基准测试，指定测试时长或次数，并获得各种统计数据。GitHub 仓库。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinybench/releases/tag/v3.0.0

**Fetch Mock v12.0：模拟** `**fetch**` **API 请求** — 一个灵活的 API，用于模拟通过 `fetch` 或类 fetch 库发出的 HTTP 请求。支持浏览器、Node 和 web/service workers。

**长按识别二维码查看原文**

https://www.wheresrhys.co.uk/fetch-mock/

**parse-xml v4.2：快速、兼容的 XML 解析器** — 其目标是快速、健壮且具有良好的错误处理能力，并且没有原生依赖。v4.2 版本比之前的版本快了高达 28%。

**长按识别二维码查看原文**

https://github.com/rgrove/parse-xml

**Dependency Cruiser v16.5：依赖关系可视化工具** — 如果你想查看输出效果，这里有一整页真实项目的依赖图，包括 Chalk、Yarn 和 React。

**长按识别二维码查看原文**

https://github.com/sverweij/dependency-cruiser

**Wireit：让 npm/Yarn 脚本更智能、更 �� 效** — 基于 `npm run`，Wireit 为你的脚本增加了结果缓存、并行化和监视/重新运行等功能。还有一个 VS Code 扩展可以帮助你编写这些增强脚本。

**长按识别二维码查看原文**

https://github.com/google/wireit

**match-sorter v7.0：确定性的最佳匹配数组排序** — 如果你有一个需要过滤和确定性排序的数组，match-sorter 提供了一个特定的、可预测的算法。可以在这里体验在线演示。

**长按识别二维码查看原文**

https://github.com/kentcdodds/match-sorter

**AutoCannon v8.0：快速的 HTTP/1.1 基准测试工具** — 受 wrk 和 wrk2 启发，支持 HTTP 管道。

**长按识别二维码查看原文**

https://github.com/mcollina/autocannon

**版本发布：**

- **serverless-express v4.16** — 在 AWS Lambda、API Gateway、Lambda@Edge 等环境运行 Express，现已支持 Express 5。

- **Execa v9.5** — 强大的进程执行库。v9.5 在重定向 `stdout` 或 `stderr` 到文件时，可以选择追加而不是替换。

- **Medusa v2.0** — 流行的基于 Node.js 的电商平台。

- **📺 YouTube.js v11.0** — YouTube 私有 API 的非官方 JS 客户端。

- **Mineflayer v4.23** — 用 JavaScript 创建 Minecraft 机器人。

- **Faker v9.1** — 生成大量假数据。

- **AVA v6.2** — 流行的 Node 测试运行器。

- **Opossum v8.2** — 断路器库。

🙋🏻‍♀️