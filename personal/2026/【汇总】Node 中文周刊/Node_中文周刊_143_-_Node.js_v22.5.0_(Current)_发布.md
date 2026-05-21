# Node 中文周刊 #143 - Node.js v22.5.0 (Current) 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533629&idx=1&sn=9955d063d69c55aa531e14f0248f2d9e&chksm=e9210fdfde5686c9f4d9eacb7b72270d8d7a5202a69ec06fe50374994627040e3340abdcb98c\#rd  
> 抓取时间: 2026/2/2 23:52:20

---

> 本期看点：description: Node.js v22.5.0 已经发布，但不要安装它！这是一个值得注意的发布，原因有三：首先，node:http 中的 WebSocket 功能现在已经公开。其次，还记得 Node 如何嵌入 SQLite 吗？node:sqlite 现在已包含并可以使用。然而第三点，v22.5.0 引入了一个严重的 bug，所以你应该尝试 v22.5.1。

> 编辑：TimLi

🔥 本周热门

**Node.js v22.5.0（Current）发布** —— 但不要安装它！—— 这是一个值得注意的发布，原因有三：首先，`node:http` 中的 WebSocket 功能现在已经公开。其次，还记得 Node 如何嵌入 SQLite 吗？`node:sqlite` 现在已包含并可以使用。然而第三点，v22.5.0 引入了一个严重的 bug，所以你应该尝试 v22.5.1 。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.5.0

Antoine du Hamel

**Node v22.5.0 崩溃的事后分析** —— “Current”发布线为我们提供了 Node 的最新功能，但也冒着有时包含严重 bug 的风险，v22.5.0 就是这样的情况。Node v22.5.1 发布以修复这个错误。Matthew McEachen 进一步写下了他遇到这个 bug 的经历。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/53934

Yagiz Nizipli 等人

**为什么在 Node 中生成新进程如此缓慢？** —— Val Town 平台的开发者注意到 Node 每秒无法生成超过 40 个外部进程，而 Deno 和 Bun 可以做得更多。有办法显著改善这一点吗？实际上，是有的！

**长按识别二维码查看原文**

https://blog.val.town/blog/node-spawn-performance/

Max McDonnell

**不阻塞事件循环的实用指南** —— 探讨了单线程环境中同步和异步工作的核心原则，强调了非阻塞代码对高效事件循环利用的重要性。

**长按识别二维码查看原文**

https://www.bbss.dev/posts/eventloop/

Slava Knyazev

**在 Heroku 上使用 pnpm** —— 如果你使用 Heroku 平台，他们的 Node.js buildpack 现在支持 pnpm 包管理器，它提供了显著的磁盘空间和安装时间改进。

**长按识别二维码查看原文**

https://blog.heroku.com/using-pnpm-on-heroku

Colin Casey (Heroku)

🛠 代码与工具

**MikroORM v6.3：模式优先？** —— 如果你还没有尝试过 MikroORM（一个用于 Node 的 TypeScript ORM），那么它非常值得一试。v6.3 带来了更多改进，并引入了使用“模式优先”风格的选项，可以从数据库创建实体定义。

**长按识别二维码查看原文**

https://mikro-orm.io/blog/mikro-orm-6-3-released

Martin Adamek

**Docmost：开源协作 Wiki 和文档工具** —— 如果你想要类似 Notion 但开源且由 Node 驱动的东西（它的底层是一个 NestJS 应用程序），这个工具有很多可以提供的。

**长按识别二维码查看原文**

https://docmost.com/

Docmost Team

**📊 Chartbrew v3.7：从多个源创建实时报告仪表板** —— 开源，由 Node 构建，让你可以连接到多个数据源并汇总数据转化为图表和仪表板。

**长按识别二维码查看原文**

https://github.com/chartbrew/chartbrew

Chartbrew

**fdir v6.2：高性能目录爬虫库** —— 需要快速异步或同步扫描目录吗？

**长按识别二维码查看原文**

https://github.com/thecodrr/fdir

Abdullah Atta

**版本发布：**

- 🤖 **OpenAI Node v4.53.0** —— OpenAI API 的官方 Node 库增加了对他们最新的 `gpt-4o-mini` 模型的支持。

- **smol-toml v1.3** —— 小巧、快速的 TOML 解析器和序列化器。现在同时提供 ES 模块（ESM）版本和 CommonJS（CJS）单文件版本，以支持更多使用场景。

- **exiftool-vendored v28.0** —— 跨平台访问 ExifTool 以管理多媒体文件的元数据。

- **Poolifier v4.1** —— 使用 `worker_threads` 和 `cluster` 的工作池。

- **pnpm v9.6** —— 快速、节省空间的包管理器。

- **file-type v19.3** —— 检测缓冲区的文件类型。

- **np v10.0.7** —— 更好的 `npm publish`。

🙋🏻‍♀️