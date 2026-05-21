# JavaScript 中文周刊 #199 - Apache ECharts v6.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543110&idx=1&sn=5e22ab9acc4edd2f42e3614015d86689&chksm=e92162a4de56ebb2519519e8eb2f4755cc0028d3b59201467fbe2ccea6f42fac07635a299de5\#rd  
> 抓取时间: 2026/2/2 23:49:48

---

> 本期看点：Apache ECharts v6.0 发布，新增设计语言、动态主题与暗色模式。Vite 生态系统最新动态大汇总。JavaScript 是如何演进的。MathJax v4.0：浏览器中的 JS 数学公式渲染引擎。

> 编辑：TimLi

🔥 本周热点

**Apache ECharts v6.0：强大的数据可视化库** —— 从首次发布至今已有 12 年，ECharts 再次迈出重要一步。它支持从折线图、柱状图、饼图到 3D 图表、日历图和桑基图等多种可视化类型。v6 版本带来了全新的设计语言、动态主题切换、暗色模式支持以及更多图表类型。快来体验 100+ 个示例和查看 GitHub 仓库吧。

**长按识别二维码查看原文**

https://echarts.apache.org/handbook/en/basics/release-note/v6-feature/

Apache Software Foundation

**TypeScript v5.9 发布** —— 这是 TypeScript 一次温和的进步，新增了 `import defer` 支持、`--module node20` 以及”可展开悬停提示”功能（如下图），让你在 IDE 中能看到更详细的类型信息。我们还了解到，v6.0 将作为一个过渡版本，为即将在 TypeScript 7.0 中推出的基于 Go 的”原生移植版”做准备。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-9/

Microsoft

💡 最新版本的 VS Code 已经集成了 TypeScript 5.9，并提供了”可展开悬停提示”功能，这里有更详细的说明。

**长按识别二维码查看原文**

https://code.visualstudio.com/updates/v1_103

**⚖️ Oracle 在 JavaScript™ 商标案中的最新动态** —— Oracle 对 Deno 申请取消 JavaScript 商标的回应中，否认了”业界和公众普遍认为’JavaScript’是通用术语”这一说法。这下我们知道了！

**长按识别二维码查看原文**

https://ttabvue.uspto.gov/ttabvue/v?pno=92086835&pty=CAN&eno=16

United States Patent and Trademark Office

**快讯：**

- Sarah Gooding 分享了 TC39 最新提案进展，包括 `Math.sumPrecise`、Uint8Array/base64 转换函数和 `Iterator.concat`。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/172912/web
    

- Vite 生态系统最新动态大汇总，涵盖了 Vite 7、Rolldown、Oxlint 和 Vitest 等多个项目。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/whats-new-jul-2025
    

- SvelteKit 新增了实验性的远程函数功能，让你可以在 SvelteKit 应用程序的任何位置调用服务器端函数。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/docs/kit/remote-functions
    

- Vercel 现在原生支持部署 Hono 应用程序。Hono 是一个轻量级的跨运行时 Web 应用程序框架。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/deploy-hono-backends-with-zero-configuration
    

📖 文章和视频

**▶ JavaScript 是如何演进的：与 Daniel Ehrenberg 一起探索 TC39 内部** —— 这是一段录制精良的 47 分钟面对面对话，采访对象是 TC39 委员会最活跃的成员之一。内容不仅涵盖了 JavaScript 即将推出的新特性，还介绍了 TC39 的工作方式，以及你如何参与其中、提出想法，推动语言发展。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=v9Al9-0jkoQ

The Weekly Dev’s Brew

💬 虽然还很粗糙，但为了方便无法观看视频的朋友，我把 YouTube 字幕原文放在这个 gist 里了。你也可以在这里以播客形式收听和订阅。

**长按识别二维码查看原文**

https://gist.github.com/peterc/8cf0986e9c9cac8d4e5c0c27c728b446

**V8 的** `**JSON.stringify**` **性能提升超过 2 倍的秘密** —— V8 团队对 `JSON.stringify` 进行了性能优化，这让使用 V8 13.8 及以上版本（如 Chrome 138）的应用程序在执行多个常见任务时获得了自动的性能提升。本文深入解析了这次性能提升背后的底层工作。

**长按识别二维码查看原文**

https://v8.dev/blog/json-stringify

Patrick Thier (V8)

