# JavaScript 中文周刊 #85 - npm 包溯源功能

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519197&idx=1&sn=d314a4eb7a82c8b9fcdb5674798745c5&chksm=e921c03fde5649296fa76c4d65d25253c052fd0870ced35a60064fd0ff9a9465cee8b52a239f\#rd  
> 抓取时间: 2026/2/2 23:52:09

---

> 本期看点：作为官方 npm 注册表的管理者，GitHub 一直致力于改善其安全性。从本周起，如果你通过 GitHub Actions 构建 npm 包，那么你可以发布包的溯源信息，从而使用户有办法验证包是从哪个仓库构建、以及如何构建的。

> 编辑：Yucohny、liujinyi

## 🔥 本周热门

**介绍 npm 包溯源功能** — 作为官方 npm 注册表的管理者，**GitHub** 一直致力于改善其安全性。从本周起，如果你通过 GitHub Actions 构建 npm 包，那么你可以发布包的**溯源信息**，从而使用户有办法验证包是从哪个仓库构建、以及如何构建的。Socket 的人员 **进一步介绍了它的工作原理**。

**长按识别二维码查看原文**

https://github.blog/2023-04-19-introducing-npm-package-provenance/

DeHamer 和 Harrison（GitHub）

**Vite v4.3：现在变得更更更更快了** — 一个流行的前端工具链的小版本更新，但专注于性能。《**我们如何让 Vite 4.3 变得更快》** 深入探讨了相关细节。

**长按识别二维码查看原文**

https://vitejs.dev/blog/announcing-vite4-3.html

Evan You 和贡献者

**快讯：**

- **TypeScript v5.1 Beta 已发布** ，该版本允许返回 undefined 的函数不需要 return 语句，对于 get 和set 访问器属性可以有不相关的类型，使用JSX时可以有命名空间属性名称等等。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-1-beta/
    

- **React 核心团队** 似乎 **受到了** Meta 最近一轮裁员的 **影响**（以及 **Relay 团队**），尽管 Dan Abramov **最近指出** Meta 仍在投资生态系统。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/mattcarrollcode/status/1648770402272018432
    

## 📒 教程与趣事

**Chrome 为 PWA 提供更丰富的安装 UI** — 这为开发人员提供了新的机会，以鼓励最终用户安装他们的应用程序。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/richer-install-ui-desktop/

Adriana Jara（Chrome 开发者）

**Passkeys：Passkeys 是什么以及为什么要使用它？** — 作者一直在尝试使用 passkeys 和相关的 WebAuthn API 将其应用于 Web。这是一种越来越普遍的安全方法，这篇文章为此提供了基础知识。

**长按识别二维码查看原文**

https://css-tricks.com/passkeys-what-the-heck-and-why/

Neal Fennimore

**将 React Flow 与 Web Audio API 集成** — **React Flow** 是一个构建基于节点的编辑器和交互式图表的组件，因此非常适合用于构建音频信号链。这里有很多深度，一些不错的例子，这些技术可能对许多其他用例都有用。

**长按识别二维码查看原文**

https://reactflow.dev/blog/react-flow-and-the-web-audio-api/

Hayleigh Thompson

**在 JavaScript 中创建枚举的方法** — 枚举是一组命名常量。在 JavaScript 中，可以使用普通对象、冻结对象、代理对象或基于类的方法来创建枚举。本文详细介绍了这些方法。

**长按识别二维码查看原文**

https://dmitripavlutin.com/javascript-enum/

Dmitri Pavlutin

**Deno vs. Node：没有人准备好转移** — **Deno** 作为 Node 的替代方案有很多优点，但 Node 有时间、成熟度和庞大的、已建立的用户群（本周 Node v20 的发布表明，Node 仍在继续发展）。

**长按识别二维码查看原文**

https://cult.honeypot.io/reads/deno-vs-node-main-differences/

Piumi Liyana Gunawardhana（Honeypot）

**如何在 JavaScript 中处理日期和时间**

**长按识别二维码查看原文**

https://gomakethings.com/how-to-work-with-dates-and-times-in-vanilla-javascript/

Chris Ferdinandi

## 🛠 代码与工具

**Tachyon v2.0：一个小型脚本，可以使页面导航更快** — 它通过在用户导航到页面之前对页面进行预渲染，使页面转换尽可能快。

**长按识别二维码查看原文**

https://github.com/weebney/tachyon

Tachyon

**instant.page** 是该领域中另一个众所周知的选择。 风靡全球的静态网站生成器。

**Iconoir：1300+ 开源 SVG 图标** — 一个庞大的清晰简单的图标库，可快速集成到 React、React Native、Figma 等应用中，或者如果你喜欢的话，可以使用 CSS。

**长按识别二维码查看原文**

https://iconoir.com/

Luca Burgio

**Ark UI：一个可定制、可访问、无样式的 UI 组件库** — 与 React、Vue 和 Solid 兼容，由 **Zag.js** 提供支持。所有组件都符合可访问性标准，并且可以根据你自己的设计系统进行主题定制。

**长按识别二维码查看原文**

https://ark-ui.com/

Chakra Systems

**next-route-visualizer：可视化 Next.js 应用路由** — 一个可以可视化 Next.js 应用目录路由的包，**可以查看这个演示**。

**长按识别二维码查看原文**

https://github.com/DiiiaZoTe/next-route-visualizer

Alexander Vencel

**ohash：纯 JS 的超快哈希库**

**长按识别二维码查看原文**

https://github.com/unjs/ohash

UnJS

**版本发布：**

- **Shoelace v2.4**
    
    ↳ 流行的设计精美的 Web 组件库。
    

- **Gatsby v5.9**
    
    ↳ 全球风行的静态网站生成器。
    

- **元素 v4.3**
    
    ↳ `<time>` 的 Web 组件扩展
    

- **Fable v4.1**
    
    ↳ F# 到 JavaScript/TypeScript 编译器。
    

- **useHotkeys v4.4**
    
    ↳ React 钩子用于快捷键。
    

- **AdminJS v7.0**
    
    ↳ Node webapps 的管理面板。
    

- **lowdb v6.0**
    
    ↳ 简单、本地 JSON 数据库。
    

- **imaskjs v6.6**
    
    ↳ Vanilla JS 输入遮罩。
    

- **CKEditor 5 37.1**
    
    ↳ 丰富文本编辑器框架。
    

## 🎨 让我们开始艺术..

**DPaint JS：一个受 Deluxe Paint 启发的图像编辑器** — 有时我们喜欢链接到用 JavaScript 构建的令人印象深刻的项目，如果你曾经接触过 Commodore Amiga，你一定会喜欢这个项目。它是一个受 Deluxe Paint 启发的基于 Web 的图像编辑器，Deluxe Paint 本身是一个令人震撼的图形编辑工具，来自 1980 年代。现在我们只等待一个 NeoPaint 的克隆了.. :-)

**长按识别二维码查看原文**

https://www.stef.be/dpaint/

Steffest

## 🙋🏻‍♀️