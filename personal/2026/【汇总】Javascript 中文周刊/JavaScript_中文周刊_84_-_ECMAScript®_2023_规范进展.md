# JavaScript 中文周刊 #84 - ECMAScript® 2023 规范进展

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519043&idx=1&sn=04e92d5c4c86694e0c8f0844b82386df&chksm=e921c0a1de5649b73cf6cd51823f1c4a965e1930f9d2f64ab109448173baea8c7d6f89803b9d\#rd  
> 抓取时间: 2026/2/2 23:52:11

---

> 本期看点：上周，htmx v1.9 发布、ECMAScript® 2023 规范进展发布、Angular 重装上阵、与一些大佬聊聊 Node.js 的现状。

> 编辑：liu-jin-yi、TimLi777

## 🔥 本周热门

**JavaScript 相等性表格游戏** — 在了解了 JavaScript 中 `==` 的恐怖之后，扫雷游戏可能变得轻松了许多。如果需要深入了解，可以查看 ECMAScript 规范中的 **第 7.2.14 节** ，但一般情况下，最好使用三个等号（`===`），除非有充分的理由不这样做。

**长按识别二维码查看原文**

https://eqeq.js.org/

Reinis Ivanovs

**htmx v1.9 发布** — htmx (**主页**) 是一个越来越受欢迎的库，它允许用户通过标记 HTML 而不是编写大量 JavaScript 来使用 WebSockets、SSE、AJAX 和 CSS 过渡。v1.9 添加了对 view transitions 和内联事件处理的支持。**这些代码示例** 值得一看，htmx 可以让很多东西成为可能，而且工具或标记很少。

**长按识别二维码查看原文**

https://htmx.org/posts/2023-04-11-htmx-1-9-0-is-released/

htmx team

**ECMAScript® 2023 规范进展** — 在二月份过早地发布 ES2023 规范的进展之后，现在可以宣布：TC39 已经批准了 ECMAScript 2023 规范，虽然它仍然是候选状态，但它距离最终的 ECMA 大会批准更近了一步。2023 年的 **完成提案列表** 现在包括了 **从后面查找数组**，**支持哈希**，**Symbols 作为 WeakMap 的键**，和**通过复制更改数组**。

**长按识别二维码查看原文**

https://tc39.es/ecma262/2023/

ECMA International

**快讯：**

- ▶️ **Angular 重装上阵**，Fireship 认为 Angular 正在回归。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=nQ2A30cD3Q8
    

- Serverless 平台 AWS Lambda 在其 JS runtime 中 **引入了响应流** ，因此您可以在数据变得可用时发送响应数据，而不是一次性发送所有数据。(→ **通过 Serverless Status 了解**)
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/compute/introducing-aws-lambda-response-streaming/
    

