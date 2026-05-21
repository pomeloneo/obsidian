# JavaScript 中文周刊 #149 - Astro 4.12、ECMAScript 2024 和 Node v22.5.0

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533735&idx=1&sn=5c859ee49010c59773e77d5a39ba1647&chksm=e9210f45de568653387c288c4dcf61951bdbd06cddd1dbfbc92d822b42d36faf09ee06da991f\#rd  
> 抓取时间: 2026/2/2 23:50:51

---

> 本期看点：Astro 4.12 发布，支持 Server Islands；ECMAScript 2024 的新特性；Node v22.5.0 发布，修复了两个问题。

> 编辑：TimLi、Jojo

🔥 本周热门

**Astro 4.12：向服务器岛屿说 Hello** —— 用于构建现代内容为基础网站的灵活 Astro 框架继续不断发展壮大。v4.12 包括了一个新概念：服务器岛屿，这是一种将静态 HTML 和服务器端生成的组件整合在一起的方式。

**长按识别二维码查看原文**

https://astro.build/blog/astro-4120/

Erika and Phillips (Astro)

**ECMAScript 2024 为 JavaScript 开发者带来了什么新内容** —— 对 ECMAScript 规范中的发展进行高层次分析，包括来自 Ecma 副主席 Daniel Ehrenberg、TC39 联席主席 Rob Palmer 和开发者 Ashley Claymore 的见解。这是一个很好、很全面的现状概述。

**长按识别二维码查看原文**

https://thenewstack.io/whats-new-for-javascript-developers-in-ecmascript-2024/

Mary Branscombe (The New Stack)

💡 如果你想进一步了解即将到来的内容，Igalia 提供了关于最近在赫尔辛基举行的 TC39 会议的总结，其中介绍了哪些语言提案得到推进和讨论。

**长按识别二维码查看原文**

https://blogs.igalia.com/compilers/2024/07/18/summary-of-the-june-2024-tc39-plenary-in-helsinki/

**Node v22.5.0 崩溃的事后分析** —— Node.js 的”Current”发布线提供了最新的 Node.js 版本，但也可能会遇到一些麻烦的 bug —— 不幸的是，v22.5 版本中出现了两个问题，但很快发布了 Node v22.5.1 来解决这些问题。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/53934

Yagiz Nizipli 等人

**快讯：**

- Rich Harris 提供了关于即将到来的 Svelte 5 的一些细节，并分享了他对 React Server Components 的看法（他认为它们”相当了不起”）。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/youll-write-less-code-with-svelte-5-0-promises-rich-harris/
    

- Node.js 已添加了一个实验性功能，可以从其运行的代码中剥离 TypeScript 类型。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/pull/53725
    

- 📊 《State of React 2023》调查的结果已发布，包括来自超过 13,000 名受访者的见解，同时 Stack Overflow 的 2024 年开发者调查结果也已发布。
    
    **长按识别二维码查看原文**
    
    https://2023.stateofreact.com/zh-Hans/
    

📒 教程与趣事

**你以为你了解 Box Shadow？** —— 作者在这篇文章中展示了一些有趣的实验，探索了他称之为”在 DIV 元素上可能做的最糟糕的事情”之一，结合了 JavaScript 的使用。

**长按识别二维码查看原文**

https://dgerrells.com/blog/how-not-to-use-box-shadows

David Gerrells

**▶ 不要使用 JavaScript 来做那些事情：将功能迁移到 CSS 和 HTML 上** —— 充满代码和示例。一些技术尚未得到普遍支持，但浏览器可以提供很多东西，你不需要自己重新实现，比如颜色选择、模态框和动画效果。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=IP_rtWEMR0o

Kilian Valkhof

**如何为你的应用程序选择最佳的渲染策略** —— 介绍了静态站点生成（SSG）、服务器端渲染（SSR）、客户端渲染（CSR）、增量静态再生成（ISR）和部分预渲染（PPR）之间的区别。

**长按识别二维码查看原文**

https://vercel.com/blog/how-to-choose-the-best-rendering-strategy-for-your-app

Alice Alexandra Moore (Vercel)

**一个实用指南：如何避免阻塞事件循环** —— 这篇文章探讨了在单线程环境中同步和异步工作的核心原则，强调了编写非阻塞代码以实现高效的事件循环利用的重要性。

