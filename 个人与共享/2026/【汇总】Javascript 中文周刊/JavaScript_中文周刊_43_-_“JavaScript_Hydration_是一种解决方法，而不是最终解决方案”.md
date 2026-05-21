# JavaScript 中文周刊 #43 - “JavaScript Hydration 是一种解决方法，而不是最终解决方案”

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507400&idx=1&sn=f1a71a478fd13c2a6fbbff511dda144c&chksm=e921962ade561f3c23361f3550f47f19dae029ba67b7338198e49e92b8a971d5068263029f28\#rd  
> 抓取时间: 2026/2/2 23:53:06

---

> 本期看点：本期为大家带来了 Miško 在 JavaScript Hydration 领域的另一种尝试与使用 Angular 和 RxJs 缓存 API 响应的最佳方式等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi

## 🔥 本周热门

**使用 JavaScript 解释数学符号** — 数学有它自己迷人的符号世界，但如果你觉得它有点难以理解的话，那么这篇文章应该会对你有所帮助。它把许多数学领域的符号归结为 JavaScript 的等价物，会让你更容易理解这个数学符号。

**长按识别二维码查看原文**

https://runjs.app/blog/mathematical-notation-for-javascript-developers-explained

Haas Labs Ltd

**“JavaScript Hydration 是一种解决方法，而不是解决方案”** — 许多新型的框架提供的 Hydration 是否是不必要的开销？Angular 的作者 Miško 在本篇文章中解释了他为什么这么认为的，并分享了他们自研的 **Qwik 框架** 目前所采用的策略。

**长按识别二维码查看原文**

https://thenewstack.io/javascript-hydration-is-a-workaround-not-a-solution/

Miško Hevery

**Plasmo: ‘它就像浏览器扩展的 Next.js’** — 一个面向 React 和 TypeScript 的框架，用于创建你自己的浏览器扩展，具有实时重载、自动部署到主要浏览器扩展市场等功能。

**长按识别二维码查看原文**

https://github.com/PlasmoHQ/plasmo

Plasmo

**快讯：**

- **最新的 VS Code 更新已发布**。包括 TypeScript v4.7，令人兴奋的是 **转到定义** 功能的更新，现在可以正常的跳到外部库中的函数和符号的 JS 实现，而不是 TS 的类型定义。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_68
    

- 😆 上周，我们联系到一个使用 Office 插件在 Word 中使用 JavaScript 制作图形游戏的人 - 他又为我们带来了一期视频 ▶️ **在 Word 中实现 Wordle**。很高兴看到有人玩得开心。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=N2btcfPtxQ0
    

- **SAFARI:** Apple 的开发者大会 WWDC 目前已经结束 **新的 WebKit/Safari 功能** 将在 Safari 16 Beta 中提供。支持 Web Inspector Extensions 并支持 **Shared Workers**，即可以在浏览上下文之间共享的服务工作者。我们也可以期待 2023 年的**Web Push** 支持。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/12824/news-from-wwdc-webkit-features-in-safari-16-beta/
    

- **Astro v1.0 预计在本周发布**， 但 **新的静态站点构建器** 的发布被推迟到 7 月下旬。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/astro-1-release-update/
    

- GitHub 正在 **引入 “成就”的概念**，你可以通过实现尚未定义的目标获得徽章。
    
    **长按识别二维码查看原文**
    
    https://github.blog/2022-06-09-introducing-achievements-recognizing-the-many-stages-of-a-developers-coding-journey/
    

**版本发布：**

- **Flicking v4.9** – 灵活的轮播图组件。

- **Bree v9.0** – Node.js job 调度器。

- **Jasmine v4.2** – 测试框架。

- **EmojiMart v5.1 –** 表情符号挑选器控件。

- **Puppeteer v14.3**

## 📒 教程与趣事

**使用 JavaScript 进行半色调打印** — 通过使用基本的 JavaScript 和 Canvas 再现经典的半色调样式打印。

**长按识别二维码查看原文**

http://anderoonies.github.io/projects/halftone/

Andy Bayer

