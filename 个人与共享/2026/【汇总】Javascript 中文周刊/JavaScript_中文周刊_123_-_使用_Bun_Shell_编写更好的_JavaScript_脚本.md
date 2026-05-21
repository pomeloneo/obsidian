# JavaScript 中文周刊 #123 - 使用 Bun Shell 编写更好的 JavaScript 脚本

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526412&idx=1&sn=8ba69ada05359ab5109b38ae8e7fc313&chksm=e92123eede56aaf88ffda45adca5f5e787bb539e6ac4c8b47d0549284c546210103f747bbf51\#rd  
> 抓取时间: 2026/2/2 23:51:24

---

> 本期看点：以性能为重点的服务器端运行时 Bun，通过进行一次探索性的任务，进入了 Shell 脚本的世界，使其变得更加简单、跨平台友好且不那么冗长。

> 编辑：Yucohny

## 🔥 本周热门

**使用 Bun Shell 编写更好的 JavaScript 脚本** —— 以性能为重点的服务器端运行时 **Bun** 在快速演进的过程中，通过进行一次探索性的任务，进入了 Shell 脚本的世界，使其变得更加简单、跨平台友好且不那么冗长。如果你想试试其他的工具，**zx** 提供了类似的（但集成和聚焦较少）功能供 Node 用户使用。

**长按识别二维码查看原文**

https://bun.sh/blog/the-bun-shell

Jarred Sumner（Bun）

**AdonisJS v6 正式发布** —— 如果你想要一个具有 **出色文档** 并充满各类功能的后端 Web 框架，**Adonis** 是一个不错的选择。v6 迈出了重要的一步，将默认使用 ESM，并且实现了更加安全的类型限制（包括路由和中间件引用），还引入了新的验证库等等。

**长按识别二维码查看原文**

https://adonisjs.com/blog/adonisjs-v6-announcement

Harminder Virk

**QuickJS：小巧、可嵌入的 JavaScript 引擎** —— 几年前，FFMPEG 和 JSLinux 背后的天才 Fabrice Bellard 使用 C 构建了一个小巧而完整的 JavaScript 引擎。它现在支持 ES2023，最新版本在模块和 REPL 中添加了顶级 `await`，同时支持一些最新的 JavaScript 特性。这是 **更新日志**。

**长按识别二维码查看原文**

https://bellard.org/quickjs/

Fabrice Bellard

**快讯：**

- 在 Twitter/X 上的 **@npm_malware** 分享了实时检测到的恶意软件包。

**长按识别二维码查看原文**

https://twitter.com/npm_malware

- JetBrains 推出了 **WebStorm 2024.1 早期访问计划**，这是其商业 JavaScript/TypeScript IDE 的最新版本。

**长按识别二维码查看原文**

https://blog.jetbrains.com/webstorm/2024/01/webstorm-2024-1-eap1/

- **📅 React Conf 2024** 将于今年 5 月 15-16 日在 Lake Las Vegas 举行，同时会有直播。

**长按识别二维码查看原文**

https://conf.react.dev/

## 📒 教程与趣事

**认真使用 Web Component** —— 如果你想要深入了解使用 Web Component 与 JavaScript 构建整个应用程序的经历，那么可以看看这篇文章。作者在文章中展示了使用 Web Component 全力打造一个简单但完整的应用程序的真实情况。

**长按识别二维码查看原文**

https://naildrivin5.com/blog/2024/01/24/web-components-in-earnest.html

David Bryant Copeland

**▶ 使用 Alpine、HTMX 与 Astro 构建 Wordle 应用程序** —— 既是受欢迎的开发者也是 YouTuber 的 Jack 演示了如何使用现代 Alpine、HTMX 与 Astro 构建一个 Wordle 克隆程序。你也可以直接查看 **代码**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=vQUqgURgG8M

Jack Herrington

**对被混淆的 JavaScript 进行逆向工程并处理已签名请求的哈希值**

**长按识别二维码查看原文**

https://buer.haus/2024/01/16/reversing-and-tooling-a-signed-request-hash-in-obfuscated-javascript/

Brett Buerhaus

**使用 HTML、CSS 和纯 JavaScript 创建货币转换器**

**长按识别二维码查看原文**

https://webdesign.tutsplus.com/currency-converter-with-html-css-and-vanilla-javascript–cms-108362t

Esther Vaati

## 🛠 代码与工具

**Jint v3.0：.NET 中的 JavaScript 解释器** —— Jint 将帮助你在 .NET 应用程序中运行 JavaScript，并将 .NET 对象和函数暴露给 JavaScript 代码。**v3** 在七年的努力后推出，是完全在 .NET 内运行最符合标准的 JavaScript 引擎。

**长按识别二维码查看原文**

https://github.com/sebastienros/jint

Sébastien Ros

**Mutative：高效不可变更新的库** —— 一种高效的不可变更新库，宣称比朴素的 reducer 实现快 2-6 倍，甚至比 Immer 快 10 倍还多。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://mutative.js.org/blog/releases/1.0/

Michael Lin

**workerpool v9.1：将任务卸载到工作池** —— 一个长期存在的线程池库，不仅适用于 Node，还适用于浏览器。

**长按识别二维码查看原文**

https://github.com/josdejong/workerpool

Jos de Jong

**Partytown v0.9：在 Web Worker 中运行第三方脚本** —— 一种在主线程保持响应性的情况下，在单线程（Web Worker）中运行资源密集型脚本的方式。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://partytown.builder.io/

Partytown

**pretty-ms v9.0：将毫秒转换为可读字符串** —— `1337000000` → `15d 11h 23m 20s`

**长按识别二维码查看原文**

https://github.com/sindresorhus/pretty-ms

Sindre Sorhus

**nmea.js：解析海洋电子数据的库** —— 也许以前从未听说过 **NMEA**，但如果你使用声纳、陀螺罗盘和类似的海洋电子设备，这对你来说可能很有用。

**长按识别二维码查看原文**

https://github.com/BMSVieira/nmea.js

Bruno Vieira

**版本发布：**

- **Astro v4.2** – 永远令人惊叹的框架。

- **Puppeteer v21.9** – 现在使用 Chromium 121。

- **Next.js v14.1**

- **Qwik v1.4**

- **Redux Toolkit v2.1**

- **Mongoose v8.1** – MongoDB 对象建模方法。

- **EverShop v1.0** – 基于 Node.js 的电子商务平台。

- **pretty-quick v4.0** – 在更改的文件上运行 Prettier。

- **wavesurfer.js v7.7** – 波形渲染和播放。

- **Flatbush v4.3** – 2D 点/矩形的快速空间索引。

- **Culori v4.0** – 综合色彩库。

## 🙋🏻‍♀️