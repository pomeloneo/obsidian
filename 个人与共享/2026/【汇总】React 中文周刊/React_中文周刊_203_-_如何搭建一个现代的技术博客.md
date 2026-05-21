# React 中文周刊 #203 - 如何搭建一个现代的技术博客

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535184&idx=1&sn=80362e557a10c85f89b0e56d6f3f8d87&chksm=e92101b2de5688a47e75ed34311c9f729adea4bbd87413ace97f7a6d76a0b8c91f028a21f4e1\#rd  
> 抓取时间: 2026/2/2 23:43:15

---

> 本期看点：本期推荐了 Josh W. Comeau 分享了他如何使用 Next.js、MDX、Sandpack 和一系列其他技术重写他的博客。以及 2024 年如何在 React 中获取数据。

> 编辑：TimLi

🔥 本周热门

**Josh W. Comeau 分享了他如何使用 Next.js、MDX、Sandpack 和一系列其他技术重写他的博客** —— 和许多人一样，我们非常喜欢 Josh 的博客（尤其是他丰富的 React 文章）。他刚刚使用 Next.js、MDX、Sandpack 和一系列其他技术重建了整个网站，并详细介绍了所有相关内容。这是一个深入了解现代 React 驱动项目幕后的好机会。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/blog/how-i-built-my-blog-v2/

Josh W Comeau

**2024 年 React 数据获取指南** —— 本文更新了在 React 中从远程 API 获取数据的多种方法。注意，这里不涉及基于 Redux 的方法，而是关注一般的、广泛的方法。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-fetching-data/

Robin Wieruch

**组件组合其实很棒** —— 一位备受尊敬的作者写道，使用组件组合可以避免对互斥状态进行条件渲染（并解释了为什么我们都应该这样做）。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/component-composition-is-great-btw

Dominik Dorfmeister（又名 TkDodo）

**面向 React 开发者的 Vim 教程** —— 虽然 VS Code 如今是大多数人的首选编辑器，但对于那些愿意学习其众多命令的人来说，Vim 及其各种衍生版本有很多优势。Lee 制作了一个简单的”课程”（直接在 Vim 中运行），教你如何使用 Vim 命令来编辑 React 代码。

**长按识别二维码查看原文**

https://vimforreactdevs.com/

Lee Robinson

**使用 Heroku CI 在 Chrome 中测试 React 应用程序** —— 本文介绍了如何在 CI 流程（本例中是 Heroku 的）中对 React 应用程序进行端到端测试。

**长按识别二维码查看原文**

https://blog.heroku.com/testing-react-app-chrome-heroku-ci

Julián Duque（Heroku）

**使用 OpenTelemetry 检测 React 应用程序** Joaquín Díaz（The New Stack）

**长按识别二维码查看原文**

https://thenewstack.io/instrumenting-a-react-app-using-opentelemetry/

**React Hooks 的潜规则** Tom MacWright

**长按识别二维码查看原文**

https://macwright.com/2024/09/19/the-extra-rules-of-hooks

**在 Remix 中使用二维码** Andre Landgraf

**长按识别二维码查看原文**

https://andrelandgraf.dev/blog/2024-09-22_working-with-qr-codes-in-remix

**快讯：**

- Storybook v8.3 已发布。这个流行的前端组件工作坊与基于 Vite 的 Vitest 测试框架合作，大大加快了其组件测试功能。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/storybook-8-3/
    

- 🕹️ Christoph Nakazawa 一直在开发一款基于 React 的游戏 Athena Crisis（他在今年早些时候开源了代码），该游戏刚刚发布了 1.0 版本。
    
    **长按识别二维码查看原文**
    
    https://cpojer.net/
    

- 📊 Ruby on Rails 世界的一项重要调查显示，React 在 JavaScript 框架中已从第一名滑落，被 37signals 的 Stimulus.js 取代。
    
    **长按识别二维码查看原文**
    
    https://railsdeveloper.com/survey/2024/\#what-javascript-libraries-are-you-using-alongside-rails
    

🛠 代码与工具

**React Chrono：动态、交互式时间线组件** —— 支持水平、垂直和垂直交替时间线，具有键盘可访问性、嵌套时间线支持、幻灯片式自动播放时间线等功能。

**长按识别二维码查看原文**

https://react-chrono.prabhumurthy.com/

Prabhu Murthy 等

**React Snap Carousel：以 DOM 为先的无头轮播** —— 使用原生浏览器滚动和 CSS 滚动捕捉点以提高性能。你可以在其 Storybook 中尝试一些功能。最新版本增加了对无限轮播的支持。

**长按识别二维码查看原文**

https://github.com/richardscarrott/react-snap-carousel

Richard Scarrott

**React Loading Skeleton：适应你的应用程序的骨架屏** —— 直接在你的组件中使用”骨架”组件代替正在加载的内容，它会在真实数据到来之前自动调整到合适的大小。

**长按识别二维码查看原文**

https://github.com/dvtng/react-loading-skeleton

David Tang

**Mielo React：围绕 Mielo.css 的组件和包装器** —— 受 GNOME 的 Gtk4 外观和 LibAdwaita 的启发，这套组件和 CSS 变量驱动的样式旨在用于 Electron/Tauri 场景，以创建在 Linux 上看起来不错的应用程序。GitHub 仓库。

**长按识别二维码查看原文**

https://mielo-ui.github.io/

Anton Shramko

**版本发布：**

- **React Native Gesture Handler v2.20** —— 暴露平台原生触摸 API。现在支持 React Native 0.76。

- **Schedule-X v2.1** —— Material Design 风格的事件日历和日期选择器。

- **Framer Motion v11.6** —— 强大的 React 动画和运动库。

- **Jotai v2.10** —— 简单、灵活的 React 状态管理。

- **json-viewer v4.0** —— 以用户友好的格式显示 JSON。

- **MUI X v7.18** —— 流行的 React 组件套件。

- **Vaul v0.9.6** —— 无样式抽屉组件。（演示。）

- **Redwood v8.3** —— 流行的应用程序框架。

- **esbuild v0.24**

🙋🏻‍♀️