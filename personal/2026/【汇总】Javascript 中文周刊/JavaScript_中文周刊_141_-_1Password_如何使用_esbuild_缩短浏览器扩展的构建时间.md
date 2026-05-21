# JavaScript 中文周刊 #141 - 1Password 如何使用 esbuild 缩短浏览器扩展的构建时间

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532122&idx=1&sn=b4ccb3b0c0715c5b8cd8c5a4c1e827b9&chksm=e92135b8de56bcae99d7b5094fdb0985920d82feb8d4df8a9a6fd3530f01fad0fbb1ad7f1117\#rd  
> 抓取时间: 2026/2/2 23:51:01

---

> 本期看点：1Password 是一个流行的密码管理工具，它依赖浏览器扩展在网页上填写密码。在此之前，每次构建都会超过一分钟，这让开发人员的工作变得拖沓。esbuild 能帮助解决这个问题吗？本期介绍的文章分享了一个有趣的故事，包含了大量技术细节。

> 编辑：Yucohny、TimLi

🔥 本周热门

**1Password 如何使用 esbuild 缩短浏览器扩展的构建时间** —— 1Password 是一个流行的密码管理工具，它依赖浏览器扩展在网页上填写密码。在此之前，每次构建都会超过一分钟，这让开发人员的工作变得拖沓。esbuild 能帮助解决这个问题吗？这篇文章分享了一个有趣的故事，包含了大量技术细节。

**长按识别二维码查看原文**

https://blog.1password.com/new-extension-build-system/

Jarek Samic

**Next.js 15 候选版发布** —— 这个流行的 React 元框架即将迎来一次重要的新版本发布，候选版让你有机会尝试支持 React 19 与 React Compiler、在响应之后执行代码的 `next/after`，以及一些可能的破坏性变化。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15-rc

Delba de Oliveira 与 Zack Tanner

**aem1k：各种 JavaScript 技巧和创意编程** —— 这是一个有趣的项目。Martin 通过他的项目集合，真正捕捉到了 JavaScript 和 Web 的乐趣和表现力，包括提供一个将 JavaScript 转换为仅六个字符的 NSFW 命名工具，用 1KB 的 JavaScript 代码渲染一个 旋转地球，用 176 字节的代码实现 生命游戏，以及其他类似的项目。

**长按识别二维码查看原文**

https://aem1k.com/

Martin Kleppe

**快讯：**

- JavaScript 的创始人 Brendan Eich 在 Twitter/X 上 否认了 JavaScript 是“最糟糕”的说法，称它只是 50% 糟糕……
    
    **长按识别二维码查看原文**
    
    https://x.com/BrendanEich/status/1795865137317908739
    

- 如果你还没有深入研究过 JSR，那么可以看看 ▶️ Ryan Dahl 在 DevWorld 2024 的演讲。
    
    **长按识别二维码查看原文**
    
    https://jsr.io/
    

- Three.js 推出了 自己的 TSL 着色器语言，这是一种用 JavaScript 而不是 WebGPU 着色语言编写 WebGPU 着色器的方法。
    
    **长按识别二维码查看原文**
    
    https://github.com/mrdoob/three.js/wiki/Three.js-Shading-Language
    

📒  教程与趣事

**2024 年开始使用的 10 个现代 Node.js 运行时功能** —— 如果你觉得新功能的焦点太过集中在 Bun 或 Deno 上，不必担心——Node.js 也在快速前进。Liran 介绍了许多新功能。

**长按识别二维码查看原文**

https://snyk.io/blog/10-modern-node-js-runtime-features/

Liran Tal

**ECMAScript 2023 功能：作为 WeakMap 键的 Symbol** —— Dr. Axel 在文中解释了 WeakMap 的用途以及为什么使用 Symbol 作为键具有附加优势。

**长按识别二维码查看原文**

https://2ality.com/2024/05/proposal-symbols-as-weakmap-keys.html

Dr. Axel Rauschmayer

**▶ uBlock Origin：让我们阅读代码** —— 一位多产的代码阅读者花时间深入研究几乎完全用 JavaScript 构建的流行广告拦截器。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=L8wGnaFM_Kw

Ants Are Everywhere

**为什么需要标准的 JavaScript ORM 处理 SQL 数据库** —— 这就是 Drizzle 吗？

**长按识别二维码查看原文**

https://thenewstack.io/why-we-need-a-standard-javascript-orm-for-sql-databases/

Paul Scanlon（The New Stack）

