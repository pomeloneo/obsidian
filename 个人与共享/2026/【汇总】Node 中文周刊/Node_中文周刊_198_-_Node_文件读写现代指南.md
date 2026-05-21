# Node 中文周刊 #198 - Node 文件读写现代指南

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544100&idx=1&sn=987c91bccd29526ace52f6cb2ff648dd&chksm=e92166c6de56efd08776d6ca81262255274ffc63a50d3f4664193773ca784d7bc3d1c8016363#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544100&idx=1&sn=987c91bccd29526ace52f6cb2ff648dd&chksm=e92166c6de56efd08776d6ca81262255274ffc63a50d3f4664193773ca784d7bc3d1c8016363#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544100&idx=1&sn=987c91bccd29526ace52f6cb2ff648dd&chksm=e92166c6de56efd08776d6ca81262255274ffc63a50d3f4664193773ca784d7bc3d1c8016363#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544100&idx=1&sn=987c91bccd29526ace52f6cb2ff648dd&chksm=e92166c6de56efd08776d6ca81262255274ffc63a50d3f4664193773ca784d7bc3d1c8016363#rd)

---

> 本期看点：Node 文件读写现代指南;把 Python ASGI 集成进 Node.js 应用程序的新方法;Bun v1.3 发布并成为更接近全栈的 JavaScript 运行时，自带开发服务器和内建数据库客户端；Node.js 20+ 容器内的内存管理。

> 编辑：TimLi

🔥 本周热门

📂 **Node 文件读写现代指南** —— 这篇详细的文章手把手带你了解在 Node 中读写文件的各种方式，包括用 Promise、流、并发处理、文件句柄以及高效内存利用的小妙招，几乎把各种场景都涵盖了。

**长按识别二维码查看原文**

https://nodejsdesignpatterns.com/blog/reading-writing-files-nodejs/

Luciano Mammino

**把 Python ASGI 集成进 Node.js 应用程序的新方法** —— 还记得前阵子 Platformatic 推出的 `php-node` 吗？他们让你能把 PHP 嵌到 Node 应用程序里。现在轮到 Python 了！`@platformatic/python-node` 就是官方出品的 Node.js 原生桥接工具，直接内置 Python 解释器，支持 ASGI 协议，玩转 Python 与 Node 的混合开发。

**长按识别二维码查看原文**

https://blog.platformatic.dev/bring-python-asgi-to-your-nodejs-applications

Stephen Belanger 和 Matteo Collina

**Bun v1.3：替代型全栈 JavaScript 运行时** —— Bun 基于 JavaScriptCore，兼顾性能与优雅，现在在许多场景下都能直接替换 Node。v1.3 让它更接近“全栈”，自带开发服务器（支持热重载）、内建 MySQL/Postgres/SQLite/Redis 客户端、强大 WebSocket、默认独立包管理、以及极大加强对 Node.js 兼容性（特别是 `worker_threads` 相关）。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.3

Bun 团队

**Node.js 20+ 容器内的内存管理** —— 本文专门解答了：在容器下用 Node.js 时，你到底还需不需要手动配置 heap size，还是会自动感知？实用科普，别错过！

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/10/10/nodejs-20-memory-management-containers

De Melo Jnr. 和 Ayala（Red Hat）

📄 **Node.js 22 不该错过的新特性** —— Node 22 已经成了 LTS，你可以放心用上最新版那些炫酷的新特性。作者：Lizz Parody

**长按识别二维码查看原文**

https://nodesource.com/blog/nodejs-22-features

📄 **GitHub Copilot CLI 入门超简单** Andrea Griffiths (GitHub)

**长按识别二维码查看原文**

https://github.blog/ai-and-ml/github-copilot/github-copilot-cli-how-to-get-started/

**快讯：**

- Node.js v24.10.0（最新） 发布啦，这次更新内容偏小，主要是依赖和 bug 修复。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v24.10.0
    

- 🔒 GitHub 正在升级 npm 的安全策略，尤其是你如果用 classic token 发布包，请关注官方说明，以免被突然“限流”影响项目上线。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-10-10-strengthening-npm-security-important-changes-to-authentication-and-token-management/
    

