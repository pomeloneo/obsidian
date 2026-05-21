# JavaScript 中文周刊 #94 - Svelte 4 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521958&idx=1&sn=b074a1edc1db6f2673bb01ee1f8b4420&chksm=e921dd44de5654522f8ec668c64530bd449b11806be96d52c0716d6f1ba7a5fa7cca5b940be0\#rd  
> 抓取时间: 2026/2/2 23:51:57

---

> 本期看点：在 Svelte 3 发布的四年后，这个受欢迎的编译时框架迎来了最新的重大版本发布，它勇于以自己的方式做事。如果你是新手，可以通过交互式教程来熟悉它；如果你已经是老手了，可以直接享受 v3 到 v4 迁移指南、全新改版的网站和更出色的性能。

> 编辑：Yucohny

## 🔥 本周热门

**UnsuckJS：逐步使用轻量级 JavaScript 库**——“无需构建工具，无需编译器，无需麻烦。” 这是一个简单页面上的前端 JavaScript 库的表格，但也是一个很方便的表格，可以让你了解到诸如 Preact、bau、htmx、Hyperapp 和 Mithril 等各种库的相对流行程度、大小和最新版本。

**长按识别二维码查看原文**

https://unsuckjs.com/

Adam Hill

**Svelte 4 发布**——在 **Svelte 3** 发布的四年后，这个受欢迎的编译时框架迎来了最新的重大版本发布，它勇于以自己的方式做事。如果你是新手，可以通过 **交互式教程** 来熟悉它；如果你已经是老手了，可以直接享受 **v3 到 v4 迁移指南**、**全新改版的网站** 和更出色的性能。

**长按识别二维码查看原文**

https://svelte.dev/blog/svelte-4

Rich Harris and the Svelte Team

🤔 Claudio Holanda 的文章 _**Thoughts on Svelte(Kit), one year and 3 billion requests later**_ 提供了一些更加有趣的内容。

**长按识别二维码查看原文**

https://claudioholanda.ch/en/blog/svelte-kit-after-3-billion-requests/

**一窥 TypeScript v5.2 的新关键字：`using`**——`using` 关键字在 TypeScript v5.2 中引入了类似于 Python 的 `with` 上下文管理功能，它提供了一种在对象离开作用域时自动运行 `Symbol.dispose` 函数的方式。你可以使用它来关闭数据库连接、关闭文件句柄等等。

**长按识别二维码查看原文**

https://www.totaltypescript.com/typescript-5-2-new-keyword-using

Matt Pocock

即使你不怎么使用 TypeScript，此消息也值得关注。因为有关 `using` 的想法也是一个 ECMAScript 提案（目前处于第 3 阶段），被称为 _Explicit Resource Management_，在 **示例中** 有更多详细信息可供参考。

**长按识别二维码查看原文**

https://github.com/tc39/proposal-explicit-resource-management\#motivations

**开始学习 JavaScript AI 框架**——Andreessen Horowitz（简称 a16z）是一家知名的风险投资公司，但他们也有自己的工程团队，为希望在不太考虑工具链的情况下尝试现代机器学习技术的 JavaScript 开发人员提供了一个 **“开始学习 AI 框架”的模板**。

**长按识别二维码查看原文**

https://a16z.com/2023/06/21/the-getting-started-with-ai-stack-for-javascript/

Li, Li, and Casado（Andreessen Horowitz）

**⚡️ 快讯：**

- Fresh 是一个以 Deno 为主的全栈 Web 框架，最新发布了 **Fresh v1.2**。尽管有一些对其维护性的担忧，但现在有了一位新的全职维护者——Marvin Hagemeister，未来发展前景可期。欢迎 Marvin 的加入！

**长按识别二维码查看原文**

https://deno.com/blog/fresh-1.2

## 📒 教程与趣事

**将视频或 3D 模型的旋转与滚动驱动的动画同步**——只需使用 JavaScript 编写一点点代码，就可以使用滚动驱动的动画来控制 3D 模型与视频，而这是现代时尚网站上常见的效果。