- **/[]/** 探讨了在正则表达式中使用空字符类时 **似乎是 JS 特有的怪癖**。
    
    **长按识别二维码查看原文**
    
    https://www.abareplace.com/blog/emptybrackets/
    

- 在分析了 **GitHub pull request** 使用的语言时，可以明显看出 JavaScript/TypeScript 目前处于领先地位，Python 紧随其后。评论区更是有很多奇怪的方向。
    
    **长按识别二维码查看原文**
    
    https://lemire.me/blog/2023/04/07/programming-language-popularity-by-github-pull-requests/
    

- Vue Amsterdam 2023 的七位人士分享了他们的 **▶️ Vue.js 入门技巧**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=RUdKQKRBkhk
    

- ▶️ **与一些大佬聊聊 Node.js 的现状**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=Yl5mVte-wdw
    

- **Node v18.16.0 (LTS) 发布**，支持将 JavaScript 代码编译为单个可执行应用程序。Node 19 的 Ada URL 解析器也出现了。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v18.16.0
    

- 一份引人注目的 **React 可视化介绍**，介绍了其基本概念。
    
    **长按识别二维码查看原文**
    
    https://react.gg/visualized
    

**版本发布：**

- **Node.js v19.9 (Current)**

- **Puppeteer v19.9**

- **pnpm v8.2** – 高效的 npm 替代方案。

- **Redwood v4.5** – 流行的应用程序框架。

- **Storybook v7.0** – 这次发布了官方版本。

## 📒 教程与趣事

**Ranger：使用范围语法来操作任何东西？** — `const numbers = 1[[...8]]`，有人用这个炫技来简化写法，但我不确定大多数团队会接受这个。不过你可能会发现**实现细节**也很有趣。希望这类实验能够持续下去。

**长按识别二维码查看原文**

https://dev.to/jonrandy/ranger-js-range-syntax-for-anything-4djc

Jon Randy

**尝试 Node 内置的测试运行器** — 到 2022 年，Node 拥有了一个实验性的内置测试运行器（`node:test`）。它**将在即将发布的 Node v20 中变得稳定**，因此现在是查看它是如何工作以及与您可能已经使用的其他解决方案相比如何的好时机。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/trying-node-test-runner/

Gleb Bahmutov

**▶  正确合并 JavaScript 对象的方式** — 而且还只需要一分钟。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=TmhvqvjK5nM

Jack Herrington

**使用 Vue 3 Composition API 时应该选择什么？Ref 与 Reactive 的区别**

**长按识别二维码查看原文**

https://mokkapps.de/blog/ref-vs-reactive-what-to-choose-using-vue-3-composition-api/

Michael Hoffmann

**如何使用 Node.js 将文件流式上传到 S3 对象存储**

**长按识别二维码查看原文**

https://austingil.com/upload-to-s3/

Austin Gil

**如何在对项目一无所知的情况下贡献代码**

**长按识别二维码查看原文**

https://grifel.dev/how-to-contribute-without-knowledge

Michal Warda

## 🛠 代码与工具

**Reveal.js v4.5：HTML 演示文稿框架** — 最新版 **v4.5** 刚刚发布，本次更新增加了跳转到指定幻灯片、几个新的主题，以及支持实时重新加载子文件夹中的文件。

**长按识别二维码查看原文**

https://revealjs.com/

Hakim El Hattab

**List.js：为表格和列表添加搜索、排序、过滤功能** — 这是一个方便的库，可以为表格、列表或其他 HTML 元素添加搜索、排序、过滤和灵活性。想看看实际例子？**可以看看这里**， **还有这里的例子**。

**长按识别二维码查看原文**

https://listjs.com/

Jonny Strömberg

**Queue：可调整并发性的异步函数队列** — 这个类导出了大多数 Array API，并可以用于异步函数队列，具有可调整并发性。

**长按识别二维码查看原文**

https://github.com/jessetane/queue

Jesse Tane

**yet-another-react-lightbox：实现灯箱组件的库** — 这个库可以在几分钟内为您的项目添加灯箱组件。您可以在 **这里查看几个示例**，还有一个 **可调整设置的 playground**。**仓库地址**

**长按识别二维码查看原文**

https://yet-another-react-lightbox.com/

Igor Danchenko

**Sandpack v2.6：用于创建实时代码编辑体验的组件工具包** — 由 CodeSandbox 团队开发的组件工具包，用于创建实时代码编辑体验。**仓库地址**

**长按识别二维码查看原文**

https://sandpack.codesandbox.io/

CodeSandbox

**TS Writer：用于在运行时生成 TypeScript 代码的模板字符串模板引擎** — 这是一个相当小众的库，用于在 TypeScript 中在运行时生成代码的情况。

**长按识别二维码查看原文**

https://tinylibs.js.org/packages/ts-writer/

tinylibs

- **Minimatch v9.0**
    
    ↳ 全局匹配器库。
    
    `minimatch("bar.foo", "*.foo")`
    

- **hls.js v1.4**
    
    ↳ 在支持 MSE 的浏览器中播放 HLS。
    

- **Partytown v0.8**
    
    ↳ 从主线程上重新定位第三方脚本。
    

- **Plasmo v0.68**
    
    ↳ _“这就像是用于浏览器扩展的 Next.js”_
    

- **Obsidian v8.0** – GraphQL，为 Deno 构建。

- **MUI X v6.1** – React 组件套件。

- **TestCafe v2.5** – 自动化端到端 Web 测试。

- **Maquette v3.6** – 轻量级虚拟 DOM 库。

- **Venom v5.0** – WhatsApp 机器人库。

## 🙋🏻‍♀️