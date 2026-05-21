# JavaScript 中文周刊 #146 - 如何中止 JavaScript 中的 Promise

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533312&idx=1&sn=66f7b630f98bf632d8537718c81081ab&chksm=e92108e2de5681f4e70edd35cb9e25302cdf33a859695af7585fac8dcfd649053e2aa71cad3d\#rd  
> 抓取时间: 2026/2/2 23:50:55

---

> 本期看点：你可以取消 XHR 和 fetch 请求，但你能取消普通的 promise 吗？目前还不行，但 Zachary 探讨了如何实现最接近的效果：告诉 promise 游戏结束，并丢弃/忽略其最终结果。

> 编辑：TimLi

🔥 本周热门

**如何中止 JavaScript 中的 Promise** — 你可以取消 XHR 和 fetch 请求，但你能取消普通的 promise 吗？目前还不行，但 Zachary 探讨了如何实现最接近的效果：告诉 promise 游戏结束，并丢弃/忽略其最终结果。

**长按识别二维码查看原文**

https://webdeveloper.beehiiv.com/p/cancel-promises-javascript

Zachary Lee

**regex v2.1：将 JavaScript 的正则表达式支持提升到 ES2024+** — 来自《高性能 JavaScript》和《正则表达式食谱》合著者的 JavaScript 正则表达式增强工具。支持 ES2024 的所有正则功能，新增自由间距和注释、原子组、正则子程序、上下文感知的 `RegExp` 实例插值等功能。

**长按识别二维码查看原文**

https://github.com/slevithan/regex

Steven Levithan

💡 作者还提到，针对 `regex` 的 Babel 插件已经发布。

**长按识别二维码查看原文**

https://github.com/slevithan/babel-plugin-transform-regex

**快讯：**

- Nicholas C. Zakas 撰文介绍不同的 JavaScript 运行时 以及如何保持切换运行时的能力。
    
    **长按识别二维码查看原文**
    
    https://ckarchive.com/b/lmuehmh08vwdxid7kkm78cdoo5v00hg
    

- React Native 团队表示，构建现代 React Native 应用的开发者应该 使用一个框架，例如 Expo。
    
    **长按识别二维码查看原文**
    
    https://reactnative.dev/blog/2024/06/25/use-a-framework-to-build-react-native-apps
    

- 网络先驱 Marc Andreessen 讲述了 ▶️ Mosaic 和 Netscape 的起源故事。
    
    **长按识别二维码查看原文**
    
    https://pmarca.substack.com/p/the-true-story-as-best-i-can-remember
    

- 🤦 如果你无法将 Lighthouse 分数提升到 100%，你可以假装。这是一个需要注意的技巧。
    
    **长按识别二维码查看原文**
    
    https://www.amitmerchant.com/javascript-snippet-that-sets-all-lighthouse-scores-to-hundred/
    

- 至少有 535 种方法用 JavaScript 重新加载页面。
    
    **长按识别二维码查看原文**
    
    https://www.phpied.com/files/location-location/location-location.html
    

📒 教程与趣事

**用 React 18 提升《纽约时报》的网页性能** — 去年，《纽约时报》着手在其旗舰新闻网站上充分利用 React 18。这是对升级过程中所面临的挑战以及所获得的显著好处的介绍。

**长按识别二维码查看原文**

https://open.nytimes.com/enhancing-the-new-york-times-web-performance-with-react-18-d6f91a7c5af8?gi=37f9d14c9c45

Ilya Gurevich (NYT)

**如何使用 WebAssembly 从 JavaScript 调用 Golang 库** — 将 Go 代码编译为 WebAssembly 在浏览器中开辟了一些有趣的机会。

**长按识别二维码查看原文**

https://tderflinger.com/en/how-to-integrate-go-library-js-webpage-webassembly

Thomas Derflinger

**我们如何驯服 Node.js 的事件循环延迟** — Node 以使用极少的线程却能高效处理大量客户端而闻名，只要每个客户端的工作量很小。然而，当工作量不小的时候，事情可能会迅速脱轨。

**长按识别二维码查看原文**

https://trigger.dev/blog/event-loop-lag

Eric Allam

