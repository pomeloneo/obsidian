# JavaScript 中文周刊 #50 - Bun 是否会颠覆整个 JS 生态？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247509079&idx=1&sn=63ecaea19faf22749d18331f36e12747&chksm=e921efb5de5666a30788fbfce50eccb52e4e0bc9c9e58b69d7fb56e668bb2ccd148a2c025fa8\#rd  
> 抓取时间: 2026/2/2 23:52:56

---

> 本期看点：本期为大家带来了用 Rust 创建一个自己的 JavaScript 运行时与 Bun 是否会颠覆整个 JS 生态？等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、zy941002、TimLi777、Matrixbirds

## 🔥 本周热门

**用 Rust 创建一个自己的 JavaScript 运行时** — Bun、Rhino、Deno、Node，以及 Blueboat 等越来越多的 JavaScript 运行时出现，如果你想要拥有一个自己的 JavaScript 运行时，那么可以看看这篇文章。本文将教你使用 Rust 结合 V8 与 Tokio 快速创建一个 JavaScript 运行时。

**长按识别二维码查看原文**

https://deno.com/blog/roll-your-own-javascript-runtime

Bartek Iwańczuk

**Bun 是否会颠覆整个 JS 生态？** — 作者对 Bun 的能力和潜力进行了较深度的分析，认为虽然 Bun 现在还处在实验阶段，但是未来潜力无穷。

**长按识别二维码查看原文**

https://www.lunasec.io/docs/blog/bun-first-look/

Forrest Allison

**Douglas Crockford：“我们今天对 JavaScript 能做的最好的事情就是让它退役。”** — 这是对《JavaScript: The Good Parts》的作者，也是 JSON 的创造者 —- Douglas Crockford 的采访文章, 里面讲到了经常阅读团队其他人代码的好处、为什么我们需要更好的语言，以及他将不会再写 JavaScript 。

**长按识别二维码查看原文**

https://evrone.com/douglas-crockford-interview

Evrone

**15 个 JavaScript 初学者会犯的错误** — 这篇是我们对 James 的约稿。他还有很多精彩的 **JavaScript 视频**。

**长按识别二维码查看原文**

https://www.jamesqquick.com/blog/15-common-beginner-javascript-mistakes/

James Quick

**快讯：**

- 如果你好奇为什么维基全系列产品现在都使用 Video.js 来播放他们的视频，那么可以来看看 **这篇文章**。
    
    **长按识别二维码查看原文**
    
    https://diff.wikimedia.org/2022/07/27/wikimedia-media-playback-now-brought-to-you-with-video-js/
    

- 「TC39er」播客终于回归。最新一期的主题是：对来自 Deno 核心团队 Luca Casonato 的采访，**这一期讨论了 Deno、TC39 以及其他语言规范**。
    
    **长按识别二维码查看原文**
    
    https://tc39er.us/posts/episode-20-luca-casonato/
    

- ⚛️ Max Rozen 收集了许多 **大型真实 React 网站/应用**，必须收藏！
    
    **长按识别二维码查看原文**
    
    https://maxrozen.com/examples-of-large-production-grade-open-source-react-apps
    

- 🖼 **Storybook 7.0 新样式设计前瞻**
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/storybook-7-0-design-sneak-peek/
    

## 📒 教程与趣事

**你所必须知道的关于 Import Maps 的那些事** — **Import maps** 提供了一种控制 JavaScript 导入的方法，因此类似 `import moment from "moment"` 的语法也可以正确引入。这尽管缺乏 Firefox 和 Safari 的官方支持（尽管 polyfill 可用），但它们也已经开始在很多的地方使用。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/import-maps/

Ayooluwa Isaiah

**Qwik 如何提升 JavaScript 框架性能** — Angular 初代作者 Misko Hevery 指出他的新项目解决了一个长期存在的问题：**Qwik** 是一个承诺 “即时” 应用程序的 JavaScript 框架。如果你对此感到兴趣，你可以看看 **他的介绍性演讲**，或许这很有说服力。

