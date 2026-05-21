# React 中文周刊 #73 - Relay 13 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247500242&idx=1&sn=26e5ce1fb006442a37bbb508a19b5a2b&chksm=e9218a30de560326af946c035a650e53110939a4efec35529e9965da20effb6d01ed207226d5\#rd  
> 抓取时间: 2026/2/2 23:47:57

---

> 本周看点：Facebook 团队发布 Relay 13：用于构建数据驱动的 React 应用框架。带你通过可视化的方式学习 useEffect 的概念，简单粗暴有效！

> 编辑：Yucohny、liu-jin-yi、QC-L

## 🔥 本周热门

**关于 `useEffect` 的可视化指南** — 前几期有介绍过作者编写的关于 **React 渲染的可视化指南系列**（比如 useMemo以及 Props），最近作者又把注意力转向了 `useEffect`。他制作了一系列的 GIF 来讲清楚这些概念，既巧妙又有效，对于不愿意读长篇大论的小伙伴来说，简直是福音。如果你想学习更多，还可以参阅 面向 React 开发人员的函数可视化工作原理。

**长按识别二维码查看原文**

https://alexsidorenko.com/blog/useeffect/

Alex Sidorenko

Relay 13 发布：用于构建数据驱动的 React 应用框架 — 一种避免在 React 应用中使用命令式 API 来获取数据的方式。相反，你可以使用 GraphQL 定义你数据依赖，剩下的交由 Relay 来完成。该版本最大的亮点是引入了 全新的 Relay 编译器。

**长按识别二维码查看原文**

https://github.com/facebook/relay/releases/tag/v13.0.0

Facebook

如何组织 React 项目的目录结构 — 作者认为 `src` 目录的结构应该更加标准化，思路和 _Ruby on Rails_ 采用的方式类似。文章介绍了他的观点，让这个项目不再混乱不堪。

**长按识别二维码查看原文**

https://blog.testdouble.com/posts/2021-11-30-tdr-project-layout/

Tommy Groshong

## 🛠 代码与工具

react-tree-graph：将树形数据渲染为可视化的树形 SVG — 这是一个树形渲染组件库，目前已经迭代了 7 个大版本。拥有大量的 demo 以及 例子 可供参考。

**长按识别二维码查看原文**

https://jpb12.github.io/react-tree-graph/

James Brierley

React-Grid-Layout — 该库是一个类似于 Packery 或 Gridster 的可拖动网格组件。该库具有非常丰富的 示例 可供参考。点击查看 在线示例。

**长按识别二维码查看原文**

https://github.com/react-grid-layout/react-grid-layout

RGL

Elf：基于 RxJS 的响应式状态管理库 — Elf 是一个建立在 RxJS 之上的响应式不可变状态管理解决方案。它使用自定义 RxJS 运算符来查询状态和纯函数来更新它。点击查看 在线示例。

**长按识别二维码查看原文**

https://github.com/ngneat/elf

Netanel Basal

ActiveMDX：更容易重组和重用文档 — 该库基于 MDX 进行了二次封装。

**长按识别二维码查看原文**

https://active-mdx.soederpop.com/

Jonathan Soeder

**Markdown Editor v3.9**：简单的、基于 React 的带有预览功能的 Markdown 编辑器

**长按识别二维码查看原文**

https://github.com/uiwjs/react-md-editor

uiw

**Rendition**：Figma 上将 UI 图转为 React 代码的插件

**长按识别二维码查看原文**

https://www.figma.com/community/plugin/1031998871372194709/Rendition%3A-Figma-%3EReact-in-one-click

Caleb Ouellette and Robert Nowell

**use-cannon v4.5**：由 react-three-fiber 提供的动画 Hook

**长按识别二维码查看原文**

https://github.com/pmndrs/use-cannon

Poimandres

## ⚡️ 快讯：

- **Reacord** — 使用 React 和 Discord API 创建交互式 Discord 消息。
    
    **长按识别二维码查看原文**
    
    https://reacord.fly.dev/
    

- **react-grid-heatmap** — 流行的热力图数据可视化库。
    
    **长按识别二维码查看原文**
    
    https://github.com/arunghosh/react-grid-heatmap
    

- **react-use-focus-trap** — 一个非常有用的 React Hook 来捕获可聚焦的元素。
    
    **长按识别二维码查看原文**
    
    https://github.com/activenode/react-use-focus-trap
    

- **react-query-helper** — React Query 很好，但将变得更简单以及更轻松。
    
    **长按识别二维码查看原文**
    
    https://github.com/dano-inc/react-query-helper
    

- **react-google-calendar-api** — 将您的应用与 Google 日历集成。
    
    **长按识别二维码查看原文**
    
    https://github.com/Kubessandra/react-google-calendar-api
    

Calories-In：新的一年，新的自我！ — 在一些人的新年决心中，或许有着常年保持着减肥或改善健康状况的想法——但却通常是通过吃得更好来实现的。因此，有什么比 React 驱动的膳食计划更好的方式来迎接 2022 年的呢！这将由 React Status 阅读器提交，您可以查看 实时版本 或观看 视频演示。

**长按识别二维码查看原文**

https://github.com/vangelov/calories-in

Vladimir Angelov

## 🙋🏻‍♀️