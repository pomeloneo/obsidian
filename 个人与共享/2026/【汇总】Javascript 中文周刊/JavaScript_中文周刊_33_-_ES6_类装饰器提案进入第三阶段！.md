# JavaScript 中文周刊 #33 - ES6 类装饰器提案进入第三阶段！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247504682&idx=1&sn=7072a2ce4e86428b68986d99d2de90f0&chksm=e92198c8de5611de95409e3da9f654b3a83550b165dd433ab16c2ced0866db3e17eaf3ce2f98\#rd  
> 抓取时间: 2026/2/2 23:53:19

---

> 本期看点：本期为大家带来了在 JavaScript 中实现字符串数组的本地化适应性排序与如何利用 14 条 Linting 规则帮助您在 JavaScript 中编写异步代码等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi、Levi

## 🔥 本周热门

**ES6 类装饰器提案目前进入第三阶段** — 该提案在三年前被首次提出，目前已经 **进入第三阶段**（但还需要进行一些调整）。如果你想了解装饰器我们向你推荐 Mike Green’s 在 2019 编写的 **装饰器相关文章**，这篇文章清晰简洁的阐述了装饰器的概念已经用法。

**长按识别二维码查看原文**

https://github.com/tc39/proposal-decorators

Ecma TC39

**Electron v18.0 发布** — 流行的 Electron 跨平台“用 JS、CSS 和 HTML 构建桌面应用程序”框架上周发布了 v18 版本。**点击 🔗 查看升级详情**

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-18-0

Keeley Hammond and Sofia Nguy

**▶  Next.js 的历史** — 在讲述 Next.js 的历史时，很好地平衡了细节和高层次的概念。尽管只有 12 分钟，但它所涉及的背景和历史比你想象的要多得多。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=BILxV_vrZO0

Tyler McGinnis

**快讯：**

- **VisibleV8** 是 V8 引擎的一个补丁版本，专门用于监控和记录运行中的 JavaScript，📄 这篇文章详细地讲述了它。
    
    **长按识别二维码查看原文**
    
    https://kapravelos.com/projects/vv8
    

- Mish Ushakov 提醒我们 Next.js 和 Gatsby 不是 “静态站点的生成器” - **他们经常被人混为一谈**。
    
    **长按识别二维码查看原文**
    
    https://news.ycombinator.com/item?id=30832775
    

- 英国政府的官方公共网站 **放弃了对 jQuery 的依赖**。😢
    
    **长按识别二维码查看原文**
    
    https://twitter.com/TheRealNooshu/status/1507346592612896768
    

**版本发布：**

**Preact v10.7.0** – 小巧、快速的 React 替代方案。

**wavesurfer v6.1.0** – 使用 Web Audio 和 Canvas 的交互式音频可视化。

**Vite v2.9.0** – 下一代前端打包工具。

**D3 v7.4.0** – 数据驱动的文件库。

**React Testing Library v13** – 添加对 React v18 的支持。

**MIDIVal v0.0.16** – MIDI 消息库现在支持 MIDI 时钟。

i**oredis v5** – 高效的 Node.js Redis 客户端。

## 📒 教程与趣事

**在 JavaScript 中实现字符串数组的本地化适应性排序** — 当建立一个本地化的应用程序时，默认的字符串排序逻辑可能不能完全满足你的要求。这时建议你尝试一下 `localeCompare` 和 `Intl.Collator` API。

**长按识别二维码查看原文**

https://elijahmanor.com/byte/js-locale-sort

Elijah Manor

**14 条 Linting 规则可以更好地帮助您在 JavaScript 中编写异步代码** — 浏览 ESLint 默认提供的各种规则——这是学习一些最佳实践的有趣方式。

**长按识别二维码查看原文**

https://maximorlov.com/linting-rules-for-asynchronous-code-in-javascript/

Maxim Orlov

**Next.js 新中间件包含哪些新功能？** — Next.js v12.0 中的一个新的 beta 特性：中间件。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/04/next-js-middleware-feature/

Sam Poder （Smashing Magazine）

**理解 JavaScript Hydration** — **Hydration** 在许多基于 JS 的站点生成器中发挥着重要作用，但有时也可能造成性能瓶颈。本文是一篇概念文章，但深入探讨了新框架重新思考事物的一些方式。

**长按识别二维码查看原文**

https://dev.to/this-is-learning/conquering-javascript-hydration-a9f

Ryan Carniato

**如何处理 TypeScript 中的可选属性和 undefined？**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2022/03/28/optional-undefined-typescript/

Mattie Behrens

**如何在一小时内使用 tree-sitter 编写 Linter**

**长按识别二维码查看原文**

https://siraben.dev/2022/03/22/tree-sitter-linter.html

Siraben

## 🛠 代码与工具

**VS Code 发布 3 月份的更新** — VS Code 每月更新一次，但这次感觉像是针对 JavaScript 开发者的重大更新。本次更新主要包括对本地 `Local history` 的支持和 JS 调试器允许开发者收集和可视化的堆配置文件以密切关注内存分配。还可以在 HTML 文件中高亮显示 JS。

**长按识别二维码查看原文**

https://code.visualstudio.com/updates/v1_66

Microsoft

**a11y-dialog：一种轻量、无障碍创建对话框的方法** — 将 JS 对话框替换为`<dialog>` 元素是一种方法，但在很多情况下，这种方法并不是必须的。这里有一些很好的 **示例** 可供参考。

**长按识别二维码查看原文**

https://a11y-dialog.netlify.app/

Kitty Giraudel

**PLV8 v3.1：将 V8 引擎引入 PostgreSQL 数据库** — Postgres 是一个非常流行且可扩展性很高的关系数据库，它可以用 JavaScript 而不是 PL/pgSQL 编写程序这个特点可能会吸引你。具体请查看 **文档。**

**长按识别二维码查看原文**

https://github.com/plv8/plv8

plv8 team

**Encoding.js v2.0：检测、转换 (.jp) 字符编码** — 专门用于支持日文字符的编码，包括 Shift_JIS、EUC-JP 和 UTF-8/16。

**长按识别二维码查看原文**

https://github.com/polygonplanet/encoding.js

polygonplanet

**ts-audio v0.7.0：利用 AudioContext 播放音频列表的简单 API** — **示例**。

**长按识别二维码查看原文**

https://github.com/EvandroLG/ts-audio

Evandro Leopoldino Gonçalves

**Flatbush：对于二维点和矩形的快速静态空间索引**

**长按识别二维码查看原文**

https://github.com/mourner/flatbush

Vladimir Agafonkin

## 🙋🏻‍♀️