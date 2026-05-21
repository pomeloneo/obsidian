# JavaScript 中文周刊 #217 - JavaScript 打包器速度战结束，体积优化成新战场

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545241&idx=1&sn=9cd9c6cb5d25edef27ca22c4fdf8f90d&chksm=e9217a7bde56f36d73c38eb710751c34d77ba26ad5cecfe2bbe3e5ca483cf3b174cc69a0b465#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545241&idx=1&sn=9cd9c6cb5d25edef27ca22c4fdf8f90d&chksm=e9217a7bde56f36d73c38eb710751c34d77ba26ad5cecfe2bbe3e5ca483cf3b174cc69a0b465#rd)

> 抓取时间: 2026/2/2 23:49:21

---

> 本期看点：JavaScript 打包器竞争转向打包产物体积和代码质量优化，Dan Abramov 发布 RSC Explorer 工具深入探索 RSC，2025 年 Top 10 精选链接回顾年度最佳内容。

> 编辑：TimLi

🔥 本周热门

**JavaScript 打包器大奖赛** —— 现在，各类打包器已经成为很多 JavaScript 工作流程的核心，甚至有时候直接内置进运行时了（比如 Bun 的打包器）。这篇文章带你全方位了解打包领域的发展，现在速度大战已经接近终局，真正的竞争已经转向了打包产物的体积以及最终交付到用户手里的代码质量。

**长按识别二维码查看原文**

