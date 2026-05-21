# React 中文周刊 #133 - “react.dev”：全新 React 官网

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518258&idx=1&sn=467884e3b0e7b8ba7cf91483561d9846&chksm=e921c3d0de564ac6784b8091eb766709a30176d657d26f82bbb174f64137c9a25b6e37ce5377\#rd  
> 抓取时间: 2026/2/2 23:45:44

---

> 本期看点：在 2023 年如何启动一个 React 项目；回顾 React Hook 诞生的历史。

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**“react.dev”：全新 React 官网** — 随着 “reactjs․org” 退出了历史舞台，如今 React 已经推出了全新的官网，其实新的官网已经以 beta 形式开放了一段时间，无论是基础内容的数量还是现代 React 开发实践方面，新官网都有显著的提升。Dan Abramov 和 Rachel Nabors **在这篇介绍博文中** 做了更详细的解释。

**长按识别二维码查看原文**

https://react.dev/

React.js Project

**在 2023 年如何启动一个 React 项目** — 如今要启动一个 React 项目有很多选择，作者分析了各自的优劣，并针对一些可能出现的实际案例提供了建议。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-starter/

Robin Wieruch

**新的 React 文档是否 “假装 SPA 不存在了”？** — Matija 在新的 React 文档中提到，除非“你的应用有特殊的限制”，否则建议使用 “React 驱动的框架”。这么说的原因似乎主要是因为框架可以提供 SSR/SSG 能力，但是正如我们将在本周快讯中所看到的，像 Next.js 这样的框架对于单页应用来说仍然是很好用的。

**长按识别二维码查看原文**

https://wasp-lang.dev/blog/2023/03/17/new-react-docs-pretend-spas-dont-exist

Matija Sosic (Wasp)

**用 React 服务端组件在 Next.js v13 中实现国际化** — 本文展示了一个创建多语言应用的案例，它使用 **next-intl** 来实现 i18n，案例还展示了加入一些轻交互的技巧。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/03/internationalization-nextjs-13-react-server-components/

Jan Amann (Smashing Magazine)

**回顾 React Hook 诞生的历史** — 在此向哲学家桑塔亚纳表示歉意，他说过“那些不能记住历史的人注定要重蹈覆辙”。因此，本文快速回顾了 React Hook 诞生的历史，避免重复造轮子。

**长按识别二维码查看原文**

https://reacttraining.com/blog/where-did-hooks-come-from

Brad Westfall

**在 Qwik 应用中实现 Framer Motion 动画** — 本文还额外介绍了 **Motion One** 库，和 Framer Motion 类似，但是用起来更轻量更便捷。

**长按识别二维码查看原文**

https://www.builder.io/blog/framer-motion-qwik

Yoav Ganbar

**在 Digital Ocean 的 _App Platform_ 上部署 React 应用** — 案例中也演示了如何同时在 Digital Ocean 上运行一个自己部署的 Supabase 实例。

**长按识别二维码查看原文**

https://docs.digitalocean.com/developer-center/deploy-a-react-app-on-app-platform-with-self-hosted-supabase/

Timothy Mamo

**如何阻止一个 React 组件渲染？** — 答案是返回 “null”。

**长按识别二维码查看原文**

https://www.amitmerchant.com/how-to-stop-a-react-component-from-rendering/

Amit Merchant

**快讯：**

⭐️ Dan Abramov 向我们展示了 **如何用 Next.js 在使用动态路由的同时做一个纯粹的客户端 SPA**。在评论中，有人展示了 **也可以用 Astro 来做这个**。

**长按识别二维码查看原文**

https://gist.github.com/gaearon/9d6b8eddc7f5e647a054d7b333434ef6

Vladimir Angelov 实现了 **7GUIs 在 React 中使用 signals** 来管理状态。

**长按识别二维码查看原文**

https://eugenkiss.github.io/7guis/

😆 你知道 🐦 **为什么 React 官方推特账号还没有被验证吗**？因为 React 没有足够的零花钱……

**长按识别二维码查看原文**

https://twitter.com/reactjs/status/1636510852974280706

## 🛠 代码与工具

**Recharts v2.5：使用 React 和 D3 构建的图表库** — 易于部署的声明式组件，原生 SVG 支持，以及对 D3 的轻量级依赖。提供线图、柱状图、散点图、复合图、饼图和雷达图。这里 **有很多示例**，并且带有代码。

**长按识别二维码查看原文**

https://github.com/recharts/recharts

recharts

**Bright：用于语法高亮的 React 服务器组件** — 可定制，包括所有 VS Code 的语法高亮主题，其中一些在官网上进行了展示。

**长按识别二维码查看原文**

https://bright.codehike.org/

Code Hike

**React ProseMirror：将 ProseMirror 编辑器与 React 集成** — **ProseMirror** 是一个用于构建 Web 富文本编辑器的工具包。

**长按识别二维码查看原文**

https://github.com/nytimes/react-prosemirror

The New York Times

**React Native DateTimePicker v7.0** — 适用于 iOS、Android 和 Windows 的 React Native 日期和时间选择器。v7.0 在 Android 上增加了对 TurboModules 的支持，并支持所谓的 **新架构**。

**长按识别二维码查看原文**

https://github.com/react-native-datetimepicker/datetimepicker

Vojtech Novak et al.

**用于图片的“呼吸半调”动画** — 难以描述，但很有趣。这里是实际效果。

**长按识别二维码查看原文**

https://github.com/ozluy/breathing-halftone

Yusuf Ozlu

**⚡️ 好库推荐：**

- **Downshift v7.6**
    
    ↳ 用于构建可访问的组合框/下拉组件的工具集
    

- **React Table Library v4.1**
    
    ↳ 一款 “几乎无头” 的表格组件
    

- **Solito v3.1**
    
    ↳ 让 React Native 使用 Next.js 风格的路由 API
    

- **Beautiful React Hooks v4.3**
    
    ↳ 许多量身定制的 React Hooks
    

- **markdown-to-jsx v7.2**
    
    ↳ 可定制的 React Markdown 组件
    

- **React Native Testing Library v12.0**
    
    ↳ 提供一份 **迁移指南**。
    

## 🙋🏻‍♀️