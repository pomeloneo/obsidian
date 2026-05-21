# JavaScript 中文周刊 #144 - 千呼万唤始出来：State of JavaScript 2023 问卷调查结果

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532773&idx=1&sn=6a1fd42648047ba716937f5eacc18ef7&chksm=e9210b07de568211ccbb4c02ad43cbf898148b31cc203038e470884a81d3d58f16927bd656e0\#rd  
> 抓取时间: 2026/2/2 23:50:58

---

> 本期看点：2023 年度的Javascript 开发者调查报告终于出炉，提供了更多的统计维度和可视化。JavaScript 模块化发展中，ESM 逐渐取代 CJS，但迁移仍然存在很多挑战。为改善开发体验，多个提案正推进标准化，提升性能、安全性和模块间互操作性。

> TimLi、Jojo

🔥 本周热门

**2023 年 JavaScript 现状调查结果** —— 2023 年度 JavaScript 开发者调查结果终于出来了。包含了以下有趣的议题：JS 新特性使用情况, 主流工具/库在不同时间段的受欢迎程度，人们正在使用的构建工具，JavaScript 和 TypeScript 使用情况对比等等。

**长按识别二维码查看原文**

https://2023.stateofjs.com/zh-Hans/

Devographics

**JavaScript 如何最终改善模块体验** —— 多个长期提案统称为「module harmony」，将弥补 JavaScript 脱离 CommonJS 时所丢失的功能。

**长按识别二维码查看原文**

https://thenewstack.io/how-javascript-is-finally-improving-the-module-experience/

Mary Branscombe / The New Stack

**React 19 差点让互联网变得更慢** —— 即使是事先计划好的更改，如果人们没有意识到，也会对开发人员的体验产生重大影响。React 19 中对 Suspense 的更改导致了很多争议，但故事有一个圆满的结局，React 团队准备更密切倾听最终用户的意见。

**长按识别二维码查看原文**

https://blog.codeminer42.com/how-react-19-almost-made-the-internet-slower/

Henrique Yuji

**快讯：**

- Evan You，Vue.js 的作者, 最近发表了▶️ Vue 的十年，涵盖了 Vue 的过去和未来。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=OmrwRrZitv4
    

- 在推特/X上， Daniel Lemire展示了一个情况 Bun 比 Node.js 快得多，即便当两者使用相同的底层库时也是如此，这是由于 V8 引擎的复杂性导致。
    
    **长按识别二维码查看原文**
    
    https://x.com/lemire/status/1803598132334436415
    

- 🎵 你知道 TC39 现在有了自己的流行乐队 并且发了一首歌吗?
    
    **长按识别二维码查看原文**
    
    https://brucelawson.co.uk/2024/tc39-the-song/
    

📒  教程与趣事

**▶  使用 TypeScript 创建具有 3D 效果的的投射光线** —— 光线投射是一种有点老式的 3D 环境渲染技。（您可能在 1992 年的《德军总部 3D》中见过），它很容易理解，也值得实践一次。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=K1xEkA46CuM

Tsoding Daily

**TypeScript monorepo 中的实时类型** —— 让 TypeScript monorepo 感觉更加「实时」的的几种策略。

**长按识别二维码查看原文**

https://colinhacks.com/essays/live-types-typescript-monorepo

Colin McDonnell

**当主要的 npm 库商业化时会发生什么？** —— ua-parser-js 库 通常用于解析用户代理，并获得每周 1200 多万次下载，但它最近已切换到 AGPL+ 商业许可证。

**长按识别二维码查看原文**

https://adventures.nodeland.dev/archive/what-happens-when-a-major-npm-library-goes/

Matteo Collina

**可以同时打包 ESM 和 CJS 的** `**tsup**` **和 “检测类型错误工具”** —— tsup 让 TypeScript 库打包更加轻松；这个网站可以分析包的类型问题。

**长按识别二维码查看原文**

https://johnnyreilly.com/dual-publishing-esm-cjs-modules-with-tsup-and-are-the-types-wrong

John Reilly

**📄 如何使用 Google Sheets 作为 React 的「数据库」** Paul Scanlon

**长按识别二维码查看原文**

