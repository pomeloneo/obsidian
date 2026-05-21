# React 中文周刊 #236 - React 仍然感觉很荒谬，为什么没人讨论这个问题？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542433&idx=1&sn=0e7ce3fa8d6e456980b5ba09e6374279&chksm=e9216d43de56e4553cd614839bc08f331ca3b9bb0b3d068f8cb1e26a8102fea9f9e08b5bd370\#rd  
> 抓取时间: 2026/2/2 23:42:03

---

> 本期看点：React 开发社区讨论现代 SPA 应用程序复杂性痛点引发热议，Vercel Ship 2025 大会回顾，React 数据获取学习指南，Tuono 推出 React/Rust 全栈框架，Time Picker：基于 shadcn/ui 的日期/时间选择器组件。

> 编辑：TimLi

🔥 本周热门

**React 仍然感觉很荒谬，为什么没人讨论这个问题？** —— 通常我们不会推荐这种有争议的文章，但是本周 React 博客圈实在太平静了。而且这篇文章在 Reddit 和 Hacker News 上引发了大量讨论，所以我们决定给它一个机会。Mario 指出了现代富 SPA 应用程序中复杂性的一些痛点，以及像 React 这样灵活的库如果使用不当，很容易导致混乱。不过说到底，这个问题并不是 React 独有的！

**长按识别二维码查看原文**

https://mbrizic.com/blog/react-is-insane/

Mario Brizic

😅 现在，我们能不能看到一些持相反观点的正面文章呢？

**Vercel Ship 2025 回顾** —— 在我们上周发送 **React Status** 时，Vercel 的年度大会正在进行。我们之前分享了直播链接，现在你可以在一个地方了解所有公告，包括他们的 AI SDK 更新、Fluid 计算选项、Vercel Sandbox、Rolling Releases 功能、机器人检测等。

**长按识别二维码查看原文**

https://vercel.com/blog/vercel-ship-2025-recap

Vercel

**📄 没时间学习（Web）框架 X** —— 如何判断什么时候值得学习新东西？ Wouter Groeneveld

**长按识别二维码查看原文**

https://brainbaking.com/post/2025/06/no-time-to-learn-web-framework-x/

**📄 使用** `**useOptimistic**` **让你的应用程序响应更快** Kent C. Dodds

**长按识别二维码查看原文**

https://www.epicreact.dev/use-optimistic-to-make-your-app-feel-instant-zvyuv

**📄 React 数据获取学习指南** React Practice

**长按识别二维码查看原文**

https://reactpractice.dev/articles/study-guide-data-fetching-in-react/

**📄 使用 Storybook 9 自动化前端无障碍功能** Dominic Nguyen

**长按识别二维码查看原文**

https://storybook.js.org/blog/the-accessibility-pipeline-for-frontend-teams/

**快讯：**

- 🧊 Reactylon 是一个基于 Babylon.js 的 React 3D/扩展现实框架，我们最近介绍过它 —— 现在它有了一个展示页面，展示了一些使用案例。
    
    **长按识别二维码查看原文**
    
    https://www.reactylon.com/
    

- 🇬🇧 React Advanced London 是一个将于今年 11 月在伦敦举行的线上和线下 React 活动。
    
    **长按识别二维码查看原文**
    
    https://reactadvanced.com/
    

- 🤖 Anthropic 为 Claude 添加了直接构建和分享 AI 驱动应用程序的功能，这些应用程序可以使用 React 驱动的 UI。
    
    **长按识别二维码查看原文**
    
    https://www.anthropic.com/news/claude-powered-artifacts
    

- ECMAScript 2025 规范已经被 Ecma International 批准，Pawel Grzybek 在这里分享了一些新的语言特性 —— 希望很快就能在 JavaScript 实现中看到这些特性。
    
    **长按识别二维码查看原文**
    
    https://tc39.es/ecma262/2025/
    

🛠 代码与工具

**🗓️ Time Picker：基于 shadcn/ui 的日期/时间选择器组件** —— 简单、优雅，使用体验良好。

**长按识别二维码查看原文**

https://time.openstatus.dev/

OpenStatus

**Tuono：React/Rust 全栈框架** —— 如果你喜欢 React 和 Next.js，但更倾向于用 Rust 构建后端，这个框架就是为你准备的。Tuono 支持类似 Next.js 风格的完整 React 服务端体验，但底层使用 Rust。

**长按识别二维码查看原文**

https://tuono.dev/

Valerio Ageno 等

**react-xtermjs：React 版 Xterm.js** —— 如果你想在 React 应用程序中添加基于 Xterm.js 的终端风格体验。更多详情请参考这篇博文。**GPL 许可证。**

**长按识别二维码查看原文**

https://github.com/Qovery/react-xtermjs

Rémi Bonnet

✂︎ 深度精选

由于本周比较安静，我们回顾了一下尚未进入简讯的积压项目。以下是一些值得关注的内容：

- 你知道 Vercel 为开发者创建了自己的字体吗？它叫做 Geist，采用开源许可，有多种字重，包含 600+ 字形，支持 32 种语言，还有等宽变体。GitHub 仓库。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/font
    

- 📉 Josh Justice 深入讲解了如何使用 MUI X Charts 在 React 中创建高级折线图。
    
    **长按识别二维码查看原文**
    
    https://testdouble.com/insights/guide-advanced-line-graphs-in-react-with-mui-x-charts
    

- Neobrutalism 是一套基于 shadcn/ui 的视觉冲击力强的组件套件，具有直接、简洁的风格。
    
    **长按识别二维码查看原文**
    
    https://www.neobrutalism.dev/
    

- 如何为 React 应用程序添加样式 探讨了一些关于样式的思考，以及作者为什么认为基于 Tailwind 的方法优于更传统的语义化方法。
    
    **长按识别二维码查看原文**
    
    https://alexkondov.com/full-stack-tao-styling/
    

- 使用 Kamal 2 部署 Next.js 应用程序 —— Kamal 是一个源自 Ruby 世界的基于容器的部署工具。
    
    **长按识别二维码查看原文**
    
    https://nts.strzibny.name/deploying-next-kamal-2/
    

- 如何使用 Framer Motion 创建”胶状”搜索交互
    
    **长按识别二维码查看原文**
    
    https://tympanus.net/codrops/2024/11/18/how-to-create-a-gooey-search-interaction-with-framer-motion-and-react/
    

**版本发布：**

- **UI Builder v2.0** —— 为你的应用程序添加类似 Figma 的可视化组件，让用户以无代码方式组合页面、邮件、仪表板等。

- **AG Charts v12.0** —— 功能丰富的图表库，支持多个框架。

- **Yet Another React Lightbox v3.24** —— 现代 React 灯箱组件。

- **Schedule-X v2.35** —— Material Design 风格的事件日历和日期选择器。

- **Ink v6.0.1** —— 使用 React 构建命令行应用程序。