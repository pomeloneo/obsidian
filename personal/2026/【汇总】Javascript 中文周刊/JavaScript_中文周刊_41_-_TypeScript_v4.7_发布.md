# JavaScript 中文周刊 #41 - TypeScript v4.7 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247506516&idx=1&sn=f1359aa1ef534420fa205644e00708e0&chksm=e92191b6de5618a004a8ff2e18fbb59fb5f5a9455d6063fc08091845a438f1c4e43fbaae779b\#rd  
> 抓取时间: 2026/2/2 23:53:09

---

> 本期看点：本期为大家带来了 Airbnb 如何通过 Metro 获得更快的 JavaScript 构建速度和 2022 年 Reacrt 状态管理库总结等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi、Black-Hole、Levi

## 🔥 本周热门

**比较三种不改变原数组的数组处理方法** — 作者 Dr. Axel 对比了 `for-of`，`.reduce()` 和 `.flatMap()` 这三种不改变原数组的数组处理方法。读完本篇文章你就可以选择最适合你自己的方法来处理数组。

**长按识别二维码查看原文**

https://2ality.com/2022/05/processing-arrays-non-destructively.html

Dr. Axel Rauschmayer

**npm 安全更新：GitHub 从四月的攻击中得到的启示** — 上个月，GitHub，npm 注册表的管理者，**报告** 说被盗的 OAuth 令牌被用来访问某些私人仓库、私人软件包清单和元数据，以及 npm 用户账户数据。值得注意的是: _“GitHub 发现了一些 npm 注册表的明文用户凭证，这些凭证是在 npm 整合到 GitHub 日志系统后在内部日志中捕获的。”_ 注意：**不要在版本控制（或日志）中存储秘文或凭证。**

**长按识别二维码查看原文**

https://github.blog/2022-05-26-npm-security-update-oauth-tokens/

Greg Ose（GitHub）

**TypeScript v4.7 发布** — 本次最主要的更新就是对 Node.js 的 ESM 的支持 – 对这个特性的支持的过程还是比较艰辛的。**本次更新对文件扩展名的依赖依然引起了争论**。点击链接查看详情。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-7/

Daniel Rosenwasser

Next.js Layouts RFC：Next.js 的重大更新 — 如果你是 Next.js 的用户，那么建议你阅读本篇文章，因为一些重要的更新即将到来，特别是围绕路由、应用结构和布局（包括嵌套布局）。

**长按识别二维码查看原文**

https://nextjs.org/blog/layouts-rfc

Neutkens, Markbage, et al.（Vercel）

**快讯：**

- DigitalOcean 推出了一个 **新的无服务器功能平台** – 你可以直接在上面运行你的 JS 代码。
    
    **长按识别二维码查看原文**
    
    https://www.digitalocean.com/blog/introducing-digitalocean-functions-serverless-computing
    

- Angular v14（目前处于 RC 阶段）即将发布 – **快来看看有什么新的内容**。
    
    **长按识别二维码查看原文**
    
    https://nevzatopcu.medium.com/what-is-new-in-angular-14-d31edf91fd3e
    

- Netlify 聘请了 SolidJS 项目的创始人 Ryan Carniato 全职工作 – **这是他发布的文章**
    
    **长按识别二维码查看原文**
    
    https://www.solidjs.com/
    

- 下周，**Node v17 将不再维护**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/trott/status/1529593378190393344
    

- _Ghost_ 是一个由 Node.js 构建的 CMS 和博客平台，已经成为一个独立的生态系统，现在有一个新的主要版本：**Ghost v5.0**
    
    **长按识别二维码查看原文**
    
    https://ghost.org/changelog/5/
    

**版本发布：**

- **Electron v19** – 支持了 Chromium v102、V8 v10.2 和 Node v16.14.2。

- **Neutralino.js v4.6** – 轻量级跨平台的桌面应用程序框架。

- **fast-check v3.0** – 基于属性的测试框架。

- **Knex v2.1.0** – 用于 Node.js 的 SQL 构建器。

- **Cypress v9.7.0** – 在浏览器中测试任何内容。

- **Storybook v6.5** – UI 组件开发工具。

## 📒 教程与趣事

**什么是“边缘计算”？** — 本篇文章主要介绍了传统服务器、客户端（浏览器）、静态站点生成器以及云函数之间的优劣。

**长按识别二维码查看原文**

https://austingil.com/edge-compute-knitted-dog-hats/

