# JavaScript 中文周刊 #16 - 如何用 React、Express.js 和 esbuild 构建服务器端渲染

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496795&idx=2&sn=3527e4dc7ca00b0a9fa45ef19c64b636&chksm=e921bfb9de5636af00366c75140c686e43ab5af260afed9da0deef91870e2bdb54e7edc34983#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496795&idx=2&sn=3527e4dc7ca00b0a9fa45ef19c64b636&chksm=e921bfb9de5636af00366c75140c686e43ab5af260afed9da0deef91870e2bdb54e7edc34983#rd)  
> 抓取时间: 2026/2/2 23:53:40

---

> 本期看点：上周，Igor 离开了 Angular 团队，他宣布将由 Jeremy 继续领导团队继续前行。关于 JSON 模块化的提案目前已经进入第三阶段，并且在最新的 Node 和 Chrome 浏览器中已经作为实验特性支持。

> 编辑：liu-jin-yi、QC-L、Yucohny

## 🔥 本周热门

**asciinema-player：相比上个版本 JS 包体积减少 4 倍，编译速度增加 50 倍！** — **asciinema** 是一个基于 Python 的终端操作录屏器，如果想要在网络上播放录屏结果，就需要使用 asciinema-player。该库最初使用 ClojureScript 编写，同时使用 JS + Rust 混合构建（还使用了一些 **SolidJS**）。但现在，该库的 v3 版本已经完全的使用 JS 和 Rust 重构，目前已经进入收尾阶段，正式版即将发布。

**长按识别二维码查看原文**

https://blog.asciinema.org/post/smaller-faster/

Marcin Kulik

**Mitosis：将你的组件编译为任意框架的组件！** — 该库是一个单一的组件代码库，可以帮助你实现将目前的组件编译为 Vue，React，Solid，Angular，Svelte 组件等。可以试试这个 **在线的示例**，看看它是如何工作的。

**长按识别二维码查看原文**

https://github.com/BuilderIO/mitosis\#readme

Builder.io

**Floating UI：小巧的 Tooltips，popovers，dropdowns，menus 组件。** — 该库尽管与 T**ippy.js** 和 **Popper** 很相似，但是 Floating UI 可以通过使用中间件的方式对定位进行控制，并且使用了 Brotli 进行压缩，而核心包只有 0.6 kb。

**长按识别二维码查看原文**

https://www.floating-ui.com/

atomiks

**Igor 离开了 Angular 团队** — Igor 曾经是 Angular 团队的领导者和核心成员，他已经在 Angular 团队中工作了超过 12 年，但是他将要离开了。在这篇文章中，他回顾了这个项目的历史，和对同伴的不舍！并宣布 Angular 团队将由 Jeremy 领导并继续前行。

**长按识别二维码查看原文**

https://blog.angular.io/thank-you-angular-d90d70f2e9d8

Igor Minar

**快讯：**

- 🎂 12 月 4 日，是 JavaScript 的 26 岁生日，这意味着 **JavaScript 已经面世 26 年了**！
    
    **长按识别二维码查看原文**
    
    https://superhighway.dev/javascript-25-years-1995
    

- AWS 发布了 **AWS Amplify Studio**，这是一个可视化的开发环境，可以使开发人员编写最少的代码实现将 Figma 转换为 React 应用。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/mobile/aws-amplify-studio-figma-to-fullstack-react-app-with-minimal-programming/
    

- 如果你看腻了力扣上面的算法题，那么来尝试一下 **Advent of Code** 吧！目前该网站已经正式运营。
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

- Jon Meyers 在 Egghead 发布了 **关于构建 SaaS 产品的新课程**，主要讲述了如何使用 Next.js，Supabase 和 Stripe 构建 SaaS 产品。而该系列的视频教程完全免费！
    
    **长按识别二维码查看原文**
    
    https://egghead.io/courses/build-a-saas-product-with-next-js-supabase-and-stripe-61f2bc20
    

**版本发布：**

**WEBMIDI.js v3.0** – 轻松使用 Web MIDI API。

**Node v17.2.0** – Node 升级到了 V8 9.6。

**npm v8.2.0**

**Polly v6.0** – 支持 HTTP 交互记录、重放和保存的库。

**DOCX v7.2** – 使用 JavaScript 生成 .docx 文件。

**React PDF Reader v1.0** – 基于 PDF.js 的再次封装。

## 📖 教程与趣事

