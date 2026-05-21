# JavaScript 中文周刊 #216 - 构建 HTML 工具的实用模式

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545115&idx=1&sn=79b3bd27778e1a57fb8de018a9600ec7&chksm=e9217af9de56f3eff8ec9f9cec132711555ee95dca60cdea136264898e785d2012440163d55a\#rd  
> 抓取时间: 2026/2/2 23:49:23

---

> 本期看点：有些工具你不需要用完整框架写，HTML、JavaScript 和 CSS 单文件就很够用，Deno v2.6 发布带来全新 dx 工具和 deno audit 安全检测，React Server Components 又发现两枚安全漏洞，Remix 商店开源。

> 编辑： TimLi

🔥 本周热门

**构建 HTML 工具的实用模式** —— 其实很多时候，打造有用的小工具没必要用上完整框架，只用 HTML、JavaScript 和 CSS 做成一个单文件就很够用。Simon 是这方面的高手，已经用 LLM 搞出过一堆类似工具，这篇文章他详细讲了自己的方法和思路，内容干货十足，强烈推荐！

**长按识别二维码查看原文**

https://simonwillison.net/2025/Dec/10/html-tools/

Simon Willison

**Deno v2.6 发布** —— Deno 这个流行的 Node.js 替代运行时，推出了一个全新的 `npx` 类工具 `dx`，可以直接运行来自 npm 和 JSR 的二进制包，还加入了 `deno audit` 工具，可以检测依赖中的安全隐患。另外还带来了更细致的运行时权限控制和 source phase imports 等新特性。

**长按识别二维码查看原文**

https://deno.com/blog/v2.6

Iwańczuk 和 Jiang（Deno 团队）

**快讯：**

- ⚠️ React Server Components 又爆出两枚安全漏洞，和上周的 React2Shell 事件不一样，是新发现的问题。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2025/12/11/denial-of-service-and-source-code-exposure-in-react-server-components
    

- 🔒 GitHub 更新 npm token 政策。 这周所有旧版 npm 经典 token 已经被撤销，现在可以用两小时的 session token 或者更细粒度的 access token 替代。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-12-09-npm-classic-tokens-revoked-session-based-auth-and-cli-token-management-now-available/
    

- 🕒 Chrome 144 Beta 出来了，带来了对 Temporal API 的支持，处理日期和时间更加方便。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/chrome-144-beta?hl=zh
    

- 微软发布了 VS Code 的 **JavaScript/TypeScript Modernizer** 预览版，它能帮你分析项目并给出升级语法和依赖的建议，适合老项目技术升级。
    
    **长按识别二维码查看原文**
    
    https://developer.microsoft.com/blog/jsts-modernizer-preview
    

- Oxlint 推出支持类型感知的 lint 功能，目前还是 alpha 版。
    
    **长按识别二维码查看原文**
    
    https://oxc.rs/blog/2025-12-08-type-aware-alpha
    

📖 文章和视频

**西雅图时报如何防御 npm 供应链攻击** —— 这篇文章介绍了 **Seattle Times** 如何采用 pnpm 替换 `npm`，加强客户端安全控制，里面有不少技术细节，值得一看。

**长按识别二维码查看原文**

https://pnpm.io/blog/2025/12/05/newsroom-npm-supply-chain-security

Ryan Sobol

**让复杂 Web 应用程序更快的提案** —— 微软团队带来的新想法，Delayed Message Timing API，可以解决多个嵌套上下文（比如 iframes、线程、多窗口等）导致的性能拖慢问题。现阶段还在征集反馈。

**长按识别二维码查看原文**

https://blogs.windows.com/msedgedev/2025/12/09/making-complex-web-apps-faster/

Joone Hur & Patrick Brosset（微软）

**用 JavaScript 自己造个 2D 物理引擎** —— 文章很复古，作者手把手教你用 JavaScript 造一个简单物理引擎，最后还把代码精简到 2KB，可以在这里试玩。

**长按识别二维码查看原文**

https://xem.github.io/articles/2D-physics.html

Maxime Euzière

**📄 Canvas 上实现跨浏览器非阻塞图片渲染** —— 提高用户体验和页面响应速度的技巧，特别适合对图片渲染要求高的场景。Alexander Myshov

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2025/non-blocking-image-canvas/

**📄** Prelude of the Chambered **重制：经典 Java 游戏用 TypeScript 实现** —— 移植 Minecraft 创作者当年在 **Ludum Dare** 比赛做过的 Java 游戏。Angelo Lima

**长按识别二维码查看原文**

https://angelo-lima.fr/en/prelude-of-the-chambered-reborn-typescript-web-port/

**📄 Angular 技巧** —— 一个专门讲大规模 Angular 应用程序最佳实践的文档站点。Martin Boué

**长按识别二维码查看原文**

https://ngtips.com/

🛠️ 代码和工具

