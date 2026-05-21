# JavaScript 中文周刊 #152 - JavaScript 正则表达式的历史和未来

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534608&idx=2&sn=d21fb65c13f22e7c3d30138006fcaf5f&chksm=e92103f2de568ae44e27d9dd061efc641e30c5a2f449ec73ebb783275a4810c787fb2a2ae441\#rd  
> 抓取时间: 2026/2/2 23:50:48

---

> 本期看点：JavaScript 中的正则表达式支持一直有点令人失望，但情况已经有所改善。Steven 带我们回顾了一下正则表达式的进化历程，同时展示了他的 ‘regex’ 库，这个库将 JS 正则表达式提升到了真正的 A++ 级别。

> 编辑：TimLi

🔥 本周热点

**正则表达式的进化：JavaScript 中正则表达式的历史和未来** —— JavaScript 中的正则表达式支持一直有点令人失望，但情况已经有所改善。Steven 带我们回顾了一下正则表达式的进化历程，同时展示了他的 ‘regex’ 库，这个库将 JS 正则表达式提升到了真正的 A++ 级别。Steven 是 O’Reilly 出版的《正则表达式经典实例》和《高性能 JavaScript》的合著者，所以他在这方面很有发言权。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2024/08/history-future-regular-expressions-javascript/

Steven Levithan

**Node v22.7.0 (Current) 发布** —— Node 22.6 让你可以从源代码中剥离类型，现在通过 `--experimental-transform-types`，你还可以在运行之前将仅 TypeScript 语法转换为 JavaScript。模块语法检测现在也默认启用了。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.7.0

Rafael Gonzaga

**Bun v1.1.25：现在每秒运行 129 万个请求** —— 我在标题上开了个小玩笑，但这个基于 JavaScriptCore 的 JS 运行时的最新版本确实添加了 `node:cluster` 支持，并用这个在”Hello World”示例中展示了高水平的 HTTP 吞吐量。对 V8 的 C++ API 的支持也已经落地 —— 这很值得注意，因为 Bun 并不是基于 V8 的。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.1.25

Ashcon Partovi

**快讯：**

- 我们最近提到了 ECMASCript 2024，但 Pawel Grzybek 有一个简洁明了的 ES2024 规范新特性概述。
    
    **长按识别二维码查看原文**
    
    https://pawelgrzybek.com/whats-new-in-ecmascript-2024/
    

- 🐅 Wasp 会成为 “全栈 Web 开发的 JavaScript 版 Django” 吗？ Wasp 团队当然是这么认为的。
    
    **长按识别二维码查看原文**
    
    https://wasp-lang.dev/
    

- 🎙️ Node.js 和 Deno 的创造者 Ryan Dahl 参加了 Stack Overflow 播客，谈论了 Deno 目前的局限性以及 Deno 2.0 即将带来的内容。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.blog/2024/08/20/ryan-dahl-deno-20-scale-improve-npm-nodejs/
    

📒 教程与趣事

**50 个 TypeScript 错误** —— 这是一本标题略显生动的书，深入探讨了你可能在 TypeScript 中遇到的许多微妙错误。它在 Leanpub 上提供 PDF、iPad 和 Kindle 格式，或者你可以直接在它的 GitHub 仓库上阅读全文。至少值得浏览一下，看看你是否遇到过其中提到的任何问题。

**长按识别二维码查看原文**

https://leanpub.com/50-ts

Azat Mardan

**Redux 官方基础教程** —— 这份长期存在的指南教你如何正确使用流行的 Redux 状态容器以及最佳实践，现在进行了大幅改写。整个教程使用了 TypeScript，添加了新概念，并更多地涵盖了 RTK/React Toolkit 的特性。

**长按识别二维码查看原文**

https://redux.js.org/tutorials/essentials/part-1-overview-concepts

Redux 团队

**React 正在成为一个全栈框架** —— React 仅仅是一个前端库吗？后端如何融入其中？作者分享了是什么让他开始将 React 视为更像是一个全栈解决方案的想法。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-full-stack-framework/

Robin Wieruch

**📄 使用 JavaScript 生成器可视化算法** Alexander G. Covic

**长按识别二维码查看原文**

https://www.covicale.com/blog/using-javascript-generators-to-visualize-algorithms

