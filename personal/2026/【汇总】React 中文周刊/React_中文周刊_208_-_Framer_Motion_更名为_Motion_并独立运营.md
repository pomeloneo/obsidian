# React 中文周刊 #208 - Framer Motion 更名为 Motion 并独立运营

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537424&idx=1&sn=eb6d26e59f95248a62b81e7ee611c73f&chksm=e92118f2de5691e438100679a618d519cf85fd29bdacb065d9e93bd217d6cba6d20feb5903a6\#rd  
> 抓取时间: 2026/2/2 23:43:04

---

> 本期看点：Framer Motion 更名为 Motion 并成为独立开源项目，Next.js 15 生产环境配置实践分享，Storybook v8.4 发布带来一键组件测试，React Native Windows 0.76.0 支持新架构预览，Expo SDK 52 正式发布。

> 编辑：TimLi

🔥 本周热门

**Framer Motion 现已更名为 Motion** —— Framer Motion 一直是 React 应用程序中强大且广受欢迎的动画库，现在它已更名为 Motion，并从 Framer 公司独立出来，成为”面向社区的独立开源项目”。

**长按识别二维码查看原文**

https://motion.dev/blog/framer-motion-is-now-independent-introducing-motion

Matt Perry

**2024 年如何为生产环境配置 Next.js 15** —— 作者分享了他将 Next.js 应用程序扩展到每月超过 10 万活跃用户和数百万访问量的经验。

**长按识别二维码查看原文**

https://www.reactsquad.io/blog/how-to-set-up-next-js-15-for-production

Jan Hesters (ReactSquad)

**Storybook v8.4 发布** —— 这个流行的前端组件工作台迎来了一个小版本更新，但它是”我们功能最丰富的小版本更新之一”，包括一键组件测试、Svelte 5 支持、React Native Storybook 8 以及其他改进。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-8-4/

Michael Shilman

**通过禁用内联事件处理程序让** `**dangerouslySetInnerHTML**` **更安全** —— 当你需要使用这个特性时，如何开始消除潜在的威胁。

**长按识别二维码查看原文**

https://macarthur.me/posts/safer-dangerouslysetinnerhtml/

Alex MacArthur

**▶ 从 Next.js 到 htmx：一个真实案例** —— 这是一个有趣的案例研究，通过 50 分钟的屏幕录像解释：“用 htmx 驱动的 HTML 元素替换我的组件并不是一件容易的事，但这值得投入时间。”

**长按识别二维码查看原文**

https://htmx.org/essays/a-real-world-nextjs-to-htmx-port/

Pouria Ezzati

**📄 React 中的样式困境** —— 一位开发者分享了不同样式方案的经验，包括它们的优缺点。Petar Ivanov

**长按识别二维码查看原文**

https://thetshaped.dev/p/the-styling-dilemma-in-react

**📄 使用** `**i18n-check**` **验证你的 react-intl 应用程序翻译** Lingual

**长按识别二维码查看原文**

https://lingual.dev/blog/validating-react-intl-applications/

**📄 使用** `**useCallback()**` **防止不必要重渲染的完整指南** Jing Li

**长按识别二维码查看原文**

https://hygraph.com/blog/react-usecallback-a-complete-guide

**📄 React 和** `**FormData**` Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-form-data/

**快讯：**

- Microsoft 发布了 React Native Windows 0.76.0，其中包含了对”新架构”的预览支持。
    
    **长按识别二维码查看原文**
    
    https://github.com/microsoft/react-native-windows/releases/tag/react-native-windows_v0.76.0
    

- Expo 发布了 Expo SDK 52，这是这个流行的 React Native 应用程序开发平台工具的最新版本（现已包含 React Native 0.76）。
    
    **长按识别二维码查看原文**
    
    https://expo.dev/changelog/2024/11-12-sdk-52
    

- 🎧 Facebook React 团队的前成员 Tom Occhino 做客 Stack Overflow 播客，不仅聊了一些 React 的历史，还谈到了他目前在 Vercel 与 Next.js 相关的工作，以及”Vercel 如何通过 v0 重新思考 IDE”。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.blog/2024/11/01/how-a-creator-of-react-is-rethinking-ides/
    

🛠 代码与工具

**React Query Builder v8.0** —— 一个可自定义的查询构建器组件，同时提供了一系列实用函数，可以导入和导出各种查询语言，如 SQL、MongoDB 等。

**长按识别二维码查看原文**

https://react-querybuilder.js.org/

Sapient Global Markets

**React Native Godot：将 Godot 游戏引擎引入 RN** —— 如果你一直在等待将流行的开源游戏引擎 Godot 引入 React Native 应用程序，这里有一个早期尝试可以参考（目前仅支持 iOS）。

**长按识别二维码查看原文**

https://github.com/calico-games/react-native-godot

Calico Games

**🗓️ Schedule-X 2.5：Material Design 日历和日期选择器** —— 提供 React/Preact、Vue、Svelte、Angular 或纯 JS 组件形式。开源但有带额外功能的高级版本。GitHub 仓库。

**长按识别二维码查看原文**

https://schedule-x.dev/

Tom Österlund

**Formity：使用 JSON 构建动态多步表单的库** —— 页面上有一个简单但有效的演示，它使用基于 JSON 的语法构建，支持循环、变量和运算符，可以存储在任何地方。

**长按识别二维码查看原文**

https://www.formity.app/

Martí Serra Molina

**💰 React Currency Input Field Component v3.9** —— 一个旨在捕获货币输入细节的组件，如果简单的自由格式输入无法满足你的需求，可以尝试这个。可以通过在线演示体验。

**长按识别二维码查看原文**

https://github.com/cchanxzy/react-currency-input-field

Chun Chan

**版本发布：**

- **📊 visx v3.12** —— Airbnb 的 React 可视化组件套件现在包含了桑基图组件。

- **use-local-storage-state v19.5** —— 用于在 `localStorage` 中持久化数据的 Hook。

- **markdown-to-jsx v7.6** —— 轻量级 Markdown 组件。（演示）