**Remix 商店开源啦** —— Remix Store 是 Remix 项目的官方周边商店，它本身的代码就是 Remix 团队用 Remix 搞出的精彩案例，还用上了 Hydrogen，想学 Remix 的同学不要错过。

**长按识别二维码查看原文**

https://remix.run/blog/oss-remix-store

Brooks Lybrand 和 Remix 团队

💡 你不用是真正的 Remix 用户，也能从这些代码中得到启发。比如商店那个 ‘glitchy’ 404 页 的代码就在这里，可以直接拿来用或魔改成你自己的。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/178438/web

**🕒** `**<relative-time>**` **5.0：把时间戳格式化为更自然的相对时间显示** —— 这个 web 组件给你一个标准的日期时间，它就能自动渲染成“2 天前”这种格式。GitHub 在所有代码库和 PR 页面都在用这东西。

**长按识别二维码查看原文**

https://github.com/github/relative-time-element

GitHub

**ts-exec：用 SWC 在 Node 上跑 TypeScript** —— Adonis 作者带来的新工具，用于在 Node 上运行 TypeScript。Node 22.18 以后支持了 type stripping，不过 `ts-exec` 还能支持 JSX、装饰器等，和 `ts-node`、`tsx` 相比有自己的优点，详细对比见这里。

**长按识别二维码查看原文**

https://github.com/poppinss/ts-exec

Harminder Virk

**Toastflow：Vue 3 的 Toast 通知库** —— 这是个超级好玩的 toast 通知 playground，能在线试效果，多希望其它项目也有这样的功能。虽然 Toastflow 理论上支持多框架，但目前只有 Vue 3 渲染器。GitHub 地址在这。

**长按识别二维码查看原文**

https://toastflow.adrianjanocko.sk/

Adrián Janočko

**Devalue：JSON.stringify 搞不定的，它能行** —— 来自 Svelte 项目组的小巧库，和 `JSON.stringify` 类似，但能支持循环引用、重复引用、正则、`Map`、`Set`、甚至自定义类型。点这里可以在线体验。

**长按识别二维码查看原文**

https://github.com/sveltejs/devalue

Svelte

**iceberg-js：Apache Iceberg 的 JavaScript 客户端** —— 这是为 Apache Iceberg REST Catalog API 设计的极简、跨环境 JavaScript 客户端，只要你有 Iceberg 数据目录，无论啥环境都能跑。

**长按识别二维码查看原文**

https://supabase.com/blog/introducing-iceberg-js

Katerina Skroumpelou（Supabase）

📢 生态系统其他有趣的内容

放点最近圈里的各种新鲜事：

- 📺 今年早些时候，Dimitri Mitropoulos 曾让大家大开眼界：他在 TypeScript 的类型系统里跑 Doom。现在他又带来了 ▶️ TypeSlayer，能帮你诊断并修复 TypeScript 性能问题，配有很炫的 3D 可视化。效果爆炸，可惜还没公开上线。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=IP6EZXzXBzY
    

- Chrome 团队有个CSS Wrapped 2025，回顾了今年 CSS 世界的大变化，带你极速了解最新发展。
    
    **长按识别二维码查看原文**
    
    https://chrome.dev/css-wrapped-2025/
    

- GitHub 公布了一些 GitHub Actions 平台相关的更新，并透露 2026 年还会有新功能上线。
    
    **长按识别二维码查看原文**
    
    https://github.blog/news-insights/product-news/lets-talk-about-github-actions/
    

- 🗳️ Chrome 团队的 Rick Viscomi 在征集你希望未来网页有啥特性，欢迎 去投票。这个和 Interop 2025 投票不是一回事，官方明确会持续统计，长期有效。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/upvote-features
    

- 🤖 OpenAI 推出了新模型 GPT 5.2，大家快围观！
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/178463/web
    

**版本发布：**

- **Node.js v24.12.0 (LTS)** —— Node.js 首次在 LTS 版中把类型剥离功能标为稳定。

- **@platformatic/python-node v2.0** —— 让 Python ASGI 应用程序能在 Node.js 跑，新版支持 HTTP 响应流和双向 WebSocket。

- **Bun v1.3.4** —— 现已支持 `URLPattern`，测试框架能用可控/模拟定时器，`console.log` 也和 Node 一样支持 `%j` 占位符。

- **React v19.2.3**、**v19.1.4**、和 **v19.0.3** —— 均已发布。

- **Inertia v2.3** —— 经典服务端路由与控制器，帮你用 React、Vue、Svelte 做单页应用程序，特别适合和 Django、Rails、Laravel 等后端结合。

- **OpenPGP.js v6.3** —— JavaScript 版 OpenPGP 新发布。

- 🗓️ **React Datepicker v9.0** —— 老牌 React 日期选择器升级。

- 🎸 **SVGuitar v2.5** —— 能在线画吉他和弦指法图的 SVG 库，弹琴党必备。

- **pnpm v10.25** —— 高速又省空间的包管理器又更进一版。

- **js-tokens v10.0** —— 超迷你的 JavaScript 源码 tokenizer。