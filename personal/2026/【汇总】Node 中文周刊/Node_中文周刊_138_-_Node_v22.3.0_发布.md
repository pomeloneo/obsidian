# Node 中文周刊 #138 - Node v22.3.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532439&idx=1&sn=1cc05e1c130c69da28c8f151475187d7&chksm=e9213475de56bd6386aac0c649bcf1fd8578a9e9ffa89c63022c380f23a511da04c7eb861b8b\#rd  
> 抓取时间: 2026/2/2 23:52:26

---

> 本期看点：Node v22.3.0 发布，包含了许多小改动，以及快照测试。研究人员发现 npm 注册表易受缓存投毒攻击。当一个重要的 npm 库进行商业化时会发生什么？

> 编辑：loveloki、TimLi

🔥 本周热门

Node v22.3.0（Current）发布 — 这是一个包含许多小改动的版本，除了 快照测试  外没有重大变化。快照测试将任意值序列化为字符串，与一组预构建的已知“良好”值进行比较（存储为代表期望状态的“快照”）。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.3.0

Rafael Gonzaga

研究人员发现 npm 注册表易受缓存投毒攻击 — 这个漏洞的基本思想是，特定版本的目标包可以被伪装成在短时间内不可用。这不是一个**巨大的**漏洞，但仍然很重要，GitHub 正在修复。

**长按识别二维码查看原文**

https://socket.dev/blog/npm-registry-vulnerability-to-cache-poisoning-and-dos-attacks

Sarah Gooding (Socket)

使用 `tsup` 和 ‘Are the Types Wrong’ 同时发布 ESM 和 CJS 模块 — tsup 让捆绑 TypeScript 库变得容易，Are the Types Wrong? 是一个用于分析包中 TypeScript 类型问题的工具，特别是与 ESM 相关的模块解析问题。

**长按识别二维码查看原文**

https://johnnyreilly.com/dual-publishing-esm-cjs-modules-with-tsup-and-are-the-types-wrong

John Reilly

当一个重要的 npm 库进行商业化时会发生什么？ — 每月下载量超过 1200 万的 ua-parser-js 库常用于解析用户代理字符串。最近转变为 AGPL+ 商业许可。

**长按识别二维码查看原文**

https://adventures.nodeland.dev/archive/what-happens-when-a-major-npm-library-goes/

Matteo Collina

**快讯：**

👨🏾‍💻 加入 Sentry 于 7 月 16 日举办的会议，和 Node、Laravel、Prisma 、Supabase 的 CEO、核心开发者一起讨论后端开发趋势。现在预约吧 ！

**长按识别二维码查看原文**

https://sentry.io/resources/?utm_medium=paid-community&utm_source=nodeweekly&utm_campaign=fy25q2-roundtable-backend&utm_content=newsletter-roundtable-backend-register

🪝 Hookdeck：为你的事件驱动应用提供无服务器队列。了解更多。

**长按识别二维码查看原文**

https://hookdeck.com/discover/nodeweekly?ref=nodeweekly-536

📄 如何在 Node 中为视频创建 WebVTT 文件（使用 AssemblyAI） – Web 视频文本轨格式（WebVTT）是字幕/闭幕字幕的常见标准。AssemblyAI 的平台在这方面做了大量工作。

**长按识别二维码查看原文**

https://www.assemblyai.com/blog/vtt-video-nodejs/

Niels Swimberghe

📄 用 20 种语言实现 UUIDv7 – 出乎意料地简短而甜美。

**长按识别二维码查看原文**

https://antonz.org/uuidv7/

Anton Zhiyanov

📄 在 Playwright 中编写你的第一个视觉回归检查

**长按识别二维码查看原文**

https://www.checklyhq.com/blog/screenshot-monitoring-with-playwright/

Nočnica Mellifera

📄 在 Node 应用中捕获垃圾回收轨迹 CoderOasis

**长按识别二维码查看原文**

https://coderoasis.com/capturing-nodejs-garbage-collection-traces/

📄 调用 Google Gemini 时使用 JSON Schema

**长按识别二维码查看原文**

https://www.raymondcamden.com/2024/06/11/using-json-schema-with-google-gemini

Raymond Camden

🛠  代码与工具

super-regex：超时长运行正则表达式 — 许多正则表达式实现存在所谓的 ReDoS 漏洞，某些正则表达式可能导致过长的评估时间。`super-regex` 引入了正则表达式**超时**的能力，当执行时间过长时自动超时。

**长按识别二维码查看原文**

https://github.com/sindresorhus/super-regex

Sindre Sorhus

💡 `super-regex` 只是封装了 Node 的常规正则表达式实现，但如果你能容忍完全切换到另一个正则表达式引擎，RE2JS 也值得一看。

**长按识别二维码查看原文**

https://github.com/le0pard/re2js

Electron 31.0.0：跨平台桌面应用框架 — Chromium 升级到 v126，V8 升级到 v12.6，Node.js 升级到 v20.14.0。WebSQL 支持终于被移除。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-31-0

OpenJS Foundation

Eicrud：基于 NestJS 的 CRUD/授权框架 — 扩展 NestJS / Fastify，并与 MikroORM、CASL 和 class-validator 一起工作。GitHub 仓库

**长按识别二维码查看原文**

https://eicrud.com/

**版本发布：**

- Ts.ED 7.72 – 基于 Express 的 Node + TypeScript 框架。

- pnpm 9.4 – 快速、高效的包管理器。

- Fastify 4.28 – 快速、低开销的 Node Web 框架。

- ESLint 9.5.0

🙋🏻‍♀️