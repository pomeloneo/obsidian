# React 中文周刊 #246 - Cloudflare 复盘服务宕机：useEffect 使用不当

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543702&idx=1&sn=5191d6fb29d8ff345c96d63ea90a71c3&chksm=e9216074de56e962cac1b26e91574f24b40bc4ef926f7b45d95507af52568fbe300aa89c2566\#rd  
> 抓取时间: 2026/2/2 23:41:41

---

> 本期看点：Cloudflare 控制面板因 useEffect 使用不当导致服务宕机。各框架对 React Server Components 的支持情况。React 已成为默认选择——这正在扼杀前端创新。Expo SDK 54 发布：支持 IOS 26 和 Liquid Glass。

> 编辑：TimLi

**Cloudflare 控制面板故障源于** `**useEffect**` **使用不当** —— 这个 bug 并非由 React 本身引起，但很少见到因为错误使用 React 特性而导致服务被大量不必要的请求淹没并最终宕机。这提醒我们，这种事情可能发生在任何人身上。

**长按识别二维码查看原文**

https://blog.cloudflare.com/deep-dive-into-cloudflares-sept-12-dashboard-and-api-outage/

Lianza 和 Madruga（Cloudflare）

**如何控制** `**package.json**` **的规模** —— 当看到 Val Town 的 React 应用程序中有一个 863 MB 的 `node_modules` 文件夹时，Tom 开始思考”依赖卫生”以及如何控制规模。文章提供了一些实用的建议和工具推荐。

**长按识别二维码查看原文**

https://blog.val.town/gardening-dependencies

Tom MacWright

**各框架对 React Server Components 的支持情况** —— 对比了 Next.js、Vite、Waku、Forket、Parcel、React Router 和 RedwoodSDK 在主要 RSC 相关功能方面的支持情况。文章还提供了用于测试每个框架的代码，这些代码本身就是很好的参考资料。

**长按识别二维码查看原文**

https://rsc.krasimirtsonev.com/

Krasimir Tsonev

**“React 已成为默认选择——这正在扼杀前端创新”** —— 这篇观点鲜明的文章本周引发了广泛讨论，它指出了”以 React 为默认选择”的思维方式带来的弊端和惯性。我们还以为大家都在说 React 发展太快呢？😅

**长按识别二维码查看原文**

https://www.lorenstew.art/blog/react-won-by-default

Loren Stewart

**📄 使用 React 和 MooseStack 构建基于 ClickHouse 的 API** —— MooseStack 是一个用于构建实时分析后端的框架。Fiveonefour 和 ClickHouse

**长按识别二维码查看原文**

https://clickhouse.com/blog/clickhouse-powered-apis-in-react-app-moosestack

**📄 在 Expo 和 React Native 中创建”当前位置”地图** Louie Berwanger

**长按识别二维码查看原文**

https://spin.atomicobject.com/current-location-expo-react-native/

**📄 2025 年的 Redux：复杂 React 项目的可靠选择** Stef van Wijchen

**长按识别二维码查看原文**

https://stefvanwijchen.com/react-and-redux-in-2025/

**🔊 Discord 的 React Native 之旅，对话 Chas Jhin** React Native Radio 播客

**长按识别二维码查看原文**

https://infinite.red/react-native-radio/rnr-343-discords-journey-to-react-native-with-chas-jhin

**快讯：**

- `<Activity />` 现已在 React 的 Canary 发布渠道中提供。你可以在这里了解更多关于这个特性的信息。我们预计下一个版本的 Next.js 也会支持这个特性。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2025/04/23/react-labs-view-transitions-activity-and-more\#activity
    

- pnpm 项目发布了一篇关于缓解供应链攻击的文章，并发布了 pnpm 10.16，新增了 `minimumReleaseAge` 设置，可以防止安装过于新的包。
    
    **长按识别二维码查看原文**
    
    https://pnpm.io/supply-chain-security
    

- Kent C. Dodds 一年前发布的 React 19 速查表至今仍然实用且相关。
    
    **长按识别二维码查看原文**
    
    https://www.epicreact.dev/react-19-cheatsheet
    

- 如果你是 Vercel 用户，你可能已经注意到构建速度提升了最多 30%。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/builds-now-start-up-to-30-faster
    

🛠 代码与工具

**Expo SDK 54 发布：React Native 开发者的重大更新** —— Expo 框架在 React Native 领域继续快速发展，新版本带来了预编译的 React Native iOS 构建（大幅缩短构建时间）、iOS 26 和 Liquid Glass 支持，并使用了 React Native 0.81 和 React 19.1。新的 Expo File System 也已经稳定。

**长按识别二维码查看原文**

https://expo.dev/changelog/sdk-54

Hughes 和 Vatne（Expo）

📺 Simon Grimm 制作了一个视频，详细介绍了 Expo 54 的所有重要变化以及他为什么对此感到兴奋。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=oWVie6GVI-I

**Conform v1.10：类型安全的表单验证库** —— 让你可以控制从客户端到服务器的表单提交生命周期，并通过 `useForm()` hook 暴露表单状态。v1.10 改进了与 Valibot 的集成以及未来的 `useForm` hook。

**长按识别二维码查看原文**

https://conform.guide/

Edmund Hung

**💱 React Currency Input Field Component v4.0** —— 一个旨在处理货币输入细节的组件，适用于自由格式输入无法满足需求的场景。你可以通过在线演示来试用。

**长按识别二维码查看原文**

https://github.com/cchanxzy/react-currency-input-field

Chun Chan

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- ⚠️ 我们上周提到的重大 npm 供应链攻击仍在继续蔓延，已影响数百个包。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/174364/web
    

- Dolt Workbench 是一个基于 React 的 Electron 打包桌面应用程序，用于处理 SQL 数据库。他们的团队分享了用于同时打包和发布多平台应用程序的完整自动化发布流程。
    
    **长按识别二维码查看原文**
    
    https://www.dolthub.com/blog/2025-09-11-automating-desktop-release-process/
    

- Safari 26.0 已随 macOS 26.0、iOS 26.0 等一起发布。除了大量 CSS 增强功能和用于嵌入 3D 模型的新 `<model>` 元素外，现在所有网站都可以在用户将其添加到主屏幕时在 iOS 和 iPadOS 上”成为 Web 应用程序”。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/17333/webkit-features-in-safari-26-0/
    

- Feedsmith 2.0 已发布 —— 这是一个快速的、用于解析和生成网络订阅（RSS、Atom 等）的一体化库。
    
    **长按识别二维码查看原文**
    
    https://feedsmith.dev/
    

- 有人想出了如何在一次性电子烟设备上托管网站。作者提到了 React，说电子烟的 20KB RAM 可能不够我们使用……😅
    
    **长按识别二维码查看原文**
    
    https://bogdanthegeek.github.io/blog/projects/vapeserver/
    

- Bun v1.2.22 已发布。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-v1.2.22
    

**版本发布：**

- **React on Rails v16.0** —— 一个将 React 集成到 Ruby on Rails 应用程序的方案。

- 🗓️ **DayPicker v9.10** —— 用于创建日期选择器、日历和日期输入的组件。

- **TanStack Form v1.20** —— 强大的、类型安全的 Web 表单状态管理。

- **TanStack Query v5.89** —— 异步状态管理和数据获取。