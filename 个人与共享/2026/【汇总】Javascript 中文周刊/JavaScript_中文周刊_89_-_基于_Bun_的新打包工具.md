# JavaScript 中文周刊 #89 - 基于 Bun 的新打包工具

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520463&idx=1&sn=789d7616e1e871467fd4eccf2add9fe5&chksm=e921db2dde56523bae4bb812e0ecf374dacd95331174efbf1bbda2259e91cf321e23f4e31dfd\#rd  
> 抓取时间: 2026/2/2 23:52:03

---

> 本期看点：上周、Bun 发布了新打包工具、jQuery v3.7.0 发布、Hemanth.HM 分享了他维护的 ES2023 代码示例列表。

> 编辑：liu-jin-yi

## 🔥 本周热门

**基于 Bun 的新打包工具** — **Bun** 是最新的 JavaScript Runtime 之一，它建立在 JavaScriptCore 引擎之上，专注于速度，并旨在成为 Node.js 的可替代品。上周发布的 **v0.6.0** 是迄今为止最大的发布版本，其中包括独立可执行文件生成等功能，但是其新的 JavaScript 打包工具和压缩器可能会吸引更多的关注。本文深入探讨了其中的原因。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-bundler

Jarred Sumner

🤔 如果想阅读更多关于 Bun 打包器的测评，Shane O’Sullivan **已试用了新的打包工具并分享了他的想法**。在 Hacker News 也有一些**讨论**。虽然现在的 `esbuild` 已经足够快，但是在打包领域看到任何进展都是非常不错的。

**长按识别二维码查看原文**

https://shaneosullivan.wordpress.com/2023/05/17/using-bun-js-as-a-bundler/

**Deopt Explorer：一款用于检查 V8 跟踪日志信息的 VS Code 扩展程序** — 这是一份详尽的介绍微软新工具的文章，它能够分析 V8 引擎内部的结构，包括 CPU 分析数据、内联缓存的操作方式、去优化，以及函数的运行方式等等。文章内容丰富，值得一读。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/introducing-deopt-explorer/

Ron Buckton (Microsoft)

**jQuery v3.7.0 发布** — 😆 v3.7 版本将 Sizzle 选择器引擎合并到核心中，添加了一些无单位的 CSS 属性，增加了一个新的 `uniqueSort` 方法。

**长按识别二维码查看原文**

https://blog.jquery.com/2023/05/11/jquery-3-7-0-released-staying-in-order/

Timmy Willison (jQuery Foundation)

**⚡️ 快讯：**

- TC39 的 Hemanth.HM 开始维护了一个类似于他之前维护的 **ES2022**、**ES2021** 和 **ES2020** 代码示例列表的 **ES2023 代码示例列表**。
    
    **长按识别二维码查看原文**
    
    https://h3manth.com/ES2023/
    

- 🤔 The New Stack 发布了一篇关于 **Meta 支持 OpenJS Foundation** 的文章。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/meta-backs-the-openjs-foundation-for-greater-diversity/
    

- Meta / Facebook 的开发团队写了一篇文章，介绍了他们在 Messenger Desktop 中从 Electron 切换到 React Native 所带来的效率提升。**文章链接**
    
    **长按识别二维码查看原文**
    
    https://developers.facebook.com/blog/post/2023/05/17/messenger-desktop-faster-and-smaller-by-moving-to-react-native-from-electron/
    

- 诸如 Cloudflare Workers 这样的平台使用 V8 隔离机制存在一个缺点，即不支持打开 TCP sockets。如果你需要通过 TCP 与 RDBMS 等进行通信，将会是一个障碍。不过，Cloudflare Workers **引入了一个 connect() API**， 可用于在 Workers 函数中创建 TCP sockets。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/workers-tcp-socket-api-connect-databases/
    

- Promise.withResolvers **进入第二阶段**。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-promise-with-resolvers
    

## 📒 教程与趣事

**如何使 JavaScript 获得完整的类型支持** — 你可以通过 JSDoc 格式书写类型，TypeScript 编译器可以理解并提供类型检查，这样你就可以享受 TypeScript 的好处，同时仍然使用纯 JavaScript。

**长按识别二维码查看原文**

https://www.pausly.app/blog/full-type-support-with-plain-javascript

Pausly

TypeScript 的 JS 项目使用 TypeScript 页面 提供了更多关于类型支持的信息，介绍了从普通 JS 代码的类型推导到开启 `strict` 的完整 TypeScript 支持的不同严格程度的选择。

**长按识别二维码查看原文**

https://www.typescriptlang.org/docs/handbook/intro-to-js-ts.html

**▶  使用 JavaScript 编写一个可玩的国际象棋游戏** — 本教程不使用 canvas，而是利用 DOM、SVG 和 JavaScript 等技术实现。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Qv0fvm5B0EM

