# JavaScript 中文周刊 #191 - 2025 年 React 现状与社区观察

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542089&idx=1&sn=a39d9e8dd3ec02e864459608decfdf70&chksm=e9216eabde56e7bd25bd16617b08f9155cbca8e6a9fe4f009e524f89496ca9c66e0388450f25\#rd  
> 抓取时间: 2026/2/2 23:49:58

---

> 本期看点：Redux 维护者 Mark Erikson 带来 2025 年 React 现状与社区观察，Oxlint v1.0 发布，pnpm v10.12 推出实验性全局虚拟存储，npmgraph：可视化 npm 依赖关系的工具，Odyc.js：像素风游戏/故事的 JS 库。

> 编辑：TimLi

🔥 本周热点

**2025 年 React 现状与社区观察** —— React 依然是 JavaScript 生态里最重要的依赖之一，但最近各种新特性和创新也引发了不少关于未来方向的讨论。Redux 维护者 Mark Erikson 这次带来了 React 发展历程的梳理，讲了讲这些创新背后的原因，还专门澄清了一些关于 React 未来的 FUD 和误解。

**长按识别二维码查看原文**

https://blog.isquaredsoftware.com/2025/06/react-community-2025/

Mark Erikson

**Oxlint v1.0 发布：超快的 Linter 工具** —— Oxlint 诞生才 18 个月，就凭借 **极致的速度** 在 JavaScript 和 TypeScript 社区刷足了存在感。它基于 Rust，性能比 ESLint 快 50~100 倍，同时还兼容了数百条 ESLint 规则。现在，Oxlint 终于迎来稳定版。

**长按识别二维码查看原文**

https://voidzero.dev/posts/announcing-oxlint-1-stable

Boshen Chen 和 Cameron Clark

**pnpm v10.12 推出实验性全局虚拟存储** —— pnpm 一直以速度和高效著称，远超 `npm`。这次 v10.12 更进一步，带来了“全局虚拟存储”，让 `node_modules` 通过软链接共享依赖，多个项目不用重复安装同样的包，省时省空间。

**长按识别二维码查看原文**

https://socket.dev/blog/pnpm-introduces-global-virtual-store-and-expanded-version-catalogs

Sarah Gooding (Socket)

**快讯：**

- **Surfin’ Safari?** 本周 Apple 的 WWDC25 发布会带来了不少新东西，除了“液态玻璃”之外，Safari 26（beta） 也有新特性，比如 `RegExp` 对象支持模式修饰符。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/16993/news-from-wwdc25-web-technology-coming-this-fall-in-safari-26-beta/
    

- OpenPGP.js 被曝出一个漏洞，有兴趣的可以看看分析。
    
    **长按识别二维码查看原文**
    
    https://codeanlabs.com/blog/research/cve-2025-47934-spoofing-openpgp-js-signatures/
    

- Matteo Collina 发布了关于部分 Node.js 版本即将 EOL 的提醒，并给出升级到 v22 的建议。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/announcements/node-18-eol-support
    

- Gleam 是一门面向 Erlang 和 JS 运行时的易读易写语言。最近大新闻是 Gleam 编译到 JS 后性能提升了 30%！
    
    **长按识别二维码查看原文**
    
    https://gleam.run/
    

📖 文章和视频

**Suppressions of Suppressions** —— 你用 linter 保持代码整洁时，可能会把一些太严格或不相关的规则禁用掉。但这些“抑制”有时会让严重 bug 被埋没。Dan Abramov 建议：应该加一条规则，禁止禁用最关键的检查。

**长按识别二维码查看原文**

https://overreacted.io/suppressions-of-suppressions/

Dan Abramov

**回顾早期 JavaScript 代码** —— 虽然不是最早的 JS，但 Trevor 带你回顾 2006-2015 年（ES6 之前）那会儿的 JavaScript 代码风格。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/revisiting-legacy-javascript

Trevor I. Lasn

**Node 原生热模块重载的实现思路** —— 通过巧妙利用模块钩子（module hooks），可以高效地在 Node 里实现“热模块”功能，原生又实用。

**长按识别二维码查看原文**

https://immaculata.dev/blog/native-nodejs-hmr.html

Immaculata

**📺 别再盲目用** `**JSON.parse**` **和** `**JSON.stringify**` —— Jack 讲了这两个函数的局限和一些替代方案，值得一看。Jack Herrington

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=PtcQwb1uBhc

**📄 ESLint 语言插件如何提升 DSL 易用性** Nicholas C. Zakas

**长按识别二维码查看原文**

https://eslint.org/blog/2025/06/language-plugins-dsl-benefits/

