# JavaScript 中文周刊 #97 - 如何将 Fastify 和 Vue 3 静态网站部署到 Heroku

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522699&idx=1&sn=acf7ecbeca4ce743dab3f0f067003464&chksm=e921d269de565b7f9bfd52c2935019ab35affa2ece08fba8625ac6b33e393c82f3c99f0fe9e4\#rd  
> 抓取时间: 2026/2/2 23:51:54

---

> 本期看点：上周，Prettier v3.0 现在由 ESM 驱动、Crockford 讲述普通的 JavaScript 和 DOM

> 编辑：liu-jin-yi

## 🔥 本周热门

**Driver.js: 制作页面导览、突出显示与上下文帮助** — 无依赖的原生 JavaScript 库,用以搭建页面导览和上下文帮助系统。该项目存续多年,近期全新完善并新增 **种种改进** ,还被全新打造。许多实例供参考。

**长按识别二维码查看原文**

https://driverjs.com/

Kamran Ahmed

**组件狂欢：诸多 UI 库代码示例** — 通过各种任务的简单代码片段比较 React、Vue、Svelte、Angular、Ember 等框架,展现 UI 组件最佳实践。

**长按识别二维码查看原文**

https://component-party.dev/

Mathieu Schimmerling

**Prettier v3.0: 现在由 ESM 驱动**—流行的多语言代码格式化工具得到了一次重大升级，最大的变化是重构为 ES 模块（尽管它仍然可以通过 CommonJS 作为一个库使用）。一个副作用是 Prettier 现在支持基于 ESM 的插件和异步解析器，这意味着**Prettier 插件开发者需要做一些必要的改变**。

**长按识别二维码查看原文**

https://prettier.io/blog/2023/07/05/3.0.0.html

Sosuke Suzuki

**Crockford 讲述普通的 JavaScript 和 DOM** — 多年来，Douglas 一直要求我们只使用 JavaScript 中_好的部分，**▶️ stop using JavaScript**，现在他建议放弃 “库”，转而直接使用 DOM。Lea Verou 🐦 **拾起了这个故事**，并说这个建议到 2023 年对于大多数 Web 应用来说仍然不太实用。

**长按识别二维码查看原文**

https://www.crockford.com/domjs.html

Douglas Crockford

**⚡️ 快讯：**

- `obj?.prop=value;`**可选链式赋值** 提案在本周的 TC39 会议上推进到了第一阶段。(**解释性幻灯片**)
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-optional-chaining-assignment
    

- YouTube 热门频道 Fireship 对▶️ **htmx in 100 seconds**进行了解释–来得正是时候，因为 **htmx** 正在引起大量新的兴趣。如果您想知道 Fireship 背后的策划人是谁，Honeypot 已经上传了▶️，**关于他的纪录片短片**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=r-GSGH2RxJs
    

- Sandworm 的朋友们分享了**npm 注册表**的现状，其中包括大量的琐事、历史、软件包数量统计以及软件包中最常用的关键字。
    
    **长按识别二维码查看原文**
    
    https://blog.sandworm.dev/state-of-npm-2023-the-overview
    

- 谷歌分享了使 **用其基于浏览器的新 API 的滚动驱动动画性能案例** 研究与 “经典 JavaScript 技术”的对比。不出所料，脱离主线程运行的速度要快得多，目前该规范仍处于草案阶段。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/scroll-animation-performance-case-study/
    

- 现在，当您在 **npmjs.com** 上 **查看软件包的出处** 信息时，npm 会检查链接的源提交和 repo，**并在无法确定出处时发出警告**
    
    **长按识别二维码查看原文**
    
    https://www.npmjs.com/
    

- GitHub 正推出 **GitHub․com 上无密码、基于密码的认证** 的测试版。
    
    **长按识别二维码查看原文**
    
    https://github.blog/2023-07-12-introducing-passwordless-authentication-on-github-com/
    

## 📒 教程与趣事

**(Deno)HTTP 服务器的有用函数** — 你可以把 HTTP 看作是一个功能性的方式，请求进入，响应/结果出去。作者探讨了 Deno 新的`Deno.serve`函数，以及它和`/x/http_fns` **函数** 如何为常见的 HTTP 任务提供功能更强的方法。

**长按识别二维码查看原文**

https://jollytoad.deno.dev/blog/http_fns

Jollytoad

**创建随机化的塞尔达：王国之泪图案** — 任天堂的新塞尔达游戏使用重复的几何图案作为其美学的一部分。本篇博文将介绍如何使用 SVG 和 JavaScript 重现此类图案。

**长按识别二维码查看原文**

https://cloudfour.com/thinks/coding-randomized-zelda-patterns/

