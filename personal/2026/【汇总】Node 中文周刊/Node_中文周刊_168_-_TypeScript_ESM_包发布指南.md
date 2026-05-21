# Node 中文周刊 #168 - TypeScript ESM 包发布指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539808&idx=1&sn=233e3cf6d2e4848f05a8c71e91478492&chksm=e9211782de569e94c7e8d1deb0bd8df4d010a2647e5bfba1c424faad695f3c06dfc2ed16671c\#rd  
> 抓取时间: 2026/2/2 23:51:51

---

> 本期看点：Axel 博士详解如何发布基于 ESM 的 TypeScript npm 包，Node.js v22.14.0 发布并新增 TypeScript stdin 执行支持，Anthony Fu 分享转向”纯 ESM”的理由，Node.js v20.18.3 将导入属性和 JSON 模块支持标记为稳定特性。

> 编辑：TimLi

🔥 本周热门

**如何使用 TypeScript 发布基于 ESM 的 npm 包** —— 现在你几乎可以在任何地方使用 ES 模块了，所以了解如何将它们打包并发布到 npm 变得非常重要。Axel 深入探讨了你需要了解的所有内容，并分享了一些实用工具。

**长按识别二维码查看原文**

https://2ality.com/2025/02/typescript-esm-packages.html

Dr. Axel Rauschmayer

**Node v22.14.0（LTS）发布** —— Node 的最新稳定/LTS 版本带来了一系列常规的 bug 修复和改进。其中比较值得注意的包括：通过 `stdin` 执行的代码支持 TypeScript、新增 `--disable-sigusr1` 标志、`assert.register()` 和 `t.assert.fileSnapshot()`。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.14.0

Antoine du Hamel

**为什么要转向”纯 ESM”** —— ES 模块的普及已经持续多年，如果你还在观望，可能是有充分的理由。虽然你可以维护同时支持 ESM 和 CommonJS 的包，但 Anthony 认为现在是时候转向”纯 ESM”了，他在这里解释了原因。

**长按识别二维码查看原文**

https://antfu.me/posts/move-on-to-esm-only

Anthony Fu

**Node v20.18.3（LTS）发布** —— 主要更新是将导入属性和 JSON 模块的支持向后移植，现在这些功能被认为是稳定的。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.18.3

Marco Ippolito

**📄 你的** `**tsconfig.json**` **检查清单** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/01/tsconfig-json.html

**📄 我真的需要这个 Node 依赖吗？** Brian Muenzenmeyer

**长按识别二维码查看原文**

https://brianmuenzenmeyer.com/posts/2024-do-i-need-this-node-dependency/

**📄 如何编写不糟糕的 Cypress 测试** Jonathan Chaffer

**长按识别二维码查看原文**

https://spin.atomicobject.com/write-cypress-tests-that-dont-suck/

**快讯：**

- 🎥 我想把一些 CSS 动画转换成 MP4 视频，但不想自己录屏。最后用 Puppeteer、Node 和 `fluent-ffmpeg` 解决了问题！这是我用来无头转换 HTML 到视频的代码。
    
    **长按识别二维码查看原文**
    
    https://gist.github.com/peterc/8a8ac6e25904c9aee28a325c0f24d392
    

- 🔠 GitHub 更新了它出色的 Monaspace 等宽编程字体系列，增加了对 Nerd Fonts 的支持，包含更多字形、额外的数字 0 设计和更多连字等。
    
    **长按识别二维码查看原文**
    
    https://github.com/githubnext/monaspace/releases/tag/v1.200
    

- Node 20 正在向后移植 `require(esm)` 的无标志支持。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/pull/56927
    

🛠 代码与工具

**import-in-the-middle：模块加载拦截器** —— 这个工具可以在 Node 中拦截 ES 模块的加载过程，如果你想以某种方式修改模块，这会很有用。如果你更喜欢传统方式，还可以使用 require-in-the-middle。

**长按识别二维码查看原文**

https://github.com/nodejs/import-in-the-middle

Node.js Team