Austin Gil

**Airbnb 如何通过 Metro 获得更快的 JavaScript 构建速度** — Airbnb 从 Webpack 迁移到 **Metro**（一个针对 React Native 的 JavaScript 构建工具，但 Airbnb 将其用于 Web 项目）以及它如何使他们的开发反馈”几乎瞬间完成“。

**长按识别二维码查看原文**

https://medium.com/airbnb-engineering/faster-javascript-builds-with-metro-cfc46d617a1f

Rae Liu

**如何将我们的 Node.js 库转换成 Done （使用 Deno）** — 我们找到了一种 ”运行时适配器“ 模式，我们认为它代表了一种通用的方法，可能对其他希望支持 Deno 的库作者有用。

**长按识别二维码查看原文**

https://www.edgedb.com/blog/how-we-converted-our-node-js-library-to-deno-using-deno

James Clarke (EdgeDB)

**2022 年 Reacrt 状态管理库总结** — 这个领域有很多选择，包括 Zustand、Recoil、XState，当然还有 Redux。

**长按识别二维码查看原文**

https://www.albertgao.xyz/2022/02/19/react-state-management-libraries-2022/

Albert Gao

**JSON 和 JavaScript 中字符串化的怪象** — 这不是最直截了当的方式，虽然至少有一个（复杂的）【**书面规范**】用于解释 `JSON.stringify` 的操作。

**长按识别二维码查看原文**

https://www.zhenghao.io/posts/json-oddities

Zhenghao

**从 SPA 到 MPA** — 本篇文章主要介绍了当前 SPA 所面临的挑战，以及介绍了为什么需要向 MPA 转变。

**长按识别二维码查看原文**

https://nolanlawson.com/2022/05/21/the-balance-has-shifted-away-from-spas/

Nolan Lawson

**避免 Puppeteer 的反模式**

**长按识别二维码查看原文**

https://serpapi.com/blog/puppeteer-antipatterns/

Greg Gorlen

**让 Astro 在构建 Web 应用时，与众不同的 5 个方面**

**长按识别二维码查看原文**

https://launchdarkly.com/blog/5-things-that-make-astro-unique-for-building-web-apps/

Brian Rinaldi

## 🛠 代码与工具

**🥷  Ninja Keys：向你的应用或网站添加命令面板或设置键盘快捷键** — 如果你在 GitHub 中使用过 `Cmd/Ctrl+K` 或者在 VS Code 中使用过命令面板，你会觉得很熟悉，它可以用在原生 JS 中或者与 Vue、React 或者 Svelte 一起使用。**这里有Demo 页面**。**Kbar** 是专注于 React 的另一个同类库。

**长按识别二维码查看原文**

https://github.com/ssleptsov/ninja-keys

Sergei Sleptsov

**Filesize.js：将文件大小转为可读的字符串** — 举个例子，`"123456 bytes"` 可以转为 `"120.56 KB"`，同时也它可以支持不同的转换标准。**GitHub 仓库**

**长按识别二维码查看原文**

https://filesizejs.com/

Jason Mulligan

**LunchboxJS：为 Vue 定制的 Three.js 渲染器** — 这里有完整的 **文档**，可以把它理解为 Vue 版的 react-three-fiber。

**长按识别二维码查看原文**

https://lunchboxjs.com/

Breakfast Studio LLC

**React-Uploady v1.0：文件上传组件** — 该组件的目标是简单易用而且高度可定制，具有文件上传按钮，预览，拖放上传区域等功能。**文档很完善**，**还有录屏演示**。

**长按识别二维码查看原文**

https://react-uploady.org/

Yoav Niran

**EStimator.dev：现代 JavaScript 优化计算器**— 该计算器可以计算出某一网站利用更现代的 JS 语法对于页面大小优化量。

**长按识别二维码查看原文**

https://estimator.dev/

Google Chrome Labs

**Browser Extension Template：快速创建浏览器扩展的项目框架** — 有点类似 create-react-app 那样。

**长按识别二维码查看原文**

https://github.com/Debdut/browser-extension

Debdut Karmakar

**Nuxt Content v2：映射来自 content 目录的 Markdown、YAML、CSV 或 JSON 文件的 Nuxt 模块**

**长按识别二维码查看原文**

https://content.nuxtjs.org/blog/announcing-v2/

Chopin, Guilloux, Birang, and Ollivier

## 🙋🏻‍♀️