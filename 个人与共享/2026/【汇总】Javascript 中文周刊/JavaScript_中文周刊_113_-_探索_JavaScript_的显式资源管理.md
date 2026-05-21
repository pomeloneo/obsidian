# JavaScript 中文周刊 #113 - 探索 JavaScript 的显式资源管理

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525159&idx=1&sn=252d7fe020bbdc566a12f6ff11e5aea3&chksm=e92128c5de56a1d32ce75c624a310b1cc38973f1cb7d0478b69c874723250690f71735ce9044\#rd  
> 抓取时间: 2026/2/2 23:51:35

---

> 本期看点：探索 JavaScript 的显式资源管理是一次对显式资源管理想法的实际观察，该想法目前在 TC39 的第三阶段（TypeScript v5.2 也有部分的支持），它可以更加轻松地“清理”不再被使用或需要的资源。

> 编辑：Zhper、Yucohny

## 🔥 本周热门

**探索 JavaScript 的显式资源管理** —— 这是一次对显式资源管理想法的实际观察，该想法 **目前在 TC39 的第三阶段**（**TypeScript v5.2 也有部分的支持**），它可以更加轻松地“清理”不再被使用或需要的资源。

**长按识别二维码查看原文**

https://iliazeus.github.io/articles/js-explicit-resource-management-en/

Ilia Pozdnyakov

**一篇轻量级 JavaScript 框架综述** —— 这篇概述是面向 **Django**（也就是说 Python）开发者的，但如果你想避开像 React 或 Angular 这样大型的框架，也可能会喜欢着眼于更多替代方案，从 Stimulus 和 htmx 到 类似 Laravel Livewire 这样更间接的选择。

**长按识别二维码查看原文**

https://saashammer.com/blog/lightweight-javascript-framework-review-for-django-developers/

Michael Yin

**快讯：**

- 🥳 AWS 正在庆祝 **AWS Amplify JavaScript v6** 的盛大发布，它包括了对 Next.js 应用程序路由和服务器操作的全面支持。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/mobile/amplify-javascript-v6/

- James Q Quick 在 **软件工程日报** 播客上对 **Astro 的优势进行了良好的解释**。

**长按识别二维码查看原文**

https://softwareengineeringdaily.com/2023/11/14/the-astro-framework-with-james-quick-2/

- 🎵 有人录制了一个关于 TypeScript 的 ▶️ **说唱音乐视频**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=3ySPR3QCxO8

## 📒 教程与趣事

**67 个基于浏览器的调试技巧** —— 列出了一些有用的、“不明显”技巧，可以最大限度地利用浏览器的调试工具。前提是对所述工具已经存在适当的理解。

**长按识别二维码查看原文**

https://alan.norbauer.com/articles/browser-debugging-tricks

Alan Norbauer

**探索 V8 的字符串：实现和优化** —— **注意：这是非常专业的内容，大多数 JavaScript 开发者不需要过于深究**。这是 V8 引擎处理字符串的一个优异表现，包括使用了让它能够与 C++ 这样的语言媲美的优化。

**长按识别二维码查看原文**

https://iliazeus.github.io/articles/js-string-optimizations-en/

Ilia Pozdnyakov

▶ **Angular v17 的新内置控制流概述** —— **Angular v17** 于上周发布，其中一个重要的增强是支持模板中的一种新语法，这看起来更像 Javascript-y。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=DOffmVeBk0o

Dmytro Mezhenskyi

**在 Node 之外使用 npm 包** —— 学习如何在“其他地方”运行 npm 包，比如无服务器平台、浏览器等等。

**长按识别二维码查看原文**

https://neon.tech/blog/using-npm-packages-outside-node

George MacKerron (Neon)

**我从构建一个网络音频插件系统学习到了什么**

**长按识别二维码查看原文**

https://blog.benwiley.org/audio-plugins/

Ben Wiley

**面向 JavaScript 开发者的 rust 测试概述**

**长按识别二维码查看原文**

https://www.shuttle.rs/blog/2023/11/08/testing-in-rust

Joshua Mo

## 🛠 代码与工具

**gsplat.js：高斯喷洒库** —— 高斯喷洒是一种越来越流行的图形渲染技术，它不是在一个场景中渲染数百万个微小的、有纹理的三角形，而是得到一个更杂乱的彩蛋式喷洒，每一个彩蛋都会创建一个光滑的、彩色的斑点，而不是刻板的形状。**这个演示** 简单又醒目。

**长按识别二维码查看原文**

https://github.com/dylanebert/gsplat.js

Dylan Ebert

**Reveal.js v5.0：HTML 展示框架** —— 一种使用标准 web 技术构建展示页面的方法。这个 **项目的主页** 本身就是这样的展示。v5.0 支持了“滚动模式”，它本质上把展示变成了更典型的滚动式 web 体验。—— **这里是一个演示**。

**长按识别二维码查看原文**

https://github.com/hakimel/reveal.js/releases/tag/5.0.0

Hakim El Hattab

**Perfect Freehand：为了创造更好的手画线的库** —— 你可以 **在这里尝试一下**。让你的电子签名不再僵硬割裂！可能会对绘图应用程序有帮助。

**长按识别二维码查看原文**

https://github.com/steveruizok/perfect-freehand

Steve Ruiz

**@storybook-test：更加精简和强大的故事书测试** —— @storybook/test 将 `@storybook/jest` 和 `@storybook/testing-library` 的 API 整合到一个新的、单独的包中，由 Vitest 提供支持。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-test/

Kasper Peulen

**版本发布：**

- **Node.js v21.2.0 (Current)**

- **visx v3.5** – 用于 React 的基于 D3 的可视化原语。

- **fx v31.0** – 强大的终端 JSON 查看器。

- **Astro v3.5**，**Ember v5.4**，和 **Prisma v5.6**。

- **Marked v10.0** – Markdown 解析器和编译器。还有 **marked-terminal v6.1**，它允许你在终端上呈现由 Markd 处理的 Markdown。

- **HumanizeDuration.js v3.31.0** – 在许多自然语言中将毫秒转换为文本的持续时间。

- `**actions/github-script**` **v7.0** – 在 GitHub Actions 中编写 GitHub API 脚本。

- **Plasmo v0.84.0** – **“像 Next.js 一样面向浏览器扩展”**。

- **PDFKit v0.14.0** – 面向 Node 和浏览器的 PDF 生成器。

- **React Joyride v2.7** – 在应用程序中创建导览。

## 🙋🏻‍♀️