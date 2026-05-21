# React 中文周刊 #207 - Docusaurus 3.6 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537226&idx=1&sn=d5bcba764374ad8f45a190273c8c4e2b&chksm=e92119a8de5690bef773e3c3c52ef2bea48bef250db971851a8b9777f69b0ada96e304f0f27c\#rd  
> 抓取时间: 2026/2/2 23:43:06

---

> 本期看点：Docusaurus 3.6 发布，使用 Rspack、SWC 和 Lightning CSS 等工具使构建过程比以往更快；React GJS renderer 让你用 React 构建原生 Gnome GTK 应用程序；React 编译器进入 beta 阶段；

> 编辑：TimLi

🔥 本周热门

**Docusaurus v3.6：面向文档的静态站点生成器** —— 我们一直都很喜欢 Meta 的 Docusaurus，这是一个用于构建和部署技术文档站点的流行工具（看看这些案例）。v3.6 版本专注于性能优化，现在使用 Rspack、SWC 和 Lightning CSS 等工具使构建过程比以往更快。

**长按识别二维码查看原文**

https://docusaurus.io/blog/releases/3.6

Meta

⚡ MikroORM 的文档站点构建时间在开发环境从 6 分 40 秒缩短到 2 分 30 秒，在生产环境从 12 分钟缩短到 4 分 30 秒。

**长按识别二维码查看原文**

https://mikro-orm.io/

**React GJS 渲染器：用于 GNOME JavaScript 的 React 渲染器** —— 这个项目适合开发 Linux 桌面应用程序的开发者，它让你可以通过 GJS（GNOME JavaScript）环境使用 React 构建原生 Gnome GTK 应用程序（可以将其理解为类似 Node.js 的运行时，但专门用于 GNOME 桌面应用程序，并由 SpiderMonkey 驱动）。

**长按识别二维码查看原文**

https://github.com/react-gjs/renderer

Szymon Bretner

**▶ React 编译器的下一步是什么？** —— React 编译器现已进入 beta 阶段。在最近的 React India 活动中，核心团队成员简要介绍了编译器的改进情况和未来发展方向（19 分钟）。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=qd5yk2gxbtg

Sathya Gunasekaran

**使用 Go 和 React 创建全栈应用程序** —— 探讨如何将前端和后端的精华结合到一个应用程序中，以一个名为”Go Eats”的食品订购服务为例。

**长按识别二维码查看原文**

https://blog.jetbrains.com/go/2024/11/04/create-a-full-stack-app-with-go-and-react/

Mukul Mantosh (JetBrains)

**如何（不）在 React Server Action 后重置表单** —— “曾经有一段时间表单不会自动重置……最近，表单开始自动重置，现在大家都想知道如何在出现（验证）错误时保持表单内容不变。”

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-server-action-reset-form/

Robin Wieruch

**Shopify 如何构建其 2023 年黑色星期五全球销售可视化** —— Shopify 正在为 2024 年的黑色星期五季做准备，同时分享了他们如何使用 Three.js 和 React Three Fiber 构建去年那个引人注目的销售可视化效果。不得不说，着色器承担了大部分工作，而不是 React。

**长按识别二维码查看原文**

https://shopify.engineering/how-we-built-shopifys-bfcm-2023-globe

Diego Macario Bello (Shopify)

**如何使用 React 和 AI 代理创建 AI 驱动的新闻聚合器** —— 哦不！你应该不会想这么做吧…… 😅 不过，看到 KaibanJS 代理构建框架的实际应用还是很酷的。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/11/04/how-to-create-an-ai-powered-newsletter-aggregator-with-react-and-ai-agents/

Dariel Villa

**📄 在 React 应用程序中实现实时视频模糊或虚拟背景** —— Farhan CK

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/video-background-removal

**📄 在 Next.js App Router 中管理高级搜索参数过滤** —— Aurora Scharff

**长按识别二维码查看原文**

https://aurorascharff.no/posts/managing-advanced-search-param-filtering-next-app-router/

**快讯：**

- 2024 年 React 现状调查还剩不到两周时间。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-react/2024
    

- Shopify 已完成将其移动应用程序迁移到 React Native，这里有一个关于迁移过程的讨论。
    
    **长按识别二维码查看原文**
    
    https://threadreaderapp.com/thread/1853619638141071573.html
    

- ▶️ 100 秒解释 Next.js 的 `use cache`。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=OWmRn74CQKY
    

🛠 代码与工具

**React-Ace：在 React 应用程序中集成 Ace 编辑器** —— Ace 是一个历史悠久的面向代码的 Web 编辑器控件。这里有一个快速演示。

**长按识别二维码查看原文**

https://github.com/securingsincity/react-ace

James Hrisho

**Sonner v1.7：固执己见的 Toast 通知组件** —— 默认样式美观但可自定义。主页上有实时演示，也可以查看 GitHub 仓库。v1.7 主要改进了动画效果、浏览器支持，并添加了 React 19 支持。

**长按识别二维码查看原文**

https://sonner.emilkowal.ski/

Emil Kowalski

**：快速访问组件源代码** —— 在浏览器中按住 `Option` 键点击 React 组件即可在 VS Code 中打开源代码。此外，`Option + 右键点击`可以打开上下文菜单，显示父组件的 props、文件名、列号和行号。

**长按识别二维码查看原文**

https://github.com/ericclemmons/click-to-component

Eric Clemmons

**版本发布：**

- **BlockNote v0.19** —— 类 Notion 的基于块的编辑器。现在支持列布局和客户端导出为 `.docx` 和 PDF。项目主页上有演示。

- **Tailwind Next.js Starter Blog v2.3** —— 博客启动模板。

- **MDX Editor v3.16** —— Markdown 富文本编辑器组件。

- **React Suite v5.74** —— React 组件套件。（示例）

- **🗓️ React DayPicker v9.3** —— 可自定义的日期选择器。

- **uikit v0.8** —— 为 Three.js 构建高性能 3D UI。

- **xr v6.4** —— 为 React Three Fiber 带来 VR/AR 功能。