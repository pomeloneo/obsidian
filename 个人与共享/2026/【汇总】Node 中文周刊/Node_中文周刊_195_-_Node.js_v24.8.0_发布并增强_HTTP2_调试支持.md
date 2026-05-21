# Node 中文周刊 #195 - Node.js v24.8.0 发布并增强 HTTP/2 调试支持

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543674&idx=1&sn=c2d3bab7277f2157af057c4963b70752&chksm=e9216098de56e98e704bc04e6f4b5788f09b3356fb6e0854e92a0cc39edba1daa60e9a74b2d5\#rd]http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543674&idx=1&sn=c2d3bab7277f2157af057c4963b70752&chksm=e9216098de56e98e704bc04e6f4b5788f09b3356fb6e0854e92a0cc39edba1daa60e9a74b2d5#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543674&idx=1&sn=c2d3bab7277f2157af057c4963b70752&chksm=e9216098de56e98e704bc04e6f4b5788f09b3356fb6e0854e92a0cc39edba1daa60e9a74b2d5#rd]http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543674&idx=1&sn=c2d3bab7277f2157af057c4963b70752&chksm=e9216098de56e98e704bc04e6f4b5788f09b3356fb6e0854e92a0cc39edba1daa60e9a74b2d5#rd)

---

> 本期看点：Node.js v24.8.0 发布并增加 Chrome DevTools 中检查 HTTP/2 网络调用的支持，pnpm v10.16 新增延迟依赖更新功能以防止恶意包，Express.js 5 生产环境配置指南发布，Feedsmith v2.0：Web Feed 解析和生成库。

> 编辑：TimLi

🔥 本周热门

**Node.js v24.8.0（当前版本）发布** —— 最大的新特性是增加了在 Chrome DevTools 中检查 Node 发起的 HTTP/2 网络调用的支持。此外还有一些加密相关的增强功能，并且 `npm` 升级到了 v11.6 版本。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.8.0

Michaël Zasso

**pnpm v10.16 新增延迟依赖更新支持** —— 这个高效的替代 npm 包管理器新增了一个功能，允许你为包依赖指定”最小发布时间”。比如设置为”1440”（分钟）意味着只会安装发布超过一天的包。这可以帮助避免那些很快就被撤回的恶意包版本。

**长按识别二维码查看原文**

https://pnpm.io/blog/releases/10.16

Zoltan Kochan

**又来了：关于 npm 供应链攻击的思考** —— 文章指出”npm 已经成为分发恶意软件最大且最容易的途径”，并将矛头指向了 npm 注册表的管理者 Microsoft。

**长按识别二维码查看原文**

