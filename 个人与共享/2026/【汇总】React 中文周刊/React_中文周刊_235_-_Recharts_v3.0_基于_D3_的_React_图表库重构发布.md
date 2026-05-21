# React 中文周刊 #235 - Recharts v3.0 基于 D3 的 React 图表库重构发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542302&idx=1&sn=693afd0750bc81fd04d17786f3b3fd5d&chksm=e9216dfcde56e4ea0c9c75a3c18661bf1e5133540274bdd98ec441a338938966a5b6edd0f097\#rd  
> 抓取时间: 2026/2/2 23:42:05

---

> 本期看点：Recharts v3.0 发布并带来大规模重构，Vercel Ship 2025 大会，SST v3 展示现代 AWS Serverless 基础设施方案，三行代码将任意 React 应用程序连接到 MCP 服务器，使用 RN 构建 macOS 桌面应用程序。

> 编辑：TimLi

🔥 本周热门

**Recharts v3.0：基于 D3 的 React 图表库** —— 这是一个基于 SVG 和组件的流行图表库的重大重构版本。它提供多种类型的折线图、面积图、柱状图、散点图、组合图、饼图和雷达图，并附带示例代码。GitHub 仓库。

**长按识别二维码查看原文**

https://github.com/recharts/recharts/releases/tag/v3.0.0

recharts

**▶ Vercel Ship 2025 大会** —— Vercel 的 Ship 2025 大会已经结束，但你可以通过这个视频回顾一下。里面有很多精彩内容，包括：如何迁移到 Vercel，从 SEO 到 AEO 面向 AI 引擎优化，使用 Next.js 和 Vercel 重建电子商务网站。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=EfiKu56xvJk

Vercel

**▶ 使用 React Native 构建 macOS 桌面应用程序** —— React Native 不仅可以用于移动应用程序，还可以用于构建 Mac、电视和 Windows 应用程序。Jack 用 14 分钟展示了如何用它为 Mac 构建一个 AI 聊天机器人应用程序。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Apy672AQb4U

Jack Herrington

**SST v3 发布：现代 AWS Serverless 基础设施** —— SST 是一个使用 TypeScript 定义全栈应用程序基础设施的框架。这篇文章演示了如何使用 SST 在 AWS 上部署 React（和 Hono）全栈应用程序，并将 SST 与 Terraform 和 CloudFormation 等替代方案进行了比较。

**长按识别二维码查看原文**

https://spin.atomicobject.com/sst-v3-for-aws-serverless/

Nathan Papes

**📄 将 React 的 引入原生 JavaScript** Joeri Sebrechts

**长按识别二维码查看原文**

https://plainvanillaweb.com/blog/articles/2025-06-12-view-transitions/

**📄 深入理解 React 重渲染：触发原因及其重要性** Serhii Shramko

**长按识别二维码查看原文**

https://shramko.dev/blog/react-rerender

**📄 使用 Cursor 将我的博客从 WordPress 迁移到 Next.js 和 Vercel** Eric Dodds

**长按识别二维码查看原文**

https://www.ericdodds.com/blog/using-cursor-to-migrate-my-wordpress-blog-to-nextjs-and-vercel

**📄 AI 能重建 Rails 页面到 Next.js 吗？我们试了试……** Jimmy Thigpen

**长按识别二维码查看原文**

https://thoughtbot.com/blog/can-ai-rebuild-a-rails-page-in-next-js-we-tried-it

**📺 在 Expo 应用程序中使用 TanStack Query：无与伦比的开发者和用户体验提升** Devlin Duldulao

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=QTQm4TbarsI

**快讯：**

- Vite 7.0 已发布。如果你要从 v6 升级，这里有迁移指南。
    
    **长按识别二维码查看原文**
    
    https://vite.dev/blog/announcing-vite7.html
    

- Shopify 的 William Candillon 探讨了 React Native 中高级图形的未来，包括 React Native Skia、WebGPU、Three.js 以及新的 Skia Graphite 后端如何改变游戏规则。
    
    **长按识别二维码查看原文**
    
    https://shopify.engineering/webgpu-skia-web-graphics
    

- Certificates.dev 现在提供 React 认证。
    
    **长按识别二维码查看原文**
    
    https://certificates.dev/react
    

🛠 代码与工具

**三行代码将任意 React 应用程序连接到 MCP 服务器** —— 在上周发布前，我们简单提到了 Cloudflare 的新 use-mcp hook。现在这里有一篇完整的文章，详细介绍了它在快速创建 Model Context Protocol (MCP) 客户端方面的优势。

**长按识别二维码查看原文**

https://blog.cloudflare.com/connect-any-react-application-to-an-mcp-server-in-three-lines-of-code/

Cloudflare

**Warka：用于电子墨水显示屏的 React 框架** —— 由多个部分组成，包括使用 React 编写的前端、基于 Python 的服务器，以及使用 ESP32 驱动的电子墨水显示设备。这里有实物照片。

**长按识别二维码查看原文**

https://github.com/k3nz0/Warka

Moez Ezzeddine

**🔊 Soundz：为组件添加音效的另一种方式** —— 继 react-sounds 和 use-sound 之后，这是一个为组件添加音效的全新尝试。这里有多个在线示例。

**长按识别二维码查看原文**

https://soundzjs.vercel.app/

Kaycee Ingram

**react-force-graph：2D、3D、VR 和 AR 力导向图** —— 一个用于创建复杂网络/图形关系可视化的工具。这里有一个大型演示以及多个带源码的示例。

**长按识别二维码查看原文**

https://github.com/vasturiano/react-force-graph

Vasco Asturiano

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- ⭐ CKEditor JavaScript 富文本编辑器的创建者深入解释了他们如何将编辑器的包体积减少 40%。这是一篇值得一读的好文章。
    
    **长按识别二维码查看原文**
    
    https://ckeditor.com/blog/how-we-reduced-ckeditor-bundle-size/
    

- 流行的服务器端 JavaScript 运行时替代品 Bun v1.2.17 支持服务器端代码的预先打包，并进一步提升了 Node.js 兼容性。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.17
    

- AdonisJS Node.js Web 应用程序框架正在转变方向，正在努力实现 AdonisJS 7 的路线图。
    
    **长按识别二维码查看原文**
    
    https://adonisjs.com/blog/roadmap-to-adonisjs-7
    

- Dr. Axel Rauschmayer 分享了一些在 JavaScript 中让正则表达式更易用的技巧。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/06/javascript-regexp-tips.html
    

- 如果你厌倦了复杂的 Web 语法高亮方案， 是一个有趣的新自定义元素，它使用 CSS Custom Highlight API 来避免无尽的 元素。
    
    **长按识别二维码查看原文**
    
    https://andreruffert.github.io/syntax-highlight-element/
    

**版本发布：**

- **ReMDX v0.16** —— 使用 React 和 MDX 构建简约演示文稿。(示例)

- **Intergalactic v16.4** —— 设计系统和 50+ React 组件库。

- **React Admin v5.9** —— 构建 B2B 前端界面的框架。

- **rn-swiper-list v2.5** —— React Native 版 Tinder 风格滑动组件。

- **MDXEditor v3.37** —— Markdown 富文本编辑器组件。

- **BlockNote v0.32** —— “Notion 风格”的基于块的编辑器。

- **Node.js 24.3.0（当前版本）** 和 **Node 22.17.0（LTS）** 已发布。

- **SVGO v4.0** —— 流行的 Node.js SVG 优化工具的最新主要版本已发布。