# JavaScript 中文周刊 #164 - Component Party 支持 Svelte 5 和 Angular 17

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537480&idx=1&sn=0ba71e2a2508c8603e33b1db6d6fb1d0&chksm=e92118aade5691bcc6b4e4d6af05b84917d67e23bca41edb6e349e6bd4b3039c8cce6e975df6\#rd  
> 抓取时间: 2026/2/2 23:50:33

---

> 本期看点：Component Party 项目新增对 Svelte 5 和 Angular 17 的支持，npm 创始人推出新一代包管理器 vlt 及无服务器注册表，TypeScript 5.7 RC 版发布带来多项新特性，VS Code 引入 Copilot Edits 功能支持多文件编辑，Storybook 8.4 发布并支持 Svelte 5。

> 编辑：TimLi

🔥 本周热点

**Component Party：UI 框架的罗塞塔石碑** —— 这是一个长期维护的项目，通过简单的代码片段对比多个不同的框架（如 React、Vue、Svelte、Angular、Qwik、Solid.js 等）完成各种任务的方式。现已支持 Svelte 5 和 Angular 17/Renaissance。

**长按识别二维码查看原文**

https://component-party.dev/

Mathieu Schimmerling

**未来我们还会关心框架吗？** —— Paul 思考了一个问题：随着 LLM 和智能代理在软件开发中的应用越来越广泛，是否会减少对新框架和额外开发者抽象层的需求。

**长按识别二维码查看原文**

https://paul.kinlan.me/will-we-care-about-frameworks-in-the-future/

Paul Kinlan

`**vlt**` **包管理器和无服务器注册表** —— 一个经验丰富的团队（包括 npm 创始人 Isaac Schlueter）推出了 Vlt，旨在”构建 JavaScript 包管理的未来”。首批成果包括可替代 `npm` 的 `vlt` 客户端，以及一个可以自托管用于分发包的无服务器包注册表。

**长按识别二维码查看原文**

https://blog.vlt.sh/blog/introducing-vlt-and-vsr

Clarke、Adorno、Schlueter 和 Karrys

💡 Sarah Gooding 在这里分享了更多关于 Vlt 的背景故事。

**长按识别二维码查看原文**

https://socket.dev/blog/vlt-debuts-new-javascript-package-manager-and-serverless-registry

**TypeScript v5.7 候选版本发布** —— 这个广受欢迎的 JS 超集新增了对 ES2024 目标的支持，可以在变量未初始化时报错，添加了相对路径重写功能，并可以使用 Node 的编译缓存来减少解析工作。最终版本预计将在一两周内发布。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-7-rc/

Microsoft

**快讯：**

- 🤖 Microsoft 在 VS Code 中引入了 Copilot Edits —— 它提供了在项目中同时处理多个文件的方式。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2024/11/12/introducing-copilot-edits
    

- Jawsm 是一个早期的实验性 JavaScript 到 WebAssembly 编译器（类似于 Porffor），但它的目标是直接使用最先进的 WASM 特性，如 WasmGC 和异常处理。
    
    **长按识别二维码查看原文**
    
    https://github.com/drogus/jawsm
    

- 💜 CSS 现在有了官方 logo！
    
    **长按识别二维码查看原文**
    
    https://nerdy.dev/a-community-css-logo
    

📒 教程与趣事

**JavaScript Import Attributes（ES2025）详解** —— Import Attributes（现已进入 TC39 第 4 阶段，并且已经得到支持）为导入模块时提供有用的元数据添加了一种方式。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/import-attributes-in-javascript

Trevor I. Lasn

💡 Trevor 最近发表了一系列精彩的文章。他还深入探讨了 `Promise.try` 和 JavaScript 位移运算符的工作原理。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/promise-try-in-javascript

**使用 OGL 创建 ASCII 着色器** —— 一个非常酷的效果演示，通过这个教程可以学习如何使用轻量级 WebGL 库 OGL 开始着色器编程。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/11/13/creating-an-ascii-shader-using-ogl/

Andrico Karoulla

**BBC 导航栏组件为什么会在不同外接显示器上出现问题** —— 探讨了一个与外接显示器定位相关的有趣 bug。教训是”浏览器在多显示器设置中表示屏幕坐标的方式存在互操作性问题”。

**长按识别二维码查看原文**

https://www.joshtumath.uk/posts/2024-11-08-how-a-bbc-navigation-bar-component-broke-depending-on-which-external-monitor-it-was-on/

