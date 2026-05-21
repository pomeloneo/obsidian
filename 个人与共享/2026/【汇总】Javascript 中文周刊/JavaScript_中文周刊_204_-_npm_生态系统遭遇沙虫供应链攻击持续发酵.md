# JavaScript 中文周刊 #204 - npm 生态系统遭遇”沙虫”供应链攻击持续发酵

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543734&idx=1&sn=6595ca650ef0782ee357e523535395ca&chksm=e9216054de56e94232bd7287451cf1e4d26d02f96a2757f30b13a5a243199c4f48ed3339746a\#rd  
> 抓取时间: 2026/2/2 23:49:41

---

> 本期看点：npm 生态系统遭遇”沙虫”供应链攻击已影响数百个包，WebAssembly 3.0 标准正式发布并新增多项 JavaScript 互操作性特性，尤雨溪最新采访出炉，以及离线 MDN 文档下载地址。

> 编辑：TimLi

🔥 本周热点

**npm 生态系统遭遇”沙虫”供应链攻击持续发酵** —— 这次攻击以《沙丘》小说中的沙虫命名。这场针对 npm 生态系统的恶意供应链攻击规模不断扩大，已影响数百个包，攻击者试图从开发者的机器上窃取令牌和密钥。

**长按识别二维码查看原文**

https://socket.dev/blog/ongoing-supply-chain-attack-targets-crowdstrike-npm-packages

Pandya、van der Zee 和 Brown（Socket）

这一事件引发了一系列回应和应对措施：

- pnpm 10.16 发布，新增了 `minimumReleaseAge` 选项来延迟依赖更新——这里有详细说明。预计未来会有更多工具采用类似功能。
    
    **长按识别二维码查看原文**
    
    https://pnpm.io/blog/releases/10.16
    

- Tane Piper 在《关于 npm 供应链攻击的思考》中指出了微软在其中的责任。
    
    **长按识别二维码查看原文**
    
    https://tane.dev/2025/09/oh-no-not-again…-a-meditation-on-npm-supply-chain-attacks/
    

- Drew DeVault 探讨了一个”不太可能实现”的 JavaScript 美好未来，重点关注改善现状所需的系统性变革。
    
    **长按识别二维码查看原文**
    
    https://drewdevault.com/2025/09/17/2025-09-17-An-impossible-future-for-JS.html
    

**⚖️ Deno 发起众筹：帮我们筹集 20 万美元从 Oracle 手中解放 JavaScript** —— JavaScript™ 实际上是 Oracle 的商标，但 Ryan Dahl 和 Deno 团队正在发起挑战，希望筹集资金完成商标撤销申请的关键发现阶段。

**长按识别二维码查看原文**

https://deno.com/blog/javascript-tm-gofundme

Ryan Dahl（Deno）

**快讯：**

- WebAssembly 3.0 标准正式发布（大多数浏览器已支持），新增多项改进 JavaScript 互操作性的特性，包括垃圾回收、尾调用、异常处理以及直接操作 JavaScript 字符串的方法。
    
    **长按识别二维码查看原文**
    
    https://webassembly.org/news/2025-09-17-wasm-3.0/
    

- ▶️ Vue 作者 Evan You 近期接受了 Laravel 项目的 Nuno Maduro 采访，谈及他在 Google 的经历、Vue.js 的诞生过程、Next.js 与 Nuxt 的关系，以及他目前在 void(0) 的工作。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=FS0Ds0nIC8E
    

- 我们最近提到了最新的 JavaScript 运行时 Andromeda，现在又出现了 Ion，这是一个旨在将 JavaScript 引擎引入 Rust 程序的运行时。
    
    **长按识别二维码查看原文**
    
    https://tryandromeda.dev/
    

- Webflow 向 Astro 项目捐赠了 15 万美元。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/webflow-official-partner/
    

📖 文章

**Fetch 流很棒，但不适合测量上传/下载进度** —— Fetch 上传流看似很适合跟踪上传进度，但正如 Jake 指出的，“数据从流中被读取并不意味着它已经通过网络发送”。他还讨论了使用响应流测量下载进度时的相关问题。

**长按识别二维码查看原文**

https://jakearchibald.com/2025/fetch-streams-not-for-progress/

Jake Archibald

**告别 TypeScript（我们爱你，TypeScript）** —— 一个有趣的故事：一个工程团队决定放弃他们 250 万行的 TypeScript 代码，转而使用 .NET 和 C\#。不过他们的前端仍将保留 React。

**长按识别二维码查看原文**

https://engineering.usemotion.com/moving-off-of-typescript-e7bb1f3ad091?gi=582c3b850ad7

Chander Ramesh

**React 已成为默认选择——这正在扼杀前端创新** —— 这篇观点鲜明的文章本周引发了广泛讨论，它指出了”React 默认选择”思维模式带来的弊端和惯性。

**长按识别二维码查看原文**

https://www.lorenstew.art/blog/react-won-by-default

Loren Stewart

