# JavaScript 中文周刊 #9 - JavaScript V8 引擎 V8 9.6 正在快马加鞭的赶来！

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247494163&idx=1&sn=0a34187fdd821f219aacfa11e331a8de&chksm=e921a1f1de5628e729e37b2a71c9a3b395bf5a569c5e73771401e37a5acb743005ef0a1143a4#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247494163&idx=1&sn=0a34187fdd821f219aacfa11e331a8de&chksm=e921a1f1de5628e729e37b2a71c9a3b395bf5a569c5e73771401e37a5acb743005ef0a1143a4#rd)

> 抓取时间: 2026/2/2 23:53:48

---

> 本期看点：本周 Serverless 开放了 Serverless Cloud 的预览版本，并且 Remix 项目获得了 300 万美元的融资，这使得该项目有了更多的可能性，或将要开放其源码。ESLint 也发布了 v8.0.0。

> 编辑：liu-jin-yi、QC-L、Matrixbirds

## 🔥 本周热门

Parcel v2 发布 — Parcel 是一款快速免配置的 webapp 构建工具，于 2017 年横空出世（issue 364！），随即在 JavaScript 领域中掀起了一场使用热潮。V2 版本是一次全面的重写，采用了和 V1 相同的原则，通过默认的 Tree Shaking、全新的插件系统、ES 模块 bundling、自动代码拆分、图像资源优化，可以适合 “任何大小和复杂性”的项目。

**长按识别二维码查看原文**

https://parceljs.org/blog/v2/

Parcel Team

Remix 项目获得 300 万美元的融资 — _React Training_ 和 _React Router_ 的开发团队一直在开发一款名为 _Remix_ 的全栈式 JavaScript 框架，目前，该框架只对付费用户开放使用权（用户好评如潮！）。这一轮的融资使这个项目有了很多新的可能性，包括开放框架的源代码–这对我们所有人来说都是一个好消息。

**长按识别二维码查看原文**

https://remix.run/blog/seed-funding-for-remix

Michael Jackson and Ryan Florence

**快讯：**

- JavaScript V8 引擎的最新分支，V8 9.6，已经创建。这一次的更新亮点很少，支持在 WebAssembly 模块中使用 JavaScript 的外部引用是唯一值得注意的特性。

**长按识别二维码查看原文**

https://v8.dev/blog/v8-release-96

- 在 Twitter 上，外国码友们分享了他们在 JavaScript 中书写的优秀示例，看了这个你会有很大的收获。

**长按识别二维码查看原文**

https://twitter.com/jamesqquick/status/1448060114053763076

- Serverless 已经开放了Serverless Cloud 的预览版本，这是（目前）一个专门针对 JavaScript 开发者的 Serverless 平台。

**长按识别二维码查看原文**

https://www.serverless.com/blog/introducing-serverless-cloud-public-preview

ESLint v8.0.0 发布 — ESLint 是一款流行的可插拔、可配置的 linter 工具，用于维护 JavaScript 代码质量。v8.0 版本已经可以娴熟的检查 ES2022 的相关代码。如果你想要从旧版本升级，可以使用这个迁移指南。

**长按识别二维码查看原文**

https://eslint.org/blog/2021/10/eslint-v8.0.0-released

ESLint Team

**版本发布：**

deck.gl v8.6 – 基于 WebGL2 驱动的大规模数据可视化。

crypto-hash v2.0 – 用于浏览器和服务器端的哈希加密模块。

React Static v7.6.0 – 适用于 React 的渐进式静态网站生成器。

Jasmine v3.10 – 测试框架。

npm v8.1.0

## 📖 教程与趣事

AWS 如何将其适用于 JavaScript 的 AWS 开发工具包的发布大小减半的？ — AWS 对其模块化 JavaScript 包的大小做了一些巨大的改进，主要是通过清理明显的东西，如评论、源地图和不必要的 TypeScript 源。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/developer/how-we-halved-the-publish-size-of-modular-aws-sdk-for-javascript-clients/

Trivikram Kamat（AWS）

如何解决 CORS 的跨域问题？ — 谷歌的开发者 Jake 书写了他所知道的关于 跨源资源共享 （CORS）的所有信息。这里有一个demo可以帮助你更好的理解 CORS。

