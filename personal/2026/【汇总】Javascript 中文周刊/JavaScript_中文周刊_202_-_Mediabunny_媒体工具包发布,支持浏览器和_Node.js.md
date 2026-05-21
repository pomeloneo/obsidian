# JavaScript 中文周刊 #202 - Mediabunny 媒体工具包发布,支持浏览器和 Node.js

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543505&idx=1&sn=eb155167f2d7f0083eace875a5f778aa&chksm=e9216133de56e825f3223224c7c2aa05c2b9a2b357addeba5698de87fa88562e53913356064b\#rd  
> 抓取时间: 2026/2/2 23:49:44

---

> 本期看点：Mediabunny 媒体工具包发布，支持转换格式、提取元数据、生成缩略图等功能，Ripple 全新 TypeScript UI 框架，Chrome 17 周年回顾，Peaks.js v4.0：音频波形交互 UI 组件。

> 编辑：TimLi

🔥 本周热点

**Mediabunny：完整的 JavaScript 媒体工具包** —— 这个库同时支持浏览器和 Node.js，让你可以读取、写入和转换常见的媒体文件格式（如 MP4、MP3 和更多格式），而无需依赖 FFmpeg 等工具。你可以生成缩略图、提取元数据，甚至将代码转换成视频等。GitHub 仓库。

**长按识别二维码查看原文**

https://mediabunny.dev/

Vanilagy

**为什么浏览器要限制 JavaScript 定时器？** —— 你知道吗？`setTimeout(0)` 中的零并不真的意味着”零”。浏览器会将定时器限制在至少几毫秒以上，这会降低依赖它们的代码的执行速度。不过别担心，Nolan 为我们展示和测试了一些替代方案。

**长按识别二维码查看原文**

https://nolanlawson.com/2025/08/31/why-do-browsers-throttle-javascript-timers/

Nolan Lawson

**Ripple：全新开发中的 TypeScript UI 框架** —— 这是一个新框架，旨在将 React、Solid 和 Svelte 的精华部分融合到一个包中。值得注意的是，它的作者曾参与开发 React 和 Svelte，同时也是 Lexical 和 Inferno 的作者，所以非常值得关注。更多信息可以查看GitHub 仓库。

**长按识别二维码查看原文**

https://www.ripplejs.com/

Dominic Gannaway

**快讯：**

- Viteland 8 月更新概览汇总了 Oxlint、Vite、Vitest、Rolldown 等项目的最新进展。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/whats-new-aug-2025
    

- Angular 团队发布夏季重大更新，包括无 Zone 变更检测、新动画特性、AI 集成、更好的调试功能等。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.dev/angular-summer-update-2025-1987592a0b42?gi=dd942b485e1b
    

- Thoughtbot 分享了 2025 年即将举办的 JavaScript 会议列表。
    
    **长按识别二维码查看原文**
    
    https://thoughtbot.com/blog/upcoming-javascript-and-react-conferences-for-2025
    

📖 文章与视频

**Chrome 浏览器 17 周年：一段历史回顾** —— 一篇精彩的文章，回顾了 Chrome 的起源和多年来的发展历程。Addy 介绍了关键里程碑（如多进程架构）、安全性、AI 领域的探索等内容。

**长按识别二维码查看原文**

https://addyosmani.com/blog/chrome-17th/

Addy Osmani

💡 说到 Chrome，开发者必试的 Chrome API 介绍了许多 Chrome 独有的 JavaScript API，其中大部分我都没听说过。

**长按识别二维码查看原文**

https://anchorbrowser.io/blog/top-chrome-apis-every-developer-should-try

**面向 JavaScript 开发者的** Lean **入门** —— 这是对 Lean 的全面介绍，它是一个定理证明器和用于创建形式化验证代码的语言。Dan Abramov 最近对它产生了浓厚兴趣。他说：“我从未写过这样带有证明的代码。你试过吗？”

**长按识别二维码查看原文**

https://overreacted.io/lean-for-javascript-developers/

Dan Abramov

**使用** `**Intl.Segmenter**` **获取准确的文本长度** —— 当 `.length` 返回的结果不符合预期时，这个技巧很有用。

**长按识别二维码查看原文**

https://blog.sangeeth.dev/posts/accurate-text-lengths-with-intl-segmenter-api/

Sangeeth Sudheer

**不用 XSLT 让 XML 更易读** —— Jake 用 JavaScript 巧妙地解决了这个小众问题。

**长按识别二维码查看原文**

https://jakearchibald.com/2025/making-xml-human-readable-without-xslt/

Jake Archibald

**📄 压力测试 Biome 的** `**noFloatingPromises**` **检查规则** Dimitri Mitropoulos (Vercel)

**长按识别二维码查看原文**

