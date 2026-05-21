# React 中文周刊 #256 - React 出现严重安全漏洞！赶紧自查升级。

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544958&idx=1&sn=620e055287a7926944070dddf736ef59&chksm=e9217b9cde56f28a8a3e545f09a35e620edef69a5c5884d48e25dc599edbc0526a2ac0ad6864\#rd  
> 抓取时间: 2026/2/2 23:41:18

---

> 本期看点：React 出现严重安全漏洞，漏洞涉及 react-server-dom 的 v19.0、19.1.0、19.1.1 和 19.2.0，React 团队已发布对应修复版本，Vite v8 测试版发布并首次引入 Rolldown 内核，React Router 对 React Server Components 的实验性支持，Anthropic 收购 Bun。

> 编辑：TimLi

🔥 本周热门

⚠️ **React Server Components 出现严重安全漏洞** —— React 团队刚刚发布了重要安全通知，所有支持 RSC（React Server Components）的应用程序都要留意了！不管你有没有用到 RSC，只要升级到 `react-server-dom-webpack`、`react-server-dom-parcel`、`react-server-dom-turbopack` 的 v19.0、19.1.0、19.1.1 和 19.2.0，都会存在远程代码执行的风险，必须尽快升级修复。不过，如果你用的 React 不涉及服务端，其实就不用担心这个漏洞。

**长按识别二维码查看原文**

https://react.dev/blog/2025/12/03/critical-security-vulnerability-in-react-server-components

The React Team

💡 React v19.0.1、v19.1.2 和 v19.2.1 都是为了修复此次漏洞刚刚发布的新版本。

**长按识别二维码查看原文**

https://github.com/facebook/react/releases/tag/v19.0.1

**Vite v8 测试版：首次引入 Rolldown 内核** —— Vite 8 首个 Beta 版本发布，底层用上了 Rolldown，让生产构建速度更快、插件系统更强大，为未来扩展性打下基础。

**长按识别二维码查看原文**

https://vite.dev/blog/announcing-vite8-beta

VoidZero Inc.

**React Router 对 React Server Components 的新尝试** —— **你知道 React Router 现在也在实验 RSC 的支持了吗？** 虽然还在实验阶段，但已经很接近正式上线，看下来他们对于 RSC 的探索做得还是很到位，值得大家重点关注。

**长按识别二维码查看原文**

https://www.epicreact.dev/react-routers-take-on-react-server-components-4bj7q

Kent C. Dodds

📄 **TanStack 的两年开源全职之路** —— Tanner Linsley 这篇文章讲述了 TanStack 这套开源库家族近几年如何不断壮大的故事，现在可以说是社区里最成功的一批开源产品了。

**长按识别二维码查看原文**

https://tanstack.com/blog/tanstack-2-years

📺 **React Native 新架构：不是“新”，而是变成标准姿势** —— React Native 核心团队成员聊聊架构升级带来的变化，“the new architecture” 已经成了大家都在用的“老架构”了。

**长按识别二维码查看原文**

https://www.callstack.com/podcasts/its-not-new-how-the-architecture-unlocks-react-natives-future

📄 **Next.js 服务器遭攻击只需 0.0001 美分？！** —— 这篇文章介绍了一个攻击方式，不过目前漏洞已经被官方修复，只要把 Next.js 升级到 15.5.5 或 16.0 以上就安全了。Alex Browne

**长按识别二维码查看原文**

https://www.harmonyintelligence.com/taking-down-next-js-servers

📄 **Next.js 16：认证和权限的大升级** Will Johnson (Auth0)

**长按识别二维码查看原文**

https://auth0.com/blog/whats-new-nextjs-16/

📄 **Designing Design Systems** Dominik Dorfmeister

**长按识别二维码查看原文**

https://www.reddit.com/r/reactjs/comments/1pbh3c0/designing_design_systems/

🛠  代码与工具

