# JavaScript 中文周刊 #51 - 检查原生 JavaScript 函数是否被覆盖

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247509322&idx=1&sn=acd2a01585cf91a68ab757339c9b2f4a&chksm=e921eea8de5667bec075c00f9fbb463de4ff1e99b6fe9b1f7c0c33cbf224c68684e5ec8859c9\#rd  
> 抓取时间: 2026/2/2 23:52:55

---

> 本期看点：本期为大家带来了如何检查原生 JavaScript 函数是否被覆盖与使用 Bud 更快地构建现代 Web 应用程序等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、山鬼、Matrixbirds

## 🔥 本周热门

JS1024 2022 竞赛获奖名单 — JS1024 是一项“代码高尔夫”竞赛，参赛者有 15 天的时间在 1024 字节内创建 JavaScript 或 GLSL 程序。这个比赛总会产生很多创意的想法，并附有很棒的但并非缩小的源代码可以查看。JS1024 2022 获胜的 JS 条目是 这个古怪的打字游戏，获胜的基于着色器的条目是 3D 隧道体验。我们可以从中学到许多东西，包括在 一个使用大量评论的条目 中压缩 1900 多个英文单词和特制的 WOFF2 字体文件！

**长按识别二维码查看原文**

https://js1024.fun/results/2022

JS1024

**快讯：**

- 新的 VS Code 版本 发布，在这个版本中，JS 调试功能 进行了改进，▶️ 这种“粘性滚动”功能 特别简洁，因为即使在长时间运行时，它也能将您的函数签名保持在屏幕上。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_70
    

- 如果您使用 AWS 的 _Lambda_ 无服务器平台来运行您的函数并且您大量使用它，那么他们的 新分层定价结构 可能会节省大量资金。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/compute/introducing-tiered-pricing-for-aws-lambda/
    

## 📒 教程与趣事

检查原生 JavaScript 函数是否被覆盖 — 如何确定 JavaScript 原生函数是否被覆盖？当原生函数可能在运行时被重写时，你将无法完全相信它们。这篇文章介绍了一个并不完美的方法来检查是否出现了这种情况。

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2022-07-30-checking-if-a-javascript-native-function-was-monkey-patched/

Matteo Mazzarolo

使用 Bud 更快地构建现代 Web 应用程序 — Bud 是一个相对较新的 Go 和 JavaScript 驱动的全栈 Web 框架，Bud 框架中有许多好的想法。▶️ 这个 15 分钟的视频 介绍了如何使用它创建 Hacker News 克隆，这是一个有趣的演示。如果 Go 在后端适合你，那么 Bud 也值得一看。

**长按识别二维码查看原文**

https://goingwithgo.com/2022/08/matt-mueller-building-modern-web-applications-faster-with-bud/

Preslav Rachev

在 Node.js 中使用 util.parseArgs() 解析命令行参数 — 就在今年，Node 18.3 中添加了这项功能。

**长按识别二维码查看原文**

https://2ality.com/2022/08/node-util-parseargs.html

Dr. Axel Rauschmayer

使用 Jest 替换 Angular 项目中的默认测试运行器

**长按识别二维码查看原文**

https://spin.atomicobject.com/2022/08/02/jest-angular-project/

Rob Bell

## 🛠 代码与工具

vue-grid-layout: 基于 Vue.js 的支持拖拽和调整大小的网格布局 — 它类似 jQuery 版本的Gridster.js 。主页里有它的示例程序地址。Github 代码仓库地址。

**长按识别二维码查看原文**

https://jbaysolutions.github.io/vue-grid-layout/

JBay Solutions

safe-json-value: 当 JSON 序列化时不会失败 — 避免 `JSON.serialize()` 方法抛异常，更改类型，或以其他方式意外地转换值，因为有时候开发者需要这些保证。

**长按识别二维码查看原文**

https://github.com/ehmicky/safe-json-value

ehmicky

colorgrad: 高性能的，基于 Rust 实现的颜色渐变库 — 使用 Rust 编译成 WebAssembly 的场景已经越渐流行。它的代码非常的精简，便于学习和上手。在线示例程序。

**长按识别二维码查看原文**

https://github.com/mazznoer/colorgrad-js

Nor Khasyatillah

Embla Carousel 7: 支持流体运动，精准滑动的轮播组件 — 一个备受争议的 UI 组件，但它的示例程序 能满足交互功能。同时不依赖框架，可以很容易的和 React、Vue、Svelte 框架集成。

**长按识别二维码查看原文**

https://www.embla-carousel.com/

David Jerleke

ts-version: 在类型中访问当前 TypeScript 的版本 — 为了解决 TypeScript 版本处理软件包的方式略有不同，但又不希望使用 TypesVersions 提供类型的完整副本，你可以用它来根据类型调整 TypeScript 依赖的版本问题。

**长按识别二维码查看原文**

https://www.npmjs.com/package/@phryneas/ts-version

Lenz Weber-Tronic

PowerGlitch: PowerGlitch 是一个没有外部依赖关系的独立库。它利用 CSS 动画在图像上创建一个小故障效果。不需要操作画布或 DOM。

**长按识别二维码查看原文**

https://7ph.github.io/powerglitch/\#/

PowerHat

**版本发布：**

- Parcel v2.7

- Ember v4.6

- Ionic v6.2 – 跨平台的应用开发框架。

- Cypress v10.4 – 受欢迎的基于浏览器的测试框架。

- Ohm v16.4 – 面向 JavaScript 开发者，自定义语法树分析&解释器的框架。

- Electron vStore 8.1 – 基于 Electron 的简单数据持久化组件库。

- Meriyah v4.3 – 100%兼容，自托管的 JS 语法树解释器。(示例程序)

- React Spreadsheet Grid v2.3 – 类似 Excel 的网格 React UI 组件。

- Inferno v8.0.2 – 高性能类 React 的前端框架。

- Peaks.js v2.0.3 – BBC 官方声波 UI 组件。

❓ **你知道吗?**

- 这里有一个精选列表包含 150 多个静态站点生成器及相关的资源。如果希望更了解静态站点生成器相关的扩展知识, 这里可以了解更多。

**长按识别二维码查看原文**

https://github.com/myles/awesome-static-generators

- 在 MacOS 系统，当你调整窗口大小时按住 Option (⌥) ，会一次从所有方向调整大小，对于那些部分在屏幕外的窗口来说很方便。

## 🙋🏻‍♀️