https://thenewstack.io/how-to-use-google-sheets-as-a-database-with-react-and-ssr/

**📺 Svelte 和 RSC 如何改变 Web 开发** —— 其中包括 Svelte 的 Rich Harris、Tracy Lee、Ben Lesh 和 Adam Rackis。This Dot Media

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=QTJtR8IUsQM

**📄 掌握日期格式使用** `**Intl.DateTimeFormat**` Rafael Camargo

**长按识别二维码查看原文**

https://rafaelcamargo.com/blog/mastering-date-formatting-using-intl-date-time-format-in-javascript/

**📄 MobX 记忆组件（你不需要 React 编译器)** —— 如果你确实在使用 MobX，看这里。Mike Johnson

**长按识别二维码查看原文**

https://www.mikejohnson.dev/posts/2024/06/mobx-react-compiler

**📄 将滚动动画从 JavaScript 重构为 CSS** Andrico Karoulla

**长按识别二维码查看原文**

https://component-odyssey.com/articles/08-refactoring-a-js-driven-scroll-animation-to-css

**📄 用 32 种语言实现 UUIDv7** —— 没想到原来这么简单。Anton Zhiyanov

**长按识别二维码查看原文**

https://antonz.org/uuidv7/

🛠  代码与工具

**Phoenix：可以使用 JS 编写脚本的 macOS 窗口管理器** —— macOS 将在 Sequoia 中添加更多窗口管理功能，但现在完全可以使用 JavaScript 编写脚本将会怎么样？这里是 Github 仓库

**长按识别二维码查看原文**

https://kasper.github.io/phoenix/

Kasper Hirvikoski

**JSONEditor：用于查看和编辑 JSON 的组件** —— 如果您的应用程序需要让用户直接使用 JSON，那么值得一看。它支持文本和树视图，并且兼容各种浏览器。在线 Demo。

**长按识别二维码查看原文**

https://github.com/josdejong/jsoneditor

Jos de Jong

**Rooster v9.6：微软独立于框架的富文本编辑器** —— 仅嵌套在一个“div”元素内的富文本编辑器 (demo)。已经有好几年了，但仍然维护着。

**长按识别二维码查看原文**

https://github.com/Microsoft/roosterjs

Microsoft

**NLUX：用于渲染对话式 AI 体验的库** —— 如果您想在自己的服务或第三方 AI 后端之上启动 ChatGPT 风格的对话体验，NLUX 提供了快速启动界面所需的组件。

**长按识别二维码查看原文**

https://docs.nlkit.com/nlux

Salmen Hichri

**⚙︎ NodeSwift** —— 连接 Node.js 和 Swift，以便您可以编写与 Node 交互的 Swift 代码，反之亦然。Kabir Oberai

**长按识别二维码查看原文**

https://github.com/kabiroberai/node-swift

**⚙︎ Vuesion** —— Next/Vue 应用开发的模板. Werner-Most Ideen GmbH

**长按识别二维码查看原文**

https://vuesion.github.io/docs/en/v5/

**⚙︎ Kitbag Router** —— 类型安全的 Vue.js 路由工具。Craig Harshbarger

**长按识别二维码查看原文**

https://router.kitbag.dev/

**版本发布：**

- **Electron Store v10.0** ——Electron 应用程序的简单数据持久性。

- **React Date Picker v7.1** ——简单的日期选择器组件 (Demo)。

- **Monads v0.7** —— 受 Rust 启发的 `Option`, `Result`,和 `Either` 类型。

- **Plasmo v0.88** —— “就像用于浏览器扩展的 Next.js”

- **MUI X v7.7** —— 流行的 React 组件套件。

- **React Tag Autocomplete v7.3**

- **htmx v2.0** —— ”通过 HTML 属性访问大量 JS 和 Web API 功能”的库，最近更新了主要版本，主要是为了删除弃用内容，放弃 IE 支持。

- **Electron v31** —— 跨平台桌面应用框架升级至 Chromium v126、Node v20.14 和 V8 12.6。

- **Relay v17** —— Facebook 的 React 声明式 GraphQL 客户端。

- **ESLint v9.5**

- **Serverless Framework v4**

- **pnpm v9.4**

🙋🏻‍♀️