**“问题不在 JavaScript，而在于要替换浏览器”** —— RedwoodSDK（一个用于在 Cloudflare 上构建服务器端应用程序的 React 框架）的创建者认为，SPA 式开发是为了解决平台限制而做出的妥协，现在采用服务器优先的方法更有意义。

**长按识别二维码查看原文**

https://rwsdk.com/blog/spa-is-dead

Peter Pistorius

**📄 为我的博客添加 Bluesky 评论功能** —— 这是个不错的想法，也许能给你一些启发。Natalie B

**长按识别二维码查看原文**

https://natalie.sh/posts/bluesky-comments/

**📄 从创建 PostCSS 中学到的经验** Andrey Sitnik (Evil Martians)

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/what-we-learned-from-creating-postcss

**📄 Stan：一个全新的 TypeScript 状态管理库** Rafał Krupiński

**长按识别二维码查看原文**

https://rkrupinski.com/post/introducing-stan

**📄 关于锚点元素** `**href**` **属性你可能不知道的几件事** Jim Nielsen

**长按识别二维码查看原文**

https://blog.jim-nielsen.com/2025/href-value-possibilities/

**📺 tRPC vs oRPC：类型安全 API 之战** Jack Herrington

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=_oHJUxkAM1w

🛠 代码和工具

**MathJax v4.0：浏览器中的 JS 数学公式渲染引擎** —— 经过数年开发，MathJax 再次证明了它是 Web 数学公式渲染的最佳选择之一。当然也有在线演示。v4.0 新增了更多字体、更好的默认字体、换行支持、ESM 支持等众多功能。

**长按识别二维码查看原文**

https://www.mathjax.org/MathJax-v4.0.0-available/

Cervone, Sorge, et al.

**Panda CSS v1.0：现代化、构建时、类型安全的 CSS-in-JS 方案** —— 这是一个注重开发体验的 CSS-in-JS 方案，由 Chakra UI 的创建者开发。它提供构建时生成的样式和开箱即用的类型安全特性，支持 Remix、Vite、Next.js、Astro，甚至服务器组件。

**长按识别二维码查看原文**

https://panda-css.com/

Segun Adebayo

**zx v8.8：用 Node.js 编写更好的 Shell 脚本** —— 这是一个广受欢迎的工具，它让 Node 环境下的 shell 脚本编写变得更愉快，提供了 `child_process` 的实用封装、参数转义和合理的默认值。v8.8 改进了 zx 的管道功能。（查看文档）

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/8.8.0

Google

**🔊 React Native Audio API** —— 在你的 React Native 应用程序中获得 Web Audio API 的强大功能和灵活性，无论是在 iOS、Android 还是 Web 平台。这篇博文有更详细的说明。

**长按识别二维码查看原文**

https://docs.swmansion.com/react-native-audio-api/

Software Mansion

**🎁 小彩蛋：**

- AwesomeIndex（如上图）提供了一种搜索数百个”awesome”风格精选链接列表的方法。这个想法很有潜力，因为这些列表中包含了大量有用的资源。
    
    **长按识别二维码查看原文**
    
    https://awesomeindex.dev/
    

- r2dec-js 是一个基于 JavaScript 的反编译器，可以将汇编代码转换为”伪 C 代码”，用于学习目的。
    
    **长按识别二维码查看原文**
    
    https://github.com/wargio/r2dec-js
    

- Bali 是一个用 Nim 语言创建的 JavaScript 词法分析器、解析器和解释器。
    
    **长按识别二维码查看原文**
    
    https://github.com/ferus-web/bali
    

- 👀 你想念 ActionScript 3.0 和 Flex 吗？不想？这周我发现 Apache 正在通过 Apache Royale 延续这个梦想。
    
    **长按识别二维码查看原文**
    
    https://royale.apache.org/
    

- 🤖 你可能听说过 OpenAI 发布了 GPT-5，但我觉得他们面向开发者的 GPT-5 介绍被忽视了，其中有一些很有深度的内容。他们还发布了两个开放权重模型。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/172950/web
    

- 今天我才知道 JSON 有自己的 logo。

**版本发布：**

- **eslint-plugin-angular v5.0** —— AngularJS 应用程序的 ESLint 插件，现已支持 ESLint v9。

- **Ghost v6.0** —— 基于 Node.js 的独立发布和博客平台。

- **Joi v18.0** —— 模式描述语言和数据验证器。

- **📈 Fuite v5.0.8** —— Web 应用程序内存泄漏检测工具。