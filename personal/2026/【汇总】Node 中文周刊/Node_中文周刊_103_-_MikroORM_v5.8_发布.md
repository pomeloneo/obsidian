# Node 中文周刊 #103 - MikroORM v5.8 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523779&idx=1&sn=81578b12e6888bd8a3521ff43df93311&chksm=e921d621de565f37ce4e5259b077dd803a3ea7aefb87968ae95b21ca986675d78941c7946e4f\#rd  
> 抓取时间: 2026/2/2 23:53:08

---

> 本期看点：每当提到 MikroORM 时，人们总是说它非常出色，值得更多关注。MikroORM 是一个基于 Data Mapper、Unit of Work 以及 Identity Map 模式的 Node ORM，支持 SQL 和 NoSQL 数据库，并且能够分析代码以帮助更轻松地创建实体。

> Yucohny、loveloki

## 🔥 本周热门

**MikroORM v5.8 发布** —— 每当提到 **MikroORM** 时，我总是看到人们说它非常出色，值得更多关注，所以我正在尽我的一份力帮助它。它是一个基于 Data Mapper、**Unit of Work**（支持隐式事务和更改检测！）以及 **Identity Map** 模式的 Node ORM，支持 SQL 和 NoSQL 数据库，并且能够分析代码以帮助更轻松地创建实体。

**长按识别二维码查看原文**

https://mikro-orm.io/blog/mikro-orm-5-8-released

Martin Adámek

**Bun v1.0：JavaScript/TypeScript 运行时替代方案** —— 我们将在 **JavaScript Weekly** 中更多地关注 Bun，但是这个基于 **JavaScriptCore** 构建的性能优先的服务端 JavaScript 运行时在 Node 世界中仍然很重要，因为它是唯一一个声称作为 **“Node.js 的即插即用替代品”** 的存在。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.0

Jarred Sumner et al.

来自 Snyk 的 James Konik 尝试进行对 **Node、Deno 与 Bun 进行比较**。Hexagon 还创建了一个简单的 **功能比较表✅** ❌。

**长按识别二维码查看原文**

https://snyk.io/blog/javascript-runtime-compare-node-deno-bun/

**使用 `npx` 运行 GitHub Gist** —— Nate Taras 最近 **创建** `**npx**` **工具** 一文启发 Kelly 实现了这个简单的远程执行 `npx` **gist** 的示例。这是一个聪明的想法，因为 GitHub gist 可以自动充当 git 仓库，并且 `npx` 可以运行针对托管在 git 仓库中的包。

**长按识别二维码查看原文**

https://gist.github.com/kfox/1280c2f0ee8324067dba15300e0f2fd3

Kelly Fox

**Node v20.6.1（Current）发布** —— 一个补丁级别的发布，旨在修复一个关于 **在被 ESM 加载时的循环 CJS 依赖问题**。这个问题足够重要，以至于 **影响了众多热门项目**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.6.1

Ruy Adorno 与 Rafael Gonzag

**每天收到父母安好的通知** —— 在英国这个真正热爱茶的国家，有人通过监测每天是否使用水壶来关心家人。Node 用于通过 Telegram 发送消息通知。

**长按识别二维码查看原文**

https://remysharp.com/2023/09/11/getting-daily-notifications-my-parent-is-okay

Remy Sharp

**使用 JavaScript 操作 JPEG 和 EXIF 数据** —— 这篇文章介绍了在不依赖第三方库的情况下浏览 JPEG 格式并且直接读取和替换 EXIF 标签的方法。

**长按识别二维码查看原文**

https://getaround.tech/exif-data-manipulation-javascript/

Cédric Patchane

**Node 作业调度器：Bull 还是 Agenda？** —— 这不是一个对抗性的标题，**Bull** 和 **Agenda** 都是 Node 的作业调度系统 😉 ……不过我会选择 Bull，快来看看 **新的 BullMQ**。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/09/06/job-schedulers-for-node-bull-or-agenda.html

