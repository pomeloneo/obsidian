# React Status 中文周刊 #19 - React Hook发布两周年回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247485856&idx=1&sn=ddd7479834f797b2176d40fe3005a616&chksm=e9224242de55cb5427e7e017e2f4dfd73d3a7bcd138423bba7c7c10e82979b3fcbd81f6b4cec\#rd  
> 抓取时间: 2026/2/2 23:49:54

---

> React Hook 已发布两年之久，让我们跟随推荐文章一起了解下 Hook 的前世今生。除 React 相关外，还有一个框架推荐，近来关于 Tailwind 和 CSS-in-JS 的话题不断，与其纠结用哪个，不如全都要？
> 
> 应各位大佬要求，二维码下添加了链接，但**阅读原文**更佳哦~
> 
> **电脑阅读，请阅读原文。**

## 🔥 本周热门

**React Hook 发布两周年回顾** — 我们从 2018 年年末的第 112 期开始，引入了 Hook，此后 Hook 便势不可挡。此文介绍了 Hook 的优缺点，以及 Hook 对 React 及其他框架带来的影响（尤其是 Vue 和 Svelte）。

原文链接：https://dev.to/ryansolid/the-react-hooks-announcement-in-retrospect-2-years-later-18lm

Ryan Carniato

**BBC 是如何将 3100 万 UV 的站点迁移为 React 同构应用，并提高页面性能的？** — 在第 213 期中，我们介绍了 Simorgh：BBC 也使用了 React？尽管此文并不是它的续篇，但本文也就 BBC 的发展前景及其使用 React 提高效率进行了深入研究。

原文链接：https://medium.com/bbc-design-engineering/bbc-world-service-web-performance-26b08f7abfcc

Chris Hinds (BBC)

**`useEffect` vs `useLayoutEffect`** — 根据作者所说，99% 的情况都会使用 `useEffect` 而不是 `useLayoutEffect`。但是，有些情况下使用 `useLayoutEffect` 会更好，比如在 DOM 发生突变的情况下，避免操作 DOM 时发生抖动。

原文链接：https://kentcdodds.com/blog/useeffect-vs-uselayouteffect

Kent C. Dodds

**React Aria：使用 React Hook 编写的 UI 组件库，支持无障碍访问** — Adobe 遵循 WAI-ARIA 逐步编写出来的组件库，以确保为**所有**用户都提供最佳的 UI 体验。

原文链接：https://react-spectrum.adobe.com/react-aria/index.html

Adobe

## 📘 教程与趣事

**▶  Zaid Ajaj：在 F# 中构建 React 应用** — 近日，在 .NET Conf 2020 上，Zaid Ajaj 介绍了一种拓宽开发视野的方式，那就是使用函数式编程语言 F# 和 Fable 构建 React 应用。

原文链接：https://www.youtube.com/watch?v=a6Ct3CM_lj4

dotNET

**适用于 Next.js 夜间模式的完美解决方案** — 上期我们介绍了使用夜间模式（只针对 Gastsby 用户），本期将介绍另外一种，标题中的“完美”意味着整个应用中，没有一点日间模式的元素混入。

原文链接：https://sreetamdas.com/blog/the-perfect-dark-mode

Sreetam Das

**常见的 React 面试题以及专业回答** — 年终将近，如果你决定要去面试，这篇文章对你来说很值得一看。当然，我们希望你能深入理解它们，而并非背诵答案。

原文链接：https://dev.to/scrimba/react-interview-questions-to-expect-in-2021-with-answers-dfl

Alex Booker

**使用 React Hooks 从 UI 中解耦数据** — 学习如何编写一个函数式组件，借助 Fetch API，根据数据获取延迟和返回数据渲染组件。

原文链接：https://medium.com/javascript-in-plain-english/decouple-data-from-ui-with-react-hooks-6f7fe968c3e3

Suhan Wijaya

**比较 Next.js 中的样式书写方式** — 尽管 Next.js 提供了用于全局和组件级别的样式书写方式，但是这显然不够，本文调研了 7 个样式方案，并举例如何使用它们。

原文链接：https://www.smashingmagazine.com/2020/09/comparison-styling-methods-next-js/

Adebiyi Adedotun Lukman

**React Router v5 的过渡动画**

原文链接：https://ui.dev/react-router-v5-animated-transitions/

Tyler McGinnis

## 🛠 代码与工具

**Reapop 3.0：简单且可自定义的通知组件** — 它是一个非常优秀的通知组件，同时提供了交互友好的 Demo。

仓库地址：https://github.com/LouisBarranqueiro/reapop

Louis Barranqueiro

**React Awesome Reveal：使用 Intersection Observer API 写动画** — 这是一个很棒的库，你可以像使用其他库一样使用它，或者也可以当作是深入理解 Intersection Observer API 的工具。查看 Demo 了解更多。

仓库地址：https://github.com/dennismorello/react-awesome-reveal

Dennis Morello

**React-Tensorflow：用于 Google 的机器学习平台 Tensorflow 的 React Hooks** — 现在，你终于可以将 Google 开发的 Tensorflow 机器学习平台集成到你的 React 应用中了。

仓库地址：https://github.com/joshuaellis/react-tensorflow

Josh Ellis

**8 个具有 Native 功能的 React Native 库** — 使用这 8 个库与 UI 进行了无缝集成，充分利用了硬件的功能，其中每个库都有详细介绍，以帮助你快速入门。

原文链接：https://blog.bitsrc.io/react-native-libraries-for-native-features-31795a2917e6

Shanika Wickramasinghe

**Twin：使用 CSS-in-JS 的 Tailwind** — 特大喜讯：有了这个库，你将不用再纠结 Tailwind 和 CSS-in-JS 二选一的问题。

仓库地址：https://github.com/ben-rogerson/twin.macro

Ben Rogerson

**next-api-middleware：用于组合 Next.js API 中间件** — 与其将所有代码写在 API 路由的处理函数中，为什么不试试将它们通过中间件的方式解耦你的逻辑？

仓库地址：https://github.com/htunnicliff/next-api-middleware

Hunter Tunnicliff

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。