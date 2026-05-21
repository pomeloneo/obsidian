# JavaScript 中文周刊 #147 - es-toolkit: 一个现代 JavaScript 实用工具库

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533464&idx=1&sn=874111b663cdaf11fb6d90231e832714&chksm=e921087ade56816c0f1613c57f9cdd1c1ae7221ba95d1f0c09af04cdb342a7cb47634e6edf18\#rd  
> 抓取时间: 2026/2/2 23:50:54

---

> 本期看点：类似于 Lodash，但它更新、更快、更小，具有摇树优化和内置的 TypeScript 支持。它不像 Lodash 那么全面，但正在朝着“实现 Lodash 所有功能”的目标迈进。

> 编辑：TimLi

🔥 本周热门

**es-toolkit: 一个现代 JavaScript 实用工具库** — 类似于 Lodash，但它更新、更快、更小，具有摇树优化和内置的 TypeScript 支持。参考指南 展示了目前支持的函数 — 它不像 Lodash 那么全面，但正在朝着“实现 Lodash 所有功能”的目标迈进。

**长按识别二维码查看原文**

https://github.com/toss/es-toolkit

Viva Republica  Inc

**ESLint 的未来展望** — 11 岁的 ESLint 正通过不断发展成为一个任何人都可以为其编写插件的与语言无关的代码检查工具，为未来的 11 年做准备。在 ESLint v9.0 中引入的新配置系统“只是重大变革的开始”。

**长按识别二维码查看原文**

https://eslint.org/blog/2024/07/whats-coming-next-for-eslint/

Nicholas C. Zakas

**加速 JavaScript 生态系统：隔离声明** — “TypeScript 的新隔离声明特性对于开发者之间共享代码是一个改变游戏规则的因素。” 这是 Marvin 关于在 JavaScript 世界中寻找性能提升的精彩系列中的最新内容。

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-10/

Marvin Hagemeister

**快讯：**

- ▶️ 对将模块发布到 npm 与 JSR 的并排比较
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=dzycAeRdOSM
    

- 🎙️ Vue 的创建者 Evan You 参加了 DejaVue 播客 ，谈论了 Vue 的过去十年。
    
    **长按识别二维码查看原文**
    
    https://share.transistor.fm/s/6b6bab42
    

- 🗣️ 浏览器中由 JavaScript 驱动的文本转语音 变得非常出色。
    
    **长按识别二维码查看原文**
    
    https://huggingface.co/spaces/diffusionstudio/vits-web
    

- Node 官方正在努力将 SQLite 集成到 Node.js 中 。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/pull/53752
    

📒 教程与趣事

**在 JavaScript 中重现 THX “Deep Note”** — 使用 Tone.js 进行有趣的声音生成。请注意，人们在不同浏览器上报告的结果参差不齐，但对我来说是有效的。

**长按识别二维码查看原文**

https://keliris.dev/articles/deep-note

Alexander Keliris

**在 Angular 中引入** `**@let**` — 新的 `@let` 语法扩展了 Angular 内置的模板语法，提供了在组件模板中定义变量的更好方式。

**长按识别二维码查看原文**

https://blog.angular.dev/introducing-let-in-angular-686f9f383f0f?gi=7609b4936f03

Mark Thompson 和 Kristiyan Kostadinov

**隐蔽的 React 内存泄漏：React Compiler 也无法拯救** — 虽然新的、令人兴奋的 React Compiler 可以解决很多问题，并使大多数代码库的性能提高，但了解棘手的边缘情况是有必要的。

**长按识别二维码查看原文**

https://schiener.io/2024-07-07/react-closures-compiler

Kevin Schiener

**📄 调整和传输 ArrayBuffers** – Dr. Axel 继续对 ECMAScript 2024 的探索。Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2024/06/array-buffers-es2024.html

**📄 如何使用原生 JavaScript 创建 Chrome 扩展** Esther Vaati

**长按识别二维码查看原文**

https://webdesign.tutsplus.com/how-to-create-a-chrome-extension-with-vanilla-javascript–cms-108762t

**📄 通过构建支持 Suspense 的库来学习 React Suspense** Slava Knyazev

**长按识别二维码查看原文**

https://www.bbss.dev/posts/react-learn-suspense/

**📄 如何成功举办技术大会** – 来自 Remix 背后的团队。Bob Ziroll

**长按识别二维码查看原文**

https://github.com/remix-run/meetup-guides/blob/main/running-a-successful-meetup.md

**📄 从 Express 迁移到 Fastify** Tom MacWright （Val Town）

**长按识别二维码查看原文**

https://blog.val.town/blog/fastify/

🛠 代码与工具

**React Flow v12: 创建基于节点的编辑器和交互式图表** — 作为 xyflow 的一部分，这使得创建基于节点的用户界面变得容易，您可以按照自己的选择将交互式组件连接在一起。还有一个 Svelte 版本 。

**长按识别二维码查看原文**

https://www.xyflow.com/blog/react-flow-12-release

Moritz Klack 和 John Robb

**Croner v8.1: “Cron” 触发和评估** — 使用 cron 语法 按照您选择的计划触发函数。它还可以评估 cron 表达式，为您提供即将到来的时间列表。

**长按识别二维码查看原文**

https://croner.56k.guru/

Hexagon

**TinyBase v5.0: 本地优先应用的响应式数据存储** — 如果您在构建后端时不想那么头疼，这是一个充当应用响应式后端的数据存储。v5.0 包括一个新的 mergeableStore 类型 ，可以将您的数据包装为无冲突复制数据类型（CRDT）。这是主页 。

**长按识别二维码查看原文**

https://tinybase.org/guides/releases/\#v5-0

James Pearce

**PLV8: 在 PostgreSQL 中使用 JavaScript 函数** — 您知道您可以在 Postgres 中使用 JavaScript 来实现诸如存储过程和触发器之类的功能吗？PLV8 是实现这一功能的扩展。PLV8ify 通过将 JS/TS 文件转换为 PLV8 就绪的 SQL 添加了一个额外的层。

**长按识别二维码查看原文**

https://plv8.github.io/

PLV8JS 开发组

**版本发布：**

- **pnpm v9.5** — 这个注重效率的包管理器引入了 Catalogs，一种具有可共享依赖版本说明符的方式。

- **Node.js v22.4.1（Current） ， v20.15.1（LTS） 和 v18.20.4 （LTS）**

- **Deno v1.45 ， Angular v18.1**

- **file-type v19.1** — 从 `Buffer` 、 `Uint8Array` 或 `ArrayBuffer` 检测文件类型。现在它也可以从 web 流读取 。

- **🗓️ Schedule-X v1.50** — Material 设计风格的事件日历和日期选择器。

- **getJS v2.0** — 用 Go 编写的从网站获取 JavaScript 源代码/文件的工具。

- **wa-sqlite v1.0** — 支持浏览器存储扩展的 WebAssembly SQLite 。

- **QuickJS v1.2** — 在 WebAssembly QuickJS 沙箱中执行 JavaScript 代码。

- **True Myth v7.4** — TypeScript 中的安全、惯用的空值和错误处理。

- **tinyqueue v3.0** — JavaScript 中的小而简单的优先级队列。

- **MiniSearch v7.0** — 内存中的全文搜索引擎。

- **Jotai v2.9** — React 的简单、灵活的状态管理。

- **Eruda v3.1** — 移动浏览器的控制台/开发者工具。

🙋🏻‍♀️