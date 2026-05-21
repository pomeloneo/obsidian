# React 中文周刊 #115 - 一封来自 Phoenix 的作者写给 React 的情书

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512099&idx=1&sn=5385189022b2fcc6cb25474b2aa1fd83&chksm=e921fbc1de5672d7eb92907c1c7aa2c88fce7f58975fde36c4ba9fc3aec285ea703fe8a4cc79\#rd  
> 抓取时间: 2026/2/2 23:46:26

---

> 本期看点：这里有一封来自 Phoenix 的作者写给 React 的情书；同时，Gatsby v5.0 发布：迄今为止最快的 Gatsby。

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**一封来自 Phoenix 的作者写给 React 的情书** — 实际上，与其说是一封情书，不如说是来自 **Fly.io** 的作者对 React 优秀特点的逐一阐述。还有一个有趣的点，本文的作者也是 Elixir 的 **Phoenix 框架** 的作者，该框架本身也借鉴了 React 的思想。

**长按识别二维码查看原文**

https://fly.io/blog/love-letter-react/

Chris McCord (Fly.io)

**Gatsby v5.0：迄今为止最快的 Gatsby** — 除了 Next.js 以外，Gatsby 也是一个基于性能导向的 React 框架，在 5.0 版本中 Gatsby 又向前迈进了一步，推出了 **Slice API**，用于加快整个网站的常见更新、部分 hydration 的 beta 版、新推出用于加载脚本的 Script 组件、支持增量构建和部署等很多其他功能。Gatsby 团队为了把 Gatsby 定调为 **‘反应式网站生成器’** 也做了很长时间的努力。

**长按识别二维码查看原文**

https://www.gatsbyjs.com/blog/gatsby-5/

Josh Johnson (Gatsby Team)

**Rockpack v3.0：又一个 React 应用程序生成器** — Rockpack 就像 _Create React App_ 一样，目标是让项目配置时间尽可能地短，但 Rockpack 对于把事情做到什么程度持有一些不同的意见，它自己也抱有很多想法，包括服务器端渲染和 **这次 3.0 版本推出的** 各种 lint。

**长按识别二维码查看原文**

https://github.com/AlexSergey/rockpack

Alex Sergey

**用 Wails 和 React 在 Go 中构建一个桌面应用程序** — **Wails** 于 Go(lang) 就像 Electron 于 Node 一样，你可以前端用 JavaScript，后端用 GO 在 Mac、Linux 和 Windows 上开发桌面应用程序。与其说这是一个完整的教程，不如说是一个尝试，如果你想了解具体实现，可以看看这个 **demo**。

**长按识别二维码查看原文**

https://react.statuscode.com/link/131395/web

Ed Rutherford

**如何用 DALL-E 和 React 生成图片** — 最近，人工智能创建的图像在社交网络上热火朝天。那么基于 DALL-E 有一个对外开放的官方 API，本文会介绍如何将一个人工智能产品–**DALL-E**--的功能纳入 React 应用程序。

**长按识别二维码查看原文**

https://react.statuscode.com/link/131399/web

Lorenzo Zarantonello

**▶  ⚠️ 一个 Next.js 13 版本的警告：对 React 新 hook “use” 的错误使用可能会引发无限循环** — 作者在视频中做了详细解释。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=zwQs4wXr9Bg

Jack Herrington

**探索 Bun 的内置 React 模板**

**长按识别二维码查看原文**

https://medium.com/deno-the-complete-reference/react-boilerplate-with-bun-36808ee0bfaf

Mayank Choubey

**用 AWS Amplify 和 Route 53 在 10 分钟内部署一个 React 应用程序**

**长按识别二维码查看原文**

https://dev.to/aws-builders/deploy-react-app-in-10-minutes-with-aws-amplify-and-route-53-24om

Samuel Olubayo (AWS Community Builders)

## 🛠 代码与工具

**React Calendar v4.0：React 应用程序的“终极”日历** — 一个流行的、风格简单的 React 日历组件，主要是让用户选择日期。注意，您需要在 React v16.8+ 上才能使用 v4.0。**GitHub 仓库**。

**长按识别二维码查看原文**

https://projects.wojtekmaj.pl/react-calendar/

Wojciech Maj

**CRACO v7.0：覆盖 Create React App 配置** — 如果你仍然喜欢 Create React App，而不是如 Next.js 之类的更大的 React 应用构建方式，CRACO 让你继续使用 CRA，但增加了一个可理解的配置层。**查看文档**。

**长按识别二维码查看原文**

https://github.com/dilanx/craco

Dilan

**Ultra: 没有历史包袱的 Deno React Streaming 框架** — 围绕 ES 模块和 import maps 等本地浏览器特性构建，而不是将代码打包。这个项目有一个非常引人注目的 Web 页面。

**长按识别二维码查看原文**

https://ultrajs.dev/

Omar Mashaal et al.

**符合 SAP Fiori 用户体验的 UI5 Web Components 包装实现** — 如果您的目标是用 React 扩展 SAP 功能，这些组件提供了反映其 **Fiori** 技术平台的用户体验。

**长按识别二维码查看原文**

https://github.com/SAP/ui5-webcomponents-react

SAP

**D-Tale：可用于 Pandas 数据结构的基于 React 的可视化工具** — 如果您需要与基于 Python 的数据分析过程进行交互，这个基于 flask 后端和 React 前端的成熟组合可以可视化 Pandas 数据结构。

**长按识别二维码查看原文**

https://github.com/man-group/dtale

Man Group

**audio-player：一款基于 Hook 的音频播放器** — 带有自定义控件、播放列表、过滤器和搜索的音乐播放器。

**长按识别二维码查看原文**

https://github.com/madzadev/audio-player

Madza

**⚡️ 好库推荐：**

- **React Bootstrap v2.6** 基于 React 构建的 Bootstrap 5 组件

- **React Native Share v8.0** 分享数据共享到其它（社交）应用程序

- **React Flow v11.2** 创建基于节点的交互式 UI

- **React DayPicker v8.3.6** 可定制的日期选择器组件

- **React Native Big List v1.6** React Native 高性能列表组件

- **React-PDF v6.0.2** 像展示图片一样便捷的预览 PDF 文件

- **React Page v5.2** 可自定义的浏览器内容编辑器

- **Gestalt v81.0** 基于 Pinterest Design System 的组件库

## 🙋🏻‍♀️