**构建框架可互操作的 Web Components** — 如果你使用不同的框架，如 React、Svelte、Vue 等。通常会选择适合每个框架的组件库，但如果你可以以与框架无关的方式编写一次此类组件并在任何你想要的地方使用它们，会怎样？Web Components 提供了一种方法，可以帮你实现跨框架使用组件。

**长按识别二维码查看原文**

https://css-tricks.com/building-interoperable-web-components-react/

Adam Rackis

**使用 JavaScript 实现一个超声波支付系统** — 这是一个在设备之间进行超声波数据传输的有趣实验。

**长按识别二维码查看原文**

https://charliegerard.dev/blog/ultrasonic-payments/

Charlie Gerard

**▶  使用 100 秒向你介绍 RedwoodJS** — RedwoodJS 是一个全栈 JS 框架，由 GitHub 的一位联合创始人提供支持。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=o5Mwa_TJ3HM

Fireship

**通过 UTM 在 Apple Silicon Mac 上运行 Windows/ARM**

**长按识别二维码查看原文**

https://2ality.com/2022/06/windows-on-macs-via-utm.html

Dr. Axel Rauschmayer

**你应该使用 Framer Motion 还是 Motion One 做动画？** — **Framer Motion** 和 **Motion One** 到底应该使用哪一个？本文的作者就这个问题对这两个 JavaScript 动画库进行了对比。

**长按识别二维码查看原文**

https://motion.dev/blog/should-you-use-framer-motion-or-motion-one

Matt Perry

**使用 Angular 和 RxJs 缓存 API 响应的最佳方式**

**长按识别二维码查看原文**

https://tomastrajan.medium.com/the-best-new-way-to-cache-api-responses-with-angular-rxjs-5cbc05d12f10

Tomas Trajan

## 🛠 代码与工具

**KaTeX v0.16.0：最快的网络数学排版库** — 该库 无依赖。可在页面上渲染大量公式。**在线 Demo**。

**长按识别二维码查看原文**

https://katex.org/

Emily Eisenberg and Sophie Alpert

**Timeline JS：为 Web 创建有用的时间线** — 该库由一所大学的新闻实验室创建的，使用人群面向非技术开发人员。**点击 🔗 查看示例**。

**长按识别二维码查看原文**

https://timeline.knightlab.com/

Northwestern University Knight Lab

**Fastify v4.0 发布：一个 Node.js Webapp 框架** — 这是高性能 Node.js Web 框架的第一个主要版本。更新重点放在了稳定性、现代化和改进已经相当稳定的开发人员体验上，而不是华而不实的新功能。这篇文章介绍了一些更新的特性。

**长按识别二维码查看原文**

https://medium.com/@fastifyjs/fastify-v4-ga-59f2103b5f0e

Fastify Team

**pretty-ms：将毫秒转换为可读的字符串** — `1337000000` → `15d 11h 23m 20s`

**长按识别二维码查看原文**

https://github.com/sindresorhus/pretty-ms

Sindre Sorhus

**最适合 UI 设计师的 JavaScript 和 CSS 动画库** — 本篇文章介绍了九个动画库，涵盖了每个库优点和缺点以及合适使用。

**长按识别二维码查看原文**

https://www.sitepoint.com/our-top-9-animation-libraries/

Alex Walker

**qnm：用于查看 `node_modules` 目录的 CLI 实用程序** — 该库的目标是让你更容易看到 `node_modules` 目录中的情况，包括支持搜索软件包。同时支持 npm 和 yarn。

**长按识别二维码查看原文**

https://github.com/ranyitz/qnm

Ran Yitzhaki

**is-online v10.0：检查 Internet 连接是否正常** — 该库可在 Node.js 和浏览器中使用，可使用不同的方法来检查互联网是否正常。

**长按识别二维码查看原文**

https://github.com/sindresorhus/is-online

Sindre Sorhus

**Awesome Readme Template：GitHub 项目的 README 模板**

**长按识别二维码查看原文**

https://github.com/Louis3797/awesome-readme-template

Louis-Kaan Ay

**math.gl：用于地理空间和 3D/WebGL 可视化用例的数学模块**

**长按识别二维码查看原文**

https://math.gl/

Uber

## 🙋🏻‍♀️