**残障人士如何使用网络** — 描述了残障人士使用网络的工具和方法，以及他们面临的障碍。有趣的是 用户角色，展示了特定人群的具体体验。

**长按识别二维码查看原文**

https://www.w3.org/WAI/people-use-web/

W3C

**一套现代网页性能指南** — 一系列有用的指南，涵盖了核心网页性能指标、JavaScript 优化、指标等内容。

**长按识别二维码查看原文**

https://www.speedcurve.com/web-performance-guide/

SpeedCurve

**📄 为什么 Google Sheets 将其计算工作器从 JS 移植到 WasmGC** Thomas 和 Steiner (Google)

**长按识别二维码查看原文**

https://web.dev/case-studies/google-sheets-wasmgc

**📄 在 JavaScript 中处理粘贴内容** Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2024/07/03/working-with-pasted-content-in-javascript

**📄 如何用 JavaScript 解析 HTML** Brian Wachira

**长按识别二维码查看原文**

https://blog.apify.com/javascript-parse-html/

**📄 TypeScript v5.5：一场重磅发布** Dan Vanderkam

**长按识别二维码查看原文**

https://effectivetypescript.com/2024/07/02/ts-55/

🛠 代码与工具

**BWIP-JS：纯 JavaScript 的条形码生成器** — 一个可以用超过 100 种不同条形码类型和标准生成条形码的库，包括单维和二维条形码。当然，这里有一个在线演示，你可以发现比想象中更多的条形码类型。

**长按识别二维码查看原文**

https://github.com/metafloor/bwip-js

Mark Warren

**Superstruct v2.0：定义接口以在运行时验证数据** — 设计用于在运行时验证数据，具有受 TypeScript、Flow、Go 和 GraphQL 启发的注释 API。GitHub 仓库。

**长按识别二维码查看原文**

https://docs.superstructjs.org/

Ian Storm Taylor

**Termino.js v2.0：在浏览器中创建终端体验** — 无依赖项，易于定制，你可以在单个页面上创建多个终端实例。演示。

**长按识别二维码查看原文**

https://github.com/MarketingPipeline/Termino.js

Marketing Pipeline

**Fabric.js v6.0：一个 SVG 到 Canvas 和 Canvas 到 SVG 的库** — 在 HTML5 canvas 上提供一个交互式对象模型，使得处理多个视觉元素更容易。主页是一个完整的在线演示。

**长按识别二维码查看原文**

https://github.com/fabricjs/fabric.js

Fabric.js

**Flitter：一个 Flutter 风格的 JavaScript 数据可视化框架** — 具有声明式语法，支持 SVG 和 Canvas，允许你构建高性能的数据可视化、交互式图表、图表等。它还易于与 React、Svelte 等集成。

**长按识别二维码查看原文**

https://flitter.pages.dev/

Flitter

**SquirrellyJS v9：一个强大的模板引擎** — 一个现代化、可配置且快速的模板引擎，承诺“拥有 Nunjucks 的力量”和“EJS 的简洁”。这里有一个 在线 playground，你可以看到它的实际效果。GitHub 仓库。

**长按识别二维码查看原文**

https://squirrelly.js.org/

Ben Gubler

**Sliderland：一个极简的编码游乐场** — 一个基于滑块控件的可视化工具，你可以用简单的公式进行编码。我们几年前曾链接过这个，但它仍然是进行一些快速、可视化的 JS 数学实验的有趣方式。Tixy.land 类似，但基于二维网格。

**长按识别二维码查看原文**

https://sliderland.blinry.org/

blinry

**版本发布：**

- **Backbone.js v1.6** – 经典库的小更新。

- **Qwik v1.6** – Qwik v2 即将到来。

- **一系列 Node.js 安全更新** 已于 7 月 9 日发布。

- **ESLint v9.6、PrimeVue v4.0、Bun v1.1.18**

- **Hexo v7.3** – 流行的 Node.js 博客框架/生成器。

- **gridstack.js v10.3** – 快速构建响应式交互式仪表板。

- **React-PDF v9.1** – 用于显示 PDF 的 React 组件。

- **MUI X v7.8** – 流行的 React 组件套件。

🙋🏻‍♀️