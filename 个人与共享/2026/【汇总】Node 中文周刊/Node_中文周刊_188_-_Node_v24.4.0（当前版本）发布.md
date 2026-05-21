# Node 中文周刊 #188 - Node v24.4.0（当前版本）发布

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542658&idx=1&sn=b574d2093cf171c1242ca78a0a2d7790&chksm=e9216c60de56e57601efec07cc8ca8ae205bba1af3669aa506466912e8c334c5c741e7bfb3ca#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542658&idx=1&sn=b574d2093cf171c1242ca78a0a2d7790&chksm=e9216c60de56e57601efec07cc8ca8ae205bba1af3669aa506466912e8c334c5c741e7bfb3ca#rd): 2026/2/2 23:51:26

---

> 本期看点：Node v24.4.0 支持自定义监视模式信号及权限模型标志，TypeScript v5.9 Beta 发布并引入 import defer 和 node20 模式，Node.js 版本管理器性能差异分析，Necord：创建 Discord 机器人的框架。

> 编辑：TimLi

🔥 本周热门

**Node v24.4.0（当前版本）发布** —— 现在你可以使用 `--watch-kill-signal` 来指定在 Node 的”监视模式” 重启进程时发送的信号；`spawn` 和 `spawnSync` 现在可以传递权限模型标志；此外还包括常规的 V8 和依赖项更新。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.4.0

Rafael Gonzaga

💡 Node 团队还宣布在未来一两天内将发布 v24.x、22.x 和 20.x 的新版本，以解决一些安全问题，请留意这些更新。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/vulnerability/july-https://nodejs.org/en/blog/vulnerability/july-2025-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/july-https://nodejs.org/en/blog/vulnerability/july-2025-security-releases-security-releases)

**提案：Node.js 转向年度主版本发布** —— 目前正在讨论 Node 是否可以转向年度主版本发布，并将偶数版本的 LTS 支持期从当前的 30 个月缩短到 24 个月。欢迎社区在这个帖子中提供反馈。

**长按识别二维码查看原文**

https://github.com/nodejs/Release/issues/1113

Rafael Gonzaga 等

**TypeScript v5.9 Beta 发布** —— 最重要的新特性可能是对 `import defer` 的支持，此外还有新的 `node20` 模式，它类似于 `nodenext` 但目标是 ES2023。我们还了解到，基于 Go 的”原生移植版” TypeScript 最终将作为 TypeScript 7 发布。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-9-beta/\#support-for—module-node20

Microsoft

**📊 Node 版本管理器之间 500 倍的性能差距（以及为什么你可能不需要在意）** —— Pavel 开篇就说：“你选择的 Node.js 版本管理器可能会让 shell 启动速度慢 500 倍”。他分享了一些基准测试结果，但最后得出结论：除非你经常启动新的 shell，否则这可能并不是太大的问题。

**长按识别二维码查看原文**

https://nodevibe.substack.com/p/the-500x-performance-gap-between

Pavel Romanov

**📄 JavaScript 作用域提升存在问题** —— Parcel 的创建者认为作用域提升与现代 JS 模式存在冲突。Devon Govett

**长按识别二维码查看原文**

https://devongovett.me/blog/scope-hoisting.html

**📄 使用** `**Array.fromAsync()**` **实现现代异步迭代** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/07/14/modern-async-iteration-in-javascript-with-array-fromasync/

**📄 类型化查询构建器：比较 Kysely 和 Drizzle** Guillaume Billey

**长按识别二维码查看原文**

https://marmelab.com/blog/2025/06/26/kysely-vs-drizzle.html

**快讯：**

