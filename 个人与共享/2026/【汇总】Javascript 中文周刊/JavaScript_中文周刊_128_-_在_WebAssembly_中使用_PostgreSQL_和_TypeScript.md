# JavaScript 中文周刊 #128 - 在 WebAssembly 中使用 PostgreSQL 和 TypeScript

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529131&idx=1&sn=7d1ed7a3502126027b944305d8496f8d&chksm=e9213949de56b05f9b6a4a628425669832abb71ed02f49a6f864a0f8304b56999bcc7fd7572a\#rd  
> 抓取时间: 2026/2/2 23:51:18

---

> 本期看点：人们曾在 Linux VM WASM 层之上将 Postgres 引入浏览器。而现在 PGlite 能够将 Postgres 的 WASM 构建打包成一个 TypeScript 库，可以在浏览器中或者在 Node.js 或 Bun 中运行，压缩后仅为 3.7MB。

> 编辑：Yucohny、Jojo

🔥 本周热门

**PGlite：在 WebAssembly 中使用 PostgreSQL 和 TypeScript** —— 人们曾在 Linux VM WASM 层之上将 Postgres 引入浏览器。而现在 PGlite 能够将 Postgres 的 WASM 构建打包成一个 TypeScript 库，可以在浏览器中或者在 Node.js 或 Bun 中运行，压缩后仅为 3.7MB。你可以在 此处体验实时部署。

**长按识别二维码查看原文**

https://github.com/electric-sql/pglite

ElectricSQL / Neon

**Parcel v2.12.0：现已支持 Bun 风格的宏** —— 这个受欢迎的零配置构建工具引入了对捆绑时宏的支持，例如那些在 Bun 中提供的宏。宏返回的值将内联到捆绑包中，取代原始调用。这里有 一个新的在线 REPL，你可以在其中使用支持大部分 Parcel 功能的浏览器中体验 Parcel。

**长按识别二维码查看原文**

https://parceljs.org/blog/v2-12-0/

Parcel.js

**快讯：**

- 有关 V8 JavaScript 引擎的最近更新摘要。
    
    **长按识别二维码查看原文**
    
    https://blog.appsignal.com/2024/02/28/top-8-recent-v8-in-node-updates.html
    

📒  教程与趣事

- **使用 Performance API 上报核心 Web 指标** —— Performance API 提供了一种从 JavaScript 测量和评估 Web 性能指标的接口。Geoff 演示了如何利用其功能来进行性能报告测试。
    
    **长按识别二维码查看原文**
    
    https://www.smashingmagazine.com/2024/02/reporting-core-web-vitals-performance-api/
    

Geoff Graham

- **一行有趣的 JavaScript 代码** —— 具体而言，使用 `Promise.race` 同时前向和后向搜索音频文件，并在找到相关元数据立刻停止。
    
    **长按识别二维码查看原文**
    
    https://dbushell.com/2024/02/27/a-fun-line-of-code/
    

David Bushell

- **为什么** `**is-number**` **包每周有 7000 多万次下载？** —— 部分原因是它包含在一个非常流行项目使用的依赖链中。
    
    **长按识别二维码查看原文**
    
    https://shubhamjain.co/2024/02/29/why-is-number-package-have-59m-downloads/
    

Shubham Jain

- **JavaScript 重写世界的 17 个方程式** —— 如果你喜欢数学，这非常有趣。
    
    **长按识别二维码查看原文**
    
    https://runjs.app/blog/equations-that-changed-the-world-rewritten-in-javascript
    

RunJS

- **使用 Astro、Tailwind CSS 和 Alpine.js 创建侧边栏导航**
    
    **长按识别二维码查看原文**
    
    https://lexingtonthemes.com/tutorials/how-to-create-a-sidebar-navigation-with-tailwindcss-and-alpine-js/
    

Michael Andreuzza

🛠  代码与工具

- **PrimeVue 3.49.0：Vue UI 组件库** —— 一组成熟丰富的面向 Vue 开发人员的开源 UI 组件，我们几年前首次提到。这个新版本包括用于 输入一次性密码 和用于向导式工作流程的 “stepper” 的组件。还有一种新的可选 声明性语法 用于使用组件，使其代码更易于阅读和编写。
    
    **长按识别二维码查看原文**
    
    https://primevue.org/
    

PrimeTek

- **Embla Carousel 8：具有流畅运动和“滑动精度”的轮播组件** —— 轮播是一种常见但经常受到诟病的 UI 元素，但这里的 示例 对我们来说效果相当不错。与库无关，但如果需要的话，可以轻松集成到 React、Solid 和 Angular 中。v8.0 版本发布说明 涵盖了许多新功能。
    
    **长按识别二维码查看原文**
    
    https://www.embla-carousel.com/
    

David Jerleke

- **Readability.js：从 HTML 文档中提取可读内容** —— 这是 Firefox 的 阅读视图 所使用的库的独立版本。我们已经有几年没有提到它了，但它继续得到改进。
    
    **长按识别二维码查看原文**
    
    https://github.com/mozilla/readability
    

Mozilla

- **Viz.js：在浏览器中使用 Graphviz** —— Graphviz 是一个拥有 30 多年历史的开源图形绘制工具套件。Viz.js 基于 WebAssembly Graphviz ，将一些功能带入浏览器，正如主页上的实时演示所示。GitHub 仓库。
    
    **长按识别二维码查看原文**
    
    https://viz-js.com/
    

Michael Daines

- **🎨 Vue Color Wheel：Vue 3 的轮式颜色选择器** —— 虽然这不是一个新颖的想法，但在其主页上展示得非常优雅。如果轮式视图不是必需的话，Coloris 是这个领域中一个不错的基本替代品。
    
    **长按识别二维码查看原文**
    
    https://vue-color-wheel.vercel.app/
    

Robert Shaw

- **WXT: 下一代 Web 扩展框架** —— 一个用于创建跨浏览器扩展的框架。你可以针对 Chrome、Firefox、Edge 和 Safari 进行开发。在这个领域，另一个选择是 Plasmo。
    
    **长按识别二维码查看原文**
    
    https://wxt.dev/
    

WXT

**版本发布：**

- **Express.js v4.18.3** – 时隔十六个月的首次发布。😁

- **Deno v1.41** – `deno compile`二进制文件大小大幅缩小，官方支持 Linux ARM64 二进制文件，并改进了与 Node.js 的兼容性。

- **Playwright v1.42** – 浏览器远程控制和运行工具包。

- **Babel v7.24.0** – 支持导入 JSON 模块，并更新了其装饰器实现。

- **TinyMCE v7.0** – 富文本编辑器组件，现在采用 GPL 许可。

- **React Strict DOM (RSD)** – React DOM 和 StyleX 的实验性集成，标准化了 Web 和本地 React 组件的开发。

- **🗓 React Date Picker v6.2** – 简单的日期选择器组件，这里是演示。

- **webdav-client v5.4** – 用于 Node 和浏览器的 WebDAV 客户端库。

- **Jotai v2.7** – 用于 React 的简单灵活的状态管理。

- **🎹 JZZ v1.8** – 用于 Node 和浏览器的 MIDI 库。

- **RxDB v15.10** – 离线优先、反应式数据库。

- **Bun v1.0.29** – 较小的增强。

🙋🏻‍♀️