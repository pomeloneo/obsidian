# JavaScript 中文周刊 #181 - Bare：轻量级模块化 JS 应用程序运行时问世

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541006&idx=1&sn=c4ff267e083643f8946863da60c0e068&chksm=e9216aecde56e3fa7f2ce4dd121524e98377ce19b8f3139074118a75f3d886ad465b39cf40c1\#rd  
> 抓取时间: 2026/2/2 23:50:11

---

> 本期看点：Bare 一个轻量级 JavaScript 运行时并支持多个 JS 引擎，Deno 与 Oracle 就 JavaScript 商标展开法律争议，JavaScript 同步 await 探讨，Anime.js 发布 v4.0，Safari 18.4 支持声明式 Web Push 和迭代器助手。

> 编辑：TimLi

🔥 本周热点

**Bare：一个轻量级的模块化 JS 应用程序运行时** —— 想象一个类似 Node.js 但更精简的运行时：就是 Bare。它和 Node 一样基于 V8 和 libuv（不过它支持多个 JavaScript 引擎），但 Bare 的理念是尽可能精简（只提供模块系统、插件系统和线程支持），然后依靠用户空间模块独立发展。这是个很有趣的想法 —— 点击这里了解更多详情。

**长按识别二维码查看原文**

https://bare.pears.com/

Holepunch

**Deno 与 Oracle JavaScript™ 商标之争最新进展** —— Deno 向美国专利商标局提交申请，要求撤销 Oracle 声称拥有的 ‘JavaScript’ 商标，而 Oracle 则强硬回应。Ryan 回顾了这个事件的来龙去脉，并呼吁大家帮忙传播这个消息（如果你认同 Oracle 已经放弃了这个商标，在这里签署公开信是个不错的开始）。

**长按识别二维码查看原文**

https://deno.com/blog/deno-v-oracle3

Ryan Dahl

**React v19.1 发布** —— 最大的亮点是 Owner Stacks，这是一个仅用于开发环境的功能，用于追踪哪些组件负责渲染其他组件。19.1 还带来了一些修复和小型功能更新（比如在边缘环境中支持流式传输），用于服务器端预渲染 RSC 的新 API，以及增强的 Suspense 支持。

**长按识别二维码查看原文**

https://github.com/facebook/react/releases/tag/v19.1.0

Matt Carroll (Facebook)

**快讯：**

- Safari 18.4 已发布，支持声明式 Web Push、迭代器助手、`Error.isError`，并提升了 `JSON.parse` 和 `JSON.stringify` 函数的性能。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/16574/webkit-features-in-safari-18-4/
    

- 一个将 TypeScript 风格的枚举引入 JavaScript 的长期提案即将在 TC39 下次会议上进行讨论。作者 Ron Buckton 准备了一份演示文稿介绍其优势。感谢 Rob Palmer 提供这个信息。
    
    **长按识别二维码查看原文**
    
    https://github.com/rbuckton/proposal-enum
    

- ES2025 规范已进入候选阶段，预计将在 6 月份最终通过。
    
    **长按识别二维码查看原文**
    
    https://tc39.es/ecma262/2025/
    

📒 教程与趣事

**用 TypeScript、Jupyter、Polars 和 Observable Plot 探索艺术** —— Deno 的一个引人注目的特性是它对 Jupyter Notebooks 和笔记本式编程的支持，这在 Python 世界中很常见。Trevor 展示了如何在实践中使用这样的笔记本环境进行数据探索。

**长按识别二维码查看原文**

https://deno.com/blog/exploring-art-with-typescript-and-jupyter

Trevor Manz

**JavaScript 能有同步的** `**await**` **吗？** —— Dr. Axel 探讨了异步代码与同步代码的差异问题，以及如何克服当前的限制。同步 `await` 可能会带来什么影响？

**长按识别二维码查看原文**

https://2ality.com/2025/03/sync-await.html

Dr. Axel Rauschmayer

**JavaScript 缺失的一环？Wasp 提供全栈解决方案** —— 深入了解 Wasp 团队如何围绕 React、Node 和 Prisma 构建全栈 Web 应用程序框架。如果你在寻找一个更传统风格的全栈方案，这是个不错的选择。

**长按识别二维码查看原文**

https://thenewstack.io/javascripts-missing-link-wasp-offers-full-stack-solution/

Loraine Lawson (The New Stack)

