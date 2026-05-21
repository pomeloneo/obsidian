# Node 中文周刊 #83 - 新的 npm 包有一半是垃圾包吗？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518563&idx=1&sn=c08b1a6b6d0f243dbbfdae06882a7f99&chksm=e921c281de564b9736ede0254233374aba1d06cac49044c85e615f5a62e22ef9bd2dbccd90b3\#rd  
> 抓取时间: 2026/2/2 23:53:36

---

我们决定 **将 nodeweekly 更新到周二**。由于下时间周二太近了，因此我们会跳过下周二的周刊。**我们会在 2023.4.11 的周二继续更新**，到时候见！

_Peter Cooper, nodeweekly 原小编_

> 本期看点：Sandworm Audit 分析工具的创建者，声称官方 npm 注册表中“超过一半的新包”只是占位符。

> 编辑：gaao、Yucohny

## 🔥 本周热门

**新的 npm 包有一半是垃圾包吗？** — _Sandworm_ 是 **Sandworm Audit** 包分析工具的创建者，声称官方 npm 注册表中“超过一半的新包”只是占位符，其中 README 包含指向各种恶意站点的链接。

**长按识别二维码查看原文**

https://blog.sandworm.dev/one-in-two-new-npm-packages-is-seo-spam-right-now

Gabi Dobocan (Sandworm)

**Node v16.20.0 (LTS) 发布** — 不是大版本。主要更新依赖项，如 npm（更新至 8.19.4）和 undici。这个版本升级是由于将 **支持对外部共享 JS 内置函数的功能** 进行了回溯。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v16.20.0

Beth Griggs (Node.js Team)

**加速 JavaScript 生态系统：npm Scripts**— 关于在性能方面寻找“low hanging fruit”的精彩系列中的最新一期。作者对此作了最好的解释：_“’npm scripts’一直以来是由 JavaScript 开发者执行……。尽管它们的使用率很高，但并没有得到很好的优化，增加了大约 400ms 的开销。在这篇文章的讲解中，我们能够把它降到大约 22 毫秒。”_

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-4/

Marvin Hagemeister

**Cloudflare Workers 的 Node.js 兼容性** — _Cloudflare Workers_ 是一个流行的无服务器平台，它使用 **V8 isolates** 而不是 Node 运行时。这意味着缺乏对 Node 函数的支持，但随着对 `AsyncLocalStorage`，`EventEmitter`，`Buffer`，`assert`和 `util` 的支持，情况正在发生变化，接下来还会有更多的支持。

**长按识别二维码查看原文**

https://blog.cloudflare.com/workers-node-js-asynclocalstorage/

James M Snell

**CLI 应用程序的 npm 包的概况** — 如果你想创建一个 CLI 应用程序，现在有很多选项可以覆盖诸如漂亮的输出、解析参数和接受用户输入等领域。这篇文章总结了这些领域的一些选择。

**长按识别二维码查看原文**

https://blog.kilpatrick.cloud/posts/node-cli-app-packages/

Joey Kilpatrick

**理解 Node 的** `**module.exports**` **和** `**exports**`

**长按识别二维码查看原文**

https://www.sitepoint.com/understanding-module-exports-exports-node-js/

James Hibbard

**快讯：**

- **npm 加入 GitHub** 至今已经三年了。

**长按识别二维码查看原文**

https://github.blog/2020-03-16-npm-is-joining-github/

- **Mongoose** 是一个很受欢迎的数据库，用来模拟来自 Node 的 NongoDB 的数据，但是它的主要维护者 Valeri Karpov 透漏他们正在以 **stargate-mongoose** 的形式 **致力于 Cassandra 对 Mongoose 的支持**。

**长按识别二维码查看原文**

https://mongoosejs.com/

- 如果你正在寻找数据库配置，**Technically Database 数据库** 提供了一些流行选项的简单概述。

**长按识别二维码查看原文**

https://technically.dev/database-database

- 如果你是 Azure 函数使用者，Node.js 的编程模型的第 4 版 **目前正在进行预览**。这意味着函数的结构和定义方式发生了变化。

**长按识别二维码查看原文**

https://techcommunity.microsoft.com/t5/apps-on-azure-blog/azure-functions-version-4-of-the-node-js-programming-model-is-in/ba-p/3773541

## 🛠 代码与工具

**np v7.7.0：一个更好的`npm publish`** — 使用交互式 UI 使发布包的过程更加顺畅，检查你发布的内容是否正确，运行测试，推送提交和标记等。

**长按识别二维码查看原文**

https://github.com/sindresorhus/np

Sindre Sorhus

**Nano JSX：一个轻量级的 SSR 优先的 JSX 库** — 功能包括没有虚拟 DOM，没有外部依赖，按需 hydration，支持 Node 和 Deno 基于服务器端渲染情况。

**长按识别二维码查看原文**

https://nanojsx.io/

Nano JSX

**Concurrent.js：将模块加载到后台线程中** — 这是一个适用于 JavaScript 环境（包括浏览器、Nodee、Deno）的并发计算方法，这个库允许你动态地将模块导入工作线程（在 Node 中）或 Web Workers（在浏览器中）中。

**长按识别二维码查看原文**

https://github.com/bitair-org/concurrent.js

Bitair

**pnpm v8.1：备选快速且空间高效的软件包管理器** — 最新版本新增了一个名为 `dedupe-direct-deps` 的配置，默认情况下是禁用的，当设置为`true`时，已经链接到工作区根目录下的 `node_modules` 目录的依赖项将不会链接到子项目的`node_modules` 目录。此功能在 v8.0.0 中默认启用，但会导致问题，因此最好将其默认禁用。

**长按识别二维码查看原文**

https://github.com/pnpm/pnpm/releases/tag/v8.1.0

pnpm

**Sharp v0.32.0：来自 Node 的高性能图像处理** — 几年来没有好好的使用它，但它真的很好。它在后台使用 `libvips` 来提供它声称的“最快的调整 JPEG, PNG, WebP 和 TIFF 图像大小的模块”。你还可以旋转，做伽玛校正，裁剪等。这里有 **图像大小调整 API 和示例**。

**长按识别二维码查看原文**

https://github.com/lovell/sharp

Lovell Fuller

**版本发布：**

- **Unfurl v6.3**
    
    ↳ oEmbed、Twitter 和 Open Graph 元数据抓取工具。
    

- **JZZ v1.6.1**
    
    ↳ 用于 Node 和浏览器的 MIDI 库。
    

- **NodeBB v2.8.10**
    
    ↳ 流行的论坛软件。
    

- **Moon v1.0**
    
    ↳ Rust 驱动的任务运行器和 repo 管理工具。
    

- **Strapi v4.9**
    
    ↳ 基于 Node.js 的无头 CMS。
    

- **Prisma v4.12**
    
    ↳ 用于 Node 和 TypeScript 的下一代 ORM。
    

## 🙋🏻‍♀️