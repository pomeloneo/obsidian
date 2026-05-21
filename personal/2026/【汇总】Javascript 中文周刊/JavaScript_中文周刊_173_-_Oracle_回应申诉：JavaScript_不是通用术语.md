# JavaScript 中文周刊 #173 - Oracle 回应申诉：JavaScript 不是通用术语

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539710&idx=1&sn=4bb18be66c872f5c6bcd9da1bc796245&chksm=e921101cde56990a5fa0f257cbc4ebe11a8d00abebd466757cf2e92629da11c3e98529dab86c\#rd  
> 抓取时间: 2026/2/2 23:50:21

---

> 本期看点：Oracle 对 Deno 的 JavaScript 商标申诉作出回应，Chrome 即将推出新的 moveBefore DOM 方法并已被 React 采纳，Angular 纪录片发布讲述框架发展历程，Nx 为工作空间推出全新体验提升 TypeScript 支持，RE2JS v1.0 发布带来线性时间的正则表达式匹配。

> 编辑：TimLi

🔥 本周热点

**Oracle 声称”JavaScript”不是通用术语** —— 在这份驳回动议中，Oracle 对 Deno 试图证明 Oracle 不应持有 JavaScript™ 商标的申请做出回应，声称”相关消费者并不认为 JAVASCRIPT 是一个通用术语”（Oracle 是不是只把给它付钱的人当作相关消费者？）。这份回应中还包含了其他一些令人啼笑皆非的见解。

**长按识别二维码查看原文**

https://deno.com/blog/deno-v-oracle2

Ryan Dahl

**JavaScript 中拆分长任务的多种方法** —— 由于浏览器和事件循环的工作机制，让单个任务独占主线程会导致网站界面卡顿。Alex 通过一个简单的例子解释了这个问题，并详细对比了从基础的 `setTimeout()` 到 `requestAnimationFrame()`、Channel Messaging 和 Web Workers 等不同解决方案的优缺点。

**长按识别二维码查看原文**

https://macarthur.me/posts/long-tasks/

Alex MacArthur

**▶ Angular：纪录片** —— 这部新作来自制作过广受好评的 ▶️ Node.js 和 ▶️ Ruby on Rails 纪录片的团队，讲述了广受欢迎的 Angular（前身是 AngularJS）框架的起起落落，由一众 JavaScript 界的知名人士主演。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=cRC9DlH45lA

Honeypot

**快讯：**

- Chrome 即将推出新的 `moveBefore` DOM 方法，可以在不重置元素状态的情况下移动 DOM 树中的元素。React 已经在着手使用这个特性了。
    
    **长按识别二维码查看原文**
    
    https://chromestatus.com/feature/5135990159835136
    

- 想在 Vue 或 React 组件中写 PHP 代码吗？如果你是 Laravel 用户，可能会感兴趣。Aaron Francis 展示了一种实现方式。虽然目前还未开源，但他的演示非常酷。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/165467/web
    

- 是 Nx 用户吗？Nx 为其工作空间推出了全新体验，速度更快、效率更高，解决了大型 monorepo 中 TypeScript 编辑器支持的诸多问题。
    
    **长按识别二维码查看原文**
    
    https://nx.dev/
    

- Josh Goldberg 详细解释了 ESLint 和 TypeScript 的区别，不只是表面的那些。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/01/differences-between-eslint-and-typescript/
    

📒 教程与趣事

**2025 年该选择哪个富文本编辑器框架？** —— 一份当前活跃开发的所见即所得编辑器清单，可以直接集成到你的应用程序中。文章还详细分析了每个选项的优缺点。

**长按识别二维码查看原文**

https://liveblocks.io/blog/which-rich-text-editor-framework-should-you-choose-in-2025

Dexemple 和 Rowny（Liveblocks）

**如何用 TypeScript 发布基于 ESM 的 npm 包** —— 现在你几乎可以在任何地方使用 ES 模块了，是时候了解如何将它们打包发布到 npm 了。Axel 深入讲解了所有你需要知道的内容，还分享了一些实用工具。

**长按识别二维码查看原文**

https://2ality.com/2025/02/typescript-esm-packages.html

Dr. Axel Rauschmayer

**Deno 中的 WebAssembly 入门指南** —— 教你如何构建一个简单的 WASM 模块，并在 JavaScript 中调用 Rust 代码。

**长按识别二维码查看原文**

https://deno.com/blog/intro-to-wasm

Jiang 和 Sherret（Deno）

**在 Vite 中使用 TypeScript** —— 如果你已经用 Vite 创建了基于 JavaScript 的 React 项目，想要转向 TypeScript，这里有基本的步骤指南。

**长按识别二维码查看原文**

