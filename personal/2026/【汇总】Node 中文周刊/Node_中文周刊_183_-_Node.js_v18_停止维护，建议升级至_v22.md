# Node 中文周刊 #183 - Node.js v18 停止维护，建议升级至 v22

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542028&idx=1&sn=3f78e603622bdd9fd10e2f8904379b37&chksm=e9216eeede56e7f8c56ca8f0e42c95db286808b017da70495f071bccc0b0e5e4efc24f69bb23#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542028&idx=1&sn=3f78e603622bdd9fd10e2f8904379b37&chksm=e9216eeede56e7f8c56ca8f0e42c95db286808b017da70495f071bccc0b0e5e4efc24f69bb23#rd): 2026/2/2 23:51:32

---

> 本期看点：Node.js v18 及更早版本已进入 End-of-Life 阶段建议直接升级到 v22，Node v24.2.0 发布新增 import.meta.main 布尔值支持，Jest 30 正式发布带来重要改进，Orange ORM 发布支持 Node、Bun 和 Deno 的优雅 ORM 解决方案，介绍如何用模块钩子在 Node 中实现原生热模块重载。

> 编辑：TimLi

🔥 本周热门

**重要提醒：警惕 Node.js 已停止维护的版本** —— Matteo Collina 指出，Node.js 生态正处于一个“关键时刻”，v18 及更早版本已经进入 End-of-Life 阶段。他详细解释了这对还在用老版本的用户意味着什么，并建议大家直接跳过 Active LTS v20，直接升级到 v22，这样更有利于未来的兼容和安全。如果你实在离不开老版本，Matteo 也给出了一些可行的建议。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/node-18-eol-support

Matteo Collina

💡 顺带一提，Matteo Collina 还在 bsky 上发帖 讨论了 TypeScript 支持是否应该回移植到 Node.js 22 的问题，感兴趣可以去看看。

**长按识别二维码查看原文**

https://bsky.app/profile/nodeland.dev/post/3lr6qoy5s3p2t

**Node v24.2.0（当前版）发布** —— ES 模块现在新增了一个布尔值 `import.meta.main`，可以判断当前模块是否是进程的入口（比如你只想在直接运行模块时执行某些代码）。另外，nghttp2 已经移除了对 HTTP/2 优先级信号的支持。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.2.0

Antoine du Hamel

💡 这个变更 还意味着，如果你在用 权限系统，不需要再把应用程序的入口传给 `--allow-fs-read` 了，省事不少。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/58579

**用模块钩子在 Node 实现原生热模块重载** —— 这篇文章介绍了如何巧妙利用模块钩子，在 Node 里高效地实现“热模块”功能，原生又实用。

**长按识别二维码查看原文**

https://immaculata.dev/blog/native-nodejs-hmr.html

Immaculata

**Node 配置和环境变量的正确打开方式** —— 这是一篇总结 Liran Tal 最近分享的博客，讲了在 Node 里处理配置和环境变量的各种坑，以及一些最佳实践，帮你少踩雷。

**长按识别二维码查看原文**

https://blog.platformatic.dev/stop-losing-sleep-over-nodejs-config-heres-how-to-get-it-right

Luca Maraschi

**📄 Node 里搞定 Postgres 数据库迁移** —— 推荐用 `node-pg-migrate` 这个工具。Boas Falke

**长按识别二维码查看原文**

https://blog.bitexpert.de/blog/migrations-with-node-pg-migrate

**📄 用 Node.js 和 gRPC 构建 API** Salem Olorundare

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/building-apis-with-node-js-and-grpc/

**📄 在 Node 里用 Sequelize 操作 SQL** Damilola Olatunji

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/06/11/using-sql-in-nodejs-with-sequelize.html

**快讯：**

- Sarah Gooding 总结了 TC39 最近会议上讨论和推进的提案，包括 `Array.fromAsync`、`Error.isError` 和显式资源管理等内容。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/tc39-advances-9-proposals
    

- 距离上次大版本已经过去好几年了，Jest 30 终于发布，带来一大波重要改进。
    
    **长按识别二维码查看原文**
    
    https://jestjs.io/blog/2025/06/04/jest-30
    

- SQLite-JS 是个有趣的 SQLite 扩展，让你可以用 JavaScript 写自定义 SQLite 函数。
    
    **长按识别二维码查看原文**
    
    https://github.com/sqliteai/sqlite-js
    

🛠 代码与工具

**🍊 Orange ORM：Node 和 TypeScript 的优雅 ORM** —— 这是一个强大的 ORM，支持 Node、Bun 和 Deno，兼容 TypeScript 和 JavaScript，同时支持 CommonJS 和 ESM。它采用 Active Record 风格的查询方式，文档齐全，如果你要和主流 SQL 数据库打交道，非常值得一试。

**长按识别二维码查看原文**

https://orange-orm.io/

Lars-Erik Roald

**Mock Service Worker：REST/GraphQL API Mock 工具库** —— 拦截请求后你可以自定义 mock 响应。它用类似 Express 的路由语法捕获请求，支持参数、通配符和正则。最近还发布了不少新版本。GitHub 仓库。

**长按识别二维码查看原文**

https://mswjs.io/

Artem Zakharchenko

**🌐 tz-lookup：根据经纬度快速推算时区** —— **“这个包牺牲了一些精度来换取速度和体积。”** 不过对于大多数时区推断场景来说，已经够用了。

**长按识别二维码查看原文**

https://github.com/photostructure/tz-lookup

Matthew McEachen

📢 其他 JavaScript 相关

这里还有一些最近 JavaScript 领域的有趣新闻，别错过：

- Rolldown 是一个基于 Rust 的超快 JavaScript 打包器，未来有望成为 Vite 的默认打包工具。Evan You 最近 官宣了 Rolldown-Vite，你现在就可以用这个替代包体验 Rolldown 驱动的 Vite，很多开发者反馈构建速度大幅提升。
    
    **长按识别二维码查看原文**
    
    https://rolldown.rs/
    

- Gleam 是一门易读易写的语言，能同时运行在 Erlang 和 JavaScript 平台。最近的好消息是 Gleam 编译到 JS 后速度提升了 30%，值得关注。
    
    **长按识别二维码查看原文**
    
    https://gleam.run/
    

- 2025 年 CSS 现状调查 已经开放，欢迎参与。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-css/2025
    

**版本发布：**

- **Babel 8 Beta** —— 距离 alpha 版已经两年了，官方表示“Babel 8 计划的所有重大变更都已完成”。

- **Prisma v6.9** —— 新一代 Node.js + TypeScript ORM。Prisma 针对 PostgreSQL 和 SQLite 的 Rust-free 版本已进入预览。

- **OpenAI Node v5.2** —— OpenAI 官方 Node API 库。

- **MongoDB Node.js Driver v6.17** —— MongoDB 官方最新 Node 驱动。

- **node-llama-cpp v3.9** —— 本地运行 LLM，绑定 `llama.cpp`。

- **Firewalk v2.3** —— 高效遍历 Firestore 集合的库。

- **Rewire v8.0** —— Node 单元测试的猴子补丁工具。

- **Jasmine v5.8** —— 浏览器和 Node 的测试框架。

- **node-hid v3.2** —— 访问 USB 和蓝牙 HID 设备。

- **Mocha v11.6** —— Node 和浏览器的测试框架。

- **JsBarcode v3.12** —— 条形码生成库。

- **AVA v6.4** —— 受欢迎的 Node 测试工具。