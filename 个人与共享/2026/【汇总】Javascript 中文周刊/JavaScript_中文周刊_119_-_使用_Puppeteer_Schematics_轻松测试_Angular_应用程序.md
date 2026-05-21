# JavaScript 中文周刊 #119 - 使用 Puppeteer Schematics 轻松测试 Angular 应用程序

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525862&idx=1&sn=2a99ec4a4c16ab1963c562e0830c05ba&chksm=e9212e04de56a71228f7988cf3bffda69e988bc92ddaaebc4332483da0cc093739d801cefe93\#rd  
> 抓取时间: 2026/2/2 23:51:28

---

> 本期看点：Puppeteer 是一个用于自动化浏览器交互的强大工具。现在经由新发布的 `@puppeteer/ng-schematics` 便可以更轻松地与 Angular 项目集成。此工具为设置和运行 Puppeteer 测试提供了开箱即用的体验，最大限度地减少配置负担并加速自动化之旅——特别是创建端到端测试！

> 编辑：Yucohny、TimLi

## 🔥 本周热门

**使用 Puppeteer Schematics 轻松测试 Angular 应用程序** —— Puppeteer 是一个用于自动化浏览器交互的强大工具。现在经由新发布的 `@puppeteer/ng-schematics` 便可以更轻松地与 Angular 项目集成。此工具为设置和运行 Puppeteer 测试提供了开箱即用的体验，最大限度地减少配置负担并加速自动化之旅——特别是创建端到端测试！

**长按识别二维码查看原文**

https://blog.angular.io/introducing-puppeteer-schematics-test-your-angular-apps-with-ease-dea6947f6299

Jecelyn Yeen

**开发者应该如何阅读《网页内容可访问性指南》（WCAG）** —— WCAG 是网络可访问性标准参考的简明指南。作者在文章中介绍了为什么 WCAG 难以阅读却又推荐开发者进行阅读。

**长按识别二维码查看原文**

https://uxdesign.cc/how-a-developer-should-read-wcag-b1aec621b9d2

Daniel Berryhill

**SolidStart Beta 2 发布** —— SolidStart 团队很高兴有越来越多的项目开始基于 SolidStart 构建，在新增许多贡献者的同时还得到了 Chrome 团队的支持。最新的 Beta 2 版本变得更智能、更能隔离变化，这将帮助团队更快地迈向 v1.0 版本。

**长按识别二维码查看原文**

https://github.com/solidjs/solid-start/releases/tag/v0.4.0

solidjs

## 📄 教程与趣事

**关于 JS 的 PTC 问题的评论** —— PTC（Proper tail call）是唯一一个写在 ES6 标准中但至今（2023 年 12 月）绝大多数 JavaScript 引擎都不支持的特性。作者在文章中回顾了其几年前的观点并再次做出了总结。

**长按识别二维码查看原文**

https://zhuanlan.zhihu.com/p/673102423

贺师俊

**TypeScript JSDoc 应用及其局限性** —— 数月前 Svelte 团队高调宣布放弃 TypeScript 并转向 JSDoc 一定算作个大新闻。本文则详细探讨了在纯 JavaScript 环境中使用 JSDoc 进行类型检查的可行性与局限性，以及为了缓解部分局限性的各种小技巧以及注意点。作者认为，即使在纯 JavaScript 环境下使用 JSDoc 提供的类型检查，也能在最小配置的情况下极大程度提高 JavaScript 项目的可维护性，但相比于直接使用 TypeScript，仍然存在诸多不便与局限性。

**长按识别二维码查看原文**

https://zhuanlan.zhihu.com/p/670568566

Snowflyt

**浏览器跨 Tab 窗口通信原理及应用实践** —— 多窗口下进行相互通信指在浏览器中不同窗口（包括不同标签页、不同浏览器窗口甚至不同浏览器实例）之间进行数据传输和通信的能力。这篇文章就介绍了如何使用纯前端技术实现多窗口通信。

**长按识别二维码查看原文**

https://zhuanlan.zhihu.com/p/669185635

Coco

notachraf 也发布了一篇文章 **无服务器实现多窗口共享状态** 探讨此问题！

**长按识别二维码查看原文**

https://medium.com/@not.achraf/sharing-a-state-between-windows-without-a-server-6d5c1716cbc8

**TypeScript 校验库 ArkType 简介** —— 如何在运行时进行类型校验一直是一个重要需求，在此领域已经存在了被广泛使用的 Zod 与更早的 AJV。而近期，由于不满于 Zod 语法冗长且性能较差的问题，ArkType 作为新一代的运行时类型校验工具被推出，它最大的特点是维持了几乎与 TypeScript 一比一的简洁语法，并且声称性能比 Zod 好得多。该库大量使用了 TypeScript 的类型体操技巧保证类型安全，使用户可以在编辑器中获得即时的类型推导反馈，并且相比于其他新兴的运行时校验工具如 Typia，它不需要安装任何额外插件就可直接使用。

**长按识别二维码查看原文**

https://zhuanlan.zhihu.com/p/650365261

Snowflyt

## 🛠 代码与工具

**💎 5 个超酷的 JavaScript 物理动画库 🤓**

**长按识别二维码查看原文**

https://dev.to/random_ti/5-cool-javascript-physics-libraries-f9

Random

**Shikiji：漂亮又强大的语法高亮工具** —— 与 VS Code 的语法高亮引擎相同，Shikiji（式辞）是一款基于 TextMate 语法和主题的美观且强大的语法高亮工具，它能够为几乎所有主流编程语言提供非常准确和快速的语法突出显示。Shikiji 无需维护自定义正则表达式，无需维护自定义 CSS，无需维护自定义 HTML。

**长按识别二维码查看原文**

https://shikiji.netlify.app/

antfu

## 🙋🏻‍♀️