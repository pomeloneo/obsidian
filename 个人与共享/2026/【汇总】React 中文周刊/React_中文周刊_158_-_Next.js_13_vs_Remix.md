# React 中文周刊 #158 - Next.js 13 vs Remix

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524371&idx=1&sn=fb6b51782415118587bede9262296f5e&chksm=e9212bf1de56a2e7e678aa206e90c02c11fc358dc7ce806d780e69854f4b721fdd104dde209c\#rd  
> 抓取时间: 2026/2/2 23:44:51

---

> 本期看点：本期介绍了一篇文章，其对 Next.js 与 Remix 这两个流行框架进行了功能点对比，也对它们之间的相似性和差异进行了深入探讨。

> 编辑：Yucohny、TimLi777、edison-hm

## 🔥 本周热门

**Tailwind Next.js Starter Blog v2.0：一个 Next.js 博客的启动模板** —— 这个项目已经存在了几年，并且一直在频繁更新，现在使用了现代化的 Next 应用目录方式以及服务器组件 —— 这里有 **完整的更新说明**。顺便一提，这篇文章就是用这个博客模板创建的实例上托管的 ;-)

**长按识别二维码查看原文**

https://github.com/timlrx/tailwind-nextjs-starter-blog

Timothy Lin

**Next.js 13 vs Remix：一个案例研究** —— 这篇文章不仅仅对两种流行框架之间进行了功能点对比，更对它们之间的相似性和差异进行了深入探讨。

**长按识别二维码查看原文**

https://prateeksurana.me/blog/nextjs-13-vs-remix-an-in-depth-case-study/

Prateek Surana

**Memoization 的艰难之战** —— 两年前，Dan Abramov 写过一篇关于 **在你使用** `**memo()**` **或** `**usememo**` **之前应做的事情** 的文章，而现在 Dominik 更进一步探讨了为什么 memo 不应该是进行性能优化的首选。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/the-uphill-battle-of-memoization

Dominik Dorfmeister

**使用 Yalc 本地测试 React 库** —— **Yalc** 简化了开发包与“发布”包的流程，这些都能够完全在本地完成。现在可以尝试无需发布到远程便可以公开注册表。

**长按识别二维码查看原文**

https://www.propelauth.com/post/test-your-react-libraries-with-yalc

Andrew Israel（PropelAuth Blog）

**探索 Next.js 中的 React 服务器组件和服务器操作**

**长按识别二维码查看原文**

https://www.antstack.com/blog/exploring-react-server-components-and-server-actions-with-next-js/

Hafsa Hayath

**使用 GitHub Actions 自动化 React Native 工作流**

**长按识别二维码查看原文**

https://elazizi.com/posts/5-github-actions-to-automate-your-react-native-workflow/

Youssouf El Azizi

**快讯：**

- GitHub 的一位工程师写了一篇关于她是 **如何使用 Copilot Chat 构建一个 React 应用原型** 的文章。我个人认为，这种聊天“虚拟配对”方式比 Copilot 的传统“自动完成”方式更有用。

**长按识别二维码查看原文**

https://github.blog/2023-09-27-how-i-used-github-copilot-chat-to-build-a-reactjs-gallery-prototype/

- 也许你知道 **Remotion** 是一个用于从 React 创建视频的热门库，但是你知道 **它推出了一个赏金计划吗**？

**长按识别二维码查看原文**

https://www.remotion.dev/

## 🛠 代码与工具

**react-markdown：支持渲染 Markdown 文档的组件** —— 一种稳定、可扩展且安全的 Markdown 渲染方式，它内部实现了一套虚拟 DOM，并且新版本也已升级 React 18 了。这里是 **GitHub 地址**。

**长按识别二维码查看原文**

https://remarkjs.github.io/react-markdown/

Espen Hovlandsdal

**Craft.js v0.2：构建拖拽页面编辑器** —— 将项目的引导页以文本编辑器的形式展示是一个大胆的举动，但是我们觉得这很酷。这里是 **GitHub 地址**。

**长按识别二维码查看原文**

https://craft.js.org/

Prev Wong

**nice-modal-react：eBay 在 React 中管理模态框的方法** —— 这个管理模态框的方式非常的 React，并且没有任何依赖。你可以试试 **在线 demo**。

**长按识别二维码查看原文**

https://github.com/eBay/nice-modal-react

eBay

**ReactToPrint：打印 React 组件** —— 该库通过弹出一个堪比原生打印窗口的形式，使用户可以打印 React 组件（是的你没看错，就是打印——尽管目前只能打印为 PDF）。点击查看 **CodeSandbox 演示**。

**长按识别二维码查看原文**

https://github.com/gregnb/react-to-print

Greg NB 与 Matthew Herbst

**React Native BLE PLX v3.0：低功耗蓝牙库** —— 蓝牙低功耗是一种大量应用于可穿戴健康和健身外设领域的技术。该库开放了 React Native 与此类设备的集成，不过不支持传统的蓝牙设备。

**长按识别二维码查看原文**

https://github.com/dotintent/react-native-ble-plx

Intent

**Neobrutalism：React 组件集合** —— 我们并不确定所谓的 **ne(o|u)brutalism** 是否会一直存在下去，但这个组件库仍然对标着市面上的其他组件库。这里是 **GitHub 地址**。

**长按识别二维码查看原文**

https://neobrutalism-components.vercel.app/docs

Samuel Breznjak

**版本发布：**

- **react-native-big-calendar v4.3** – 用于 React Native 应用程序的 Google Calendar/Outlook 风格的全页日历。

- **react-inlinesvg v4.0.5** – 将内嵌、本地或远程 SVG 加载到 React 组件中。

- **next-translate v2.6** – 适配 Next.js 的简易国际化库。

- **prism-react-renderer v2.1** – 利用 Prism 高亮显示 React 元素。

- **useFilePicker v2.1** – 打开系统文件选择的 hook。

- **vaul v0.7** – 不自带样式的抽屉组件。

- **React Aria October 2023**

- **react-native-geolocation v3.1**

## 🙋🏻‍♀️