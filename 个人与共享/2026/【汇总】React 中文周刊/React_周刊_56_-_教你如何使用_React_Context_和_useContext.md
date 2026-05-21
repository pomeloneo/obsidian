# React 周刊 #56 - 教你如何使用 React Context 和 useContext

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247492030&idx=1&sn=2b4a93e3bdc99ab87dca353b88fe51be&chksm=e921aa5cde56234ad12d863e112fcc2c41d4152aae709958ce72761ef7965f825fc143067b0b\#rd  
> 抓取时间: 2026/2/2 23:48:34

---

> 本周看点：教你如何使用 React Context 和 useContext、由 React Native for Web 开发的 Twitter 网页、Next.js 应用如何做状态管理等等。
> 
> 电脑阅读，请点击阅读原文或直接访问 https://docschina.org/weekly/react

> 编辑：edison-hm、syjstc、whatwewant

## 🔥 本周热门

**教你如何使用 React Context 和 useContext** — 尽管 React Context 可以不用关心组件在树中的位置，进而简化对全局数据的访问，但是在项目中引入 context 也会相应地增加复杂度。而且，props 传递两到三个层级通常不会引起什么大问题，所以 context 也并不适用于所有场景。

**长按识别二维码查看原文**

https://dmitripavlutin.com/react-context-and-usecontext/

Dmitri Pavlutin

**由 React Native for Web 开发的 Twitter 网页** — 从 Twitter 用 React Native for Web 来开发网页可以看出，Twitter 有着在网页和移动端应用之间共享通用代码库的野心。本文详细解释了 React Native for Web 最终编译出看似凌乱的 HTML 和 CSS 的原因。

**长按识别二维码查看原文**

https://giuseppegurgone.com/twitter-html/

Giuseppe Gurgone

**可视化测试 React Hooks 和组件** — Jest 和 React Testing Library 都是流行的测试库，但作者认为他们缺乏更贴近真实使用场景的可视化测试能力。本文中作者使用 Storybook 来填补这个测试难点的“空缺”。

**长按识别二维码查看原文**

https://marmelab.com/blog/2021/08/31/testing-react.html

François Zaninotto

**Data Table Component 7.0：灵活的 React 数据表格库** — 该库功能丰富，易于设置且提供了大量的文档。查看官网的 “kitchen sink” 示例了解更多。这里是它的 GitHub 仓库。

**长按识别二维码查看原文**

https://react-data-table-component.netlify.app/?path=/story/getting-started-intro–page

John Betancur

**如何开发一款安卓新闻类 app** — 本文介绍了如何使用 React Native 结合 NativeBase、Expo、React Navigation 和 News API 实现一款功能齐全的新闻类 app。

**长按识别二维码查看原文**

https://t.co/tTRQvWElGY?amp=1

Nishant Kumar

**Next.js 应用如何做状态管理** — 在 Next.js 应用中管理状态是件棘手的事，本文介绍了一些模式来规避常见场景中的复杂性以及 “provider 地狱”。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/08/state-management-nextjs/

Átila Fassina

**让你的 React Native 应用为 iOS 15 和 Android 12 做好准备** — 今年晚些时候会发布新的移动端操作系统版本，本文列举出一些可提前做好的准备，以避免在这些新版本成为主流后可能会出现的降级处理。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2021/09/01/preparing-your-app-for-iOS-15-and-android-12

Samuel Susla

**react-window 实现大数据列表的虚拟滚动**

**长按识别二维码查看原文**

https://blog.openreplay.com/virtualizing-large-data-lists-with-react-window

Ikeh Akinyemi

**将大型 CRA 项目从 JavaScript 迁移至 TypeScript**

**长按识别二维码查看原文**

https://chrisfrew.in/blog/converting-a-large-project-from-javascript-to-typescript/

Chris Frewin

**用 React 实现一个自定义 Button 组件**

**长按识别二维码查看原文**

https://sohnya.hashnode.dev/how-to-build-custom-component-button-in-react

Sonia Uduma

**如何使用 AWS Amplify、Amazon 和 React 开发一款 Serverless 聊天机器人** — 阅读本文无需数据科学或 NLP 知识。

**长按识别二维码查看原文**

https://sandro.volpee.de/how-to-develop-a-serverless-chatbot-with-aws-amplify-amazon-lex-and-react

Sandro Volpicella

**在 React 应用中添加 CSV 和 JSON 文件下载功能**

**长按识别二维码查看原文**

https://theroadtoenterprise.com/blog/how-to-download-csv-and-json-files-in-react

Thomas Findlay

## 🛠 代码与工具

**react-web-editor：一款所见即所得的编辑器** — 该库支持调整元素大小和元素拖拽，还支持富文本编辑。

**长按识别二维码查看原文**

https://www.npmjs.com/package/react-web-editor

CHEWCHEWW

**Colorwaver：一款根据场景自动生成调色板的移动端应用** — 该应用可以为你移动设备识别到的场景自动生成相应的调色板，就像 demo 展现的那样。而且如果你想学习带有后端代码的 React Native 应用仓库，也可以看看该库的源码。

**长按识别二维码查看原文**

https://github.com/mrousavy/Colorwaver

Marc Rousavy

**react-render-tracker** — 这款工具用于监测无意间触发重新渲染和卸载引起的性能问题。

**长按识别二维码查看原文**

https://github.com/lahmatiy/react-render-tracker

Roman Dvornov

**react-recipes** — 作为 beautiful-react-hooks 的补充，我们在 254 期 中介绍过 beautiful-react-hooks。这是另一个 hook 集合，有了它你就可以不用自己写 hook 了。

**长按识别二维码查看原文**

https://github.com/craig1123/react-recipes

Craig Walker

**use-cannon** — 是什么让动画看起来“真实”？很重要的一点是要结合现实世界的物理学，而这款由 React Three Fiber 提供的 hook 库也同样做到了（和物理学的结合），ping pong 的演示很好地说明了这点。

**长按识别二维码查看原文**

https://github.com/pmndrs/use-cannon

Poimandres

**reactant** — 你是否曾经希望 React 更向 Angular 靠拢？这是个有争议的想法，但这个 React 框架的灵感正是来自这样的想法。

**长按识别二维码查看原文**

https://github.com/unadlib/reactant

Michael Lin

**⚡️ 好库推荐：**

- react-monacoeditor — Monaco 是一款 Visual Studio Code 中使用的代码编辑器。在这里，它以 React 组件的形式呈现

- react-native-iap — 在 Android 或 iOS 中实现基本的应用内购买功能

- use-resize-observer — 如 demo 所示，该库可以检测元素尺寸的变化并返回相关数据

- chartbrew — 直接根据连接的数据库创建出漂亮的图表

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。