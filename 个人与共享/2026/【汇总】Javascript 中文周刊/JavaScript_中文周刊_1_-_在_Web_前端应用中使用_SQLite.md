# JavaScript 中文周刊 #1 - 在 Web 前端应用中使用 SQLite

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491249&idx=1&sn=d72f7682a059928ec815c2465461161f&chksm=e9225553de55dc453802c51847f49f3769f0038d2870106be0ba08cd1041ad7685323ac26711#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491249&idx=1&sn=d72f7682a059928ec815c2465461161f&chksm=e9225553de55dc453802c51847f49f3769f0038d2870106be0ba08cd1041ad7685323ac26711#rd)

> 抓取时间: 2026/2/2 23:53:57

---

> 很多小伙伴在后台咨询我，JavaScript 中文周刊为什么不更新了，现在，它回来了！
> 
> 本周看点：Chromium 正在开发并支持使用 `import` 导入 CSS 样式，以后可以像 ESModule 一样引入 CSS。一年一度的 JS13KGames 编码竞赛已经开始，有兴趣的小伙伴可以参与参与。

编辑 | liu-jin-yi

whatwewant

Matrixbirds

QC-L

## 🔥 本周热门

**Ruby on Rails’ 的作者认为现代的前端应用无需打包和转译** — 大卫·海涅迈尔·汉森（Ruby on Rails 的作者）已经解释了他在基于 Rails 的应用程序中看到 JavaScript 的未来，它涉及使用 import 映射，同时不再需要像 webpack 这样的打包工具 —— 相反，应用程序将只获取所需的 ES 模块。他还在 这个时长为 27 分钟的视频 中展示了它的工作原理。

**长按识别二维码查看原文**

