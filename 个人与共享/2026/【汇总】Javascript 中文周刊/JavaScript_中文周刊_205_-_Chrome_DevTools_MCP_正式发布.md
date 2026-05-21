# JavaScript 中文周刊 #205 - Chrome DevTools MCP 正式发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543827&idx=1&sn=0ba8e57807dc57c985db422199bdeae8&chksm=e92167f1de56eee70e16a27bf95751c4bd2cb6a6f5473001a769651e7bb99c5e59d8593fdc4a\#rd  
> 抓取时间: 2026/2/2 23:49:40

---

> 本期看点：Chrome DevTools MCP 正式发布，GitHub 发布更安全的 npm 供应链计划应对近期攻击，GitHub Copilot CLI 进入公开预览阶段，如何将现代 TypeScript 移植到 DOS 系统上运行。

> 编辑：TimLi

🔥 本周热点

**让 AI 成为你的眼睛：Chrome DevTools MCP 正式发布** —— Chrome 团队发布了 Chrome DevTools 的 MCP 服务器，让 Claude Code 或 OpenAI Codex 等 AI 助手能够使用 DevTools 来调试和分析你的 Web 应用程序的性能和行为（甚至可以用来自动化操作 Chrome）。Addy 在文章中很好地解释了这项技术的潜力。

**长按识别二维码查看原文**

https://addyosmani.com/blog/devtools-mcp/

Addy Osmani

**GitHub 发布更安全的 npm 供应链计划** —— 针对最近几周发生的 npm 生态系统供应链攻击，GitHub 安全研究高级总监详细介绍了 GitHub 采取的应对措施，包括：阻止上传带有最近恶意软件特征的包、加强包发布安全性，以及推广使用可信发布机制。

**长按识别二维码查看原文**

https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/

Xavier René-Corail（GitHub）

**快讯：**

- Netscape Navigator 2.0 Beta 发布 30 周年 —— 这是第一个支持 JavaScript 的浏览器。
    
    **长按识别二维码查看原文**
    
    https://www.jwz.org/blog/2025/09/netscape-navigator-2-0-was-released-30-years-ago-today/
    

- 本周 TC39 会议议程中多个提案取得进展，包括 Import Bytes、Iterator Chunking 和 `Array.prototype.pushAll`。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/agendas/blob/main/2025/09.md
    

- Chrome 团队预计 Chrome/Chromium 对 Temporal API 的支持将在 Chromium 144 版本中落地（当前稳定版本是 140）。
    
    **长按识别二维码查看原文**
    
    https://chromestatus.com/feature/5668291307634688
    

- InfoQ 分享了轻量级 React 替代方案 Preact 11 beta 版本的新特性更新。
    
    **长按识别二维码查看原文**
    
    https://www.infoq.com/news/2025/09/preact-11-beta/
    

- IEEE 发布了 2025 年度编程语言排行榜，JavaScript 和 TypeScript 分别位列第 6 和第 7 名。
    
    **长按识别二维码查看原文**
    
    https://spectrum.ieee.org/top-programming-languages-2025
    

📖 文章与视频

**从 Steam 到软盘：将现代 TypeScript 移植到 DOS 系统上运行** —— 一款受 DOS 启发的编程游戏（在 Steam 上可购买）的开发者尝试让游戏在真实的 DOS 系统上运行。借助 jSH（一个用于 DOS 的 JavaScript 引擎）的帮助，这个想法勉强实现了。

**长按识别二维码查看原文**

https://jimb.ly/2025/09/23/qauntumpulse-from-steam-to-floppy/

Jimbly / Dashing Strike

**npm 安全最佳实践** —— 一份详尽的最佳实践、技巧和建议清单，帮助你更安全地使用 npm 包管理生态系统及其工具。

**长按识别二维码查看原文**

https://github.com/bodadotsh/npm-security-best-practices

Boda

**JSON 在不同编程语言中并非完全一致** —— 如果你使用 JSON 在不同编程语言构建的系统之间通信，请务必小心。不同库的实现差异可能会导致”一些最令人崩溃的调试经历”。

**长按识别二维码查看原文**

https://blog.dochia.dev/blog/json-isnt-json/

Dochia CLI

**📄 别再用** `**.reverse().find()**` **了：来试试** `**findLast()**` Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/09/22/stop-using-reverse-find-meet-findlast/

**📄 在 JavaScript** `**BigInt**` **中存储大量数据的探索** Jonathan Frere

**长按识别二维码查看原文**

https://jonathan-frere.com/posts/bigints-are-cool/

**🎤 让桌面框架更易访问：Electron 专题访谈** —— 一段 20 分钟的对话，采访了一位资深 Electron 维护者。The GitHub Podcast

**长按识别二维码查看原文**

https://the-github-podcast.simplecast.com/episodes/making-desktop-frameworks-more-accessible-with-electron

