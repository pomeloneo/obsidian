# React 中文周刊 #253 - 请停止滥用 useTransition！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544575&idx=1&sn=0cec34140bd3f315f62cb91772e85a95&chksm=e921651dde56ec0b34d5db499f611f9b04967510420919c287436277f8d540c87673a7bbb75c\#rd  
> 抓取时间: 2026/2/2 23:41:25

---

> 本期看点：Nicolas 指出 useTransition 滥用会导致交互问题并带来案例和替代方案，2025 年 Expo 在 React Native 生态中的定位分析，URL 作为应用程序状态管理的最佳实践探讨，ElevenLabs UI 组件库发布并专为多模态 Agent 场景设计。

> 编辑：TimLi

🔥 本周热门

**别在所有地方盲目用** `**useTransition**` —— `useTransition` 这个 hook 能让 UI 更新可中断，但滥用会让交互变得一团糟。Nicolas 指出这点，并带来了一些在线案例和替代方案，帮你更好地用对它。

**长按识别二维码查看原文**

https://www.charpeni.com/blog/dont-blindly-use-usetransition-everywhere

Nicolas Charpentier

**2025 年如何看 Expo 与 React Native** —— Expo 现在在 React Native 生态里的定位，就像 Next.js 之于 React。到底适不适合你的团队？Jack 帮你梳理了一下利与弊。

**长按识别二维码查看原文**

https://hashrocket.com/blog/posts/expo-for-react-native-in-2025-a-perspective

Jack Rosa

**URL 也是你的 State** —— 如果网站设计到位，URL 其实可以优雅地反映应用程序中的各种状态。Ahmad 深挖了这种经常被忽视的方式，并带来了 JS 和 React Router 的实用例子。

**长按识别二维码查看原文**

https://alfy.blog/2025/10/31/your-url-is-your-state.html

Ahmad Alfy

💡 nuqs 也是近几年很火的、专注类型安全的参数状态管理器，同样能帮你做状态同步。

**长按识别二维码查看原文**

https://nuqs.dev/

📄 **在 React Native 里用 Victory Native 绘制双 Y 轴图表** —— Victory Native 是一个 React Native 开源图表库，推荐数据可视化场景一试。Valerie Nielson

**长按识别二维码查看原文**

https://spin.atomicobject.com/victory-native-xl/

📄 **用** `**useSyncExternalStore**` **实现 Concurrent Hydration** Jacob ‘Kurt’ Groß

**长按识别二维码查看原文**

https://kurtextrem.de/posts/react-uses-hydration

**快讯：**

- Snapchat 团队最近把自家用多年的跨平台 UI 框架 **Valdi** 开源了，虽然不是 React Native，但也是同类赛道。更多介绍点这里。
    
    **长按识别二维码查看原文**
    
    https://github.com/Snapchat/Valdi
    

- 🔎 React Source Lens 让你在浏览器里点选组件，直接打开源码到编辑器，再也不用满世界找文件了。
    
    **长按识别二维码查看原文**
    
    https://github.com/darula-hpp/react-source-lens
    

- 🇯🇵 如果你认识在日本做技术的公司，最近 React 圈的大佬 Dan Abramov 正在找日本的工作哦！你可以推荐给周围小伙伴。
    
    **长按识别二维码查看原文**
    
    https://overreacted.io/hire-me-in-japan/
    

🛠  代码与工具

**ElevenLabs UI：面向多模态 Agent 场景的** `**shadcn/ui**`**-系组件库** —— 这是一套专为 agent 和音频类应用程序设计的 React 组件库，包括语音小球、波形、语音代理、音频播放器等。你可以在 官方文档站 直接体验各种交互组件。

**长按识别二维码查看原文**

https://ui.elevenlabs.io/

ElevenLabs

**Mantine DataTable：数据密集型应用程序的表格组件** —— 这是专为 Mantine 8 打造的高可定制数据表格/数据网格组件，轻松应对数据复杂场景。

**长按识别二维码查看原文**

https://icflorescu.github.io/mantine-datatable/

Ionut-Cristian Florescu

**Ink v6.5：用 React 构建交互式 CLI 应用程序** —— 这是一个非常流行的终端 React 渲染器，用组件方式打造高交互终端应用程序。v6.5 特别新增 增量渲染 支持，让终端 UI 性能再升级。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

**Valtio v2.2：用 Proxy 实现简单易用的状态管理** —— Valtio 能把对象变成响应式代理，组件外也能访问和订阅状态，还支持 computed 属性 等进阶用法。GitHub 地址点这里。

**长按识别二维码查看原文**

https://valtio.dev/

Daishi Kato

📢  其他生态

这周生态圈还有这些值得关注的新鲜事：

- Node.js v25.2.0 (Current) 发布了，重点是 type stripping 功能正式稳定（其实 v24 就能用）。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v25.2.0
    

- Matt Perry 分享了他关于 web 动画性能的所有经验，详见 The Web Animation Performance Tier List。
    
    **长按识别二维码查看原文**
    
    https://motion.dev/blog/web-animation-performance-tier-list
    

- 🇷🇴 老牌 JSHeroes 大会 2025 年 5 月 14-15 日将在罗马尼亚举办。如果你有想法分享，CFP （征稿）开放到 12 月 31 日。
    
    **长按识别二维码查看原文**
    
    https://jsheroes.io/
    

- 🇯🇵 想用日语写 JS 吗？来看看 KokoScript，真·会说“こんにちは”！
    
    **长按识别二维码查看原文**
    
    https://watilde.github.io/KokoScript/
    

- Bun v1.3.2 更新发布。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-v1.3.2
    

**版本发布：**

-  **React Native Apple Authentication v2.5** —— iOS 和 Android 都能上“使用 Apple 登录”。

- **react-jsonschema-form v6.1** —— 用 JSON Schema 描述表单结构，声明式搞定表单生成。（在线演示）

- 📅 **React Date Picker v8.9** —— 非常易用的日期选择组件。（Demo）

- **Fortune Sheet v1.0.4** —— 兼容 Google Sheets/Excel 风格的表格控件。（演示）

- **next-intl v4.5.0** —— Next.js 国际化全流程支持。

- **React Chrono v3.2.1** —— 现代化时间线组件。