[https://world.hey.com/dhh/modern-web-apps-without-javascript-bundling-or-transpiling-a20f2755](https://world.hey.com/dhh/modern-web-apps-without-javascript-bundling-or-transpiling-a20f2755)

David Heinemeier Hansson (DHH)

**在 Web 前端应用中使用 SQL** — absurd-sql 是一个主要为 Web 提供 SQLite 持久化存储的后端项目。它基于 IndexedDB 实现，同时还使用了 sql.js，因此你可以在 webapps 中使用 SQLite。查看原文，了解更多有趣的想法。

**长按识别二维码查看原文**

[https://jlongster.com/future-sql-web](https://jlongster.com/future-sql-web)

James Long

**热点新闻：**

- Chromium 正在开发针对 使用 `import` 导入 CSS 样式 的支持，在此功能支持后，你就可以像使用 ES 模块那样使用 CSS 了。
    
    **长按识别二维码查看原文**
    
    [https://blogs.windows.com/msedgedev/2021/08/17/css-module-scripts-import-stylesheets-like-javascript-modules/](https://blogs.windows.com/msedgedev/2021/08/17/css-module-scripts-import-stylesheets-like-javascript-modules/)
    

- 🎲 一年一度的 JS13KGames 编码竞赛已经开始 并持续到 9 月 13 日 —— 主题是 “太空”。准备好建立一个游戏了吗？
    
    **长按识别二维码查看原文**
    
    [[JavaScript_中文周刊_221_-_LibPDF：TypeScript_里的_PDF_解析与生成]][[JavaScript_中文周刊_221_-_LibPDF：TypeScript_里的_PDF_解析与生成]]
    

- 如果你在一个 `Map` 对象中放入超过 2^24 个 item，你会遇到奇怪的错误信息。
    
    **长按识别二维码查看原文**
    
    https://searchvoidstar.tumblr.com/post/659634228574715904/an-amazing-error-message-if-you-put-more-than-2-24
    

- 🎂 Bootstrap 10 周年
    
    **长按识别二维码查看原文**
    
    [https://blog.getbootstrap.com/2021/08/19/ten/](https://blog.getbootstrap.com/2021/08/19/ten/)
    

**版本发布：**

Mocha 9.1.0 版本 – 测试框架。

**长按识别二维码查看原文**

[https://github.com/mochajs/mocha/releases/tag/v9.1.0](https://github.com/mochajs/mocha/releases/tag/v9.1.0)

svgo 2.4.0 版本 – 用于优化 SVG 文件的节点工具。

**长按识别二维码查看原文**

[https://github.com/svg/svgo/releases/tag/v2.4.0](https://github.com/svg/svgo/releases/tag/v2.4.0)

Node 16.7.0 版本 – 增加了一个实验性的递归 `cp` 方法。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/release/v16.7.0/](https://nodejs.org/en/blog/release/v16.7.0/)

Capacitor 3.2.0 版本 – 为 iOS、Android 和 Web 构建原生 PWA 应用。

**长按识别二维码查看原文**

[https://github.com/ionic-team/capacitor](https://github.com/ionic-team/capacitor)

WebTorrent 1.5.0 版本 – 流式 Torrent 客户端。

**长按识别二维码查看原文**

[https://github.com/webtorrent/webtorrent](https://github.com/webtorrent/webtorrent)

Cypress 8.3.0 版本 – 浏览器端测试框架。

**长按识别二维码查看原文**

[https://github.com/cypress-io/cypress/releases/tag/v8.3.0](https://github.com/cypress-io/cypress/releases/tag/v8.3.0)

## 📖 教程与趣事

**使用原生 JS 创建可交互的甘特图组件** — 将甘特图（常用于可视化时间表）编码为可重用的 Web 组件，涵盖组件的架构，用 CSS Grid 渲染日历布局，以及用代理对象管理可拖动任务的状态。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/08/interactive-gantt-chart-component-vanilla-javascript/

Anna Prenzel

**关于加载第三方 JavaScript 脚本** — 如何更好更安全的加载第三方 JavaScript 脚本，这个是一个永恒的话题，查阅本文学习如何减少其对性能的影响。

**长按识别二维码查看原文**

https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript

Addy Osmani 与 Arthur Evans

**关于如何拆分 React 组件的指南（观点来自 70 年代！）** — 从 70 年代的一篇论文中摘录了一些有趣的观点。_“设计易于扩展和收缩的软件”_ - David Parnas。

**长按识别二维码查看原文**

https://joaoforja.com/blog/guideline-on-how-to-decompose-a-react-component/

João Forja

**如何在 JSDoc 注释中编写 TypeScript 接口** — 一种避免构建步骤的方法，但仍然能享受 TypeScript 对你的 `.js` 文件的类型检查。

**长按识别二维码查看原文**

https://goulet.dev/posts/how-to-write-ts-interfaces-in-jsdoc/

Wes Goulet

`return await promise`**vs** `return promise` — 在异步函数中使用 `return await promise` 和 `return promise` 有什么区别吗？

**长按识别二维码查看原文**

https://dmitripavlutin.com/return-await-promise-javascript/

Dmitri Pavlutin

**作者从** **React 开发者的角度尝试了 Angular，本文讲述了作者喜欢它的六个方面**

**长按识别二维码查看原文**

https://t.co/pWi8CtaXiB?amp=1

Louis Petrik

**如何用 Next.js 和 Tailwind CSS 建立一个组合网站**

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/how-to-build-a-portfolio-site-with-nextjs-tailwindcss/

Manu Arora

**真假难辨：揭秘 JavaScript 中 == 与 ===**

**长按识别二维码查看原文**

https://www.sitepoint.com/javascript-truthy-falsy/

Craig Buckler

## 🛠 代码与工具

**wavesurfer.js：通过网络音频和画布 API 实现可导航的音频波形** — 如果你正在打造一个播客播放器，想提升音频体验，或者想展示可见且可交互式的音频波形，此仓库一定不容错过。

**长按识别二维码查看原文**

https://github.com/katspaugh/wavesurfer.js

katspaugh and contributors

**Marked 3.0：一个快速的 Markdown 解析器和编译器** — 支持浏览器端或服务端。查看 Demo。

**长按识别二维码查看原文**

https://github.com/markedjs/marked

https://marked.js.org/demo/

Christopher Jeffrey

**zx 3.0：能编写更好 Shell 脚本的工具** — 与使用类似 `bash` 之类的东西来组合一个快速脚本不同，`zx` 提供了各种细节来使用你熟悉和喜爱的 JavaScript 来做同样的事情。

**长按识别二维码查看原文**

https://github.com/google/zx

Google

**v-lazy-image：用于懒加载图像的 Vue.js 组件** — 使用 Intersection Observer，结合 CSS 动画进行渐进式渲染，以保持流畅。查看 Demo。

**长按识别二维码查看原文**

https://github.com/alexjoverm/v-lazy-image

Alex Jover

**Pyodide：将 Python 编译成 WebAssembly 用于 Web** — Python 在编程教育和数据科学的世界中崛起，因此如果你有在浏览器中与 JavaScript 互操作的场景，此库不容错过。

**长按识别二维码查看原文**

https://pyodide.org/en/stable/index.html

Pyodide contributors 和 Mozilla

**Notistack：一个用于方便快捷地通知库** — 你可以在文档中查看一系列的 Demo 和 API。

**长按识别二维码查看原文**

https://github.com/iamhosseindhv/notistack

Hossein Dehnokhalaji

Serendipity：美观的 VSCode 主题，同时具有暗黑和明亮模式 — 调色板的选择是为了让视网膜显示器上的眼睛赏心悦目。

**长按识别二维码查看原文**

https://wvsc.dev/

michael andreuzza

## 🕰 旧事新谈

- 如何避免/防止未捕获的异步错误。
    
    **长按识别二维码查看原文**
    
    https://advancedweb.hu/how-to-avoid-uncaught-async-errors-in-javascript/
    
    ‍‍‍‍‍‍‍‍‍‍‍‍
    

- 如何使用 `fetch()` API 来加载和发布 JSON 数据。—— Dmitri Pavlutin
    
    **长按识别二维码查看原文**
    
    https://dmitripavlutin.com/fetch-with-json/
    

- 如何在 CSS 和 JavaScript 中检测媒体查询支持 —— Kilian Valkhof。
    
    **长按识别二维码查看原文**
    
    https://kilianvalkhof.com/2021/web/detecting-media-query-support-in-css-and-javascript/
    

**😄 趣事**

**Fishdraw：程序生成的鱼类图画** — 这个基于 Node 的项目创造了 “各种奇怪的鱼”，并自诩为完全程序化生成的，其输出结果看起来相当惊人。

**长按识别二维码查看原文**

https://github.com/LingDong-/fishdraw

Lingdong Huang

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。