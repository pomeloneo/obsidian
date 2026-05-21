# JavaScript 中文周刊 #115 - Deno Cron 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525391&idx=1&sn=13dc211ff7cd63439cb8951c54838c30&chksm=e9212fedde56a6fb835fa810f383709dce1c181010aacebe6398596ab6da8dcc9d2db0bbfde4\#rd  
> 抓取时间: 2026/2/2 23:51:33

---

> 本期看点：Deno 添加了一个 cron 风格的特性，可以使用 `Deno.cron` 在预定义的时间表上运行代码。Deno Cron 将会在长时间运行的程序中局部地工作（在 `Deno.cron` 后面添加 `--unstable`），但在 **Deno Deploy** 上，它将会分析定义并按时运行代码，并且无需额外的工作。

> 编辑：Zhper、TimLi、Yucohny

## 🔥 本周热门

**使用 Web Component 消除 JavaScript 框架锁定？** —— 你能否构建一个每个组件都使用不同框架编写的应用程序？答案是肯定的。Web Component 并不新颖但目前却 **炙手可热**，Jake 演示了一个有趣的例子。他解释道：**“假设你正在编写一个 Vue 的应用程序，但你确实需要使用一个只能够作为 React 组件使用的库，你可以将该库包装为一个 Web Component，然后在 Vue 应用程序中使用它……”**

**长按识别二维码查看原文**

https://jakelazaroff.com/words/web-components-eliminate-javascript-framework-lock-in/

Jake Lazaroff

**Deno Cron 发布** —— Deno 添加了一个 cron 风格的特性，可以使用 `Deno.cron` 在预定义的时间表上运行代码。Deno Cron 将会在长时间运行的程序中局部地工作（在 `Deno.cron` 后面添加 `--unstable`），但在 **Deno Deploy** 上，它将会分析定义并按时运行代码，并且无需额外的工作。

**长按识别二维码查看原文**

https://deno.com/blog/cron

Zinkovsky 与 Jiang（Deno）

**Biome 格式化工具赢得了“Prettier 挑战”** —— 两周前，Prettier 的创建者为一个基于 Rust 的代码格式化工具 **提供了 $10k 的赏金**，条件是能够通过 Prettier 测试套件中超过 95% 的测试。从 **Rome 衍生的** 工具链 **Biome**，已经获得了该奖项，并且奖金因 **许多贡献者** 的支持而增加。

**长按识别二维码查看原文**

https://biomejs.dev/blog/biome-wins-prettier-challenge/

Biome

**🤔** **一篇来自 Prettier POV 的帖子** 解释了为什么 @vjeux 愿意提供赏金：他认为“竞争的缺乏”阻碍了 Prettier 的发展。

**长按识别二维码查看原文**

https://prettier.io/blog/2023/11/27/20k-bounty-was-claimed

**快讯：**

- 📺 Vue.js 的创建者 Evan You 对 **VueConf Toronto** 的参与者 **展示了关于 Vue 和 Vite 状态的一次更新**（48 分钟）。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Hz_zCR28oKE

- 🎙️ **Off The Main Thread** 是一个新的播客节目，由 Jake Archibald 和 Surma（以前都是 Google / **HTTP 203** 的成员）主持。

**长按识别二维码查看原文**

https://offthemainthread.tech/

- 🎂 这和 JavaScript 没有关系，不过你们中的一些人可能会用到它，**Notepad++ 已经有 20 岁了**，它是一个流行的开源代码编辑器，也是 Windows 记事本的替代品。

**长按识别二维码查看原文**

https://notepad-plus-plus.org/news/v86-20thyearanniversary/

- **🙋 State of JavaScript 2023 调查** 目前仍然开放参与。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-js/2023

## 📒 教程与趣事

