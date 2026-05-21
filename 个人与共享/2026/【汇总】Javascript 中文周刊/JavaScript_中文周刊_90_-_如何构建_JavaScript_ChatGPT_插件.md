# JavaScript 中文周刊 #90 - 如何构建 JavaScript ChatGPT 插件

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520558&idx=1&sn=e859fc93190f52d64e433cf4763b99ef&chksm=e921daccde5653dae0015d53a0a49eeb00a9ac19cd15a2cc35335592d1aaa4aaf89885515890\#rd  
> 抓取时间: 2026/2/2 23:52:02

---

> 本期看点：上周，Rafael Gonzaga 发布了 Node.js 在 2023 年的性能测评、现在 `deno compile` 也支持 npm 包、TC39 第 96 次会议结束。

> 编辑：TimLi777、liu-jin-yi

## 🔥 本周热门

**DeviceScript：专为微型设备设计的 TypeScript**——DeviceScript 是微软新推出的一种语言，旨在将 TypeScript 的编程体验应用到低资源的微控制器设备中。它被编译为一种自定义的虚拟机字节码，可以在这样的受限环境中运行（类似于 Go 的 **TinyGo**）。虽然主要面向 VS Code 用户，但也提供了 **命令行选项**。

**长按识别二维码查看原文**

https://microsoft.github.io/devicescript/

Microsoft

**Node.js 在 2023 年的性能测评**—— 主要在 EC2 实例上运行了几个不同的基准测试套件，测试了 Node 20、18.16 和 16.20 的性能表现。

**长按识别二维码查看原文**

https://blog.rafaelgss.dev/state-of-nodejs-performance-2023

Rafael Gonzaga

**Deno v1.34：现在 `deno compile` 也支持 npm 包** — **Deno** 这个版本主要关注 npm 和 Node 的兼容性，Deno 的编译命令（用于将项目转换为单个二进制可执行文件）现在也支持 npm 包，这有望开启很多新的使用场景。

**长按识别二维码查看原文**

https://deno.com/blog/v1.34

Deno 团队

**⚡️ 快讯：**

- TC39 的 Hemanth.HM 分享了 **TC39 第 96 次会议的一些更新**。`Atomics.waitAsync`、正则表达式的 `/v` 标志以及检测格式良好的 Unicode 字符串的方法都升级到了第 4 阶段。
    
    **长按识别二维码查看原文**
    
    https://dev.to/hemanth/updates-from-the-96th-tc39-meeting-4goe
    

- Angular 团队分享了 **他们年度开发者调查的结果**。超过 12,000 名 Angular 开发者参与了调查。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.io/angular-developer-survey-2022-results-summary-d17c88f62690?gi=f49c1e41bcf2
    

## 📒 教程与趣事

**揭秘 Tupper’s Formula** — Tupper 的自指公式 是一种公式，当被绘制时，可以代表它自己。你感到困惑吗？幸运的是，Eli 向我们展示了这一概念的简单性，并教我们如何使用 JavaScript 渲染我们自己的公式。

**长按识别二维码查看原文**

https://eli.thegreenplace.net/2023/demystifying-tuppers-formula/

Eli Bendersky

**Web Components 简介** — 本文提供了一个实用而简单的介绍。介绍了如何使用 **自定义元素 API** 来创建一个基本的选项卡面板，该 API 已被主流浏览器支持。

**长按识别二维码查看原文**

https://blog.rasvi.io/2023-05-21-webcomponent-intro-with-example

Mohamed Rasvi

**▶ 在 Visual Studio Code 中使用 p5.js 进行创意编程** — **p5.js** 是一个“创意编码”库，主要受到 **Processing** 的的启发。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=1h6vZl-OuB0

Daniel Shiffman 和 Olivia Guzzardo

**▶  为什么 React 没有消失？** — 这篇文章某种程度上是对两周前 Adam Elmore 的视频：▶️ 我对 React 受够了 的反驳。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ADKvP8Xn4g8

Joscha Neske

**比较三种非破坏性处理数组的方法** — `for-of`、`.reduce()` 和 `.flatMap()` 比较一下。

**长按识别二维码查看原文**

