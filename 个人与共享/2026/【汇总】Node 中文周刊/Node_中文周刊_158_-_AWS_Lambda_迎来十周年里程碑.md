# Node 中文周刊 #158 - AWS Lambda 迎来十周年里程碑

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537560&idx=1&sn=a2771a0ee283e45955827999e9e3d74e&chksm=e921187ade56916c8101677fe7b66c3ce6fa9ba683874460545bc8a4837225ac9dda2bee219c\#rd  
> 抓取时间: 2026/2/2 23:52:02

---

> 本期看点：AWS Lambda 庆祝十周年并回顾无服务器计算的发展历程，Val Town 推出创新的在线 TypeScript 社交编程平台，Node.js v18.20.5 LTS 版本发布并将导入属性标记为稳定，Discordeno v19 发布带来重大更新。

> 编辑：TimLi

🔥 本周热门

**AWS Lambda 十周年：回顾与展望** —— AWS Lambda 作为亚马逊的云函数服务，实际上开创了”无服务器”这一概念，并对 Node.js 在云端的应用产生了重大影响。Node v0.10 是其最初也是唯一支持的运行时（直到一年后才加入了 Java 支持）。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/aws/aws-lambda-turns-ten-the-first-decade-of-serverless-innovation/

Jeff Barr (AWS)

**Val Town：一个编写和部署 TypeScript 的社交平台** —— 继续无服务器相关的话题，“如果 GitHub Gists 可以运行，而 AWS Lambda 更有趣”是对这个在线平台的恰当描述。在这里，你可以编写简短的函数（称为”val”），它们会在 V8 隔离环境中运行。你可以将它们连接在一起、设置定时任务，甚至通过 HTTP 提供服务等。

**长按识别二维码查看原文**

https://www.val.town/

Steve Krouse

**Node v18.20.5（LTS）发布** —— Node v18 仍处于”维护 LTS”阶段（直到 2025 年 5 月），虽然你不能期待什么重大更新，但这个版本更新了许多关键依赖，并将导入属性和 JSON 模块支持标记为稳定版。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.20.5

Antoine du Hamel

**通过电话与 ChatGPT 对话** —— 这需要一些第三方服务，如 Twilio、AssemblyAI 以及 OpenAI 的 GPT 4，但你可以用 Node 将这些服务组合在一起，做出一个相当不错的演示。

**长按识别二维码查看原文**

https://www.assemblyai.com/blog/talk-to-chatgpt-on-a-phone-call/

Artem Oppermann

**npmpackage.info：在单页面上展示详细的包信息** —— 只需输入一个 npm 包的名称，这个在线工具就能为你提供一个快速的”仪表板”式视图，显示项目的主要统计数据，包括质量评分、提交记录、未解决问题、发布版本、包大小等信息。

**长按识别二维码查看原文**

https://npmpackage.info/

Shrinath Nayak

**📄 运行旧 Node 项目的困境** —— 当你几年没有部署一个应用程序时，问题可能会快速堆积。Abdisalan Mohamud

**长按识别二维码查看原文**

https://abdisalan.com/posts/tragedy-running-old-node-project/

**📄 使用 Fraction.js 在 JavaScript 中进行精确的小数计算** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/fraction-numbers-in-javascript

**📄 如何在 Node 中快速读取文件（以及与 Bun 的对比）** Daniel Lemire

**长按识别二维码查看原文**

https://lemire.me/blog/2024/03/12/how-to-read-files-quickly-in-javascript/

**📄 如何避免 Playwright 中的不稳定测试** Zanini 和 Ackerson

**长按识别二维码查看原文**

https://semaphoreci.com/blog/flaky-tests-playwright

**📄 如何为 process.env 添加强类型** Matt Pocock

**长按识别二维码查看原文**

https://www.totaltypescript.com/how-to-strongly-type-process-env

🛠 代码与工具

**💬 Discordeno v19：强大的 Discord API 库** —— 这是一个用于操作流行的 Discord 聊天系统并构建机器人的长期解决方案。v19 是一次重大更新，包含了破坏性变更。GitHub 仓库。

**长按识别二维码查看原文**

https://discordeno.js.org/

Discordeno Team

**SVG To Font v6.1：将 SVG 图标转换为字体文件** —— 这既是一个命令行工具也是 Node 库，可以读取一组 SVG 文档并输出 WOFF2、WOFF、EOT、TTF 和 SVG 字体。特别适合从一组图标生成 Web 字体，如这个演示所示。

**长按识别二维码查看原文**

https://wangchujiang.com/svgtofont/

Kenny Something

**wacat v1.2：用”猫咪混乱”测试你的 Web 应用程序** —— 使用虚拟的”猫咪在键盘上乱走”方式来折磨应用程序，进行随机点击和表单提交。v1.2 版本增加了 LLM 集成，用于检测和处理过程中的错误状态。

**长按识别二维码查看原文**

https://github.com/mikesmallhelp/wacat

Mika Tapanainen

**Node-OracleDB v6.7：Oracle 官方 Node 数据库驱动** —— 虽然我本人不是 Oracle 数据库用户，但我很欣赏 Oracle 在维护其 Node.js 驱动方面付出的努力。v6.7 添加了 OpenTelemetry 支持和可设置的 V$ 会话属性。

**长按识别二维码查看原文**

https://medium.com/@sharad-chandran/node-oracledb-6-7-brings-more-flexibility-and-power-to-oracle-database-apps-a3c315738864

Sharad Chandran (Oracle)

**版本发布：**

- **☕ Javet v4.1** —— Java + V8。将 Node.js 和 V8 嵌入 Java。更新至 Node v22.11.0 并添加 Float16 支持。

- **node-pg-migrate v7.8** —— 从 Node 管理数据库迁移。现在支持表分区。

- **🐂 BullMQ v5.27** —— 基于 Redis 的可靠分布式队列。

- **Verdaccio v6.0.2** —— 轻量级本地私有 npm 注册表。

- **airtap v5.0** —— 在 1789+ 浏览器中运行 TAP 单元测试。

- **ESLint v9.15.0**