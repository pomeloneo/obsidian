# React 中文周刊 #122 - 恢复更新

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514404&idx=1&sn=c8e5d3198f8c7e1359eaf857bfe8d4b6&chksm=e921f2c6de567bd03d3ddeaf9f2281de998f4d097d26c5c6dc71367281a7d6752090c5b17ef6\#rd  
> 抓取时间: 2026/2/2 23:46:07

---

> 本期看点：Next.js v13.1、Storybook v7.0 beta 发布；使用 ChatGPT 作为 Reducer；以及一系列库的更新

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**React Wrap Balancer：一款优化标题折行效果的组件** — _React Wrap Balancer_ 是一个通过避免单行展示的单词（有时被称为**“孤行”**）来改善标题呈现效果的组件。**GitHub 仓库**。

**长按识别二维码查看原文**

https://react-wrap-balancer.vercel.app/

Shu Ding

**Storybook v7.0 进入 Beta 阶段** — 这是近两年来这个流行的前端 UI 开发工具的第一个大版本更新（这里会有 Breaking Change）。有很多新功能，包括性能改进、交互测试等等。在此查看 **完整的更改日志**。您现在可以通过 **迁移指南** 尝试 Beta 版。

**长按识别二维码查看原文**

https://storybook.js.org/blog/7-0-beta

Storybook

**在 React Native 中对 TypeScript 进行头等支持** — 随着新发布的 v0.71，你会得到一个新的“默认是 TypeScript (TS)”的应用程序模板 —— TS 声明随基本包一起发布，文档现在也是 TypeScript 优先的（当然，Flow 或常规 JavaScript 仍然是可以使用的）。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2023/01/03/typescript-first

Nick Gerleman (React Native Team)

**Shopify 将其最大的手机应用移植到 React Native 的故事** — Shopify 已将 React Native 视为“Shopify 移动设备的未来”。作为其中的一部分，它一直在迁移其 300 多个屏幕的 Shopify Mobile 应用程序，以下是这项艰巨任务的进展情况。

**长按识别二维码查看原文**

https://shopify.engineering/migrating-our-largest-mobile-app-to-react-native

Shopify

**快讯**

- **Next.js v13.1** 在圣诞节前发布，并进行了一些小的改进。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/next-13-1
    

- 在 Reddit 上，有一个关于 **为什么人们喜欢使用 Next.js** 的讨论。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/reactjs/comments/zprham/why_do_people_like_using_nextjs/
    

- ⭐️ Next.js 刚刚在 GitHub 中 **超过**了 _Create React App_ 的 Star 数，如果你喜欢这种受欢迎程度的测量方式。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/i/web/status/1610165503468658689
    

🤖 **将 ChatGPT 作为一个通用的 Redux Reducer？** — OpenAI 的 **ChatGPT** 最近受到了**很多**关注，所以有另一个新颖的应用程序也就不足为奇了。

**长按识别二维码查看原文**

https://spindas.dreamwidth.org/4207.html

Michael Smith

**▶  3 个导致 App 崩溃的 React 错误** — 一位名为 Jack Herrington 的 React YouTuber 讲解了三个编写 React 时会犯的错误（以及如何解决它们）。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=QuLfCUh-iwI

Jack Herrington

**在 TypeScript 中像专家一样处理错误** — _“学习我用来处理错误和编写更简洁代码的设计模式。”_

**长按识别二维码查看原文**

https://engineering.udacity.com/handling-errors-like-a-pro-in-typescript-d7a314ad4991?gi=c2ed84ad0ecd

Kolby Sisk

**如何用 React 创建一个圣诞音乐小游戏** — 不错的高水平文章。

**长按识别二维码查看原文**

https://www.lloydatkinson.net/projects/2022/christmas-project-2022-music-quiz/

Lloyd Atkinson

**使用 React、Node 和 EmailJS 创建一个日程安排应用程序**

**长按识别二维码查看原文**

https://dev.to/novu/creating-a-scheduling-app-i-wish-somebody-showed-me-this-technique-when-i-first-started-coding-2icd

Nevo David

## 🛠 代码与工具

**RAQB v6.0：React 应用的用户友好型“查询生成器”** — 特别是过滤器式查询。**在线示例**

**长按识别二维码查看原文**

https://github.com/ukrbublik/react-awesome-query-builder

Denis Oblogin

**Recharts：基于 D3 的可组合 React 图表** — 有 **大量示例** 可供查看。包含折线图、面积图、条形图、组合图、散点图、雷达图和饼图，所有这些都采用极简、简洁的风格。

**长按识别二维码查看原文**

https://recharts.org/en-US/

Recharts Group

**Schedulely：基于 CSS 网格的 React 日历控件** — 仍处于早期开发阶段，但它具有体积小、可扩展性和响应性强的特点，并且开箱即用。**GitHub  仓库**

**长按识别二维码查看原文**

https://bruceharrison1984.github.io/Schedulely/

Bruce Harrison

🤡 **uselessHooks：一组无用的 React Hooks** — 显然这些会 “给你的同事留下深刻印象” —— 我们不太确定…

**长按识别二维码查看原文**

https://github.com/btahir/uselesshooks

Bilal

**⚡️ 好库推荐：**

- **Redwood v3.8**↳ 基于 React + GraphQL 的全栈框架

- **Downshift v7.1**↳ 用于构建灵活的、符合 WAI-ARIA 标准的自动完成或下拉控件的基础库

- 🎬 **Scene.js v1.9**↳ 基于 JS + CSS 的时间轴动画库

- **Linkify v4.1**↳ 查找文本中的 URL 并转换为链接

- **React Tracking v9.3**↳ 基于 React 的声明式用户行为采集框架

- **React Simple Keyboard v3.5**↳ 可定制的虚拟键盘 **(查看 Demo)**

- **PCUI v3.0** – PlayCanvas 出品的 UI 组件库

- **React Arborist v2.2** – 树形结构组件

- **Mantine v5.10** – 一款受欢迎的 React 组件库

- **ka-table v7.7** – React 表格组件

## 🎁 奖励篇

**Component Party：框架的罗塞塔石碑?** — 通过涵盖各种任务的简单代码片段，对不同框架（React、Vue、Svelte、Angular、Ember 等）进行比较。

**长按识别二维码查看原文**

https://component-party.dev/

Mathieu Schimmerling

## 🙋🏻‍♀️