https://2ality.com/2022/05/processing-arrays-non-destructively.html

Dr. Axel Rauschmayer

**构建您的第一个 JavaScript ChatGPT 插件** — 插件提供了一种扩展 ChatGPT 功能的方式。

**长按识别二维码查看原文**

https://www.sitepoint.com/javascript-chatgpt-plugin/

Mark O’Neill

**我是如何将我的 Angular 应用转换为独立组件模式的。**

**长按识别二维码查看原文**

https://blog.bitsrc.io/how-ive-shifted-my-angular-app-to-standalone-components-approach-48c344bb714a?gi=da6bb6a221f9

Kamil Konopka

## 🛠 代码与工具

**Javy v1.0：一个 JS 到 WebAssembly 工具链** — 最初是在 Shopify 建立的，Javy 将你的 JS 代码运行在嵌入式 WASM 运行时中。值得 浏览一下示例 来感受一下这个过程。

**长按识别二维码查看原文**

https://github.com/bytecodealliance/javy?ck_subscriber_id=887809557

Bytecode Alliance

**Inkline v4.0：一个可定制的 Vue.js 3 UI/UX 库** — 一个设计系统和众多可定制的组件，设计以移动优先（但也友好桌面端），并且考虑到了可访问性。

**长按识别二维码查看原文**

https://www.inkline.io/

Alex Grozav

**BlockNote：一个类似 Notion 的基于块的文本编辑器** — 灵活，提供广泛的 API，可以与您想要做的任何事情集成。您可以拖放块，添加实时协作，添加可定制的“斜线命令”菜单等。建立在 ProseMirror 和 TipTap 之上。

**长按识别二维码查看原文**

https://www.blocknotejs.org/

TypeCell

**Windstatic：一套由 Tailwind 和 Alpine.js 构建的 170 多个组件和布局** — 分类为页面部分、导航和表单，每个类别包括多个组件，可以放入项目中。

**长按识别二维码查看原文**

https://windstatic.com/

Michael Andreuzza

**ls-lint v2.0：一个快速的文件和目录名称 linter** — 用 Go 编写，但针对 JS/前端开发用例，`ls-lint` 提供了一种强制执行文件命名和目录结构规则的方法。

**长按识别二维码查看原文**

https://github.com/loeffel-io/ls-lint

Lucas Löffel

**Jest Puppeteer v9.0：使用 Jest 和 Puppeteer 运行测试** — Jest 预设，可使用 Puppeteer 进行端到端测试。

**长按识别二维码查看原文**

https://github.com/argos-ci/jest-puppeteer/

Argos CI

**ts-sql-query：类型安全的 SQL 查询构建器** — 想要以类型安全的方式构建动态的 SQL 查询，并由 TypeScript 验证查询？那么这个就是你要的，它支持众多基于 SQL 的数据库系统，但_不_是一个 ORM 本身。

**长按识别二维码查看原文**

https://ts-sql-query.readthedocs.io/en/stable/

Juan Luis Paz Rojas

**版本发布：**

- Astro v2.5

- Preact v10.15
    
    ↳ 快速的 3KB React 替代品
    

- TypeScript v5.1 RC

- Electron v24.4

- MapLibre GL JS v3
    
    ↳ 基于 WebGL 的矢量切片地图。
    

- Hashids.js v2.3
    
    ↳ 生成类似 YouTube 的 ID。
    

- Tabulator v5.5
    
    ↳ 交互式表格和数据网格控件。
    

- gridstack.js v8.2
    
    ↳ 仪表盘布局和创建库。
    

- Cypress GitHub Action v5.8
    
    ↳ 用于运行 Cypress 端到端测试的 Action。
    

- ReacType v16.0
    
    ↳ 可以导出 React 代码的可视化原型工具。
    

- Mongoose v7.2
    
    ↳ MongoDB 模型库。
    

- Eta (η) v2.2
    
    ↳ 嵌入式 JS 模板引擎。
    

- AVA v5.3
    
    ↳ 流行的 Node 测试运行器。
    

- MelonJS v15.3
    
    ↳ HTML5 游戏引擎。
    

## 🙋🏻‍♀️