# JavaScript 中文周刊 #208 - Bun v1.3 全栈 JavaScript 运行时重大更新

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544160&idx=1&sn=40871f7cbecf94273df13fc59e79f6fa&chksm=e9216682de56ef94af1ca458288419bde9566128a14dfb6f1770ff7469b8d17cd81a81ffa095\#rd  
> 抓取时间: 2026/2/2 23:49:36

---

> 本期看点：Bun v1.3 发布并成为全栈 JavaScript 运行时，内置全栈开发服务器和数据库，Vite+ / VitePlus 全新工具链正式发布，Node.js v25.0.0 当前版本上线并内置 Web Storage 支持，WAICT：提升 Web 上 JavaScript 可信度。

> 编辑：TimLi

🔥 本周热点

**Bun v1.3：全栈 JavaScript 运行时** —— Bun 1.3 刚推出没多久，这绝对是这周 JavaScript 圈里最热的消息！Bun 是一个追求高性能和极致开发体验的 JavaScriptCore 驱动的运行时系统，这次 v1.3 升级后，既可以作为 Node.js 的无缝替代品，还具备了一大波新特性，成为名副其实的“全栈运行时”，包括：

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.3

- 在 `Bun.serve` 里内置了全栈开发服务器和热重载功能
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.3\#hot-reloading
    

- 更高效的垃圾回收（GC），闲置时 CPU 和内存占用更低

- 内置 MySQL 和 Redis 客户端（之前有 Postgres 和 SQLite，现在更加齐全）

- 前后端应用程序都能一次性打包进一个可执行文件
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.3\#compile-full-stack-apps-to-a-standalone-executable
    

- Windows 和 macOS 下支持可执行文件的代码签名
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.3\#code-signing-support
    

- 包管理方式默认采用了类似 pnpm 的隔离安装，点这里了解详情
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/175807/web
    

当然啦，Bun 每次大版本发布都少不了▶️  发布视频，强烈推荐一看！

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175808/web

来自 Bun 团队

**Vite+ / VitePlus 发布** —— Evan 在上周的 ViteConf 上正式发布了这个基于 Vite 的全新工具链（现已早期公开）。它比传统的 Vite 更强大、统一，同时有商业化考虑，但个人、开源项目和小企业都能免费用，源代码也会开放。

**长按识别二维码查看原文**

https://voidzero.dev/posts/announcing-vite-plus

Evan You

**Node.js v25.0.0（当前版本）正式上线** —— Node 最新的前沿版本来了！这次内置开启了 Web Storage、`JSON.stringify` 性能显著提升，权限模型引入了新的 `--allow-net` 选项，还直接支持 `Uint8Array` 的 base64/hex 转换，WebAssembly 和 JIT 也都有优化升级。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.0.0

Rafael Gonzaga

**快讯：**

- Cloudflare Sandboxes 新服务上线，你可以在隔离安全的容器“沙盒”里运行不可信的 JavaScript 和 Python 代码。
    
    **长按识别二维码查看原文**
    
    https://sandbox.cloudflare.com/
    

- Remix 项目的活动 Remix Jam 上周举行，感兴趣的同学可以 ▶️ 观看完整直播。想直接看 Remix 3 的新特性展示，跳到 `03:24:30`。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/175814/web
    

- 为什么 `typeof null === 'object'`？ Piotr Zarycki 深入追溯了这段历史，比你想象的更有故事。
    
    **长按识别二维码查看原文**
    
    https://pzarycki.com/en/posts/js-null/
    

- Lit 项目加入 OpenJS Foundation，影响力进一步扩大。
    
    **长按识别二维码查看原文**
    
    https://lit.dev/blog/2025-10-14-openjs/
    

📖 文章和视频

**提升 Web 上 JavaScript 可信度** —— 这篇文章介绍了由 W3C 支持的 WAICT（Web Application Integrity, Consistency, and Transparency）项目，目标是让网页像 App Store 一样安全，保证浏览器执行的代码真的没被篡改。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175823/web

Michael Rosenberg (Cloudflare)

**▶  超越 Signals** —— SolidJS 创作者半小时深度演讲，聊聊 signal（响应式信号）对前端架构的影响以及未来发展趋势，虽然现在 signal 已经很常见了，但他认为才刚刚开始，未来可期！

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175825/web

Ryan Carniato

**Lazy Fields：不用装饰器也能让代码 30 倍提速** —— 这招来自 Joist ORM 团队，对性能有极大提升，适合喜欢挖掘极限效率的同学。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175828/web

Stephen Haberman (Joist)

**🌿 快速搞懂 Barnsley 蕨类分形图** —— Barnsley 分形 用数学方式生成自然界蕨类结构，想了解分形画图的可以玩一玩这个教程。

**长按识别二维码查看原文**

https://slicker.me/javascript/fern%20fractal.htm

Slicker

💡 Slicker 其实还有不少有意思的“古早” JavaScript 效果，比如 Julia 集合分形、等离子波、火焰特效 等，有空可以去看看。

**长按识别二维码查看原文**