**ffast：实验性的 Node.js FFI（外部函数接口）库** —— 这是一个概念验证项目，旨在将所有必要的底层绑定引入 JS 环境，让你可以直接用 JavaScript 创建 FFI 包装器，无需依赖 libffi。作者表示目前在 Linux x64/ARM64 和 macOS/ARM64 上可用（但有诸多限制）。

**长按识别二维码查看原文**

https://github.com/just-js/ffast

Billy Whizz

**Human Regex：使用类英语语法的人性化正则表达式构建器** —— 虽然经过多年的正则表达式使用经验后我已经非常熟悉它们，但不得不说大多数开发者并不太喜欢它们 😉 这个库提供了一种更自然的流式语法选项。Magic Regexp 和 Super Expressive 是这个领域的其他选择。

**长按识别二维码查看原文**

https://github.com/rajibola/human-regex

Ridwan Ajibola

**Pundit-TS：用完整类型安全组织你的授权逻辑** —— 受 Ruby 的 Pundit 库启发，Pundit-TS 提供了一种 TypeScript 风格的方式，让你在应用程序中实现基于角色和属性的访问控制模型。

**长按识别二维码查看原文**

https://github.com/fatihky/pundit-ts

Fatih Kaya

**web-worker v1.5：为浏览器和 Node 提供一致的 Web Workers** —— 想发布同时在 Node 和客户端使用 Web Workers 的 npm 模块吗？在 Node 中，它基于 `worker_threads` 提供了一个兼容 Web 的 Worker 实现。在浏览器中，它就是 `Worker` 的别名。

**长按识别二维码查看原文**

https://github.com/developit/web-worker

Jason Miller

**fast-folder-size：计算目录总大小** —— 可以作为命令行工具或 Node 模块使用。

**长按识别二维码查看原文**

https://github.com/simoneb/fast-folder-size

Simone Busoli

**ioredis 5.5：Node 的强大、高性能、功能完整的 Redis 客户端**

**长按识别二维码查看原文**

https://github.com/redis/ioredis

Zihua Li

**remove-unused-vars** —— 一个用于移除未使用变量的实验性新工具。

**长按识别二维码查看原文**

https://github.com/webpro-nl/remove-unused-vars

Lars Kappert

📢 其他 JavaScript 相关

以下是 JavaScript 生态圈中其他一些有趣的新闻，以防你错过：

- Alex MacArthur 展示了七种不同的方法来拆分长任务。其中只有少数几种适用于 Node，主要关注浏览器场景，因为在浏览器中冻结 UI 是绝对不能接受的。
    
    **长按识别二维码查看原文**
    
    https://macarthur.me/posts/long-tasks/
    

- 多本热门编程指南的作者 Beej 发布了 Beej 的 Git 指南，这是一个从入门到精通的在线资源，帮助你使用这个世界上最流行的分布式版本控制系统。
    
    **长按识别二维码查看原文**
    
    https://beej.us/guide/bggit/
    

- 使用 Nx 的用户注意了！Nx 为其工作空间带来了全新的体验，更快、更高效，并解决了大型 monorepo 中的各种 TypeScript 编辑器支持问题。
    
    **长按识别二维码查看原文**
    
    https://nx.dev/
    

- 📺 来自精彩的▶️ Node.js：纪录片的创作者推出了▶️ 关于 Angular 框架的新纪录片。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=LB8KwiiUGy0
    

**版本发布：**

- **pnpm v10.3** —— 这个快速、高效的包管理器增加了 `strict-dep-builds` 选项，如果有任何依赖项包含未经审查的构建脚本，将以非零退出代码退出。

- **Express Zod API v22.8** —— 快速的模式验证和自定义中间件。

- **Mongoose v8.10** —— 流行的 MongoDB 对象建模库。

- **Typegoose v12.11** —— 将 Mongoose 8.10 模型定义为 TypeScript 类。

- **Jasmine v5.6** —— 适用于浏览器和 Node 的测试框架。

- **Globby v14.1** —— 用户友好的 glob 匹配工具。