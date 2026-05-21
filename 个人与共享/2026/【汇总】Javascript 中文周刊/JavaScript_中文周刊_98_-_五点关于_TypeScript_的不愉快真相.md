# JavaScript 中文周刊 #98 - 五点关于 TypeScript 的不愉快真相

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522824&idx=1&sn=e9b51da5a92a0ee27195fae236cd4df3&chksm=e921d1eade5658fc30a83d5d1c9fe60dd17cb7dbd4a66347717b5ea0f5d660eb95eb7517093b\#rd  
> 抓取时间: 2026/2/2 23:51:52

---

> 本期看点：上周，`Promise.withResolvers` 提案进入第三阶段、Hristiyan Dodov 发布了关于 JSX 的起源及其存在的原因的相关文章。

> 编辑：Jojo、TimLi777、liu-jin-yi

## 🔥 本周热门

**pkg-size: 查询 npm 包的真实大小** — pkg-size 可以在不离开浏览器的情况下显示一个 npm 包的真实大小，包括其依赖项。它使用 WebContainers 技术在浏览器环境中「安装」实际的软件包，从而得出精确的包大小。

**长按识别二维码查看原文**

https://pkg-size.dev/

Hiroki 在 Twitter 上发布了一个 **链式推文**，进一步解释了它的工作原理。他解释说，**WebContainers** 技术能够让 Node.js 的运行时环境运行在浏览器中，而不是在本地或远程服务器上，这有利于开发体验。pkg-size 就是利用了这一技术，让用户能在浏览器中检查 npm 包的真实大小。

总的来说，pkg-size 是一个界面设计很美的网站，能够准确显示用户 npm 包(包括依赖项)的大小，能有效帮助 JavaScript 开发者。

Hiroki Osame

**TypeScript 和逐渐类型的来临** GitHub ReadME 项目提供了一篇全面的新闻报道，介绍了静态类型如何进入 JavaScript 世界，TypeScript 提供了什么，一些替代方案以及给 JavaScript 本身添加类型注解的可能性。

**长按识别二维码查看原文**

https://github.com/readme/featured/typescript-gradual-types

Mike Melanson (GitHub)

**Storybook 7.1: 构建 UI 组件的工作坊** — v7.1 引入了面向新团队成员的在应用程序内入门，为 Tailwind、MUI、styled-components 和 MUI 提供零配置样式**支持**，Vue 3 源代码片段等。

**长按识别二维码查看原文**

https://github.com/storybookjs/storybook/releases/tag/v7.1.0

Storybook Team

**五点关于 TypeScript 的不愉快真相** — 对于一个看似痴迷于 TypeScript 的世界来说，这是一个简单的现实：“如果你想进入 TypeScript，就不要认为你可以把 JavaScript 抛在后面。它会找到你，它会抓住你。”

**长按识别二维码查看原文**

https://oida.dev/5-truths-about-typescript/

Stefan Baumgartner

**⚡️ 快讯：**

- **Promise.withResolvers 提案** 提案已在 TC39 上从第 2 阶段进展到第 3 阶段， **数组分组**，和 **源阶段引入**也进入了第 3 阶段。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-promise-with-resolvers
    

- 🗣 从 Hacker News 上的**讨论**来看，最近该网站没有充斥新的 JavaScript 框架链接的原因。React 是否“赢得胜利”？AI 抢占了焦点？还是 **JavaScript 静静地酝酿着改革……？**
    
    **长按识别二维码查看原文**
    
    https://news.ycombinator.com/item?id=36780295
    

- 👴🏻 1996 年的一篇博客文章突然出现，告诉我们 **Netscape 3.0 中的最新 JavaScript 特性** – 确实是历史的回眸。向操作符向 `typeof` 问好!
    
    **长按识别二维码查看原文**
    
    https://www.infoworld.com/article/2077267/new-javascript-features-in-navigator-3-0.html
    

## 📒 教程与趣事

**“如何使用 Rust SDK 生成 JS 和 Python SDK”** — PostgresML 是一个将机器学习功能添加到 Postgres 的扩展。它的团队非常喜欢并且更倾向于使用 Rust，但是大多数用户都在使用 JavaScript 或 Python。那么怎么办呢？可以使用 Rust 同时编写多语言库。

**长按识别二维码查看原文**

https://postgresml.org/blog/how-we-generate-javascript-and-python-sdks-from-our-canonical-rust-sdk

Silas Marvin (PostgresML)

**使用 `jscodeshift` 更新代码** — TypeORM 是一个 Node 的 ORM，它引入了一些不兼容的更新，要求作者在代码中更新大量调用。这是一个绝佳的时机，用户可以使用“codemod”自动完成这项工作。即使你不使用 TypeORM，这篇文章也可能会给你一些在其他地方使用这种方法的灵感。

**长按识别二维码查看原文**

https://dev.clintonblackburn.com/2023/07/15/upgrading-typeorm-with-jscodeshift.html

Clinton Blackburn

**如何提升 React 18 应用性能** — 如果你还没有完全了解 React 在并发渲染、transitions、Suspense 以及 React 服务器组件方面的更新，那么这篇文章将是一篇很好的回顾和入门，帮助你快速了解 React 新功能如何显著提升性能。

**长按识别二维码查看原文**

https://vercel.com/blog/how-react-18-improves-application-performance

