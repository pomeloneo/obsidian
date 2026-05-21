# React Status 中文周刊 #44 - React 18 开发计划

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247489638&idx=1&sn=659059fef9c1d64d0fa3fd4eb7e8c751&chksm=e9225384de55da9228f128e1b75ff5e40401229309e37a3c494277bc06007c498f91451a7897\#rd  
> 抓取时间: 2026/2/2 23:49:03

---

编辑 | whatwewant

syjstc

edison-hm

> 本周看点：React 18 发布计划、为什么我的 React 应用很慢、React SEO 策略和最佳实践等等。除此之外，还附有很多最佳实践，具体内容小伙伴们看文章吧~
> 
> 端午已至，祝大家端午安康~
> 
> 电脑阅读，请点击阅读原文或直接访问 https://docschina.org/weekly/react

## 🔥 本周热门

**[React 18 发布计划](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247489226&idx=1&sn=792bce9cfaf6161ed792429fee591214&chksm=e9225d28de55d43e4128275ff761c77d2e99acfc0e0f1b656e2bada24151d5b0690fc15e7103&scene=21#wechat_redirect)** — React 团队编写了一篇文章，介绍了即将到来的 React 18 中所有令人兴奋的事情。不过这个版本至少在几个月后才会最终稳定，所以不必惊慌。下面列举了几条关键的内容：

- 首先，这些更新，对于大多数用户来说可以忽略。而库的开发者是需要关注它们的。如果你想了解更多，可以看看 Cassidy Williams 写的简单介绍。

- React 18 的第一个 alpha 版本现在可以试用了。但是不要着急将它用在生产环境，因为它还不稳定。

- 新的基于 Suspense 的服务端渲染架构。

- 通过自动批处理减少非必要的渲染。

- Transitions API，即使在复杂的渲染场景下，也能保持应用的流畅性。

- 启动了 React 18 工作组，被邀请的社区成员能够直接参与 React 团队的公开讨论。

**长按识别二维码查看原文**

https://zh-hans.reactjs.org/blog/2021/06/08/the-plan-for-react-18.html

The React Core Team

**▶  为什么我的 React 应用很慢？** — Smashing Magazine 播客的最新一集涵盖了 React 性能，Drew McLellan 与 JavaScript 性能专家 Ivan Akulov 讨论了导致 React 应用变慢的原因以及可以采取的措施。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/06/smashing-podcast-episode-38/

Smashing Magazine Podcast podcast

**Reactron 介绍** — Reactron 是一个 React 组件可视化和测试工具，它推荐开发者试用 TDD。

**长按识别二维码查看原文**

https://t.co/CfGjsxLnig?amp=1

Nathaniel Armstrong

**如何创建具有可调整大小列的 React 表格组件** — 文章分为两部分，第一部分介绍如何使用 React 表格库创建表格组件，第二部分 则介绍调整大小功能。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-table-component

Robin Wieruch

**`React.useMemo()` 最佳实践** — 通过记忆来提高组件的性能，避免冗余、耗时的函数调用。

**长按识别二维码查看原文**

https://dmitripavlutin.com/react-usememo-hook/

Dmitri Pavlutin

## 📘 教程与趣事

**React 状态模式的现代指南** — 曾经有一段时间，Redux 几乎是公认的 React 状态管理最佳方案，但现在已经有了很多其他选择，它们大多基于 Hooks，本文介绍了其中几个。

**长按识别二维码查看原文**

https://blog.logrocket.com/modern-guide-react-state-patterns/

Fredrik Strand Oseberg

**为什么 React Hooks 不能使用条件语句** — 如果你也曾遇到过 `React Hook "useState" is called conditionally` 这样的错误，那么本文非常适合你，它将告诉你为什么。

**长按识别二维码查看原文**

https://blog.atomrc.dev/p/why-you-cannot-condition-react-hooks/

Thomas Belin

**如何创建跳转文本输入标签** — 本文是一篇非常棒的教程，教你如何创建跳转文本输入标签。如果你还不知道“跳转文本输入标签是什么，看看这个 CodePen 示例就知道了。

**长按识别二维码查看原文**

https://t.co/c3qwh1fTeH?amp=1

Mikael Ainalem

**使用 ClojureScript 编写 JavaScript 和 React 的教程** — ClojureScript 本质上是将 Clojure (Lisp 方言和函数式语言)编译成 JavaScript 的编译器，本身支持函数式编程。

**长按识别二维码查看原文**

https://jerue.org/blog/lessons-on-writing-javascript-and-react-from-clojurescript/

Ryan Jerue

**React SEO 策略和最佳实践** — 什么是 SEO？简单的解释就是，你的应用是否能从所有搜索结果中脱颖而出，取决于它是否被 Googlebot 和其他网络爬虫有效地索引。本文解释了这些爬虫是如何为你的应用编制索引的，然后提供了针对性的优化方案。

**长按识别二维码查看原文**

https://www.toptal.com/react/react-seo-best-practices

Vineet Markan

**在学习 React Native 之前你应该学习什么** — 如果你的目标是开发一个跨平台的移动应用程序，那么直接使用 React Native 开发应用是不错的选择。但是，你可能要考虑先学习一些前置技术。

**长按识别二维码查看原文**

https://blog.logrocket.com/what-you-should-learn-before-learning-react-native/

Vijit Ail

**如何使用 Gatsby 创建博客** — 想要找一个简单并且专注博客的开发框架？那么，请认准 Gatsby。

**长按识别二维码查看原文**

https://t.co/zJo5GYw72g?amp=1

Daniele Fontani

**如何在 Next.js 中以编程式方式动态更改路由**

**长按识别二维码查看原文**

https://flaviocopes.com/nextjs-programmatically-change-route/

Flavio Copes

## 🛠 代码与工具

**boring-avatars：生成自定义头像的 React 组件** — 从通用渐变到类似人脸的创作，这个库 (GitHub) 可以从任何用户名和调色板生成自定义的、基于 SVG 的圆形头像。

**长按识别二维码查看原文**

https://boringavatars.com/

Boring Designers

**十一个让你的 React 应用更上一层楼的库** — 虽然这些类型的文章总是反映作者的特定偏好，但你仍然可以在这个集合中找到一些新的和有价值的东西。

**长按识别二维码查看原文**

https://t.co/aJ3U8y34oU?amp=1

Jeffrey Chiu

**react-native-multithreading：多线程非阻塞方案** — 虽然 JavaScript Interface (JSI) 创造了新的机会，但它也许会让一些长时间运行的调用阻塞到主线程。

**长按识别二维码查看原文**

https://github.com/mrousavy/react-native-multithreading

Marc Rousavy

**twilio-video-app-react：多人视频应用** — 新冠病毒引发的视频会议爆炸式增长，这可能会促使你也想开发一个有竞争力的视频会议产品。

**长按识别二维码查看原文**

https://github.com/twilio/twilio-video-app-react

Twilio

**Lepton：基于 Github Gists 的代码片段管理工具** — 快速上手，你只要正常使用 GitHub Gists 就可以了，没有额外学习成本。也许可以用在你的项目中。

**长按识别二维码查看原文**

https://github.com/hackjutsu/Lepton

CosmoX

**sweetalert2-react-content：SweetAlert2 的 React 组件** — 符合 WAI-ARIA 标准的 JavaScript 弹出通知组件，同时它也可以提供基于 React 的复杂内容。

**长按识别二维码查看原文**

https://github.com/sweetalert2/sweetalert2-react-content

SweetAlert2

**⚡️ 好库推荐：**

你可能会错过的有趣项目：

- react-nice-avatar — 简单、可自定义的 React 头像组件

- keen-slider — 灵活而强大的触摸滑块组件，兼容所有常见浏览器

- React Easy Emoji — 轻量级的适合 React 的 emoji 工具，完整支持 Twemoji

- react-svg-radar-chart — 以流行的 2D 图表显示多变量数据

- react-spring-lightbox — 支持手势操作的灵活图片预览库

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。