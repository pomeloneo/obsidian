# JavaScript 中文周刊 #26 - 如何在浏览器使用后端语言进行编程？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247502164&idx=1&sn=134b91ecc8d9a23a3b653d188a429cce&chksm=e92182b6de560ba085510cb91021ecb443adbfaee12318d7eeb973cc7999c2b929e9e499ba07\#rd  
> 抓取时间: 2026/2/2 23:53:28

---

> 本期看点：上周 JS Party 发布了深入剖析 SolidJS 的播客，内容干货十足。如何在浏览器使用后端语言进行编程呢？感兴趣的小伙伴可以点击详情查看！

> 编辑：山鬼、Matrixbirds、Yucohny

## 🔥 本周热门

**基于 JavaScript 的开源数据可视化工具库：Apache Echarts v5.3** — 从版本记录 可以看到最新版本中新增的功能。例如：帧动画、自定义加载动画，以及 SVG 渲染相比之前在性能上有了质的飞跃。点击查看在线示例。

**长按识别二维码查看原文**

https://echarts.apache.org/en/index.html

Apache Software Foundation

**🥊 如何在浏览器使用后端语言进行编程？** — 你可能会认为这是关于使用 WebAssembly 在浏览器中运行 Python 之类的代码，但这并不是作者想分享的。作者提到的是通过服务端的 WebSocket 连接浏览器平台，由服务端处理 HTML 渲染更新到浏览器，这种方案日益流行，并且已经在 Elixir 和 Rails 全栈框架中支持。

**长按识别二维码查看原文**

https://github.com/readme/featured/server-side-languages-for-front-end

GitHub

**🎧 JS Party 播客** - 上周 JS Party 发布了 深入剖析 SolidJS 的播客，内容非常 nice！，他们去年 12 月底还发布了 关于 Svelte 的优势 的播客，甚至有邀请律师一起讨论 GitHub Copilot 的法律影响的播客。

**长按识别二维码查看原文**

https://changelog.com/jsparty

The Changelog podcast

**快讯：**

- 🤑 很少有 JavaScript 应用会被以超百万美金的售价卖给 **纽约时报**，`Wordle` 游戏的作者在 ▶️ **Syntax podcast 这里** 向我们分享他的故事。
    
    **长按识别二维码查看原文**
    
    https://syntax.fm/show/430/creator-of-wordle-josh-wardle
    

- 上一期所提到的新增 Fetch API 已经在 **Node.js v17.5.0** 中作为实验性功能得到了支持。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v17.5.0/
    

- Khronos WebGL 工作组通知大家 **WebGL v2.0 现已得到所有主流浏览器的广泛支持**，并且已经开始迁移到 WebGL v2.0。
    
    **长按识别二维码查看原文**
    
    https://www.khronos.org/blog/webgl-2-achieves-pervasive-support-from-all-major-web-browsers
    

- curl HTTP 客户端目前新增了 **选项 –json** ，它会让发送 json 变得更加便利。
    
    **长按识别二维码查看原文**
    
    https://daniel.haxx.se/blog/2022/02/02/curl-dash-dash-json/
    

- 当某位 JavaScript 开发人员决定跳过 React 和 SPA 并 构建一个 **Rails 应用程序时**，竟然引起了 激烈的讨论。
    
    **长按识别二维码查看原文**
    
    https://reviewbunny.app/blog/dont-make-me-think-or-why-i-switched-to-rails-from-javascript-spas
    

- Vue 博客官宣：Vue3 已经成为 **默认版本**，Vue 官网 vuejs.org 已经更新。
    
    **长按识别二维码查看原文**
    
    https://blog.vuejs.org/posts/vue-3-as-the-new-default.html
    

**版本发布：**

**Vite v2.8.0** – 下一代前端构建工具。

**RedwoodJS v0.45.0** – 可按节点部署的 JavaScript 全栈框架。

**MikroORM v5** – Node 的数据映射器 ORM。

**AdminJS v5.6** – 基于 Node.js 实现的后台管理面板。

**npm v8.5.0**

**Ember.js v4.2.0**

## 📖 教程与趣事

**如何轻松调试 JavaScript** — 这篇文章也许并不深入，但这是一次轻松愉快的 JavaScript 调试之旅。

**长按识别二维码查看原文**

https://flaviocopes.com/debugging/

Flavio Copes

**Angular Compiler 的工作原理** — Angular Compiler（称为 `ngc`）是用于编译 Angular 应用程序和库的工具。这篇文章深入探讨了它的作用以及它是如何实现的。

