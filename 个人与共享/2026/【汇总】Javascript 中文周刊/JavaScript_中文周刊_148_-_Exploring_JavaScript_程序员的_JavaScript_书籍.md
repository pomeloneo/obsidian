# JavaScript 中文周刊 #148 - Exploring JavaScript: 程序员的 JavaScript 书籍

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533604&idx=1&sn=51bc3e8afdb53b92addde98de8578d8f&chksm=e9210fc6de5686d056bae82e03869d71dc0de23f1706bb0b48b1f3be220dc78e57c82c547cda\#rd  
> 抓取时间: 2026/2/2 23:50:53

---

> 本期看点：Dr. Axel 多年来一直在更新精彩的博客文章以及曾担任 JavaScript Weekly 编辑，而且他还出版了一系列内容丰富的书籍，你大多可以在线免费阅读，包括新更新的 《Exploring JavaScript (ES2024 Edition)》、《Deep JavaScript》 和 《Tackling TypeScript》。

> 编辑：TimLi

🔥 本周热门

**Exploring JavaScript：程序员的 JavaScript 书籍** — Dr. Axel 多年来一直在更新精彩的 博客文章 以及曾担任 JavaScript Weekly 编辑，而且他还出版了一系列内容丰富的书籍，你大多可以在线免费阅读，包括新更新的 《Exploring JavaScript (ES2024 Edition)》、《Deep JavaScript》 和 《Tackling TypeScript》。

**长按识别二维码查看原文**

https://exploringjs.com/

Dr. Axel Rauschmayer

**Node.js v22.5.0（当前版本）发布** — 这是一个值得注意的版本，原因有两个：首先，`node:http` 中的 WebSocket 功能现在已公开，其次，Node 正在嵌入 SQLite，并且现在可以通过 `node:sqlite` 直接访问它。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.5.0

Antoine du Hamel

**▶  dotJS 2024 的演讲** — dotJS 2024 几个月前在巴黎举行，现在所有的演讲都可以在 YouTube 上观看。亮点包括 Lea Verou 讨论 API 和 UI 设计之间的相似性、David Flanagan 讲述 WebAssembly 的进展 和 Minko Gechev 讨论 现代框架功能的融合。这些演讲都很简短，所以可以快速获取要点。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLMW8Xq7bXrG7fOUOLJQw9I7ygJCbue9zO\#dotjs2024

YouTube

**快讯：**

- TypeScript 5.6 的第一个测试版预计下周发布——这是 TypeScript 5.6 的迭代计划，如果你想提前了解功能和时间表。
    
    **长按识别二维码查看原文**
    
    https://github.com/microsoft/TypeScript/issues/59250
    

📒 教程与趣事

**如何制作复杂的 Chrome 扩展** — 现在，快速制作一个简单的浏览器扩展并不是什么大问题，特别是有像 Extension 这样的工具来启动项目。更大的扩展则是另一回事，所以从一个已经构建过复杂扩展的团队中学习经验是很有意义的。

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/how-to-make-complex-chrome-plugins-a-zero-gravity-guide

Nina Torgunakova

**一个 TypeScript 开发者对 Zig 的看法** — Rust 可能是目前最酷的系统编程语言，但 Zig 也有很多优点（值得注意的是 Bun 就是用它实现的）。这是一个从 TypeScript 角度出发的好入门指南。

**长按识别二维码查看原文**

https://effectivetypescript.com/2024/07/17/advent2023-zig/

Dan Vanderkam

**JavaScript 有多快？模拟 2000 万粒子** — “挑战：在手机上使用纯 JavaScript 以 60 FPS 的速度仅用 CPU 模拟 1,000,000 粒子。开始吧。” 这是我一直支持的那种有趣且详细的实验。

**长按识别二维码查看原文**

https://dgerrells.com/blog/how-fast-is-javascript-simulating-20-000-000-particles

David Gerrells

**Node.js 流的读写指南** — Matteo 提醒我们在合适的情况下使用 Node 强大的 流数据功能 的好处，以及如何处理背压和错误管理。

**长按识别二维码查看原文**