Ania Kubow

**你的 Jest 测试可能存在问题** — 你的 Jest 测试套件出了问题吗？你可能没有充分利用测试框架的功能，特别是在防止测试之间状态泄漏方面可能存在问题。

**长按识别二维码查看原文**

https://jamiemagee.co.uk/blog/your-jest-tests-might-be-wrong/

Jamie Magee

**使用 Playwright 进行可视化回归测试指南** — Playwright 浏览器控制库可以作为全 JavaScript 编写的端到端测试机制的基础，比较测试的视觉输出可以帮助定位问题所在。

**长按识别二维码查看原文**

https://lost-pixel.com/blog/post/playwright-visual-regression-testing

Dima Ivashchuk (Lost Pixel)

**React Server Components、Next.js App Router** — Addy Osmani 概述了 React Server Components、Next.js App Router 的实现、其他实现方式、向混合渲染的转变以及相关链接。

**长按识别二维码查看原文**

https://addyosmani.com/blog/react-server-components-app-router/

Addy Osmani

## 🛠 代码与工具

**VanJS：一款不使用 JSX 的 1.2KB 响应式 UI 框架** — 在这个竞争越来越激烈的领域中，VanJS 特别轻盈优雅，作者花费了大量的心血来记录并提供 **将 HTML 转换为其自定义格式的工具**。顺便提一下，VanJS 是 “vanilla JavaScript” 的缩写。**GitHub 代码库链接**。

**长按识别二维码查看原文**

https://vanjs.org/

Tao Xin

**Legend-State v1.0：更快的 React 状态管理库** — 又一个状态管理解决方案？经过一年的努力，Legend State 1.0 宣称在几乎所有指标上都是最快的选项，并且他们有 **基准测试结果来证明它**。无论如何，这篇详细的介绍都值得一看。**GitHub 代码库链接**

**长按识别二维码查看原文**

https://legendapp.com/open-source/legend-state-v1/

Moo․do

**Starry Night: 类似于 GitHub 的语法高亮工具** — 显然，GitHub 自己的语法高亮方法并不是开源的，但这个工具采用了类似的方法，而且它是开源的。尽管它因为使用了 Oniguruma 正则表达式引擎的 WASM 版本而有一些性能问题，但为了追求质量，这是必须的。

**长按识别二维码查看原文**

https://github.com/wooorm/starry-night

Titus Wormer

**Garph v0.5：一款适用于 TypeScript 的全栈 GraphQL 框架** — 这是一个“电池包含”的框架，无需代码生成即可提供全栈 GraphQL API。**GitHub 代码库链接**。

**长按识别二维码查看原文**

https://garph.dev/

Step CI

**headless-qr：一个简单、现代的 QR 代码库** — 这是一个较老项目的简化版本，去掉了不必要的额外代码。将二进制转换为图像是你的任务，或者如果你想要一个开箱即用的画布渲染的 QR 代码，可以使用 QRCode.js 。

**长按识别二维码查看原文**

https://github.com/Rich-Harris/headless-qr

Rich Harris

**Scroll Btween：使用滚动位置平滑过渡 DOM 元素的 CSS 值** — 滚动/视差库通常感觉相同，但这个库展示了一些多样化的例子，包括颜色、图像和文本，而且没有任何依赖。

**长按识别二维码查看原文**

https://olivier3lanc.github.io/Scroll-Btween/

Olivier Blanc

**eslint-plugin-check-file：用于保持文件和文件夹名称一致性的规则** — 该插件允许你在项目中强制执行一致的命名模式，包括文件和目录名称。

**长按识别二维码查看原文**

https://github.com/DukeLuo/eslint-plugin-check-file

Huan

**版本发布：**

- Gatsby v5.10

- Node.js v20.2

- Rome v12.1
    
    ↳ 格式化/检查工具现在支持第三阶段的装饰器语法。
    

- Ember.js v5.0
    
    ↳ 应用程序框架。
    

- Jasmine v5.0
    
    ↳ 测试框架。
    

- Transformers.js v2.0
    
    ↳ 可以直接在浏览器中运行 Hugging Face transformers。
    

- PrimeReact v9.4
    
    ↳ UI 组件库。
    

- The Lounge v4.4
    
    ↳ 跨平台的自托管 web IRC 客户端。
    

- Faast.js v8.0
    
    ↳ 简洁的无服务器批量计算工具。
    

## 😎 追随潮流

**js2flowchart.js** — 这是一个可将 JavaScript 代码转换成漂亮的 SVG 流程图的可视化库。如果你想玩一下，而又不想安装任何东西，可以使用在线版本。

**长按识别二维码查看原文**

https://github.com/Bogdan-Lyashenko/js-code-to-svg-flowchart

Bohdan Liashenko

## 🙋🏻‍♀️