**长按识别二维码查看原文**

https://www.bbss.dev/posts/eventloop/

Slava Knyazev

**为什么在 Node.js 中生成新进程如此缓慢？** —— Val Town 平台的开发人员注意到，Node.js 每秒最多只能生成 40 个外部进程，而 Deno 和 Bun 能够生成更多的进程。

**长按识别二维码查看原文**

https://blog.val.town/blog/node-spawn-performance/

Max McDonnell

**📺 如何让你的开发者博客文章产生更大影响** —— 从 Postgres 社区的角度出发，但给出的建议是通用的，并且解释得很好。Claire Giordano

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=UhDkARpmBGU

**📄 自带 API 密钥：在浏览器扩展中支持用户提供的 OpenAI 密钥和提示** Stephen Siegert

**长按识别二维码查看原文**

https://www.xiegerts.com/post/browser-extension-genai-key-prompts/

**📄 如何有效地审查代码：GitHub 一位工程师的哲学** Sarah Vessels (GitHub)

**长按识别二维码查看原文**

https://github.blog/developer-skills/github/how-to-review-code-effectively-a-github-staff-engineers-philosophy/

**📄 Airbnb 如何平稳升级 React** —— 这绝非小事。Andre Wiggins（Airbnb）

**长按识别二维码查看原文**

https://medium.com/airbnb-engineering/how-airbnb-smoothly-upgrades-react-b1d772a565fd

🛠 代码与工具

**Ky：小巧、优雅的基于 Fetch 的浏览器 HTTP 客户端** —— 使得 Fetch API 更易使用，如这里所示。如果你想要简化你的 `fetch` 调用，值得一看。

**长按识别二维码查看原文**

https://github.com/sindresorhus/ky

Sindre Sorhus

**React Native Filament：用于 React Native 的 3D 渲染引擎** —— 快速、原生的 3D 渲染，带有 React 的特色。渲染在一个单独的线程上进行，以提高效率。GitHub 仓库以及相当不错的文档。

**长按识别二维码查看原文**

https://margelo.github.io/react-native-filament/

Marc Rousavy

**Git Granary：个人 Git LFS 服务器** —— 一个使用 TypeScript 编写、基于 Deno（但也可在 Bun 和 Node.js 下运行）的 Git Large File Storage (LFS) 服务器实现，适用于自托管的个人使用场景。

**长按识别二维码查看原文**

https://dbushell.com/2024/07/25/git-granary/

David Bushell

**litegraph.js：一个图形节点引擎和编辑器** —— 如果你需要为用户创建和操作图形或连接节点的系统，比如用于图形、音频或数据流水线，这将会很有用。演示。

**长按识别二维码查看原文**

https://github.com/jagenjo/litegraph.js

Javi Agenjo

**版本发布：**

- **Mikro ORM v6.3** —— 用于 Node.js 和 TypeScript 的流行 ORM，现在支持可选的”schema-first”方法。

- **Uppy v4.0** —— 强大的、模块化的 JavaScript 文件上传器。

- **Preact v10.23** —— 3KB 大小的 React 兼容替代品。

- **Node.js v20.16.0 (LTS)、Storybook v8.2、pnpm v9.6、Meteor.js v3**

- **🤖 OpenAI Node v4.53.0** —— OpenAI 官方 Node.js 库为他们最新的 `gpt-4o-mini` 模型添加了支持。

- **Rollup v4.19** —— ES 模块打包工具增加了对装饰器的支持。

- **eslint-plugin-unicorn v55.0** —— 一个地方包含了 100 多个有用的 ESLint 规则。

- **eslint-plugin-promise v7.0** —— 强制执行 Promise 的最佳实践。

- **pretty-ms v9.1** —— 将毫秒转换为易读的字符串。

- **Tinybase v5.1** —— 用于本地优先应用程序的强大响应式数据存储。

- **MiniSearch v7.1** —— 内存中的全文搜索引擎。（演示。）

- **swup v4.7** —— 用于服务器端渲染网站的页面转场库。

- **Jasmine v5.2** —— 用于浏览器和 Node.js 的测试框架。

🙋🏻‍♀️