# JavaScript 中文周刊 #174 - Style Observer：监听 CSS 属性变化的新库

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539865&idx=1&sn=ffe81536cf7274972cd00642ec927e58&chksm=e921177bde569e6d9ffc7fe1c794427c8e758f8807137fb3becc075efdefb06778a9d3c2b2dd\#rd  
> 抓取时间: 2026/2/2 23:50:20

---

> 本期看点：Lea Verou 发布 Style Observer 库用于监听 CSS 属性变化，Anthony Fu 认为是时候转向纯 ESM 了，ECMAScript 正则表达式转义提案，Popover API 已成为所有主流浏览器的基础特性，如何使用 GitHub Copilot 重构代码。

> 编辑：TimLi

🔥 本周热点

**Style Observer：一个监听 CSS 属性变化的库** —— Lea Verou 是一位备受推崇的开发者，她每次解决问题都能提供完善的解决方案。这次她推出了一个经过充分测试的 JavaScript 库，用于监听 CSS 属性的变化，并妥善处理了各种浏览器兼容性问题。更多详情请查看项目主页（值得注意的是，.style 已成为新的顶级域名）。

**长按识别二维码查看原文**

https://lea.verou.me/blog/2025/style-observer/

Lea Verou

💡 Lea 还有许多其他优秀项目值得一看，比如 Color.js，这个库同样完美地解决了在 JavaScript 和浏览器中处理和操作颜色的问题。

**长按识别二维码查看原文**

https://lea.verou.me/projects/

**为什么要转向”纯 ESM”** —— 使用 ES 模块的趋势已经持续多年，如果你还在观望，可能是有自己的理由。虽然你可以维护同时支持 ESM 和 CommonJS 的包，但 Anthony 认为是时候完全转向 ESM 了，他在文章中解释了原因。

**长按识别二维码查看原文**

https://antfu.me/posts/move-on-to-esm-only

Anthony Fu

💡 说到这个话题，Sarah Gooding 写了一篇关于 `require(esm)` 已经被移植到 Node.js 20 并趋于稳定的文章，这让转向 ESM 的理由更加充分了。

**长按识别二维码查看原文**

https://socket.dev/blog/require-esm-backported-to-node-js-20

**快讯：**

- 🤔 行业分析师 Kate Holterhoff 质疑”npm 是否足够好”，并探讨为什么会有这么多项目试图替代或扩展 npm 包管理系统。
    
    **长按识别二维码查看原文**
    
    https://redmonk.com/kholterhoff/2025/01/30/is-npm-enough/
    

- 📱 React Native 团队发布了最近一次贡献者峰会的总结。React Native 开发者必读。
    
    **长按识别二维码查看原文**
    
    https://reactnative.dev/blog/2025/02/03/react-native-core-contributor-summit-2024
    

- Popover API 现已成为浏览器的”基础特性”，所有主流浏览器都提供了良好支持。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/popover-baseline
    

- 🤖 读者 Ishan Anand 正在开发一个完全在浏览器中运行的 GPT2（OpenAI 早期产品）实现，用于支持一些有趣的基于浏览器的电子表格数据处理实验。
    
    **长按识别二维码查看原文**
    
    https://spreadsheets-are-all-you-need.ai/gpt2/
    

📒 教程与趣事

**如何实现代码复制按钮及其重要性** —— 这是一个在网页上常见的功能，可以让读者更方便地获取分享的源代码。David Bushell 也写了一篇后续文章，分享了他在实现这个功能时的经验。

**长按识别二维码查看原文**

https://whitep4nth3r.com/blog/how-to-build-a-copy-code-snippet-button/

Salma Alam-Naylor

**ECMAScript 正则表达式转义提案** —— `RegExp.escape()` 是一个函数，可以将提供的文本转换为转义版本，使其在用作正则表达式或其一部分时能够精确匹配自身。Axel 还用纯 JavaScript 实现了一个版本，帮助理解其工作原理。

**长按识别二维码查看原文**

https://2ality.com/2025/01/regexp-escape.html

Dr. Axel Rauschmayer

**2025 年如何开始一个 React 项目** —— 虽然开始 React 项目的方式有很多，Robin 分析了几种流行方案的优缺点。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-starter/

Robin Wieruch

**学习如何构建现代浏览器扩展** —— 在开发浏览器扩展时，很容易遇到过时的文档。幸运的是，Hui 已经走过这个过程，并分享了一些技巧。

**长按识别二维码查看原文**

