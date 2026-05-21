# Node 中文周刊 #54 - Node v18.8.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247509936&idx=1&sn=92bbbb95ca87381830048daa9392c89d&chksm=e921ec52de5665449ebdb80381e35aebebb3ca2bbfd4f70395a01745e78b3222be8e2a5047d4\#rd  
> 抓取时间: 2026/2/2 23:54:15

---

> 本期看点：因编写系列文章《Node 最佳实践》而出名的 Yoni 提出了关于 Node 开发模式与工具的 9 种常见的新的选型的思考。

> 编辑：Otto-J、Yucohny

## 🔥 本周热门

**Crawlee：Web 爬虫和自动化工具库** — 看到 Crawlee 这样的一个新项目正式启动，并正大张旗鼓地做着宣传，总是很开心的。Crawlee 发布了一段 ▶️ **三分钟介绍应用场景** 的视频，一篇 **介绍文章** 与一个 **很不错的官网**。Crawlee 基于 **Puppeteer** 与 **Playwright** 等工具构建，实现了代理、重试、爬虫，以及逻辑运行等功能。Crawlee 来自 Apify，且现在已经开源。

**长按识别二维码查看原文**

https://blog.apify.com/announcing-crawlee-the-web-scraping-and-browser-automation-library/

Apify

**是否需要重新选择流行的 Node 开发模式与工具？** — Yoni 因为编写系列文章 **《Node 最佳实践》** 而出名，在这些文章中他认为我们应该时常反思根深蒂固的方法。Yoni 在这篇文章中提出了 9 种常见的新的选型思考，比如使用 Dotenv、Passport.js，基于 `NODE_ENV` 进行逻辑判断等。

**长按识别二维码查看原文**

https://practica.dev/blog/popular-nodejs-pattern-and-tools-to-reconsider/

Yoni Goldberg

**Node v18.8.0（Current）发布** — 本次更新引入了 `--build-snapshot` 和 `--snapshot-blob` 选项来创建和使用用户侧的快照。npm 也升级为 8.18.0，同时引入了 `npm query` **命令**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.8.0/

Ruy Adorno

**Node v16.17.0（LTS）发布** — 本次更新引入了很多实用功能，获得了很多最新版的功能更新。从 Node v16.17.0 发布之后，用户可以使用 `util.parseArgs` 命令函参数解释方法，实验性的 ESM loader hooks，`node:test` 模块和运行器，以及更新依赖项。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v16.17.0/

Michaël Zasso

**使用 AWS Elastic Beanstalk 部署 Node 应用** — **Elastic Beanstalk** 是最早支持应用部署编排的服务。虽然现在有很多方法来部署应用，但它仍旧是 AWS 用户的选择之一。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/node-elastic-beanstalk/

Samson Omojola

**如何使用 OpenTelemetry 追踪 Node.js 应用** — 本文介绍了五个步骤接入 OpenTelemetry，更好地排查追踪应用在生产环境的错误。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2022/08/23/how-use-opentelemetry-trace-nodejs-applications

Patil, Frota, Panchamukhi (Red Hat)

**快讯：**

- Deno 项目宣布 **将会发布“重大更新”**，包括一个目标：“在未来三个月内让绝大多数 npm 包可运行在 Deno 中”。这会让 Node 开发人员有更多可选运行时。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/changes
    

- 🥯 另一个服务端 JS 运行时 **Bun** 正在大张旗鼓地宣传。Bun 的作者创办了 **Oven** 公司，并筹集到 700 万美元的资金。不过道阻且长，仍然 **存在很多问题** 需要处理。社区中有许多人担心项目的长远规划。Jarred 对这个项目的潜力和发展 ▶️ **充满激情**，我们会持续报道。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/
    

## 🛠 代码与工具

**file-type v18.0：在 Buffer, Uint8Array 和 ArrayBuffer 数据中检测文件类型** — file-type 能够实现通过 **魔法数字** 特征在 Buffer, Uint8Array 与 ArrayBuffer 检测文件类型，而不是根据后缀名推断。

**长按识别二维码查看原文**

https://github.com/sindresorhus/file-type

Sindre Sorhus

**Soketi：简洁、快速的 WebSockets 服务端** — 你是否想使用 Serverless WebSockets？Soketi 可以通过 Cloudflare Workers 部署，以快速使用 Serverless WebSockets。Soketi 在全球范围内可用，并且更靠近用户，保持一致的推送协议。值得注意的是，Soketi 需要使用 TypeScript 编写。

**长按识别二维码查看原文**

https://github.com/soketi/soketi

Soketi Team

**brotli-wasm：可靠的 Brotli 压缩和解压工具** — 通过提供 WebAssembly 在浏览器和 Node 环境中运行。

**长按识别二维码查看原文**

https://github.com/httptoolkit/brotli-wasm

HTTP Toolkit

**NodeGui：使用 CSS 和 JS 构建跨平台桌面应用** — 和 Electron 很像？是的，但有些不同，底层使用 Qt GUI 框架，可以开发复杂问题，也在内存使用方面更有效率。

**长按识别二维码查看原文**

https://docs.nodegui.org/

NodeGui

**版本发布：**

- **Wild Wild Path v3.1** – 🤠 使用通配符和正则表达式的对象路径匹配。

- **NATS.js v2.8** – NATS 邮件系统的 Node 客户端。

- **Slonik v30.3** – PostgreSQL 客户端，提供运行时和构建时候的安全类型检查。

- **mojo.js v1.4** – 受 Perl 启发的实时 web 框架。

- **Undici v5.10** – HTTP/1.1 客户端。

- **cacheable-request v9.0** – 原生 HTTP 请求包装，符合 RFC 缓存。现在是纯 ESM 模块。

- **Fastify v4.5.2‍**

- **npm v8.18.0**

## 🙋🏻‍♀️