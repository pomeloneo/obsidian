# JavaScript 中文周刊 #215 - JavaScript 30 岁生日快乐！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544995&idx=1&sn=7f45d7261222a89e9d54059a50a67fb0&chksm=e9217b41de56f257dbf3f8e4614c3277a563d4ebba2e22bc9d765463c46b2c199a8a789d54a7\#rd  
> 抓取时间: 2026/2/2 23:49:25

---

> 本期看点：JavaScript 正式诞生距今已经 30 年，TypeScript 7 进展公布，新版基于 Go 重写速度提升 10 倍，Anthropic 收购 Bun JavaScript 运行时并承诺继续开源，Vite 8 Beta 发布。

> 编辑：TimLi

🎉  JavaScript 诞生 30 周年啦！  🎉

早在 1995 年 5 月，33 岁的 Brendan Eich 只用十天时间就 写出了 JavaScript 的第一个原型，那时候它还叫 **Mocha**，后来叫 **LiveScript**。1995 年 12 月 4 日，Netscape 和 Sun Microsystems 在官方新闻发布中 首次正式推出“JavaScript”，说它“是一种易于使用的面向对象脚本语言，方便大家在客户端和服务器端创建联动的在线应用程序”。

**长按识别二维码查看原文**

https://arstechnica.com/gadgets/2025/12/in-1995-a-netscape-employee-wrote-a-hack-in-10-days-that-now-runs-the-internet/

30 年过去，JavaScript 已经牢牢扎根在 Web 平台核心，不仅仅是前端，连桌面应用程序、操作系统（比如 Windows 也用 React Native）、移动应用程序，甚至 各种单片机上 都有它的身影。

**长按识别二维码查看原文Jolt.js**

https://www.espruino.com/

让我们期待再来 30 年，也希望 大家关于 JavaScript 商标的那些混乱和诉讼都早点有个结果。Larry，能不能送我们个不一样的圣诞礼物啊？ 😅

**长按识别二维码查看原文**

https://javascript.tm/letter

**顺便说一句，别忘了上面那张生日合集中找找 1995 年的彩蛋哦。**

🔥 本周热点

**TypeScript 7 进展** —— TypeScript 项目最近对外很低调，但其实团队一直在加紧开发 TypeScript 6.0 和 7.0。6.0 是最后一个基于 JavaScript 的版本，会为后续原生 Go 移植版（7.0）铺路，而新版 7.0 已经展现出速度能提升 10 倍！

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/progress-on-typescript-7-december-2025/

Daniel Rosenwasser（Microsoft）

**Anthropic 收购 Bun JavaScript 运行时** —— 最近几年对 Bun 这个基于 JavaScriptCore 的 JS/TS 运行时来说可谓风云变幻。Anthropic（以其 Claude LLMs 闻名）如今把 Bun 作为自家 Claude Code 代理开发工具等产品的底层引擎。Jarred 也在文中讲述了 Bun 的成长故事，并保证 Bun 会继续开源并变得更强大。

**长按识别二维码查看原文**

https://bun.com/blog/bun-joins-anthropic

Jarred Sumner

**快讯：**

- ⚠️ React 团队最近 公布了 React Server Components 的一个重要安全漏洞，会影响支持 RSCs 的应用程序，部分 Next.js 也受影响。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2025/12/03/critical-security-vulnerability-in-react-server-components
    

- 🎄 每年一度的 Advent of Code 正在进行，今年有 12 天的编程谜题等你解锁。
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

- 如果你想玩点更偏 JavaScript 的，AdventJS 提供了一些可以在浏览器里直接做的 JS 谜题。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/178093/web
    

- Advent of Svelte 整个 12 月每天都会分享一则 Svelte 小贴士。
    
    **长按识别二维码查看原文**
    
    https://advent.sveltesociety.dev/2025
    

- WebGPU 现在已在主流浏览器全面支持。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/webgpu-supported-major-browsers
    

📖  文章与视频

No More Tokens: Locking Down `npm` Publishing Workflows —— 最近 npm 安全事件频发，11ty 作者 Zach 专门梳理了一下自己 npm 的安全状况，也分享了许多可以借鉴的安全经验。

**长按识别二维码查看原文**

https://www.zachleat.com/web/npm-security/

Zach Leatherman

💡 Liran Tal 也分享了 一篇 npm 安全实践干货，有需要的可以看看。

**长按识别二维码查看原文**

https://snyk.io/articles/npm-security-best-practices-shai-hulud-attack/

用 JSDoc 玩转 JavaScript 类型系统 —— 如果你更喜欢写 JavaScript 又想要一点类型优势，用 JSDoc 其实很有意思，也是不少开发者的选择。

**长按识别二维码查看原文**

https://thathtml.blog/2025/12/nuances-of-typing-with-jsdoc/

Jared White

浏览器处理 Base64 数据有多快？ —— 在大多数现代硬件下，速度都能轻松上 GB/s，就是 Firefox 和 Servo 慢点。

**长按识别二维码查看原文**

https://lemire.me/blog/2025/11/29/how-fast-can-browsers-process-base64-data/

Daniel Lemire

用 JS 做“无人机氛围噪音”合成器 —— 利用 Web Audio API 和颗粒合成技术让任意文件都能变成声音，可以在线体验 demo！

**长按识别二维码查看原文**

https://bs.stranno.su/drone-ambient-noise-synthesizer/