Lydia Hallie (Vercel)

**提速 300 毫秒：采取必要措施减少维基百科的总阻塞时间（TBT）**

**长按识别二维码查看原文**

https://www.nray.dev/blog/300ms-faster-reducing-wikipedias-total-blocking-time/

Nicholas Ray

**关于 JSX 的起源及其存在的原因**

**长按识别二维码查看原文**

https://dodov.dev/blog/origins-of-jsx-and-why-it-exists

Hristiyan Dodov

## 🛠 代码与工具

**wavesurfer.js v7: 音频波形播放器** — 如果您正在创建播客播放器、音频体验或任何可能需要查看交互式音频波形的场景，请查看此项目。**GitHub 仓库**。

**长按识别二维码查看原文**

https://wavesurfer-js.org/

katspaugh and contributors

**TOAST UI Grid：一个可定制的网页网格控件** — 一个功能强大的 MIT 许可的网格样式控件，用于显示、编辑和管理数据。它来自与 **TUI Editor** 和 **TUI Calendar** 相同的团队，虽然它本身就很出色，但还有适用于 Vue 和 React 的包装器。**GitHub 仓库**。

**长按识别二维码查看原文**

https://ui.toast.com/tui-grid/

NHN

**Pines：一个为 Alpine.js 和 Tailwind 项目设计的 UI 组件库** — 包括滑块、工具提示、手风琴、模态框等组件。纯 CSS 组件可在任何 Tailwind 项目中使用，而需要 JS 的组件则专为 Alpine.js 设计。

**长按识别二维码查看原文**

https://devdojo.com/pines

devdojo

**YouTube.js v5.5：一个基于 YouTube 私有 API 的封装库** — 这是你可能期望会很快被某种方式阻止的东西，但它已经有 18 个月的历史了，所以… 😆 这个趣味不仅仅是给 Node 或 Deno 用户的 - 如果你能通过自己的服务器代理请求，它也可以在浏览器中工作。

**长按识别二维码查看原文**

https://github.com/LuanRT/YouTube.js

LuanRT

**Eruda v3.0：一款用于移动浏览器的控制台** — 如果你处于无法访问 DevTools 的情况，你可以将 Eruda 添加到你的页面，它提供了一种类似虚拟开发者工具的功能，可以在任何浏览器中使用，包括移动端。

**长按识别二维码查看原文**

https://github.com/liriliri/eruda

LiriLiri

**Reagraph v4.10：适用于 React 的 WebGL 图形可视化库** — 这里有一个基本的代码示例。本周的更新增加了对三维聚类的支持。**GitHub 仓库**。

**长按识别二维码查看原文**

https://reagraph.dev/?path=/story/demos-cluster–three-dimensions

REAGRAPH

**brotli-wasm v2.0：Brotli 压缩和解压缩工具** — 通过 WebAssembly 实现了对 Node 和浏览器的支持。

**长按识别二维码查看原文**

https://github.com/httptoolkit/brotli-wasm

HTTP Toolkit

**Pacquet：一款全新的、_实验性_ Node 包管理器** — 出自一位 Node.js 核心成员之手。

**长按识别二维码查看原文**

https://github.com/anonrig/pacquet

Yagiz Nizipli

**🎉 版本发布：**

- Fresh v1.3
    
    ↳ Deno Web 框架。现在插件可以将路由和中间件注入到应用程序中，支持 `Deno.serve`，并且你可以创建异步路由组件。
    

- Downshift v8.0
    
    ↳ 用于构建符合 WAI-ARIA 的 React 自动完成、组合框和选择组件的基本元素。
    

- Node.js v18.17.0 (LTS)
    
    ↳ Node 18 获得了 Ada 2.0 WHATWG URL 解析器。
    

- Fastify v4.20
    
    ↳ 快速、低开销的 Node.js 网络框架。
    

- Shareon v2.2
    
    ↳ 轻量级、时尚的社交网络“分享”按钮。
    

- Helipopper v8.0
    
    ↳ 适用于 Angular 的工具提示和弹出框。(演示。)
    

- Ink v4.3
    
    ↳ 用于交互式命令行应用的 React。
    

- 📅 React Calendar v4.4

- ♖ React Chessboard v4.0

## 🎵 来点音乐

**Chip Player JS：基于浏览器的 MIDIs、MODs 和游戏音乐** — 这个网站的创建者，和我一样，对老式数字音乐有着迷恋 — MIDI 文件、追踪器等等。他决定不再让一台老电脑运行，而是 **构建一个基于浏览器的音乐播放器** 来播放这些文件。

**长按识别二维码查看原文**

https://chiptune.app/

Matt Montag

附言：如果你正在寻找特定的音乐来听，**著名的挪威跟踪器音乐制作人 Jogeir Liljedahl** 的音乐 非常值得一试 — 尤其是 _Overture_ 或者 _Guitar Slinger_。或者试试 **Donkey Kong Country** 的 梦幻般的 _Aquatic Ambience_？令人惊奇的是，跟踪器通过大量重复使用和操纵样本，成功地将大量内容压缩到了几百 KB 大小。

**长按识别二维码查看原文**

https://chiptune.app/browse/Modland/coma%27s%20favorite%20Protracker/Jogeir%20Liljedahl/

## 🙋🏻‍♀️