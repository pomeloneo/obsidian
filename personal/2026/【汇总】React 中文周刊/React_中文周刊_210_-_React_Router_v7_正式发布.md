# React 中文周刊 #210 - React Router v7 正式发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538318&idx=1&sn=8e9b0df49ed0df33b5410cb516a239c1&chksm=e9211d6cde56947ae49c9e172a3d6ebed8faaebcd06dd57a44f18aaca586b8b62d6336429e64\#rd  
> 抓取时间: 2026/2/2 23:43:00

---

> 本期看点：React Router v7 发布，带来 Remix 中的热门功能并为 React 18/19 过渡提供支持；Vite v6.0 发布，引入实验性环境 API；Tremor 提供强大的 React 仪表板组件套件；TanStack Start 全栈 React 框架进入 beta 阶段。

> 编辑：TimLi

🔥 本周热门

**React Router v7 正式发布** —— Michael 对此做出了最好的解释：“v7 将 Remix 中所有你喜欢的功能都带回了 React Router。我们建议所有 Remix v2 用户都进行升级。对于大多数 React 生态系统用户来说，我们相信 React Router v7 将是连接 React 18 和 19 之间最平滑的桥梁。”该项目还推出了一个全新的主页。

**长按识别二维码查看原文**

https://remix.run/blog/react-router-v7

Michael Jackson

💡 Alem Tuzlak 发布了一个▶️ 关于是否应该立即升级的分析。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=s8H5-CZOlm0

**Vite v6.0 发布** —— 尽管 Vite 来自 Vue.js 的创建者，但凭借其速度、简单性和可扩展性的完美组合，它已经迅速成为 React 生态系统的核心。v6 在这些方面都有所加强，并引入了一个实验性的”环境 API”，让框架作者能够以更强大的方式使用 Vite。

**长按识别二维码查看原文**

https://vite.dev/blog/announcing-´vite6.html

Evan You 等

**基于特性的 React 架构** —— “在基于特性的架构中，每个特性都尽可能地与其他特性解耦。这样我们就能让组件及其数据获取函数专注于各自的领域。”

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-feature-architecture/

Robin Wieruch

**▶ 使用 AI 在 30 分钟内构建提词器应用程序** —— 如今使用 AI 工具构建应用程序并不罕见，但如果你从未见过这个过程，这是一个很好的示例，从开始到部署的全过程都有展示。作者使用了 Vercel 的 v0、Replit 和 Cursor。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=PbqYgK1xpms

Kilian Ekamp

**📄 从 Gatsby 迁移到 Eleventy** —— 从 React 框架转向 Node.js 静态站点生成方案。Matt Steele

**长按识别二维码查看原文**

https://steele.blue/gatsby-to-eleventy/

**📄 使用 React Three Fiber 创建动态地形变形** —— 让动画 3D 模型在雪地上留下脚印。Oguzhan Tufenk

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/11/27/creating-dynamic-terrain-deformation-with-react-three-fiber/

**📄 React 面试前要尝试的 7 个挑战** —— Corina Udrescu

**长按识别二维码查看原文**

https://reactpractice.dev/articles/7-challenges-to-do-before-a-react-interview/

**快讯：**

- 📉 上周我们介绍了 Aiden Bai 的 React Scan 工具，它可以检测 React 应用程序中的性能问题。Aiden 一直很忙，他用它发现了 GitHub 上渲染缓慢的原因（GitHub 已经修复了这个问题）。现在这个工具也提供了 CLI 版本。
    
    **长按识别二维码查看原文**
    
    https://react-scan.million.dev/
    

- 最新的 State of JavaScript 调查现已开放。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-js/2024?source=react_status
    

- TanStack Start 全栈 React 框架现已进入 beta 阶段。开发者 Leonardo 制作了一个▶️ 10 分钟的视频导览。
    
    **长按识别二维码查看原文**
    
    https://tanstack.com/start/latest
    

- Deno 正在向 USPTO 提起与 Oracle 的 JavaScript 商标之争。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-v-oracle
    

- TypeScript v5.7 已发布。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-7/
    

🛠 代码与工具

**Tremor：用于仪表板和图表的 React 组件套件** —— 使用 React、Tailwind CSS 和 Radix UI 构建，你可以通过复制粘贴组件或通过 npm 包来使用 Tremor。它提供了所有典型的仪表板 UI 元素，如图表、进度指示器、活动追踪器、手风琴、表格等。

**长按识别二维码查看原文**

https://tremor.so/

Tremor Labs

**Spoiled：一个逼真的”剧透”组件** —— 主页就是一个实时演示。这是一种在用户想要查看之前保持内容隐藏的巧妙方式。由 CSS Painting API 驱动，并提供静态图片作为后备方案。GitHub 仓库。

**长按识别二维码查看原文**

https://spoiled.vercel.app/

Alexey Taktarov

**TinyBase v5.4：本地优先应用程序的响应式数据存储** —— 这是一个强大的响应式数据存储，你可以将其作为应用程序的整个后端。v5.4 版本通过在 Cloudflare Durable Objects 上运行的 WebSocket 同步服务器提升了性能。

**长按识别二维码查看原文**

https://tinybase.org/guides/releases/\#v5-4

James Pearce

**React Burger Menu v3.1：画布外侧边栏组件** —— 提供多种效果和样式，由 CSS 过渡和 SVG 路径动画驱动。GitHub 仓库。

**长按识别二维码查看原文**

https://negomi.github.io/react-burger-menu/

Imogen Wentworth

**React Swipeable：滑动事件处理 Hook** —— 可定制、轻量级的 hook，提供管理滑动交互所需的所有信息。GitHub 仓库。

**长按识别二维码查看原文**

https://commerce.nearform.com/open-source/react-swipeable

Nearform

**🩻 dwv-react：React DICOM 格式医学图像查看器** —— DICOM 是用于分发医学图像（如 CT 或 MRI 扫描）的标准格式。

**长按识别二维码查看原文**

https://ivmartel.github.io/dwv-react/

ivmartel

**版本发布：**

- **Relay v18.2** —— Facebook 的响应式基于 GraphQL 的 React 框架。（主页）

- **React Native Share v12.0** —— 在应用程序之间共享简单数据。

- **lowlight v3.2** —— 用于虚拟 DOM 和非 HTML 内容的虚拟语法高亮。

- **React Admin v5.4** —— 用于构建 B2B 前端界面的框架。

- **🗓️ React DayPicker v9.4** —— 可定制的日期选择器。

- **Fortune Sheet v0.20** —— 类似 Excel 的电子表格控件。

- **Preact v10.25** —— 3KB 大小的 React 兼容替代品。

- **Ink v5.1** —— 使用 React 构建命令行应用程序。

- **React Tag Autocomplete v7.4**