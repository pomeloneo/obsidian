# Node 中文周刊 #194 - npm 生态系统遭受重大供应链攻击

> 原文链接: [](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543566&idx=1&sn=1b756a3d903beef4714ede9000ac7787&chksm=e92160ecde56e9fa320447dbf37d29e9de8f684dd7ae5e4ceb0c7c745bcc5c00c50046e2b75d#rd)[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543566&idx=1&sn=1b756a3d903beef4714ede9000ac7787&chksm=e92160ecde56e9fa320447dbf37d29e9de8f684dd7ae5e4ceb0c7c745bcc5c00c50046e2b75d#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543566&idx=1&sn=1b756a3d903beef4714ede9000ac7787&chksm=e92160ecde56e9fa320447dbf37d29e9de8f684dd7ae5e4ceb0c7c745bcc5c00c50046e2b75d#rd): 2026/2/2 23:51:19

---

> 本期看点：npm 生态系统遭受重大供应链攻击，Cloudflare Workers 现已支持 Node HTTP 服务器，Node.js v20.19.5（LTS）发布，Mediabunny 发布无需 FFmpeg 的 JavaScript 媒体工具包。

> 编辑：TimLi

🔥 本周热门

**npm 生态系统遭受重大供应链攻击** —— 今年 7 月，Socket 曾警告过一场针对 npm 包发布者的钓鱼活动。不幸的是，一位多产的包作者（以及其他开发者，比如 DuckDB，他们详细解释了攻击的过程）成为了受害者，导致一些流行的包被攻击者控制（包括 Chalk、debug 和其他包）。

**长按识别二维码查看原文**

https://socket.dev/blog/npm-author-qix-compromised-in-major-supply-chain-attack

Gooding、Brown 等人（Socket）

💡 受上述事件启发，Zbyszek Tenerowicz 展示了一个有趣的工具，这是他参与开发的一个 Webpack 插件，名为 LavaMoat。它可以通过预定义的策略来沙箱化和限制依赖包的访问权限。

**长按识别二维码查看原文**

https://github.com/naugtur/running-qix-malware

**Cloudflare Workers 现已支持 Node HTTP 服务器** —— 几周前我们提到过，Cloudflare Workers 的本地开发工具开始支持 Express.js 应用程序。现在这项支持已经正式登陆 Workers 平台，只要启用 Node.js 兼容模式，就可以使用 `node:http` 的客户端和服务器 API。

**长按识别二维码查看原文**

https://blog.cloudflare.com/bringing-node-js-http-servers-to-cloudflare-workers/

Nizipli 和 Snell（Cloudflare）

**Node.js v20.19.5（LTS）发布** —— 这是一个主要包含 bug 修复和大量依赖更新的小版本更新。它紧随 v22.19.0（LTS） 之后发布，后者取消了 `--experimental-wasm-modules` 的实验标记，为 `http` 模块添加了 `server.keepAliveTimeoutBuffer` 选项，并通过 `NODE_USE_SYSTEM_CA` 环境变量增加了使用系统证书颁发机构（CA）的功能。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.19.5

Marco Ippolito

**📄 使用** `**Intl.Segmenter**` **获取准确的文本长度** —— 当 `str.length` 返回的结果不符合预期时，这个技巧会很有用。Sangeeth Sudheer

**长按识别二维码查看原文**

https://blog.sangeeth.dev/posts/accurate-text-lengths-with-intl-segmenter-api/

**📺 如何用 4 美元的 VPS 处理 5 亿次点击** —— 一位开发者分享了他的 Node.js 网站在爆火后的幕后故事。Andrew Schmelyun

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=nk3Ti0tCGvA

**📄 为什么我从 Docker 转向了 Podman（你也该这样做）** Dominik Szymański

**长按识别二维码查看原文**

https://codesmash.dev/why-i-ditched-docker-for-podman-and-you-should-too

**📄 Node.js 中的 UDP：技术指南** Pavel Romanov

**长按识别二维码查看原文**

https://nodevibe.substack.com/p/udp-in-nodejs-deep-technical-guide

**快讯：**

- Vercel 现已支持零配置的 Express 后端，运行在 Node 上的 Vercel Functions 现在也支持优雅关闭，给你 500 毫秒的时间来执行清理任务。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/zero-configuration-express-backends
    

- 📗 NodeBook 是一本正在编写中的新书，承诺深入探讨 Node 的内部原理。目前已经发布了关于 V8 JavaScript 引擎和 Node 事件循环工作原理的内容。
    
    **长按识别二维码查看原文**
    
    https://www.thenodebook.com/
    

- 在 X 平台上，Marco Ippolito 感叹 Node.js 陷入了一个矛盾：对某些开发者来说”太快”，而对另一些人来说又”太慢”。
    
    **长按识别二维码查看原文**
    
    https://x.com/satanacchio/status/1965072308789514255
    

🛠 代码与工具

**Mediabunny：JavaScript 的完整媒体工具包** —— 这是一个无需依赖 FFmpeg 就能读取、写入和转换主流媒体文件格式（如 MP4、MP3 等更多格式）的库。你可以用它来生成缩略图、提取元数据，甚至将代码转换成视频等。GitHub 仓库。

**长按识别二维码查看原文**

https://mediabunny.dev/

Vanilagy

**sqs-consumer v13.0：无需样板代码构建 Amazon SQS 应用程序** —— 让你无需编写样板代码就能构建基于 SQS（Simple Queue Service）的应用程序。只需定义一个异步函数来处理 SQS 消息即可。连 BBC 都在用这个工具。

**长按识别二维码查看原文**

https://github.com/bbc/sqs-consumer

BBC

**github-script v8.0：在 GitHub Actions 工作流中操作 GitHub API** —— 如果你想在 GitHub Actions 中使用 JavaScript 来操作 GitHub API，这个工具就是为你准备的。现已支持 Node.js 24。

**长按识别二维码查看原文**

https://github.com/actions/github-script

GitHub Actions

📢 其他生态快讯

以下是生态系统中其他一些有趣的故事：

- 了解浏览器为什么要限制 JavaScript 定时器，Nolan Lawson 的这篇文章还介绍了一些让函数尽快执行的技巧。
    
    **长按识别二维码查看原文**
    
    [https://nolanlawson.com/https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025/08/31/why-do-browsers-throttle-javascript-timers/](https://nolanlawson.com/https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025/08/31/why-do-browsers-throttle-javascript-timers/)
    

- Andromeda 是最新加入 JavaScript 运行时阵营的新成员，由 Nova 引擎驱动。它使用 Rust 构建，支持直接的 GPU 加速图形处理、单文件编译和内存安全特性。
    
    **长按识别二维码查看原文**
    
    https://tryandromeda.dev/
    

- 🗓️ Thoughtbot 分享了 [https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025](https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025) 年剩余时间的 JavaScript 会议列表。
    
    **长按识别二维码查看原文**
    
    [https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025](https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025)
    

- `Intl` Playground 是一个很方便的网站，可以快速查看 `Intl.DateTimeFormat` 的不同选项在实际中的效果。
    
    **长按识别二维码查看原文**
    
    https://intlin.site/
    

- Deno 的 Fresh 框架发布了 Fresh 2.0 Beta 版。现在它可以作为 Vite 插件运行，这开启了许多新的可能性。
    
    **长按识别二维码查看原文**
    
    https://fresh.deno.dev/
    

- 今天学到：MacBook Pro 有一个”盖子角度传感器”可以通过编程查询。这个 X 平台上的视频展示了这个功能的有趣效果。
    
    **长按识别二维码查看原文**
    
    https://github.com/samhenrigold/LidAngleSensor
    

**版本发布：**

- **serverless-http v4.0** —— 在 AWS Lambda 上使用你熟悉的中间件框架（如 Express、Koa）。

- **express-openapi-validator v5.6** —— 根据 OpenAPI 3.x 规范自动验证 Express 中的 API 请求和响应。

- **Prisma v6.15** —— 这个流行的 Node.js 和 TypeScript ORM 新增了一些 AI 安全防护措施。

- **Tinypool v2.0** —— 轻量级的 Node.js 工作线程池实现。

- **Sidequest v1.7** —— 可扩展的 Node 应用程序后台任务处理器。

- **MongoDB Node.js Driver v6.19** —— 最新的官方 MongoDB 驱动程序。

- **Electron v38.0** —— 跨平台桌面应用程序框架。

- **express-rate-limit v8.1** —— Express 应用程序的基础限流工具。

- **Fastify v5.6** —— 快速、低开销的 Node web 框架。

- **JSPyBridge v1.2.5** —— 在 Node 中运行 Python 代码，反之亦然。

- **NodeBB v4.5** —— 基于 Node.js 的论坛系统。

- ESLint v9.35.0