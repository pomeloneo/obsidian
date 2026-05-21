# Node 中文周刊 #186 - 2025 年 Node.js 现代开发模式

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542407&idx=1&sn=e2e3601fe703f96109bb90c460a6394f&chksm=e9216d65de56e47356adca22675443b345e87fb965c7a2f8491181e9c4c65ad146cb8eb7983b#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542407&idx=1&sn=e2e3601fe703f96109bb90c460a6394f&chksm=e9216d65de56e47356adca22675443b345e87fb965c7a2f8491181e9c4c65ad146cb8eb7983b#rd): 2026/2/2 23:51:29

---

> 本期看点：2025 年 Node.js 现代开发模式总结 ES 模块、内置 Web API、测试运行器等特性，Node v22.17.0（LTS）发布并带来多项 API 稳定升级，Transformers.js 支持在 Node 中运行 Gemma 3n 模型，Repomix 发布助力代码库 AI 友好化。

> 编辑：TimLi

🔥 本周热门

**2025 年 Node.js 现代开发模式** —— 今年已经过半，让我们来看看 Node.js 目前的发展潜力。Ashwin 为我们总结了一些重要特性，包括 ES 模块、内置 Web API、测试运行器、监视模式、权限模型、import maps 等。

**长按识别二维码查看原文**

https://kashw1n.com/blog/nodejs-2025/

Ashwin

**Node v22.17.0（LTS）发布** —— 这是一个重要的 LTS 版本，`assert.partialDeepStrictEqual()` 升级为稳定版，同时还有许多长期处于实验阶段的 API 和函数也转正了，另外还从 Node 24 向后移植了一些特性。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.17.0

Antoine du Hamel

💡 Node v24.3.0（Current）已经发布，但没有重大新特性。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.3.0

**Ecma International 批准 ECMAScript 2025：有什么新特性？** —— Ecma 大会已经批准了 ES2025 语言规范，你可以在这里阅读完整规范，或者看看 Dr. Axel 写的这篇简明解释。

**长按识别二维码查看原文**

https://2ality.com/2025/06/ecmascript-2025.html

Dr. Axel Rauschmayer

**用 Cedar 在 5 分钟内保护你的 Express API** —— Cedar 是一个用于定义和评估权限的语言和规范。它的新库 authorization-for-expressjs 让 Express.js 应用程序可以轻松使用 Cedar 进行授权。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/opensource/secure-your-application-apis-in-5-minutes-with-cedar/

Trevor Schiavone (AWS)

**V8：使用反优化和内联对 WebAssembly 进行推测性优化** —— 这是一篇**非常**技术性的文章，V8 团队介绍了两项重要的新优化技术，可以让 WebAssembly 代码运行得更快。

**长按识别二维码查看原文**

https://v8.dev/blog/wasm-speculative-optimizations

Daniel Lehmann 和 Matthias Liedtke (V8)

**📄 如何使用 NestJS 作为 WebRTC 视频聊天的信令服务器** Christian Nwamba

**长按识别二维码查看原文**

https://www.telerik.com/blogs/how-to-use-nestjs-signaling-server-webrtc-video-chat

**📄 如何写出引人入胜的软件发布公告** Michael Lynch

**长按识别二维码查看原文**

https://refactoringenglish.com/chapters/release-announcements/

**📺 使用 Claude Code 构建 GitHub Actions 工作流** —— Simon 用的是 Python，但你完全可以让 Claude 使用 JavaScript 甚至 shell 脚本。Simon Williso

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VC6dmPcin2E

**💬 为什么我的 Node 多人游戏在 500 玩家时会卡顿，但 CPU 占用很低？** —— 一个公开讨论。Hacker News

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=44389408

**快讯：**

- 🦋 Node.js 项目现在有了官方 Bluesky 账号用于分享更新，团队希望听听你对内容发布的建议。
    
    **长按识别二维码查看原文**
    
    https://bsky.app/profile/nodejs.org
    

- Ryan Dahl 发布了关于 JavaScript™ 商标纠纷的最新进展。Oracle 还有一个月时间对 Deno 的撤销申请做出完整回应。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-v-oracle4
    