https://www.robinwieruch.de/vite-typescript/

Robin Wieruch

**📄 用 p5.js 构建有趣的定格动画光标** Jorge Toloza

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/02/06/building-a-playful-stop-motion-crayon-cursor-in-p5-js/

**📄 使用** `**npx is-my-node-vulnerable**` **确保 Node 应用程序安全** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/is-my-node-vulnerable

**📄 TypeScript 中的只读访问** —— 如何使用 `readonly` 关键字。Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/02/typescript-readonly.html

**📄 如何用 CSS 和 JavaScript 设置 WebGL 着色器颜色** Nicolas Mattia

**长按识别二维码查看原文**

https://www.nmattia.com/posts/2025-01-29-shader-css-properties/

🛠 代码与工具

**RE2JS v1.0：线性时间的正则表达式匹配** —— RE2 是 Google 开发的正则表达式引擎，设计目标是使执行时间与输入大小成正比，以避免回溯导致的所谓”ReDoS”问题。这个项目将这种保护机制带到了浏览器端。

**长按识别二维码查看原文**

https://github.com/le0pard/re2js

Oleksii Vasyliev

**Fuse.js v7.1：轻量级模糊搜索库，零依赖** —— 想要一个简单的搜索功能，又不想搭建专门的后端？这个成熟的解决方案可能适合你。这里有在线演示。

**长按识别二维码查看原文**

https://www.fusejs.io/

Kiro Risk

**🎨 tinygradient v2.0：渐变生成库** —— 在 JavaScript 中生成具有无限色标和步骤的颜色渐变。支持命名颜色、十六进制颜色、RGV、HSVa 和 RGB CSS 字符串。GitHub 仓库。

**长按识别二维码查看原文**

https://mistic100.github.io/tinygradient/

Damien Sorel

**parse-duration v2.0：将人类可读的时长转换为毫秒** —— 你可能会好奇为什么一个将 `1hr 20mins` 转换成 `4800000` 的库需要升级到 v2。实际上，它现在支持更多单位（`mo`、`mth`、`microsec` 和 `nanosec`），迁移到了 ESM，并支持本地化。

**长按识别二维码查看原文**

https://github.com/jkroso/parse-duration

Jake Rosoman

**Waveform Renderer** —— 快速从 MP3 或 WAV 文件创建可视化波形图，还可以编辑外观。可以看作是 Wavesurfer.js 的轻量级替代品。GitHub 仓库。

**长按识别二维码查看原文**

https://waveform-renderer.vercel.app/

Andres Felipe Alarcon

🎵 来点音乐…

纯 JavaScript 实现的 Protracker 模块播放器 —— 我特别喜欢 90 年代的音序器音乐、JavaScript 实验和酷炫的网页体验，这个项目三者兼具。如果你不了解音序器音乐，它是一种在网格上编写音乐的方式，通过触发样本播放来制作音乐。这段代码用纯 JavaScript 实现了解析和播放 Protracker 文件。（注：上图是原版 Protracker 应用程序的界面，这个实验更注重代码实现，界面相对简单。）

**长按识别二维码查看原文**

https://dittytoy.net/ditty/e910e130a3

srtuss

**版本发布：**

- **ES Module Shims v2.0** —— 在浏览器原生 ESM 支持的基础上，为 import maps 和其他 ES 模块特性提供 polyfill。

- **pnpm v10.2** —— 高效的替代包管理器。

- **Turborepo v2.4**

- **🍪 CookieConsent v3.1** —— 一个轻量级、纯 JS 的 GDPR 合规 cookie 同意机制，用来烦扰所有用户满足监管要求。

- **Happy DOM v17.0** —— 跨运行时的 JS 网页浏览器实现，不含 UI。现已支持 ES 模块。

- **remove-unused-vars v0.0.4** —— 一个实验性的代码未使用变量删除工具。

- **get-value v4.0** —— 使用属性路径（`a.b.c`）获取对象中的嵌套值。

- **mp4-muxer v5.2** —— 纯 TypeScript 实现的 MP4 复用器，支持 WebCodecs API、视频和音频。

- 🗺️ **react-map-gl v8.0** —— MapboxGL JS 的 React 友好 API 封装。演示。

- 🗓️ **Schedule-X v2.17** —— Material Design 风格的事件日历和日期选择器。

- **Wasp v0.16** —— Wasp 是一个类似 Rails 的框架，使用 Node、React 和 Prisma。

- **web-worker v1.5** —— 在浏览器和 Node 中提供一致的 Web Workers。

- **Js_of_ocaml (jsoo) v6.0** —— OCaml 到 JavaScript 的编译器。

- **RxDB v16.5** —— 为 JS 应用程序设计的离线优先、响应式数据库。