# Node 中文周刊 #119 - Node v21.6.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526099&idx=1&sn=73879061d52a12041bf25bf52769c414&chksm=e9212d31de56a427a843e537f708e4bf035b17b1c7976aa4ed9b9756c0a4cd890ab798d1047b\#rd  
> 抓取时间: 2026/2/2 23:52:49

---

> 本期看点：Node v21.6.0（Current）已发布，最新版本包括对实验性权限模型的改进，通过 JSON 配置文件配置快照的能力，以及在 `net.createConnection` 流中提供的三个新事件。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**npm 回顾：从数字中追溯** —— Socket 带来了对 npm 注册表过去一年的回顾，主要关注统计数据（有 250 万个活跃包！），包括下载数量、热门包，以及一些“古怪的事实”，比如拥有最多维护者的包（如果你好奇的话，是 554 个）。

**长按识别二维码查看原文**

https://socket.dev/blog/2023-npm-retrospective

Philipp Burckhardt（Socket）

**Node v21.6.0（Current）发布** —— 最新版本包括对 **实验性权限模型** 的改进，通过 JSON 配置文件配置快照的能力，以及在 `net.createConnection` 流中提供的三个新事件。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v21.6.0

Rafael Gonzaga

**Node v20.11.0（LTS）发布** —— 与此同时，“可能应该使用的Node版本”经历了各种调整，其中最引人注目的可能是添加了 `import.meta.dirname` 和 `import.meta.filename`，它们发挥了与 `__dirname` 和 `__filename` 相同的作用，但适用于新的、闪亮的 ES 模块化世界。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.11.0

Ulises Gascón

**在 Cloudflare Workers 上使用 AssemblyAI 转录音频** —— 这可能有点特定于平台，但我们一直在尝试使用 AssemblyAI 进行音频转录，效果非常好。

**长按识别二维码查看原文**

https://www.assemblyai.com/blog/transcribe-audio-cloudflare-workers-assemblyai-nodejs-typescript/

Niels Swimberghe（AssemblyAI）

**在 Node 中防止和调试内存泄漏** —— 这是关于实用基础知识的入门指南。

**长按识别二维码查看原文**

https://betterstack.com/community/guides/scaling-nodejs/high-performance-nodejs/nodejs-memory-leaks/

Stanley Ulili

**快讯：**

- Yagiz Nizipli 参加了 Syntax․fm 播客，**▶️谈论了 JavaScript 性能和新的 Node 功能**。如果你有一个小时的时间，那么这个关于各种 Node 主题的精彩更新不容错过。

**长按识别二维码查看原文**

https://syntax.fm/show/716/js-perf-wins-and-new-node-js-features-with-yagiz-nizipli

- Josh Sherman 进行了一次最新的 **DigitalOcean、Linode 与 Vultr 的基准测试**。

**长按识别二维码查看原文**

https://joshtronic.com/2024/01/07/vps-showdown-january-2024-digitalocean-vs-linode-vs-vultr/

- Simon Willison 演示了他如何通过连接 GitHub Action、Issue 与 Page **创建一个每日计划**。

**长按识别二维码查看原文**

https://til.simonwillison.net/github-actions/daily-planner

## 🛠 代码与工具

**Tinybench：小巧简单的基准测试库** —— 无依赖，但使用可用的精确计时功能（例如 `process.hrtime` 或 `performance.now`）。然后就可以对任何想要的函数进行基准测试，指定要进行基准测试的时间或次数，并获得各种统计信息。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinybench

Tinylibs

**Fast-CSV v5.0：基于流的 CSV 解析器和格式化器** —— 一个长期维护的库，多年来一直得到良好的维护，并在 2024 年迎来了一个重大的新版本。它以“流为先”的方式构建，以避免在处理大型数据集时对大内存的需求，它提供了开箱即用的灵活性。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://c2fo.github.io/fast-csv/

C2FO

**⌨️🐈 wacat：使用“猫咪混乱”测试 Web 应用程序** —— 采用“猫咪走过键盘”的方式来折磨 Web 应用程序，模拟随机的点击和表单提交。

**长按识别二维码查看原文**

https://github.com/mikesmallhelp/wacat

Mika Tapanainen

**Automock：改善优化单元测试流程** —— 一个专为单元测试设计的库（与 Jest、Sinon 或 NestJS 一起使用），依赖于 TypeScript 生成模拟对象，通过自动模拟类的外部依赖等方式简化测试过程。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://automock.dev/docs/getting-started/

Omer Morad

**web-worker v1.3：浏览器与 Node 一致的 Web Workers** —— 在 Node 中，它作为基于 `worker_threads` 的与 Web 兼容 Worker 实现。在浏览器中，它是 `Worker` 的别名，因此可以在创建同构模块时获得更一致的体验。

**长按识别二维码查看原文**

https://www.npmjs.com/package/web-worker

Jason Miller

**版本发布：**

- **Piscina v4.3** – 高效的工作线程池实现。

- **Nock v13.5** – HTTP 服务器模拟和期望库。

- **Mongo Seeding v4.0** – 用于填充 MongoDB 数据库的工具。

- **find-my-way v8.1** – 高性能的 HTTP 路由库。

- **emoji-regex** – 用于匹配所有仅包含表情符号的正则表达式。

- **hostile v1.4** – 编程式操作 `/etc/hosts`。

- **Necord v6.6** – 使用 NestJS 创建 Discord 机器人。

- **Prettier v3.2**

## 🙋🏻‍♀️