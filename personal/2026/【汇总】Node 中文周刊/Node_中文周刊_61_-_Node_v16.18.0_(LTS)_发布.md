# Node 中文周刊 #61 - Node v16.18.0 (LTS) 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511351&idx=1&sn=39f5434dbcd2917e3e3b0b284af42101&chksm=e921e6d5de566fc3f3bb26ad43f2c176a1e2ac2a0028b4878173f8cb02f7689d0d91b21df870\#rd  
> 抓取时间: 2026/2/2 23:54:06

---

> 本期看点：Dr. Axel 为我们带来本期精彩文章：《如何编写 CommonJS 模块，以便它们的导出可以从 ES 模块实现按照名称导入》。

> 编辑：gaao12、Yucohny

## 🔥 本周热门

**njt：快速导航至 npm 包资源** — 如果你想要快速访问 npm 包的首页、仓库、issues，甚至包成本估算，那么 njt 将会是一个不错的选择。njt 提供了一个快速跳转到与 npm 包相关的各种资源目的地的方法。你可以在终端中安装并使用，也可以通过 **LaunchX 扩展程序** 将 njt 添加至 VS Code 的命令面板然后使用，或者在 Google 与 Firefox 浏览器进行配置然后搜索，亦或 **直接在网页上使用它**。如果你对此有兴趣，可以来看看 GitHub 仓库。

**长按识别二维码查看原文**

https://www.npmjs.com/package/njt

Alexander Kachkaev

**Node v16.18.0 (LTS) 发布** — 主要是向后兼容的修复和调整——没有大的更新。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v16.18.0/

Juan José (Node Core Team)

**如何编写 CommonJS 模块，以便它们的导出可以从 ES 模块实现按照名称导入** — 如果你曾经在使用 CommonJS 和 ES 模块之间纠结过，那么这篇文章或许值得一读。Axel 博士在这里解决了一个关键的交叉兼容性问题。

**长按识别二维码查看原文**

https://2ality.com/2022/10/commonjs-named-exports.html

Dr. Axel Rauschmayer

**向 Jest 测试添加 OpenTelemetry Observability** — 如何通过关注事物来从 Jest 的测试中获得更多。

**长按识别二维码查看原文**

https://sprkl.dev/observability-jest-tests/

Eliran Maman (Sprkl)

🔐 **使用 Twilio Verify 进行 Node.js 身份验证** — 如果您对使用第三方服务感到满意，那么将 2FA 引入您的 Express.js 应用程序并不难。作者演示了通过创建一个简单的应用程序，展示了如何使用基于密码的身份验证以及由 Twilio 的 **Verify API** 提供支持的额外 OTP（一次性密码）层来验证用户身份。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/10/nodejs-authentication-twilio-verify/

Alexander Godwin

## 🛠 代码与工具

**IP Index：快速的离线 IP 查找库** — 作为快速的离线 IP 查找库，它将提供有关 IP 的信息，包括黑名单状态、VPN/主机，以及地理和 ASN 信息等。值得注意的是，GitHub 仓库也每天更新。

**长按识别二维码查看原文**

https://github.com/Umkus/ip-index

Mykhailo Gorianskyi

**cRonstrue：将 `cron` 表达式转换为人类可读形式** — cRonstrue 是一个 JavaScript 库，它解析 `cron` 表达式并输出人类可读的形式。例如，给定表达式 `*/5* ** *`，它将输出“每 5 分钟”。该库是从名为 cron-expression-descriptor 的原始 C# 实现移植而来的，并且还可以在其他几种语言中使用。

**长按识别二维码查看原文**

https://github.com/bradymholt/cronstrue

Brady Holt

**Whoiser：为 Node.js 打造的 WHOIS 客户端** — 给定域名、TLD 或 IP 地址，它会查询在线 WHOIS 数据库以获取信息。

**长按识别二维码查看原文**

https://www.npmjs.com/package/whoiser

Andrei Igna

**Print Ready：将 HTML 转换至 PDF** — 这是一个基于 JavaScript 的 CLI，用于将 HTML 转换为 PDF。

**长按识别二维码查看原文**

https://github.com/humanwhocodes/print-ready

Nicholas C. Zakas

**Check HTML Links：HTML 中断链/引用的快速检测器** — 你可以在静态页面上运行来查找 `href`，`src`，与 `srcset` 中的断链，并且可以在几秒钟内处理 500-1000 个文档。

**长按识别二维码查看原文**

https://github.com/modernweb-dev/rocket/tree/main/packages/check-html-links

Modern Web

**human-signals：获取 Process 进程信号信息** — 本质上是一个 JavaScript 对象，但是包含了有关各种 POSIX 信号的信息（如 `SIGHUP`, `SIGINT` 等）。

**长按识别二维码查看原文**

https://github.com/ehmicky/human-signals

ehmicky

**Flyweight：一种面向 SQLite 的全新 ORM** — 还处于早期，但围绕 SQLite 提供了一些额外的抽象，你可能会喜欢。

**长按识别二维码查看原文**

https://github.com/thebinarysearchtree/flyweight

Andrew Jones

**版本发布：**

- **AdminJS v6.4**
    
    ↳ Node 应用程序的管理面板/UI。
    

- **Faker v7.6**
    
    ↳ 生成大量模拟数据。
    

- **Middy v3.6**
    
    ↳ 适用于 AWS Lambda 的 Node 中间件引擎。
    

- **quagga2 v1.7.5**
    
    ↳ 浏览器和 Node 的高级条码扫描。
    

- **node-jira-client v8.2**
    
    ↳ Jira REST API 的 Node 包装器。
    

- **RedisSMQ v7.1.1**
    
    ↳ 高性能 Redis 消息队列。
    

## 🙋🏻‍♀️