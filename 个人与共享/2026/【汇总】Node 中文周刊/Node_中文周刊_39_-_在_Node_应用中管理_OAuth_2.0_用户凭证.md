# Node 中文周刊 #39 - 在 Node 应用中管理 OAuth 2.0 用户凭证

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247506208&idx=1&sn=e6623e79819375ab82bbc03d021388bf&chksm=e92192c2de561bd4256fbbd88d5c906bd4a6d046d74d84c58880ca216d7ef4d831b853315eeb\#rd  
> 抓取时间: 2026/2/2 23:54:33

---

> 本期看点：本期为大家带来了如何在 TypeScript 中使用新的 ES 模块和在 Node 应用中管理 OAuth 2.0 用户凭证等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、辛宝 Otto、gaao

## 🔥 本周热门

**增强 `npm` 账号的两步验证体验** — 过去的六个月，GitHub 致力于持续加强 `npm` 发布过程中的安全性，两步验证（tow-factor authentication，简称 2FA）是其中非常重要的增强安全手段。目前，2FA 已经处于公开测试阶段。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123442/web

Myles Borins (GitHub)

**Web-Interoperable JavaScript Runtimes 社区小组成立** — Cloudflare、Vercel、Shopify、Node 和 **Deno** 的核心贡献者们成立了一个新的小组，这个小组将围绕互操作性，和基于 JS 环境但不属于浏览器的 Web API 开发标准展开工作。就像浏览器在功能上协作一样，后端平台的功能也可以彼此协作。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123474/web

James M Snell

**Ryan Dahl 在 JavaScript Containers 的发言** — Ryan 是 Node 的原作者，也是 Deno 的作者。他认为 JavaScript 是一种通用脚本语言，同时谈论了 JS 沙箱如何充当一种高级版本的传统的 Linux 容器，并且在未来几年中只会变得更加重要。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123444/web

Ryan Dahl

**解决了针对行业后门的 npm Packages 问题** — Snyk、JFrog 和 ReversingLabs 花了相当多的时间查看一家 **安全研究公司的实习生** 构建的模块，它们用于研究依赖性混淆。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123446/web

The Register

**快讯：**

- 📅 **NodeConf EU** 将在 10 月 3-5 号在爱尔兰举办。如果你想发言参与讨论，可以在 7 月 6 号之前进行 联系。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/123448/web
    

- **Jest** 是 JS 测试框架，它 **正在加入 OpenJS 基金会**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/123450/web
    

- 一些 Node 版本发布的原因是在 OpenSSL 或者 V8 等关键依赖中发现了漏洞。OpenSSL 现在有一个 **低风险** 的问题，具体细节解释可以参考 **Rafael Gonzaga 的文章**。但这个问题重要性不足以让 Node 发布新版本。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/123452/web
    

- Node v16 LTS 已经可以在 Vercel 中使用了，AWS Lambda **也即将官方支持**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/123455/web
    

- npm 启用两步验证是一个重要举措，如果对此你有疑惑，这里介绍了 **通过购买过期域名来接管流行的 npm 包**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/123456/web
    

**怎么在 Node 模块中调用勒索软件攻击** — 这个开始是作为一个学习实验的，为了看看这是多么难的后来变成了很容易。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123458/web

Charlie Gerard

**我们如何在 TypeScript 中使用新的 ES 模块支持**

**长按识别二维码查看原文**

https://nodeweekly.com/link/123459/web

Yonatan Kra

**如何使用 GitHub Pull API 来管理 Pull Request**

**长按识别二维码查看原文**

https://nodeweekly.com/link/123460/web

Carlos Schults

**在 Node 应用中管理 OAuth 2.0 用户凭证**

**长按识别二维码查看原文**

https://nodeweekly.com/link/123460/web

Shehzad Akbar

## 🛠 代码与工具

**GraphQL Yoga v2.0：一个轻量但功能全面的 GraphQL 服务** — 号称“最简单的方式运行 GraphQL 服务”，Yoga 遵循 `GraphQL over HTTP spec`，支持文件上传，通过 HTTP 服务发送订阅事件等等。它可在 Node、Deno、Serverless 上运行。GitHub 地址。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123461/web

Michał Tyszkiewicz

**URL State Machine：快速的符合规范的 URL 状态机** — 旨在遵循 WhatWG 规范。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123463/web

Yagiz Nizipli

**Agenda v4.3：Node 中轻量的任务调度方案** — 使用 MongoDB 作为后端持久层，提供了速度限制，暂停和启用切换，重复任务等功能。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123466/web

Ryan Schmukler

**nve v15.0：使用特定的 Node 版本执行脚本** — 可在文件、命令行、REPL 交互环境下执行指定 Node 版本或者多个版本的命令。比如，同时在多个环境下运行 `npm test`。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123467/web

ehmicky

**Kafka.js v2.0：现在的 Apache Kafka 客户端** — 生产可用，支持 Kafka v0.10+。Kafka 是流行的开源系统，可以用于大规模处理流处理任务。作为 4 年来第一个主要的版本，也提供了 迁移指南。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123468/web

Túlio Ornelas

**MongoDB 官方 Node 驱动 v4.6.0** — 你可以在 `change` 事件中返回的顶级文档中定义类型。

**长按识别二维码查看原文**

https://nodeweekly.com/link/123471/web

MongoDB Inc.

**Hexo v6.2：快速、简单的 Node.js 博客框架**

**长按识别二维码查看原文**

https://nodeweekly.com/link/123473/web

Hexo

## 🙋🏻‍♀️