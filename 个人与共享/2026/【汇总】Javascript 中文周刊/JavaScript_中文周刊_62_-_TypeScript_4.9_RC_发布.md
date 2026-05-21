# JavaScript 中文周刊 #62 - TypeScript 4.9 RC 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511982&idx=1&sn=e4932725e491e67fb4de76938a7f6021&chksm=e921e44cde566d5ae599a3789aa410ac231c4dac21e2e618cd618cf2968bc43c0714b897c1d8\#rd  
> 抓取时间: 2026/2/2 23:52:41

---

> 本期看点：上周，Evan You 在 GitHub 上发布了 Turbopack 与 Vite 关于 HMR 的速度对比的测试结果文章，引起了广泛的讨论.……更多热门文章资讯请点击本期周刊查看！

> 编辑：Jojo、Yucohny、Matrixbirds

## 🔥 本周热门

**JavaScript 中的 “realm” 是什么？** — 关于 ‘realm’ 我们平常是用不到的，但是了解它会加深你对底层 JS 的理解。realm 本质上是 JavaScript 程序的完整执行环境。

**长按识别二维码查看原文**

https://weizman.github.io/page-what-is-a-realm-in-js/

Gal Weizman

> 如果你的 _真的_ 想一探究竟，那么就和  Axel 一起，进入 **ShadowRealm** 的世界吧… …

**Turbopack 真的比 Vite 快 10 倍吗？** —上周的大新闻是 **Turbopack** 的发布，它是基于 Rust 的 Webpack “继任者”。Turbopack 在宣传时说比 vite 快了十倍， 尤雨溪亲自写了这篇文章对此说法进行反驳，并运行了一些基准测试进行更细致的性能对比。（Turbopack 已经对此进行道歉）

**长按识别二维码查看原文**

https://github.com/yyx990803/vite-vs-next-turbo-hmr/discussions/8

Evan You

**Shopify 收购 _Remix_ 项目** — 在开源仅仅一年之后，**Remix**，一个令人兴奋的全栈 Web 框架及其相关公司，已被电子商务巨头 Shopify 收购。Dion 在这里解释了原因，但如果你更喜欢▶️ **简短的两分钟视频概述** Fireship 频道收录了这个新闻。

**长按识别二维码查看原文**

https://shopify.engineering/remix-joins-shopify

Dion Almaer (Shopify)

**TypeScript 4.9 RC 发布** — 期待已久的版本又向前迈进了一大步。`satisfies` 用以验证表达式的类型是否匹配某些类型，而 _不更改_ 实际结果类型。这里还有 **类的 auto-accessors**（ES 本身即将推出的功能）和编辑器增强功能，比如 **删除未使用的导入 和 导入排序**。4.9 最终版预计在两周后亮相。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-9-rc/

Daniel Rosenwasser

**快讯：**

- _React Native_ **已将其默认的新应用程序模板**从 Flow 切换为 TypeScript。
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/react-native/pull/35165
    

- 🎄 Vue 的开发者正在传递一封**✉️ Advent of Vue的电子邮件**，它承载了一组以节日主题的编码谜题去构建 Vue 组件。去思考 代码的 Advent of Code 但更多的是 Vue-y！
    
    **长按识别二维码查看原文**
    
    https://adventofvue.com/
    

- **The Component Gallery** 触手可及方便索引的组件库。
    
    **长按识别二维码查看原文**
    
    https://component.gallery/components/
    

- Svelte 团队分享了截至 2022 年 11 月的**更新状态**。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-november-2022
    

## 📒 教程与趣事

**2022 年如何构建，测试并发布一个 TypeScript 编写的 npm 包 —** 在这篇内容精炼又贴心的演练文章里，介绍了这些基本步骤。

**长按识别二维码查看原文**

https://www.strictmode.io/articles/build-test-and-publish-npm-package-2022

Ianis Triandafilov

**‘Next.js 打包出的产物会感谢你’** — 如果你的 Next.js 应用打包出的产物比预期的更加大一些，前端工程师 Renato 的打包优化建议会使你受益。

**长按识别二维码查看原文**

https://renatopozzi.me/articles/your-nextjs-bundle-will-thank-you

Renato Pozzi

**设计一个符合正常人阅读的计算日期差的 JavaScript 工具库** — 有许多类似的工具库提供了“2 分钟之前”, “五个月之前” 或者 “一年之前”，这样的功能，你是否有了解到 `Intl` API 也可以做到？如：`Intl.RelativeTimeFormat()`，支持国际化数词。GitHub 官方仓库的**relative-time** 可以帮助你了解更多 Intl API 的使用。

**长按识别二维码查看原文**

https://www.amitmerchant.com/human-readable-date-difference-in-javascript/

Amit Merchant

**基于 Storybook test runner 实践代码测试的覆盖率 —**代码测试的覆盖报告会显示当前测试覆盖了多少的代码，帮助你找到未覆盖测试的地方。Storybook 的 test runner 工具可生成测试覆盖报告，并且现已支持 React、Preact、Svelte 和 Vue 这些主流框架的开箱即用。