**📄 通过异步块预加载优化 SPA 加载时间** Matteo Mazzarolo

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2024-08-13-async-chunk-preloading-on-load/

**📄 在 Angular v18.2 中使用** `**isolatedModules**` Thompson 和 Lyding (Angular 团队)

**长按识别二维码查看原文**

https://blog.angular.dev/using-isolatedmodules-in-angular-18-2-68a7d3a6c03d

**📄 如何在 JavaScript 应用程序中生成 PDF** Colby Fayock

**长按识别二维码查看原文**

https://spacejelly.dev/posts/generate-a-pdf-from-html-in-javascript

🛠 代码与工具

**Milkdown：插件驱动的所见即所得 Markdown 编辑器框架** —— 这是一个基于插件系统的轻量级所见即所得 Markdown 编辑器，能够实现高度定制。有趣的是，文档本身就是由这个编辑器渲染的。GitHub 仓库在此。

**长按识别二维码查看原文**

https://milkdown.dev/

Mirone

**Fuite 5.0：用于查找 Web 应用程序内存泄漏的工具** —— 这是一个 CLI 工具，你可以指向一个 URL 来分析内存泄漏。这里有它的工作原理。还有一个视频教程。

**长按识别二维码查看原文**

https://github.com/nolanlawson/fuite

Nolan Lawson

**LogTape：零依赖的简单日志库** —— 我很喜欢这种新风格的库，它承诺支持所有主要运行时（Node、Deno、Bun），以及边缘函数和浏览器开发工具。

**长按识别二维码查看原文**

https://github.com/dahlia/logtape

Hong Minhee

**📊 Chart.js v4.4：基于 Canvas 的 Web 图表** —— 这是那种感觉已经存在很久但仍然看起来新鲜并得到良好更新的库之一。柱状图、线图、面积图、气泡图、饼图、环形图、散点图和雷达图都可以轻松渲染。示例和 GitHub 仓库。

**长按识别二维码查看原文**

https://www.chartjs.org/

Chart.js 贡献者

**Legend State：小巧、快速和现代的 React 状态系统** —— 一年前，Jack Herrington 曾猜想 Legend State 可能是 ▶️ “终极状态管理器”，从那时起，它取得了很大进展，现在号称是最快的 React 状态库。

**长按识别二维码查看原文**

https://www.legendapp.com/open-source/state/v3/

Jay Meistrich

**Tagger：零依赖的原生 JavaScript 标签库** —— 你可以在这里试用实时演示。

**长按识别二维码查看原文**

https://github.com/jcubic/tagger

Jakub T. Jankiewicz

**tinykeys v3.0：~650 字节的键绑定库** —— 尽可能保持简单和精巧。

**长按识别二维码查看原文**

https://github.com/jamiebuilds/tinykeys

Jamie Kyle

**heic-to：在浏览器中将 HEIC/HEIF 图像转换为 JPEG 或 PNG**

**长按识别二维码查看原文**

https://github.com/hoppergee/heic-to

Hopper Gee

**版本发布：**

- **PlayCanvas Engine v2.0** – 强大的基于 JS 的 Web 图形平台。

- **Node v20.17.0 (LTS)** – Node 的 LTS 版本增加了对 `require` 同步 ESM 图的支持。

- **Astro v4.14** – 这个流行的通用内容站点框架现在包含了一个用于管理站点内容的实验性 API。

- pnpm v9.8, Vuetify v3.7, Neo.mjs v7.0

- **Cheerio v1.0** – Node 的 HTML/XML 操作库。

- **🎨 Chroma.js v3.0** – JavaScript 颜色操作库。

- **eta (η) v3.5** – 适用于 Node、Deno 和浏览器的嵌入式 JS 模板引擎。

- **Embla Carousel v8.2** – 具有流畅动效和良好滑动精度的轮播库。

- **d3-graphviz v5.6** – Graphviz DOT 渲染和动画过渡。

- **Alpine AJAX v0.9** – 用于构建服务器驱动前端的 Alpine.js 插件。

- **Happy DOM v15.0** – 不带 UI 的 Web 浏览器的 JS 实现。

- **Elliptic v6.5.7** – 纯 JS 实现的椭圆曲线密码学。

- **Poku v2.5** – 跨平台 JavaScript 测试运行器。

🙋🏻‍♀️