https://blog.platformatic.dev/a-guide-to-reading-and-writing-nodejs-streams

Matteo Collina

**React 开发者需要了解的 React Native 知识** — 虽然 React 和 React Native 有很多相似之处，但它们在底层是不同的。这里有一些你需要了解的内容，以便顺利过渡。

**长按识别二维码查看原文**

https://expo.dev/blog/from-web-to-native-with-react

Kadi Kraman (Expo)

**📄 NPM 供应链安全：为什么我们对未来可以乐观** Robat William

**长按识别二维码查看原文**

https://blog.scottlogic.com/2024/07/09/supply-chain-security-in-npm-we-can-be-optimistic-about-the-future.html

**📄 如何在 Three.js 中使用着色器创建滚动时的失真和颗粒效果** Jan Kohlbach

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/07/18/how-to-create-distortion-and-grain-effects-on-scroll-with-shaders-in-three-js/

**📄 如何在 2024 年构建一个以 JavaScript UI 组件为先的开发工具初创公司** Corbado

**长按识别二维码查看原文**

https://www.corbado.com/blog/component-first-developer-tool-startup

🛠 代码与工具

**Poku 2.0：一个跨平台的 JS 测试运行器** — Poku 的理念是“将 JavaScript 的本质带回测试”。它在 Node、Bun 和 Deno 上运行方式相同，并自动检测 ESM、CommonJS 和 TypeScript。

**长按识别二维码查看原文**

https://poku.io/

Weslley Araújo

**InfiniteGrid 4.12：无限排列卡片元素的网格布局** — 一种成熟且已建立的方法，用于创建由不同大小的卡片元素组成的网格。适用于桌面和移动设备，并且有 React、Vue、Angular、Svelte 等集成。GitHub 仓库。

**长按识别二维码查看原文**

https://naver.github.io/egjs-infinitegrid/

NAVER

**🤖 Micro Agent：一个为你编写代码的 AI 代理** — 一个基于 Node.js 的工具，它首先编写测试用例，然后迭代解决方案直到测试通过。

**长按识别二维码查看原文**

https://github.com/BuilderIO/micro-agent

Builder․io

**Hyphenopoly v6.0：客户端断字的 Polyfill** — 如果用户代理或语言不支持 CSS 断字（这是 Baseline 的一部分，但支持情况各不相同），则对文本进行断字。一个有趣的 WebAssembly 用例。

**长按识别二维码查看原文**

https://github.com/mnater/Hyphenopoly

Mathias Nater

**simplex-noise.js：一个快速的 Simplex 噪声实现** — 小巧、独立且快速，你可以在这样的酷炫演示中使用它，或者将其应用于图像或其他数据的逼真颗粒/噪声效果。

**长按识别二维码查看原文**

https://github.com/jwagner/simplex-noise.js

Jonas Wagner

**Maska v3.0：零依赖的输入掩码库** — 首页上有几个演示。轻量且独立于框架，但提供 Vue 2/3、Alpine.js 和 Svelte 的集成。GitHub 仓库。

**长按识别二维码查看原文**

https://beholdr.github.io/maska/v3/\#/

Form․io

**版本发布：**

- **ESLint v9.7.0** – 支持 ES2025 中正则表达式的重复捕获组。Duy Ng 还分享了一些 迁移到 ESLint 9+ 的技巧。

- **Boa v0.19** – 一个用 Rust 编写的 JS 引擎，用于嵌入其他项目。

- **Meteor v3.0** – 用于实时应用的全栈框架。

- **jQuery v4.0 Beta 2、htmx v2.0.1、swc v1.7**

- **Wasp v0.14** – Wasp 是一个类似 Rails 的框架，适用于 React、Node.js 和 Prisma。

- **PKI.js v3.2** – 纯 JS 库，用于处理公钥系统。包括证书、签名等。

- **📷 Vision Camera v4.5** – 用于 React Native 的高级相机控制。

- **AlaSQL.js v4.5** – 同构 JavaScript SQL 数据库。

- **Eruda v3.2** – 移动浏览器的控制台/开发工具。

- **MUI X v7.10** – 流行的 React 组件套件。

🙋🏻‍♀️