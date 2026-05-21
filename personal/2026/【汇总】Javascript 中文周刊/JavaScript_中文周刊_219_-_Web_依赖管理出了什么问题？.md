# JavaScript 中文周刊 #219 - Web 依赖管理出了什么问题？

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545545&idx=1&sn=9488a14aaa956fdff897638b8bfc3788&chksm=e921792bde56f03d0c498030a17da450a9d2d88789acc7784fbf4f5337cbbecb8dc47edf4f01#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545545&idx=1&sn=9488a14aaa956fdff897638b8bfc3788&chksm=e921792bde56f03d0c498030a17da450a9d2d88789acc7784fbf4f5337cbbecb8dc47edf4f01#rd)

> 抓取时间: 2026/2/2 23:49:19

---

> 本期看点：Lea Verou 深入分析 Web 平台依赖管理的根本问题，Temporal API 在 Chrome 144 中正式支持全部功能，TypeScript 简洁指南，memlab v2.0 内存泄漏检测工具，State of HTML 2025 年度调查结果。

> 编辑：TimLi

🔥 本周热点

**Web 依赖管理出了什么问题？** —— Web 平台的依赖管理存在根本性问题：依赖管理应该是平台的基础功能，而不应该依赖于打包工具。Lea Verou 深入分析当前方案的不足（直接部署 node_modules、使用 CDN、import maps 等），并提出改进方向：依赖管理应像 Node.js、Python、Rust 那样成为一等公民，让开发者能够直接安装并使用依赖，而不是被迫使用打包器。

**长按识别二维码查看原文**

