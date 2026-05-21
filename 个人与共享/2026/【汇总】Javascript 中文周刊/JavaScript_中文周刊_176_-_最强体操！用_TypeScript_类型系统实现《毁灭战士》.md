# JavaScript 中文周刊 #176 - 最强体操！用 TypeScript 类型系统实现《毁灭战士》

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540423&idx=1&sn=012e755d75416bfc0c9943eeb109195a&chksm=e9211525de569c33aee63e42e7f04838125f30d555372f1526c1e52d2d4d040796b821a0ab31\#rd  
> 抓取时间: 2026/2/2 23:50:17

---

> 本期看点：开发者用 TypeScript 类型系统成功运行《毁灭战士》，Bun v1.2.3/v1.2.4 发布并提升构建性能，TypeScript 入门指南，Next.js v15.2 推出新调试体验，Chromium 团队推进 Observable API。

> 编辑：TimLi

🔥 本周热点

**开发者用 TypeScript 类型系统实现了《毁灭战士》** —— TypeScript 类型系统有一个有趣的特性：它是图灵完备的，这让一些开发者尝试完全用类型系统来实现应用程序。一位开发者花了 18 个月时间，生成了 177TB 的类型定义，成功让 1993 年的《毁灭战士》在其中运行。这个项目既荒谬又令人惊叹，他在这个广受好评的 7 分钟视频中解释了项目细节 👏

**长按识别二维码查看原文**

https://socket.dev/blog/typescript-types-running-doom

Sarah Gooding（Socket）

**Bun v1.2.3 和 v1.2.4 发布** —— 这个基于 JavaScriptCore 的运行时正在快速发展。v1.2.3 增强了前端开发服务器功能（运行 `bun ./index.html` 就能自动完成所有打包工作）。现在可以使用 `bun init` 创建新的 React 项目。同时，Bun v1.2.4 将 macOS 应用程序的构建速度提升了 60%，macOS 可执行文件现在也支持代码签名了。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.2.3

Jarred Sumner 等

**TypeScript 是什么？JavaScript 程序员必读指南** —— 你可能注意到了，备受尊敬的 JavaScript 开发者和作者 Dr. Axel 最近一直在深入研究 TypeScript。在这篇文章中，他很好地总结了 TypeScript 的”是什么”（而不是”为什么”）。即使你不打算使用它，这也是一份很好的入门指南，因为你迟早会在某处遇到它。

**长按识别二维码查看原文**

https://2ality.com/2025/02/what-is-typescript.html

Dr. Axel Rauschmayer

**快讯：**

- ⭐ Chromium 团队正在推进 Observable API 的发布。这对像 RxJS 这样的库来说是一个重大进展。
    
    **长按识别二维码查看原文**
    
    https://groups.google.com/a/chromium.org/g/blink-dev/c/stxSgTgMHog
    

- 📊 BenchJS 是一个值得尝试的在线 JavaScript 基准测试沙盒。
    
    **长按识别二维码查看原文**
    
    https://benchjs.com/
    

- JavaScript 的记录和元组提案（目前在 TC39 的第 2 阶段）取得了新进展。你可以在这里体验这个特性。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-record-tuple/issues/393
    

- Windows 95 in Electron 正如其名，是在 Electron 应用程序中运行的 Windows 95！v4.0 版本添加了 Office 95 和 IE 5.5，可以进行（有限的）网页浏览。
    
    **长按识别二维码查看原文**
    
    https://github.com/felixrieseberg/windows95/releases/tag/v4.0.0
    

- 📊 2024 年 React Native 现状调查结果已经发布。
    
    **长按识别二维码查看原文**
    
    https://results.stateofreactnative.com/en-US/
    

📒 教程与趣事

**2025 年值得关注的 React 库** —— 多产的 React 博主 Robin 每年都会更新他的 React 生态系统必备库清单。他涵盖了从项目创建和包管理，到状态管理、动画、表单创建、身份验证和国际化等多个方面。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-libraries/

Robin Wieruch

**使用可变堆数字为 V8 引擎提速** —— V8 团队使用 JetStream2 基准测试套件来研究性能问题，并实现了一个新的优化方案，不仅让 `async-fs` 基准测试性能提升了 2.5 倍，其他方面也有显著改进。

**长按识别二维码查看原文**

https://v8.dev/blog/mutable-heap-number

Victor Gomes（V8）

**使用弱引用颠覆控制流** —— 弱引用与普通引用的不同之处在于，它不会阻止被引用对象被垃圾回收。大多数现代 JavaScript 运行时都支持弱引用，James 展示了它们的实用之处。

**长按识别二维码查看原文**

https://jlongster.com/subverting-control-weak-refs

James Long

**⭐ JIT（即时编译）如何让 JavaScript 更快** Royal Bhati

**长按识别二维码查看原文**

https://www.royalbhati.com/posts/why-js-is-fast

**📄 在浏览器中使用 AI 进行拼写修正** —— 探索 Chrome 最新的 AI 功能。Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2025/02/27/using-ai-in-the-browser-for-typo-rewriting

**📄 给普通开发者的 JavaScript 引擎 JIT 漏洞入门** Josiah Pierce