https://chenhuijing.com/blog/learning-web-extensions/#%F0%9F%8E%99

Hui Jing

**测试 10 个 JavaScript 框架的 HTML 默认输出** —— 现在使用 JavaScript 框架已经成为许多网站开发者的首选方式，但这些流行框架在生成有效、无错误的 HTML 方面表现如何呢？

**长按识别二维码查看原文**

https://meiert.com/en/blog/javascript-framework-html-defaults/

Jens Oliver Meiert

📄 **使用** `**Intl.DurationFormat**` **实现本地化的时长显示** Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2025/02/13/using-intldurationformat-for-localized-durations

📄 **如何使用 GitHub Copilot 重构代码** Anthony Grutta（GitHub）

**长按识别二维码查看原文**

https://github.blog/ai-and-ml/github-copilot/how-to-refactor-code-with-github-copilot/

📄 **在 Vue.js 应用程序中使用 RxDB 作为数据库** RxDB

**长按识别二维码查看原文**

https://rxdb.info/articles/vue-database.html

📄 **支持向浏览器粘贴文件** Fileber

**长按识别二维码查看原文**

https://docs.fileber.com/blog/pasting-files-into-browser

🛠 代码与工具

**Ohm：JavaScript 和 TypeScript 的解析工具包** —— 这是一个基于 PEG（Parser Expression Grammar，解析器表达式语法）的解析器库，可用于构建解释器、编译器、分析工具等。您可以通过在线编辑器体验其语法功能。

**长按识别二维码查看原文**

https://ohmjs.org/

Warth、Dubroy 等

**Human Regex：使用英语语法的人性化正则表达式构建器** —— 虽然我用了 8 年 Perl 后已经和正则表达式成为好朋友，但大多数开发者并不喜欢它。这个库提供了一种自然、流畅的方法。你也可以考虑使用 Magic Regexp 和 Super Expressive 这样的替代方案。

**长按识别二维码查看原文**

https://github.com/rajibola/human-regex

Ridwan Ajibola

**Svader：创建 GPU 渲染的 Svelte 组件** —— 查看示例可以更好地了解它提供的功能。

**长按识别二维码查看原文**

https://github.com/sockmaster27/svader?ck_subscriber_id=887809557

Holger Dal Mogensen

**web-worker v1.5：为浏览器和 Node 提供一致的 Web Workers API** —— 如果您需要发布同时支持 Node 和客户端的 Web Workers npm 模块，这个工具可能会对您有所帮助。在 Node 环境中，它基于 `worker_threads` 提供了一个与 Web 标准兼容的 Worker 实现；在浏览器中，它则是原生 `Worker` 的别名。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/165813/web

Jason Miller

**我一直想要的 React 数据表格** —— 深入了解一个基于 **shadcn/ui** 的特别快速和整洁的数据表格组件（GitHub 仓库）。查看在线演示。

**长按识别二维码查看原文**

https://www.openstatus.dev/blog/data-table-redesign

Maximilian Kaske

🔠 字体小彩蛋

**GitHub 扩展了其 Monaspace 字体系列** —— Monaspace 是 GitHub 推出的一套针对编程场景的出色等宽字体。最新的 v1.2 版本更进一步，增加了对 Nerd Fonts 的支持和符号、新的方框绘制字形、字符、字符变体、连字等。

**长按识别二维码查看原文**

https://github.com/githubnext/monaspace/releases/tag/v1.200

GitHub

**版本发布：**

- **Node.js v23.8.0（当前版本）** 和 **Node.js v22.14.0（LTS）**

- **Node.js v20.18.3（LTS）** —— import 属性和 JSON 模块的向后移植现已稳定。

- **pnpm v10.3** —— 这个快速、高效的包管理器新增了 `strict-dep-builds` 选项，当依赖项有未经审查的构建脚本时会返回非零退出码。

- **Pixi.js v8.8** —— 快速、灵活的 2D WebGL 渲染器。

- **Astro v5.3**、**Prettier v3.5**、**Electron v34.2**

- **Kaluma v1.2** —— 为 RP2040（树莓派 Pico）设计的轻量级 JavaScript 运行时。

- **bcrypt.js v3.0** —— 纯 JavaScript 实现的优化版 bcrypt，可在浏览器中运行。

- **Jasmine v5.6** —— 适用于浏览器和 Node 的测试框架。

- **Midscene.js v0.11** —— 让 AI 成为你的浏览器操作员。