**🚂 1993 年的一台蒸汽机车是如何搞坏我的 Yarn 测试的** —— 一个有趣的 bug 追踪故事，内容确实如标题所示。Yew Leong

**长按识别二维码查看原文**

https://blog.cloudflare.com/yarn-test-suffers-strange-derailment/

**📄 解决 JavaScript 中的循环依赖问题** Bryan Braun

**长按识别二维码查看原文**

https://www.bryanbraun.com/2025/03/29/breaking-down-circular-dependencies-javascript/

**📄 使用 Playwright 进行自动化视觉回归测试** Frederik Dohr

**长按识别二维码查看原文**

https://css-tricks.com/automated-visual-regression-testing-with-playwright/

**📄 我的 WebAssembly 初体验总结** Chris Wellons

**长按识别二维码查看原文**

https://nullprogram.com/blog/2025/04/04/

🛠 代码与工具

**Anime.js v4.0：Web 动画 JavaScript 库** —— 如果你对 Web 动画感到厌倦，也许 Anime.js 能重新激起你的兴趣。这是一个成熟库的重大升级，可用于制作 CSS 属性、SVG、DOM 和 JS 对象的动画。它流畅、构建精良，现在还配备了全新的文档。

**长按识别二维码查看原文**

https://animejs.com/

Julian Garner

**Milkdown v7.7：所见即所得的 Markdown 编辑器框架** —— 一个基于插件系统的所见即所得 Markdown 编辑器框架，支持高度自定义。文档本身就是用 Milkdown 渲染的。GitHub 仓库。

**长按识别二维码查看原文**

https://milkdown.dev/

Mirone

**TinyBase v6.0：本地优先应用程序的响应式数据存储** —— 这是一个强大的响应式数据存储，可以作为多种类型应用程序的完整后端。v6.0 没有添加新功能，但增加了对 React 19 的支持，并完全转向 ESM。查看主页了解更多。

**长按识别二维码查看原文**

https://tinybase.org/guides/releases/\#v6-0

James Pearce

📢 其他

以下是来自开发者领域的一些有趣更新和实用资源：

- 如果你想写一篇能登上 JavaScript Weekly 的博客文章，不妨看看 Michael Lynch 写的《如何写出开发者爱读的博客文章》。然后回复告诉我们你的想法！
    
    **长按识别二维码查看原文**
    
    https://refactoringenglish.com/chapters/write-blog-posts-developers-read/
    

- Chrome 135+ 支持 CSS Overflow 5 规范，让创建原生滚动和轮播体验变得更容易。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/carousels-with-css
    

- Yoni Goldberg 写了一篇关于用例代码模式的优雅和强大之处的文章。
    
    **长按识别二维码查看原文**
    
    https://practica.dev/blog/about-the-sweet-and-powerful-use-case-code-pattern/
    

- GitHub 给项目维护者的建议：每个维护者都需要知道的 5 个 GitHub Actions。
    
    **长按识别二维码查看原文**
    
    https://github.blog/open-source/maintainers/5-github-actions-every-maintainer-needs-to-know/
    

- 🤖 The New Stack 的 Alex Williams 探讨了 AI 代理如何悄然改变前端开发。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/how-ai-agents-are-quietly-transforming-frontend-development/
    

**版本发布：**

- **Express v5.1** —— 这个长期存在的 Node.js Web 框架迎来更新，5.x 终于成为 npm 上的 `latest` 标签版本。

- **React Email v4.0** —— 用于渲染 HTML 邮件的组件和工具。

- **zx v8.5** —— Google 开发的 Node shell 脚本工具。

- **Astro v5.6**、**Ember v6.3**、**Turborepo v2.5**、**Node.js v23.11.0**、**Bun v1.2.8**

- **node-llama-cpp v3.7** —— 通过 `llama.cpp` 绑定在本地运行 LLM。

- **bignumber.js v9.2** —— 任意精度的十进制和非十进制算术库。

- **TS-Pattern v5.7** —— 具有智能类型推断的模式匹配库。

- **React Admin v5.7** —— 用于构建 B2B 前端界面的框架。

- **UVCanvas v0.3** —— 用 React 渲染精美的着色画布。

- **Danfo.js v1.2** —— 受 Pandas 启发的 JavaScript 数据分析工具包。

- **Vuetify v3.8** —— Vue 组件框架。