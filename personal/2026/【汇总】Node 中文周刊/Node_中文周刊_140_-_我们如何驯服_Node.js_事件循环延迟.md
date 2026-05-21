# Node 中文周刊 #140 - 我们如何驯服 Node.js 事件循环延迟

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533161&idx=1&sn=4157c43d05d1aced92a58770737f4419&chksm=e921098bde56809d0894ba9480c7f7a8a2ee3e3feaa7258f2e8d869e22f714d2e3acb2cb080f\#rd  
> 抓取时间: 2026/2/2 23:52:24

---

> 本期看点：Node 众所周知使用很少的线程却能高效地处理大量客户端，只要与每个客户端相关的工作够‘小’即可。然而，当你遇到嵌套循环时，就像在这个故事中一样，情况可能迅速失控。Node 官网的这篇指南：不要阻塞事件循环包含了最佳实践。

> 编辑：TimLi

🔥 本周热门

**我们如何驯服 Node.js 事件循环延迟** — Node 众所周知使用很少的线程却能高效地处理大量客户端，只要与每个客户端相关的工作够‘小’即可。然而，当你遇到嵌套循环时，就像在这个故事中一样，情况可能迅速失控。Node 官网的这篇指南：不要阻塞事件循环包含了最佳实践。

**长按识别二维码查看原文**

https://trigger.dev/blog/event-loop-lag

Eric Allam

**Node 的 2024 年 7 月 2 日安全发布** — 上周发布了维护版本的 22.x、20.x 和 18.x 以解决五个不同的安全漏洞/问题。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/july-2024-security-releases

The Node.js Project

**📊 分析 Node.js 应用程序** — 如果你遇到不寻常的性能问题，分析你的应用可以找出问题的来源。本教程提供了一个示例项目，并涵盖了多种分析方法。

**长按识别二维码查看原文**

https://betterstack.com/community/guides/scaling-nodejs/profiling-nodejs-applications/

Stanley Ulili

**如何在 Node 中执行数据验证** — 探讨了 Node 后端的数据验证，并向我们展示了如何在 Express 中使用 express-validator 库来实现。

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/06/19/how-to-perform-data-validation-in-nodejs.html

Antonello Zanini

**📄 使用 Serverless Framework 和 Node.js 部署 AWS Lambda 函数** Marco Moauro

**长按识别二维码查看原文**

https://implementing.substack.com/p/deploy-aws-lambda-functions-with-serverless-node

**📄 在 TypeScript 中创建具有 CommonJS 和 ESM 支持的 npm 包** Waldek Mastykarz

**长按识别二维码查看原文**

https://blog.mastykarz.nl/create-npm-package-commonjs-esm-typescript/

**📄 超越等宽字体：寻找完美的编码字体** Shamin 和 Turner (Evil Martians)

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/beyond-monospace-the-search-for-the-perfect-coding-font

🛠  代码与工具

**SquirrellyJS v9: 一个强大的模板引擎** — 一个现代、可配置且快速的模板引擎，承诺拥有“与 Nunjucks 同样的强大功能”和“与 EJS 同样的简单性”。如果你想看实际效果，可以试试在线演示。GitHub  仓库.

**长按识别二维码查看原文**

https://squirrelly.js.org/

Ben Gubler

**fast-json-stringify v6.0: 比** `**JSON.stringify()**` **快 2 倍？** — 特别是在小负载情况下，比 `JSON.stringify()` 显著更快，随着负载增大，其性能优势减少。

**长按识别二维码查看原文**

https://github.com/fastify/fast-json-stringify

Fastify

**Dats v5.1: 一个最小的零依赖** `**statsd**` **客户端库** — StatsD 是由 Etsy 原创开发的统计/指标聚合服务。

**长按识别二维码查看原文**

https://github.com/immobiliare/dats

Immobiliare Labs

**版本发布：**

- **Hexo v7.3** - 流行的博客框架/生成器。

- **xero-node v8.0** - 为流行的 Xero 会计系统提供的 Node SDK。

- **🌈 yoctocolors v2.1** - 最小的终端文本着色库。

- **MongoDB Node.js Driver v6.8** - 最新的官方 MongoDB 驱动程序。

- **js-bson v6.8** - Node 和浏览器的 MongoDB BSON 解析器。

- **ESLint v9.6.0**

🙋🏻‍♀️