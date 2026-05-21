# Node 中文周刊 #62 - Node.js v19 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511517&idx=1&sn=10520b11b2f5fbf2420522f02487a6ed&chksm=e921e63fde566f2918d0d3506ab34f067db8065316a387354f56cfa07be40936691542d32cc7\#rd  
> 抓取时间: 2026/2/2 23:54:05

---

> 本期看点：Node.js v19 发布，这个版本包含的新功能有增加监听模式、默认启用 HTTP KeepAlive、V8 引擎升级至 v10.7 等等，快来一览究竟吧！

> 编辑：Otto-J、Yucohny

## 🔥 本周热门

**Node.js v19 发布**

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/v19-release-announce/

Node v19 版本数字是奇数，因此当前版本不会作为 LTS 发布，而是在 2023 年年初之前，将作为 current 发布，并拥有所有最新的功能特性。同时，Node v19 将在 2023 年 6 月 1 日迎来 “end of life”。来自核心团队的 Rafael Gonzaga 提出：“如果你有兴趣立刻体验新功能，Node v19 已经准备好了。”

Node v19 的新功能包含：

- **监听模式**：添加了实验性的 `-watch` 标识，与 Nodemon 功能一样，该模式会监听忽略文件之外的文件变动，然后重启服务进程。另外，Node v18.11.0 (LTS) 也包含了当前功能。

- **HTTP KeepAlive 现在默认启用**：之前一直作为选项功能开启，现在设置为默认生效了。要注意的是，默认的持续时间是 5 秒钟。

- **V8 v10.7**：Node V8 引擎升级到了最新版。虽然不是一个大的发行版本，但是引入了 `Intl.NumberFormat`。

- WebCrypto API 现在是稳定版本，但 Ed25519，Ed448，X25519 和 X448 除外。

- 包括 npm v8.19.2 与 llhttp v8.1.0 在内的其他一些依赖项升级。

从当前情况来看，我们会把 Node v18.x 和 v19.x 都视为 Current 版本，但 Node v18 会在 10 月 25 日开始作为 LTS 版本。更多信息请参考 **发布信息** 与来自 OpenJS Foundation **发布的信息中的其他细节**。

**长按识别二维码查看原文**

https://github.com/nodejs/release

The Node.js Team

**选择最合适的 Docker Node.js 镜像** — 如果你一直把 `FROM node` 作为 Dockerfile 的依赖项，请三思：还有其他的选择。

**长按识别二维码查看原文**

https://snyk.io/blog/choosing-the-best-node-js-docker-image/

Liran Tal (Snyk)

▶ **使用 Phero 轻松保证端到端类型安全** — **该工具库** 提供了一个示例，演示了一种基于 TypeScript 类型安全的方式在前端和后端之间进行通信。**GitHub 仓库**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=BS8nRuszlqo

Jasper Haggenburg

**PowerShell、NPM Scripts 和静默删除的参数** — 如果你使用 Powershell 你可能会发现一些参数没有通过 `npm run` 来正确传递，Lloyd 解释了背后的原因。

**长按识别二维码查看原文**

https://www.lloydatkinson.net/posts/2022/powershell-npm-scripts-and-silently-dropped-arguments/

Lloyd Atkinson

▶ **Next.js 速成课程** — 已经有了很多类似的视频，但这是一个基于最新版本的最新视频，相信可以帮助你学会 Next.js。时长大概 2 小时 30 分钟。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=uU80SSxn9_c

Anson Foong

**使用 Puppeteer 爬取 Google Maps** — 如果你有官方的 API 的话不需要使用，但看看背后实现的原理还是很有趣的。

**长按识别二维码查看原文**

https://serpdog.io/blog/web-scraping-google-maps

Darshan Khandelwal

**不使用 DNS Lookup 发送 UDP 信息**。

**长按识别二维码查看原文**

https://hermanradtke.com/sending-udp-messages-in-nodejs-without-dns-lookups/

Herman J. Radtke III

**Wix：使用 Node 应用的进程来降低 K8S 的 Pod 成本**。

**长按识别二维码查看原文**

https://thenewstack.io/wix-multithreaded-node-js-to-cut-kubernetes-pod-costs/

Jessica Wachtel (The New Stack)

**快讯：**

- **Node v18.11.0 (Current)** 上周发布了。当前版本共享了 Node v19 的 `-watch` 新功能，Node v18 在下周会成为新的 LTS 版本。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v18.11.0/
    

- OpenJS Foundation 告诉我们 **有两个 Node.js 课程和证书会有大的折扣**，10 月 25 日截止。
    
    **长按识别二维码查看原文**
    
    https://training.linuxfoundation.org/oct-2022-jspromo/
    

## 🛠 代码与工具

**Javet v2.0.0：在 Java 应用中启用 Node 和 V8** — 它可以在 JVM 环境中启用 V8 和完整的 Node.js 运行时。这里有 **PPT** 演示了这个想法并解释了工作原理。Javet 的名字来自 Java，V 和 Eight。

**长按识别二维码查看原文**

https://www.caoccao.com/Javet/

Sam Cao

**Editly v0.14.0：声明式命令行的视频剪辑工具** — 把 Node 和 FFmpeg 结合到一起，可以更程序化地剪辑视频，而不用和复杂的 `FFmpeg` 命令行选项打交道。

**长按识别二维码查看原文**

https://github.com/mifi/editly

Mikael Finstad

**lady-gg：简单的 TS gRPC 客户端**。

**长按识别二维码查看原文**

https://github.com/stepci/cool-grpc

Mish Ushakov

- **Awilix v8.0**
    
    ↳ Node 的控制反转 IoC 容器。
    

- **Nx v15.0**
    
    ↳ 智能、快速、可拓展的构建系统。
    

- **Nightwatch v2.4**
    
    ↳ E2E 测试框架，现在改进了组件测试的支持。
    

- **lowdb v4.0**
    
    ↳ 简单的 本地 JSON 数据库。
    

- **Prisma v4.5**
    
    ↳ 下一代 ORM， 有很多功能更新。
    

- **PSD v0.3**
    
    ↳ 零依赖的 PSD/Photoshop 文件解析。
    

- **fdir v5.3**
    
    ↳ 性能有限的目录爬虫，支持 glob 功能。
    

- **google-translate v2.0**
    
    ↳ 使用 Google 的 Translate API。
    

- **Mercurius v11.1**
    
    ↳ 使用 Fastify 实现 GraphQL 服务。
    

- **Mongoist v2.5.6**
    
    ↳ MongoDB 驱动，基于 `async`/`await` 实现。
    

- **Mojo.js v1.7**
    
    ↳ 受到 Perl 的 Mojolicious 启发的 Web 框架。
    

## 🙋🏻‍♀️