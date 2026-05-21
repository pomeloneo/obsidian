# Node 中文周刊 #112 - 来自 Node.js Collab Summit 2023 的演讲

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525122&idx=1&sn=29687645369c150379071701272edb98&chksm=e92128e0de56a1f6826dfbecab8226daed329b0cbc7a81a78b463230ef918599067f67cf3243\#rd  
> 抓取时间: 2026/2/2 23:52:57

---

> 本期看点：如果想要跟上 Node 项目内部的最新讨论，可以看看本期介绍的最新 Node.js Collab Summit 的视频。例如视频中就介绍了 Milo，Paolo Insogna 为 Node 开发的新的 Rust 驱动的 HTTP 解析器。

> 编辑：Yucohny

## 🔥 本周热门

**36 个 Node CLI 应用程序最佳实践** —— 来自多个基于 Node 的 CLI 工具的创作者，这是一系列有助于使用 Node 构建成功的用户友好的 CLI 工具的最佳实践集合，这里还附有一个 **总结流行 CLI 框架选项的附录**。

**长按识别二维码查看原文**

https://github.com/lirantal/nodejs-cli-apps-best-practices

Liran Tal

**▶ 来自 Node.js Collab Summit 2023 的演讲** —— 如果想要跟上 Node 项目内部的最新讨论，这里有最新 Node.js Collab Summit 的视频。例如视频中就介绍了 **Milo**，Paolo Insogna 为 Node 开发的新的 Rust 驱动的 HTTP 解析器。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLyspMSh4XhLMSx9Bcdnt1aU1WdRnk3mZy\#collabsummit

OpenJS Foundation

**Bun 是否会吃掉 Node.js 的午餐？** —— 一个将一个代码库（一个名为“午餐”的餐厅投票应用）从 Node 迁移到 Bun 并查看其表现的实验。他们对其印象深刻，但发现它“尚未准备好投入生产，因为仍然在常见任务中会遇到分段错误。”

**长按识别二维码查看原文**

https://labzero.com/blog/can-bun-eat-node-js-s-lunch-testing-the-trendy-toolkit

Jeffrey Carl Faden

**安全代码审查提示以防范易受攻击的 Node 代码** —— 如何识别易受攻击的代码模式？能发现不足的输入验证吗？这篇安全代码审查指南能够帮助增强 Node 开发的安全性。

**长按识别二维码查看原文**

https://www.nodejs-security.com/blog/secure-code-review-tips-to-defend-against-vulnerable-nodejs-code

Liran Tal

**不保持与 DynamoDB 一致性的影响**

**长按识别二维码查看原文**

https://advancedweb.hu/the-effects-of-not-maintaining-consistency-with-dynamodb/

Tamás Sallai

`**git rebase**` **可能出现的问题有？**

**长按识别二维码查看原文**

https://jvns.ca/blog/2023/11/06/rebasing-what-can-go-wrong-/

Julia Evans

**在 Node 中使用 Timeout**

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/11/08/how-to-use-timeouts-in-nodejs.html

Antonello Zanini

**快讯：**

- 来自 Node 核心团队的 Erick Wendel 提醒 Node v20.5 及更高版本将支持 **水平分区/分片测试**，即可以使用 `-test-shard` 参数，并传入总共的分区数以及要运行的分区号。

**长按识别二维码查看原文**

https://twitter.com/erickwendel_/status/1724075830400164215

- **Prettier v3.1** 已发布，并且支持上周发布的 **Angular 17** 中的新控制流语法以及一个新的实验性的三元表达式格式化选项（例如 `x ? y : z`）。

**长按识别二维码查看原文**

https://prettier.io/blog/2023/11/13/3.1.0

- Node TSC 成员 Yagiz Nizipli 建议 **使用 Biome 进行代码格式化**，因为 ESLint 已 **弃用了其核心格式化规则**。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/50672

- 如果正在使用 Amazon SQS，请考虑 **更新 AWS SDK 以减少延迟** —— AWS 推出了一种新的、更有效的基于 JSON 的协议。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/aws/new-for-amazon-sqs-update-the-aws-sdk-to-reduce-latency/

## 🛠 代码与工具

**Wild Wild Path v5：带通配符和正则表达式的对象属性路径** —— 一种访问对象属性的狂野方式（可以是深度嵌套的），通过支持通配符和正则表达式的基于字符串的查询。**这些示例** 有助于理解这个概念。

**长按识别二维码查看原文**

https://github.com/ehmicky/wild-wild-path

ehmicky

**Globby v14.0：用户友好的 Glob 匹配** —— 给它一组 Glob 模式，它会返回一组匹配的路径。它甚至支持否定匹配和 `.gitignore`。

**长按识别二维码查看原文**

https://github.com/sindresorhus/globby

Sindre Sorhus

**cRonstrue：将 Cron 表达式转换为自然语言的库** —— 不仅仅是英语，还支持约 **三十种不同的区域设置**。这里有 **一个在线演示**。

**长按识别二维码查看原文**

https://github.com/bradymholt/cRonstrue

Brady Holt

**HyperExpress v6.14：由 uWebSockets.js 提供支持的高性能服务器** —— 尽管名字里有 Express.js，但与 Express.js 没有任何关系，尽管它确实具有一些有限的 API 兼容性。想要快速提供 WebSocket 服务的可以试试。

**长按识别二维码查看原文**

https://github.com/kartikk221/hyper-express

Kartik

**nve 17：使用特定的 Node.js 版本运行事务** —— 使用特定版本（或多个版本）的 Node 执行文件、命令或 REPL。例如，可以一次运行 `npm test` 在多个版本上，需要注意 Node 最低版本是 v18.18.0。

**长按识别二维码查看原文**

https://github.com/ehmicky/nve

ehmicky

**wait-on v7.1：等待端口、文件、套接字等的 CLI 和 Node 库** —— 当需要等待文件、端口、套接字等类似资源变得可用时（或相反）时。

**长按识别二维码查看原文**

https://github.com/jeffbski/wait-on

Jeff Barczewski

**版本发布：**

- **tsx v4.x** – 在 Node.js 中运行 TypeScript 和 ESM。

- **Marked v10.0** – Markdown 解析器和编译器。

- **marked-terminal v6.1** – 在终端打印 Markdown 的 Marked（上述解析器）的渲染器。

- **getmac v6.0** – 获取所在机器的 MAC 地址。

- **express-openapi-validator v5.1** – 使用 Express 和 OpenAPI 3.x 规范自动验证 API 请求和响应。

- **Nightwatch v3.3** – 集成的端到端测试框架。

- **Middy v4.7** – 用于 AWS Lambda 的 Node 中间件引擎。

## 🙋🏻‍♀️