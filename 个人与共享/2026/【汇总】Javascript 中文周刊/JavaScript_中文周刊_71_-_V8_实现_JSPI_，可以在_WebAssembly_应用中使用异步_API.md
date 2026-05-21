# JavaScript 中文周刊 #71 - V8 实现 JSPI ，可以在 WebAssembly 应用中使用异步 API

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514938&idx=1&sn=45f1181fa39eec77dae9465e5cf4f232&chksm=e921f0d8de5679ceca7dbd5c1ebd7276af72132e6780c2d97bbec714ad1cceda830728d38dd6\#rd  
> 抓取时间: 2026/2/2 23:52:30

---

> 本期看点：V8 团队对一个新的 API 进行了相关技术实现，让 WebAssembly 应用程序能够抹平外部环境同步/异步的差异（考虑到许多应用程序是同步编写的，但现代 Web API 大多是异步的）。JSPI 有助于弥补两个环境的差异，同时可以通过开启 Chrome 中的一个 Flag 对其进行测试。

> 编辑：TimLi777、QC-L、Yucohny

## 🔥 本周热门

**为什么不建议使用 `document.write()`？** — 许多年前，`document.write` 是客户端 JavaScript 代码的主流写法，但它早已被认为是一种不好的做法 — 因为它会阻塞下载，同时也阻塞执行，这使得解析器的工作时间远远超过预期时间。

**长按识别二维码查看原文**

https://csswizardry.com/2023/01/why-not-document-write/

Harry Roberts

**WebAssembly 的 JavaScript Promise 集成 API (简称 JSPI)** — V8 团队对一个新的 API 进行了相关技术实现，让 WebAssembly 应用程序能够抹平外部环境同步/异步的差异（考虑到许多应用程序是同步编写的，但现代 Web API 大多是异步的）。JSPI 有助于弥补两个环境的差异，同时可以通过开启 Chrome 中的一个 Flag 对其进行测试。

**长按识别二维码查看原文**

https://v8.dev/blog/jspi

McCabe, Michaud, Rezvov, Dahl / V8 Team

**快讯：**

- 最新一期的 ▶️ **JS Party 博客** 讨论了 JavaScript 框架的“兴衰”和现代小型框架的趋势。
    
    **长按识别二维码查看原文**
    
    https://changelog.com/jsparty/258
    

- **Aurelia 2 现在处于测试阶段**。
    
    **长按识别二维码查看原文**
    
    http://aurelia.io/blog/2023/1/14/announcing-the-aurelia-2-beta/
    

## 📒 教程与趣事

**构建一个无障碍的主题选择器** — 一个有吸引力的、易于遵循的教程，介绍了如何实现切换网站主题的功能。

**长按识别二维码查看原文**

https://fossheim.io/writing/posts/accessible-theme-picker-html-css-js/

Sarah L. Fossheim

**Chrome Tracing 的初级指南** — 当你想深入了解 _Performance_ 标签时。可以使用 Tracing 功能，使用它可以记录下浏览器在幕后所做的事情。

**长按识别二维码查看原文**

https://nolanlawson.com/2022/10/26/a-beginners-guide-to-chrome-tracing/

Nolan Lawson

**在 TypeScript 中像专业人士一样处理错误** — _“学习如何处理异常以及写出更清洁的代码的设计模式”_

**长按识别二维码查看原文**

https://engineering.udacity.com/handling-errors-like-a-pro-in-typescript-d7a314ad4991?gi=b00949efe1b4

Kolby Sisk

**带示例的** `**async/await**` **初学者指南**

**长按识别二维码查看原文**

https://www.sitepoint.com/javascript-async-await/

James Hibbard

**在开始使用 Vue 3 时应避免的 10 个错误**

**长按识别二维码查看原文**

https://fadamakis.com/10-mistakes-to-avoid-when-starting-with-vue-3-1d1ced8552ae?gi=249e0002f7b2

Fotis Adamakis

## 🛠 代码与工具

**RoughNotation: 使用 Rough.js 实现，手写风格的仿笔记注释动画库** — 使用 Rough.js（本身就是一个值得学习的项目）来实现手绘样式。页面上有很多漂亮的交互式示例，展示了各种注释样式（方框、下划线、圆圈等）。

**长按识别二维码查看原文**

https://roughnotation.com/

Preet Shihn

**Modern Errors：以简单、稳定、一致的方式处理错误** — 你可以创建错误类，包装或聚合错误，还提供了一些插件，如打印错误报告信息，打印堆栈跟踪等。在 Node 和浏览器中都能使用。

**长按识别二维码查看原文**

https://github.com/ehmicky/modern-errors

**Shifty: 一个小型、快速的 Tweening 引擎** — 它所做的只是 Tweening（在动画中，给定一些参数，返回每一关键帧对应的属性）。它是一个低级别的动画解决方案，你可以把它集成到你选择的任何渲染机制中。这里的例子很好地展示了它，因为它可以用于非传统意义上的“动画”。**GitHub 仓库**。

**长按识别二维码查看原文**

https://jeremyckahn.github.io/shifty/doc/

Jeremy Kahn

**Barba.js: 用于页面之间的平滑视觉过渡** — 这个库的主页非常酷炫，展现了很多这个库的功能，而且非常丝滑。**GitHub 仓库**。

**长按识别二维码查看原文**

https://barba.js.org/

De Rosa, Michel, et al.

**Rete.js 1.5: 一个可视化编程的框架** — 在浏览器中创建一个基于 Node.js 的编辑器并应用逻辑。这里有几个 DEMO，如果你有兴趣还可以看看 GitHub 仓库。

**长按识别二维码查看原文**

https://rete.js.org/

Vitaliy Stoliarov

**gpu-io: GPU 加速计算库** — 用于物理模拟和其他数学计算。对 WebGL 的威力的一个整洁的看法。可以来这里看看 **相关示例**。

**长按识别二维码查看原文**

https://github.com/amandaghassaei/gpu-io

Amanda Ghassaei

**版本发布：**

- **⭐️ esbuild v0.17.0**
    
    ↳ 流行的构建工具。请注意，这是一个关键版本，有向后不兼容的变化。
    

- **Inertia.js v1.0**
    
    ↳ 为任何后端构建 SPA 应用。
    

- **React Native v0.71**

- **Chart.js v4.2**
    
    ↳ 基于 Canvas 的简单图表。(**例子**)
    

- **Serialize JavaScript v6.0.1**
    
    ↳ 将 JS 序列化为 JSON 超集。
    

- **axios-retry v3.4**
    
    ↳ Axios 插件，重试失败的请求。
    

- **Axios v1.2.3**
    
    ↳ 流行的 HTTP 客户端库。
    

- **Commander.js v10.0**
    
    ↳ 让 Node.js CLI 变得简单。
    

- **Mineflayer v4.7**
    
    ↳ 用于 Minecraft 机器人的 JS API。
    

- **Wretch v2.4**
    
    ↳ 封装了 Fetch API 的请求库，有很多优秀的特性。
    

## 🙋🏻‍♀️