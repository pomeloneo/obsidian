# React 中文周刊 #216 - 用 SRCL 来打造终端风格的 React 应用程序

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539409&idx=1&sn=f47f02bae1f3dc006ca610a5a18635b8&chksm=e9211133de569825bc3bdb1fab51aca70ae2e00886c3a00039c6ef9102eb67b81b161998469b\#rd  
> 抓取时间: 2026/2/2 23:42:46

---

> 本期看点：用 SRCL 来打造终端风格的 React 应用程序，Storybook v8.5 引入实时 Axe 无障碍检查并支持 React 19，React Native v0.77 发布并扩展 CSS 样式能力，Reanimated 4 发布首个 beta 版本，深入解析 Reeact 应用程序初始加载性能。

> 编辑：TimLi

🔥 本周热门

**SRCL：打造终端风格的 React 应用程序** —— 项目主页就是一个生动的演示。SRCL 提供了一套 React 组件和样式，用于重现等宽字体、终端般的视觉效果。

**长按识别二维码查看原文**

https://www.sacred.computer/

Internet Development Studio Company

**Storybook v8.5：UI 组件构建和测试工坊** —— Storybook 现在可以在你构建组件时实时运行 Axe a11y (无障碍)检查，这对于满足无障碍要求和规范至关重要。此外还内置了对 React 19、Vite 6 和 Angular 19 的支持，以及实验性的 Bun 支持和项目代码覆盖率报告功能。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-8-5/

Michael Shilman

**React Native v0.77 带来全新样式功能** —— 随着新架构的落地，React Native 团队开始专注于新特性开发。v0.77 试图通过支持新的 CSS 属性来与 Web 开发保持一致，这显著扩展了可用的样式选项，包括 `display: contents`。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2025/01/21/version-0.77

Novak、Chami、Friedman 和 Hogan

**为热门 React 应用程序选择状态管理库** —— ……以及我们为什么选择了 MobX。Photoroom 团队对 Zustand、MobX 和 Redux 进行了深入测试，并解释了他们为什么对选择 MobX 感到满意。

**长按识别二维码查看原文**

https://www.photoroom.com/inside-photoroom/picking-a-state-management-library-why-we-went-with-mobx-

Eliot Andres（Photoroom）

**📊 深入解析初始加载性能** Nadia Makarevich

**长按识别二维码查看原文**

https://www.developerway.com/posts/initial-load-performance

**📄 100 个 React 应用程序创意** —— 如果你正在寻找灵感？React Practice

**长按识别二维码查看原文**

https://reactpractice.dev/articles/100-react-app-ideas/

**📄 我是如何将原生 React Native 应用程序迁移到 Expo 的** Alfred Lieth Årøe

**长按识别二维码查看原文**

https://expo.dev/blog/how-i-migrated-my-bare-react-native-app-to-expo

**📄 使用 Next.js 构建单页应用程序** Next.js 文档

**长按识别二维码查看原文**

https://nextjs.org/docs/app/building-your-application/upgrading/single-page-applications

**快讯：**

- Stupid Simple React（ssreact）是一个将 Preact 和 JSX 编译器结合的项目，只需导入一个 21KB 的脚本就能直接在 HTML 中运行 React。这是个有趣的想法，你可以在这里体验。
    
    **长按识别二维码查看原文**
    
    https://ssreact.com/
    

- 一年前，Kelly Sutton 写了一篇关于他的公司如何放弃 React 的文章，但结果如何呢？在《告别 React 一年后》中，他分享了这一年来的经历。
    
    **长按识别二维码查看原文**
    
    https://kellysutton.com/2024/01/15/moving-on-from-react.html
    

🛠 代码与工具

**Reanimated v4：新颖但不失熟悉感** —— Software Mansion 发布了 Reanimated 4 的首个 beta 版本，这是 React Native 应用程序中创建流畅、高性能动画的流行解决方案的最新版本。看起来非常有前景。

**长按识别二维码查看原文**

https://blog.swmansion.com/reanimated-4-is-new-but-also-very-familiar-b926dd59aa40?gi=3a0ddd07c8bb

Krzysztof Magiera

**Puck v0.18：自托管的 React 可视化编辑器** —— 现在包含了一个全新的拖放引擎，完全支持 CSS grid 和 flexbox，可实现高级布局。GitHub 仓库和在线演示。

**长按识别二维码查看原文**

https://github.com/measuredco/puck/releases/tag/v0.18.0

Measured Corporation Ltd.

**FortuneSheet v1.0：基于 React 的电子表格控件** —— v1.0 切换到了更快的公式解析和计算系统。这里有一个在线 Storybook 演示。

**长按识别二维码查看原文**

https://github.com/ruilisi/fortune-sheet

苏州睿理思科技有限公司

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- Bun 的最新版本为其 `Bun.serve()` 功能添加了按需前端打包功能，这意味着你可以在共享后端服务器中使用 HTML 导入来按需构建单页 React 应用程序。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.1.44
    

- Dr. Axel Rauschmayer 深入探讨了 TypeScript 的枚举特性。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/01/typescript-enum-patterns.html
    

- Learn Yjs 是一套正在开发中的实用教程，用于学习如何使用 Yjs CRDT (冲突解决数据类型)库构建实时协作应用程序。
    
    **长按识别二维码查看原文**
    
    https://learn.yjs.dev/
    

- ArkType 2.0 提供了一种有趣的方式，可以为运行时和编辑器中的验证推断 1:1 的 TypeScript 类型，在每次按键时都能得到类型级别的反馈。
    
    **长按识别二维码查看原文**
    
    https://arktype.io/docs/blog/2.0
    

- 你知道吗？所有主流浏览器现在都支持直接链接到网页中的文本片段了。
    
    **长按识别二维码查看原文**
    
    https://frontendmasters.com/blog/cool-people-link-to-text-fragments/
    

**版本发布：**

- **React Testing Library v16.2** —— 鼓励良好实践的 DOM 测试工具。增加了对 React 错误处理程序的支持。

- **React Admin v5.5** —— 用于构建 B2B 前端界面的框架。现已支持 React 19 和 React Router 7。

- **React Scan v0.1** —— 自动扫描性能问题并消除应用程序中的慢速渲染。

- **React Menu v4.3** —— 用于构建无障碍菜单和下拉框的组件。现已支持 React 19。

- **react-keyed-flatten-children v3.1** —— 在保留键的同时将数组和片段展平为一维数组。

- **BlockNote v0.23** —— “Notion 风格”的 block-based (基于块)编辑器。

- **Rspack v1.2**