# React 中文周刊 #191 - React 19 和 Suspense 的三幕剧

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532628&idx=1&sn=f9dceed5429c0589bff47506621f353c&chksm=e9210bb6de5682a056cb8342628705af3283560d39326596fa6ef60fca36359f58cc429dcf16\#rd  
> 抓取时间: 2026/2/2 23:43:40

---

> 本期看点：React 19 RC 的发布引发了关于 Suspense 行为变化的争议。起初，Suspense 的并发加载被改为瀑布式加载，导致性能问题和社区反对。经过讨论和反馈，React 团队决定推迟发布，并恢复并发加载。这个过程展示了社区反馈的重要性和 React 团队的开放态度。

> 编辑：TimLi

🔥 本周热门

**React 19 和 Suspense：三幕戏剧** —— React 19 RC 的发布引发了关于 Suspense 行为变化的争议。起初，Suspense 的并发加载被改为瀑布式加载，导致性能问题和社区反对。经过讨论和反馈，React 团队决定推迟发布，并恢复并发加载。这个过程展示了社区反馈的重要性和 React 团队的开放态度。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/react-19-and-suspense-a-drama-in-3-acts

Dominik Dorfmeister（也叫 TkDodo）

💡 Henrique Yuji 在 React 19 如何（几乎）让互联网变慢 中也谈到了同样的问题，这在 Hacker News 上引发了 一场非常广泛的讨论。来自 2023 的这个 PR 进一步介绍了导致变化的原因。

**长按识别二维码查看原文**

https://blog.codeminer42.com/how-react-19-almost-made-the-internet-slower/

**如何使用 Google Sheets 作为 React 的“数据库”** —— 使用这种方法最吸引人的原因是什么？通过简单地分享一个他们可能已经会用的 Google Sheet，使你的应用程序数据对技术人员和非技术人员都可用。

**长按识别二维码查看原文**

https://thenewstack.io/how-to-use-google-sheets-as-a-database-with-react-and-ssr/

Paul Scanlon

**Relay 17：数据驱动的 React 应用框架** —— 像 React 一样，Relay 来自 Facebook 并被用于其许多通过 GraphQL 消费数据的系统中。React Conf 2021 上的演讲 ▶️ 重新介绍 Relay 能让你快速了解主要概念。

**长按识别二维码查看原文**

https://github.com/facebook/relay/releases/tag/v17.0.0

Meta / Facebook

**通过 JSI 桥接 React Native 和 Rust** —— 详细介绍了一个团队构建一个可以与用 Rust 编写的核心逻辑桥接的 React Native SDK 的方法。

**长按识别二维码查看原文**

https://ditto.live/blog/bridging-react-native-and-rust-via-jsi

Teodor Ciuraru

**📄 Mobx 记忆化组件（你不需要 React Compiler..）** —— 如果你正在使用 Mobx。Mike Johnson

**长按识别二维码查看原文**

https://www.mikejohnson.dev/posts/2024/06/mobx-react-compiler

**📄 创建一个带加载/等待状态的 React 表单** Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-form-loading-pending-action/

**📄 通过实例解释的四个新的 React 19 Hooks** Kunal Nalawade

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/react-19-new-hooks-explained-with-examples/

**快讯：**

- 📅 React Rally 将于 2024 年 8 月 12-14 日在犹他州帕克市回归。这个 演讲者阵容 看起来很棒！
    
    **长按识别二维码查看原文**
    
    https://www.reactrally.com/
    

- 🇲🇦 React Africa 是今年 11 月在非洲首次举办的国际 React 大会，地点在摩洛哥卡萨布兰卡，线上和线下都有。
    
    **长按识别二维码查看原文**
    
    https://react-africa.com/
    

- ⚽ 2024 年 UEFA 欧洲足球锦标赛（也称为“欧锦赛”）正在进行中，Jonny Burger 使用 Remotion 在 React 中重新创建了其电视图形。推文视频 或 代码。
    
    **长按识别二维码查看原文**
    
    https://x.com/JNYBGR/status/1802711935298728420
    

- Vercel 已推出 Vercel AI SDK v3.2
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/introducing-vercel-ai-sdk-3-2
    

🛠 代码与工具

**React Tag Autocomplete v7.3** —— 一种灵活、易访问的标签组件，让用户在选择标签时能更容易地朝正确方向前进。这里有 一个在线演示 供你查看其效果。

**长按识别二维码查看原文**

https://github.com/i-like-robots/react-tag-autocomplete

Matt Hinchliffe

**Reassure v1.0：React 和 React Native 的性能测试助手** —— 在 CI 或本地机器上自动进行 React 应用的性能回归测试。会将多次运行应用场景的渲染特性和指标与已知的稳定版本进行比较供你分析。

**长按识别二维码查看原文**

https://github.com/callstack/reassure

Callstack

**NLUX：用于渲染对话式 AI 体验的库** —— 如果你想在你的服务或第三方 AI 后端上快速搭建一个 ChatGPT 风格的对话组件，这个库可以帮你很轻松的实现。

**长按识别二维码查看原文**

https://docs.nlkit.com/nlux

Salmen Hichri

**react-signature-pad-wrapper：Signature Pad 的包装器** —— 如果你想在应用中提供用户手写签名的功能，这里是一个适合的控件。演示

**长按识别二维码查看原文**

https://github.com/michaeldzjap/react-signature-pad-wrapper

Michael Dzjaparidze

**React Native Background Actions v4.0** —— 一个用于在 Android 和 iOS 上运行后台任务的后台服务库（至少直到宇宙热寂为止）。

**长按识别二维码查看原文**

https://github.com/Rapsssito/react-native-background-actions

Rapsssito

**⚙︎ Yet Another React Lightbox** —— 快速将 lightbox 组件添加到你的项目中。Igor Danchenko

**长按识别二维码查看原文**

https://yet-another-react-lightbox.com/

**⚙︎ React Native Magic Modal** —— 简化 React Native 中的模态管理。Gabriel Taveira

**长按识别二维码查看原文**

https://github.com/GSTJ/react-native-magic-modal

**版本发布：**

- **React Content Loader v7.0.2** —— SVG 驱动的“占位符”加载组件。

- **React Date Picker v7.1** —— 简单的日期选择器组件。(演示)。

- **React Tooltip v5.27** —— 一个不出意外的 tooltip 组件！

- **Plasmo v0.88** —— “像 Next.js 一样的浏览器扩展框架。”

- **MUI X v7.7** —— 流行的 React 组件套件。

🙋🏻‍♀️