# React 中文周刊 #219 - React 2024 年度调查结果出炉

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539834&idx=1&sn=2cdc5984426a15e2f896dce9002ecbae&chksm=e9211798de569e8e65bece28fb6c4a7ff7954e910d01acf2df441593f6f736a80546a4692af6\#rd  
> 抓取时间: 2026/2/2 23:42:40

---

> 本期看点：React 2024 年度调查显示 forwardRef 和 memo 是开发者最头疼的问题，Chrome 即将推出新的 moveBefore DOM 方法并已获 React 团队支持，PlayCanvas 发布面向 React 的 3D Web 开发框架，Vercel 推出新一代”流动计算”功能升级 Functions 服务。

> 编辑：TimLi

🔥 本周热门

**React 2024 年度调查结果出炉** —— 这份来自近 8000 名开发者的调查结果内容丰富，值得仔细研究。调查显示，`forwardRef` 和 `memo` 是 React 开发者最头疼的两个问题，Redux 仍然是状态管理库中的领头羊，而单页应用（SPA）目前仍然是 React 最主要的使用场景。

**长按识别二维码查看原文**

https://2024.stateofreact.com/en-US

Devographics

**2025 年如何开始一个 React 项目** —— 虽然创建 React 项目的方式有很多，Robin 在这里分析了几种流行方案的优缺点。（这篇文章你可能看过，不过已经更新到 2025 年版本了。）

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-starter/

Robin Wieruch

**我为什么要用 React 重写 ProseMirror 的渲染器** —— 一位纽约时报的前工程师分享了他多年来将 React 与 ProseMirror 集成的经验。ProseMirror 是一个用于构建富文本编辑器的工具包，但它与 React 配合的问题一直广受诟病。这篇文章深入探讨了其中的技术挑战。

**长按识别二维码查看原文**

https://smoores.dev/post/why_i_rebuilt_prosemirror_view/

Shane Friedman

**📄 我们用 Go 和 WebAssembly 替换了 React 前端** —— 虽然你可能不会这么做，但了解别人的经历还是很有趣的。Alex Suraci（来自 Dagger 博客）

**长按识别二维码查看原文**

https://dagger.io/blog/replaced-react-with-go

**📄 2025 年该选择哪个富文本编辑器框架？** —— 一份当前活跃开发的所见即所得编辑器选项清单。Dexemple 和 Rowny（来自 Liveblocks）

**长按识别二维码查看原文**

https://liveblocks.io/blog/which-rich-text-editor-framework-should-you-choose-in-2025

**📄 用 LLM 和 React 设计背景** —— 这个想法很棒。Ben Shumaker

**长按识别二维码查看原文**

https://www.vigilant.run/blog/designing-backgrounds-with-llms-and-react

**📄 React 中的单一职责原则：组件专注度的艺术** Christian Ekrem

**长按识别二维码查看原文**

https://cekrem.github.io/posts/single-responsibility-principle-in-react/

**快讯：**

- React Native 团队发布了最近一次贡献者峰会的精彩总结。如果你是 React Native 用户，一定要看看。
    
    **长按识别二维码查看原文**
    
    https://reactnative.dev/blog/2025/02/03/react-native-core-contributor-summit-2024
    

- Chrome 即将推出新的 `moveBefore` DOM 方法，可以在不重置元素状态的情况下移动 DOM 树中的元素。React 团队已经在着手使用这个特性了。
    
    **长按识别二维码查看原文**
    
    https://chromestatus.com/feature/5135990159835136
    

- PlayCanvas 展示了 PlayCanvas React，这是一种全新的、对 React 友好的 3D Web 体验构建方式。
    
    **长按识别二维码查看原文**
    
    https://blog.playcanvas.com/declarative-3d-with-playcanvas-react/
    

🛠 代码与工具

**React D3 Tree：交互式树形图组件** —— 非常适合用来展示家谱或组织架构图。这里有几个实用的示例。使用 D3 进行渲染。GitHub 仓库。

**长按识别二维码查看原文**

https://bkrem.github.io/react-d3-tree/

Ben Kremer

**我一直想要的 React 数据表格** —— 介绍了一个基于 shadcn/ui 的高性能、简洁的数据表格组件（GitHub 仓库）。你可以在这里查看在线演示。

**长按识别二维码查看原文**

https://www.openstatus.dev/blog/data-table-redesign

Maximilian Kaske

**Quicky：轻松自托管 Next.js 和 Node.js 应用程序** —— 一个简化 Next.js 和 Node 项目部署和管理的命令行工具。

**长按识别二维码查看原文**

https://quicky.dev/

Quicky

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- 📺 继精彩的▶️ 《Node.js：纪录片》之后，制作团队带来了▶️ 全新的 Angular 纪录片，如果你想了解竞品，不妨看看 ;-)
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=LB8KwiiUGy0
    

- Style Observer 是 Lea Verou（以制作精良的库而闻名）推出的一个用于观察 CSS 属性变化的新库。
    
    **长按识别二维码查看原文**
    
    https://lea.verou.me/blog/2025/style-observer/
    

- Alex MacArthur 展示了七种不同的方法来拆分 JavaScript 中的长任务，主要针对浏览器使用场景。
    
    **长按识别二维码查看原文**
    
    https://macarthur.me/posts/long-tasks/
    

- 被正则表达式的格式吓到了吗？Human Regex 尝试通过命名方法提供一个流畅的链式 JavaScript API 来创建正则表达式。
    
    **长按识别二维码查看原文**
    
    https://github.com/rajibola/human-regex
    

- Vercel 推出了新的“流动计算”选项，这本质上是其 Functions 服务的进化版。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/introducing-fluid-compute
    

**版本发布：**

- 🖼️ **React Image Gallery v1.4** —— 带缩略图支持的轮播图片画廊组件。现已支持 React 19。

- **React Native BLE PLX v3.5** —— 一个在 React Native 应用程序中使用蓝牙低功耗设备的工具。

- **Cursify** —— 使用 React、Tailwind 和 Framer Motion 构建的动画光标组件。（在线演示）

- **React Ace v14.0** —— 将 Ace 代码编辑器集成到 React 应用程序中。现已支持 React 19。

- **Turborepo v2.4** —— 新版本重点改善了开发者体验。