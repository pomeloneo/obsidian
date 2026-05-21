# Node 中文周刊 #2 - Node v16.8.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491532&idx=1&sn=caa9b0e1ff67eaec0bbe3b5688850a1b&chksm=e922542ede55dd387b4ead3470fa916c01a8813f1868474216bf2746f2c8fced87e8596c2705\#rd  
> 抓取时间: 2026/2/2 23:55:19

---

> 本期编辑：GXG、Xleine 本周看点：Node v16.8.0 发布，该版本引入了 `stream.Duplex.from`，`stream` 的 `isDisturbed` 帮助函数，同时将 `toUSVString` 函数暴露给了开发者。另外，npm registry 将弃用 TLS 1.0 和 TLS 1.1，还有环境在使用 TLS 1.0 和 1.1 的小伙伴要抓紧时间更新了哦~

## 🔥 本周热门

**Mongoose v6 简介** — 如果你是 MongoDB 的用户，那么本文不容错过。如果你已是 Mongoose 的老用户，你应参考 5.x 到 6.x 迁移指南。细细想来，Mongoose v5 发布距今已经过去三年多了，所以也是时候该更新了，v6 官方做出了很多努力。:-)

**长按识别二维码查看原文**

https://thecodebarbarian.com/introducing-mongoose-6.html

Valeri Karpov

**Node v16.8.0 发布** — 正常的版本迭代。引入了 `stream.Duplex.from`、`stream` 的 `isDisturbed` 帮助函数，同时 `toUSVString` 已经暴露给开发者使用（“USV String” 是 unicode 标量值所有可能序列的集合）。一周前，Node 16.7.0 添加了一个实验性的递归 `cp` 方法的具体实现。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v16.8.0/

Michaël Zasso

**zx 3：用于编写更好的 Shell 脚本的工具** — 与 `bash` 之类来编写快速执行脚本的方式不同，`zx` 提供了各种工具可以帮助你用熟悉的 JavaScript 代码来做同样的事情。随着 3.0 和 3.1 在几天内相继的发布，很多工作都在完善当中。如果你对此感兴趣，可以参阅 此 Demo。

**长按识别二维码查看原文**

https://github.com/google/zx

Google

**npm registry 正在弃用 TLS 1.0 和 TLS 1.1** — 从 10 月开始，所有与 npm 网站和 registry 本身的连接都必须使用 TLS 1.2 或更高版本。影响范围并不大，因为目前 99% 的流量已经满足这个要求，但是如果你正在运行一些古老的 Node 二进制文件或在使用奇奇怪怪的设备，你需要在文中介绍的测试运行期间之前检查它们并修复它们。

**长按识别二维码查看原文**

https://github.blog/2021-08-23-npm-registry-deprecating-tls-1-0-tls-1-1/

GitHub

**jq 简介** — jq 是一个快速的、由 C 驱动的命令行实用程序，用于对 JSON 数据进行解析、排序、过滤、执行等任何操作。本文是用来快速记住 jq 语法的不二之选。

**长按识别二维码查看原文**

https://earthly.dev/blog/jq-select/

Adam Gordon Bell

**从 NAN 向 Node-API 迁移：一个小故事** — Node 原生插件的创建者介绍了从 NAN 向 Node-API（以前的 N-API）的转变 —— 本文针对原生插件创建者而写，内容会稍微深入一些。

**长按识别二维码查看原文**

https://nodesource.com/blog/NAN-to-Node-API-migration-a-short-story

Santiago Gimeno

**快讯：**

- **ls-lint** — 一款用 Node 编写的文件及目录名的 linter 工具，目前 npm 下载量已经超过 500k。
    
    **长按识别二维码查看原文**
    
    https://ls-lint.org/
    

## 🛠 代码和工具

**libOBS（OBS Studio）可用于 Node.js 和 Electron** - OBS Studio 是一个非常流行的视频录制，流媒体和合成系统，经常被主播使用。使用此库可以轻松在 Node 上实现直播功能。而 obs-websocket-js 是现有的另一种较为流行的方案。

**长按识别二维码查看原文**

https://github.com/stream-labs/obs-studio-node

stream-labs

**LevelGraph v3.0：适用于 Node 和浏览器的 JavaScript 图形数据库** — 基于 LevelDB 实现，以提高性能，它可以在 Node 应用或任何支持 IndexedDB 的浏览器中使用。

**长按识别二维码查看原文**

https://github.com/levelgraph/levelgraph

Matteo Collina 及 LevelGraph 相关贡献者

**undici v4.5：适用于 Node 的现代 HTTP/1.1 客户端** — 我们已经写过几篇关于 Undici 的文章，它似乎真的正在成为适用于 Node 的最佳现代 HTTP 客户端。最新的 v4.5.0 为 `fetch` 添加了 TS 类型。

**长按识别二维码查看原文**

https://github.com/nodejs/undici

Matteo Collina 及 Undici 贡献者

**http-server：一个简单的零配置命令行 HTTP 服务器** — 比其他简单的命令行 HTTP 服务器更加定制化（前提是有需求）。

**长按识别二维码查看原文**

https://github.com/http-party/http-server

Robbins，Squires 等。

**pg-boss v6.2.0: Postgres + Node 任务队列系统** — 用于后台处理和可靠异步执行的任务队列。它使用 Postgres 的相关特性来保证安全。

**长按识别二维码查看原文**

https://github.com/timgit/pg-boss

Tim Jones

**Tedious v12.0：用于连接 SQL Server 数据库的 TDS 模块** — 如果你想使用 TDS（表格数据流），可以使用此库。TDS 是专门用于与微软的 SQL Server（从 2000 年到 2017 年）交互的协议。

**长按识别二维码查看原文**

https://github.com/tediousjs/tedious

Mike D Pilsbury

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。