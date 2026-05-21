# Node 中文周刊 #193 - Calm 团队迁移 Rush.js 到 Node 原生 TypeScript，性能提升 40%

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543320&idx=1&sn=96874895f75f091e4031483163dd7763&chksm=e92161fade56e8ec7fa0db2b148231c547b47523d1a9c324cd040afab8ff8101916e4430475f#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543320&idx=1&sn=96874895f75f091e4031483163dd7763&chksm=e92161fade56e8ec7fa0db2b148231c547b47523d1a9c324cd040afab8ff8101916e4430475f#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543320&idx=1&sn=96874895f75f091e4031483163dd7763&chksm=e92161fade56e8ec7fa0db2b148231c547b47523d1a9c324cd040afab8ff8101916e4430475f#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543320&idx=1&sn=96874895f75f091e4031483163dd7763&chksm=e92161fade56e8ec7fa0db2b148231c547b47523d1a9c324cd040afab8ff8101916e4430475f#rd)

---

> 本期看点：Calm 团队分享 Rush.js monorepo 迁移到 Node 类型剥离的实践经验，JavaScript 生态系统 semver 库性能提升 33 倍，从零开始理解 Promises，Cronicle：带有 Web 前端的 Cron，ImageJS v1.0：图像处理和操作库。

> 编辑：TimLi

🔥 本周热门

**如何将我们的 Rush.js Monorepo 迁移到 Node 类型剥离** —— 从 v23.6 版本开始（以及在 v22.18.0 LTS 版本中），Node 已经支持通过类型剥离来运行（大部分）TypeScript 代码。Calm 团队对这项技术提升生产力和开发体验的潜力感到兴奋，并开始了迁移工作。这篇文章分享了他们在迁移过程中遇到的挑战和最终成果。

**长按识别二维码查看原文**

https://blog.calm.com/engineering/how-we-migrated-our-rushjs-monorepo-to-node-type-stripping

Stuart Dotson (Calm)

**加速 JavaScript 生态系统：Semver** —— 这是 Marvin 关于优化 JavaScript 生态系统重要组件的多年系列文章的最新一篇：“在安装过程中，包管理器会进行大量的 semver 比较。npm、yarn 和 pnpm 使用的 `semver` 库可以优化到比原来快 33 倍。”

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-12/

Marvin Hagemeister

**消除 AWS Lambda 上的 JavaScript 冷启动问题** —— Porffor 是一个预先编译（ahead-of-time）JavaScript 编译器，它能让进程启动时间缩短到毫秒级以下。这更像是一个面向未来的尝试，适合用来实验，而不是立即部署到生产环境。

**长按识别二维码查看原文**

https://goose.icu/lambda/

Oliver Medhurst

📄 **理解** `**Promise.any()**`**：当一个成功就够了** —— 在多个 Promise 中，只要有一个完成就立即解析。Matt Smith

**长按识别二维码查看原文**