https://vercel.com/blog/stress-testing-biomes-nofloatingpromises-lint-rule

**📄 如何用 Web Workers 和 Partytown 优化第三方脚本** Jakub Andrzejewski

**长按识别二维码查看原文**

https://www.debugbear.com/blog/partytown-web-workers

**📄 不用 React 的 Redux：在原生 JS 中的状态管理** Moritz Kröger

**长按识别二维码查看原文**

https://javascriptweekly.com/link/173866/web

**📄 简单实现函数式自定义元素** Ginger (Piccalilli)

**长按识别二维码查看原文**

https://piccalil.li/blog/functional-custom-elements-the-easy-way/

🛠 代码与工具

**Peaks.js v4.0：音频波形交互 UI 组件** —— 这个最初由 BBC 研发部门开发的项目，可以在 canvas 元素上渲染音频波形，支持滚动、缩放等音频编辑器常见功能。使用 **LGPL 许可**。

**长按识别二维码查看原文**

https://codeberg.org/chrisn/peaks.js

Chris Needham 等

💡 这个领域还有其他选择，包括新发布的 Waveform Renderer 1.0（附带交互式演示），它专注于波形渲染，此外还有 Wavesurfer.js。

**长按识别二维码查看原文**

https://waveform-renderer.vercel.app/

**Redux Toolkit v2.9：Redux 的”全包”工具集** —— 这个用于 Redux 状态管理的长期工具集进行了性能升级，重写了 RTK Query 的订阅和轮询系统，在缓存条目被移除时自动中止进行中的请求等。

**长按识别二维码查看原文**

https://github.com/reduxjs/redux-toolkit/releases/tag/v2.9.0

Mark Erikson

**react-window v2.0：快速渲染大型数据列表** —— 这个组件库可以快速渲染大型数据列表，避免常见的性能问题。提供了多个示例，需要 React 18。（Tanstack Virtual 是这个领域的另一个选择）。

**长按识别二维码查看原文**

https://react-window.vercel.app/

Brian Vaughn

✉️ 其他资讯

由于各种原因——尤其是 8 月份的休假（抱歉！）——我积累了一些很棒的投稿想要单独分享：

- 🎨 Eyecons 是一个 VS Code 图标主题，可以自动调整图标颜色以匹配你的编辑器主题——当然，是从这个列表中的主题。
    
    **长按识别二维码查看原文**
    
    https://eyecons.dev/
    

- TypeScript Result 引入了 `Result` 类型，帮助你以更类型安全的方式处理错误。
    
    **长按识别二维码查看原文**
    
    https://github.com/everweij/typescript-result
    

- Vue Log Arsenal 是一个插件，为 Vue 3 应用程序添加了各种日志指令，可以直接在元素中使用，比如这样。
    
    **长按识别二维码查看原文**
    
    https://github.com/MvdZon/Vue3-log-arsenal
    

- Michael Sweeney 展示了一个”JavaScript 魔术技巧”，使用函数作为原始值和能记住其祖先的嵌套代理。
    
    **长按识别二维码查看原文**
    
    https://dev.to/overthemike/cosplay-and-wiretapping-javascripts-hidden-superpowers-1gcm
    

- StateLayer 是一个即将推出的声明式 3D 组件框架，其主页就是一个实时演示。还有一个入门教程，教你如何从零开始构建 3D 场景。
    
    **长按识别二维码查看原文**
    
    https://statelayer.com/
    

- fp-filters 是一个精心策划的函数式编程过滤器函数集合，包含超过一百个常用函数。
    
    **长按识别二维码查看原文**
    
    https://github.com/Oaxoa/fp-filters
    

**版本发布：**

- Deno 的 Fresh 框架发布了 **Fresh 2.0 Beta** 版本。现在可以作为 Vite 插件运行，开启了许多新可能。

- **Electron v38.0** —— 跨平台桌面应用程序框架。现在使用 Chromium 140 和 Node 22.18，搭配 V8 14.0。

- **Ember v6.6** —— “用于构建雄心勃勃的 Web 应用程序”的框架。

- **Node.js v20.19.5 (LTS)**

- **serverless-http v4.0** —— 在 AWS Lambda 上使用你现有的中间件框架（如 Express、Koa）。

- 🖋️ **Signature Pad v5.1** —— 基于 Canvas 的平滑签名绘制控件。

- **Tinypool v2.0** —— 极简的 Node.js 工作线程池实现。

- **gRPC Web v2.0** —— 面向浏览器客户端的 gRPC JavaScript 实现。

- **Jasmine v5.10** —— 适用于浏览器和 Node 的测试框架。

- **NodeBB v4.5** —— 基于 Node.js 的论坛系统。

- **Watt v3** —— Node.js 应用程序服务器。