Omonigho Kenneth Jimmy

**在 AWS Lambda 上运行 Playwright 脚本** —— 如果你也曾苦苦挣扎地让它工作，可以看看 Matt 提供的建议。

**长按识别二维码查看原文**

https://steele.blue/playwright-on-lambda/

Matt Steele

**使用 eBPF 观察 Node.js 进程**

**长按识别二维码查看原文**

https://opeonikute.dev/posts/observing-node-with-ebpf

Opeyemi Onikute

**快讯：**

- Node 16 现在已经达到生命周期终点（EOL），这意味着它将不再接收更新。造成此结果的主要原因是 OpenSSL。你可以在 **这里了解更多关于 Node 发布计划**的信息。

**长按识别二维码查看原文**

https://github.com/nodejs/Release

- 来自 **Node 性能团队** 的 Yagiz Nizipli 邀请感兴趣帮助 Node 提升性能的人参加他们的一个 Zoom 会议。他还指出，🐦 **团队中没有人因其工作而获得报酬**，以回应本周 Twitter/X 上的批评和相反的说法。

**长按识别二维码查看原文**

https://github.com/nodejs/performance

- Yagiz 还创建了 **关于从 Node 中移除** primordials** 的讨论**。作为一个仅供内部使用的功能，**primordials** 为核心模块提供了一种访问 Node 中真正干净、不被其他模块或第三方代码污染的底层对象的方式。

**长按识别二维码查看原文**

https://github.com/nodejs/TSC/issues/1438

## 🛠 代码与工具

**Semgrep v1.39：多语言轻量级静态分析工具** —— Semgrep 是一个用于本地分析代码的命令行工具，具有大量预设规则（可在 **用于探索的仓库** 中寻找），并提供一个测试工具。想象一下，它是一个加速的、具备语言识别功能的 `grep`，你已经完成了一半的工作 😁（它并非由 Node 构建，但 Node 是其支持和常见目标之一）。

**长按识别二维码查看原文**

https://github.com/returntocorp/semgrep

R2C

**csv42：小巧、快速的 CSV 解析器，支持嵌套 JSON** —— 作者还发表了一篇关于 **为何构建它的博客文章**。

**长按识别二维码查看原文**

https://github.com/josdejong/csv42/

Jos de Jong

**Disco Node：使用协同过滤进行推荐的 Node 库** —— pgvector 最活跃的贡献者推出的新 Node 库。

**长按识别二维码查看原文**

https://github.com/ankane/disco-node

Andrew Kane

**quick-lru v7.0：简单的 LRU 缓存** —— 用于需要缓存，但还要限制底层对象大小的情况。

**长按识别二维码查看原文**

https://github.com/sindresorhus/quick-lru

Sindre Sorhus

**Zettlr v3.0：现代化 Markdown 编辑器** —— 一个相当吸引人的编辑器。由于其使用的是 GPL 许可证，因此你可以在任何地方集成它。这里是 **GitHub 仓库** 和 **主页**。

**长按识别二维码查看原文**

https://zettlr.com/post/zettlr-300-released

Zettlr

**版本发布：**

- **Foal v4.0**
    
    ↳ 基于 TypeScript 的 Node.js 框架，这是 注意事项。
    

- **node-mssql v10.0**
    
    ↳ Node Microsoft SQL Server 客户端。
    

- **sqs-consumer v7.3**
    
    ↳ 无需样板代码使用 SQS 。
    

- **easy-soap-request v5.4**
    
    ↳ 使 SOAP 请求更加简单的库。
    

- **Mongoose v7.5.1**
    
    ↳ MongoDB 对象建模库。
    

- **ncc v0.38**
    
    ↳ 将 Node 模块编译为单个文件。
    

- **openai-node v4.6**

- **Fastify v4.23**

- **Electron v26.2**

## 🙋🏻‍♀️