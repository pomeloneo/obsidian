# Node 中文周刊 #178 - Koa v3.0 发布：下一代 Web 框架的新篇章

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541367&idx=1&sn=bde08af3ba3892717241412ac75b91ca&chksm=e9216995de56e08304e5374919506f454dab972828ec915ade3347e34dd2662594c4e8ee1682\#rd  
> 抓取时间: 2026/2/2 23:51:39

---

> 本期看点：Koa v3.0 正式发布并带来现代化的 HTTP 中间件框架，Node.js v22.15.0 LTS 版本发布支持系统证书，Node.js 测试 CI 基础设施遭遇重大安全事件复盘，V8 引擎引入显式编译提示功能以提升启动性能。

> 编辑：TimLi

🔥 本周热门

**Koa v3.0：富有表现力的 HTTP 中间件框架** —— Koa 首次亮相已有十多年，它作为”下一代” Web 框架诞生，与 Express.js 有着共同的血统（和团队），但更多地依赖于当时的现代 JavaScript 特性和理念。虽然 Express 最近有所复兴，但 Koa 也在不断进步，提供了一个极具吸引力的替代方案。v3.0 发布说明。

**长按识别二维码查看原文**

https://koajs.com/

Koa 贡献者

**Node v22.15.0（LTS）发布** —— 这次 Node 最新 LTS 版本的更新包含超过 300 个提交，虽然没有重大功能更新，但内容丰富。现在你可以在 Windows 和 macOS 上使用系统证书，多个依赖包得到更新，文档也有改进，并且新增了 `process.execve` 功能。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.15.0

Ulises Gascón

**Node.js 测试 CI 安全事件详解** —— Node.js 项目最近在其测试 CI 基础设施中遇到了一个严重的安全事件。攻击者利用了 Jenkins 流水线中的一个漏洞，这篇文章详细介绍了事件的来龙去脉以及解决方案。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/march-2025-ci-incident

Node.js 技术指导委员会

**给 V8 一个提示：使用显式编译提示加快启动速度** —— 虽然这不是 Node 特有的功能，但这个 V8 优化未来可能会变得很重要。显式编译提示让你可以指示 V8 预先编译特定文件，从而加快启动速度。该功能已在 Chrome 136 中发布。

**长按识别二维码查看原文**

https://v8.dev/blog/explicit-compile-hints

Marja Hölttä

**📄 十年影响力：我们的 npm 包如何达到 10 亿次下载并塑造 JavaScript** —— 标题虽然有点大，但背后有一个精彩的故事。Forward Email

**长按识别二维码查看原文**

https://forwardemail.net/en/blog/docs/how-npm-packages-billion-downloads-shaped-javascript-ecosystem

**📄 使用** `**async-tree**` **让静态站点生成器变得更小** —— Jan Miksovsky

**长按识别二维码查看原文**

https://jan.miksovsky.com/posts/2025/04-23-async-tree.html

**📄 如何使用 Mocha 在 Node 中编写单元测试** —— Antonello Zanini

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/04/23/how-to-write-unit-tests-in-nodejs-using-mocha.html

**快讯：**

- ⏰ 提醒一下，Node.js v18 将在明天结束生命周期！虽然还有商业支持选项，但如果你能升级到 Node v22，现在就是最好的时机。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/about/previous-releases
    

- 相关消息，Node.js v23 现已进入”维护”模式，不会再有计划中的更新。不过 v24 即将发布，它将成为新的”当前”版本。

- Bun 在向 Node.js 兼容性迈进的过程中继续前进，现在 `events` 模块的 Node.js 测试已 100% 通过。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/
    

- Bun 的其他新闻：Bun 现在有了一个 `llms-full.txt` 文件，包含纯文本文档，可以输入到 LLM 中，帮助你使用 AI 代理等工具处理 Bun。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/llms-full.txt
    

- 使用 Node.js 的 Vercel Functions 现在可以检测取消的请求并在完成前停止执行。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-vercel-functions-now-support-request-cancellation
    

🛠 代码与工具

**Seyfert：构建 Discord 机器人的框架** —— 从响应简单命令到创建组件和获取用户输入，为这个流行的聊天系统创建机器人。最初只支持 Node，但最新版本也支持 Deno 和 Bun。GitHub 仓库。

**长按识别二维码查看原文**

https://www.seyfert.dev/

socram03

**Scala.js v1.19.0：将 Scala 和 JavaScript 结合** —— Scala 是一个强大的语言，已经超越了其 JVM 根源，现在也支持 JavaScript 和原生运行时。Scala.js 是一个 Scala 到 JS 的编译器，主页上有一些很棒的代码和功能对比。

**长按识别二维码查看原文**

https://www.scala-js.org/news/2025/04/21/announcing-scalajs-1.19.0/

Scala.js 团队

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- 我最近在学习一些 C\#，很喜欢这个 TypeScript 对比 C# 指南，主要展示了用 TypeScript/JavaScript 和 C# 实现相同功能的对比示例。
    
    **长按识别二维码查看原文**
    
    https://typescript-is-like-csharp.chrlschn.dev/
    

- 我对这个在 JavaScript 中使用 DuckDB-WASM 创建基础”3D”游戏的实验很感兴趣。这种集成方式也可以用于更实用的数据处理目的。
    
    **长按识别二维码查看原文**
    
    https://www.hey.earth/posts/duckdb-doom
    

- 流行的创意编程库 p5.js 2.0 最近发布，由于这是一次重大升级，所以推出速度非常慢。
    
    **长按识别二维码查看原文**
    
    https://medium.com/processing-foundation/p5-js-2-0-you-are-here-f827f40519a7
    

- 随着 Deno 2.3 即将发布，Deno 团队分享了一些关于最近 Deno 改进的更新。
    
    **长按识别二维码查看原文**
    
    https://deno.news/archive/deno-v23-is-almost-here
    

- Simon Willison 说，如果你想为他人创建完全免费的软件，静态 HTML 和 JavaScript 是最佳方案。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/Apr/28/give-it-away-for-free/
    

- 现在你可以在 pnpm 和 Yarn 中使用 JSR 包了。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/add-jsr-with-pnpm-yarn
    

**版本发布：**

- **🤖 OpenAI Node v4.96** —— OpenAI API 的官方 Node 库。增加了对新的 gpt-image-1 模型的支持。

- **Nest v11.1** —— 用于构建企业级应用程序的流行 Node.js 框架。

- **Electron v36.0** —— 跨平台桌面应用程序框架。

- **Mongoose v8.14** —— 流行的 MongoDB 对象建模库。

- **file-type v20.5** —— 检测文件、流或数据的文件类型。

- **node-argon2 v0.43** —— Argon2 哈希算法的绑定。

- **Middy v6.2** —— Node.js AWS Lambda 中间件引擎。

- **Jasmine v5.7** —— 适用于浏览器和 Node 的测试框架。

- **📊 Chartbrew v4.0** —— 创建实时报告仪表板。

- **pnpm v10.10** —— 快速、节省空间的包管理器。