[https://lea.verou.me/blog/2026/web-deps/](https://lea.verou.me/blog/2026/web-deps/)

Lea Verou

**快讯：**

- 📺 React Conf 2025 全部视频上线，包括 25 场演讲和 23 场采访，还能看到 核心团队的四位成员同场对谈。
    
    **长按识别二维码查看原文**
    
    [https://conf.react.dev/](https://conf.react.dev/)
    

- Deno 和 Oracle 的 JavaScript 商标纠纷有了小进展，Oracle 申请延长 60 天，Deno 也同意了。看起来这案子能拖到 2027 年。
    
    **长按识别二维码查看原文**
    
    [https://bsky.app/profile/deno.land/post/3mbuirnjqxc22](https://bsky.app/profile/deno.land/post/3mbuirnjqxc22)
    

- 📘 The Concise TypeScript Book 是一本简明、精炼的 TypeScript 指南，完全免费开放阅读。
    
    **长按识别二维码查看原文**
    
    [https://github.com/gibbok/typescript-book](https://github.com/gibbok/typescript-book)
    

📖 文章与视频

**Date 已经过时，Temporal 正在崛起** —— Temporal API 被许诺要解决 JavaScript 中 `Date` 的各种坑，这事已经说了好些年，现在终于真的快要了！Mat 用不少实例详细对比了 `Date` 的缺陷，强调了 Temporal 的优势。

**长按识别二维码查看原文**

[https://piccalil.li/blog/date-is-out-and-temporal-is-in/](https://piccalil.li/blog/date-is-out-and-temporal-is-in/)

Mat "Wilto" Marquis

**💡 Temporal 目前在 浏览器中的支持 还不算理想，但 Chrome 144 这周刚好正式支持了全部功能。如果你等不及，也可以用 Temporal Polyfill 过渡下。**

**长按识别二维码查看原文**

[https://caniuse.com/temporal](https://caniuse.com/temporal)

**JavaScript 的日期计算会出多大幺蛾子？** —— **"有个我自己踩到的 date 问题，一旦 Temporal 普及起来就好解决多了。"**

**长按识别二维码查看原文**

[https://philna.sh/blog/2026/01/11/javascript-date-calculation/](https://philna.sh/blog/2026/01/11/javascript-date-calculation/)

Phil Nash

**别什么都往数组里塞（多用迭代器，代码更高效）** —— 本文介绍了 **iterator helpers** 这个新特性，能帮你懒加载数据，按需处理，比数组遍历高效不少，而且现在支持的环境也蛮多。

**长按识别二维码查看原文**

[https://allthingssmitty.com/2026/01/12/stop-turning-everything-into-arrays-and-do-less-work-instead/](https://allthingssmitty.com/2026/01/12/stop-turning-everything-into-arrays-and-do-less-work-instead/)

Matt Smith

**怎么"偷"一个 React 组件** —— 原理揭秘：如果你想复刻某个线上 React 应用程序的组件，没源码也不是不行。通过理解 React 的内部结构（比如 Fiber）、结合 LLMs 等工具，还真能还原个差不多。

**长按识别二维码查看原文**

[https://fant.io/react/](https://fant.io/react/)

David Fant

**📄 JavaScript 的** `**for**`**-**`**of**` **循环其实挺快的** Suren Enfiajyan

**长按识别二维码查看原文**

[https://waspdev.com/articles/2026-01-01/javascript-for-of-loops-are-actually-fast](https://waspdev.com/articles/2026-01-01/javascript-for-of-loops-are-actually-fast)

**📄 为啥 ARM 里有个"JavaScript 指令"？** —— 其实就是 `FJCVTZS` 这条指令。NotNotP

**长按识别二维码查看原文**

[https://notnotp.com/notes/til-why-arm-has-a-js-instruction/](https://notnotp.com/notes/til-why-arm-has-a-js-instruction/)

**📄 我是怎么用 lit-html 写自定义元素的** Dave Samaniego

**长按识别二维码查看原文**

[https://frontendmasters.com/blog/custom-elements-with-lit-html/](https://frontendmasters.com/blog/custom-elements-with-lit-html/)

**📄** `**document.currentScript**` **比你想象得有用** Chris Coyier

**长按识别二维码查看原文**

[https://frontendmasters.com/blog/document-currentscript-is-more-useful-than-i-thought/](https://frontendmasters.com/blog/document-currentscript-is-more-useful-than-i-thought/)

**📄 WebAssembly 的前世今生** Emnudge

**长按识别二维码查看原文**

[https://emnudge.dev/blog/what-happened-to-webassembly/](https://emnudge.dev/blog/what-happened-to-webassembly/)

**memlab v2.0：发现 JavaScript 内存泄漏的利器** —— 这是 Facebook 开源的一套测试和分析工具，专门帮你查找内存泄漏和性能优化机会。写好测试场景后，memlab 就能自动对比内存快照，帮你过筛子，把内存问题揪出来。

**长按识别二维码查看原文**

[https://facebook.github.io/memlab/](https://facebook.github.io/memlab/)

Facebook Open Source

**Fabric.js v7.1：强大的 SVG 抽象库** —— 给 HTML5 canvas 加一层交互式模型，用起来更轻松了。无论浏览器还是 Node 环境都能搞。

**长按识别二维码查看原文**

[https://github.com/fabricjs/fabric.js](https://github.com/fabricjs/fabric.js)

Fabric.js

**Ohm：JavaScript & TypeScript 的语法解析工具** —— 这个项目前几年介绍过，现在已经进化了不少。Ohm 用 PEG 构建解析器，可用于解释器、编译器、分析工具等，还能 在线玩 grammar。

**长按识别二维码查看原文**

[https://ohmjs.org/](https://ohmjs.org/)

Warth、Dubroy 等人

**Superdiff v3.2：对比两个数组或对象，找出差异** —— 有两个超像的对象或数组，想快速看区别？Superdiff 现在性能更强了，还支持数据流输入，并能用 worker 单独线程高效 diff。

**长按识别二维码查看原文**

[https://github.com/DoneDeal0/superdiff](https://github.com/DoneDeal0/superdiff)

antoine

📢 其他生态

一些领域的新鲜事儿：

- 🤖 Linus Torvalds 最近也在"vibe coding"了，开始玩 Google 的 Antigravity 工具，还用它 造了点数字音效。
    
    **长按识别二维码查看原文**
    
    [https://www.zdnet.com/article/linus-torvalds-vibe-coding-ai/](https://www.zdnet.com/article/linus-torvalds-vibe-coding-ai/)
    

- GitHub 计划 2026 年为 npm 包引入"分阶段发布"，上线前多一步审核，防止意外上线漏洞包。
    
    **长按识别二维码查看原文**
    
    [https://javascriptweekly.com/link/179168/web](https://javascriptweekly.com/link/179168/web)
    

- 🗓️ Astro 团队发布 了 2025 年年度回顾，这一年对他们来说收获超大。
    
    **长按识别二维码查看原文**
    
    [https://astro.build/blog/year-in-review-2025/](https://astro.build/blog/year-in-review-2025/)
    

- Anil Dash 讲了 Markdown 如何统治了世界的故事。
    
    **长按识别二维码查看原文**
    
    [https://www.anildash.com/2026/01/09/how-markdown-took-over-the-world/](https://www.anildash.com/2026/01/09/how-markdown-took-over-the-world/)
    

- State of HTML 2025 年度调查结果 已经可以看啦。
    
    **长按识别二维码查看原文**
    
    [https://2025.stateofhtml.com/en-US/](https://2025.stateofhtml.com/en-US/)
    

- 最近发现 Deno（JavaScript 运行时）已经能在 Python 的 PyPI 上分发了，这样 Python 应用程序调用 JS 更方便。
    
    **长按识别二维码查看原文**
    
    [https://github.com/denoland/deno/issues/31254](https://github.com/denoland/deno/issues/31254)
    

- 2025 年，Bun 成为 JavaScriptCore（Safari 和 Bun 的 JS 引擎）第三大贡献者。
    
    **长按识别二维码查看原文**
    
    [https://x.com/bunjavascript/status/2010933884196962724](https://x.com/bunjavascript/status/2010933884196962724)
    

**版本发布：**

- **Node.js 2026 年 1 月 13 日安全更新** —— 按计划终于发了 v20.x、22.x、24.x、25.x 的安全补丁，一次性修复了 5 个漏洞。

- **Bun v1.3.6** —— `Bun.Archive` 现在支持操作 tar 包，`Bun.JSONC` 支持解析带注释的 JSON，还有不少性能提升和小优化。

- **pnpm v10.28** —— 这个高效包管理器加入了 `beforePacking` 钩子，可以在发布时自定义 `package.json` 内容。

- **Angular 21.1** 本周预计发布，上周 rc0 已经上线，小伙伴们可以抢先体验。

- **Ember 6.9**、**ESLint v10.0.0 RC0**、**Rspack 1.7**

- **JavaScriptKit v0.38** —— Swift 框架，用于通过 WebAssembly 操作 JavaScript。

- 🎵 **alphaTab v1.8** —— 音乐记谱、吉他谱渲染的超酷库。

- **Neo.mjs v11.20** —— 多线程 Web 应用程序引擎。

- **Monio v0.70.0** —— Kyle Simpson 的 IO monad 实现。

- **Ant Design v6.2** —— UI 设计体系和 React 组件库大更新。

- **xstyled v4.1** —— React 的 CSS-in-JS 工具包，主打工具式和高可维护性。

- **Jint v4.5** —— .NET 平台上的 JavaScript 解释器。