[https://redmonk.com/kholterhoff/2025/12/16/javascript-bundler-grand-prix/](https://redmonk.com/kholterhoff/2025/12/16/javascript-bundler-grand-prix/)

Kate Holterhoff

**"我用 LLMs 把 JustHTML 从 Python 移植到 JavaScript，只花了 4.5 小时"** —— 高产的 AI 博主 Simon Willison 分享了用 OpenAI 的 Codex CLI 和 GPT 5.2，把一个通过全部 html5lib-tests 标准的 HTML5 解析器，从 Python 移植到 JavaScript 的整个过程。这套解析器不仅通过了 9200 多条标准测试，你还可以直接 在线体验或者查看代码。

**长按识别二维码查看原文**

[https://simonwillison.net/2025/Dec/15/porting-justhtml/](https://simonwillison.net/2025/Dec/15/porting-justhtml/)

Simon Willison

**快讯：**

- 🛠️ Dan Abramov 展示了他的新工具"RSC Explorer"，可以让你深入了解 React Server Components 的内部运行机制。
    
    **长按识别二维码查看原文**
    
    [https://overreacted.io/introducing-rsc-explorer/](https://overreacted.io/introducing-rsc-explorer/)
    

- Cloudflare Workers 的 **Wrangler** 工具现在已经支持自动配置，可以用多种 Web 框架一键部署应用程序，比如 Next.js、Astro、TanStack Start、SvelteKit、Nuxt 等。
    
    **长按识别二维码查看原文**
    
    [https://developers.cloudflare.com/changelog/2025-12-16-wrangler-autoconfig/](https://developers.cloudflare.com/changelog/2025-12-16-wrangler-autoconfig/)
    

- picknplace.js 给拖拽交互这种老话题带来了新玩法。
    
    **长按识别二维码查看原文**
    
    [https://jgthms.com/picknplace.js/](https://jgthms.com/picknplace.js/)
    

- 🤖 OpenAI 发布了全新的 GPT 5.2 Codex 模型，并且还帮安全研究者发现了两个 React 的新漏洞。
    
    **长按识别二维码查看原文**
    
    [https://javascriptweekly.com/link/178707/web](https://javascriptweekly.com/link/178707/web)
    

🏆 2025 年 Top 10 精选链接

1. **一个让人困惑的 JavaScript 解析难题** —— Hillel 只用了 14 个字节的代码，设计了今年最火的小谜题。很多玩了多年的 JavaScript 老手都答错了，包括我在内！
    
    **长按识别二维码查看原文**
    
    [https://www.hillelwayne.com/post/javascript-puzzle/](https://www.hillelwayne.com/post/javascript-puzzle/)
    

Hillel Wayne

1. **Ecma International 批准 ECMAScript 2025：有哪些新东西？** —— Ecma 每年都会正式通过最新的 ECMAScript 语言规范。今年你可以直接查阅 ES2025 的完整标准文档，或者看看 Dr. Axel 的简明解读，省时又高效。
    
    **长按识别二维码查看原文**
    
    [https://2ality.com/2025/06/ecmascript-2025.html](https://2ality.com/2025/06/ecmascript-2025.html)
    

Dr. Axel Rauschmayer

1. **"我发现 Generator 用起来越来越顺手了"** —— 如果你没怎么玩过 generator 函数，这篇文章很适合入门，作者还分享了自己的看法："其实 Generator 的实用性还没被大家真正认可呢，得慢慢来……"
    
    **长按识别二维码查看原文**
    
    [https://macarthur.me/posts/generators/](https://macarthur.me/posts/generators/)
    

Alex MacArthur

1. **Web 世界中，大家都怎么用 JavaScript？** —— 今年的 HTTP Archive《Web Almanac》深入分析了 JS 的使用现状，包括 TypeScript 的流行趋势、Web Worker 的普及度、甚至 jQuery 依然还在江湖独领风骚！
    
    **长按识别二维码查看原文**
    
    [https://almanac.httparchive.org/en/2024/javascript](https://almanac.httparchive.org/en/2024/javascript)
    

HTTP Archive

1. **2025 年每个 JS 开发者都该知道的一些特性** —— 这是一篇速读清单，快速带你扫一遍今年特别有用的特性，比如迭代器助手、`structuredClone()`、集合操作等。
    
    **长按识别二维码查看原文**
    
    [https://waspdev.com/articles/2025-04-06/features-that-every-js-developer-must-know-in-2025](https://waspdev.com/articles/2025-04-06/features-that-every-js-developer-must-know-in-2025)
    

Suren Enfiajyan

1. **如何优雅维护** `**package.json**` —— 分享了依赖管理的好习惯，以及超实用的工具推荐，让你的项目不再混乱。
    
    **长按识别二维码查看原文**
    
    [https://blog.val.town/gardening-dependencies](https://blog.val.town/gardening-dependencies)
    

1. **JavaScript 简史** —— 这份史诗级时间线盘点了 JavaScript 的历史，现在和将来都值得收藏。
    
    **长按识别二维码查看原文**
    
    [https://deno.com/blog/history-of-javascript](https://deno.com/blog/history-of-javascript)
    

1. **Debug 故事：我经历过的最难调试的 Bug** —— 一位前 Google Docs 工程师回忆十年前遇到的一个古怪 bug，真的是让人头疼又难忘。
    
    **长按识别二维码查看原文**
    
    [https://www.clientserver.dev/p/war-story-the-hardest-bug-i-ever](https://www.clientserver.dev/p/war-story-the-hardest-bug-i-ever)
    

1. **大家对 Electron 总有误解** —— Electron 维护者现身说法，解释了这些年来项目背后的技术选择。
    
    **长按识别二维码查看原文**
    
    [https://felixrieseberg.com/things-people-get-wrong-about-electron/](https://felixrieseberg.com/things-people-get-wrong-about-electron/)
    

1. **是时候全面拥抱 ESM 了** —— 你可以同时维护 ESM 和 CommonJS，但 Anthony 解释了为啥现在终于该转向纯 ESM 时代了。
    
    **长按识别二维码查看原文**
    
    [https://antfu.me/posts/move-on-to-esm-only](https://antfu.me/posts/move-on-to-esm-only)
    

🗓️ 2025 年 JavaScript 月度大事记

咱们一起梳理一下 2025 年，每个月 JavaScript 领域都发生了哪些大事吧：

**一月——** 今年刚开年，Bun 作为 JS 新秀运行时，就带来了 Bun 1.2 的重大升级。同时 Express.js 也公布了新进展。

**长按识别二维码查看原文**

[https://bun.sh/blog/bun-v1.2](https://bun.sh/blog/bun-v1.2)

**二月——**Angular 纪录片 上线了，备受好评。与此同时，Deno 和 Oracle 的 JavaScript 商标之争打得火热。TypeScript 5.8 发布，特别让 Node 开发者兴奋。顺带一提，有人居然用 TypeScript 类型系统实现了 Doom，真是脑洞大开。

**长按识别二维码查看原文**

[https://www.youtube.com/watch?v=cRC9DlH45lA](https://www.youtube.com/watch?v=cRC9DlH45lA)

**三月——**Babylon.js 8.0（微软的 3D 引擎）和 Express 5.1 正式发布。

**长按识别二维码查看原文**

[https://blogs.windows.com/windowsdeveloper/2025/03/27/announcing-babylon-js-8-0/](https://blogs.windows.com/windowsdeveloper/2025/03/27/announcing-babylon-js-8-0/)

**四月——**Koa 3.0 发布，Node.js 全球协作峰会 在巴黎举行，p5.js 2.0 也同步上线。

**长按识别二维码查看原文**

[https://koajs.com/](https://koajs.com/)

**五月——** Remix 项目迎来巨大变动；GSAP 动画工具宣布免费开放；Glitch 平台正式关停。Deno 团队制作了详细的 JavaScript 历史时间线，而微软首次预览了 Go 版原生编译的 TypeScript。

**长按识别二维码查看原文**

[https://remix.run/blog/wake-up-remix](https://remix.run/blog/wake-up-remix)

**六月——**Oxlint 1.0 和 Vite 7.0 发布。Dr. Axel 推出最新的《Exploring JavaScript》ES2025 版本。Biome v2 成为首个不用 `tsc`，却能感知类型的 JavaScript linter。Ecma 也 正式通过 ECMAScript 2025 标准。

**长按识别二维码查看原文**

[https://voidzero.dev/posts/announcing-oxlint-1-stable](https://voidzero.dev/posts/announcing-oxlint-1-stable)

**七月——**JS1024 代码高尔夫大赛举办。Deno 2.4 上线，Vercel 收购了 NuxtLabs。

**长按识别二维码查看原文**

[https://javascriptweekly.com/link/178749/web](https://javascriptweekly.com/link/178749/web)

**八月——**TypeScript 5.9 和 Apache Echarts 6 发布。jQuery 团队也发布了 jQuery 4.0 的候选版本，只不过正式版还得再等一等。

**长按识别二维码查看原文**

[https://devblogs.microsoft.com/typescript/announcing-typescript-5-9/](https://devblogs.microsoft.com/typescript/announcing-typescript-5-9/)

**九月——**Mediabunny 给媒体处理带来新玩法。Chrome 度过了自己 17 岁生日。接下来 npm 包安全领域经历了多事之秋——多款包在钓鱼攻击中被攻陷。pnpm 也推出了延迟依赖更新的支持。用 macOS Tahoe 的同学发现，Electron 应用程序居然会变卡，问题还和操作系统的私有 API 相关。Deno 项目组还向社区筹款 20 万美元维权 JavaScript 商标案。

**长按识别二维码查看原文**

[https://mediabunny.dev/](https://mediabunny.dev/)

**十月——**React Compiler v1.0 和 Node.js v25.0 发布。Node.js 24 成为全新 LTS 版本。React 团队宣布成立 React Foundation，以降低对 Meta 的依赖。Bun 1.3 热闹登场，Evan You 也发布了 Vite+。GitHub 官宣 TypeScript 成为平台上最火语言。

**长按识别二维码查看原文**

[https://react.dev/blog/2025/10/07/react-compiler-1](https://react.dev/blog/2025/10/07/react-compiler-1)

**十一月——** 传说中的 Shai Hulud 供应链攻击，以"2.0 版"的形式又冒头了。JavaScript Engines Zoo 上线，让大家见识到 JS 运行时和引擎的多样性。Google 发布了 Angular v21。

**长按识别二维码查看原文**

[https://about.gitlab.com/blog/gitlab-discovers-widespread-npm-supply-chain-attack/](https://about.gitlab.com/blog/gitlab-discovers-widespread-npm-supply-chain-attack/)

**十二月——**JavaScript 正式 30 岁啦！ 微软公布了 TypeScript 7.0 的最新进展，Deno 2.6 也同步发布。Node.js v24.12.0 (LTS) 终于实现了类型剥离功能的 LTS 稳定上线。

**长按识别二维码查看原文**

[https://javascriptweekly.com/issues/764](https://javascriptweekly.com/issues/764)

**版本发布：**

- **Tesseract.js v7.0** —— OCR 识别库，图片提取文字速度更快。

- **Base UI v1.0** —— 新一代团队力推的高颜值 React 组件库。

- **Wasp v0.20** —— 专为 React 19、Node 和 Prisma 打造的 Rails 风格框架。

- **Graffle v7.4** —— 可以任意环境运行的 JavaScript GraphQL 客户端。

- **Next.js v16.1**，**Bun v1.3.5**，**MathJax v4.1**，**Prisma v7.2**