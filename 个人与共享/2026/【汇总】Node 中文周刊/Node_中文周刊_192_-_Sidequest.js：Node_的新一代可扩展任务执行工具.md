# Node 中文周刊 #192 - Sidequest.js：Node 的新一代可扩展任务执行工具

> 原文链接: [](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543208&idx=1&sn=2196f795420ea05ff45c47236621a053&chksm=e921624ade56eb5cd2e8ca52192fbbccffb962373f8c876547e7b76ac4156881b83317fe2821#rd)[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543208&idx=1&sn=2196f795420ea05ff45c47236621a053&chksm=e921624ade56eb5cd2e8ca52192fbbccffb962373f8c876547e7b76ac4156881b83317fe2821#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543208&idx=1&sn=2196f795420ea05ff45c47236621a053&chksm=e921624ade56eb5cd2e8ca52192fbbccffb962373f8c876547e7b76ac4156881b83317fe2821#rd): 2026/2/2 23:51:21

---

> 本期看点：Sidequest.js 发布新一代可扩展 Node 后台任务处理器，Node.js v24.6.0 发布并支持系统证书和 Zstd 字典，Cloudflare Workers 即将支持 Express 应用程序，LooksSame：图片视觉对比库。

> 编辑：TimLi

🔥 本周热门

**Sidequest.js：Node 的新一代可扩展任务执行工具** —— 这是一个现代化的、可扩展的 Node 后台任务处理器，包含基于 Web 的仪表盘，支持多种后端存储，并且对 TypeScript 支持友好。GitHub 仓库。**使用 LGPL 3.0 许可证。**

**长按识别二维码查看原文**

https://sidequestjs.com/posts/intro-to-sidequest/

Merencia 和 Guizzo

**Node.js v24.6.0（当前版本）发布** —— 这是一个相对较小的更新。Node 24.6 允许你通过设置 `NODE_USE_SYSTEM_CA` 环境变量（类似于 `--use-system-ca`）来使用系统的受信任证书，`zlib` 增加了 Zstd 字典支持，`http` 为服务器添加了 `keepAliveTimeoutBuffer` 选项。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.6.0

Rafael Gonzaga

**Cloudflare Workers 即将支持 Express 应用程序** —— 虽然现在已经有像 Hono 这样的工具可以在不同运行时环境中快速构建类似 Express 的 Web 应用程序，但 Express 仍然是目前最受欢迎的选择。所以看到边缘平台 Cloudflare Workers 直接支持它是一个好消息——不过目前仅支持本地开发。

**长按识别二维码查看原文**

https://jross.me/run-express-js-on-cloudflare-workers/

James Ross

💡 相关新闻：AWS Lambda 现在支持使用 GitHub Actions 来简化函数部署，这样当你推送代码时，就可以快速部署。

**长按识别二维码查看原文**

https://aws.amazon.com/about-aws/whats-new/2025/08/aws-lambda-github-actions-function-deployment/

**📄 Shopify Webhook 解析错误导致数据库被删除的经验教训** —— 一个意外的 `undefined` 值传入 Prisma 引发的问题。不过 Prisma 的验证错误确实捕获到了这个问题。Ingressr

**长按识别二维码查看原文**

https://www.ingressr.com/blog/webhook-security-incident-analysis/

**📄 npm 在 CI/CD 工作流中采用 OIDC 实现可信发布** —— 深入了解 npm 的最新功能：使用 OpenID Connect 在 CI/CD 工作流中实现 npm 包的”可信发布”。Sarah Gooding (Socket)

**长按识别二维码查看原文**

https://socket.dev/blog/npm-trusted-publishing

**📄 理解 Node.js 中的火焰图** Lizz Parody (NodeSource)

**长按识别二维码查看原文**

https://nodesource.com/blog/understanding-flame-graphs-in-nodejs

**快讯：**

- 👋 Node 官方网站现在有了一个专门解释”生命周期结束”（EOL）流程的页面，说明了版本进入 EOL 后可能出现的问题，以及不同 Node 版本的当前状态。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/eol
    

- 如果你在 Vercel 上托管了很多 Node 项目，一直担心需要一个一个地升级，现在你可以在 Vercel 上批量升级过时的 Node.js 版本了。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/bulk-upgrade-deprecated-node-js-versions
    

- Oxlint 现在预览版支持类型感知的代码检查。
    
    **长按识别二维码查看原文**
    
    https://oxc.rs/blog/2025-08-17-oxlint-type-aware
    

🛠 代码与工具

**🖼️==🖼️? LooksSame：图片视觉对比库** —— 这个库是为视觉回归测试而设计的，它考虑了人类的色彩感知，因此比较灵活，不仅仅是精确的像素对比。**（注意：为了避免引入大型依赖，仅支持 PNG 格式。）**

**长按识别二维码查看原文**

https://github.com/gemini-testing/looks-same

Yandex 和贡献者们

**zx v8.8：用 Node.js 编写更好的 Shell 脚本** —— 这是一个流行的工具，它让 Shell 脚本编写变得更愉快，为 `child_process` 提供了有用的封装，支持参数转义，并有合理的默认值。v8.8 改进了 zx 的管道功能。（文档）

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/8.8.0

Google

**Pyodide：编译到 WebAssembly 的 Python** —— 这是一个将 CPython 移植到 WebAssembly 的项目，可以在浏览器中使用，也可以在 Node.js 中使用。例如，你可以在 Node 应用程序中导入 Pyodide，然后在其中运行 Python 代码。

**长按识别二维码查看原文**

https://pyodide.org/en/stable/index.html

Pyodide 贡献者和 Mozilla

**QuickJS Sandbox v3.0：在 QuickJS 驱动的沙箱中执行 JS/TS** —— QuickJS 是 Fabrice Bellard 开发的一个小型、可嵌入的 JavaScript 引擎，这个项目对其进行了扩展，使其易于在隔离的沙箱环境中运行代码，并提供了一些基本的 Node 模块支持和虚拟文件系统。GitHub 仓库。

**长按识别二维码查看原文**

https://sebastianwessel.github.io/quickjs/

Sebastian Wessel

**🤖 YIKES：基于 LLM 的文字冒险游戏引擎** —— 虽然还处于早期阶段，但 LLM 为这个经典游戏类型带来了一些有趣的机会。

**长按识别二维码查看原文**

https://github.com/psema4/yikes

Scott Elcomb

📢 其他

以下是生态系统中其他一些有趣的故事：

- 📺 TC39 的 Daniel Ehrenberg 参与了▶️ 一个精彩的 47 分钟访谈，他讲述了 TC39 委员会的工作方式，以及**你**如何能为 JavaScript 的未来发声。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=v9Al9-0jkoQ
    

- 🏎️ Ryan Skinner 展示了 Rari，这是一个用 Rust 驱动的后端替代 Node.js 来渲染 React 服务器组件的示例，并展示了显著的性能提升。
    
    **长按识别二维码查看原文**
    
    https://ryanskinner.com/posts/how-i-built-a-full-stack-react-framework-4x-faster-than-nextjs-with-4x-more-throughput
    

- Simon Willison 展示了如何使用 devcontainers 配置 GitHub Codespaces，同时运行最新的 Python 和 Node.js LTS 版本。
    
    **长按识别二维码查看原文**
    
    https://til.simonwillison.net/github/codespaces-devcontainers
    

- Git 2.51 刚刚发布，GitHub 分享了这个版本的一些亮点。
    
    **长按识别二维码查看原文**
    
    https://github.blog/open-source/git/highlights-from-git-2-51/
    

- Dr. Axel Rauschmayer 为初学者编写了一份简单的 JavaScript 数组入门指南。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/08/javascript-arrays.html
    

- jQuery 4.0 RC 1 已经发布！
    
    **长按识别二维码查看原文**
    
    https://blog.jquery.com/2025/08/11/jquery-4-0-0-release-candidate-1/
    

**版本发布：**

- **NVM Desktop v4.1** —— 一个用于管理多个活动 Node 版本的桌面应用程序（支持 macOS、Windows 和 Linux）。

- **fdir v6.5** —— 高性能目录爬虫和 glob 库。现在提供 ESM 构建。

- **Ghost v6.0** —— 基于 Node.js 的独立发布和博客平台。

- **Fastify v5.5** —— 快速、低开销的 Node Web 框架。

- **CryptoES v3.0** —— 加密算法库。

- **Prisma v6.14** —— 下一代 Node.js + TypeScript ORM。

- **Undici v7.14** —— Node 的强大 HTTP 客户端库。

- **node-soap v1.3** —— SOAP 客户端**和**服务器库。

- **Strong SOAP v5.0** —— 带有模拟服务器功能的 SOAP 客户端。是 node-soap 的重写版本。

- **ESLint v9.33.0**