**长按识别二维码查看原文**

https://jakearchibald.com/2021/cors/

Jake Archibald

JavaScript 开发者都应该知道的 33 个概念 — 这是一个精心准备的教程链接集，包含了 33 个值得好好了解的 JavaScript 不同领域的教程，包括：类型、闭包、值的比较、作用域和不同的 JavaScript 引擎。我们以前曾推送过它，如今它又更新了许多新的链接。

**长按识别二维码查看原文**

https://github.com/leonardomso/33-js-concepts\#readme

Leonardo Maldonado

Figma 中的棋盘游戏（包含 JavaScript） — 我们不是Figma的用户，但这个基于云的设计工具当前非常流行。它还可以制作桌面游戏！

**长按识别二维码查看原文**

https://mastery.games/post/board-gaming-in-figma/

Dave Geddes

用 AnimXYZ 在 Vue 中制作可组合的 CSS 动画 — AnimXYZ 是一个可组合的 CSS 动画工具箱。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/10/composable-css-animation-vue-animxyz/

Ejiro Asiuwhu

你必须要知道的关于 TypeScript 的三个技巧。

**长按识别二维码查看原文**

https://www.cstrnt.dev/blog/three-typescript-tricks

Tim Raderschad

如何用 Next.js 将 Sass 变量导出到 JavaScript 中？

**长按识别二维码查看原文**

https://spacejelly.dev/posts/how-to-export-sass-variables-to-javascript-with-next-js/

Colby Fayock

## 🛠 代码与工具

Nuxt 3 Beta 的入门介绍 — Nuxt 3（一个深受 Vue 用户欢迎的框架）的更新亮点是其新的服务器引擎，允许它在任何地方部署，包括类似 Next.js 的无服务器部署（其中 SSR 页面部署为无服务器函数）。它还支持 Vue 3 和 Vite。想了解更多，请看Ben Hong 的现场录音。

**长按识别二维码查看原文**

https://nuxtjs.org/announcements/nuxt3-beta/

Nuxt Team

Sapling：用于遍历 React 组件层次结构的 VSCode 扩展程序 — Sapling在 VS Code 侧边栏中添加了一个交互式的依赖树，其中包括每个组件的可用 Props，以及对相关文件的简单导航。

**长按识别二维码查看原文**

https://t.co/GVhzNsDn0c?amp=1

Team Sapling

jest-extended v1.0：为 Jest 用户提供的附加匹配器 — 如果你正在使用 Jest 进行测试，这个项目为各种测试情况介绍了各种更具体的匹配器，特别是围绕类型和格式检查的匹配器。

**长按识别二维码查看原文**

https://github.com/jest-community/jest-extended

Jest Community

Ruby2JS v4.2.0：将 Ruby 转为 JavaScript 的转译器 — 这个转译器旨在使产生的代码看起来更像是 “手工制作的”，而不是转码的代码。如果你想看看它的运行情况，有一个在线 demo。

**长按识别二维码查看原文**

https://www.ruby2js.com/

Sam Ruby and Jared White

Swiper：现代化的移动触摸轮播组件 — 使用硬件加速过渡的效果，让你体验如丝般的顺滑。

**长按识别二维码查看原文**

https://swiperjs.com/

Vladimir Kharlampidi

Day.js：替代 Moment.js 的 2KB 的日期库 — 一个简洁的库，为现代浏览器解析、验证、操作和显示日期和时间，其 API 与 Moment.js 基本兼容。

**长按识别二维码查看原文**

https://github.com/iamkun/dayjs

iamkun

webpack Boilerplate 3.0：优秀的 Webpack 5 模板。

**长按识别二维码查看原文**

https://github.com/taniarascia/webpack-boilerplate

Tania Rascia

通过复选框渲染的 DOOM — 是否有可能在你的网络浏览器中玩转 DOOM，只用复选框进行渲染？这个 demo 很有趣，这里是源代码。

**长按识别二维码查看原文**

https://healeycodes.com/doom-rendered-via-checkboxes

Andrew Healey

## 🙋🏻‍♀️