▶ **2023 年你（可能）错过的 10 个 JavaScript 改变** —— 我们已经涵盖了其中的大部分，但这仍然是一个有益的复习，只需六分钟内，就能复习到像 **toSorted()**、iOS Web Push、Next.js 更新、Angular 17 和 **Bun** 的快速发展。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ANCm3oG7htM

Fireship on YouTube

Fireship 是这类快速总结的好频道。如果你想了解更多 **你需要知道的 100+ 个 JavaScript 的概念**，Fireship 也会是一个有趣频道。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=lkIFF4maKMU

**使用 Playwright 工具跟踪前端 JavaScript 异常** —— Playwright 通常用于测试前端应用，确保它们的渲染和行为正确，但如果你想确保底层 JavaScript 也按预期工作，Stefan 有一些建议。

**长按识别二维码查看原文**

https://www.checklyhq.com/blog/track-frontend-javascript-exceptions-with-playwright/

Stefan Judis

**深入了解 CheerpJ v3.0：用于浏览器的 WASM JVM** —— 关注于一个有趣的基于 WebAssembly 的 Java 虚拟机，它在浏览器中运行客户端，需要的话也可以打开双向 Java-JavaScript 进行交互操作。注意他是商业性的，但可以免费用于个人项目和评估。

**长按识别二维码查看原文**

https://labs.leaningtech.com/blog/cheerpj-3-deep-dive

Pignotti、Bates 和 De Rossi

**从 React 开发人员的角度来看 svelte**

**长按识别二维码查看原文**

https://shamun.dev/posts/svelte

Ido Shamun

## 🛠 代码与工具

**FullCalendar：JavaScript 日历控件** —— 如果希望自己的应用程序拥有类似 Google 日历风格体验，则它非常值得考虑。适配 React、Vue 和 Angular。基础版本采用 MIT 许可证授权，此外还提供具备额外功能的商业版。

**长按识别二维码查看原文**

https://fullcalendar.io/

Adam Shaw

**Syntax.js：代码语法高亮库** —— 在这个领域有许多长期存在的选项，比如 **Prism** 和 **highlight.js**，但看到一种新的轻量级的方式很有意思。

**长按识别二维码查看原文**

https://github.com/williamtroup/Syntax.js

William Troup

**ai2html：将 Adobe Illustrator 文件转换成 HTML** —— 我们注意到《金融时报》正在使用这个工具来分享他们设计的图表，效果非常好。这是个并不新但是长期在维护的项目，并且有 **很多示例**。

**长按识别二维码查看原文**

http://ai2html.org/

The New York Times Company

**aws-lite：一个新的 Node.js 驱动 AWS API 客户端** —— AWS 在其 API 和工具方面做得很好，但有时候他们的方法显得有些笨重。`aws-lite` 提供了一个更简单、更快速的选择。“你可以把它看作是 AWS JavaScript SDK 的社区驱动替代品。”

**长按识别二维码查看原文**

https://aws-lite.org/

Begin

**版本发布：**

- **Passport v0.7** – Express 基础应用程序中流行的身份验证中间件。

- **eta (η) v3.2** – 适用于 Node、Deno 和浏览器的嵌入式 JS 模板引擎。

- **Fable v4.6** – F# 到 JavaScript 的转译器。

- **Neutralinojs v4.15.0** – 跨平台桌面应用程序框架——使用本地可用浏览器引擎比 Electron 更轻量级。

- **jest-image-snapshot v6.3** – Jest 图像比对工具。

- **Mongoose v8.0** – MongoDB 的 ODM 框架。

- **edit-in-place v1.9** – Angular 应用的即时编辑库。

- **Jotai v2.6** – React 的简单、灵活的状态管理器。

- **sql.js v1.9** – 编译成 JavaScript 的 SQLite 3.44 版本。

- **React Share v5.0** – 社交媒体分享按钮。

- **np v9.0** – 更好的 `npm publish` 工具。

- **pnpm v8.11** – 快速、节省磁盘空间的包管理器。

## 🙋🏻‍♀️