https://slicker.me/fractals/animate.htm

📄 **用 DevTools 查找 JavaScript 对象分配位置** —— 一个稍微绕点但很实用的 Chrome DevTools 小技巧，让你追踪特定对象到底在哪分配的。Joona Heikkilä

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175835/web

📄 **现代 Node.js 文件读写指南** —— 超全面的 Node.js 读写文件方案大合集，Luciano Mammino

**长按识别二维码查看原文**

https://nodejsdesignpatterns.com/blog/reading-writing-files-nodejs/

📄 **Angular 表单如何重构为 Signal 表单** Tim Deschryver

**长按识别二维码查看原文**

https://timdeschryver.dev/blog/refactoring-a-form-to-a-signal-form

📄 **如何上手 GitHub Copilot CLI** Andrea Griffiths (GitHub)

**长按识别二维码查看原文**

https://github.blog/ai-and-ml/github-copilot/github-copilot-cli-how-to-get-started/

🛠  代码与工具

**DOMPurify v3.3：高效宽容的 HTML XSS 过滤器** —— 支持所有主流浏览器和 Node.js，测试非常全面。点这里可以在线体验。

**长按识别二维码查看原文**

https://github.com/cure53/DOMPurify

Cure53

**python-node：让 Python ASGI 程序跑在 Node.js 里** —— 几个月前 Platformatic 推出了 `php-node`，让 PHP 能嵌进 Node 应用程序。现在轮到 Python 了！@platformatic/python-node 内置 Python 解释器，可以和 Node 无缝通信，并支持 ASGI。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175841/web

Stephen Belanger 和 Matteo Collina

**jsonriver：简单高效的流式 JSON 解析器** —— 这个库能让你边接收边解析 JSON，非常适合网络流或 LLM 场景，能逐步产出“越来越完整”的数据结果。

**长按识别二维码查看原文**

https://github.com/rictic/jsonriver

Peter Burns (Google)

**Kaluma v1.3：极简 JS 运行时专为 Raspberry Pi Pico 2 打造** —— 这么小的设备也能装下 JS 运行时？Kaluma 说可以！它借助超轻量 JerryScript 引擎，不仅能跑 JS，还保留了一些 Node.js 的小便利。

**长按识别二维码查看原文**

https://kalumajs.org/

Kaluma 项目

**Triplex：可视化 React 组件构建工具** —— Triplex 原本是用来做 3D 组件布局的商业工具（基于 React Three Fiber），现在已经开源，还支持 VS Code 扩展，以及普通 React DOM 元素和组件的可视化搭建。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/175852/web

Mike Douges 和 Pmndrs

📢 其他资讯

这里来一波圈内的新鲜事小合集：

- React 团队刚刚发布 React Compiler 1.0 正式版，它能自动分析你的 React 代码自动加上 memo 优化，用起来超省心。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2025/10/07/react-compiler-1
    

- Sebastian Lague 的 ▶️ 鲜活烟雾模拟 视频，教你用数学模型模拟流体烟雾。虽然不是 JS 写的，但想搞懂原理的小伙伴可以去看看。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/175868/web
    

- 本周 Firefox 144 发布，所有主流浏览器都支持了 **view transitions** 前端小特性，页面切换动画更丝滑。
    
    **长按识别二维码查看原文**
    
    https://www.firefox.com/en-US/firefox/144.0/releasenotes/
    

- PostgreSQL 18 发布，新异步 I/O 子系统带来的性能提升立竿见影，这里有 Postgres 17 vs 18 的数据对比。
    
    **长按识别二维码查看原文**
    
    https://www.postgresql.org/about/news/postgresql-18-released-3142/
    

- 你听说过 HTML 的
    
    标签吗？ 它其实有很多有趣用法。**长按识别二维码查看原文**     
    https://denodell.com/blog/html-best-kept-secret-output-tag
    

- 🐈 Cat cams！和编程关系不大，但 meow.camera 能随机带你“云吸猫”。没看到喵星人？可以试试切换镜头。要是不爱猫，去看纳米布沙漠的野生动物吧～
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/175875/web
    

**版本发布：**

- **React Native v0.82** —— 新时代！React Native 现在完全迁移到了新架构。

- **Graffle v7.3** —— 前身叫 graphql-request 的 GraphQL 客户端，v7.3 新增了 CommonJS 支持，更兼容 Jest 和非 ESM 项目。

- **Skeleton v4.0** —— 基于 Tailwind CSS 的自适应设计系统，主页在这里，可以先睹为快。

- 🗓️ **Schedule-X v3.3** —— 事件日历控件，MIT 协议，部分高级功能需要付费。

- **json-joy v17.55.0** —— 支持 JSON 实时协作编辑的新算法和工具包。

- **Ky v1.12** —— 基于 Fetch 的简洁 HTTP 客户端，支持浏览器、Node 还有 Deno。

- 🗓️ **React Date Picker v8.8** —— 简单好用的日期选择器组件（在线演示）。

- **Faker v10.1** —— 想怎么造假数据都没问题，随心造到爽。