# React 中文周刊 #95 - 包含 5000 多个 UI 组件的可视化目录

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507486&idx=1&sn=5d7a8c44c8575e1c9f4bbe2a613b954f&chksm=e92195fcde561cea46fec0e3e3fb9b811f1a103e3ff29b1c087445f3ba3db7a6cc73cc67c80a\#rd  
> 抓取时间: 2026/2/2 23:47:10

---

> 本期看点：本期为大家带来了 “我们如何减少 React 代码库中的 bug” 与 “我是如何用 React 和 Rust 创建一个桌面生产力应用的” 等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：tmkx、syjstc、edison-hm、whatwewant

## 🔥 本周热门

▶  **用 React Native 构建类似 Gmail UI 的禅宗与艺术** — 即使我们看过很多的教学视频，但可以肯定地说，我们从来没有见过这样的：它具有很高的制作水准，全程没有台词，拍摄地点更是在日本的 **兴正寺** 。观看这种视频是一种享受。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=w-M9UFHLAl0

Takuya Matsuyama

**bulletproof-react：可扩展、用于构建可付诸生产的 React 应用程序的架构** — 之前期刊有提过 bulletproof-react，但它最近的更新值得我们再介绍一次。这不是一个样板应用或框架，而是一个带有主观色彩的指南，告诉你如何构建一个大规模的 React 应用（如果你缺乏灵感的话）。

**长按识别二维码查看原文**

https://github.com/alan2207/bulletproof-react

Alan Alickovic

**组件的百科全书：包含 5000 多个 UI 组件的目录** — Storybook 是一个流行的 UI 组件开发工具，它展示了一个超过 5000 个组件的 **可视化目录**（不是所有的都是 React，但大部分是），这些组件来自 Web 的各个角落 —— 你不需要成为 Storybook 的用户就可以使用它，因为它在每个案例中都提供了代码仓库的链接和演示。

**长按识别二维码查看原文**

https://storybook.js.org/blog/component-encyclopedia/

Dominic Nguyen (Storybook)

**快讯**

- 📅 今年十月，**React Brussels** 将在比利时和网上同时举办。
    
    **长按识别二维码查看原文**
    
    https://www.react.brussels/
    

- 📝 **Component Party** 是一种类似于 Rosetta Stone 的工具，用于比较 React、Svelte、Vue、Angular 和类似框架之间的简单代码示例。
    
    **长按识别二维码查看原文**
    
    https://component-party.dev/
    

- 🤑 **Refine** 是一款基于 React 的内部工具开发框架，其背后的公司已经筹集了 100 万美元的种子资金，用于继续开发该项目。
    
    **长按识别二维码查看原文**
    
    https://refine.dev/
    

**“我是如何用 React 和 Rust 创建一个桌面生产力应用的”** — Amine 想要有一种非常轻量级的方式来在其他任务中快速做笔记，并将 React 与基于 Rust 的 Tauri 结合起来实现这一目标。

**长按识别二维码查看原文**

https://betterprogramming.pub/how-i-created-the-focus-app-using-react-and-rust-fd8fd072d1a7?gi=b5f861316743

Amine Ben Hammou

**元素 vs 组件 vs 实例** — 对 React 中的元素、组件和实例的含义进行详细的说明，然后再看它们是如何联系在一起的。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-element-component/

Robin Wieruch

**“我们如何减少 React 代码库中的 bug”** — 对 React 中三种意想不到的代码行为进行彻底的检查，然后通过识别和理解它们的底层模式和反模式来解决这些问题。

**长按识别二维码查看原文**

https://betterprogramming.pub/how-we-reduced-bugs-in-our-react-code-base-9a7a979b4442?gi=f8ddd08ff17b

Darshita Chaturvedi and Shyam Swaroop

## 🛠 代码与工具

**react-sketch-canvas：一款可用于手绘矢量图的组件** — 这是一款功能齐全画布组件，利用 SVG 实现，也直接绘制出 SVG。你可以来先来 **试用** 感受一下，然后决定是否需要在项目中引用它。

**长按识别二维码查看原文**

https://github.com/vinothpandian/react-sketch-canvas

Vinoth Pandian

**React Switch v7.0：一款可拖拽的开关组件** — 它支持自定义样式，支持触摸设备，且具备高度的可访问性。点击 **这里** 查看示例。

**长按识别二维码查看原文**

https://github.com/markusenglund/react-switch

Markus Englund

**react-cmdk：一款可唤出命令面板的 React 组件** — 它可通过自定义实现许多高级功能，只需在页面上按下 CMD/CTRL + K 键即可查看效果。点击 **这里** 查看 GitHub 仓库。另外，它与之前推荐过的 **kbar** 非常相似。

**长按识别二维码查看原文**

https://react-cmdk.com/

Albin Groen

**利用傅里叶级数拟合出手绘线条** — 仓库中包含了一则干净的示例，当然也包含了源码。**点击这里** 查看吧。

**长按识别二维码查看原文**

https://jasonfyw.com/fourier-series/

Jason Wang

**⚡️ 好库推荐：**

**react-timeago** — 该组件可接受任何日期并将它转换成与当前日期的关系，比如“6 天前”，并且它还支持多语言

**react-easy-crop** — 使用操作简易的交互来裁切图片

**rc-image** — 从 Ant Design 场景中抽象出来的图像组件

## 🙋🏻‍♀️