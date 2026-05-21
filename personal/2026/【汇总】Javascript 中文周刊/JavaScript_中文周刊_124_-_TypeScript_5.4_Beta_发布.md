# JavaScript 中文周刊 #124 - TypeScript 5.4 Beta 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526544&idx=1&sn=7594b61e9e3acffb7622471ae58d18f0&chksm=e9212372de56aa64bcd9d709abb638d04c0bdf6d1a5f263b238f74df7747310f91e417d5cb2b\#rd  
> 抓取时间: 2026/2/2 23:51:23

---

> 本期看点：TypeScript 5.4 Beta 版本新增 `Object.groupBy` 与 `Map.groupBy`，并引入了一个新的 `NoInfer<T>` 实用类型，用于阻止 TypeScript 在推断时深入匹配内部类型，并且在这篇长文中涵盖了许多更小的内容。最终版本预计在三月发布。

> 编辑：Yucohny

## 🔥 本周热门

**Cytoscape.js：图形/网络可视化与分析库** —— 如果需要建模或可视化关系型数据，比如生物数据或社交网络数据，可以试试这个工具。主页有许多演示可供欣赏。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://js.cytoscape.org/

Max Franz

**TypeScript 5.4 Beta 发布** —— 最新版本新增 `Object.groupBy` 与 `Map.groupBy`，并引入了一个新的 `NoInfer<T>` 实用类型，用于阻止 TypeScript 在推断时深入匹配内部类型，并且在这篇长文中涵盖了许多更小的内容。最终版本预计在三月发布。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-4-beta/

Daniel Rosenwasser

**Deno v1.40：现在支持 Temporal API** —— 最近 **Deno** 的大多数版本发布都相当重要，v1.40 版本实现了 **Temporal API**、**装饰器** 和 **更多 WebGPU 特性**，这使得通往 v2 的道路更加扎实。

**长按识别二维码查看原文**

https://deno.com/blog/v1.40

Deno 团队

**快讯：**

- TIL：**pnpm** 项目维护了 **一个经常更新的包管理器基准测试**（包括 npm、pnpm 与 Yarn）。

**长按识别二维码查看原文**

https://pnpm.io/benchmarks

- 🏀 **Bouncy Ball** 展示了在浏览器中实现跳动球的 22 种方式的实时比较，其中大多数使用的是 JavaScript，并展示了代码。

**长按识别二维码查看原文**

https://sparkbox.github.io/bouncy-ball/

- **Porffor** 是一个实验性的将 JavaScript 编译为 WASM 的编译器。

**长按识别二维码查看原文**

https://porffor.goose.icu/

## 📒 教程与趣事

**试试将 Qwik 作为构建 React 应用程序的替代方案** —— Paul Scanlon 通过几个示例将 React 与 **Qwik** 进行了比较，并得出结论认为至少值得探索一下作为 React 的替代方案。

**长按识别二维码查看原文**

https://thenewstack.io/take-a-qwik-break-from-react-with-astro/

Paul Scanlon

**导入断言和导入属性** —— Google 的 TC39 和 V8 团队成员 Shu-yu Guo 解释了导入断言是如何演变为导入属性的，并在 V8 v12.3 中默认启用。

**长按识别二维码查看原文**

https://v8.dev/features/import-attributes

Shu-yu Guo（V8）

**为我的自动化游戏提高最后一丝 JavaScript 性能** —— 作者正在构建 **CivIdle**，一个休闲的“挂机”文明建设游戏，其使用 **Pixi.JS**。作为一个挂机游戏，它需要模拟在幕后经过的时间，这意味着需要进行大量的优化。

**长按识别二维码查看原文**

https://ruoyusun.com/2024/01/23/cividle-optimization.html

Ruoyu Sun

**使用 Puppeteer 测试 Web 蓝牙** —— 使用 Puppeteer 在 Chrome 中测试使用 Web 蓝牙 API 的功能。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/test-web-bluetooth-with-puppeteer

Masso 与 Beaufort

**每个软件开发人员必须了解的 Unicode 知识** —— 由 Nikita Prokopov 对 Joel Spolsky 的经典 2003 年文章进行了补充更新。

**长按识别二维码查看原文**

https://tonsky.me/blog/unicode/

Nikita Prokopov

**通过网络同步解决 Cypress 和 Playwright 中的不稳定测试问题**

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/tackling-flaky-tests-in-cypress-and-playwright

Shreya Kurian

**为什么我对 Biome 的类型推断感到兴奋**

**长按识别二维码查看原文**

https://arendjr.nl/2024/01/why-im-excited-for-biomes-type-inference

Arend van Beelen jr.

## 🛠 代码与工具

**Labyrinthos.js：一个程序化迷宫生成器** —— 主页上的交互式演示会给你基本的概念，但该库实现了各种算法来创建迷宫和地形，包括使用 Perlin 噪声、生长树木、螺旋回溯等。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://yantra.gg/labyrinthos/

Yantra Works

**David UI Angular v1.0：Tailwind + Angular 组件库** —— 到目前为止已经有十七个组件，涵盖了诸如 **滑块**、**按钮**、**通知警报** 和常见表单元素等内容。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.david-ui-angular.com/

Creative Tim

**goja：纯 Go 实现的 ECMAScript/JavaScript 引擎** —— 一种将基于 JavaScript 的脚本功能添加到 Go 语言编写的应用程序中的方式，而不涉及集成更大的外部 JavaScript 引擎。

**长按识别二维码查看原文**

https://github.com/dop251/goja

Dmitry Panov

**🎨 chroma.js：零依赖的颜色转换库** —— 这个库的文档简单却又色彩丰富，这是其 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.vis4.net/chromajs/

Gregor Aisch

**版本发布：**

- **htmx 2.0.0-alpha1** – 有 **一个草案 1.x→2.x 迁移指南** 展示了会受到影响的内容。

- **Puppeteer v21.10.0** – Chrome 的 Node.js API——现在支持实验性的 `browser.debugInfo`。

- **Neutralinojs v5.0** – 轻量级跨平台桌面应用程序框架。

- **Primate v0.28**

- **Prisma v5.9**

- **Ember v5.6**

- **Pixi.js v7.4**

- **Faker v8.4** – 规模化并按需生成虚拟数据。

- **jquery.terminal v2.38** – 创建基于 Web 的终端体验，这是 **Demo**。

- **Polished v4.3** – 一种在 JavaScript 中写样式的轻量级方法。

- **Dependency Cruiser v16.1** – 可视化依赖关系的工具。

- **OverlayScrollbars v2.5** – JavaScript 自定义滚动条插件。

## 🙋🏻‍♀️