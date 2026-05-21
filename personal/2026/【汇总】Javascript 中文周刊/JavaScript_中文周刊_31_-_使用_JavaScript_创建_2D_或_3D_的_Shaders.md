# JavaScript 中文周刊 #31 - 使用 JavaScript 创建 2D 或 3D 的 Shaders

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503976&idx=1&sn=368baea8a52e3f3e97feb29dd105938b&chksm=e9219b8ade56129c966b908a9f0b38d8d58f6d1cea2de45c6d85e6225d3caac0b62ef619df83\#rd  
> 抓取时间: 2026/2/2 23:53:22

---

> 本期看点：本期为大家带来了基于 Vue3 制作一个拖拽式的文件上传组件与使用 JavaScript 创建 2D 或 3D 的 Shaders等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi、Matrixbirds、Yucohny

## 🔥 本周热门

**Shader Park：使用 JavaScript 创建 2D 或 3D 的 Shaders** — 这是一个用于简化创建渲染图形的 **JavaScript 开源库**，并且拥有完善的社区和文档。注意：因为使用了 WebGL，所以对浏览器的要求比较高！**更多示例**，请点击链接查看！

**长按识别二维码查看原文**

https://shaderpark.com/

💡 如果你更喜欢在 HTML Canvas 上绘制 2D 图形，推荐你观看这个视频：▶️ **JavaScript 创意、视觉编码介绍**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=dQKYao-daYw

**Prettier v2.6 发布** — 本次更新增加了 `singleAttributePerLine` 选项，可以每行只放置一个属性，以及添加了对 TypeScript v4.6 的支持、更好的添加上下文格式化 JS 代码（如装饰器、JSX 中的 `await` 以及行尾注释）。

**长按识别二维码查看原文**

https://prettier.io/blog/2022/03/16/2.6.0.html

Sosuke Suzuki

**Deno v1.20 发布** — 本次更新是一次重要的版本更新，本次更新主要提高了性能，为运行基准和测试套件提供了新的命令，同时为 AbortSignal 提供了超时，另外还升级了 V8 v10.0 和 TypeScript v4.6。

**长按识别二维码查看原文**

https://deno.com/blog/v1.20

The Deno Core Team

**快讯：**

- Joel Smith 带来了最新关于 **GatsbyConf 2022** 的消息。
    
    **长按识别二维码查看原文**
    
    https://www.gatsbyjs.com/blog/whats-new-at-gatsbyconf-2022/
    

- 📅 **VueConf US** 将于 2022 年 6 月 8 日至 10 日在佛罗里达州的劳德代尔堡举行。
    
    **长按识别二维码查看原文**
    
    https://us.vuejs.org/
    

- **Boa** 是一个基于 Rust 编写的 JS 词法分析器、解析器和编译器，**最新版本** 增加了更多的 ECMAScript 功能，并且支持了近 50% 的 Test262 套件。
    
    **长按识别二维码查看原文**
    
    https://boa-dev.github.io/
    

- 来看看如何用 JavaScript 编写面向 Twitter 的应用程序，**Twitter 宣布** 了一个用于 TS/JS 的新 Twitter API v2 SDK（测试版）。
    
    **长按识别二维码查看原文**
    
    https://twittercommunity.com/t/introducing-new-developer-tools-for-the-twitter-api-v2/168348
    

- 🤡 自 JavaScript Weekly 发布我们官方 **最差的专题图片** 以来，已经过去了一年。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/issues/529
    

**版本发布：**

**Verdaccio v5.8** – 私有的 npm 注册表，目前支持 **定制 web UI** 。

**Vuetify v3.0 Beta** – Vue UI 组件框架。

**MDX v2.1** – Markdown 中的 JSX。

**React Menu v3.0** – 可定制的嵌套菜单组件。

**Angular v13.3.0**。

## 📒 教程与趣事

**基于 Vue3 制作一个拖拽式的文件上传组件** — 四年前我们分享了Joseph 的教程：教你使用纯 JavaScript 实现拖拽式的文件上传，如今他又基于 Vue3 实现了一版。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/03/drag-drop-file-uploader-vuejs-3/

Joseph Zimmerman

**分享一个被众多开发者喜欢的 React 目录结构组织方式** — 我们已经分享过了很多诸如此类的文章，但对于“正确”的工程文件结构的布置方式，总是留有其他的视角空间，特别是 React 框架本身在找个观念上相当的不接纳。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/file-structure/

Josh W. Comeau

**jQuery 的源码分享：“双重分配模式”** — 作者在 jQuery 的源码里找到了一个有意思的技术设计，并且探索出了它的好处。

**长按识别二维码查看原文**