Josh Tumath

**2024 年如何为生产环境配置 Next.js 15** —— 分享作者在将 Next.js 应用程序扩展到每月超过 10 万活跃用户和数百万访问量的经验。

**长按识别二维码查看原文**

https://www.reactsquad.io/blog/how-to-set-up-next-js-15-for-production

Jan Hesters (ReactSquad)

**▶ 从 Next.js 到 htmx：一个真实案例** —— 一个通过 50 分钟屏幕录像讲解的有趣案例研究：“用 htmx 驱动的 HTML 元素替换我的组件并不是一件容易的事，但这值得投入时间。”

**长按识别二维码查看原文**

https://htmx.org/essays/a-real-world-nextjs-to-htmx-port/

Pouria Ezzati

**📄 如何优化 Vue 应用程序性能** Jakub Andrzejewski

**长按识别二维码查看原文**

https://www.debugbear.com/blog/optimize-vue-performance

**📄 如何使用 Drizzle ORM 和 Deno 构建数据库应用程序** Andy Jiang

**长按识别二维码查看原文**

https://deno.com/blog/build-database-app-drizzle

**📄 你应该使用的基本** `**tsconfig.json**` **选项** Duy NG

**长按识别二维码查看原文**

https://tduyng.com/blog/tsconfig-options-you-should-use/

**📺 使用 Svelte 5 构建富文本编辑器** Michael Aufreiter

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=T2RMYj_1g9E

🛠 代码与工具

**Lexical v0.20：Meta 开发的易扩展文本编辑器框架** —— 这是 Meta 开发的一个文本编辑器框架，注重可扩展性、可访问性和跨平台支持（甚至还有用于 iOS 的 Swift 版本）。你可以在在线演示场中试用。它对 React 的支持是一流的，但也可以适配到其他地方（比如 svelte-lexical）。

**长按识别二维码查看原文**

https://lexical.dev/

Meta / Facebook

**Storybook v8.4 发布** —— 这是这个强大的前端组件工作坊的一个小版本更新，但却是”我们功能最丰富的小版本之一”，带来了一键组件测试、**Svelte 5 支持**和 React Native Storybook 8。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-8-4/

Michael Shilman

**🗓️ Schedule-X v2.5：Material Design 日历和日期选择器** —— 提供 React/Preact、Vue、Svelte、Angular 或纯 JS 组件形式。开源但有带额外功能的高级版本。GitHub 仓库。

**长按识别二维码查看原文**

https://schedule-x.dev/

Tom Österlund

**🎵 music-metadata：流式和基于文件的音乐元数据解析器** —— 支持 MP3、FLAC、Ogg、WAV、WMA、AAC 和 AIFF 等格式，这个库可以提取 ID3v1 和 iTunes 标签等元数据供你处理。是的，它在浏览器中也能工作。

**长按识别二维码查看原文**

https://github.com/borewit/music-metadata

Borewit

**🎵 micromark v4.0.1：小巧的兼容 Markdown 解析器** —— 100% 兼容 CommonMark 标准，支持扩展（如 GitHub Flavored Markdown），并有完整的测试覆盖。

**长按识别二维码查看原文**

https://github.com/micromark/micromark

Titus Wormer

**jsep v1.4：JavaScript 表达式解析器** —— “把 jsep 想象成一个用于解析 Excel 单元格中那种表达式的工具。”

**长按识别二维码查看原文**

https://ericsmekens.github.io/jsep/

Stephen Oney

**版本发布：**

- **Expo SDK v52** —— 用于构建现代 React Native 应用程序的工具集，现在支持 React Native 0.76 和新架构。

- **Node.js v18.20.5 (LTS)** —— 大量依赖更新，并且 import attributes 和 JSON 模块现在已标记为稳定。

- 虽然没有正式公告，但看起来 Ember v6.0 即将发布。

- **Node.js v23.2.0 (Current)**、**pnpm v9.13**、**Parcel v2.13.0**

- 📊 **visx v3.12** —— Airbnb 的 React 可视化组件套件现在包含了桑基图组件。

- 🖼️ **Fabric.js v6.5** —— 通过对象模型和操作使 HTML5 Canvas 元素更具交互性。GitHub 仓库。

- **DOMPurify v3.2** —— 快速、容错的 HTML 和 SVG XSS 净化器。演示。

- **MikroORM v6.4** —— 流行的 Node.js TypeScript ORM。

- **Marked v15.0** —— 快速的 Markdown 编译器/解析器。