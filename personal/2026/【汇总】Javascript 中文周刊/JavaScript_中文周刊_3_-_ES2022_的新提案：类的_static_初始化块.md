# JavaScript 中文周刊 #3 - ES2022 的新提案：类的 static 初始化块

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491967&idx=1&sn=3c538c1129814ea4aca30d7d0fabdcfa&chksm=e921aa9dde56238b125ba92433491741ec1cbb8cabd695a5a7b3ca960b6f33a18c0ee838e908#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491967&idx=1&sn=3c538c1129814ea4aca30d7d0fabdcfa&chksm=e921aa9dde56238b125ba92433491741ec1cbb8cabd695a5a7b3ca960b6f33a18c0ee838e908#rd)

抓取时间: 2026/2/2 23:53:55

---

> 本期看点：class 的 static 初始化块的提案进入第四阶段，已被纳入 ES2022。对提案感兴趣的小伙伴可以查看 TC39 的第 85 次会议纪要。一位以色列的 JavaScript 专家成功试验了 JS 反调试技术的可行性。

编辑 | Matrixbirds

liu-jin-yi

Otto

QC-L

**Visual Studio Code 更新（2021 年 8 月）** — 官方团队会选用前一个月的月份来命名发布版本，包含的新功能有：语言自动检测，支持内置括号彩色（可通过开启 `editor.bracketPairColorization.enabled`），改进终端的字形渲染，支持行内 JS/TS 的参数名称和类型提示，改进了 async 函数和 Node.js 内部的单步调试。

**长按识别二维码查看原文**

https://code.visualstudio.com/updates/v1_60

Microsoft

**ES2022 的新语法提案：类静态初始化块** — 熟悉 Java 的同学会觉得这简直和 Java 如出一辙，尽管如此，该提案当前已进入第四阶段，计划纳入 ES2022。

**长按识别二维码查看原文**

https://2ality.com/2021/09/class-static-block.html

Dr. Axel Rauschmayer

**💡 对上面的话题感兴趣？你可以参考 Hemanth HM 所记录的 TC39 第 85 次会议的更新** 关于未来会被纳入到 JavaScript 的新特性，其中包括 来自 Hack 语言的管道符号 以及 `Array.fromSync`。

**长按识别二维码查看原文**

https://dev.to/hemanth/updates-from-the-85th-meeting-of-tc39-2kep

**Neutralino v2.7：轻量级跨平台桌面程序框架** — 功能与 Electron 类似，不同的是，Electron 会依赖不同版本的 Chromium，而它则基于原生内置的 `webview`，与 Electron 相比较，更小，更快，但需要你了解不同 `webview` 之间存在的差异。

**长按识别二维码查看原文**

https://neutralino.js.org/

Codezri

**热点新闻：**

- Node.js 的 v12 和 v14 两个分支上的**代码进行安全更新**修复了一些路径和符号链接相关的安全漏洞。Node v16 不存在上述问题。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/aug-2021-security-releases2/
    

- 面向前端开发者的**交互学习工具**系列。
    
    **长按识别二维码查看原文**
    
    https://www.smashingmagazine.com/2021/09/interactive-learning-tools-front-end-developers/
    

- **聊一聊 Twitter 上的对 “div soup” 和 “uglified” CSS 的解释** 以及在 React-Native 上的实践。
    
    **长按识别二维码查看原文**
    
    https://giuseppegurgone.com/twitter-html/
    

- 一名开发者证明了 **反调试技术** 概念的可行性，可以使用 JS 代码检测当前网页是否正在被调试，同时更改代码的执行流程。
    
    **长按识别二维码查看原文**
    
    https://medium.com/@weizmangal/javascript-anti-debugging-some-next-level-sh-t-part-2-abusing-chromium-devtools-scope-pane-b2796c00331d
    

**版本发布：**

- **socket.io v4.2.0 发布** – 实时场景基础库。
    
    **长按识别二维码查看原文**
    
    https://github.com/socketio/socket.io/releases/tag/4.2.0
    

- **Relay v12.0 发布** – 数据驱动的 React 框架。
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/relay/releases/tag/v12.0.0
    

- **OpenPGP.js v5.0.0 发布** – OpenPGP JS 版实现。
    
    **长按识别二维码查看原文**
    
    https://github.com/openpgpjs/openpgpjs/releases/tag/v5.0.0
    

- **on-change v4.0** – 观察对象和数组的变化。
    
    **长按识别二维码查看原文**
    
    https://github.com/sindresorhus/on-change
    

- **AdonisJS August 发布** – 全功能 Node.js web 应用框架。
    
    **长按识别二维码查看原文**
    
    https://docs.adonisjs.com/releases/august-2021-release
    