**长按识别二维码查看原文**

https://www.bram.us/2023/06/21/synchronize-videos-3d-models-to-scroll-driven-animations/

Bramus van Damme

**定位锚点弹出框（Popover）**——Popover 通常相对于其触发器定位，但使用新的 `popover` 属性时，由于这些弹出框位于顶层，脱离了其触发器的上下文，因此定位可能会有些棘手。Hidde 探讨了解决这个问题的一些方法。

**长按识别二维码查看原文**

https://hidde.blog/positioning-anchored-popovers/

Hidde de Vries

## 🛠 代码与工具

**Selecto.js：在拖动区域内使元素可选择**——假设有一些代表选择项、数据或其他内容的元素，并且希望用户能够通过点击或拖动来选择其中的一部分，就是 Selecto.js 所做的事情。**这里有一些实时示例**。

**长按识别二维码查看原文**

https://github.com/daybrush/selecto

Daybrush（Younkue Choi）

**AutoAnimate：通过一行代码为应用添加动画效果**——可以在页面上查看一些漂亮的示例，并且这个库可以与 React、Vue、Svelte 或原生 JavaScript 一起使用。

**长按识别二维码查看原文**

https://auto-animate.formkit.com/

FormKit

**Toad Scheduler：内存中的 Node 和浏览器任务调度器**——提供了比 `setTimeout` 或 `setInterval` 更多的结构，并支持类似 cron 的调度。

**长按识别二维码查看原文**

https://github.com/kibertoad/toad-scheduler

Igor Savin

**Kysely：流畅、类型安全的 SQL 查询构建器**——受 Knex 启发，并针对 Node 进行开发，同时也适用于 Deno 和浏览器，通过其流畅的 API，提供良好的自动完成体验。这里是 GitHub 仓库。

**长按识别二维码查看原文**

https://kysely.dev/

Sami Koskimäki

**AI.JSX：基于 JSX 的人工智能应用框架**——它并不是 React，但在使用上给人一种类似 React 的感觉，允许开发者指定像 ChatGPT 这样的大型语言模型应该如何与应用集成。幸运的是，这里有一系列的 **教程** 可供学习。

**长按识别二维码查看原文**

https://github.com/fixie-ai/ai-jsx

Fixie.ai

💡 SBOM 是“软件材料清单（software bill of materials）”的缩写，本质上是应用程序所依赖的依赖项和组件的清单，正如 **Liran Tal 解释的那样**。

**长按识别二维码查看原文**

https://snyk.io/blog/generate-sbom-javascript-node-js-applications/?utm_campaign=aom_2023&utm_medium=paid-email&utm_source=cooperpress-javascript-weekly&utm_content=generate-sbom-javascript-node-js-applications

**版本发布：**

- **React Native v0.72**

- **Nest v10.0**
    
    ↳ 用于构建企业级应用程序的流行 Node.js 框架。
    

- **ESLint v8.43**

- **Perspective v2.3**
    
    ↳ 数据可视化和分析组件。核心部分采用 C++ 编写，并编译为 WebAssembly，可以从 JavaScript 中 使用。
    

- **Tesseract.js v4.1.1**
    
    ↳ 适用于 100 多种语言的原生 JavaScript OCR。此版本修复了一个关于 处理使用 iOS 设备拍摄的图像的关键错误。
    

- **Shoelace v2.5**
    
    ↳ 设计精良、适用于任何框架的 UI 组件套件。
    

- **TestCafe v3.0**
    
    ↳ 用于自动化端到端测试的 Node.js 工具。
    

- **AlaSQL v4.1**
    
    ↳ 适用于浏览器和 Node 的 JS SQL 数据库。
    

- **Octokit.js v2.1**
    
    ↳ 适用于浏览器、Node 和 Deno 的 GitHub SDK。
    

## 🙋🏻‍♀️