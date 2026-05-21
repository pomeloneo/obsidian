# Node 中文周刊 #107 - Payload v2.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524485&idx=1&sn=d1c04acbbdc1f79778832f609ec76fca&chksm=e9212b67de56a271f5258bdffc63c128647ad7e068b3a31cc74dae4f3311251bf9e943c4f460\#rd  
> 抓取时间: 2026/2/2 23:53:03

---

> 本期看点：如果需要基于 Node 的无头 CMS，那么可以考虑 Payload。它支持基于 React 的可定制管理系统、GraphQL 和 REST API、灵活的身份验证以及文件上传系统等功能。James 认为 Payload 的大量功能让人感觉更像是一个类似于 Laravel 的应用程序框架。在 v2.0 前仅支持 MongoDB，现在则引入了对 Postgres、Vite 的支持以及全新的富文本编辑器等等。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Payload v2.0：基于 Node 的无头 CMS** —— 如果需要基于 Node 的无头 CMS，那么可以考虑 Payload。它支持基于 React 的可定制管理系统、GraphQL 和 REST API、灵活的身份验证以及文件上传系统等功能。James 认为 Payload 的大量功能让人感觉更像是一个类似于 Laravel 的应用程序框架。在 v2.0 前仅支持 MongoDB，现在则引入了对 Postgres、Vite 的支持以及全新的富文本编辑器等等。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://payloadcms.com/blog/payload-2-0

James Mikrut

**Japa v3.0：声称完美的 Node.js 测试框架** —— Japa 和 **AdonisJS** 出自同一个作者之手，它可以融入你的工作流程而无需任何构建工具。它的作者甚至大胆声称：“Japa 在 Node.js 测试方面已经接近于完美”。

**长按识别二维码查看原文**

https://japa.dev/docs/introduction

Harminder Virk

**web 服务器的“Hello World”测试：Go vs Node vs Nim vs Bun** —— 以下是标准的免责声明：基准测试很困难并且不总是覆盖到你应该关心的内容。这篇博客通过在 Go、Node、Bun 和 Nim 中实现最简单的 HTTP 服务器进行比较。结论是 Node 表现良好，但是在实际中最好对更复杂的用例进行基准测试。

**长按识别二维码查看原文**

https://lemire.me/blog/2023/10/07/web-server-hello-world-benchmark-go-vs-node-js-vs-nim-vs-bun/

Daniel Lemire

**隐藏 Node 和 GraphQL 的性能成本** —— 作者指出，GraphQL 的模块化结构往往会导致代码实例化过多的 promises，进而降低请求的性能。

**长按识别二维码查看原文**

https://www.softwareatscale.dev/p/the-hidden-performance-cost-of-nodejs

Utsav Shah

💡 **Postgraphile** 提供了另一个与 Node 相关的方法。

**长按识别二维码查看原文**

https://postgraphile.org/

**Termost：又一个 CLI 框架** —— 虽然并非一定需要框架才能创建 CLI 应用，但是如果需要解析参数、打印彩色日志以及开箱即用的辅助功能，**Commander.js** 和 **oclif** 将帮助简化工作。现在 Termost 提供了另一种选择，它专注于提供流畅和可链式调用的 API 并且支持 TypeScript。

**长按识别二维码查看原文**

https://github.com/adbayb/termost

Ayoub Adib

**使用 Node 部署和测试 AWS Step Functions 的基础知识**。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/10/04/deploy-and-test-aws-step-functions-with-nodejs.html

Camilo Reyes

**快讯：**

- **📅 NodeConf EU 2023** 将于下个月（11 月 6 日到 8 日）在爱尔兰举行。

**长按识别二维码查看原文**

https://www.nodeconf.eu/

- ⚙️ V8 团队的 Stephen Röttger 在博客中介绍了他们在 **启用控制流完整性（CFI）上的努力**。从本质上来讲，这是一种降低恶意第三方利用 V8 的控制流来触发 shellcode 的方法。

**长按识别二维码查看原文**

https://v8.dev/blog/control-flow-integrity

- 🍞 又一周过去了，Bun 发布了 **Bun v1.0.4**，提高了对 Node.js 的兼容性以及大幅改善了 `Bun.serve()` 的内存使用量。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.0.4

- 🔠 Phil Nash 研究了 JavaScript 中一些 **正则表达式中的潜在危险**。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/vulnerable-regular-expressions-javascript/

- **🚫 现在 GitHub Actions workflows 不再支持使用 GITHUB_ENV** 设置 NODE_OPTIONS。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-10-05-github-actions-node_options-is-now-restricted-from-github_env/

## 🛠 代码与工具

**node-webrtc：与 WebRTC M94 绑定的原生插件** —— 该项目旨在符合规范并最终将使用 W3C 的 **web-platform-tests** 项目进行测试。node-webrtc 是一个历史悠久的库，这个分支因支持现代的 Node 而闻名。

**长按识别二维码查看原文**

https://github.com/WonderInventions/node-webrtc

Wonder Inventions, Roberts, et al.

**Visual Studio Code Extension Tester v5.10** —— 通过 Selenium Webdriver 模拟用户与 VS Code 扩展交互的框架。一个非常聪明的想法。

**长按识别二维码查看原文**

https://github.com/redhat-developer/vscode-extension-tester

Red Hat

**版本发布：**

- **🍀 MongoDB In-Memory Server v9.0**
    
    ↳ 用于测试或模拟数据的内存 MongoDB 实例。
    

- **oclif v4.0**
    
    ↳ 来自 Salesforce 的开源 CLI 框架。
    

- **Poolifier v3.0**
    
    ↳ 使用 `worker_threads` 和 `cluster` 实现的工作线程池。
    

- **Mongoose v7.6**
    
    ↳ 流行的 MongoDB 对象建模库。
    

- **ArangoJS v8.5**
    
    ↳ 官方的 ArangoDB Javascript 实现。
    

- **node-cron v3.1**
    
    ↳ 按照计划执行任务。
    

- **prom-client v15.0**
    
    ↳ 用于 Node 的 Prometheus 客户端。
    

- **oauth2-mock-server v7.0**

- **pnpm 8.9**

**🕰 精彩回顾：**

- Victor Ikechukwu **强调 Node 中 CORS 的安全影响** 并且提出了一些最佳实践。

- QA 工程师 Luc Gagan 在 Playwright 分享了 **如何识别和处理不稳定测试** 的文章。

- Najia Gul 对 **如何避免网络缓存中毒攻击** 进行了研究。

- 这篇博客概述了 **时间旅行调试** 以及它和调试生产代码的关系。

## 🙋🏻‍♀️