**📄 展望未来：Angular 如何拥抱 AI 打造下一代应用程序** —— 来自 Angular 团队的最新动态。Simona Cotin（Angular）

**长按识别二维码查看原文**

https://blog.angular.dev/beyond-the-horizon-how-angular-is-embracing-ai-for-next-gen-apps-7a7ed706e1a3?gi=c9d536311441

**📄 Solid.js vs React：开发者视角** —— “Solid 让我耳目一新，它让我看到了 React 可能达到但可能永远不会达到的境界。” Alem Tuzlak

**长按识别二维码查看原文**

https://javascriptweekly.com/link/174555/web

**📄 使用 React Three Fiber 创建沉浸式 3D 天气可视化** Carter Rink

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/09/18/creating-an-immersive-3d-weather-visualization-with-react-three-fiber/

🛠 代码与工具

**npm-check-updates v18.2：将** `**package.json**` **依赖更新到最新版本** —— 这个工具可以帮你更新到最新版本，而不是指定版本。它包含一个方便的 `-i` 交互模式，让你可以逐个查看和选择要更新的包。**v18.2 新增了”冷却期”功能来防范供应链攻击**，要求包版本发布至少指定天数后才考虑更新。

**长按识别二维码查看原文**

https://github.com/raineorshine/npm-check-updates

Raine Revere

**Expo SDK 54 发布：React Native 开发者的重大更新** —— Expo 框架在 React Native 领域继续快速发展。新版本带来了预编译的 React Native iOS 构建（大幅缩短构建时间）、iOS 26 和 Liquid Glass 支持，并使用了 React Native 0.81 和 React 19.1。新的 Expo File System 也已经稳定。

**长按识别二维码查看原文**

https://expo.dev/changelog/sdk-54

Hughes 和 Vatne（Expo）

**🦋 BlueSky Likes：灵活的 Bluesky 点赞显示组件** —— 包含两个自定义元素组件：`bluesky-likes` 和 `bluesky-likers`，分别用于显示点赞数量和点赞者头像组。在线演示。

**长按识别二维码查看原文**

https://github.com/LeaVerou/bluesky-likes

Lea Verou

**Svedit：用 Svelte 构建富文本编辑器的轻量级库** —— 让你可以用 JSON 建模内容，用自定义 Svelte 组件渲染，并直接在布局中编辑。GitHub 仓库。

**长按识别二维码查看原文**

https://svedit.vercel.app/

Michael Aufreiter

🎁 小彩蛋

- IINA 是 macOS 上流行的开源媒体播放器，它刚刚添加了基于 JavaScript 的插件系统，让用户可以扩展其功能。
    
    **长按识别二维码查看原文**
    
    https://iina.io/
    

- 哪个 npm 包的版本号最大？一位开发者借助 Bun 和 npm 注册表数据，满足了自己的好奇心，发现了多个”赢家”（取决于你如何定义”版本”和”最大”）。
    
    **长按识别二维码查看原文**
    
    https://adamhl.dev/blog/largest-number-in-npm-package/
    

- 📂 想离线参考 MDN 文档？Dash macOS 文档浏览器的创建者分享了 MDN 文档的存档文件，涵盖 JavaScript、CSS、HTML 和 SVG 等领域。
    
    **长按识别二维码查看原文**
    
    https://kapeli.com/mdn_offline
    

- Bocoup 的 Mike Pennisi 讨论了网络上最被容忍的特性（却常被忽视），即 `zoom` CSS 属性。
    
    **长按识别二维码查看原文**
    
    https://www.bocoup.com/blog/the-webs-most-tolerated-feature
    

**版本发布：**

- **Safari v26.0 发布**，随 macOS 26.0、iOS 26.0 等一起推出。除了众多 CSS 增强功能和用于嵌入 3D 模型的新 `<model>` 元素外，现在所有网站都可以在用户将其添加到主屏幕时成为 iOS 和 iPadOS 上的”网络应用程序”。

- **Bun v1.2.22** —— 堆栈跟踪现在包含异步调用帧，新增 `Bun.YAML.stringify` 用于将对象转换为 YAML，打包器和压缩器也有改进。

- React Router 7.9.0 中，期待已久的中间件功能终于稳定了。

- **TypeBox v1.0** —— 一个运行时类型系统，可创建推断为 TypeScript 类型的内存 JSON Schema 对象。

- 🙂 **Vue Frimousse v0.1.3** —— Vue 的无样式、可组合表情选择器。

- **wait-on v9.0** —— CLI 工具和 Node API，用于等待文件、端口、套接字和 http(s) 资源可用。

- 🗓️ **DayPicker v9.10** —— React 日期选择器、日历和日期输入组件。

- **Wasp v0.18** —— Wasp 是一个类似 Rails 的框架，使用 Node、React 和 Prisma。

- **pretty-ms v9.3** —— 将毫秒转换为人类可读的字符串。

- **npm-publish v4.0** —— 用于发布 npm 包的 GitHub Action。

- **Hexo v8.0** —— 流行的博客框架/生成器。

- **Fresh v2.1** —— 基于 Deno 的 Web 框架。