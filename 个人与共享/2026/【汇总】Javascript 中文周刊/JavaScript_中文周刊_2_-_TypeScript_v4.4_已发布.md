# JavaScript 中文周刊 #2 - TypeScript v4.4 已发布

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491610&idx=1&sn=d2bb60f988894a311184579dd58729f1&chksm=e921abf8de5622eee1d057efab6757b292ea6fbc02b29272dd57cfa470d0bec2571e66c2e8d0#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491610&idx=1&sn=d2bb60f988894a311184579dd58729f1&chksm=e921abf8de5622eee1d057efab6757b292ea6fbc02b29272dd57cfa470d0bec2571e66c2e8d0#rd)

> 抓取时间: 2026/2/2 23:53:56

---

> 本周看点：TypeScript v4.4 已发布，同时带来了全新的官网首页。Chrome v94 中的开发工具支持了中文，可以通过 Preferences > Language 进行修改。
> 
> 编辑：Matrixbirds、liu-jin-yi、whatwewant、QC-L

**`jsc`：运行 JS 的另一种方式** — MacOS 系统的终端里，无需安装 Node 或者 Deno 的 JavaScript 运行环境，使用原生的 JavaScriptCore 也能实现 JS 的运行。（你只需要用为创建一个软连接或者可以参考文章中的示例使用它的扩展路径执行 JS 程序）

**长按识别二维码查看原文**

[https://furbo.org/2021/08/25/jsc-my-new-best-friend/](https://furbo.org/2021/08/25/jsc-my-new-best-friend/)

Craig Hockenberry

**TypeScript v4.4 已发布** — 对于喜欢静态类型的 JavaScript 用户来说是一次重大的更新。在分析控制流动态展现方面，TypeScript 已经变得更加智能，同时还在类中支持使用 `static` 块，全面提升了性能。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/

Daniel Rosenwasser

**👍 相关推荐：TypeScript 官宣了新的首页** — 这篇文章很有意思，作者分享了 TypeScript 团队重新设计首页的思考过程。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-the-new-typescript-homepage/

**Solidjs 入门级教程** — Solid 是一个用于创建用户界面的响应式的库，它没有虚拟 DOM，而是基于模板编译生成具有细粒度更新的真实 DOM 节点，然后尽可能少地出现状态更新。

**长按识别二维码查看原文**

https://css-tricks.com/introduction-to-the-solid-javascript-library/

Charlie Gerard

**热点新闻：**

- **来看看 Chrome v94 中开发者工具带来了哪些新特性。**
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/new-in-devtools-94/
    

- React Native 团队发表了一篇文章 **《关于 React Native 的多平台愿景》** 对这个框架的未来提出了更多的想法和思考。

- **长按识别二维码查看原文**
    
    https://reactnative.dev/blog/2021/08/26/many-platform-vision
    

- 你知道 Spotify 上有了新的 Web 开发者播客吗？**▶️ Minified: Web 开发者新闻**
    
    **长按识别二维码查看原文**
    
    https://open.spotify.com/show/63mosO75Cvi69t9dFChDEA
    

- Node.js 有了重大的安全改进**将在本周发版。**
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/aug-2021-security-releases2/
    

**版本发布：**

**Mongoose v6.0 发布** – 受 Nodejs 开发者欢迎的 MongoDB ODM 框架。

**Jasmine v3.9 发布** – 受欢迎的 JavaScript 测试框架。

**ExcelJS v4.3 发布** – 可读写 Excel 电子表格的 JavaScript 库。

**Jest v27.1.0 发布** – 另一种受欢迎的 JavaScript 测试框架。

**Vue-Select v3.13.0 发布** – 基于 vue 的 select 组件。

**JZZ v1.4.0 发布** – 同时支持运行在 Node.js 和浏览器环境的 MIDI 库。

**Node v16.8.0 发布** - Nodejs 运行时。

## 📖 教程与趣事

**如何使用 `Promise.any()`** — 如何使用 `Promise.any()` 从 Promise 数组里拿到第一个成功执行结束的 Promise。

**长按识别二维码查看原文**

https://dmitripavlutin.com/promise-any/

Dmitri Pavlutin

**如何将大型项目从 vue2 升级到 vue3**

**长按识别二维码查看原文**

https://crisp.chat/blog/vuejs-migration/

Baptiste Jamin

**如何使用 Git 为 JavaScript 和 TypeScript 开发者创建 Monorepos**

**长按识别二维码查看原文**

https://hieunc.medium.com/how-to-setup-monorepos-with-git-for-javascript-and-typescript-d42f1294c0d2

Hieu Nguyen (Jack)

## 🛠 代码与工具

**React Toastify 8.0：一款成熟通知组件库迎来重大更新** — React Toastify 已经五岁了，这是一款为应用程序提供弹出式 ‘Toast’ 的成熟解决方案，在 8.0 的版本里有了全新的外观升级和 API 改进，你甚至直接可以在通知里看到基于 Promise 的状态变化。

**长按识别二维码查看原文**

https://github.com/fkhadra/react-toastify/releases/tag/v8.0.0

Fadi Khadra

**simplex-noise.js：一个高性能的单工噪声实现** — 查看此CodePen示例，即可了解它的作用，无需过多解释，此外，这个看起来非常“自然”的噪音，还可以用于景观生成或 胶片颗粒。

**长按识别二维码查看原文**

https://github.com/jwagner/simplex-noise.js

Jonas Wagner

**filter-console 1.0：过滤掉不需要的 `console.log()` 的输出结果** — 如果你的应用程序中的某些内容与旧的 `console.log` 交错在一起，并且你不想看到它，这可能会很有用。

**长按识别二维码查看原文**

https://github.com/sindresorhus/filter-console

Sindre Sorhus

**Drift 1.5：为你网站上的图片添加 ‘悬浮放大’** — 具有极强的可定制性。预想了解具体使用，可以查看此 CodePen demo。此 Demo 基于 Imgix 实现，你无需依赖 Imgix 的系统，就可以将自己的图片托管在 Cloudinary 或者任何其他主机上。

**长按识别二维码查看原文**

https://github.com/imgix/drift

imgix

**Nanny-State：非常简单的状态管理** — 一款非常轻量的无框架状态管理方案，基于 µhtml 做页面渲染。

**长按识别二维码查看原文**

https://github.com/daz4126/Nanny-State

DAZ

**Vuestic UI 1.2：一个 Vue.js 3.0 UI 框架** — 具有 52 种可定制的响应式组件，自上次提到它以后，它又引入了 日历选择器 同时已经支持了 tree shaking。

**长按识别二维码查看原文**

https://vuestic.dev/

Vuestic UI

**REAFLOW：基于节点的可视化 React 方案** — 如果要渲染和操作节点的树、图表。可以查看此 demo，以了解它的工作方式及原理。

**长按识别二维码查看原文**

https://github.com/reaviz/reaflow

REAVIZ

**CornerstoneTools: 一款适用于打造医学影像(DICOM) 的工具** — 这里有一个完整的生态系统需要探索。

**长按识别二维码查看原文**

https://github.com/cornerstonejs/cornerstoneTools

cornerstone.js

**Tiny Schema Validator 5.0: JSON Schema 验证器**

**长按识别二维码查看原文**

https://github.com/5alidz/tiny-schema-validator

khaled

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。