**📄 使用 Three.js 和 GSAP 创建炫酷的 Web 动画** —— 一个简单的示例。Michael Li

**长按识别二维码查看原文**

https://spin.atomicobject.com/animations-threejs-gsap/

**📄 如何使用 Cypress 测试新的 ARIA Notify API** Mark Noonan

**长按识别二维码查看原文**

https://www.cypress.io/blog/how-to-test-the-new-a-notify-api-with-cypress

🛠 代码与工具

**🤖 GitHub Copilot CLI 进入公开预览阶段** —— 为了不让 Claude Code 和 OpenAI Codex 独占命令行开发助手市场，GitHub 发布了基于 Node 构建的命令行版 Copilot。

**长按识别二维码查看原文**

https://github.blog/changelog/2025-09-25-github-copilot-cli-is-now-in-public-preview/

GitHub

**TanStack Start v1 发布候选版本** —— TanStack 推出的基于 TanStack Router 的全栈框架已发布 v1.0 候选版本，预计与最终的 1.0 版本基本一致。这是”构建类型安全、高性能 React 应用程序的新篇章，无需繁重的抽象层”。

**长按识别二维码查看原文**

https://tanstack.com/blog/announcing-tanstack-start-v1

Tanner Linsley

**Cap’n Web：一个全新的浏览器和 Web 服务器 RPC 系统** —— 这是 Cap’n Proto 的”精神续作”，由同一作者开发。不同的是，Cap’n Web 的底层序列化是人类可读的，专注于与 JS 运行时的良好集成，并且开箱即支持 HTTP、WebSocket 和 `postMessage()`。

**长按识别二维码查看原文**

https://blog.cloudflare.com/capnweb-javascript-rpc-library/

Varda 和 Faulkner（Cloudflare）

**eslint-plugin-react-you-might-not-need-an-effect** —— 这个项目名字真是够长的！这是一个 ESLint 插件，帮助 React 开发者发现不必要的 `useEffect` 使用，因为这种情况相当常见。

**长按识别二维码查看原文**

https://github.com/NickvanDyke/eslint-plugin-react-you-might-not-need-an-effect

Nick van Dyke

🧐 跟随 Dr. Axel 学习 Web 开发

在过去几个月里，备受尊敬的 Dr. Axel Rauschmayer 一直在编写一系列面向初学者的文章，涵盖了各种 Web 开发主题，特别关注 JavaScript。他将这个系列定位为”教会从未编程的人如何使用 JavaScript 创建 Web 应用程序”。

**长按识别二维码查看原文**

https://2ality.com/archive.html\#Tag=learning%20web%20dev

这些都是很棒的入门/复习材料，非常适合分享给刚开始 Web 开发之旅的朋友。以下是目前的一些精选内容：

- 学习数字、变量和函数，以及字符串和方法。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/08/javascript-numbers-variables-functions.html
    

- 布尔值、比较和 `if` 语句以及循环。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/08/javascript-booleans-comparisons-if.html
    

- 深入了解普通对象、`Array`、`Map`和异常处理。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/08/javascript-plain-objects.html
    

- 使用 Preact 入门前端框架。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/09/frontend-frameworks.html
    

- 安装 npm 包和打包。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/09/npm-packages-bundling.html
    

- Promise 和 `async` 函数。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/09/javascript-async.html
    

P.S. **别掉进 JSON 瀑布…**

**长按识别二维码查看原文**

https://dontgojsonwaterfalls.com/

**版本发布：**

- **pnpm v10.17** —— 新的 `minimumReleaseAgeExclude` 现在支持使用模式来排除包组，使其不受最小发布时间检查的限制。

- **Astro v5.14** —— 带来了”一大波令人心动的新特性和开发体验改进”。

- *Node.js v24.9.0（当前版本）**和 **v22.20.0（LTS）**

- **Nuxt UI v4.0**、**PostgreSQL 18.0**、**ESLint v9.36.0**

- **📊 Billboard.js v3.17.0（上图）** —— 这个流行的图表库新增了图表图像标签支持、标签边框样式和标签颜色的动态控制。

- **PythonMonkey v1.3** —— 将 SpiderMonkey JS 引擎嵌入 Python 虚拟机，现已支持 Python 3.14。

- **pretty-bytes v7.1** —— 将字节大小转换为人类可读的格式（例如 1337 转换为 “1.34 kB”）。

- **Docusaurus v3.9** —— 流行的基于 React + MDX 的内容/文档站点生成器。

- **Neo.mjs v10.9** —— 用于构建快速、桌面级 Web 应用程序的多线程框架。

- **eslint-plugin-vue v10.5** —— Vue.js 官方 ESLint 插件。（主页）

- **VanJS v1.6** —— 小巧而优雅的响应式 UI 框架。（主页）

- **Milkdown v7.16** —— 插件驱动的所见即所得 Markdown 编辑器框架。