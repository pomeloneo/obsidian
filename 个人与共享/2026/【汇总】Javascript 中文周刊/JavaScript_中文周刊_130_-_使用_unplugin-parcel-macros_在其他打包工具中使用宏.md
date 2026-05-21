# JavaScript 中文周刊 #130 - 使用 unplugin-parcel-macros 在其他打包工具中使用宏

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529588&idx=1&sn=c0269c0066d5e8fdae176f672b870083&chksm=e9213f96de56b6800112ca90f518e8d92e627bddfd6251f924bfa673e304b4866e50525eb06b\#rd  
> 抓取时间: 2026/2/2 23:51:15

---

> 本期看点：宏在 Parcel 中的实现（也包括 Bun）是在构建时运行的 JavaScript 函数，其结果被内联至 bundler 中取代原始调用。现在可以在 webpack、Vite、Rollup、esbuild 等中使用此功能。

> 编辑：Yucohny

## 🔥 本周热门

**使用 `unplugin-parcel-macros` 在其他打包工具中使用 Parcel 宏** —— **宏** 在 Parcel 中的实现（**也包括 Bun**），是在构建时运行的 JavaScript 函数，其结果被内联至 bundler 中取代原始调用。现在可以在 webpack、Vite、Rollup、esbuild 等中使用此功能。**这里有一个快速示例** 展示了这个功能有多么方便。

**长按识别二维码查看原文**

](https://github.com/devongovett/unplugin-parcel-macros

Devon Govett

𝕏 Devon 在 🐦 **这篇 Twitter/X 帖子中详细介绍了这个功能**。你也可以回顾一下 **Parcel v2.12.0 的发布** 来了解更多。

**长按识别二维码查看原文**

https://twitter.com/devongovett/status/1767939537907462211

**Speedometer v3.0：测量浏览器性能的最佳方式** —— Speedometer 于 2014 年发布，最新的 **v3.0 版本** 是首次采用了完全协作的方式，涉及每个主要的浏览器引擎（Blink、Gecko 与 WebKit）。你可以 **在这里自行运行测试**。

**长按识别二维码查看原文**

https://webkit.org/blog/15131/speedometer-3-0-the-best-way-yet-to-measure-browser-performance/

Apple、Google、Microsoft 与 Mozilla

**WinterJS v1.0：快速的 WinterCG 和 WASM 兼容的 JavaScript 运行时** —— WinterJS 最初将自己定位为由 Rust 和 SpiderMonkey 驱动的 Service Worker 服务器，但现在宣称自己是最快的 WinterCG 兼容 JavaScript web 服务器。他们 **未来计划** 完全在 WebAssembly 下运行 JITed JavaScript 工作负载。

**长按识别二维码查看原文**

https://wasmer.io/posts/winterjs-v1

Wasmer

**快讯：**

- 上周我们提到了 **JSR**，这是 Deno 的新 JavaScript 注册表尝试。如果你认为那篇文章过于复杂，那么可以看看新发布的 ▶️ **6 分钟视频介绍**，涵盖了主要动机和功能。

**长按识别二维码查看原文**

https://deno.com/blog/jsr_open_beta

- **Astro** 的开发团队推出了 **Astro DB**，这是一个专门为 Astro 设计的完全托管的 SQL 数据库。

**长按识别二维码查看原文**

https://astro.build/db/

- 📊 **Node vs LLRT/QuickJS 的基准测试**。

**长按识别二维码查看原文**

https://learnaws.io/blog/node-vs-llrt

- **f(x)** 是一个绝佳的基于终端的 JSON 查看器应用程序（使用 Go 编写，但可以与 JavaScript 函数集成），**其最新版本** 还支持 YAML。

**长按识别二维码查看原文**

https://github.com/antonmedv/fx/releases/tag/32.0.0

## 📒 教程与趣事

**比较 JavaScript 框架：模板篇** —— 对 React、Vue、Angular 和 Svelte 使用的模板语言进行了彻底比较。文章的分析十分有趣，看起来这将成为一个很棒的系列。

**长按识别二维码查看原文**

https://www.maartenhus.nl/blog/comparing-javascript-frameworks-part-1-templates/

Maarten Hus

**▶ 在 2024 年使用 TypeScript 设置 Express.js 应用程序** —— 这段长达一个小时的视频不是关于构建整个应用程序的，而是以清晰、易于跟随的方式设置和运行所有东西，包括各种现代 DX 便利功能。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Be7X6QJusJA

Anson the Developer

**使用泛型使 TypeScript 函数更具重用性** —— Matt 在这里提出了一个考虑的挑战，然后展示了如何通过使用类型参数而不是 `any` 来使函数更灵活、类型安全。

**长按识别二维码查看原文**

https://www.totaltypescript.com/make-your-functions-more-reusable-with-generics

Matt Pocock

**Git 中** `**HEAD**` **的工作原理**

**长按识别二维码查看原文**

https://jvns.ca/blog/2024/03/08/how-head-works-in-git/

Julia Evans

## 🛠 代码与工具

**Rolldown：一个由 Rust 驱动的 JavaScript 打包工具** —— 这是一个日益拥挤的市场中的一个新参与者，但他们 **在这里解释了为什么要构建它**——它旨在成为 **Vite** 中使用的未来打包工具的基础，而非 esbuild 和 Rollup。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://rolldown.rs/

Rolldown

**Playwright 测试生成器** —— **Playwright** 不仅是一个用于从 JavaScript 控制浏览器的库，还包括一个工具，用于从你自己的交互中生成测试和页面导航代码。点击录制，进行操作，代码就写好了。

**长按识别二维码查看原文**

https://playwright.dev/docs/codegen

Microsoft

**TinyBase v4.7：本地优先应用程序的反应式数据存储** —— 如果你想要在应用程序中管理状态时具有更多类似数据库的结构，那么这个值得一试。**演示** 很好地展示了它的功能。**v4.7** 添加了对 Turso 的 **LibSQL**（SQLite 的一个分支）的支持。

**长按识别二维码查看原文**

https://tinybase.org/

James Pearce 等人

**webtoon/PSD：零依赖 PSD 解析器，适用于浏览器和 Node** —— PSD 是 Photoshop 使用的格式，这个库可以让你深入研究每个图像层上的元数据和像素。

**长按识别二维码查看原文**

https://webtoon.github.io/psd/

webtoon inc

**版本发布：**

- **Biome v1.6** – 工具链部分支持 Astro、Svelte 和 Vue 文件。

- **D3.js v7.9** – 受欢迎的数据可视化库。几个月前他们还推出了 **一个很棒的新主页**，如果你有一段时间没看过的话。

- **React Native Skia v1.0** – 附带 ▶️ **一个发布视频**。

- **Cypress v13.7**

- **Angular v17.3**

- **Ember v5.7**

- **Knip v5.1** – 查找未使用的文件、依赖项和导出。

- **OverlayScrollbars v2.6** – JavaScript 自定义滚动条插件。

- **🗓 date-fns v3.4** – 现代 JavaScript 日期实用程序库。

- **Slonik v37.3** – 带有类型安全性的 Node.js Postgres 客户端。

- **MQTT.js v5.4** – 用于 Node 和浏览器的 MQTT 客户端。

- **Perspective v2.9** – 快速可视化流式数据集。

- **Rspack v0.5.7** – 快速的基于 Rust 的 Web 打包工具。

## 🙋🏻‍♀️