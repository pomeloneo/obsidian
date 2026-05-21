# JavaScript 中文周刊 #101 - 将 Sharp 引入 WebAssembly 和 WebContainers

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523274&idx=1&sn=f5f33845127a06c7a5aca442cadf08dd&chksm=e921d028de56593e27f77312c543d5d413119ca417035d0d4febc4961fb04332bc17a18e10e0\#rd  
> 抓取时间: 2026/2/2 23:51:49

---

> 本期看点：本期有一篇文章介绍了如何将流行的 Node.js 图像处理模块 Sharp 移植到浏览器中，欢迎查看本期周刊了解更多关于 Sharp 的信息！

> 编辑：Yucohny、Jojo

## 🔥 本周热门

**将包现代化为 ESM 的经历** —— 这是一篇了不起的文章！Mark 因其在 React、Redux 等领域的工作而闻名，他详细介绍了将 Redux 包迁移到 ESM 时所经历的痛苦经历和深刻教训。

**长按识别二维码查看原文**

https://blog.isquaredsoftware.com/2023/08/esm-modernization-lessons/

Mark ‘acemarke’ Erikson

**⚡️ 快讯：**

- Rich Harris 发布 **推文** 表示：“Svelte 5 将会是一次激动人心的更新！”

**长按识别二维码查看原文**

https://twitter.com/Rich_Harris/status/1688581184018583558

- 谷歌推出了正在开发的 **新 IDE 的一瞥**，其名为 **Project IDX**。🐦 **Addy Osmani 表示**，它虽然以 VS Code 为基础，但具有强大的 JavaScript 框架支持，模拟器以及许多顶级的“AI 智能”。

**长按识别二维码查看原文**

https://developers.googleblog.com/2023/08/introducing-project-idx-experiment-to-improve-full-stack-multiplatform-app-development.html

- JavaScript 中引入 **可观察对象（observables）的提案** 正在重新启动，虽然处于早期阶段。如果你有任何意见，可以提交 issue~

**长按识别二维码查看原文**

https://github.com/domfarolino/observable

- 通过 一**篇包含几乎每个 HTML 元素的博文** 享受前端历史的有趣回顾（除了 `applet` ）。

**长按识别二维码查看原文**

https://www.patrickweaver.net/blog/a-blog-post-with-every-html-element/

- **Nim v2.0 已发布**。Nim 是一种受 C++ 和 Python 启发的静态类型系统语言，支持编译为 JavaScript。点击这里查看更多信息：支持的功能。

**长按识别二维码查看原文**

https://nim-lang.org/blog/2023/08/01/nim-v20-released.html

## 📒 教程与趣事

**将 Sharp 引入 WebAssembly 和 WebContainers** —— 这篇文章介绍了如何将流行的 Node.js 图像处理模块 Sharp 移植到浏览器中。点击 **这里** 了解更多关于 Sharp 的信息。

**长按识别二维码查看原文**

https://blog.stackblitz.com/posts/bringing-sharp-to-wasm-and-webcontainers/

Ingvar Stepanyan

▶ **HTMX：一种“改变游戏规则”的替代方案，值得学习吗？** —— 这是杰克典型的短视频之一，时长只有 14 分钟。他认为学习 **htmx** 可以为你的工具箱增加更多选择。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=DuGyH5RvfbY

Jack Herrington

**Node.js 的“配置地狱”问题** —— Andy 思考了为什么一个 Next.js 项目会有超过 30 个配置文件，并提出了我们可以采取的方法来避免这种情况（毫不意外，涉及到使用 **Deno**，我喜欢这种大胆的尝试）。

**长按识别二维码查看原文**

https://deno.com/blog/node-config-hell

Andy Jiang（Deno）

**使用文档画中画 API 创建屏幕+摄像头录制器** —— 这比我预期的要强大。你基本上可以使用浏览器的 API 来录制屏幕录像。至少在 Chrome 上是可以的。

