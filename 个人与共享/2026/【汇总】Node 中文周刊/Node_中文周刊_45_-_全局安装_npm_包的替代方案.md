# Node 中文周刊 #45 - 全局安装 npm 包的替代方案

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507745&idx=1&sn=9c880083cdf25ce7a1a9575089cb00d0&chksm=e92194c3de561dd5770fbcedcf27bf6de09d0564afd47ad6c3ab30d146abf3f358b963ade76f\#rd  
> 抓取时间: 2026/2/2 23:54:26

---

> 本期看点：Axel Rauschmayer 在 2ality 发表了博客，探讨了全局安装 npm 包的替代方案；js-fire v1.0 发布，我们将可以通过 JS 对象生成 CLI。

> 编辑：Yucohny、Otto-J

## 🔥 本周热门

**在 Node.js 中使用 Web Streams** — Web Streams 是 Stream 的一种标准，如今包括 Web 浏览器、Node.js 和 Deno 在内的所有主要 Web 平台都支持 Web Streams。Streams 是一种方便易用的抽象，用于从各种来源（比如文件、服务器上托管的数据等）按小块顺序读取和写入数据。这篇文章讲述了如何在 Node.js 中使用 Web Streams。

**长按识别二维码查看原文**

https://2ality.com/2022/06/web-streams-nodejs.html

Dr. Axel Rauschmayer

**全局安装 npm 包的替代方案** — 如果在 macOS 或其他一些 Unix 平台上想要全局安装 npm 包，那么可能需要 root 访问权限——这是一个相当大的缺点。这篇博客文章探讨了全局安装 npm 包的替代方案。

**长按识别二维码查看原文**

https://2ality.com/2022/06/global-npm-install-alternatives.html

Dr. Axel Rauschmayer

**Puppeteer v15.0：使用 Node 控制无头 Chrome** — **Playwright** 近几年在远程控制浏览器领域吸引了很多关注，但专注于控制 Chrome 的 Puppeteer 仍然是一个很好的选型方案。它现在支持 Chromium v103 和 Node v18。

**长按识别二维码查看原文**

https://pptr.dev/

Google

**快讯：**

- 你想要一个 **把所有的 npm 包按照字母顺序排序的分页列表吗**？感谢 `@zzzzzzzzz/switcha` 实现了这个功能。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/npm
    

- **Node v18.4.0** 发布，这是一个相对次要的版本，没有大的变化。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v18.4.0/
    

- 我们之前提到过 Node v18.3+ **内置命令行参数解析** 功能，但很多人还不了解，这是一篇介绍文章。
    
    **长按识别二维码查看原文**
    
    https://pawelgrzybek.com/til-node-js-18-3-comes-with-command-line-arguments-parser/
    

**版本发布：**

**npm v8.13**

**长按识别二维码查看原文**

https://github.com/npm/cli/releases/tag/v8.13.0

**Pino v8.1** – 高效的 JSON 格式日志库。

**长按识别二维码查看原文**

https://github.com/pinojs/pino

**Fastify v4.1** – 轻量、高效的 web 框架。

**长按识别二维码查看原文**

https://github.com/fastify/fastify

**stripe-node v9.9** – 支持 Stripe API。

**长按识别二维码查看原文**

https://github.com/stripe/stripe-node

**Faker v7.3** – 快速生成 mock 数据。

**长按识别二维码查看原文**

https://github.com/faker-js/faker

**jsdom v20.0** – Node 中实现 WHATWG DOM 和 HTML 标准。

**长按识别二维码查看原文**

https://github.com/jsdom/jsdom

**zx v7.0.2** – 使用 Node 编写 shell 脚本。

**长按识别二维码查看原文**

https://github.com/google/zx

**Sequelize v6.21** – 基于 Promise 实现的 Node.js ORM 工具，适用于 Postgres、MySQL、MariaDB、SQLite、DB2、Microsoft SQL Server、Snowflake 和 IBM i。

**长按识别二维码查看原文**

https://github.com/sequelize/sequelize

**Opossum v6.4** – 异步函数的断路器模式以及回退方案。

**长按识别二维码查看原文**

https://github.com/nodeshift/opossum

**pg-boss v7.4** – 基于 Postgres 和 Node 实现任务队列系统。

**长按识别二维码查看原文**

https://github.com/timgit/pg-boss

## 🛠 代码与工具

**js-fire v1.0：通过 JS 对象生成 CLI** — Google 发布的 **Python Fire** 可以通过 **Python** 对象创建 CLI，而 js-fire 是一个基于 JS 的实现方案。

**长按识别二维码查看原文**

https://github.com/hobochild/js-fire

Craig Mulligan

**Tinypool：更小的 Node 工作池工具** — fork 自 **Piscina** ，致力于实现更少的依赖、更小的体积。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinypool

Tinylibs

**Moon：为 JS 生态提供新的构建方案** — Moon 为了提高性能选择了使用 Rust，并专注为拥有大量依赖、众多开发者参与、复杂流程的大型项目提供功能。或许这个项目未来的发展会很有趣。

**长按识别二维码查看原文**

https://moonrepo.dev/

Miles Johnson

**node-website-scraper：下载网站到本地硬盘** — 基于 Node 实现类似 `wget \--mirror` 的功能，可以自由配置，高度定制。

**长按识别二维码查看原文**

https://github.com/website-scraper/node-website-scraper

Sophia Antipenko

**public-ipv v6.0：快速获取你的公开 IP 地址** — 适用于 Node 和浏览器环境。当前版本允许你选择 IPv4 或 IPv6 协议。

**长按识别二维码查看原文**

https://github.com/sindresorhus/public-ip

Sindre Sorhus

**grammY：最新的 Telegram Bot 框架** — grammY 能够帮助你简单地创建 Telegram Bot。

**长按识别二维码查看原文**

https://grammy.dev/

KnorpelSenf

**Middy v3.1：为 AWS Lambda 提供 Node 中间件引擎** — Middy 是流行的 AWS Lambda 中间件引擎。Middy 可以帮助我们对代码进行整理和去重，从而让我们更加专注于业务逻辑！

**长按识别二维码查看原文**

https://middy.js.org/

Luciano Mammino

**PSD v0.2：零依赖的 Photoshop PSD 文件解析工具，支持 Node 和浏览器**

**长按识别二维码查看原文**

https://webtoon.github.io/psd/

webtoon

## 🙋🏻‍♀️