- Node 官方博客正在庆祝六月的骄傲月，发布了关于身份认同的思考和对 Emilia Smith 的专访，她在 Node.js 早期做出了重要贡献。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/community/2025-pride
    

🛠 代码与工具

**Transformers.js v3.6：现在可以在 Node 中运行 Gemma 3n 了** —— **Transformers.js** 将 Hugging Face 流行的 Python **Transformers** 库的功能带到了 JavaScript 世界，让你可以使用各种机器学习模型进行自然语言处理、视觉、音频处理等（借助 ONNX）。v3.6 的一大特性是支持 Google 的新 Gemma 3n 模型。

**长按识别二维码查看原文**

https://github.com/huggingface/transformers.js/releases/tag/3.6.0

Hugging Face

💡 相关消息：Meridius Labs 正在开发一个非官方库，用于在 macOS Tahoe 上使用新的 Apple Foundation 模型。

**长按识别二维码查看原文**

https://github.com/Meridius-Labs/apple-on-device-ai

**Repomix v1.0：将代码库打包成 AI 友好的格式** —— 输入一个 GitHub URL，选择输出设置（XML、MD 等）。它基于 Node.js 开发，你也可以把它当作库来用于自己的工具开发。v1.0 本质上是一个”现在稳定且完整了”的版本。GitHub 仓库在这里。

**长按识别二维码查看原文**

https://repomix.com/

Kazuki Yamada

**Marked v16.0：快速的 Markdown 解析器和编译器** —— 在这里体验 Demo。GitHub 仓库。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

**whatsapp-api-js：WhatsApp 官方 API 的库** —— 适用于已激活 WhatsApp API 的 Meta Business App 用户。

**长按识别二维码查看原文**

https://github.com/Secreto31126/whatsapp-api-js

Tomás Raiti

📢 其他 JavaScript 相关

以下是 JavaScript 生态圈的一些其他有趣动态，以防你错过：

- Deno 团队展望了 JavaScript 的未来发展，用简单的解释和示例代码介绍了最近 TC39 会议上推进的九个提案。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/updates-from-tc39
    

- 🐘 PLJS 是一个 Postgres 扩展，让你可以用 JavaScript（由 QuickJS 驱动）而不是 PL/pgSQL 编写数据库函数。
    
    **长按识别二维码查看原文**
    
    https://github.com/plv8/pljs
    

- JSConf 2025 的演讲嘉宾名单已经公布。会议将于今年十月在马里兰州举行。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/jsconf-25-speakers-announced
    

- 如果 Cloudflare Workers 的限制太多，Cloudflare 现在有了新选择：Cloudflare Containers。**Containers** 与 Workers 集成，但不出意外地，它让你可以更灵活地将应用程序打包成容器镜像并运行。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/containers-are-available-in-public-beta-for-simple-global-and-programmable/
    

- Alex Kladov 展示了如何轻松创建服务端静态生成的 RSS 阅读器 —— 他用的是 Deno，但你用 Node 也一样容易实现。
    
    **长按识别二维码查看原文**
    
    https://matklad.github.io/2025/06/26/rssssr.html
    

- 🕒 Temporal API 提案现已进入 Stage 3 草案阶段。
    
    **长按识别二维码查看原文**
    
    https://tc39.es/proposal-temporal/
    

**版本发布：**

- **dotenv v17.0** —— 从 `.env` 加载环境变量的模块，如果你还没用上 Node 的内置机制的话可以试试。

- **Electron v37.0.0** —— 跨平台桌面应用程序开发工具包。

- **npm-package-json-lint v9.0** —— Node 项目的 `package.json` 检查工具。

- **🤖 OpenAI v5.8.0** —— 增加了对 OpenAI API 新的 webhooks 和”深度研究”功能的支持。

- **better-sqlite3 v12.2** —— 这个流行的强大 SQLite 库更新到了最新的 SQLite 3.50.2。

- **xero-node v13.0** —— **Xero** 会计系统的 Node SDK。

- **Mineflayer v4.30** —— 用 JavaScript 创建 Minecraft 机器人。

- **Undici v7.11** —— Node 强大的 HTTP 客户端库。