Stranno

📊 AWS Lambda Arm 与 x86 性能对比（各运行时） —— 对比了 Node.js 不同版本，结论：在 Lambda 上 Arm 明显优于 x86。Chris Ebert

**长按识别二维码查看原文**

https://chrisebert.net/comparing-aws-lambda-arm64-vs-x86_64-performance-across-multiple-runtimes-in-late-2025/

📄 Angular Pipes：是时候重新思考了 —— 现在已经很少见到高质量的 Angular 技术文章，这篇内容值得一读。Vyacheslav Borodin

**长按识别二维码查看原文**

https://javascriptweekly.com/link/178108/web

📄 TypeScript 严格模式其实并非递增：分析 `strictNullChecks` 和 `noImplicitAny` Huon Wilson

**长按识别二维码查看原文**

https://huonw.github.io/blog/2025/12/typescript-monotonic/

📄 如何用 TypeScript 测试一个 Vue Composable John Franey

**长按识别二维码查看原文**

https://johnfraney.ca/blog/how-to-unit-test-a-vue-composable-with-typescript/

📄 给 JavaScript 开发者看的范畴论入门 Ibrahim Cesar

**长按识别二维码查看原文**

https://ibrahimcesar.cloud/blog/category-theory-for-javascript-typescript-developers/

🛠  代码与工具

**🤖 TanStack AI：统一对接 LLM/AI 服务商的新接口** —— TanStack 家族又多了一个新成员，面向多家 AI API，支持流式输出，自动推断 Zod schema，框架无关，目前在 **alpha** 阶段。 GitHub 地址

**长按识别二维码查看原文**

https://tanstack.com/ai/latest

TanStack

💡 新出的还有 TanStack Pacer，专注于去耦合的防抖、节流、限流、队列和批处理这些常用函数处理小工具，框架无关。

**长按识别二维码查看原文**

https://tanstack.com/pacer/latest

**Remend：自动修复 Markdown 流式内容** —— 智能处理“不完整”Markdown，超级适合和 LLM 搭配场景。它基于 Vercel 自家 Streamdown 项目提炼出来，可以替换 `react-markdown`，专为 AI 流式渲染设计。

**长按识别二维码查看原文**

https://vercel.com/changelog/new-npm-package-for-automatic-recovery-of-broken-streaming-markdown

Hayden Bleasel（Vercel）

**Tinybench v6.0：极简基准测试库** —— 它会用到你环境里最精准的计时器（比如 `process.hrtime` 或 `performance.now`），可以轻松 benchmark 任意函数、定时间或定次数，还能输出丰富的统计数据，支持多种运行时。GitHub 地址

**长按识别二维码查看原文**

https://github.com/tinylibs/tinybench

Tinylibs

**Ruby2JS：Ruby 到 JavaScript 的转译器** —— 它生成的代码更像“手写 JS”而不是简单转换出来的机器代码。主页自带在线 demo，可以试着玩一玩。

**长按识别二维码查看原文**

https://www.ruby2js.com/

Sam Ruby 和 Jared White

📢  生态系统其他有趣的内容

生态圈里还有这些新鲜事：

- 🤖 Colin Eberhardt 探索了 GitHub 的 **Spec Kit** 组合玩法，用 Spec-Driven Development（SDD）方式和 AI 代理一起搭建 Svelte 应用程序。
    
    **长按识别二维码查看原文**
    
    https://blog.scottlogic.com/2025/11/26/putting-spec-kit-through-its-paces-radical-idea-or-reinvented-waterfall.html
    

- DebugBear 团队带来了 2025 Web 性能回顾，梳理了今年 DevTools 的演进，TTFB/LCP/INP 等核心指标的新变化，以及 Firefox 正式支持了 Scheduler API。
    
    **长按识别二维码查看原文**
    
    https://www.debugbear.com/blog/2025-in-web-performance
    

- Brian ‘Beej’ Hall，那个靠各种 教程（比如网络编程、Git）出名的大佬，新出了本 Beej’s Guide to Learning Computer Science。不是代码教学，而是聊怎么理解问题和解决问题的思路哲学，更侧重底层逻辑，很适合开阔思路。
    
    **长按识别二维码查看原文**
    
    https://beej.us/guide/
    

- DepX 的徽章生成器 可以帮你的 README 或项目主页加个动态 badge，展示 npm 包的依赖数目（多或少都行）。
    
    **长按识别二维码查看原文**
    
    https://depx.co/badge
    

- 想要快速弄懂椭圆曲线密码算法？这篇尝试一文说清楚了。
    
    **长按识别二维码查看原文**
    
    https://avidthinker.github.io/2025/11/28/understanding-ecdsa/
    

**版本发布：**

- **Vite 8 Beta** —— 现在基于 Rolldown，构建比以前快不少，也为后续新功能升级铺平道路。

- **Oxfmt：Oxc Formatter Alpha** —— Rust 驱动，兼容 Prettier 的代码格式化工具。

- **ESLint v10.0.0 Alpha 1**

- **Chokidar v5.0** —— 高效跨平台的 Node.js 文件监听库。

- **Prisma v7.1** —— 做 Node.js 和 TypeScript 开发的热门 ORM。

- **Neutralinojs v6.4** —— 更轻量的 Electron 替代品。

- **Express v5.2.0** 和 **v5.2.1**