**长按识别二维码查看原文**

https://www.getcontrast.io/learn/using-document-picture-in-picture-and-insertable-streams-apis-to-record-your-screen-and-camera

Sébastien Jalliffier Verne

**▶ Turbopack vs Webpack** —— 在参与开发这两个打包工具的过程中，Tobias Koppers 提出了一些有趣的观点，解释了为什么 **Turbopack** 是必要的。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Zwd_8Jy7b-c

Tobias Koppers 与 Jack Herrington

**使用 UniFFI 自动生成 Rust-JS 绑定**

**长按识别二维码查看原文**

https://hacks.mozilla.org/2023/08/autogenerating-rust-js-bindings-with-uniffi/

Ben Dean-Kawamura（Mozilla）

**将博客从 Gatsby 迁移到 Astro**

**长按识别二维码查看原文**

https://sapegin.me/blog/gatsby-to-astro/

Artem Sapegin

## 🛠 代码与工具

**Fuite v3.0：帮助查找 web 应用程序内存泄漏** —— 这是一款命令行工具，你可以将其指向任何 URL 以分析内存泄漏。**这里是介绍的博文**，还有 **视频教程** 可供参考。

**长按识别二维码查看原文**

https://github.com/nolanlawson/fuite

Nolan Lawson

**Luxon v3.4：日期和时间操作库** —— Luxon 与 Moment.js 类似，但是 Luxon 具有不可变对象、从 1 开始的月份、使用 `Intl` 强化的本地化（因此不需要区域设置或时区文件）等特性。

**长按识别二维码查看原文**

https://github.com/moment/luxon

Moment.js

**Typograms：更优雅地渲染 ASCII 图表的一种方法** —— 这是一个有趣的项目，你可以在特殊的 `script` 标签内用纯文本 ASCII 绘制图表，然后这些图表会被呈现为更美观的版本。如果 **Mermaid** 过于繁重，这是一个有趣的替代方案**。**

**长按识别二维码查看原文**

https://google.github.io/typograms/

Sam Goto / Google

💡 说到 **Mermaid**，其 **最新发布** 开始支持 **Sankey 图**。

**长按识别二维码查看原文**

https://github.com/mermaid-js/mermaid/releases/tag/v10.3.0

**d3-graphviz v5.1：Graphviz DOT 渲染和动画过渡** —— 使用 WebAssembly 版本的 Graphviz（一款流行的图形可视化工具）端口从 DOT 定义的图形中渲染 SVG 图像。

**长按识别二维码查看原文**

https://github.com/magjac/d3-graphviz

Magnus Jacobsson

**🔊 Meyda：音频特征提取库** —— 支持离线特征提取以及使用 Web Audio API 进行实时特征提取，你可以在其主页上查看演示。

**长按识别二维码查看原文**

https://meyda.js.org/

Rawlinson, Segal, Fiala, Wray, et al.

**🎉 版本发布：**

- **TypeScript v5.2 RC** —— **TypeScript v5.2 即将发布最终版本**。**使用** `**using**` **进行显式资源管理** 是最重要的特性，但也包括许多其他内容。

- **esbuild v0.19.0** —— 高性能打包工具现在可以导入包含通配符的路径，并且 **支持高级 CSS 的** `**@import**` **规则**。请注意，此版本包含了不兼容向后的变更。

- **Astro v2.10** —— 还有 **Astro 3 的首个测试版**。

- **React Virtuoso v4.5** —— 强大的虚拟列表组件。

- **Perspective v2.4** —— 快速、流式的实时数据可视化。

- **express-rate-limit v6.9** —— Express 应用的基本速率限制。

- **PLV8 v3.2** —— 在 PostgreSQL 中使用 JavaScript 作为过程语言。

- **Puppeteer v21.0** —— 在 Node.js 中进行无界面 Chrome 自动化。

## 🙋🏻‍♀️