**长按识别二维码查看原文**

https://trustfoundry.net/2025/01/14/a-mere-mortals-introduction-to-jit-vulnerabilities-in-javascript-engines/

**📄 如何在 Vue 中使用 Vitest 进行视觉回归测试** Alexander Opalic

**长按识别二维码查看原文**

https://alexop.dev/posts/visual-regression-testing-with-vue-and-vitest-browser/

**📄 为什么我们放弃了 Next.js 并从未后悔** Stewart 和 Snelling

**长按识别二维码查看原文**

https://northflank.com/blog/why-we-ditched-next-js-and-never-looked-back

**📄 使用 Angular 和原生联邦实现微前端** Manfred Steyer（Angular Blog）

**长按识别二维码查看原文**

https://blog.angular.dev/micro-frontends-with-angular-and-native-federation-7623cfc5f413?gi=82353e9f14b3

🛠 代码与工具

**Svelvet v11：使用 Svelte 构建基于节点的 UI** —— 这是一个成熟的 Svelte 组件库，用于创建交互式的基于节点的 UI 和图表。v11 版本添加了在”网格对齐”和自由模式之间切换的功能，用于操作元素。（主页底部有在线演示。）

**长按识别二维码查看原文**

https://svelvet.mintlify.app/introduction

Open Source Labs

**React Native v0.78 发布** —— 这是 React Native 的一个重要版本，它支持了 React 19（升级时需要进行一些调整），并有一些其他小改进。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2025/02/19/react-native-0.78

Novak、Cucci、Gupta 和 Cipolleschi（Meta）

**Random：可设定种子的随机数生成器** —— 除了 `Math.random`，这个库还提供了更多功能，可以轻松创建各种类型的随机值，并支持不同的分布（如正态分布、伯努利分布、泊松分布、帕累托分布和韦伯分布）。

**长按识别二维码查看原文**

https://github.com/transitive-bullshit/random

Travis Fischer

**QuickJS Sandbox v2.0：在 QuickJS 驱动的沙盒中执行 JS/TS** —— QuickJS 是 Fabrice Bellard 开发的一个小型、可嵌入的 JavaScript 引擎，这个扩展让它能够在隔离的沙盒环境中轻松运行代码，并提供了基本的 Node 模块支持和虚拟文件系统。GitHub 仓库。

**长按识别二维码查看原文**

https://sebastianwessel.github.io/quickjs/

Sebastian Wessel

📢 其他

以下是开发者生态圈中一些其他有趣的更新和实用资源：

- 还记得 Ajax 吗？这个将异步 JavaScript 和服务器动态更新等多种技术结合在一起的流行术语，是在 20 年前的这个月在这篇文章中首次提出的。
    
    **长按识别二维码查看原文**
    
    https://en.wikipedia.org/wiki/Ajax_(programming
    

- 🤖 让 LLM 为你的图片写 `alt` 文本可行吗？ Dries Buytaert 对几个模型进行了测试。
    
    **长按识别二维码查看原文**
    
    https://dri.es/comparing-local-llms-for-alt-text-generation
    

- GitHub 正在涉足 AI 开发者助手领域，展示了其新的 Copilot “代理模式”预览版。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode
    

- 🌊 深入了解使用 WebGPU 实现高性能实时流体模拟的技术。
    
    **长按识别二维码查看原文**
    
    https://tympanus.net/codrops/2025/02/26/webgpu-fluid-simulations-high-performance-real-time-rendering/
    

- Electronic Arts 通常不会开源旧游戏，但他们刚刚开源了 1996 年的《红色警戒》，这是即时战略游戏类型的先驱之一。
    
    **长按识别二维码查看原文**
    
    https://github.com/electronicarts/CnC_Red_Alert
    

**版本发布：**

- **Next.js v15.2** —— 现在提供重新设计的调试体验，并实验性支持 React 的新视图过渡 API 和在中间件中使用 Node.js 运行时。

- **Astro v5.4** —— 现在支持远程图片优化和 Markdown 中的实验性响应式图片。

- **ESLint v9.21.0** —— 现在提供 `-ext` CLI 选项来检查特定扩展名的文件。

- **Ember.js v6.2**、**Angular v19.2**、**Node.js v23.9 (Current)**

- **PrimeVue v4.3** —— Vue 的 UI 组件套件，现在带有新的”主题设计器”工具，包括 Figma 到代码的功能。

- **📅React Big Calendar v1.18** —— 类似 Google Calendar/Outlook 的日历组件。现在支持 React 19。

- **InversifyJS v7.0** —— JavaScript 的控制反转容器。提供了 v6 到 v7 的升级指南。

- **React Markdown v10.0** —— 用于渲染 markdown 的组件。（演示）

- **fast-png v6.3** —— 纯 JavaScript 的 PNG 图像编解码器。

- **Mercurius v16.1** —— 在 Fastify 之上实现 GraphQL 服务器。

- **Varlet v3.9** —— 受 Material Design 启发的 Vue 3 组件库。

- **file-type v20.4** —— 检测文件、流或数据的文件类型。

- **FxTS v1.5** —— 面向 TS/JS 开发者的函数式库。