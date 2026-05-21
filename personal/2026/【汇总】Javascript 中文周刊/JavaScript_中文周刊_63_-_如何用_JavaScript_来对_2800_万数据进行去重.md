# JavaScript 中文周刊 #63 - 如何用 JavaScript 来对 2800 万数据进行去重?

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512182&idx=1&sn=38f26e4f13edaec660f31d06398620de&chksm=e921fb94de567282e75adde433a364ed2d42a12a56dac512907e80899c677767b077159a4ffd\#rd  
> 抓取时间: 2026/2/2 23:52:40

---

> 本期看点：上周，Rome v10 发布、Gatsby v5.0 发布，号称是迄今为止最快的 Gatsby、Vercel Netlify 的 Jamstack 2022 社区调查的结果公布。……更多热门文章资讯请点击本期周刊查看！

> 编辑：Yucohny、Levi、TimLi777

## 🔥 本周热门

**Rome v10：由 Rust 驱动的 JS Linting 与格式化工具** — 由 **Babel 的作者** 创建的项目自然会引起大家的兴趣。Rome 的理想是将大家需要的所有前端开发工具统一，而格式化和 linting 是他们开始统一的第一步。

**长按识别二维码查看原文**

https://rome.tools/blog/2022/11/08/rome-10/

The Rome Team

**编者注**：尽管 Rome 还很年轻，但它已经有一些令人信服的观点，包括 **详细报错诊断**，它不仅可以告诉你你的代码有错误，还会提供更多的上下文来解释这个错误的原因，很高兴看到这种工具进一步发展。

**为什么需要生成器函数？** — 或许你在很长一段时间内不觉得需要 **generators**， 所以你可能想知道，它们有什么用处？虽然它们可能不是必需的，但它们确实具有实用性，并且可以改变你处理某些问题的方式。

**长按识别二维码查看原文**

https://jrsinclair.com/articles/2022/why-would-anyone-need-javascript-generator-functions/

James Sinclair

**Gatsby v5.0：迄今为止最快的 Gatsby** — 高性能的、基于 React 的框架。**Slice API** 主要用于加速整个站点的常见更新、部分 hydration（beta）、新的 `Script` 组件用来加载脚本、增量构建和部署。此版本遵循 Gatsby 作为 **“反应式站点生成器”** 的全新宣传。

**长按识别二维码查看原文**

https://www.gatsbyjs.com/blog/gatsby-5/

Josh Johnson (Gatsby Team)

**快讯：**

- 准备好使用 **GitHub Blocks** 来完善 README 吧！你可以将动态组件添加到您的 README 中以包含演示、实时统计信息 ，搜索功能，比较表等。
    
    **长按识别二维码查看原文**
    
    https://blocks.githubnext.com/
    

- 如果你被不断出现的新框架弄得不知所措，那可以关注一下本周刚结束的 Jamstack Conf ， 一群框架创建者讨论了这个现象，**并评论这是件好事**：
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/jamstack-panel-multiple-javascript-frameworks-are-a-good-thing/
    

- 来自 Vercel **Netlify** 的 Jamstack 2022 社区调查的 **结果** 已经发布。Serverless、React 和 Next.js 都非常受欢迎。
    
    **长按识别二维码查看原文**
    
    https://jamstack.org/survey/2022/
    

- 查看与 JavaScript 相关的 **IPFS** 状态。**IPFS** 是一个大型分布式点对点存储系统和协议。
    
    **长按识别二维码查看原文**
    
    https://blog.ipfs.tech/state-of-ipfs-in-js/
    

## 📒 教程与趣事

**新的 JavaScript 时间 API 提案 — Temporal（已进入 stage 3）** — JavaScript 的原生时间 API 一直很难用，以至于开源社区有很多时间库来处理时间。(比如 **Moment.js**) ，现在出现了一个 `Temporal` API 提案，它包含了命名更直观的方法以及更强大的功能。目前已经进入 `stage 3` **proposal** 。

**长按识别二维码查看原文**

https://vladmihet.hashnode.dev/temporal-api-javascript-dates-but-better

Vlad Mihet

**使用 Three.js 来创建蓬松的树** — 如何使用 Three.js 和 GLSL 来制作一颗蓬松的树。

**长按识别二维码查看原文**

https://douges.dev/blog/threejs-trees-1

Michael Dougall