**长按识别二维码查看原文**

https://thenewstack.io/misko-hevery-on-why-qwik-will-improve-javascript-frameworks/

Starr Campbell (The New Stack)

**🪄  使用 TypeScript 从字符串文字类型中提取参数类型** — 如果 TypeScript 的类型系统可以做的事情给您留下深刻印象或让您感到困惑，那么这篇精彩的文章会给你一个涡轮增压的剂量……！

**长按识别二维码查看原文**

https://lihautan.com/extract-parameters-type-from-string-literal-types-with-typescript/

Tan Li Hau

**使用 Preact 和 Fuse 为 Astro 写一个模糊搜索的组件**

**长按识别二维码查看原文**

https://www.lloydatkinson.net/posts/2022/writing-a-fuzzy-search-component-with-preact-and-fuse-for-astro/

Lloyd Atkinson

**我从 Rust 到** **TypeScript 的旅程笔记？** — 这不是单向道。

**长按识别二维码查看原文**

https://blog.chiselstrike.com/notes-from-my-journey-from-rust-to-typescript-9bd9d28141e3?gi=876d62715d54

Glauber Costa

## 🛠 代码与工具

**Blueboat: 一个多合一的 Serverless JavaScript 运行时** — 如果你使用过 Cloudflare Workers，它们有相似的设计思路。Blueboat 会把 V8，进程级的快照和 Rust 整合再一起，为 JavaScript 提供多租户的安全迅速的运行环境。

**长按识别二维码查看原文**

https://blueboat.io/

Heyang Zhou

**Skeleton: 一个开箱即用的 Svelte UI 组件库** — Svelte + Tailwind 打造的 Skeleton 非常友好。有大量的实例程序和文档。

**长按识别二维码查看原文**

https://skeleton.brainandbonesllc.com/

Brain and Bones, LLC

**simplex-noise.js 4.0: 一个高性能的 Simplex 噪声实现** — 包体体积小，且完全独立的高性能噪声库，你可以直接用 这个酷炫的示例程序体验，也可以对图片或其他数据应用有说服力的颗粒或者噪声。

**长按识别二维码查看原文**

https://github.com/jwagner/simplex-noise.js

Jonas Wagner

**AST Explorer: 一个在线分析 JavaScript 语法结构的工具** — 一个基于 Web 实现，用于查看 JavaScript 代码转换成语法树的工具。

**长按识别二维码查看原文**

https://astexplorer.net/

Felix Kling

**版本发布：**

- **Article Parser v7.0** – 基于 Nodejs 实现的根据 URL 提取文章内容的组件库。

- **React Simple Maps v3.0** – 用 React 实现的美化 SVG 的 map 应用。

- **Emoji Mart v5.2** – Emoji 选择器组件。

- **hls.js v1.2** – 用于解析直播视频流的 JavaScript 组件库。

- **MicroDiff v1.3 –** 零依赖用于对象和数组的对比 diff 的组件库。

- **Temporal JavaScript SDK v1.0** – 基于持久化可执行代码平台的 JavaScript SDK。

- **Impress.js v2.0** – 基于 JavaScript + CSS3 的 PPT 框架。

- **Lerna v5.3** – 基于 monorepo 的一个包管理工具，用于管理包含多个软件包。

- **Mongoose v6.5** – 基于 Node.js 的 MongoDB ODM 框架。

- **NodeBB v2.3** – 基于 Node.js 的论坛应用程序。

- **Jasmine v4.3** – 流行的 JavaScript 测试框架。

- **Node.js v18.7.0**

❓ **你知道吗?**

- 👴🏻 从 JavaScript 的周刊于 2010 年 11 月开始发布，直至本期已经是第 600 期了。当年是奥巴马担任总统的第一个任职期，iPad 发布不到一年，同时 Express.js 才刚刚发布。我很期待当第 1000 期的时候，又会有什么事件发生。

## 🙋🏻‍♀️