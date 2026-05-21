# JavaScript 中文周刊 #47 - 如何编写不阻塞浏览器的代码？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247508173&idx=1&sn=39573b3de16983a089b81575c67a968d&chksm=e921eb2fde566239e6cf006139780ceae0edeb80a664162ad4ac840eb6f4f2ca8fcf72588d04\#rd  
> 抓取时间: 2026/2/2 23:53:00

---

> 本期看点：本期为大家带来了关于如何编写不阻塞浏览器的代码与用 Vuelidate 在 Vue 3 中轻松进行表单验证等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi、Yucohny、Levi

## 🔥 本周热门

**bundlejs：在线的 npm 包捆绑器和大小检查器** — 一个在线工具，可以对项目进行 treeshake、捆绑、缩小和压缩（gzip 和 brotli），并向你展示它们的权重。尽管 **Bundlephobia** 是这个领域的另一个流行选项，但是 **Mark Erikson 认为** bundlejs 是一个更好的选择。

**长按识别二维码查看原文**

https://bundlejs.com/

Okiki Ojo

**如何编写不阻塞浏览器的代码** — 如果你看到一些文章或工具在谈论将代码从 “主线程” 中分离出来，并想知道为什么这很重要，那么你可以看看这篇文章。它涵盖了事件循环、Web Worker、异步调度，以及它们是如何产生作用的。

**长按识别二维码查看原文**

https://medium.com/@matthew.costello/frontend-web-performance-the-essentials-1-cb6513e1c3a1

Matthew Costello

**快讯：**

- **VS Code 发布更新** 。你现在可以轻松地打开和关闭源映射，在 JS 调试器中使用 Step Into Target，并且有一个 3 路合并编辑器。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_69
    

- 微软开始推出（目前在“私人预览版”中）支持 VS Code 远程开发功能的 **VS Code 服务器**，以便你可以在自己的硬件上运行它。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2022/07/07/vscode-server
    

- MDN 的成员正在讨论 **将他们的代码示例** 使用新的 JavaScript 标准重写。
    
    **长按识别二维码查看原文**
    
    https://github.com/orgs/mdn/discussions/143
    

- Shopify 现在是 **Ecma 的正式成员** ，并且即将成为 TC39 的代表之一，所以很期待看到 **JS module blocks** 上线 😆。
    
    **长按识别二维码查看原文**
    
    https://mobile.twitter.com/dassurma/status/1543957363291557888
    

**版本发布：**

- **Node v14.20.0 （LTS），v16.16.0 （LTS） 和 v18.5.0 （Current） 发布**。

- **Fuite v1.6** – 用于在 Web 应用程序中查找内存泄漏的工具。

- **oclif v3.1** – Node.js 开放式 CLI 框架。

- **Notion SDK for JS v2.0** – Notion 官方 JavaScript 客户端。

- **Tabulator v5.3** – 交互式表格与数据网格控件。

- **Preact v10.9** – 实现了除 `useId` 以外的 React 18 新 Hook。

- **Perspective v1.5.1** – 通过 WebAssembly 快速实现数据可视化。

## 📒 教程与趣事

**Chess Engines：从零到一** — 本篇文章详细的介绍了如何从零开始设计一个国际象棋的引擎。**chessboard.js** 和 **chess.js** 这两个库也可以用于实现一个国际象棋。

**长按识别二维码查看原文**

https://www.chessengines.org/

Will DePue

**使用 htmx 和 Hyperscript 重新构想前端 Web 开发** — **写 JavaScript 以避免写 JavaScript** 也是一篇关于 htmx 和这一广泛现象的精辟论述。

**长按识别二维码查看原文**

https://nomadiq.hashnode.dev/reimagining-front-end-web-development-with-htmx-and-hyperscript

Owen Jones

**用 XState 简化你的全栈应用程序** — 状态管理是那种需要花点时间才能真正掌握的东西，尤其是在不常与之相关的开发领域中，而本篇文章主要向你介绍了如何简化项目中的状态管理代码，使其更易读。

**长按识别二维码查看原文**

https://blog.theodo.com/2022/07/simplify-your-applications-with-xstate/

Daniel Belo Gonçalves

**▶  用 Vuelidate 在 Vue 3 中轻松进行表单验证** — **Vuelidate** 是一个验证库。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=7alh1KowAEI

John Komarnicki

**如何在 JavaScript 中使用原生 Web 共享 API**

**长按识别二维码查看原文**

https://daily-dev-tips.com/posts/using-the-native-web-share-javascript-api/

Daily Dev Tips

## 🛠 代码与工具

**Big Calendar 1.x：类似谷歌日历、Outlook 日历的 React 组件** — 使用 flexbox 来提高响应能力。

**长按识别二维码查看原文**

https://github.com/jquense/react-big-calendar

Jason Quense

**PocketBase：一个开源的后端服务框架** — 这是一个有趣的项目，PocketBase 可以在许多场景中取代 Firebase。它是用 Go 编写的，可以用来作为 JavaScript 前端应用程序的后端。它使用 SQLite，您还可以获得一个内置的管理仪表板，其中包含文件和用户管理。**在线演示**和**优质的文档**

**长按识别二维码查看原文**

https://pocketbase.io/

Gani Georgiev

**ProtoScript：Protocol Buffers 运行时和代码生成工具** — 该库的运行时性能不仅比谷歌的好很多，而且代码体积更小。并且代码生成器生成惯用的 JavaScript，还带有 JSON（反）序列化器和 TSDoc 注释。

**长按识别二维码查看原文**

https://www.npmjs.com/package/protoscript

Tate Thurston

**Deprank：使用 PageRank 查找代码库中的重要文件** — **PageRank**过去是一种与 Google 网页排名相关的算法，但该算法思想可以适用于对任何类型的多链接项目进行排名。

**长按识别二维码查看原文**

https://github.com/codemix/deprank

Codemix Ltd

**tsParticles：网页上的粒子、五彩纸屑和烟花特效** — 可在 Web 上创建可自定义的粒子相关效果。使用常规 2D Canvas 来提高兼容性。

**长按识别二维码查看原文**

https://particles.js.org/

Matteo Bruni

**React 的 Amplify UI 现在开放使用了** — Amplify是一种将各种 AWS 服务捆绑在一起的子平台，使它们更易于用于前端和移动项目。其中一部分是 **Amplify UI**，一个直接连接到 AWS 云的 React 组件集合（也提供 Vue 和 Angular 版本）。

**长按识别二维码查看原文**

https://aws.amazon.com/about-aws/whats-new/2022/06/general-availability-amplify-ui-react/

Amazon Web Services, Inc.

**Wayne：类似于 Express.js 但是用在 Service Worker 内部** — 具体来说，它是一个在 Service Worker 内部使用的路由库。

**长按识别二维码查看原文**

https://github.com/jcubic/wayne

Jakub T. Jankiewicz

**🤔 再说点你不知道的：**

- **您现在可以在 AWS 之外使用 AWS 的 IAM 角色/访问管理系统。**
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/security/extend-aws-iam-roles-to-workloads-outside-of-aws-with-iam-roles-anywhere/
    

- **一个没有任何数字的数独题目，居然需要两个小时才能解决？**
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=N1Fi3xt3NkY
    

- Lea Verou 在 2022 年 CSS 日发表了 **关于 CSS 自定义属性的精彩演讲**你应该会学到很多。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=ZuZizqDF4q8
    

- 🐘 我们也有**Postgres newsletter**，最近 Postgres 领域发生了很多事情，如果你也使用它，**可以去看一下**。
    
    **长按识别二维码查看原文**
    
    https://postgresweekly.com/
    

## 🙋🏻‍♀️