[https://tane.dev/https://flaviocopes.com/the-nodejs-handbook-2025-edition//09/oh-no-not-again…-a-meditation-on-npm-supply-chain-attacks/](https://tane.dev/https://flaviocopes.com/the-nodejs-handbook-2025-edition//09/oh-no-not-again…-a-meditation-on-npm-supply-chain-attacks/)

Tane Piper

**[https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/](https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/) 年如何为生产环境配置 Express.js 5** —— 一篇关于最新版 Express 基础开发流程的教程，包含了 TypeScript、ESLint、Prettier、文件结构和日志记录等内容。

**长按识别二维码查看原文**

[https://www.reactsquad.io/blog/how-to-set-up-express-5-in-https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/](https://www.reactsquad.io/blog/how-to-set-up-express-5-in-https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/)

Jan Hesters

**使用 GitHub Actions 自动化桌面应用程序的发布流程** —— Dolt Workbench 是一个打包成 Electron 应用程序的 SQL 工作台，支持多个平台。Eric 解释了 Dolt 团队是如何自动化这个过程的，并分享了他们的 GitHub 工作流代码。

**长按识别二维码查看原文**

[https://www.dolthub.com/blog/https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/-09-11-automating-desktop-release-process/](https://www.dolthub.com/blog/https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/-09-11-automating-desktop-release-process/)

Eric Richardson（DoltHub）

📄 **如何控制好** `**package.json**` —— 这里有一些不错的建议和工具推荐。Tom MacWright

**长按识别二维码查看原文**

https://blog.val.town/gardening-dependencies

📄 **Node.js 中 QUIC 支持的现状** —— 回顾了为 Node 引入原生 QUIC 支持的多年历程，Node 25 将会获得第一个实现版本。Pavel Romanov

**长按识别二维码查看原文**

https://nodevibe.substack.com/p/state-of-quic-in-nodejs

📄 **在 TypeScript 和 React 中使用 Node 原生测试运行器** Matthew Brown

**长按识别二维码查看原文**

[https://matthewbrown.io/https://flaviocopes.com/the-nodejs-handbook-2025-edition//09/04/node-test-runner](https://matthewbrown.io/https://flaviocopes.com/the-nodejs-handbook-2025-edition//09/04/node-test-runner)

📄 **将多个 CSS 文件合并成一个** —— 使用 PostCSS 或无依赖的自定义 Node.js 脚本来实现。Geoff Graham

**长按识别二维码查看原文**

https://css-tricks.com/compiling-multiple-css-files-into-one/

**快讯：**

- ⚠️ 上周我们报道了一起重大的 npm 供应链攻击，影响了多个流行的包。但类似攻击仍在继续，这次受害的是 @ctrl/tinycolor 等包。这次的攻击特别危险，因为它会安装一个密钥扫描器并窃取发现的令牌。这里有更多技术细节。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/npm-author-qix-compromised-in-major-supply-chain-attack
    

- Electron 38 已发布，升级到了 Node 22.18，这意味着默认启用了类型剥离。它还从 Chromium 138 升级到了 140（对开发者来说这是个小更新）。
    
    **长按识别二维码查看原文**
    
    https://www.electronjs.org/blog/electron-38-0
    

- 📗 Flavio Copes 更新了他广受欢迎的 Node.js 手册，推出了 [https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/](https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/) 年版本。这本手册最初发布于 2018 年，现在仍然免费，但需要提供邮箱才能访问。
    
    **长按识别二维码查看原文**
    
    [https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/-edition/](https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-https://flaviocopes.com/the-nodejs-handbook-2025-edition/-edition/-edition/)
    

🛠 代码与工具

**Feedsmith v2.0：Web Feed 解析和生成库** —— 除了可以解析各种类型的 feed，还可以创建 RSS、Atom、JSON Feed 和 OPML 文件，支持多种常见命名空间（iTunes、Podcast、Media RSS、Dublin Core 等）。这里有一个快速入门教程，介绍了如何在浏览器或 Node 中使用它。GitHub 仓库。

**长按识别二维码查看原文**

https://feedsmith.dev/

Maciej Lamberski

**Trash v10.0：将文件和目录移到”回收站”** —— 与直接删除文件（如使用 `unlink`）不同，这个工具会将文件移动到 Windows、Linux 和 macOS 上的”回收站”。

**长按识别二维码查看原文**

https://github.com/sindresorhus/trash

Sindre Sorhus

**openapi-typescript-server：从 OpenAPI 生成 TypeScript 服务器代码** —— CLI 和运行时库，帮助你实现在 OpenAPI 规范中记录的类型安全 API。

**长按识别二维码查看原文**

https://github.com/jasonblanchard/openapi-typescript-server

Jason Blanchard

📢 其他生态快讯

以下是生态系统中其他一些有趣的故事：

- Bun 项目的 Lydia Hallie 写了一篇史诗级文章”深入解析 `bun install` 的内部原理”，不仅介绍了 Bun 如何让包安装机制变得更快，还详细讲解了包安装的整个过程和痛点。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/
    

- Deno 2.5 已发布。现在你可以在 `deno.json` 中创建权限集，`Deno.test` 获得了一些开发体验改进，`deno bundle` 新增了编程 API 让你可以通过脚本打包应用程序，此外还有很多其他更新。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v2.5
    

- 一位开发者满足了自己的好奇心，回答了哪个 npm 包的版本号最大这个问题。通过探索 npm 注册表的数据，根据如何定义”版本”和”最大”，得出了不同的答案。
    
    **长按识别二维码查看原文**
    
    https://adamhl.dev/blog/largest-number-in-npm-package/
    

- 有人想出了如何在一次性电子烟上托管网站。
    
    **长按识别二维码查看原文**
    
    https://bogdanthegeek.github.io/blog/projects/vapeserver/
    

**版本发布：**

- **Ow v3.0** —— 面向人类的函数参数验证（本质上是可链式调用的易读数据验证）。

- 🖼️ **terminal-image v4.0** —— 在终端中显示图片。v4 版本增加了对 Kitty 图形协议的支持。

- **npm-publish v4.0** —— 用于发布包到 npm 注册表的 GitHub Action。现在运行在 Node 24 和 `npm` 11 上。

- **jsdom v27.0** —— WHATWG DOM 和 HTML 标准的纯 JS 实现。

- **LogTape v1.1** —— 适用于所有主要 JS 运行时的简单日志库。更新日志。

- **Undici v7.16** —— Node 的强大 HTTP 客户端库。

- **Hexo v8.0** —— 流行的博客框架/生成器。

- **node-soap v1.4** —— SOAP 客户端和服务器库。