- Node.js v18 在 [https://nodejs.org/en/blog/vulnerability/july-2025-security-releases](https://nodejs.org/en/blog/vulnerability/july-2025-security-releases) 年 4 月结束生命周期，但 Ubuntu 的维护者 Canonical 宣布 Ubuntu Pro 用户现在可以获得支持直到 2032 年。
    
    **长按识别二维码查看原文**
    
    [https://ubuntu.com/blog/nodejs-18-lts-eol-extended-from-april-https://nodejs.org/en/blog/vulnerability/july-2025-security-releases-to-may-2032-on-ubuntu](https://ubuntu.com/blog/nodejs-18-lts-eol-extended-from-april-https://nodejs.org/en/blog/vulnerability/july-2025-security-releases-to-may-2032-on-ubuntu)
    

- Callstack 宣布为 React Native 提供 Node-API 支持，为跨平台编写和共享原生代码提供了更多选择。
    
    **长按识别二维码查看原文**
    
    https://www.callstack.com/blog/announcing-node-api-support-for-react-native
    

- Igalia 团队分享了最新 TC39 全体会议的详细总结，其中包含了关于 ECMAScript 发展的许多有趣细节。
    
    **长按识别二维码查看原文**
    
    https://blogs.igalia.com/compilers/2025/07/03/summary-of-the-may-2025-tc39-plenary/
    

- 朝鲜”威胁行为者”部署了 67 个恶意 npm 包，Kirill Boychenko 告诉我们这些包是什么以及它们是如何工作的。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/contagious-interview-campaign-escalates-67-malicious-npm-packages
    

🛠 代码与工具

**Necord：创建 Discord 机器人的框架** —— 它在底层使用 Nest 和 Discord.js。示例应用程序展示了部署机器人功能有多简单。GitHub 仓库。

**长按识别二维码查看原文**

https://necord.org/

Necord

**✉️ Upyo：一个简单的跨运行时邮件发送库** —— 这是一个跨运行时的邮件库，为 SMTP 和基于 HTTP 的提供商（如 SendGrid 或 Amazon SES）提供统一的类型安全 API。**今天才知道”upyo”（우표）在韩语中是”邮票”的意思。**

**长按识别二维码查看原文**

https://upyo.org/

Hong Minhee

**Rewire v9.0：让单元测试的猴子补丁更容易** —— 为 CommonJS（仅限）模块增强特殊的 setter 和 getter，用于注入模拟对象、检查私有变量和覆盖模块内部实现。

**长按识别二维码查看原文**

https://github.com/jhnns/rewire

Johannes Ewald

**Envalid v8.1：环境变量验证** —— 确保你的程序只在满足所有环境依赖时才运行。v8.1 是一个小更新，不过是两年来的首次更新。

**长按识别二维码查看原文**

https://github.com/af/envalid

Aaron Franks

**cRonstrue v3.0：将 Cron 表达式转换为自然语言** —— 不仅支持英语，还支持大约三十种语言。还有在线演示。

**长按识别二维码查看原文**

https://github.com/bradymholt/cRonstrue

Brady Holt

📢 其他

以下是一些你可能错过的其他有趣故事：

- 📅 new Date(“wtf”) —— 你对 JavaScript 的 Date 类和日期解析的工作原理了解多少？来做这个令人头疼的测验就知道了。
    
    **长按识别二维码查看原文**
    
    https://jsdate.wtf/
    

- ANSI.tools 是一个方便的在线工具，用于分析 ANSI 转义码/序列，还有常用代码查询。
    
    **长按识别二维码查看原文**
    
    https://ansi.tools/
    

- Tae Kim 解释了他如何在 Bun 中解决”10 亿行挑战”，并能在不到 10 秒内处理 10 亿行文件。
    
    **长按识别二维码查看原文**
    
    https://www.taekim.dev/writing/parsing-1b-rows-in-bun
    

- Nginx HTTP 服务器有一个用于使用 JavaScript 扩展其功能的模块（`njs`），但它只支持 ES5。现在，`njs` 使用 QuickJS 提供更现代、更强大的体验，完全支持 ES2023。
    
    **长按识别二维码查看原文**
    
    https://nginx.org/
    

**版本发布：**

- **ESLint v9.31.0** —— 四个核心规则已更新以支持显式资源管理。

- **Serverless Express v4.17** —— 在 AWS Lambda、API Gateway、Lambda@Edge 等上运行 Express.js。

- **NATS.js v3.1** —— NATS 消息系统的 JavaScript 客户端。

- **open v10.2** —— 跨平台打开 URL、文件和可执行文件。

- **🤖 OpenAI Node v5.9** —— OpenAI 的官方 Node 库。

- **snakecase-keys v9.0** —— 将对象键转换为蛇形命名。

- **Poolifier v5.1** —— Worker 线程和集群工作进程池。