- Pavel Romanov 整理了一份如何在 Node 里用 TypeScript 的实用指南，不仅有现代“类型擦除”的流程，也介绍了 Node 类型定义与生态工具的配合和可能会遇到的坑。
    
    **长按识别二维码查看原文**
    
    https://nodevibe.substack.com/p/using-typescript-in-nodejs
    

🛠  代码与工具

**jsonriver：简单、快速的流式 JSON 解析库** —— 这个库主打一边网络流（比如 LLM 调用、请求等）一边实时增量解析 JSON，直接返回“越来越完整”的数据序列，处理大数据文件简直太香了。

**长按识别二维码查看原文**

https://github.com/rictic/jsonriver

Peter Burns (Google)

**xmlbuilder2 v4.0：JS 对象转 XML 利器** —— 支持把 JS 对象转成 XML、解析和序列化 XML，也能链式写法一步步构造文档，处理复杂 XML 场景特别方便。

**长按识别二维码查看原文**

https://github.com/oozcitak/xmlbuilder2

Ozgur Ozcitak

**Kaluma v1.3：专为 Raspberry Pi Pico 2 打造的极小 JS 运行时** —— 你能想象 JS 运行时塞进 RP2350 的 Pico 2、还带点 Node.js 味小功能吗？Kaluma 就做到了。v1.3 用了最新的 JerryScript 引擎，极度精简，适合资源受限设备。

**长按识别二维码查看原文**

https://kalumajs.org/

Kaluma 项目组

**Crosspost v1.0：一键群发多平台的 JS 库** —— 一个 Node.js 库和 CLI 工具，让你同时发 Mastodon、Bluesky、X、Discord、Telegram 等社交网络，内容分发、宣传什么的都省心不少。

**长按识别二维码查看原文**

https://github.com/humanwhocodes/crosspost

Nicholas C. Zakas

**Serialize JavaScript v7.0：让对象“超越” JSON 的序列化工具** —— 如果你想序列化正则、日期、函数，甚至 `Infinity`，这个库都帮你搞定，当然普通 JSON 能做的它也都支持。

**长按识别二维码查看原文**

https://github.com/yahoo/serialize-javascript

Yahoo

**MaxIntervalCover.js：计算最大不重叠区间的 JS 算法库**

**长按识别二维码查看原文**

https://github.com/rawify/MaxIntervalCover.js

Robert Eisele

📢  其他生态

带你逛一圈近期 JS 领域那些有意思的新东西：

- 想玩点花样？这里有个纯 JS 写的管道式组合实现（通过 `|` 实现管道），核心就是用 `Symbol.toPrimitive` 和一点巧妙代码搞出的黑科技。源码很精彩！
    
    **长按识别二维码查看原文**
    
    https://github.com/irony/aspipes
    

- 出过Node.js、Angular、React 纪录片的那帮人又来了，这次带来 ▶️ **Vite** 的纪录片，这个构建工具这几年火到飞起，片子里大神云集现身说法。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=LB8KwiiUGy0&t=17s
    

- 还是说 Vite，VoidZero 搞了个 Vite+（Viteplus），算是功能增强版，比如自带 linter、测试与 monorepo 任务管理等新特性，不过记得提前看看授权协议，别玩花了把自己绕进坑。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/announcing-vite-plus
    

- Next.js 16 测试版 发布，带来稳定的 Turbopack、React 19.2 支持，还有 React Compiler 加持。（React Compiler v1.0 也正式亮相啦。）
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/next-16-beta
    

**版本发布：**

- **Playwright v1.56** —— 微软推出的浏览器/网页自动化工具库，这次亮点是加入了 ▶️ Playwright Agents，专为 LLM 提供测试脚本“导航定义”，帮助 AI 自动写测试更智能啦。

- **Happy DOM v20.0** —— 一个跨平台的 JS 无 UI 浏览器实现，这版有个变化，JavaScript 代码默认不再直接运行了，更安全。

- **Sidequest v1.10** —— Node 应用程序用来批量处理后台任务的伸缩型处理器。最新版 SQLite 后端启用了 WAL 模式，性能直线上升。

- **🤖 OpenAI Node v6.3** —— OpenAI 官方发布的 Node API 库，基础稳定，升级勤快。

- **Ow v3.1** —— 人性化参数校验工具，链式易读，类型判别告别“屎山代码”。

- **Got v14.5** —— 让你写 HTTP 请求像聊天一样顺手的 Node 库。