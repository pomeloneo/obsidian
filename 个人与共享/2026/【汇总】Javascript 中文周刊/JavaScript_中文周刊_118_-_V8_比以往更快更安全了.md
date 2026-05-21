# JavaScript 中文周刊 #118 - V8 比以往更快更安全了

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525812&idx=1&sn=6fb40178fa040721ba7dbb08eef32e3e&chksm=e9212e56de56a7408b8a2193bd466487e8fa4153a13f8487063b1e802e3281d4d5344bc1241b\#rd  
> 抓取时间: 2026/2/2 23:51:29

---

> 本期看点：V8 团队希望在年底取得出色的表现，现在他们在性能方面有了巨大的进展。这篇文章涵盖了 2023 年 V8 引擎的亮点，包括新的 Maglev 中间层 JIT 编译器、更快的 HTML 解析器以及对几种新 JavaScript 功能的支持。

> 编辑：Yucohny、TimLi

## 🔥 本周热门

**🎉 V8 比以往更快更安全** —— V8 团队希望在年底取得出色的表现，现在他们在性能方面有了巨大的进展。这篇文章涵盖了 2023 年 V8 引擎的亮点，包括新的 Maglev 中间层 JIT 编译器、更快的 HTML 解析器以及对几种新 JavaScript 功能的支持。

**长按识别二维码查看原文**

https://v8.dev/blog/holiday-season-2023

Victor Gomes（V8）

**SvelteKit 2 发布** —— SvelteKit 的第一个官方版本发布已经一年了，尽管发布不算太久，但该框架已经迅速被社区所接受。v2.0 版本是一个渐进式版本，增加了对 **Vite 5** 的支持，并为即将于 2024 年发布的 **Svelte 5** 打下基础。

**长按识别二维码查看原文**

https://svelte.dev/blog/sveltekit-2

Svelte

**date-fns v3 发布** —— 这个 JavaScript 中用于处理日期的超级流行套件已经使用 TypeScript 重写、重新引入字符串日期参数、新增对 Node 的 ESM 支持以及所有函数都通过命名导出。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://blog.date-fns.org/v3-is-out/

Sasha Koss

**▶ TypeScript 起源：纪录片** —— 视频在 JavaScript 周刊中通常不受欢迎，但这部最受欢迎！我真正享受观看全部内容；制作得非常好。它深入探讨了 TypeScript 创建和发布背后的动机和过程，并且可以轻松取代你圣诞节播放列表中的《虎胆龙威》。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=U6s2pdxebSo

OfferZen

**26 个你可能没听过的 web 开发术语**

**长按识别二维码查看原文**

https://meiert.com/en/blog/26-other-web-development-terms/

Jens Oliver Meiert

**快讯：**

- **RIP Vue 2.x**：如果你正在使用 Vue 2，请做好准备：**Vue 2 将于 2023 年 12 月 31 日“终止生命周期”（EOL）**。

**长按识别二维码查看原文**

https://blog.vuejs.org/posts/vue-2-eol

- 我们重新审视了 Robin Wieruch 在 2023 年 1 月提出的 **2023 年的 10 个 web 开发趋势** —— 他的观点很有远见。

**长按识别二维码查看原文**

https://www.robinwieruch.de/web-development-trends/

- Linus Schlumberger 回顾了过去三年中 **所有 JavaScript 和 TypeScript 主要的新功能**。

**长按识别二维码查看原文**

https://betterprogramming.pub/all-javascript-and-typescript-features-of-the-last-3-years-629c57e73e42?gi=88591fce019a

- 相反，The New Stack 着眼于 **JavaScript 的未来方向**。

**长按识别二维码查看原文**

https://thenewstack.io/whats-next-for-javascript-new-features-to-look-forward-to/

## 📒 2023 教程与趣事经典回顾

**使用现代方式在 JavaScript 中实现深度克隆对象** — 现在不再需要 Lodash 之类的东西实现深度克隆，内置的 `structuredClone` 函数，可以让 JavaScript 中的深度克隆对象变得轻而易举。

**长按识别二维码查看原文**

https://www.builder.io/blog/structured-clone

Steve Sewell

**🔥 Web Components 将比 JavaScript 框架更长寿** —— 这是一篇观点激进的文章。Jake 在他的 **CRDT 系列博客文章中** 更多关注原生 JavaScript Web Components 而非像 React 一样的框架。

**长按识别二维码查看原文**

https://jakelazaroff.com/words/web-components-will-outlive-your-javascript-framework/

Jake Lazaroff

**移除事件监听器的多种方式** —— 回顾一些常见的方法，用于在 JavaScript 中移除事件监听器。

**长按识别二维码查看原文**

https://www.macarthur.me/posts/options-for-removing-event-listeners

Alex MacArthur

**无需构建系统编写 JavaScript** — 使用各种构建工具来进行打包和转换是当今 JavaScript 开发中的常见做法，但是如果你想保持简单会怎样呢？Julia 表示，对于简单的事情是没有必要的。这在 **Hacker News 上引起了大量讨论**。

**长按识别二维码查看原文**

https://jvns.ca/blog/2023/02/16/writing-javascript-without-a-build-system/

Julia Evans

2023 年是 **在浏览器中广泛支持导入映射** 的一年，为 JavaScript 的免构建方式提供了额外的机会。然而，根据 DHH **对“无需构建”体验的激动反应** 来看，整个话题仍然有些含糊不清。

**长按识别二维码查看原文**

https://web.dev/blog/import-maps-in-all-modern-browsers

## 🛠 2023 年代码与工具经典回顾

**Playwright 迎来重要的一年** —— 这款流行的 web 测试和自动化框架在 2023 年迈出了一些重要的步伐，尤其是在 v1.32.0 中推出了“UI 模式”，让开发者可以在 UI 环境中探索、运行和调试测试，并配备了内置的监视模式。▶️ **这个视频** 提供了很好的介绍。

**长按识别二维码查看原文**

https://github.com/microsoft/playwright/releases/tag/v1.32.0

Microsoft

**或许你不需要 Lodash 或 Underscore** —— 受 **《你也许不需要 jQuery》** 一文启发，这份详尽的文档提供了像 **Lodash** 一样的 100 种不同函数的纯 JavaScript 替代方案。

**长按识别二维码查看原文**

https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore\#readme

You Don’t Need

**Driver.js：制作页面导览、突出显示与上下文帮助** —— 无依赖的原生 JavaScript 库，用以搭建页面导览和上下文帮助系统。该项目存续多年，近期全新完善并新增 **种种改进**，还被全新打造。这里有许多实例可供参考。

**长按识别二维码查看原文**

https://driverjs.com/

Kamran Ahmed

**🤖 Transformers.js：在浏览器中运行机器学习模型** — Transformers 是一种常用于自然语言或视觉处理的机器学习模型，虽然在浏览器中直接运行这样的模型还处于起步阶段，但 Transformers.js 为你提供了一些机器学习模型，并有一些令人印象深刻的演示。

**长按识别二维码查看原文**

https://xenova.github.io/transformers.js/

Xenova

**DeviceScript：专为微型设备设计的 TypeScript**——DeviceScript 是微软新推出的一种语言，旨在将 TypeScript 的编程体验应用到低资源的微控制器设备中。它被编译为一种自定义的虚拟机字节码，可以在这样的受限环境中运行（类似于 Go 的 **TinyGo**）。虽然主要面向 VS Code 用户，但也提供了 **命令行选项**。

**长按识别二维码查看原文**

https://microsoft.github.io/devicescript/

Microsoft

## 🙋🏻‍♀️