**长按识别二维码查看原文**

https://blog.angular.io/how-the-angular-compiler-works-42111f9d2549?gi=e27f181db776

Alex Rickabaugh

**使用 HTML 的**

**标签替换 JavaScript 对话框**

— 如何在某种程度上用 HTML 对话框元素替换 JavaScript 对话框，该元素提供与

```
alert()
```

、

```
confirm()
```

和

```
prompt()
```

方法类似的功能。

**长按识别二维码查看原文**

https://css-tricks.com/replace-javascript-dialogs-html-dialog-element/

Mads Stoumann

**▶  用 TypeScript 编写 SPI SD 卡驱动程序** — 该视频来自实时低级 JavaScript 流的一个有趣的会话，该会话深入探讨了如何在低级工作以从 SD 卡读取数据。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=SIIde33EZrA&t=233s

Low Level JavaScript

**如何将 Gulp 概念与现代 JS 结合起来？** — 作者发现 Gulp 对流的依赖使得扩展变得复杂，并展示了使用异步生成器解决同一问题的不同方法。

**长按识别二维码查看原文**

https://palant.info/2022/02/08/writing-my-own-build-system-coupling-gulp-concepts-with-modern-javascript/

Wladimir Palant

**▶  Vue 3 中的有限状态机**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=fT9p9CCSrn8

Sarah Dayan

**使用 Vue 3 和 Cube 构建 Apache ECharts 数据可视化仪表板**

**长按识别二维码查看原文**

https://cube.dev/blog/building-an-apache-echarts-dashboard-with-vue-3-and-cube/

Ashutosh Singh

## 🛠 代码与工具

**zx v5.0：在 JavaScript 中编写更好的 Shell 脚本** — 比起直接用 `bash` 做一些快捷脚本，`zx` 在 JavaScript 环境中友好地提供了和 `bash` 一样的功能支持。在 v5.0 版本中，添加了对 YAML 格式的支持。

**长按识别二维码查看原文**

https://github.com/google/zx

Google

**Pintora：一个可扩展的文本转图表的渲染库** — 它的设计理念相似于 Mermaid.js (也已经发布了 新版)，但出于对可扩展的设计理念不同，如果你从 Node.js 开始使用它，则不需要无头浏览器的支持。它们的 入门教程 都有可视化的代码实例。

**长按识别二维码查看原文**

https://github.com/hikerpig/pintora

Hikerpig

**Griffel：一个基于 AOT 的 CSS-in-JS 的编译工具** — 源于微软技术团队的另一种 CSS-in-JS 的选型。这个方案几乎不依赖运行时，同时还支持服务端渲染，可以用 JS 对象定义样式，以及支持相当多的其他功能。

**长按识别二维码查看原文**

https://github.com/microsoft/griffel

Microsoft

**Fable v3.7：一个成熟的 F# 语言转 Javascript 语言的编译器** — F# 是一个来自微软 .NET 平台的”函数优先”的编程语言，它的代码阅读起来总是会很友好，如果你对用它来构建前端感兴趣，可以点开 这个在线的 REPL 工具，同时也有一些可以训练的示例程序（包括一个小巧的马里奥）。

**长按识别二维码查看原文**

https://fable.io/

Alfonso García-Caro and contributors

**从 puppeteer 迁移到 playwright 的脚本** — 当需要在两种浏览器自动化系统的迁移场景是有帮助的。

**长按识别二维码查看原文**

https://github.com/checkly/puppeteer-to-playwright

Checkly

**P42 JavaScript 重构小助手: 是 VS Code 的一个自动化重构提示插件** — 一个 Visual Studio Code 扩展，它为您的编辑器带来了 67 种自动重构和快速修复常见 JS、TS 和 React 问题的方法，因此您甚至可以在使用普通 linter 之前进行清理。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=p42ai.refactor\#p42refactor

P42 Project

**Mineflayer v4.0：基于 JavaScript 构建 Minecraft 机器人的工具** — 这里是它的 GitHub 仓库。

**长按识别二维码查看原文**

https://mineflayer.prismarine.js.org/\#/

Andrew Kelley

**15 个流行的 React 组件库之间的区别**

**长按识别二维码查看原文**

https://stackdiary.com/react-component-libraries/

Alex Ivanovs

**🌞🌝**  **SunCalc v1.9：一个轻量级的日月位置及周期的计算库**

**长按识别二维码查看原文**

https://github.com/mourner/suncalc

Vladimir Agafonkin

## 🙋🏻‍♀️