# React 中文周刊 #196 - 2023 年 React 调查报告结果出炉

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533686&idx=1&sn=6cd3e242e168271c6bdeaddc2ac000d0&chksm=e9210f94de568682a266c19918fd7d2a582156f95969536c8a1383664d22f0506052c3274195\#rd  
> 抓取时间: 2026/2/2 23:43:29

---

> 本期看点：2023 年 React 调查于去年 12 月进行，来自超过 13,000 名受访者的结果终于出炉了，其中包含许多有趣的细节。

> 编辑：TimLi

🔥 本周热门

**2023 年 React 调查报告结果出炉** —— 2023 年 React 调查于去年 12 月进行，来自超过 13,000 名受访者的结果终于出炉了。其中包含许多有趣的细节，我们了解到：

**长按识别二维码查看原文**

https://2023.stateofreact.com/zh-Hans/

- 单页应用程序（SPA）仍然是大多数开发者的首选。

- `forwardRef` 是导致最多问题的 React API。

- 🎧 React 开发者正在收听的播客。

- Python 和 PHP 是最常见的后端语言（在 JS/TS 之后）。

- MUI 和 React Bootstrap 在组件库中领先。

- React 18 的使用率很高。

Devographics

**Airbnb 如何平稳升级 React** —— Airbnb 最近完成了所有面向 Web 的网站从 React 16 到 React 18 的升级。我们中很少有人能在如此大型的系统上工作，但 Airbnb 的策略和流程可能会为你自己的升级提供一些灵感。

**长按识别二维码查看原文**

https://medium.com/airbnb-engineering/how-airbnb-smoothly-upgrades-react-b1d772a565fd

Andre Wiggins（Airbnb）

📺 在 YouTube 上，Theo 有一个视频讲述了《纽约时报》通过升级到 React 18 看到性能改进的情况。（我们最近曾介绍过《纽约时报》的文章，这启发了 Theo 的观点。）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=_6kDnkeReKo

**如何为你的应用程序选择最佳渲染策略** —— 了解静态站点生成（SSG）、服务器端渲染（SSR）、客户端渲染（CSR）、增量静态再生（ISR）和部分预渲染（PPR）之间的区别。

**长按识别二维码查看原文**

https://vercel.com/blog/how-to-choose-the-best-rendering-strategy-for-your-app

Alice Alexandra Moore（Vercel）

**DRY —— 糟糕抽象的常见来源** —— 不惜一切代价避免重复有时会导致粗糙、难以维护的代码。思考实际涉及的关注点，你可能会找到更好的方式来分解问题。

**长按识别二维码查看原文**

https://swizec.com/blog/dry-the-common-source-of-bad-abstractions/

Swizec Teller

**使用** `**useId()**` **而不是手动创建 ID** —— 为什么要使用 `useId` 而不是手动创建的 ID 来链接两个 DOM 节点以实现无障碍性。

**长按识别二维码查看原文**

https://reacttraining.com/blog/use-useid-instead-of-hand-making-ids

Brad Westfall

**📄 如何使用懒加载优化 Next.js 应用程序性能** Tapas Adhikary

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/next-js-performance-optimization/

**📄 用 React Table 渲染 Prisma 查询：低代码方式** Yiming（ZenStack）

**长按识别二维码查看原文**

https://zenstack.dev/blog/react-table

**快讯：**

- Astro v4.12 已发布，实验性支持**服务器岛屿**，这是一种集成静态 HTML 和服务器端生成组件的方式。你可以在这里看到演示。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/astro-4120/
    

- Vercel 的 Turbopack 打包工具正在搬家到 Next.js 的 monorepo 中。虽然它不是 Next.js 独有的，但 Vercel 团队希望更专注于其开发，并认为这将是一个更好的开发场所。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/turbopack-moving-homes
    

🛠 代码与工具

**React Native Filament：React Native 的 3D 渲染引擎** —— 它是快速、原生的 3D 渲染，带有 React 风格。渲染在单独的线程上进行以提高效率，在 iOS 上，Filament 使用高效的原生 Metal API。GitHub 仓库和相当不错的文档。

**长按识别二维码查看原文**

https://margelo.github.io/react-native-filament/

Marc Rousavy

**📅 React DayPicker：创建日期选择器控件的组件** —— 有很多日期选择组件，但很少有十年历史和 6000 个 GitHub 星标的。DayPicker 专注于提供基础功能，让你可以根据需要进行样式设计和自定义 —— 它还符合现代无障碍要求。GitHub 仓库。

**长按识别二维码查看原文**

https://daypicker.dev/

Giampaolo Bellavite

**🗺️ GeoStyler v15.0：用于地图样式的 UI 组件** —— 在浏览器中构建灵活的地图样式用户界面。

**长按识别二维码查看原文**

https://geostyler.org/

GeoStyler

**版本发布：**

- **React Spectrum，夏季发布** —— Adobe Spectrum 设计系统的 React 实现。

- **React Menu v4.2** —— 用于构建无障碍菜单、下拉菜单、子菜单等的组件。

- **react-native-bootsplash v6.0** —— 在启动过程中显示启动屏幕。

- **Tinybase v5.1** —— 用于本地优先应用程序的反应式数据存储。

- **Wasp v0.14** —— Wasp 是一个类似 Rails 的框架，用于 React、Node.js 和 Prisma。

- **Preact v10.23** —— 3KB 大小的 React 兼容替代品。

- **MUI X v7.11** —— 流行的 React 组件套件。

🙋🏻‍♀️