## 📖 教程与趣事

**如何打造一个价值每年 30w $ 的 Vue 组件库** — Vuetify 的作者的自述，文中讲述了如何持续维护开源组件库，并使其产生收益，本文虽然没有太多技术方面的内容，但文章观点或许会让你有所启发。

**长按识别二维码查看原文**

https://www.starterstory.com/stories/i-built-a-300k-year-vue-js-component-library

John Leider

**在 JavaScript 中使用树形数据结构** — 遍历树的基本方式：广度优先和深度优先，通过可视化的方式助你更快地理解。

**长按识别二维码查看原文**

https://stackfull.dev/tree-data-structure-in-javascript

Anish Kumar

**当我们用 `npm` 的时候，需要注意避免的几种常见的错误使用方式** — 如何避免常见的几种错误使用方式，如：依赖管理，发布包等。

**长按识别二维码查看原文**

https://blog.bitsrc.io/common-npm-mistakes-every-developer-should-avoid-60ab0642d8f9

Bhagya Vithana

**在 Svelte 应用程序中使用状态管理** — 入门教程。

**长按识别二维码查看原文**

https://auth0.com/blog/state-management-in-svelte-applications/

Fikayo Adepoju

**为什么 Electron 应用很好？** — Niels 在本文中认同了许多对 Electron 常见的批评，但其实 Electron 的用户并不关注，他认为也不需要关注。

**长按识别二维码查看原文**

https://nielsleenheer.com/articles/2021/why-electron-apps-are-fine/

Niels Leenheer

**在 Next.js 里使用状态管理** — 在 Next.js 应用程序中管理状态很快就会变得棘手。这着眼于一些模式，以帮助避免常见场景的复杂性，并避免”多层嵌套 Provider”。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/08/state-management-nextjs/

Átila Fassina

**React** useContext() **Hook 入门教程**

**长按识别二维码查看原文**

https://dmitripavlutin.com/react-context-and-usecontext/

Dmitri Pavlutin

**在 JavaScript 里异步函数缓存**

**长按识别二维码查看原文**

https://stackfull.dev/memoizing-async-functions-in-javascript

Anish Kumar

## 🛠 代码与工具

**TypeIt：功能丰富且实用的打字效果工具** — 自称是 “地球上最通用的 JavaScript 打字效果工具”，采用函数式 API，但请注意虽然它对 个人/OSS 使用是免费的，但你仍需要为商业许可证支付（少量）费用。

**长按识别二维码查看原文**

https://typeitjs.com/

Alex MacArthur

**Stitches 1.0：现代化样式库** — 基于 CSS-in-JS 的解决方案，提供了高性能，服务端渲染，主题化，关键 CSS 路径，直观的 api 等等。

**长按识别二维码查看原文**

https://stitches.dev/

Modulz

**smartcrop.js：基于图片内容进行裁剪** — 支持在浏览器和 Node.js 环境里，根据图片内容，找到最合适的部分进行图像裁剪。

**长按识别二维码查看原文**

https://github.com/jwagner/smartcrop.js

Jonas Wagner

**Roadroller：一个重量级的 JavaScript 代码压缩工具** — 它适用于将 JavaScript 代码压缩到极致的场景，更加适合示例代码，而非生产应用程序。

**长按识别二维码查看原文**

https://lifthrasiir.github.io/roadroller/

Kang Seonghoon

**Crank.js：在 h 函数，Promises，Generators 里编写 JSX 组件** — 在 JavaScript 中，通常会使用 JSX 来编写 HTML 代码，而使用 JSX 编写的组件基本上都是函数或者 Generator 函数。具体请参阅 示例代码。

**长按识别二维码查看原文**

https://crank.js.org/

Brian Kim

**parse-domain：按域名结构划分的工具** — 可以根据主机名划分出：子域名、一级域名、顶级域名，包含来自公共后缀列表中的有效顶级域名。

**长按识别二维码查看原文**

https://github.com/peerigon/parse-domain

Peerigon

**Mafs：一个基于 React 的数学可视化方案** — 这是一套成熟的满足复杂数学场景的可视化方案。你只需参考入门指南，即可以轻松执行，同时还包含很多优秀的应用场景，比如 亚轨道航天飞行。

**长按识别二维码查看原文**

https://mafs.dev/

Steven Petryk

**bundle：`npm` 包文件大小快捷查看工具** — 只需输入包的名字，点击 “run” 按钮，此工具会为你分别提供压缩，打包，以及 gzip 后的包文件大小。

**长按识别二维码查看原文**

https://bundle.js.org/

Okiki Ojo

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。