# React 中文周刊 #185 - React 19 Beta 版本发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531531&idx=1&sn=88f1275ff115a1e3ea532dbe5a75d6e7&chksm=e92137e9de56beff12f9311038a1116813e0c72aebf3b0571c197ff5fbc3de6c8466b263c0cc\#rd  
> 抓取时间: 2026/2/2 23:43:53

---

> 本期看点：本期介绍了 React 19 Beta 版的新特性，包括支持自定义元素、增强的异步事务处理能力、以及原生元数据标签的渲染等新特性。同时，提供了详细的升级指南帮助开发者顺利过渡。工具方面介绍了 extension.js 用于简化浏览器扩展开发，Divz 用于增强 3D 交互。此外，还有关于 React-Spring 动画库的可视化工具介绍，帮助开发者更好地理解和应用动画效果。

> 编辑：Yucohny、TimLi

🔥 本周热门

**React 19 Beta 版本发布** —— React 团队说这个 Beta 版是为了让库开发者为最终的 React 19 发布做好准备，但这并没有阻止所有人深入研究所有的新特性 ;-) 如果你想立即升级，这里有一个详尽的升级指南，除此之外还有很多亮点：

**长按识别二维码查看原文**

https://react.dev/blog/2024/04/25/react-19

- 完全支持自定义元素。 — 自定义元素的支持一直是 React 的一个痛点，因为 React 无法区分 prop 和 attribute，但现在终于找到了一种方法！
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/04/25/react-19\#support-for-custom-elements
    

- 所有最新的 React 服务器组件的好东西。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/04/25/react-19\#react-server-components
    

- Action – 你现在可以在过渡中使用异步函数，并获得自动的乐观更新。这为大幅简化代码和在处理表单时更顺畅的操作提供了一些机会，参考这个新 hook ：useActionState。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/04/25/react-19\#actions
    

- `use` – 使用 use 传入一个 promise，React 会挂起直到 promise 解决。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/04/25/react-19\#new-feature-use
    

- 你现在可以在组件中原生地渲染元数据标签（如 `title`，`link` 和 `meta`）。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/04/25/react-19\#support-for-metadata-tags
    

- 在你的组件树的任何地方渲染异步脚本。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/04/25/react-19\#support-for-async-scripts
    

如果你更喜欢看视频来了解 React 19 的新特性，推荐 ▶️ Theo 的介绍视频。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=sFeu_aK8cB8

**React v18.3 也发布了** —— 在 18.2 之后的近两年，React 18.3 是 React 长时间以来的第一个真正的生产版本。然而，它与 18.2 完全相同，但**添加了对弃用的警告**，所以如果你不打算直接跳到 19，这是更负责任的做法。

**长按识别二维码查看原文**

https://github.com/facebook/react/releases/tag/v18.3.0

Rick Hanlon

**使用** `**ast-grep**` **迁移到 React 19？** —— 很难说这是在简单模式还是困难模式下做事，但半自动化地进行必要的更改以使应用程序为 React 19 做好准备肯定是有趣的。

**长按识别二维码查看原文**

https://dev.to/herrington_darkholme/migrate-to-react-19-with-ast-grep-28op

Herrington Darkholme

**HTML 属性 vs DOM 属性** —— 它们是不同的，但经常被耦合。Jake 描述了这种差异，以及为什么这很重要。他还谈到了框架如何处理这种对比，以及它如何影响到目前为止 React 对自定义元素的支持。

**长按识别二维码查看原文**

https://jakearchibald.com/2024/attributes-vs-properties/

Jake Archibald

**React 19 Beta：异步事务的重大更新已经到来**

**长按识别二维码查看原文**

https://coderoasis.com/react-19-beta/

CoderOasis

**通往更清洁的 React 架构之路：API 层和获取函数**

**长按识别二维码查看原文**

https://profy.dev/article/react-architecture-api-layer-and-fetch-functions

Johannes Kettmann

**看看现在如何在 React 和 Svelte 中使用 TC39 / ES 内置 Signal**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=HSVcZa5yTKE

Jack Herrington

**将 React 与 Ruby on Rails 7 集成的方法**

**长按识别二维码查看原文**

https://thoughtbot.com/blog/how-to-integrate-react-rails

Dave Iverson

**通过构建云照片应用程序学习 Next.js 和 Cloudinary**

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/create-a-google-photos-clone-with-nextjs-and-cloudinary/

Colby Fayock

**快讯：**

- Zachary Lee 有一个关于 React 19 Beta 的快速指南，代码驱动的方式来介绍。
    
    **长按识别二维码查看原文**
    
    https://javascript.plainenglish.io/react-19-beta-release-a-quick-guide-05678e2ed571?gi=b8a271ebd18b
    

- 📅 React Rally 2024 将于今年 8 月 12-13 日在犹他州举行，并已经有一些出色的演讲者排队。门票已经开始销售。
    
    **长按识别二维码查看原文**
    
    https://www.reactrally.com/
    

- 🗓️ 流行的 React 日期选择器 和 React 日历 组件的重大新版本已经发布，支持 React 19。
    
    **长按识别二维码查看原文**
    
    https://projects.wojtekmaj.pl/react-date-picker/
    

- Andy Bell 分享了他对 React 的支持自定义元素的想法。
    
    **长按识别二维码查看原文**
    
    https://piccalil.li/blog/upcoming-custom-element-support-in-react/
    

🛠 代码与工具

**extension.js：零配置，跨浏览器扩展开发入门** —— 目标是让它像 `npx extension create my-extension` 一样简单，以开始构建你自己的 React 驱动的浏览器扩展。GitHub 仓库。

**长按识别二维码查看原文**

https://extension.js.org/

Cezar Augusto

**Divz：一个在 3D Z 轴上滚动、滑动和缩放元素的组件** —— 包裹在包含各种东西（比如图片）的各种 DIV 周围，Divz 使得在它们之间轻松切换变得容易，而且视觉效果引人注目。主页上有一些实时演示。

**长按识别二维码查看原文**

https://github.com/lewhunt/divz

Lewis Hunt

**uikit：将用户界面带到 React-Three-Fiber** —— 使用 @react-three/fiber 为 Three.js 构建 3D 用户界面，支持许多常见的 UI 控件。非常适合游戏，XR/AR 和空间场景。GitHub 仓库。

**长按识别二维码查看原文**

https://docs.pmnd.rs/uikit/getting-started/introduction

Bela Bohlender

**React Spaces：将页面或容器划分为可滚动和可调整大小的 ‘Spaces’** —— 它很像是 1990 年代风格的电脑系统画面。GitHub 仓库。

**长按识别二维码查看原文**

https://allaneagle.com/projects/react-spaces

Allan Eagle

**React-Spring 可视化工具** —— React Spring 是一个流行的基于弹簧物理的动画库，用于为组件添加动画，这是一个实时更改配置展示不同效果的 Demo。

**长按识别二维码查看原文**

https://react-spring-visualizer.com/

Joost Kiens

**版本发布：**

- **📄 React-PDF v8.0** – 显示 PDF 的 React 组件。现在支持 React 19。

- **TanStack Virtual v3.5** – 用于虚拟化可滚动元素的无头 UI。

- **ka-table v9.0** – 轻量级表格组件。

- **😀 Emoji Mart v5.6** – Emoji 选择组件。

- **Preact v10.21** – 3KB 的 React 兼容替代品。

- **MUI X v7.3.1** – 流行的 React 组件套件。

🙋🏻‍♀️