**Sourcegraph 公司讲述了为什么他们选择从 Monaco 编辑器切换到 CodeMirror** — 优点包括打包体积减少 43%，样式主题可以随着主站变化，模块化，性能更好。

**长按识别二维码查看原文**

https://about.sourcegraph.com/blog/migrating-monaco-codemirror

Kling and Dorfman

**给 React 的一封情书 (来自  Phoenix 创建人)** 来自Fly.io的开发者描述了 React 的优点以及给他自己写 **Phoenix 框架（Elixir 语言写的 web 框架）带来的启发**，同时对 React 表示了感谢。

**长按识别二维码查看原文**

https://fly.io/blog/love-letter-react/

Chris McCord (Fly.io)

**如何用 JavaScript 来对 2800 万数据进行去重?** — 这是 Stack Overflow 上一个很有趣的问题。这个任务其实并不适合 JavaScript 以及 任何 JS runtime 来做，但是办法总比困难多。

**长按识别二维码查看原文**

https://stackoverflow.com/questions/74329830/deduping-28-million-strings-using-javascript

Stack Overflow

**▶️ 一个 Next.js 13 的演示教程，里面讲了一个 use 导致的无限循环 bug** — Bug 解决方案在视频 8:40 处。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=zwQs4wXr9Bg

Jack Herrington

**在 Next 或者任何 SSR 框架中使用 Web Components**

**长按识别二维码查看原文**

https://css-tricks.com/using-web-components-with-next-or-any-ssr-framework/

Adam Rackis

**探索 Bun 的内置 React 模板**

**长按识别二维码查看原文**

https://medium.com/deno-the-complete-reference/react-boilerplate-with-bun-36808ee0bfaf

Mayank Choubey

**在 Jest 中模拟 Class 的两种方式**

**长按识别二维码查看原文**

https://meticulous.ai/blog/mocking-a-javascript-class-with-jest-two-ways-to-make-it-easier/

Geshan Manandhar

## 🛠 代码与工具

**Trix v2.0：一款所见即所得的富文本编辑器** — 这款富文本编辑器由 37signals 团队开发（其开发了著名框架 Ruby on Rails）。这款编辑器被用在 Basecamp 上，因此它的完成度毋庸置疑。**GitHub 仓库**

**长按识别二维码查看原文**

https://trix-editor.org/

Basecamp

**Riot.js v7.1：一个简单又优雅的基于组件的 UI 库** — 一个可供你选择的有趣的 UI 库，它的设计理念是用纯 web API 来完成你的 UI。**GitHub  仓库**

**长按识别二维码查看原文**

https://riot.js.org/

Riot.js

**React Calendar v4.0：React 应用程序的“终极”日历** — 一个流行、简洁的 React 日历组件，主要专注于让用户选择日期。想用 v4.0 的话 React 版本至少要 16.8。**GitHub  仓库**。

**长按识别二维码查看原文**

https://projects.wojtekmaj.pl/react-calendar/

Wojciech Maj

**safe-json-value v1.9：保证 JSON 序列化永不失败** — 防止 `JSON.serialize()` 抛出异常、更改类型或以其他方式意外转换值，因为有时您需要这种保障机制。

**长按识别二维码查看原文**

https://github.com/ehmicky/safe-json-value

ehmicky

**Rockpack v3.0：另一种 React 应用构造器** — 就像 `Create React App` 打包的目标是缩短项目设置时间，但是 Rockpack 对项目的未来发展有一些不同的看法，并包含许多想法，例如服务器端渲染和 **now**、linting。

**长按识别二维码查看原文**

https://github.com/AlexSergey/rockpack

Alex Sergey

**版本发布：**

- **Parcel v2.8** – 零配置构建工具。这是一个相当大的版本发布，具有全新的捆绑算法和改进的自动代码拆分。

- **pnpm v7.15** – 快速、节省空间的包管理器。

- **WaveSurfer.js v6.4** – 用于 Web Audio 的可示化波形图。示例

- **Kosko v3.0** – 用 JavaScript 管理 Kubernetes manifests。

- **Marked v4.2.2** – 以性能为中心的 Markdown 解析器和编译器。示例

- **React Bootstrap v2.6** – 用于 React 的 Bootstrap 5 组件。

- **React Tooltip v4.5** – 一个惊艳的提示组件。示例

- **Strapi v4.5** – 流行的基于 Node 的无头 CMS。

## 🙋🏻‍♀️