🔒 **Better Auth：一站式认证框架** —— Better Auth 集成了邮箱/密码登录、OAuth、社交登录、账号与会话管理、2FA 等一条龙认证和授权功能。最新版 v1.4 新增了无状态/无数据库的会话管理，让你开发认证系统变得更轻松。

**长按识别二维码查看原文**

https://www.better-auth.com/

Better Auth

**react-native-quick-crypto v1.0：React Native 版 Node** `**crypto**` —— 这个库用 C/C++ JSI 实现了 Node Crypto 的核心功能，在 React Native 上也能跑高性能加密了。

**长按识别二维码查看原文**

https://github.com/margelo/react-native-quick-crypto

Margelo GmbH

📸 **React Web Camera：网页多连拍的相机组件** —— 支持浏览器端多次连拍，无需反复打开摄像头，还能自定义样式灵活嵌入应用程序。这里有个 demo。

**长按识别二维码查看原文**

https://github.com/shivantra/react-web-camera

shivantra

**Docs：基于 React 的协作写作环境** —— 法国和德国政府联合打造的协作文档、Wiki 与笔记应用程序。底层用了 React、Django 和 BlockNote，功能非常强大。GitHub 地址在这里。

**长按识别二维码查看原文**

https://docs.numerique.gouv.fr/home/

The Government of France

🗓️ **FullCalendar：完整体量的 JavaScript 日历控件** —— 想要 Google Calendar 一样的体验，选它准没错。支持和 React、Vue、Angular 无缝集成，纯 JS 也能用。基础版本 MIT 协议，收费版还多了额外功能。

**长按识别二维码查看原文**

https://fullcalendar.io/

Adam Shaw

**Custom React Directives（也叫** `**use nemo**`**）** —— 各种自定义指令正在圈子里越玩越花，不如你也亲自试一把，造个属于你自己的指令吧！😅

**长按识别二维码查看原文**

https://github.com/Ademking/use-nemo

Adem Kouki

📢  其他生态圈

一些行业大新闻，也值得一看：

- 以 **Claude** 大模型出名的 Anthropic，收购了 Bun 背后的公司，Bun 是一款服务端 JavaScript 运行时，作者 Jarred Sumner 也讲了下收购背后的小故事，并强调 Bun 会像以前一样保持开放。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-joins-anthropic
    

- Electron 项目最近进入了 “静默月”，给维护团队放个假，等到 1 月份再全力冲刺，同时也回顾了 2025 年都干了些什么。
    
    **长按识别二维码查看原文**
    
    https://www.electronjs.org/blog/dec-quiet-period-25
    

- Vercel 已经支持 在 builds 和 functions 上用 Node 24 LTS 了。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-24-lts-is-now-generally-available-for-builds-and-functions
    

- DepX 的徽章生成器 能帮你生成 README 或项目主页专用 Badge，显示你的 npm 包依赖数量（多还是少，一目了然！）。
    
    **长按识别二维码查看原文**
    
    https://depx.co/badge
    

**版本发布：**

- 📊 **React Spectrum Charts v1.22.0** —— Adobe 出品，声明式图表库，专注可访问性。官网预览 效果很棒。

- **React Markdown Editor v4.0.10** —— 支持实时预览和语法高亮的 Markdown 编辑器组件。（Demo）

- **markdown-to-jsx v9.3.0** —— 灵活可定制的 Markdown 转 JSX 工具链。

- **React Uploady v1.13** —— 专注文件上传的组件与 Hook 集合。

- **Berry v51.0** —— 基于 Material UI 的 React 管理后台模板。

- **Reactylon v3.5** —— Babylon.js 加持的 React XR 框架。

- **React Three Fiber v9.4.2** —— Three.js 的 React 渲染器。

- **Prettier v3.7** —— 著名的代码格式化工具又升级啦。

- **Preact v10.28.0** —— 小体积、高性能的 React 替代方案。