[https://allthingssmitty.com/https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong//08/25/understanding-promise-any-when-one-success-is-enough/](https://allthingssmitty.com/https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong//08/25/understanding-promise-any-when-one-success-is-enough/)

📄 **JavaScript 中使用 Intl 进行单位格式化** Raymond Camden

**长按识别二维码查看原文**

[https://www.raymondcamden.com/https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong//08/22/unit-formatting-with-intl-in-javascript](https://www.raymondcamden.com/https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong//08/22/unit-formatting-with-intl-in-javascript)

📄 **从零开始理解 Promises** —— 面向初级到中级 JS 开发者。Josh W Comeau

**长按识别二维码查看原文**

https://www.joshwcomeau.com/javascript/promises/

**快讯：**

- Bun 1.3 即将发布，但 Bun v1.2.1 已经发布，亮点包括支持 MySQL、SQLite 和 Postgres 的一级数据库客户端 `Bun.SQL`，以及速度提升 500 倍的 `postMessage(string)` 函数。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-v1.2.21
    

- 在 ESLint v9.34.0 中，ESLint 增加了多线程检查支持，这可能会大大提升大型项目的检查速度。
    
    **长按识别二维码查看原文**
    
    [https://eslint.org/blog/https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong//08/multithread-linting/](https://eslint.org/blog/https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong//08/multithread-linting/)
    

- 运行在 Node.js 运行时的 Vercel Functions 现在支持 `fetch` web 处理程序。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-vercel-functions-now-support-fetch-web-handlers
    

- Next.js 15.5 已发布，稳定支持 Node.js 中间件运行时。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/next-15-5
    

🛠 代码与工具

**Cronicle：带有 Web 前端的 Cron** —— 自称是”高级 cron 替代品”，Cronicle 是一个分布式任务调度和运行器，基于 Node 应用程序构建，带有 Web 界面。GitHub 仓库。

**长按识别二维码查看原文**

https://cronicle.net/

Joseph Huckaby

**ImageJS v1.0：图像处理和操作库** —— 这是一个用于调整大小、裁剪、过滤、颜色调整和其他众多图像转换的库，可在 Node.js 和浏览器中使用（支持 JPEG、PNG、BMP 和 TIFF——这要归功于纯 JS 依赖如 fast-jpeg 和 fast-png）。v1.0 带来了 TypeScript 支持和更直观的 API。GitHub 仓库。

**长按识别二维码查看原文**

https://docs.image-js.org/blog/releases/1.0/

ImageJS Team

**google-spreadsheet v5.0：Node 的 Google Sheets API 封装** —— 从 Node 中操作 Google 在线电子表格，可以在单元格、行、工作表或文档级别进行操作。支持多种认证选项，你还可以导出表格进行下载。GitHub 仓库。

**长按识别二维码查看原文**

https://theoephraim.github.io/node-google-spreadsheet/

Theo Ephraim

**Minecraft MCP Server：让 LLM 控制 Minecraft** —— 一个有趣的方式来玩转 MCP 服务器和 LLM。它在后台使用 Mineflayer，这是一个用于创建 Minecraft 机器人的 JavaScript API。README 中的视频很酷，展示了 Claude 和这个服务器如何将白宫的照片转换成游戏中的建筑。

**长按识别二维码查看原文**

https://github.com/yuniko-software/minecraft-mcp-server

Yuniko Software

📢 其他生态快讯

以下是生态系统中其他一些有趣的故事：

- Sam Rose 制作了一个出色的 Big O 符号图解教程，包含 JavaScript 示例。如果你一直想知道 O(1)、O(log n) 等是什么意思，这是一个很好的入门教程。
    
    **长按识别二维码查看原文**
    
    https://samwho.dev/big-o/
    

- Minification Benchmarks 是一个经常更新的 JavaScript 压缩工具基准测试，最新加入了 cminify。
    
    **长按识别二维码查看原文**
    
    https://github.com/privatenumber/minification-benchmarks
    

- WebKit 团队介绍了 CSS `random()` 函数，现已在 Safari Technology Preview 中可用，之后将以某种形式出现在 CSS 中。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/17285/rolling-the-dice-with-css-random/
    

- 如果你使用 AWS，Corey Quinn 写的这份”你以为你懂但其实已经变了的 AWS 知识”清单会让你大开眼界。
    
    **长按识别二维码查看原文**
    
    [https://www.lastweekinaws.com/blog/aws-in-https://www.lastweekinaws.com/blog/aws-in-https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong/-the-stuff-you-think-you-know-thats-now-wrong/-the-stuff-you-think-you-know-thats-now-wrong/](https://www.lastweekinaws.com/blog/aws-in-https://www.lastweekinaws.com/blog/aws-in-https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong/-the-stuff-you-think-you-know-thats-now-wrong/-the-stuff-you-think-you-know-thats-now-wrong/)
    

- OAuth 图解指南。
    
    **长按识别二维码查看原文**
    
    https://www.ducktyped.org/p/an-illustrated-guide-to-oauth
    

**版本发布：**

- **Repomix v1.4** —— 将整个代码仓库打包成单个 LLM 友好的文件。v1.4 增加了集成提交历史的功能。

- **pg-promise v12.0** —— Node 的 Postgres 接口。现在移除了自定义 Promise 支持，“完全使用 ES6 Promise”。

- **🌈 yoctocolors v2.1.2** —— 轻量级终端文本着色库。来自 Chalk 同一作者的更小替代品。

- **Faker v10.0** —— 随心所欲生成虚拟数据。现在仅支持 ESM。

- **Sidequest.js v1.6** —— Node 应用程序的现代后台任务处理器。

- **🔒 Secretlint v11.2** —— 防止提交凭证/密钥的工具。

- **🤖 OpenAI Node v5.15** —— OpenAI API 的官方 Node 库。

- **InversifyJS v7.9** —— 轻量级控制反转容器。

- **Node-SSH v1.17** —— 纯 JS 实现的 SSH2 客户端和服务器模块。

- **pnpm v10.15** —— 快速、节省空间的包管理器。

- **Undici v7.15** —— Node 的强大 HTTP 客户端库。