**长按识别二维码查看原文**

https://storybook.js.org/blog/code-coverage-with-the-storybook-test-runner/

Yann Braga (Storybook)

**教你打包并发布一个 Vue.js 3.0 插件的 npm 包** — 使用 Vite 打包构建出产物，使用`vue-tsc`生成类型带来更好的开发体验。

**长按识别二维码查看原文**

https://vueschool.io/articles/vuejs-tutorials/how-to-package-and-distribute-a-vue-js-3-plugin-on-npm/

Daniel Kelly

**实现一个支持无障碍能力的提示框 UI 组件** — 一个支持颜色自适应且具有无障碍能力的`<tool-tip>`自定义 UI 组件，这篇文章介绍了它的实现思路。这里也有一个 ▶️ **视频版本的教程** 可供参考，精简版本的 JavaScript 实现。

**长按识别二维码查看原文**

https://web.dev/building-a-tooltip-component/

Adam Argyle

**▶ 基于 React 和 Three.js 复刻一个我的世界游戏 —** _**(91 minutes.)**_

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=qpOZup_3P_A

Daniel Berk

**用 WasmEdge 基于 Webassembly 运行 JavaScript 程序** — 这篇文章会带你分析它的优势和劣势。

**长按识别二维码查看原文**

https://www.secondstate.io/articles/run-javascript-in-webassembly-with-wasmedge/

Second State

**JavaScript Promise API 的概览**

**长按识别二维码查看原文**

https://www.sitepoint.com/overview-javascript-promises/

Sandeep Panda & James Hibbard beginner

## 🛠 代码与工具

**Vuestic UI 1.5: 一个 Vue 3.0 的 UI 组件库** — 这是一个提供了 60 个可定制 UI 的组件库。**v1.5** 是一个重大版本，在无障碍能力方面有显著的提高。并且提供了新的树级组件，视图分割条，下拉框和虚拟列表等组件以及暗黑主题模式等等。更多功能参见**官方网站**。

**长按识别二维码查看原文**

https://github.com/epicmaxco/vuestic-ui

Epicmax

**Joi v17.7: 对象结构描述及数据校验工具库** — Joi 可以用简单的方式帮助你描述应用里的数据结构，API 易用且直观，它可以校验数据的合法性，示例代码：`Joi.string().min(3).max(30)`。

**长按识别二维码查看原文**

https://joi.dev/api/?v=17.7.0

Sideway Inc.

**directory-serve: 便捷的将你的目录发布成 HTTP 服务** — 只需要你本地具有 Nodejs 以及 npm 环境的安装，执行`npx directory-serve .`就可以得到一个 HTTP 的服务器，并将你当前的目录发布成 HTTP 应用。

**长按识别二维码查看原文**

https://github.com/cube-root/directory-serve

Cube-Root

**relative-time: 一个支持本地化相对时间的时间格式化标签**— 这个组件提供标准化的日期时间的格式化能力，它会渲染出对应的时间格式文本。

**长按识别二维码查看原文**

https://github.com/github/relative-time-element

GitHub

**Pinceau: 一个基于 Vue 的 CSS in TypeScript 的框架**— 当前项目虽然处于早期阶段，但已可以和 Vue 无缝集成。并且支持 Nuxt，Vitesse 和 Vite 一起集成。

**长按识别二维码查看原文**

https://github.com/Tahul/pinceau

Yaël Guilloux

**Markdoc v0.2: 一个灵活的，基于 Markdown 的静态网站制作框架** — 一种 Markdown 能力的扩展，可用于博客和文档。可以直接用于 Stripe 平台的文档，也可以单独在你自己的系统里使用它。**GitHub  开源仓库地址**。

**长按识别二维码查看原文**

https://markdoc.dev/

Stripe

**版本发布:**

- **Redux Toolkit v1.9** – Redux 官方的工具集。

- **Foal v3.0** – 一个功能完备的 Node.js web 应用开发框架。

- **Vuetify 3.0** – Material 设计风格的 Vue UI 组件库。

- **Ember v4.8.1, v4.4.4, v3.28.10 & v3.24.7** – Ember 框架的安全特性升级。

- **VS Code** – 2022 年 10 月版本

- **jest-image-snapshot v6.0** 可视化的图像比较工具，最常用于视觉回归测试。

- **Sigma.js v2.4** 高性能的渲染图像渲染库。

- **Docusaurus v2.2** Meta 文档静态站点搭建框架。

- **Taxi v1.2** 精简工具库支持基于 PJAX 的导航能力和动画能力。

- **Jasmine v4.5** – 支持 Node.js 和浏览器环境的测试框架。

- **Chartist.js v1.3** – 简单易用的响应式图表库。

- **Forge v6.0** – 便于开发 Electron 应用&构建发布的工具。

- **React Toastify v9.1** – 简单易用可定制的 React 通知组件。

- **vanilla-tilt.js v1.7.3** – 体验流畅的 3D 贴图工具库。

## 🙋🏻‍♀️