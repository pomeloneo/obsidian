# Node 中文周刊 #122 - 恶意 npm 包盗窃 Roblox 用户数据

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526576&idx=1&sn=07978cccb63ed7616ae9467ccb0a5c3c&chksm=e9212352de56aa44927786736c0c424ae4911b9a9ab509b69e0ac790551cf13b2594371c9ee0\#rd  
> 抓取时间: 2026/2/2 23:52:45

---

> 本期看点：最近一次恶意 npm 包攻击瞄准了使用 Roblox（一个受欢迎的虚拟世界游戏）API 的用户。本期的一篇文章详细地介绍了这个恶意包所做的事情。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**Wasp：一个用于 React、Node 和 Prisma 的类 Rails 框架** —— 我在社交媒体上看到的关于 Node 生态系统的一个常见抱怨是缺乏“大框架”。将它与 **Sails** 和 **AdonisJS** 进行对比也许并不公平，不过 Wasp 确实是另一个选择，甚至它自称是 **类 Rails** 的。Wasp 有许多令人喜欢的地方，尤其是这个 **“Open SaaS：的 SaaS 样板应用程序**，可以让你在数分钟内通过几个步骤来构建应用程序。

**长按识别二维码查看原文**

https://wasp-lang.dev/

Wasp, Inc.

**恶意 npm 包盗窃 Roblox 用户数据** —— 看起来我们需要一个 ‘恶意 npm 包周刊’ 了。最近一次攻击瞄准了使用 Roblox（一个受欢迎的虚拟世界游戏）API 的用户。这篇文章详细地介绍了这个恶意包所做的事情。

**长按识别二维码查看原文**

https://socket.dev/blog/malicious-npm-package-masquerades-as-noblox-js

Sarah Gooding（Socket）

👾 与上面提到的恶意包不同，如果你需要与 Roblox 进行交互，可以使用这个正确的 **Noblox.js 包**。

**长按识别二维码查看原文**

https://www.npmjs.com/package/noblox.js

**命令行界面指南** —— 这是一篇精彩的 “开源指南”，旨在使用久经考验的 UNIX-y 风格编写更好的命令行程序。这里有许多有趣的地方，并有些特定于 Node 的建议。

**长按识别二维码查看原文**

https://clig.dev/

Prasad，Firshman，Tashian 与 Parish

💡 与 CLI 相关另一个值得一提的消息是：广受欢迎且功能齐全的 CLI 框架 **Commander.js** 刚刚发布了 **v12.0**。

**长按识别二维码查看原文**

https://github.com/tj/commander.js/releases/tag/v12.0.0

**在 Next.js 路由中如何处理流式文件** —— “尽管这是特定于 Next.js 的，但是它讨论了处理 Node.js 特定 API 路由和运行时无关路由之间的哲学差异，这对于更广泛的后端 JavaScript 开发者来说可能很有趣。”

**长按识别二维码查看原文**

https://www.ericburel.tech/blog/nextjs-stream-files

Eric Burel

**使用 Astra 向量搜索进行主题分类** —— 一个使用 Node 处理数据并通过管道传输到 Datastax 的 **Astra 向量数据库**（使用 Mongoose 和 JSON API 驱动程序）来进行查询的示例。

**长按识别二维码查看原文**

https://thecodebarbarian.com/topic-classifiers-in-nodejs-using-astra-vector-search.html

Valeri Karpov

**快讯：**

- **最新发布的 Deno v1.40** 引入了对 **Temporal API** 和最新的 **装饰器语法提案** 的支持。

**长按识别二维码查看原文**

https://deno.com/blog/v1.40

## 🛠 代码与工具

**Marked.js v12.0：快速的 Markdown 解析和编译器** —— 快速的低级 Markdown 编译器，可用于客户端、服务端以及 CLI。v12 根据 **最近更新** 的 CommonMark 规范进行了调整。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

**🐱 Meow v13.2：简单的 CLI 应用程序助手** —— 只需在一个对象中定义标志、帮助文本和其他功能，剩下的都由它处理。简洁又贴心，甚至没有任何依赖。

**长按识别二维码查看原文**

https://github.com/sindresorhus/meow

Sindre Sorhus

**merge-streams：将多个数据流合并为一个** —— 简单到只需要调用 `mergeStreams([streamA, streamB])`。

**长按识别二维码查看原文**

https://github.com/sindresorhus/merge-streams

Sindre Sorhus

**Neutralinojs v5.0：跨平台桌面应用程序的替代方案** —— **Neutralinojs** 提供了一种构建 Linux、Windows 和 macOS 应用程序的轻量级 Electron 替代方案，不过并不打包 Chromium⸺因为它使用操作系统现有的浏览器引擎。

**长按识别二维码查看原文**

https://neutralino.js.org/docs/release-notes/framework/\#v500

CodeZri

**pkg-tools v1.0：具有类型化配置的构建工具链** —— 对 **unbuild** 构建系统的简单抽象，可集中构建所需的配置并帮助你保持 CJS 和 ESM 的构建一致性。

**长按识别二维码查看原文**

https://github.com/pkg-tools/pkg-tools

Joe McKenney

**版本发布：**

- **Mikro ORM v6.1** – 用于 Node.js 的 TypeScript ORM。

- **query-string v8.2** – 解析和序列化 URL 查询字符串。

- **better-sqlite3 v9.4** – 在 Node 使用 SQLite 的好方法。

- **nvm-desktop v3.0** – 基于Electron 的桌面版 Node 版本管理器。

- **xero-node v5.0** – 流行的 _Xero_ 会计系统的 Node SDK。

- **gaxios v6.2** – 基于 `node-fetch` 的 Axios 风格 HTTP 客户端。

- **js-bson v6.3** – 适用于 Node 和浏览器的 MongoDB BSON 解析器。

- **node-acme-client v5.3** – 简单并且可以自由配置的 ACME 客户端。

- **Got v14.2** – 人性化的 HTTP 请求库。

- **Pino v8.18** – 快速的 JSON 日志记录器。

## 🙋🏻‍♀️