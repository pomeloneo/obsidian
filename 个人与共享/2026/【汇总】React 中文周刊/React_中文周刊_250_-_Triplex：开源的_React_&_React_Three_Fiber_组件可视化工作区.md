# React 中文周刊 #250 - Triplex：开源的 React & React Three Fiber 组件可视化工作区

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544123&idx=1&sn=c02379cb92fc0df16b289d004c8e3642&chksm=e92166d9de56efcf0da8b722a13ea661b5f941fa466ecd5d8f2cf988c67857e9b774c9d55e86\#rd  
> 抓取时间: 2026/2/2 23:41:32

---

> 本期看点：Triplex 商业工具转为开源并推出 VS Code 插件并兼容常规 React DOM 元素,React Compiler v1.0 正式发布,React Native v0.82 首次完全基于新架构构建,Next.js v16 Beta 全面拥抱 Turbopack 并支持 React 19.2 和 React Compiler。

> 编辑：TimLi

🔥 本周热门

**Triplex：全新开源的 React & React Three Fiber 组件可视化工作区** —— Triplex 之前是一款用于在 3D 场景中可视化布局 React 组件的商业工具，现在已经全面开源，并加入了 Poimandres Collective（这个团队还维护着 Three Fiber、Jotai、Zustand 等知名项目）。开源后的 Triplex 功能扩展不少，比如推出了 VS Code 插件 、同时兼容常规的 React DOM 元素与组件。

**长按识别二维码查看原文**

https://triplex.dev/blog/triplex-moves-to-pmndrs

Mike Douges 及 Pmndrs 团队

**React Compiler v1.0** —— React Compiler 终于迎来了 v1.0 版本，被官方认为足够稳定，可以自动分析你的代码并进行优化（会自动帮你做 memoization 缓存）。当然如果需要更细致的性能把控，你还是可以灵活用 `useMemo` 和 `useCallback`。

**长按识别二维码查看原文**

https://react.dev/blog/2025/10/07/react-compiler-1

Tan、Savona、Zhang

**Bun v1.3：全栈 JS 运行时** —— 这个专注性能的 JavaScriptCore 引擎迎来了大升级，不只是纯后端，已经进化为真正的“全栈运行时”：内置支持开发服务器和热更新（兼容 React Fast Refresh），默认隔离式包管理，还能一键脚手架生成 React 项目等功能。对于写 React 的开发者来说，值得关注。

**长按识别二维码查看原文**

https://bun.com/blog/bun-v1.3

The Bun Team

**React Native v0.82：新纪元来了** —— 新版号称“新纪元”，因为首次实现了完全基于 New Architecture 构建。此外，还可以试用更快的新一代 Hermes V1 引擎，不过目前还是实验性 opt-in。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2025/10/08/react-native-0.82

React Native 团队

📄 **五步搞定 React 文件结构·2025 版** Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-folder-structure/

📄 **无需重写：如何让 Expo 走进成熟应用程序** —— 不需要费劲地大规模重写，用 Expo 搭配 React Native 可让你的应用程序逐步现代化升级。Gabriel Donadel（Expo）

**长按识别二维码查看原文**

https://expo.dev/blog/how-to-bring-expo-into-mature-native-apps

📄 **GitHub Copilot CLI 上手指南** Andrea Griffiths

**长按识别二维码查看原文**

https://github.blog/ai-and-ml/github-copilot/github-copilot-cli-how-to-get-started/

📄 **TanStack Router 的 Context 继承机制剖析** Dominik Dorfmeister (TkDodo)

**长按识别二维码查看原文**

https://tkdodo.eu/blog/context-inheritance-in-tan-stack-router

🛠  代码与工具

**React Chrono v3.0：交互式时间轴组件** —— 支持横向、纵向、交替纵向等各种时间线模式，自带键盘无障碍、嵌套时间线、轮播自动播放等功能。文档 也很详细。v3.0 是一次大规模重构，带来了对 React 19 的支持，还可以集成 Google Fonts，以及更多增强。

**长按识别二维码查看原文**

https://react-chrono.prabhumurthy.com/

Prabhu Murthy 及团队

**Next.js v16 Beta 发布** —— 这个热门框架，全面拥抱了 Turbopack（默认用于新项目打包），同时支持 React 19.2 和 React Compiler，新增多项缓存能力。需要注意的是，路由系统有全面重构，建议测试下，不过理论上不需要改动你的代码。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-16-beta

Clark、Lai、Choi、Kasper、Koppers

🖨️ **React-to-Print：灵活控制 React 组件打印** —— 如果你的应用程序有票据、发票之类需要打印，借助这个库你能更好地控制打印体验。这里有详细教程，手把手教你怎么用。

**长按识别二维码查看原文**

https://github.com/MatthewHerbst/react-to-print

Herbst、Nowakowski

🎛️ **React Knob Headless：旋钮控件原始组件** —— 为需要环形（类似音频旋钮）而不是线性滑块的场景打造的无样式、无障碍旋钮原语组件。GitHub 地址在这里。

**长按识别二维码查看原文**

https://react-knob-headless.pages.dev/

Satelllte

📢  其他生态

这里汇总了一些近期社区圈子的有趣信息：

- jsonriver（如上图）是面向流式处理场景的 JSON 解析器，你不需要把整个文档等到下载完，就能一边接收流一边增量解析 JSON，比如用于网络请求或 LLM 场景。它会随着数据流入，逐步产出“越来越完整”的结果，非常适合大文件处理。
    
    **长按识别二维码查看原文**
    
    https://github.com/rictic/jsonriver
    

- 🔒 提醒下，近期 GitHub 针对 npm 的安全加强措施即将生效。如果你有发布 npm 包（尤其是还在用老的 token），要提前关注下风险。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-10-10-strengthening-npm-security-important-changes-to-authentication-and-token-management/
    

- VoidZero 发布了 Vite+（又叫 Viteplus），它是在 Vite 基础上扩展的新版本，内置了 linter、测试、monorepo 任务管理等诸多功能，不过授权协议需要留意。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/announcing-vite-plus
    

- 在 The Birth of Prettier 一文中，Christopher Chedeau（圈内人称 Vjeux）带大家回顾了自己和 James Long 十年前一起创建 Prettier 这款代码格式化工具的故事。Prettier 让 JS 社区真正普及起了基于 AST 的自动格式化流程。
    
    **长按识别二维码查看原文**
    
    https://blog.vjeux.com/2025/javascript/birth-of-prettier.html
    

**版本发布：**

- **React Three Fiber v9.4** —— Three.js 的 React 渲染器再升级。

- **📄 react-native-pdf v7.0** —— React Native 平台上的 PDF 组件。

- **📄 React PDF v10.2** —— 如果你用普通 React，也有好选择！

- **llama.ui v2.38** —— 为 AI Companion 打造的极简前端 UI，可直接本地浏览器运行。