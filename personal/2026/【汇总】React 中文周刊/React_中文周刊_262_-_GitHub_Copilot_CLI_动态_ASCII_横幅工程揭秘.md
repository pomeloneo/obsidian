# React 中文周刊 #262 - GitHub Copilot CLI 动态 ASCII 横幅工程揭秘

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545877&idx=1&sn=5f62448dd3f3d60be8c1d6ea145e4aaf&chksm=e9217ff7de56f6e1e06a192bbd3105e187810655e10833166a9015d445b338f555e30f78258f\#rd  
> 抓取时间: 2026/2/2 23:41:04

---

> 本期看点：GitHub 发布 Copilot CLI 动态 ASCII 横幅实现原理，基于 Ink 和 React 实现终端动画；React 19发布一系列更新修复服务端组件相关 DoS 漏洞；Ryan Carniato 发布《JavaScript 框架走向 2026》年度盘点；Vercel 评测显示 AGENTS.md 在 Agent 任务中优于 Skills。

> 编辑：TimLi

🔥 本周热门

**GitHub Copilot CLI 动态 ASCII 横幅的工程揭秘** —— GitHub 的 Copilot CLI 工具其实和许多基于终端的智能体很像，底层用的是 Ink，一个基于 React 的 TUI 渲染库。团队这次专门分享了如何把炫酷的动画效果塞进终端界面。顺带一提，GitHub 动画师 Cameron Foxly 还开发了 ASCII Motion，一个基于 Web 的 ASCII 艺术动画工具（也是个 开源 React 应用程序）。

**长按识别二维码查看原文**

https://github.blog/engineering/from-pixels-to-characters-the-engineering-behind-github-copilot-clis-animated-ascii-banner/

Aaron Winston（GitHub）

⚠️ **React v19.2.4、v19.1.5 和 v19.0.4 带来更多服务端组件 DoS 修复** —— 实测发现，React Server Components 之前的 DoS 修复其实还不完全，还有多个拒绝服务漏洞没修掉，这次是进一步修复这些安全问题。

**长按识别二维码查看原文**

https://github.com/facebook/react/security/advisories/GHSA-83fc-fqcc-2hmg

React 团队

💡 安全相关补充，Vercel 也总结了 Next.js 自托管应用程序里的两个 DoS 漏洞，这些问题已在 Next.js 15.5.10、15.6.0-canary.61、16.1.5 以及 16.2.0-canary.8 里修复。

**长按识别二维码查看原文**

https://vercel.com/changelog/summaries-of-cve-2025-59471-and-cve-2025-59472

**JavaScript 框架走向 2026** —— 每年 SolidJS 作者 Ryan Carniato 都对整个前端框架圈做一次盘点，今年他说整个生态正处于“超级激动人心的阶段”，并各个领域都做了拆解。有不少新动态值得关注，框架大战还远远没结束。

**长按识别二维码查看原文**

https://dev.to/this-is-learning/javascript-frameworks-heading-into-2026-2hel

Ryan Carniato

▶️ **利用 React Server Components 优化性能** —— 这场 ReactNext ’25 讲座由 Vercel 工程师带来，前面是 RSC 的基础介绍，后半部分有演示，一步步撸代码教你用更高级的写法把 RSC 性能榨干。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=TInTm-M5yBs

Gal Schlezinger

🤖 **Vercel 最新实验：**`**AGENTS.md**` **在评测中比 Skills 更强** —— Vercel 最近在 Agent 相关的研究特别多（比如刚发的 React 最佳实践 Skills 包）。不过他们最新一次面向 Next.js 16 的评测中发现，直接把 8KB 文档索引塞进 `AGENTS.md` 文件，效果反而比 Skills 更好，因为 Skills 在调用时会有命中率问题。

**长按识别二维码查看原文**

https://vercel.com/blog/agents-md-outperforms-skills-in-our-agent-evals

Vercel

📄 **TanStack Start 的 Single Flight Mutations** —— 这是一组非常详细的两篇文章，写得非常深，带你全面理解这个主题。Adam Rackis

**长按识别二维码查看原文**

https://frontendmasters.com/blog/single-flight-mutations-in-tanstack-start-part-1/

📄 **给 React Native 带来 CSS Clipping** Kamil Paradowski

**长按识别二维码查看原文**

https://www.callstack.com/blog/bringing-css-clipping-to-react-native

