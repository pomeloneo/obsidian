# JavaScript 中文周刊 #64 - 函数式编程到底有什么优点？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512484&idx=1&sn=b74851738edf7104cbea3762b6ba398e&chksm=e921fa46de567350367812dc08bd2b3fbd998eafa21d58d3899b022e6fbe8a7b1d64ee4604b0\#rd  
> 抓取时间: 2026/2/2 23:52:39

---

> 本期看点：上周，Angular v15 发布、TypeScript v4.9 发布。……更多热门文章资讯请点击本期周刊查看！

> 编辑：Yucohny、liu-jin-yi、山鬼、Matrixbirds

## 🔥 本周热门

**函数式编程到底有什么优点？** — 本篇文章是由即将出版的 《Skeptic’s Guide to Functional Programming with JavaScript》的作者 James 以一种更容易理解的方式书写的函数式编程思想的文章，相信你读完本篇文章会大有收获。

**长按识别二维码查看原文**

https://jrsinclair.com/articles/2022/whats-so-great-about-functional-programming-anyway/

James Sinclair

**Angular v15 发布** — 本次 v15 版本剔除了传统的编译器，独立的 API（没有 NgModules！）是一个稳定的主流功能，而指令组成 API 开辟了新的代码重用策略。详情可点击链接查看！

**长按识别二维码查看原文**

https://blog.angular.io/angular-v15-is-now-available-df7be7f2f4c8

Minko Gechev

**TypeScript v4.9 发布** — 本次更新主要添加了 `satisfies` **operator** 操作符、类中的 **auto-accessors**、以及 NaN 相等性检查方式的改变，以及编辑器工具和性能改进。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-9/

Daniel Rosenwasser (Microsoft)

**快讯：**

- GitHub 开源了 **两种新字体**。
    
    **长按识别二维码查看原文**
    
    https://github.com/mona-sans
    

## 📒 教程与趣事

**React Three Fiber：着色器和魔幻世界的粒子效果** — 你将会在这个有趣的交互式新手教程中学到许多有关着色器和渲染粒子效果。

**长按识别二维码查看原文**

https://blog.maximeheckel.com/posts/the-magical-world-of-particles-with-react-three-fiber-and-shaders/

Maxime Heckel

**ECMAScript 提案: 正则表达式的新标记 `/v`** — 一个新正则表达式符号的提议`/v`，可改进在字符集中的对多码位字素，例如：一些特殊的 Emoji，允许有嵌套或组合的字符集，同时可改进匹配大小写不敏感的否定字符集。这非常的复杂，不过 Dr. Axel Rauschmayer 在这里做了总结归纳。

**长按识别二维码查看原文**

https://2ality.com/2022/11/regexp-v-flag.html

Dr. Axel Rauschmayer

**不依赖 JavaScript 设计表单的 UI 状态** — 你可以用大量的`:has`伪类并且它已经有了**半良好的浏览器支持。**

**长按识别二维码查看原文**

https://webkit.org/blog/13096/css-has-pseudo-class/\#styling-form-states-without-js

Jen Simmons

**用 Storyboook 和 Nightwatch 实践组件驱动开发**

**长按识别二维码查看原文**

https://pineview.io/supercharge-your-storybook-with-nightwatch-testing/

Andrei Rusu

## 🛠 代码与工具

**tslog v4.0：支持 JS、TS 的日志输出库**— 功能丰富，类型齐全，可以通过本机 V8 进行堆栈跟踪 API、显示代码框架等。现在支持 Node 和浏览器。

**长按识别二维码查看原文**

https://tslog.js.org/

Eugene Terehov

**TanStack Router：一个完全类型安全的路由器** — React、Solid、Vue 的强大路由和一流的搜索参数 API 和 Svelte。内置缓存、自动预取等功能。

**长按识别二维码查看原文**

https://tanstack.com/router/v1

Tanner Linsley

**AEWC：将 Ace 代码编辑器添加到页面的 Web 组件** — Ace 是一个成熟的代码编辑器控件，它以`Web Components`形式包装。

**长按识别二维码查看原文**

https://github.com/MarketingPipeline/Ace-Editor-Web-Component/

Marketing Pipeline

**Twix：使用 Tailwind CSS 设计 React 组件样式** — 如果您从不喜欢在 JavaScript 中使用 CSS，那么 Tailwind 怎么样？

**长按识别二维码查看原文**

https://github.com/Idered/twix

Kasper Mikiewicz

**OverlayScrollbars v2.0：用于替换原生滚动条的 JS 滚动条插件** — 提供自定义样式的叠加滚动条，同时保持原生功能和体验。明智地使用。v2.0 是用 TypeScript 完全重写的，而且更小。

**长按识别二维码查看原文**

https://kingsora.github.io/OverlayScrollbars/

Rene Haas

**版本发布：**

- **Playwright v1.28**
    
    ↳ Web 自动化和浏览器控制框架。
    

- **Cypress v11.1**
    
    ↳ 快速、简单和可靠的测试。现在支持 Next 13。
    

- **🧹 NPKILL v0.10** 清理 `node_modules`。

- **Derby v1.1** 全栈 MVC 应用程序框架。

- **Node.js v19.1.0**

- **v1.1**
    
    ↳ 用于生成 QR 码的 Web 组件。(Demo)
    

- **FortuneSheet v0.9**
    
    ↳ 类似 Excel 的电子表格组件。(Demo.)
    

- **Happy DOM v7.7**
    
    ↳ 无 GUI 浏览器的 JS 实现。
    

- **Capacitor v4.5**
    
    ↳ 本地 PWA 应用程序 API 和工具包。
    

- **vue-concurrency v4.0**
    
    ↳ Vue 和组合 API 的并发管理。
    

- **v3.3** - 对 `<time>` 的扩展。

- **DOCX v7.7** - 生成 .docx 文件。

- **React95 v4.0** - Win95 风格的 React 组件。

**DOjS：一个关于 DOS 的 JS Canvas** — DOjS 是一个 JavaScript 编程环境，适用于运行 MS-DOS、FreeDOS 或任何基于 DOS 的 Windows（如 95、98、ME）的系统。

**长按识别二维码查看原文**

https://github.com/SuperIlu/DOjS

SuperIlu

## 🙋🏻‍♀️