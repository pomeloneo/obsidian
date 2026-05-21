# JavaScript 中文周刊 #14 - TypeScript v4.5 正式版本发布！

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496188&idx=1&sn=d3da87e2a9f2c0610e870d148ddee94d&chksm=e921ba1ede563308c87474d150eda64f09c473a909a7eace813374b052e19dad1d498dab2e48#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496188&idx=1&sn=d3da87e2a9f2c0610e870d148ddee94d&chksm=e921ba1ede563308c87474d150eda64f09c473a909a7eace813374b052e19dad1d498dab2e48#rd)  
> 抓取时间: 2026/2/2 23:53:42

---

> 本期看点：上周，TypeScript v4.5 正式版本发布！新增了例如 Awaited 类型等诸多新特性。另外一则重磅消息是 React v18 Beta 发布，官方宣布正式版或将在 2022 年第一季度正式上线。

> 编辑：Yucohny、liu-jin-yi、QC-L

## 🔥 本周热门

**为什么使用 Webpack 5 后，构建速度慢了 15 倍？** — 本篇文章主要介绍了在 Webpack 5 中存在的一个由 `concat` 数组方法引起的性能问题，以及查找这个问题的详细过程。最终文章作者向官方提出 **isseus** 并得到修复。

**长按识别二维码查看原文**

https://engineering.tines.com/blog/understanding-why-our-build-got-15x-slower-with-webpack

Eoin Hennessy（Tines）

**Etsy 的 TypeScript 之旅** — 本篇文章主要介绍了在使用 TypeScript 重构 Etsy 过程中的技术选型以及所遇到的一些问题，我相信这是一篇不可多得的选型文章。

**长按识别二维码查看原文**

https://codeascraft.com/2021/11/08/etsys-journey-to-typescript/

Salem Hilal

**使用 esbuild 的一些注意事项！** — 作者 Julia Evans 讲述了她在学习使用 **esbuild** 过程中遇到的一些问题，并且提供了在 Vue 单独引入 esbuild 时的一些注意事项。

**长按识别二维码查看原文**

https://jvns.ca/blog/2021/11/15/esbuild-vue/

Julia Evans

**TypeScript v4.5 发布** — 就在 RC 发布的两周后，TypeScript 最终迎来了正式版本的发布！之前承诺的对 Node 的 ESM 的支持现在也变成了 **实验性** 的功能。最终版本取消了条件类型的尾递归，同时添加了一些新特性。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-5/

Daniel Rosenwasser（Microsoft）

**React v18 Beta 发布** — 官方在 Twitter 上宣布 React v18 Beta 发布，正式版本将于 2022 年第一季度发布。

**长按识别二维码查看原文**

https://github.com/reactwg/react-18/discussions/112

React Working Group

**快讯：**

- **Kent C Dodds 加入了 Remix 团队** – **Remix** 是一个很有发展前景的框架，并且将于下周一开源（你可以在此处了解 更多关于它的内容）。

**长按识别二维码查看原文**

https://kentcdodds.com/blog/how-i-help-you-build-better-websites

- 如果你对 serverless 平台感兴趣，那么你可以看看 **Cloudflare Workers**，其 Wrangler **v2 版本** 已经发布，其 **Durable Objects 存储系统** 也进入了 GA 阶段，以及新的 **Services abstraction** 也以上线，另外，Workers 也**支持 ES 模块**。

**长按识别二维码查看原文**

https://workers.cloudflare.com/

- 现在由 GitHub 管理的 npm 注册表上 **存在一个很大的安全漏洞**，攻击者理论上有可能在未经适当授权的情况下“发布任何 npm 包的新版本”。

**长按识别二维码查看原文**

https://github.blog/2021-11-15-githubs-commitment-to-npm-ecosystem-security/\#security-issues-related-to-the-npm-registry

- **Ember v4.0** 已经发布，但是并没有在他们的官方博客或 Twitter 上进行通知。更多 **关于他们的 v4 进程的信息** 可以在这里查看。

**长按识别二维码查看原文**

https://github.com/emberjs/ember.js/releases/tag/v4.0.0