**JavaScript 中的 JSON 模块** — 通常情况下，你可以使用 `import` 来导入 JavaScript 代码。但是当你在一个 JSON 文件编写了一些配置，并想直接导入它的话应该怎么做？这个关于 **JSON 模块化的提案** 可以告诉你答案，该提案目前已经进入第三阶段了，并且在最新的 Node 和 Chrome 浏览器中已经作为实验特性支持。

**长按识别二维码查看原文**

https://dmitripavlutin.com/javascript-json-modules/

Dmitri Pavlutin

**如何在 npm 上发布组件包？** — 本篇文章作者 Simon’s 以自己最新编写的 Web 组件 **Datasette** 为例子，为大家介绍了如何在 npm 上发布组件包。

**长按识别二维码查看原文**

https://til.simonwillison.net/npm/publish-web-component

Simon Willison

**如何使用 Trim 方法删除字符串中多余的空格和行终止符** — 具体来说，就是安全地删除空白和行终结符。

**长按识别二维码查看原文**

https://dmitripavlutin.com/javascript-string-trim/

Dmitri Pavlutin

**如何用 React、Express.js 和 esbuild 构建服务器端渲染（SSR）？**

**长按识别二维码查看原文**

https://devtails.xyz/how-to-set-up-server-side-rendering-ssr-with-react-and-esbuild

Adam Berg

## 🛠 代码与工具

**Strapi v4：开源的 Node.js CMS 系统** — Strapi 已经发布了很长时间，并且具有优秀的社区环境。当前 v4 版本已经发布，包括新的 UI、插件 API 和查询引擎等，另外还专注于重构核心，使其更容易扩展。**点击查看 入门教程**。

**长按识别二维码查看原文**

https://strapi.io/blog/announcing-strapi-v4

Alexandre Bodin

**Plotly.js v2.7：基于 D3 和 Stack.gl 的数据可视化** — 这是一个老牌的图形库，但是当前仍在维护和更新。目前它有超过 40 种图表类型，这其中还包括 3D 可视化 – **点击查看 demo**。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/117170/web

Plotly

**Ladda：带有内置 Loading 按钮组件** — 简洁、小巧，特别适合表单提交。**GitHub  仓库地址**。

**长按识别二维码查看原文**

https://lab.hakim.se/ladda/

Hakim El Hattab

**WMR：适用于 React 或 Preact 的新型轻量级脚手架** — 开发项目所需要的一切都在这个工具中，例如打包构建、JSX、CSS 模块支持等功能。**GitHub  仓库地址**。

**长按识别二维码查看原文**

https://wmr.dev/

Preact

**noUiSlider：支持全触摸的轻量级范围滑块** — 无依赖，适合用于任何地方。**GitHub  仓库地址**。

**长按识别二维码查看原文**

https://refreshless.com/nouislider/

Leon Gersen

**jsvu：JavaScript（引擎）版本更新器** — 一个不需要从源代码进行编译的 JavaScript 引擎安装的工具。

**长按识别二维码查看原文**

https://github.com/GoogleChromeLabs/jsvu

Google

**🕹  TEGA：TypeScript 嵌入式 GameBoy 宏汇编器** — TEGA 是一个 TypeScript 库（也可在 JS 中使用），用于编程和创建 GameBoy ROM 映像。看看这个例子吧。

**长按识别二维码查看原文**

https://github.com/francisrstokes/tega

Francis Stokes

**🐍  promisio：适用于 Python 的 JavaScript 式异步编程** — 如果你想要在 Python 中使用 JS 风格的异步函数，可以看看这篇文章。

**长按识别二维码查看原文**

https://github.com/miguelgrinberg/promisio

Miguel Grinberg

**web-ext：帮助构建、运行和测试 Web 扩展的命令行工具**

**长按识别二维码查看原文**

https://github.com/mozilla/web-ext

Mozilla

**Ember Infinity：为 Ember CLI 应用程序提供简单、灵活的无限滚动功能**

**长按识别二维码查看原文**

https://github.com/ember-infinity/ember-infinity

**Converse v9.0：用 JS 编写的基于网络的 XMPP/Jabber 聊天客户端**

**长按识别二维码查看原文**

https://github.com/conversejs/converse.js

**blockify-yourself** — 上周，前 Twitter CEO Jack Dorsey ‘_做了一个 Zuck_’ 并将 **Square, Inc. 改名为 Block**，同时配备了 **新的 logo**。该标志甚至被纳入了 管理团队人员页面的头像中。现在，你可以通过 **这个 Glitch 项目** 获取你自己的块状头像。（_该项目使用 Three.js_）。

**长按识别二维码查看原文**

https://blockify-xyz.glitch.me/

Julius Tarng

## 🙋🏻‍♀️