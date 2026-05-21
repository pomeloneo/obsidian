# JavaScript 中文周刊 #4 - 新版 DevTools 支持跨浏览器使用

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247492319&idx=1&sn=e8e2493f8d09095d8f632e633bbdb12d&chksm=e921a93dde56202ba38d0ac8eb8cbe91aba8403c39928ea4f3c916584b4792054efcffff2178#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247492319&idx=1&sn=e8e2493f8d09095d8f632e633bbdb12d&chksm=e921a93dde56202ba38d0ac8eb8cbe91aba8403c39928ea4f3c916584b4792054efcffff2178#rd)

抓取时间: 2026/2/2 23:53:53

---

> 本期看点：一个非常令人振奋的消息，DevTools 可以跨浏览器使用了！社区的小伙伴编写了 replace-jquery，可以将 jQuery 的代码替换为原生代码，可以达到去 jQuery 化的目的，虽然只是个想法，但是值得一试。还有一篇关于 unknown vs any 的对比文章，想必有很多朋友对这两个类型还傻傻分不清楚。
> 
> 编辑：liu-jin-yi、Matrixbirds、QC-L、Otto、whatwewant

**构建打包非 JavaScript 的资源** — 本文将教你如何在 JavaScript 中引入并打包各种类型的资源，使它在浏览器和静态模块打包工具中都能正常工作。

**长按识别二维码查看原文**

https://web.dev/bundling-non-js-resources/

Ingvar Stepanyan (Google)

**浏览器的 DevTools 最新功能：支持跨浏览器使用** — 快来了解 DevTools 最新功能，支持跨浏览器使用，意味着以后 DevTools 将可以在 Chrome/Firefox/Safari/Edge 等任意一个浏览器中使用。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/09/devtools-cross-browser-edition/

Patrick Brosset

**用 Voronoi Tessellations 制作 SVG 图案** — 以自然界为灵感创建生成具有有趣外观的 SVG 图案。非常有趣的 JavaScript 示例。

**长按识别二维码查看原文**

https://georgefrancis.dev/writing/crafting-organic-patterns-with-voronoi-tessellations/

George Francis

**自动查找 jQuery 的调用代码，然后生成相应的原生 JS 替换代码** — 我们提供了一个工具，可以通过查找 jQuery 相关的方法并提供“原生”的替代方案来帮助你移除项目中的 jQuery 依赖。尽管目前看来这个方案还不可靠，但确实是一个有趣的想法。另外，你可以使用更轻巧的，更现代的 jQuery 替代方案，例如 Cash。

**长按识别二维码查看原文**

https://github.com/sachinchoolur/replace-jquery

Sachin Neravath

**快讯：**

- **V8 发布了 v9.4**，此版本内容改动不大，支持了类静态初始化块这一个功能，且默认可用。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/v8-release-94
    

- 亚马逊的开发者们推出了 **AWS 开发者播客** – 每周一次关于 AWS 的会谈，例如 AWS Amplify with Ali Spittel。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/awsdevelopers/status/143311242788171776
    

- 在你的终端上运行 `npx matrix-rain` 有惊喜哦。黑客帝国般的沉浸式体验，**源码地址**。
    
    **长按识别二维码查看原文**
    
    https://github.com/nojvek/matrix-rain
    

- Ruby on Rails 的作者录制了一个 **15 分钟的视频**主要展示了这个流行的后端框架将如何在其下一个主要版本中处理 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=JsNtLiph87Y
    

- **引人入胜的 OpenAI demo**，展示了如何让他们的系统根据你的指示编写代码。一开始以 Python 语言为范例进行演示，13 分钟时他们改用 JavaScript 语言进行了演示，仅通过 **描述** 就创建了一个简单的游戏。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=SGUCcjHTmGY
    

**版本发布：**

**Prettier 2.4** – 优秀的代码格式化工具。

**React Router 5.3** – React 的声明式路由。

**Acorn 8.5** – 一个小巧、快速的 JavaScript 解析器。

**Flicking 4.3** – 灵活的轮播组件。

**ember-simple-auth 4.0** – Ember.js 应用程序的身份验证。

**Ember 3.28 and 4.0 beta** – 流行且功能完备的框架。

## 📖 教程与趣事

**探索 CSS Paint API：Blob 动画** — 目前只在 Chrome（和 Edge）上支持这种有趣的动画效果，通过 JavaScript 使用 Paint API 绘制更加有趣的 CSS 的粘性/斑点形状。

**长按识别二维码查看原文**

https://css-tricks.com/exploring-the-css-paint-api-blob-animation/

Temani Afif

**Node.js 核心有哪些新变化？** — 最近 Node 的更新非常频繁，除非你密切关注它（欢迎的 Node 周刊），否则你可能会错过添加的新功能。本文分享了一些有用的新增功能。

**长按识别二维码查看原文**

https://simonplend.com/whats-new-in-node-js-core/

Simon Plenderleith

**使用 Neovim 和 Tmux 进行 JavaScript 开发** — 如果你是一个 Vim 用户，也许已经开始使用 VS Code，但是你想念之前的日子吗？Neovim 是 Vim 的一个分支，它赢得了 Elijah 的青睐，在这里他展示了它对 JavaScript 开发者的价值。

**长按识别二维码查看原文**

https://elijahmanor.com/blog/neovim-tmux

Elijah Manor

**在 JavaScript 中使用正则表达式的危险性** — 如果你不知道什么是”灾难性回溯”，这是一篇很 _基础_ 的文章，它可能会很好的告诉你。

**长按识别二维码查看原文**

https://blog.bitsrc.io/threats-of-using-regular-expressions-in-javascript-28ddccf5224c

Dulanka Karunasena

**TypeScript 中的** `**unknown**` **vs** `**any**`

**长按识别二维码查看原文**

https://dmitripavlutin.com/typescript-unknown-vs-any/

Dmitri Pavlutin

## 🛠 代码与工具

**Shoelace：一个具有前瞻性的 Web Component 组件库** — 一组精心设计的日常 UI 组件（按钮、抽屉、输入框、菜单、颜色选择器等等），以一种与框架无关的方式构建（并且有 React 版本）。

**长按识别二维码查看原文**

https://shoelace.style/

Cory LaViska

**Harlem 2.0：Vue 3 的简单可扩展状态管理库** — 提供一个简单的函数式 API 来创建、读取和改变状态–而且它最小只有 1.5KB 大小。

**长按识别二维码查看原文**

https://harlemjs.com/

Andrew Courtice

**Dannjs：一个为 JavaScript 准备的人工智能库** — 其目的是便于使用，因此它很适合用于实验当中。

**长按识别二维码查看原文**

https://dannjs.org/

Matias Vazquez-Levi

**gron：轻松查看 JSON** — 一个用 Go 编写的工具，将 JSON 转换成更容易使用的 `grep` 赋值形式，所以你可以使用 `grep` 查看结果的内容/路径。这个工具很有用。

**长按识别二维码查看原文**

https://github.com/tomnomnom/gron

Tom Hudson

**PrimeVue：一个 Vue UI 组件库** — 这是 PrimeFaces 的 Vue 版本，其中还包括React 版本。你可以在这里查看 Vue 组件。

**长按识别二维码查看原文**

https://www.primefaces.org/primevue/

primefaces

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。