Paul Hebert

**您应该在项目配置中包含的 5 个 TS 编译器标志**

**长按识别二维码查看原文**

https://egorkonovalov.github.io/flycatcher/posts/3/

Igor Konovalov

**将 Fastify 和 Vue 3 静态网站部署到 Heroku**

**长按识别二维码查看原文**

https://www.lirantal.com/blog/deploying-a-fastify-vue-3-static-site-to-heroku

Liran Tal

**Node.js 中的矢量数据库入门**

**长按识别二维码查看原文**

https://thecodebarbarian.com/getting-started-with-vector-databases-in-node-js.html

Valeri Karpov

## 🛠 代码与工具

**MDX Editor: 丰富的 Markdown 编辑器 React 组件** — 用于 React 应用程序的**Lexical** 驱动的 Markdown 编辑器，支持代码块、表格等。**现场演示** 展示了您需要看到的大部分内容。

**长按识别二维码查看原文**

https://mdxeditor.dev/

Petyo Ivanov

**electron-vite: 下一代 Electron 打包工具** — Electron 桌面应用程序框架和 Vite 前端工具包就是如此。还有一个 **Electron Vite 模版** App可以用来启动一个新的应用程序。

**长按识别二维码查看原文**

https://electron-vite.org/

Alex Wei

**📊 Vizzu v0.8: 动画数据可视化库** — 制作数据可视化相当容易，但制作动画却很难。Vizzu 帮助您创建动画数据故事和探索。有很多 **展示** 和 **示例** 供您浏览。

**长按识别二维码查看原文**

https://lib.vizzuhq.com/latest/

Vizzu Inc.

**🐊 Putout: 一种可配置的、基于 Babel 的线路器和代码转换器**—使用 ESLint 提供典型的 linting 功能，使用 Babel 提供代码转换功能，但与其他工具相比，它的与众不同之处在于可以进行”更剧烈的代码转换”。它不是最流行的选择，但它在其 **详尽的 README** 中为自己做了很好的辩护。

**长按识别二维码查看原文**

https://github.com/coderaiser/putout

coderaiser

**标准化音频上下文：跨浏览器网络音频 API 封装器** — Web Audio API 子集的无副作用抽象，可在所有主流浏览器中可靠运行。

**长按识别二维码查看原文**

https://github.com/chrisguttandin/standardized-audio-context

Christoph Guttandin

**Kanel：从 Postgres 生成 TypeScript 类型** — 它通过检查实时数据库工作，并输出代码，您可以添加到 TypeScript 项目，并使用类似 **Knex - GitHub 仓库地址**

**长按识别二维码查看原文**

https://kristiandupont.github.io/kanel/

Kristian Dupont

**🎉 版本发布：**

- **Ember v5.1**
    
    ↳ 这个雄心勃勃、永不放弃的 JS 框架向 TypeScript 世界迈出了一大步具有稳定的 TypeScript 支持，并且类型丰富。
    

- **p5.js v1.7**
    
    ↳ 受处理启发的 JavaScript 库，用于创造性编码。v1.7引入了 WebGL 2 和帧缓冲支持。
    

- **Prisma v5.0**
    
    ↳ 适用于 Node.js 和 TypeScript 的流行的 ORM。5.0 版本在性能方面有了重大改进。
    

- **Boa v0.17**
    
    ↳ 一个用 Rust 编写的实验性 Javascript 词法、解析器和编译器，可以嵌入到其他项目中–它现在有一个模块系统。
    

- **Octokit.js v3.0**
    
    ↳ 用于浏览器、Node 和 Deno 的官方 GitHub SDK。
    

- **Release It! v16.1**
    
    ↳ 自动化 npm 软件包发布和版本控制。
    

- **zlFetch v6.0**
    
    ↳ Fetch API 的便利封装。
    

- **Terminalizer v0.10**
    
    ↳ 记录您的终端并生成 GIF 动画。
    

- **eslint-plugin-prettier v5.0**
    
    ↳ 更漂亮，但作为 ESLint 规则。
    

- **Preact v10.16**
    
    ↳ 3KB 的 React 兼容替代品。
    

- **typescript-eslint v6.0**

## 🍩 来点小甜点

**donut.js: donut.c，但是在 JavaScript 中**—**donut.c** 是 2006 年发布的一个甜甜圈形状的 C 语言程序，运行时会在屏幕上显示一个旋转的 ASCII 文本甜甜圈动画。下面是一个新鲜出炉的 JavaScript 变体！

**长按识别二维码查看原文**

https://github.com/EvanZhouDev/donut-js

Evan Zhou

## 🙋🏻‍♀️