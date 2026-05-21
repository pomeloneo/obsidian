# JavaScript 中文周刊 #15 - JavaScript 引擎如何提升其运行时的性能呢？

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496478&idx=1&sn=3fb4d3a1778b50e6ef86de46ea6e1c5d&chksm=e921b8fcde5631eab6fb01b77733e1d2cb61ff9cbe46480e78d232dfd1aff5ac0b60951bb19c#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496478&idx=1&sn=3fb4d3a1778b50e6ef86de46ea6e1c5d&chksm=e921b8fcde5631eab6fb01b77733e1d2cb61ff9cbe46480e78d232dfd1aff5ac0b60951bb19c#rd)  
> 抓取时间: 2026/2/2 23:53:41

---

> 本期看点：上周，有开发人员发现 **npm** 包中存在 **birthday** 这个子命令彩蛋。这样的做法无疑会造成开发者与使用者之间出现信任危机！

> 编辑：Black-Hole、liu-jin-yi、Yucohny

## 🔥 本周热门

**Remix: 一个基于 React 开源的 Web 应用框架** — Remix 是一个包含了前后端的 Web 应用框架，Remix 会在服务端 **并行** 加载数据，使得加载速度变的非常快。极大地消除了 Loading 状态。更多了解：

- **▶️ Kent C Dodd 录制的视频教程**。该视频讲解了 Remix 绝大部分的功能。
    
    **长按识别二维码查看原文**
    
    h
    

- **Remix 入门教程**。
    
    **长按识别二维码查看原文**
    
    https://flaviocopes.com/remix/
    

- **在线 demo 尝试**。
    
    **长按识别二维码查看原文**
    
    https://stackblitz.com/edit/node-qg1z8m
    

Remix Team

**Vercel 公司获得 D 轮融资 1.5 亿美元** — Vercel 打算把这些钱用于：支持开源项目、加快 Edge Function 进度、创建端对端开发平台、团队发展等。

**长按识别二维码查看原文**

https://vercel.com/blog/vercel-funding-series-d-and-valuation

Vercel

**Prettier v2.5 发布：增加了对 TypeScript v4.5 新语法和 MDX v2 注释语法的支持** — 例如: `import { type A } from "mod";` 和 `Import Assertions` 等。

**长按识别二维码查看原文**

https://prettier.io/blog/2021/11/25/2.5.0.html

Sosuke Suzuki

**快讯：**

- 上周，有开发人员发现 `npm` 在无任何声明的情况下向 npm 包中添加了 `birthday` 这个子命令。**经过分析这其实是 一个与生日有关的复活节彩蛋**。
    
    **长按识别二维码查看原文**
    
    https://github.com/npm/cli/issues/4091
    

**版本发布：**

**Chalk v5.0** – 设置 Node.js 中终端字体样式。

**ShareDB v2.2** – 基于操作转换（OT）实时后端数据库。

**Signature Pad v4.0** – 基于 Canvas 的平滑签名组件。

**node-qrcode v1.5** – 支持在 Node.js 和浏览器环境中生成二维码。

**ESLint v8.3.0** – 代码自动审查工具。

**Espree v9.1** – 兼容 Esprima 的 JavaScript 解析器。

**React Redux v8 Beta**

## 📖 教程与趣事

**自动化 JavaScript 意外回归 MacOS** — 一位资深的 MacOS 专家思考为什么在 MacOS 上使用 JavaScript 实现自动化功能，而不使用 AppleScript 和 Python。

**长按识别二维码查看原文**

https://scriptingosx.com/2021/11/the-unexpected-return-of-javascript-for-automation/

Armin Briegel

**Svelte 与 React 和 Vue 之间的区别？** — 本文介绍了 Svelte 和其他框架的区别，以及存在哪些优势，和使用不同框架编写代码的区别。

**长按识别二维码查看原文**

https://joshcollinsworth.com/blog/introducing-svelte-comparing-with-react-vue

Josh Collinsworth

**JavaScript 引擎如何提升其运行时的性能？** — 作者较为详细的介绍了 JavaScript 引擎是如何提升 JavaScript 解析和执行速度的，以及解释了这么做的原因。

**长按识别二维码查看原文**

https://blogg.bekk.no/how-javascript-engines-achieve-great-performance-fb0b36601557?gi=132060dac5b5

Robin Heggelund Hansen

**如何将 WebAssembly（由 Rust 创建）与 React 组件一起使用？** — 本文将会使用代码示例告诉你，将 Rust 集成到 React 中会有多么的容易。

**长按识别二维码查看原文**

https://www.joshfinnie.com/blog/using-webassembly-created-in-rust-for-fast-react-components/

Josh Finnie

**使用 React Hooks 的最佳实践。**

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/11/useful-react-hooks/

Ifeanyi Dike (Smashing Magazine)

**JavaScript 工具：Volta 与 nvm 的区别**

**长按识别二维码查看原文**

https://sirre.al/2021/02/12/volta-vs-nvm-for-managing-javascript-tooling/

Jon Surrell

**为什么使用 IndexedDB 很慢与相应的替代方案**

**长按识别二维码查看原文**

https://rxdb.info/slow-indexeddb.html

RxDB Documentation

## 🛠 代码与工具

**Polly v5.2: 录制、回放 以及保存 HTTP 交互** — 支持 Node.js 和浏览器，并且可以让你能够控制录制、重放和拦截测试中的 HTTP 请求。

**长按识别二维码查看原文**

https://github.com/Netflix/pollyjs

Netflix, Inc.

**Fiddle: 入门 Electron 最简单的方案** — 如果你想快速学习 Electron，并想快速模拟一些场景时，可以试一试 Fiddle。

**长按识别二维码查看原文**

https://github.com/electron/fiddle

Electron

**reading-time: 网页阅读时间估算** — 给它一些文本内容，它会估算并返回给你一个阅读完所需时间。

**长按识别二维码查看原文**

https://github.com/ngryman/reading-time

Nicolas Gryman

**file-type: 检测 Buffer、Uint8Array 和 ArrayBuffer 中的文件类型** — 例如，给它一个 PNG 的原始数据（例如 Uint8Array 类型），它会告诉你这是一个 PNG 文件。

**长按识别二维码查看原文**

https://github.com/sindresorhus/file-type

Sindre Sorhus

**PickBetterPack: 从 `package.json` 定义的依赖项中分析出相似的包** — 这个工具会分析你的 `package.json` 依赖，然后展示一个树状图，告诉你每一个依赖包有哪些其它相似的包。

**长按识别二维码查看原文**

https://pickbetterpack.com/

PickBetterPack

**use-prosemirror: 在 React 中更加容易地使用 ProseMirror 编辑器** — 只需要使用一个 React Hook 和一个组件，就可以完成在 React 中接入 ProseMirror。

**长按识别二维码查看原文**

https://github.com/dminkovsky/use-prosemirror

Dmitry Minkovsky

**Color v4: 一个颜色转换操作库** — 支持 rgb、rgba、hsl、hwb 等格式，和读取、修改等操作。

**长按识别二维码查看原文**

https://github.com/Qix-/color

Qix

**React Image Crop: 一个响应式图像裁剪工具**

**长按识别二维码查看原文**

https://github.com/DominicTobias/react-image-crop

Dominic Tobias

**Elementary Grid: 一个使用 JS +** _**Elementary**_ **实现动力音乐创作的工具** — 使用 Elementary Audio 和 React 制作的音调合成器。

**长按识别二维码查看原文**

https://teetow.github.io/elementary_grid/

Johan Althoff

## 🙋🏻‍♀️