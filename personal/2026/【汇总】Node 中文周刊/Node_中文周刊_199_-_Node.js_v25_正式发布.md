# Node 中文周刊 #199 - Node.js v25 正式发布

> 原文链接: [](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544213&idx=1&sn=d2e1338592bd73219285b507cddeebde&chksm=e9216677de56ef61105b17e11923ace296622f61a026ec47dcaf50c6ff6afb54b4b1aeb57214#rd)[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544213&idx=1&sn=d2e1338592bd73219285b507cddeebde&chksm=e9216677de56ef61105b17e11923ace296622f61a026ec47dcaf50c6ff6afb54b4b1aeb57214#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544213&idx=1&sn=d2e1338592bd73219285b507cddeebde&chksm=e9216677de56ef61105b17e11923ace296622f61a026ec47dcaf50c6ff6afb54b4b1aeb57214#rd): 2026/2/2 23:51:13

---

> 本期看点：Node.js v25 正式发布，内置启用 Web Storage 和 JSON.stringify 性能大提升，Ace CLI 框架构建书签应用程序教程，Node.js 回压机制与 DTrace 探索实践，Wretch v3.0 让 fetch 更丝滑的链式封装库发布。

> 编辑：TimLi

🔥 本周热门

**Node.js v25.0.0（Current）正式发布** —— 最新的 Node.js 前沿版本来了！这次内置启用了 Web Storage，`JSON.stringify` 性能大提升，权限控制模型里新增了 `--allow-net` 选项，还内建了 `Uint8Array` 的 base64/hex 转换，以及 WebAssembly 和 JIT 优化。上图也说明了 Node 24 很快会升级为 LTS“活跃”版本，而 Node 22 将进入维护期。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.0.0

Rafael Gonzaga

💡 Node v22.21.0（LTS） 也顺便发布了，带来了 `--use-env-proxy` 和 `NODE_USE_ENV_PROXY` 的 HTTP 代理支持。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.21.0

**用 Ace 构建 CLI —— 基于 Node（及 Bun）的书签应用程序** —— Ace是 AdonisJS 团队打造的 CLI 应用程序开发框架，也许你以前没怎么关注过。

**长按识别二维码查看原文**

https://blog.galaxycloud.app/building-clis-with-ace-a-bookmarks-app-in-node-js-and-bun/

Harminder Virk

**Node.js 回压实战引发的 DTrace 探索** —— 回压机制能帮流控制好数据生产和消费的速度。Tyler 用 DTrace 去监测：禁用回压后，Node.js 里的 GC（垃圾回收）激增，系统负载激烈波动，挺长知识的。

**长按识别二维码查看原文**

https://tylerhillery.com/blog/tyler-tries-dtrace/

Tyler Hillery

📄 **Node 测试运行器自带的代码覆盖率支持** —— 这个功能文档很实用，不少人没怎么注意过。Aviv Keller

**长按识别二维码查看原文**

https://nodejs.org/en/learn/test-runner/collecting-code-coverage

📄 **为什么** `**typeof null === object**` —— 深挖 JS 历史的老梗，这篇展开得比你想象的还细。Piotr Zarycki

**长按识别二维码查看原文**

https://pzarycki.com/en/posts/js-null/

快讯：

- ▶️ Nordic.js 2025 的大会演讲 YouTube 已上线，包括 Joyee Cheung 关于 ▶️ 2025 年 Node.js 包发布 的分享，还有 Marco Ippolito 的 ▶️ Node 23 的 `node.config.json` 文件讲解。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/@nordicjs/videos
    

- 视频还没出，不过 Node.js TSC 成员 Ruy Adorno 前不久在 JSConf 带来了 Node.js 的新特性和未来 的主题，PPT 已经公开，内容很全。
    
    **长按识别二维码查看原文**
    
    https://events.linuxfoundation.org/jsconf-north-america/
    

- Vercel 现已原生支持 NestJS 应用程序零配置上线。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/zero-configuration-support-for-nestjs
    

🛠 代码与工具

**Wretch v3.0：让** `**fetch**` **更丝滑的链式封装库** —— 这个自带元老气质的库让 `fetch` 更好用，API 支持链式扩展。可以看看上手示例。3.0 新版不用再装 polyfill，错误处理更优雅，重试策略更智能，还加了上传进度监控等贴心功能。

**长按识别二维码查看原文**

https://github.com/elbywan/wretch

Julien Elbaz

**Graffle v7.3：简洁、跨平台的 GraphQL 客户端** —— 之前叫 `graphql-request`，升级到 v7.3 后补上了 CommonJS 支持，兼容 Jest 和非 ESM 系统，用起来更灵活。

**长按识别二维码查看原文**

https://graffle.js.org/

Jason Kuhrt

**DOMPurify v3.3：高效的 HTML XSS 清洗工具** —— 支持 Node 和现代浏览器，稳定可靠，测试很给力。

**长按识别二维码查看原文**

https://github.com/cure53/DOMPurify

Cure53

**ImapFlow：现代易用的 IMAP 邮件客户端库** —— IMAP 是用于邮件客户端与远程邮件服务器交互的标准协议，ImapFlow 让相关操作变得更简单。

**长按识别二维码查看原文**

https://imapflow.com/

Postal Systems OÜ

**ATSippy：支持重连和压缩的 Bluesky Jetstream 客户端** —— Jetstream 可以抓取 Bluesky 大量事件流，ATSippy 帮你自动断线重连还带事件压缩。

**长按识别二维码查看原文**

https://github.com/lukeacl/atsippy

Luke Cashion-Lozell

📢 其他生态

带你看看最近 JS 圈子里的一些有意思的新鲜事：

- Dan Abramov 分享了 他调 bug 的心得，号称“通杀一切 bug 策略”，核心思路其实就是——不断简化例子，不断归纳，把复杂问题肢解清楚。
    
    **长按识别二维码查看原文**
    
    https://overreacted.io/how-to-fix-any-bug/
    

- Cloudflare Sandboxes 推出新服务，让不可靠的 JavaScript（还有 Python）代码可以在沙盒环境下安全运行，别怕代码“放飞自我”。
    
    **长按识别二维码查看原文**
    
    https://sandbox.cloudflare.com/
    

- PostgreSQL 18 刚发版，新增了异步 IO 子系统，某些场景性能直接跃升，PlanetScale 家还做了 Postgres 17 和 18 的性能对比实测。
    
    **长按识别二维码查看原文**
    
    https://www.postgresql.org/about/news/postgresql-18-released-3142/
    

- NYT（纽约时报）解谜爱好者必看，Andrew Healey 用 TypeScript 演示了 怎么解 NYT 的 Pips 谜题。
    
    **长按识别二维码查看原文**
    
    https://healeycodes.com/solving-nyt-pips-puzzle
    

**版本发布：**

- **Faker v10.1** —— 随心造假数据贼方便，开发填充数据场景必备。

- 🤖 **Repomix v1.8** —— 把整个代码仓库打包成单文件，LLM 喂数据超级顺畅，支持 **Claude Code** 官方插件。

- **node-oracledb v6.10** —— Oracle 数据库的 Node 驱动，现在在 Thin 模式也支持高级队列（AQ）了。

- **node-rdkafka v3.6** —— Kafka 官方 C/C++ 库的 Node.js 封装。

- 🤖 **OpenAI Node v6.6** —— OpenAI API 的官方 Node 库。

- **zx v8.8.5** —— 谷歌出品，提升 Node Shell 脚本体验的利器。

- **terminal-image v4.1** —— 终端直接展示图片工具。

- **Got v14.6** —— 让你写 HTTP 请求像聊天一样舒服。

- **Pino v10.1** —— Node 下超快的 JSON 日志库。

- **ESLint v9.38.0**