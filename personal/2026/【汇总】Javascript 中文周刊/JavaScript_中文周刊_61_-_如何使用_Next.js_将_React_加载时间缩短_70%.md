# JavaScript 中文周刊 #61 - 如何使用 Next.js 将 React 加载时间缩短 70%

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511824&idx=1&sn=a2d0e278b2222667c2fc5ac2bbcacd6a&chksm=e921e4f2de566de4267560b10a8c2090cd604c20d9f1c38d9f981575fda0132d88a6f22cdbc8\#rd  
> 抓取时间: 2026/2/2 23:52:43

---

> 本期看点：上周，Turbopack 正式发布、SQLite 也发布了官方文档.……更多热门文章资讯请点击本期周刊查看！

> 编辑：Yucohny、山鬼、Jojo

## 🔥 本周热门

**Turbopack：基于 Rust 的 Webpack “继承者”** — 该项目目前已经超过了 30 亿的下载量。尽管 **webpack** 长期占据着构建工具冠军的宝座，同时 **Vite** 也在快速发展，但是 Vercel 还是认为它们太慢了，并资助了 **Turbopack** 的工作。这是一个值得关注的项目，它比 webpack 和 Vite 都有巨大的性能提升， **但依旧有一些限制需要考虑：**

**长按识别二维码查看原文**

https://vercel.com/blog/turbopack

- 尽管 Turbopack 和 Webpack 都来自于同一个创建者，但是 Turbopack 是否是 webpack 的“继承者”是有争议的，因为 Turbopack 还不能做很多 Webpack 可以做的事情。相比于 Turbopack，Webpack 是一个拥有自己维护者的活跃项目。

- 它与 React 和 Next.js v13 密切相关——随后将 **支持 Vue** 和 **Svelte**。

- 类似 Rust 驱动的 **SWC** 来转译 JS/TS。

- 如果你感兴趣，可以看看来自 Vite 的 Evan You 在推特上发布的关于 Turbopack 🐦 的**一系列看法**。

Koppers 和 Palmer (Vercel)

**快讯：**

- SQLite 项目发布了 **官方的 WASM/JS 文档**，这涉及到 SQLite 在 WebAssembly 和浏览器环境的上下文的 **场景**。sql.js 一直走在这个领域的前面并且逐渐升温。
    
    **长按识别二维码查看原文**
    
    https://sqlite.org/wasm/doc/ckout/index.md
    

- CodePen 是 **Preact** (React 的较小替代品) Playground 的理想场所 – 并且 Chris Coyierr **解释了如何使用**。
    
    **长按识别二维码查看原文**
    
    https://blog.codepen.io/2022/10/27/using-preact-on-codepen/
    

- Christian Heilmann 提醒我们，`JSON.stringify` **可以创建格式良好**、过滤后的，以及多行输出的字符串。
    
    **长按识别二维码查看原文**
    
    https://christianheilmann.com/2022/10/28/reminder-json-stringify-can-create-multi-line-formatted-and-filtered-strings-from-json/
    

## 📒 教程与趣事

**哪个无服务器边缘平台拥有最快的 Git 部署？** — Deno 背后的团队测试了一些流行的无服务器边缘计算提供商 （包括他们自己的 _Deno Deploy_ 查看哪个具有最快的 git 部署时间。面对不同的 benchmarks，应该有自己的判断，必要时可以自行进行测试。

**长按识别二维码查看原文**

https://deno.com/blog/fastest-git-deploys-to-the-edge

Andy Jiang (Deno)

**我们如何使用 Next.js 将 React 加载时间缩短 70%** — 将 _Create React App_ 替换为 Next .js，业务规划平台 **Causal** 通过减少加载时间显着改善了用户体验。如何？好吧，只需一点点 SSR 就能让您走得更远。

**长按识别二维码查看原文**

https://www.causal.app/blog/next-js

Causal Engineers

**如何使用 Fresh 和 Deno 构建博客** — 在其他 Deno 新闻中，如果您想尝试一下 Deno，但不确定要做什么，如何在 Fresh Web 框架 上创建一个简单的博客？然后快速部署到 Deno Deploy。

**长按识别二维码查看原文**

https://deno.com/blog/build-a-blog-with-fresh

Andy Jiang (Deno)

**如何用 JavaScript 编写你的第一个单元测试** — 如果您是多产的测试人员，请继续滚动。如果不是，这是一个非常简单的入门。

**长按识别二维码查看原文**

https://snyk.io/blog/how-to-write-unit-test-in-javascript/

Chip Verek

**检测来自 JS 的系统主题偏好更改** — `window.matchMedia` 和 `addEventListener` 进行处理。

**长按识别二维码查看原文**

https://davidwalsh.name/detect-system-theme-preference-change-using-javascript

David Walsh

**Angular 14.2 路由器的进步。**

**长按识别二维码查看原文**

https://blog.angular.io/advancements-in-the-angular-router-5d69ec4c032

Andrew Scott

**使用来自 Alpine.js 的 Cloudinary 的图像 API。**

**长按识别二维码查看原文**

https://www.raymondcamden.com/2022/10/27/using-cloudinary-with-alpinejs

Raymond Camden

## 🛠 代码与工具

**npoint：带有模式验证的简单 JSON 存储箱** — 当你在开发应用程序或网站，或者只是单纯试一试新的库时，你可以使用 npoint 作为轻量级后端。如果您愿意，您甚至可以让其他人更改数据。

**长按识别二维码查看原文**

https://www.npoint.io/

Alex Zirbel

**Satori：将 HTML 和 CSS 转换为 SVG** — React 和 JSX 是实现这一目标的首选途径，但即使没有它们，Satori 仍然可以工作。值得关注的是，它支持 Vercel 的新 **“社****交卡”图像生成** 功能。

**长按识别二维码查看原文**

https://github.com/vercel/satori

Vercel

**Downshift v7.0：构建可访问的 React 组件** — 增加了能够提供有状态逻辑的钩子来实现可以创建自动完成、组合框和“选择”框的下拉组件，然后可以依靠这些组件来实现与手机的网页应用技术兼容的优点。

**长按识别二维码查看原文**

https://www.downshift-js.com/

PayPal

🎉 **Canvas Confetti：在你的浏览器中加载五彩纸屑！** — 准备好使用 Confetti 在浏览器中放些烟花了吗！这里有大量的演示可以查看，欢迎查看 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.kirilv.com/canvas-confetti/

Kiril Vatev

**版本发布：**

- **Babel v7.20.0** - 现在支持 TypeScript v4.9 和 Deno 作为编译目标。

- **Handsontable v12.2** - 流行的电子表格数据网格。

- **Deno v1.27** – 区别于 Node.js 和 Bun 的 JS 服务器端运行时。

- **Qwik v0.12** – HTML 优先框架。

- **NPKILL v0.9** - 列出 `node_modules` 目录并清理。

- **Wild Wild Path v3.3** - 带有通配符和正则表达式的对象属性路径。

- **capture-website v3.2** - 使用 Puppeteer 捕获网站的屏幕截图。

- **Mongoose v6.7** – Node.js 的 MongoDB 对象建模库。

👻 正好赶上万圣节…

**Creepyface：使人脸图像“跟随”鼠标** — 这是我们的团队成员的面孔跟随你的鼠标移动的效果。如果你想重新创建属于自己的效果，那么快去吧，此时正赶上万圣节特别版！这里有为 React 用户打造的 **一个组件**。

**长按识别二维码查看原文**

https://creepyface.io/

Alejandro Tardín

## 🙋🏻‍♀️