https://www.zhenghao.io/posts/double-assignment

Zhenghao He

**Next.js 入门课程** — Next.js 发布了一个新的入门课程，涵盖了 React 的基本知识，以及它与 Next.js 的关系，教你构建第一个 Next.js 的应用程序。

**长按识别二维码查看原文**

https://nextjs.org/learn/foundations/about-nextjs

Next.js

**Remix vs Next.js** — Remix 是一个基于 React 的全栈框架，由 React-Router 的原始团队实现。它相比 Next.js.采用了不同的方法，并且受到开发者欢迎，这篇文章将会分析它们之间的差异。

**长按识别二维码查看原文**

https://bejamas.io/blog/remix-vs-nextjs/

David Herbert

**实现一个单表排序且支持分页的功能** - 基于原生 JavaScript 实现一个支持可排序和分页功能的表格。

**长按识别二维码查看原文**

https://www.raymondcamden.com/2022/03/14/building-table-sorting-and-pagination-in-javascript

Raymond Camden

**▶  一篇关于 Typescript Excels 的讨论** — 这是来源自 Luke Hoban 和 Daniel Rosenwasser 的访谈。

**长按识别二维码查看原文**

https://thenewstack.io/earning-its-way-to-a-first-class-programming-language-where-typescript-excels/

The New Stack podcast

**为了获得瞬时的性能提升，升级 Next.js 到新版本** — 一个来自 Vercel 团队升级 Next.js 的案例分享，从 v8.0 的 demo 到 v12.0 的标准，在这个过程中可以看到 Next.js 的性能上有巨大的改进。

**长按识别二维码查看原文**

https://vercel.com/blog/upgrading-nextjs-for-instant-performance-improvements

Lydia Hallie

**使用 Set 来获得一个去除重复值的数组**

**长按识别二维码查看原文**

https://daily-dev-tips.pages.dev/posts/getting-unique-values-from-a-javascript-array-using-set/

Chris Bongers

## 🛠 代码与工具

**Peaks v1.0：交互式音频波形 UI 组件** — 当你为某种需求编写一个交互式的音频编辑器时，这个组件会提供展示音频波形UI的便捷能力。值得注意的是，Peaks.js 是由 BBC 官方团队开发的。

**长按识别二维码查看原文**

https://github.com/bbc/peaks.js

BBC

**Wave.js v2.0: 音频可视化库** — 这是一个用于 JavaScript 的音频可视化库，它能够创建对音频文件或音频流做出反应的动态动画。这里有一些 **现场演示**。

**长按识别二维码查看原文**

https://github.com/foobar404/Wave.js

Austin Michaud

**Faker v6.0：在 Node 或浏览器中生成大量虚假数据** — 在维护者“流氓”问题之后，一个社区团队 接管 了流行的 Faker 项目，他们的第一个主要版本现已发布，并提供 ESM 支持。可以看看 **v5 到 v6 迁移说明**。

**长按识别二维码查看原文**

https://github.com/faker-js/faker

Faker.js Team

**sysend.js：在同一浏览器中的打开页面或选项卡之间发送消息** — 这是一个抽象发送机制的小型库，可以实现在同一浏览器中打开的页面之间互相发送消息。该库基于 localStorage 和 BroadcastChannel API 实现，并且支持跨域通信。这里有一个是 **demo**。

**长按识别二维码查看原文**

https://github.com/jcubic/sysend.js

Jakub T. Jankiewicz

**Chrome Extension CLI: 下一代 Chrome 扩展程序服务** — 想要尽快搭建 Chrome 扩展应用？这个工具将会给你带来快捷得开发体验。

**长按识别二维码查看原文**

https://github.com/dutiyesh/chrome-extension-cli

Dutiyesh Salunkhe

**js2xml：将 JavaScript 代码转换为 XML 文档** — 相比于使用正则表达式，这里使用 XPath 来更加容易提取嵌入在 JavaScript 中的代码。

**长按识别二维码查看原文**

https://github.com/scrapinghub/js2xml

Scrapinghub

**Emoji Button: 基于原生 JavaScript 实现的表情符号选择器** — 这是一个可以实现将按钮元素转换为表情符号选择器的库。如果你对它得源码或使用方法感兴趣，可以看看 **GitHub 仓库**。

**长按识别二维码查看原文**

https://emoji-button.js.org/

Joe Attardi

**Liqvid v2.1：使用 React、HTML、CSS 和 JS 创建交互式视频** — 现在，您也可以在视频中使用 Web Animations API。

**长按识别二维码查看原文**

https://liqvidjs.org/blog/2022/03/13/liqvid-2-1/

Yuri Sulyma

## 🙋🏻‍♀️