**📄 JavaScript 里要避免的坑** —— 一些基础但容易踩的点，值得提醒。Suren Enfiajyan

**长按识别二维码查看原文**

https://waspdev.com/articles/2025-06-13/things-to-avoid-in-javascript

**📄 Angular 20 看起来无聊？其实有 6 个理由让它不无聊** Yan Sun

**长按识别二维码查看原文**

https://blog.logrocket.com/angular-v20-update/

🛠 代码与工具

**npmgraph：可视化 npm 依赖关系的工具** —— 这个 Web 工具只要输入一个或多个 npm 包名（甚至直接上传 `package.json`），就能帮你可视化这些包的依赖关系图，还能看到它们的交集。你可以按维护者数量等多种方式给包上色，还能下载 SVG 格式的依赖图。

**长按识别二维码查看原文**

https://npmgraph.js.org/

Kieffer、Brigante 等

**Jest 30：更快、更轻、更强的 JS 测试框架** —— 这个流行的测试框架迎来“明显更快”的新版本，带来了更好的 ESM 和 TypeScript 支持、性能提升等。想升级可以看官方文档。

**长按识别二维码查看原文**

https://jestjs.io/blog/2025/06/04/jest-30

Zaytsev & Nakazawa

**🍊 Orange ORM：面向 JavaScript 和 TypeScript 的 Active Record ORM** —— 适用于 Node、Bun 和 Deno，支持 TypeScript 和 JavaScript，兼容 CommonJS 和 ESM。它采用 Active Record 风格的查询方式，文档齐全，如果你用主流 SQL 数据库，值得一试。

**长按识别二维码查看原文**

https://orange-orm.io/

Lars-Erik Roald

**Vue Equipment：Nuxt 和 Vue.js 的工具包** —— 这里收集了一批现成可用的插件和组合式函数，帮你用 Vue 和 Nuxt 快速搭建现代 Web 应用程序。详细介绍看这里。

**长按识别二维码查看原文**

https://www.vue.equipment/

Magic as a Service

**🌓 DarkModeJS v2.0：管理暗黑模式的小工具包** —— 利用 `matchMedia` API 和 `prefers-color-scheme` 媒体查询，能在用户切换暗黑模式时自动触发函数。

**长按识别二维码查看原文**

https://github.com/Assortment/darkmodejs

Assortment

**🕹️ Odyc.js：像素风游戏/故事的 JS 库** —— 有点 Game Boy Color 的 8-bit 复古风。你可以用它做小游戏，也可以在在线 playground 里试试官方示例。

**长按识别二维码查看原文**

https://odyc.dev/

Charles Cailleteau

👀 其他

本周还有这些值得关注的生态圈动态：

- GitHub 上的第 10 亿个仓库（名字有点 NSFW，慎点）刚刚被创建，社区一片欢腾。
    
    **长按识别二维码查看原文**
    
    https://github.com/AasishPokhrel/shit/issues/1
    

- Shopify 介绍了他们让 import maps 更易用的探索， 包括 shim、HTML 规范和推动浏览器厂商改进等。
    
    **长按识别二维码查看原文**
    
    https://shopify.engineering/resilient-import-maps
    

- GitHub 的远程 MCP 服务器 现已公测，AI 工具和代理可以实时访问 GitHub 上的 issues、PR 等上下文，做自动化操作。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-06-12-remote-github-mcp-server-is-now-available-in-public-preview/
    

- 你可能还记得 TypeScript 团队正在用 Go 重写 TypeScript 编译器，以获得原生编译速度和 Go 的并发优势。John Reilly 和 Ashley Claymore 详细解释了为什么 Go 是“务实之选”。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/typescript-native-port/
    

**版本发布：**

- **H3 v2 Beta** —— 跨运行时、专注 Web 标准的 HTTP 服务器框架。

- **Node.js v24.2（Current）** —— ES 模块里新增了 `import.meta.main`，可以判断当前模块是不是主入口。

- **Visual Studio Code 2025 年 5 月版** —— MCP 支持大升级，而且 VS Code 扩展现在也能用 ES 模块了。

- **Deno v2.3.6**、**Rollup v4.43**、**Jasmine v5.8**、**Vue DevTools v7 for Firefox**

- **Midscene.js v0.18** —— 让 AI 和 JavaScript 一起帮你自动操作浏览器。

- **Acorn v8.15** —— 小巧、快速的 JavaScript 解析器。

- **xo v1.1** —— 有主见但可配置的 ESLint 封装工具。

- **Mocha v11.6** —— Node 和浏览器通用的测试框架。

- **JsBarcode v3.12** —— 条形码生成库。