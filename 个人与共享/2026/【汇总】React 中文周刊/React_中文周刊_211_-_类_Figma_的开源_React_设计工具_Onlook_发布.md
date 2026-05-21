# React 中文周刊 #211 - 类 Figma 的开源 React 设计工具 Onlook 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538444&idx=1&sn=26ae348362f5a764f1ef32929465bc89&chksm=e9211ceede5695f8ec896fe80ad5c5d63087722199502c1511ee7673e38beb57e5692c44046e\#rd  
> 抓取时间: 2026/2/2 23:42:58

---

> 本期看点：类 Figma 的开源 React 设计工具 Onlook 正式发布，支持实时设计到代码转换；MUI X v7.23.0 发布并添加完整的 React 19 支持；Radon IDE v1.0 推出专注于 React Native 开发的 IDE 工具；Astro 5.0 正式发布，React Three XR 发布 WebXR 开发教程。

> 编辑：TimLi

🔥 本周热门

**Onlook：一款类似 Figma 的开源 React 设计应用程序** —— 这是一款新的开源、本地优先的类 Figma 设计应用程序（支持 Windows、Linux 和 macOS），专门针对 React 使用场景。你可以直接在实时页面上设计布局，并立即将更改写入代码。虽然还处于早期阶段，但看起来非常有前景。GitHub 仓库。

**长按识别二维码查看原文**

https://onlook.dev/

On Off Inc.

**📉 如何提升 React 中的”交互到下一帧绘制”性能** —— 交互到下一帧绘制（INP）是一个常见的 Web 性能指标，用于衡量应用程序对用户交互的延迟和响应性，Google 甚至将其作为排名机制的一部分。Jacob 提供了大量建议和资源，帮助你改善 React 应用程序的 INP 表现。

**长按识别二维码查看原文**

https://kurtextrem.de/posts/improve-inp-react

Jacob ‘Kurt’ Groß

**React 数据获取模式** —— 这篇文章不是讲解如何在 React 应用程序中获取数据，而是介绍了一些用于组织数据获取的常见模式。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-data-fetching-patterns/

Robin Wieruch

**使用 Storybook 测试 React 服务器组件** —— 由于服务器组件横跨前后端，测试起来可能比较棘手，但 Storybook 提供了一种解决方案，这里将告诉你具体方法。

**长按识别二维码查看原文**

https://storybook.js.org/blog/component-testing-rscs/

Michael Shilman

**📄 为什么我放弃 React 转向 Go、HTMX 和 Templ** —— 始终要确保找到适合你的解决方案。Eduardo Rodriguez

**长按识别二维码查看原文**

https://blog.erodriguez.de/dependency-management-fatigue-or-why-i-forever-ditched-react-for-go-htmx-templ/

**📄 如何使用 React Three Fiber 和 GLSL 编写基于着色器的显示效果** Colin Demouge

**长按识别二维码查看原文**

https://react.statuscode.com/link/162996/web

**📄 Expo 中的实时字体管理** Mauro Garcia

**长按识别二维码查看原文**

https://medium.com/@valentineminer27/real-time-font-management-in-expo-2dc107fc89d1

**快讯：**

- 想要使用 React Three XR 构建沉浸式 WebXR 体验吗？Meta Quest 团队为你准备了一份详细的教程。
    
    **长按识别二维码查看原文**
    
    https://pmndrs.github.io/xr/docs/getting-started/introduction
    

- 如果你还在使用 X（原 Twitter），强烈建议关注 Aiden Bai，他是 React Scan 的创建者。他一直在用这个工具测试各大使用 React 的网站（比如 Apple 的网站），发现了许多渲染问题。
    
    **长按识别二维码查看原文**
    
    https://x.com/aidenybai
    

- 🔥 Astro 5.0 已经发布。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/astro-5/
    

🛠 代码与工具

**MUI X v7.23.0：用于复杂场景的高级 React 组件** —— 我们一直在勤奋地链接这个流行组件套件的每个新版本，但从未”正式”介绍过它，现在是时候了！MUI X 是一套完善的、专业设计的 MIT 许可的组件。v7.23.0 改进了数据网格组件并添加了完整的 React 19 支持。

**长按识别二维码查看原文**

https://mui.com/x/

MUI

**Radon IDE v1.0：React Native 开发 IDE** —— 之前称为 React Native IDE，Radon 是一个扩展，可以将 VS Code 或 Cursor 显著扩展为功能齐全的 React Native（和 Expo）开发 IDE。这是一个付费产品，但所有收入都会投入到开源 React Native 开发中，其功能集可能会让你觉得物有所值。

**长按识别二维码查看原文**

https://ide.swmansion.com/

Software Mansion

**Verification Input：可定制的掩码输入组件** —— 查看主页上的演示，这个组件非常适合输入 OTP 验证码、特定类型的密码等。GitHub 仓库。

**长按识别二维码查看原文**

https://andreaswilli.github.io/react-verification-input/

Andreas Willi

**🦋 react-bluesky-embed：在你的应用程序中嵌入 Bluesky 功能** —— 许多人认为社交微博平台 Bluesky 正处于”高光时刻”。如果你也这么认为，现在可以将其功能直接嵌入到你的应用程序中了。

**长按识别二维码查看原文**

https://github.com/hichemfantar/react-bluesky-embed

Hichem Fantar

**版本发布：**

- **📊 React JSX Highcharts v5.0.2** —— 使用正确的 React 组件构建的 Highcharts。现已支持 Highcharts v12。

- 🍩 **Minimal Pie Chart v9.0** —— 灵活、轻量级的饼图和环形图组件。

- **Yoga v3.2** —— Meta 的便携式布局引擎，用于 React Native 0.77。

- **React Easy Crop v5.2** —— 用于裁剪图片和视频的组件。(演示。)

- **React Native Skia v1.6** —— React Native 的高性能 2D 图形库。

- **React Native SVG v15.10** —— React Native 的跨平台 SVG 支持。

- **TanStack Form v0.39** —— 强大的、类型安全的 Web 表单状态管理。

- **React Icons v5.4** —— 可在 React 应用程序中使用的流行图标集。

- **BlockNote v0.20** —— 类 Notion 的基于块的编辑器。