📄 **如何写出高质量的 React 单元测试** Elio Capella Sánchez

**长按识别二维码查看原文**

https://eliocapella.com/blog/writing-good-unit-tests/

**快讯：**

- 在 Reddit 的 `/r/reactjs` 有开发者分享了 用了 React Compiler 后，性能提升堪称翻天覆地，真的震惊到自己。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/reactjs/comments/1qkthp8/started_using_the_react_compiler_and_was_pretty/
    

- 还有 Reddit 发起了 TanStack Start、React Router、Next.js 谁更好用的讨论，TanStack 获得了最多推荐。有评论还说 **“John Resig 说 tanstack 很棒，顶级背书！”** 😁
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/reactjs/comments/1qqu390/tanstack_vs_react_router_vs_next/
    

- Expo SDK 55 的 beta 发布 正在火热进行，集成了 React Native 0.83.1 和 React 19.2.0，现在应用程序还可以选择用 Hermes v1。
    
    **长按识别二维码查看原文**
    
    https://expo.dev/changelog/sdk-55-beta
    

🛠 代码、工具和库

**Facehash：极简风格的用户头像组件** —— 并不是所有用户都会上传头像，Facehash 可以为缺省头像的位置带来一丝新意。它可以生成自动且有细节感的头像，也能在用户自定义头像加载失败时兜底显示。

**长按识别二维码查看原文**

https://www.facehash.dev/

Cossistant

**React Tilt Button：自带“弹性按压”+ 3D 倾斜效果的按钮组件** —— 这个按钮的亮点是“软绵绵按下去”的感觉，鼠标悬浮其上时还会有 3D 倾斜，有点像真手按住一样。非常可爱的自定义按钮，看看这个 GitHub 仓库 吧。

**长按识别二维码查看原文**

https://react-tilt-button.vercel.app/

Archis Vaze

🔁 **Travels v1.0：高效、节省内存的撤销/重做库** —— 只保存每次变更而不是全部历史快照，所以内存占用非常低，轻松给你的应用程序加上撤销/重做功能。还带有适配 React 的 `use-travel` hook。

**长按识别二维码查看原文**

https://github.com/mutativejs/travels

Mutative

**React2AWS：用 React 组件管理 AWS 基础设施** —— 说白了，好像在“把 XML 倒腾回来”？😅 不过创意确实新颖，直接用 JSX 写 AWS 资源描述，最后生成生产环境可用的 Terraform 配置代码。

**长按识别二维码查看原文**

https://www.react2aws.xyz/

Marko Marinovic

📢 其他生态系统

下面是本周生态圈的一些新鲜事：

- Bun 最近连发两版新版本：Bun v1.3.7 带来了 35% 的 `async`/`await` 性能提升，对 ARM64 优化，还原生支持 JSON5 和 JSONL，更新了 JavaScriptCore 引擎。Bun v1.3.8 则内置了 Markdown 解析器。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-v1.3.7
    

- Yarn 6 现已预览，这款老牌 npm 替代工具即将 10 岁，直接用 Rust 重写，主打极致性能，不过正式版大概要等到 2026 年第三季度。
    
    **长按识别二维码查看原文**
    
    https://yarn6.netlify.app/blog/2026-01-28-yarn-6-preview/
    

- Meta 的 StyleX CSS-in-JS 库换了新官网，还上线了 全新 Playground。
    
    **长按识别二维码查看原文**
    
    https://stylexjs.com/
    

- “两年半都在 vibe coding，现在又回归手写笔记了”
    
    **长按识别二维码查看原文**
    
    https://atmoio.substack.com/p/after-two-years-of-vibecoding-im
    

- 🎨 一个超实用的 Web SVG 路径编辑工具。
    
    **长按识别二维码查看原文**
    
    https://yqnn.github.io/svg-path-editor/
    

**版本发布：**

- **React Timeline Editor v1.0** —— 用于制作类似时间轴编辑器的组件（上图就是实际效果）。官网有很多案例，可以参考。

- 🤖 **React Native AI v0.12.0** —— 一个端侧 AI 工具包，支持 Vercel AI SDK。

- **react-dropzone v14.4** —— 非常简单的文件拖拽上传 React hook。

- **focus-trap-react v12.0** —— 限定键盘焦点只能停留在指定区域的 React 组件。

- **Rspack v2.0 Alpha 1** —— 新增原生 RSC 插件（有 示例代码）。