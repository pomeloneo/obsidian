# Node 中文周刊 #165 - NodeBB v4.0.0 引入联邦功能

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539381&idx=1&sn=b2693b2898eb6f8e18fc0e62a608ea76&chksm=e9211157de56984119deba2784de32a557a14eb749d06fcc3273d23195800c06bcb61155bb45\#rd  
> 抓取时间: 2026/2/2 23:51:54

---

> 本期看点：NodeBB v4.0.0 发布并加入联邦宇宙，Node.js 多个版本线发布安全更新，npm 仓库发现针对 Chalk 和 Chokidar 的恶意包名仿冒，ArkType v2.0 推出优化的运行时验证方案，NestJS 发布 v11.0 重大更新并升级至 Express v5。

> 编辑：TimLi

🔥 本周热门

**NodeBB v4.0.0 发布：基于 Node.js 的论坛系统** —— NodeBB 已经走过近 12 个年头，继续以现代 Node.js 的方式提供经典的论坛体验。v4 版本最大的更新是支持联邦功能，实现了 NodeBB 实例之间以及与更广泛的联邦宇宙（fediverse）的互联。值得注意的是，这个开源项目（代码仓库）采用 GPL 许可证，而 NodeBB Inc 则提供托管服务。

**长按识别二维码查看原文**

https://community.nodebb.org/topic/18545/nodebb-v4.0.0-federate-good-times-come-on

NodeBB, Inc.

**2025 年 1 月 21 日安全更新发布** —— Node 23.x、22.x、20.x 和 18.x 版本即将推出新的更新，以解决一些尚未公开的安全问题。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/january-2025-security-releases

The Node.js Project

**TypeScript 枚举：使用场景与替代方案** —— 深入探讨 TypeScript 中一个没有直接 JavaScript 对应物的特性（因此在 Node 的类型擦除方法中无法保留，不过你可以使用 `--experimental-transform-types` 或 tsx）。

**长按识别二维码查看原文**

https://2ality.com/2025/01/typescript-enum-patterns.html

Dr. Axel Rauschmayer

**npm 包中发现针对 Chalk 和 Chokidar 的包名仿冒（typosquatting）和隐藏开关** —— 最新研究发现多个恶意包通过 包名仿冒（typosquatting）方式冒充终端字符串样式库 Chalk 和文件监控库 Chokidar，针对 Node 开发者实施安全攻击。

**长按识别二维码查看原文**

https://socket.dev/blog/kill-switch-hidden-in-npm-packages-typo-squatting-chalk-and-chokidar

Kush Pandya (Socket)

**📄** `**Promise.race**` **和** `**Promise.all**` **并非”公平”** —— 也就是说，它们存在偏差，并不完全随机。Chris Krycho

**长按识别二维码查看原文**

https://v5.chriskrycho.com/notes/javascript-promise-race-and-promise-all-are-not-fair/

**📄 Node、Bun 和 Deno 中的 Fetch 和 HTTP/2 支持** —— Georges Haidar

**长按识别二维码查看原文**

https://blog.disintegrator.dev/posts/http2-support-in-js-runtimes/

**快讯：**

- 流行的 NestJS 框架 发布了 11.0 版本。我们正在等待完整的博客文章，但这似乎是一次重大更新（现在使用 Express v5）。这里有一份 v10 到 v11 的迁移指南。
    
    **长按识别二维码查看原文**
    
    https://nestjs.com/
    

- Vercel 将在 2025 年 8 月 1 日停止支持 Node v18。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-18-is-being-deprecated
    

- GitHub 的 Dependabot（自动依赖更新系统）不再支持 npm 6，要求使用 npm 9 或更高版本。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-01-20-dependabot-will-no-longer-support-npm-v6/
    

🛠 代码与工具

**ArkType v2.0：运行时验证库** —— 这是一个易于部署的模式验证解决方案，可以 1:1 推断 TypeScript 定义，并将其用作优化的数据验证器，既可以在运行时使用，也可以在编辑器中提供即时类型反馈。

**长按识别二维码查看原文**

https://arktype.io/docs/blog/2.0

ArkType

**react-nil v2.0：React “空渲染器”** —— 一个有趣的实验，用于在不需要渲染任何内容但想要使用 hooks、suspense、context 和其他 React 生命周期功能的场景中使用 React，比如在 Node 应用程序中。

**长按识别二维码查看原文**

https://github.com/pmndrs/react-nil

Poimandres

**Electron v34.0.0** —— 这个使用 JS、HTML 和 CSS 构建桌面应用程序的框架更新到了 Chromium 132、Node 20.18.1，并添加了访问无响应渲染器 JavaScript 调用栈的方法。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-34-0

Electron Team

**file-type v20.0：检测 Buffer、Uint8Array 或 ArrayBuffer 的文件类型** —— 例如，给它一个 PNG 文件的原始数据，它会告诉你这是一个 PNG 文件。使用”魔数”方法，专门针对非文本格式。v20 版本增加了对更多格式的支持，包括 JAR、Word/Excel 模板，现在还支持 ZIP 解压缩。

**长按识别二维码查看原文**

https://github.com/sindresorhus/file-type

Sindre Sorhus

📢 其他 JavaScript 相关

以下是一些你可能错过的 JavaScript 生态圈其他有趣新闻：

- Learn Yjs 是一个仍在开发中的优秀教程集，用于学习如何使用 Yjs CDRT 库构建实时协作应用程序。
    
    **长按识别二维码查看原文**
    
    https://learn.yjs.dev/
    

- Bun 的最新版本在其 `Bun.serve()` 功能中添加了按需前端打包。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.1.44
    

- 如果你还没有使用过 WASM，Hemath 提供了一个易于理解的 WebAssembly 基础入门。
    
    **长按识别二维码查看原文**
    
    https://hemath.dev/blog/webassembly/introduction-to-webassembly/
    

- 流行的 Astro 框架发布了 2024 年度回顾。
    
    **长按识别二维码查看原文**
    
    https://astro.build/
    

- Google 已经开始要求用户在搜索时启用 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://techcrunch.com/2025/01/17/google-begins-requiring-javascript-for-google-search/
    

**版本发布：**

- **😀 Happy DOM v16.7** —— 跨运行时的 Web 浏览器 JS 实现（不含 UI）。现在支持模拟本地 HTTP 服务器，可以从本地文件系统提供文件。

- **better-sqlite v11.8** —— 在 Node 中使用 SQLite 的优秀方式。现在支持 SQLite 3.48.0。

- **Faker v9.4** —— 随心所欲地生成虚拟数据。

- **🎶Ableton.js v3.6** —— 从 Node 控制 Ableton DAW 实例。

- **Nightwatch.js v3.11** —— Node.js 端到端测试框架。

- **pg-diff v3.0** —— PostgreSQL 架构和数据比较工具。

- **qs v6.14** —— 查询字符串解析和字符串化库。

- **YouTube.js v13.0** —— YouTube 私有 API 的 JS 客户端。

- **Commander.js v13.1** —— Node.js CLI 应用程序框架。