**想摆脱 React 的复杂性？试试 Vue 吧** —— 如果你还没有尝试过 Vue，这篇高水平的文章可能会提供一些背景信息。

**长按识别二维码查看原文**

https://thenewstack.io/want-out-of-react-complexity-try-vues-progressive-framework/

Richard MacManus（The New Stack）

**📄 为什么还没有 JavaScript 版的 Laravel**

**长按识别二维码查看原文**

https://wasp-lang.dev/blog/2024/05/29/why-we-dont-have-laravel-for-javascript-yet

Vince Canger（Wasp）

**📄 Next.js 变得越来越难用了**

**长按识别二维码查看原文**

https://www.propelauth.com/post/nextjs-challenges

Andrew Israel

**📄 使用 HTML 的** `**<dialog>**` **在 React 中创建模态框**

**长按识别二维码查看原文**

https://spacejelly.dev/posts/how-to-create-a-modal-in-react-with-html-dialog

Colby Fayock

**📄 Angular 18 中的新功能**

**长按识别二维码查看原文**

https://www.angularaddicts.com/p/whats-new-in-angular-18

Gergely Szerovay

🛠  代码与工具

**Regexper：将 JavaScript 正则表达式显示为铁路图** —— 学习正则表达式时，或者当你有一个复杂的正则表达式却不知道它的作用时，这个工具可能会派上用场，这种情况并不少见……

**长按识别二维码查看原文**

https://regexper.com/

Jeff Avallone

**Hono v4.4：适用于任何环境的标准 JavaScript Web 应用程序框架** —— Hono 是一个小型、快速的 web 框架，具有简单明了的 API、支持中间件，并且几乎可以在任何平台上运行（Deno、Bun、Node 以及 Cloudflare 等）。v4.4 将其引入 JSR，增加了超时中间件和一个获取连接客户端信息的助手。

**长按识别二维码查看原文**

https://github.com/honojs/hono/releases/tag/v4.4.0

Yusuke Wada 与贡献者

**Inertia.js v1.1：为任何后端构建单页应用程序** —— Inertia 作为各种前端库（如 React、Vue 或 Svelte）和服务器端框架（如 Rails 或 Laravel）之间的“粘合剂”。

**长按识别二维码查看原文**

https://inertiajs.com/

Jonathan Reinink

**ShareDB v5.0：基于操作变换的实时数据库后端** —— 当你需要实时同步 JSON 文档时（例如用于实时协作应用程序）可以试试这个工具。

**长按识别二维码查看原文**

https://github.com/share/sharedb

ShareJS

**Qlock：一个 JavaScript 自复制时钟** —— 我们之前介绍过 Martin 的一系列创意 JavaScript 实验，但为什么不以一个特别有趣的例子来结束呢？这段 自复制程序 是不需要输入但能输出其自身源代码的程序。这里有一个有趣的 JavaScript 例子，它不仅是一个自复制程序，还是一个时钟。

**长按识别二维码查看原文**

https://aem1k.com/qlock/

Martin Kleppe

**版本发布：**

- **Rspack v0.7** – 快速的基于 Rust 的构建工具。

- **Storybook v8.1** – 前端组件工作台。

- **Deno v1.44**

- **PyMiniRacer v0.12.2** – 从 JavaScript 中调用 Python，再从你的 Python 中调用 JavaScript。

- **Knip v5.17.0** – 查找并删除未使用的文件、依赖项和导出，现在有了 更多功能。

- **PM2 v5.4** – 流行的基于 Node.js 的生产环境进程管理器。

- **Melange v4.0** – 为 JavaScript 开发者设计的 OCaml 编译器。

- **Neutralinojs v5.2** – 轻量级跨平台桌面应用框架。

- **Billboard.js v3.12** – 流行的图表库新增漏斗图。

- **Peaks.js v3.4** – BBC 创建的音频波形 UI 组件。

- **Happy DOM v14.12** – 无 UI 的 Web 浏览器 JavaScript 实现。

- **Retire.js v5.0** – 根据已知漏洞进行安全扫描的 JavaScript 库。

- **React Native Boilerplate v4.2** – RN 应用程序的入门模板。

- **RE:DOM v4.1** – 创建用户界面的微型库。

- **AlaSQL.js v4.4** – 同构 JavaScript SQL 数据库。

- **is-what v5.0** – 简单小巧的 JavaScript 类型检查函数库。

- **FxTS v1.0** – 函数式编程库。

🙋🏻‍♀️