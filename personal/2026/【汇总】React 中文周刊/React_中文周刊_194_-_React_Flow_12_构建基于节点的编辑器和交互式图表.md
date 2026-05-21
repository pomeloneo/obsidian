# React 中文周刊 #194 - React Flow 12: 构建基于节点的编辑器和交互式图表

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533375&idx=1&sn=d1d6b8b34b04af0b1c7822a487083a9d&chksm=e92108ddde5681cb25a50a446a944ab67670ea87878f2b8ea8c0abc0dbf8fa3d3149daf899ee\#rd  
> 抓取时间: 2026/2/2 23:43:34

---

> 本期看点：React Flow 发布了 12 版本，支持服务器端渲染、暗黑模式、更多的 Hook 和工具，并通过 TSDoc 实现了更好的开发体验。并且，现在已经合入 xyflow, 又叫 @xyflow/react。

> 编辑：TimLi

🔥 本周热门

**React Flow 12: 构建基于节点的编辑器和交互式图表** — 如今更广为人知的是 xyflow ，这个成熟的库能轻松创建“基于节点的用户界面” ，在其中可以按照自己的选择将众多交互式组件连接在一起。第 12 版引入了服务器端渲染支持、暗黑模式、更多的钩子和助手，并通过 TSDoc 实现了更好的开发体验。

**长按识别二维码查看原文**

https://www.xyflow.com/blog/react-flow-12-release

Moritz Klack 和 John Robb

**隐蔽的 React 内存泄漏：React 编译器也无法拯救** — 闭包可能导致 React 中的内存泄漏，虽然新的、令人兴奋的 React 编译器可以解决很多问题，并使大多数代码库的性能更高，但了解棘手的边缘情况是有好处的。

**长按识别二维码查看原文**

https://schiener.io/2024-07-07/react-closures-compiler

Kevin Schiener

**▶ React 19 的** `**use**` **Hook 可能影响应用性能** — React 19 中的新 `use` Hook 看起来很棒。然而，存在一些潜在问题，需要进行一些探索和解释。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=t6MeFVF3V9I

Jack Herrington

**通过构建支持 Suspense 的库来学习 Suspense** — 还有什么比亲自动手更好的学习方式呢 ？尤其是当涉及到一个文档有点尴尬的主题时。

**长按识别二维码查看原文**

https://www.bbss.dev/posts/react-learn-suspense/

Slava Knyazev

**▶ 在 Vite 和 Next.js 中使用 React 19** — Vercel 的产品副总裁 从一个仅使用客户端的 React 应用程序开始 ，使用 Vite，并探讨 React 19 如何让生活更美好，然后转向 Next.js 示例。（32 分钟）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=AdkNcFUsRQQ

Lee Robinson （Vercel）

**▶** `**useCallback**` **与** `**useMemo**` — 虽然表面上它们可能看起来相似，但在短短 11 分钟内，我们了解了它们的差异，以及为什么引用相等性是一个如此重要的概念。更棒的是，这是他的第一个 YouTube 视频！

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=M8NaTJN8xh4

Jan Hesters

**通往更干净（的）React 架构之路：领域逻辑** — 这是正在进行的系列的最新部分，对一个有很多不良实践的 React 代码库逐步进行重构。

**长按识别二维码查看原文**

https://profy.dev/article/react-architecture-domain-logic

Johannes Kettmann

**📄 使用 Skia 和 Reanimated 在 React Native 中构建图像滑块** Omowunmi Sogunle

**长按识别二维码查看原文**

https://www.tweag.io/blog/2024-07-04-image-transition-react-native-skia/

**📄 React 的状态管理库简史** Prabashwara Seneviratne

**长按识别二维码查看原文**

https://www.frontendundefined.com/posts/monthly/react-state-management-libraries-history/

🛠 代码与工具

**TinyBase v5.0: 面向本地优先应用的响应式数据存储** — 一个能充当应用响应式后端的数据存储。如果想减少应用后端带来的烦恼那这就很适合，其中包括与 React 的绑定和预先构建的响应式组件。v5.0 包含了新的mergeableStore 类型，能够将数据包装为无冲突复制数据类型(CRDT)。

**长按识别二维码查看原文**

https://tinybase.org/guides/releases/\#v5-0

James Pearce

**版本发布：**

- **react-jsx-parser v2.0** – 解析 JSX 并输出渲染的组件。现在支持 React 18+。

- **React Native Reanimated v3.13** – 重新实现了 React Native 的 Animated 。

- **🗓️ schedule-x v1.50** – 采用 Material Design 的事件日历和日期选择器。

- **📅 React Date Picker v7.3** – 简单的日期选择器组件。

- **Storybook v8.2** – 前端组件和 UI 工作坊。

- **Jotai v2.9** – 针对 React 的简单、灵活的状态管理。

- **PrimeReact v10.7** – 广泛的 UI 组件库。

- **MUI X v7.9** – 流行的 React 组件套件。

🙋🏻‍♀️