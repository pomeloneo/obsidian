# Node 中文周刊 #176 - Fastify + React 性能是 Next.js 的 7 倍？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541174&idx=1&sn=1e369617719d599ed8a35fcae2c080ec&chksm=e9216a54de56e34213527fe8458ada55409fab7a8fd965aabb58f04c3fb24dfb73c950ef8177\#rd  
> 抓取时间: 2026/2/2 23:51:41

---

> 本期看点：Fastify 与 React 集成方案性能表现优异，@fastify/react 发布 1.0 版本；Tauri 和 Electron 的对比；ESLint 引入批量抑制功能简化代码检查管理；Lexe 工具可将 Node 应用打包成小于 10MB 的可执行文件。

> 编辑：TimLi

🔥 本周热门

**Fastify + React —— 速度是 Next.js 的 7 倍？** —— Node 的 Fastify 框架有一个成熟的 Vite 集成插件（这里有详细介绍），包括刚刚发布 1.0 版本的 @fastify/react。它让你能够在 Fastify 之上轻松创建快速、功能丰富（当然比 Next.js 少一些）的 React 应用程序。速度如何？看起来非常快。

**长按识别二维码查看原文**

https://hire.jonasgalvez.com.br/2025/apr/9/fastify-speed/

Jonas Galvez

💡 如果你在寻找比 Next.js 更轻量但文档完善的替代品，Waku 也值得一试。

**长按识别二维码查看原文**

https://waku.gg/

**构建桌面应用程序：Tauri 和 Electron 的对比** —— Electron 是构建基于 JS 和 HTML 的跨平台桌面应用程序的自然选择，但现在出现了许多替代方案，比如 Neutralinojs 和基于 Rust 的 Tauri。这篇文章简明扼要地展示了 Tauri 的不同之处以及为什么你可能会选择它。

**长按识别二维码查看原文**

https://gethopp.app/blog/tauri-vs-electron

Costa Alexoglou

**2025 年每个 JavaScript 开发者都应该知道的特性** —— 一篇快速列举了一些现代 JavaScript 特性的文章，包括迭代器助手、`structuredClone()`和集合操作等。

**长按识别二维码查看原文**

https://waspdev.com/articles/2025-04-06/features-that-every-js-developer-must-know-in-2025

Suren Enfiajyan

**📄 掌握 Docker 和 VS Code：提升你的开发工作流** —— 包含 Node.js 示例。Vladimir Mikhalev

**长按识别二维码查看原文**

https://www.docker.com/blog/master-docker-vs-code-supercharge-your-dev-workflow/

**📄 TypeScript 部署：最新进展和未来方向** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/04/deploying-typescript-present-future.html

**📄 NPM 安全最佳实践** OWASP Cheat Sheet Series

**长按识别二维码查看原文**

https://cheatsheetseries.owasp.org/cheatsheets/NPM_Security_Cheat_Sheet.html

**📄 在 Bun 中调试 JavaScript 内存泄漏** Jarred Sumner

**长按识别二维码查看原文**

https://bun.sh/blog/debugging-memory-leaks

**快讯：**

- 📘 Dr. Axel Rauschmayer 发布了《探索 TypeScript：TS 5.8 版本》——你可以购买，也可以在线免费阅读 HTML 版本。
    
    **长按识别二维码查看原文**
    
    https://exploringjs.com/ts/
    

- ESLint 添加了”批量抑制”支持，这让采用更严格的代码检查规则变得更容易管理。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/04/introducing-bulk-suppressions/
    

- 如果你上周在使用 npm 时遇到问题，那是因为 npm registry 意外清除了所有用户的访问令牌。这个事件在这里有详细总结，现在已经解决，一切都恢复正常了。
    
    **长按识别二维码查看原文**
    
    https://github.com/orgs/community/discussions/156354
    

- Bun v1.2.9 已发布。这个替代 JS 运行时一如既往地在持续增强其 Node.js 兼容性。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.9
    

🛠 代码与工具

**Lexe：将 Node 应用程序打包成单个可执行文件** —— Node 实际上有创建单文件可执行应用程序的机制，也有很多其他工具可以实现这一点。但 Lexe 采用了不同的方法，它使用亚马逊的轻量级 LLRT 引擎来生成小于 10MB 的二进制文件。不过请注意，“Lexe 不是 Node.js 的直接替代品，它只支持 Node.js API 的一个子集。”

**长按识别二维码查看原文**

https://github.com/Ray-D-Song/lexe

Ray-D-Song

**Prisma ORM v6.6.0 发布** —— 引入了一个更灵活的新 `prisma-client` 生成器，支持 ESM，并预览了一个 MCP 服务器，让 AI 代理和工具能够管理 Postgres。

**长按识别二维码查看原文**

https://www.prisma.io/blog/prisma-orm-6-6-0-esm-support-d1-migrations-and-prisma-mcp-server

Nikolas Burk

**Chrono v2.8：自然语言日期解析器** —— 给它一个字符串，比如”今天”、“上周五”、“两周后”，甚至完整的日期和时间，它都能生成相应的日期对象。

**长按识别二维码查看原文**

https://github.com/wanasit/chrono

Wanasit Tanakitrungruang

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- Matt Smith 展示了使用空值合并运算符 `??` 应用默认值的更好方法，比使用 `||` 更优。
    
    **长按识别二维码查看原文**
    
    https://allthingssmitty.com/2025/04/10/mastering-default-values-in-javascript-with-the-nullish-coalescing-operator/
    

- 🤖 上周，Google 发布了 Firebase Studio，这是一个在线 AI 开发环境，类似于你可能在 v0、Cursor 或 Lovable 中看到的工具。
    
    **长按识别二维码查看原文**
    
    https://firebase.studio/
    

- ☁️ Cloudflare 在其”开发者周”期间发布了很多更新：现在可以轻松将 Next.js 应用程序部署到 Cloudflare Workers，你可以在 git 仓库中添加”部署到 Workers”按钮，现在可以在一个 Worker 中部署完整的前端、后端和数据库（支持 React Router、Astro、Vue.js、Svelte 等），还有更多功能。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/deploying-nextjs-apps-to-cloudflare-workers-with-the-opennext-adapter/
    

**版本发布：**

- **🤖 openai-node v4.94** —— OpenAI 的官方 Node 库增加了对其最新的仅 API 版 GPT 4.1 模型的支持。

- **🕒 Spacetime v7.9** —— 轻量级时区库。现在支持SQL ISO 格式的时间格式化。

- **xero-node v11.0** —— 流行的 Xero 会计系统的 Node SDK。

- **Tesseract.js v6.0.1** —— 支持 100 多种语言的纯 JS OCR 工具。

- **Javet v4.1.2** —— 将 Node.js 和 V8 嵌入到 Java 中。