- Netlify 已经 **筹集了 1.05 亿美元**，将加倍投入在 Jamstack 生态系统上，并且希望能增加 Cassidy Williams 上的预算。😊

**长按识别二维码查看原文**

https://www.netlify.com/press/netlify-raises-usd105-million-to-transform-development-for-the-modern-web

**版本发布：**

**Tagify v4.9** – 优雅的标签输入组件。

**Vuetify v2.6** – 为 Vue 打造的 Material 组件框架。

**execa v6.0** – 一个更好的 Node 进程启动器。

**Plottable v3.12.0** – D3.js 上的模块化图表组件。

**Teaful v0.8** – 微型 React 状态库。

**Dann.js v2.4** – 神经网络库。

**Electron.js v16**

## 📖 教程与趣事

**如何使用 React Three Fiber 构建 3D 场景？** — 如果你想通过 React 在浏览器中构建整洁的 3D 可视化效果，可以点开看看。

**长按识别二维码查看原文**

https://varun.ca/modular-webgl/

Varun Vachhar

**用于现代 Web 开发的强大命令行工具** — 你最喜欢的命令行工具是什么？在这篇博文中，Louis 分享了他在过去几年中遇到的一系列相关命令行应用程序和实用程序。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/11/powerful-terminal-commandline-tools-modern-web-development/

Louis Lazaris

**使用 Web Workers 提升第三方脚本性能** — 尽管 Partytown 是一个仍在试验中的库，但是依然可使用 Web Worker 技术来提高第三方脚本的性能。

**长按识别二维码查看原文**

https://blog.logrocket.com/using-web-workers-boost-third-party-script-performance/

Arek Nawo

**如何在 Vue 中正确的使用防抖和节流函数？** — 如果你想知道如何在 Vue 组件中对观察者和事件处理程序进行去重和节流，可以看看这篇文章。

**长按识别二维码查看原文**

https://dmitripavlutin.com/vue-debounce-throttle/

Dmitri Pavlutin

**使用 TensorFlow.js 检测 Serverless、Twilio Video 中的物体。**

**长按识别二维码查看原文**

https://www.twilio.com/blog/object-detection-serverless-video-tensorflow-js

Lizzie Siegle（Twilio）

## 🛠 代码与工具

**Dexie.js v3.2：IndexedDB 包装器** — Dexie 为大多数流浏览器的 IndexedDB API 提供了一个成熟的包装器，现在它与反应式 UI 库集成。Dexie.js 的 主页 也进行了改版，修改之处包括有关框架的示例。

**长按识别二维码查看原文**

https://github.com/dfahlander/Dexie.js/releases/tag/v3.2.0

David Fahlander

**MicroDiff：轻量级、无依赖的对象和数组 Diff 库** — 给定两个对象或数组，MicroDiff 将返回它们之间的差异，并且拥有高性能和 TypeScript 支持。

**长按识别二维码查看原文**

https://github.com/AsyncBanana/microdiff

AsyncBanana

**React Location：用于 React 应用程序的企业级路由** — 该库是从 React Router v6 中剥离的库，其声明式和异步路由，可以让你的应用程序更加简洁，更加灵活。

**长按识别二维码查看原文**

https://react-location.tanstack.com/

Tanner Linsley

**browser-or-node v2.0：检查代码是否在浏览器或 node.js 运行时中运行** — 它提供一种简单的方法来判断您的代码当前是否在浏览器、Node、Web Worker 或者 Deno 中运行。

**长按识别二维码查看原文**

https://github.com/flexdinesh/browser-or-node

Dinesh Pandiyan

**Geodesy：测量地球经纬度方位库** — _Geodesy_ 是测量地球、形状、距离等的科学库。如果你需要处理这些概念，这些示例将非常有用。

**长按识别二维码查看原文**

https://github.com/chrisveness/geodesy

Chris Veness

**μPlot v1.6：快速、小巧、基于画布的时间序列图表库**

**长按识别二维码查看原文**

https://github.com/leeoniya/uPlot

Leon Sorokin

## 🙋🏻‍♀️