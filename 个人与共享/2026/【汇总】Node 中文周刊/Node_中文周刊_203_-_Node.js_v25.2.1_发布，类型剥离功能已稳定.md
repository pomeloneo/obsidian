# Node 中文周刊 #203 - Node.js v25.2.1 发布，类型剥离功能已稳定

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544676&idx=1&sn=2d44b6b32d3cd3034b654c908399337a&chksm=e9216486de56ed90652614e4fafe3da438ebb1a046c8b193c2a92839487f5583834e712a4395#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544676&idx=1&sn=2d44b6b32d3cd3034b654c908399337a&chksm=e9216486de56ed90652614e4fafe3da438ebb1a046c8b193c2a92839487f5583834e712a4395#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544676&idx=1&sn=2d44b6b32d3cd3034b654c908399337a&chksm=e9216486de56ed90652614e4fafe3da438ebb1a046c8b193c2a92839487f5583834e712a4395#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544676&idx=1&sn=2d44b6b32d3cd3034b654c908399337a&chksm=e9216486de56ed90652614e4fafe3da438ebb1a046c8b193c2a92839487f5583834e712a4395#rd)

---

> 本期看点：Node.js v25.2.1 发布并将 Type Stripping 功能标记为稳定，Electron 和 Tauri 桌面应用程序开发对比分析，V8 垃圾回收器近两年发展回顾，Inquirer.js v13.0 完全转向 ESM 并完成现代化升级。

> 编辑：TimLi

🔥 本周热门

**Node.js v25.2.1（当前版本发布，v25.2.0 Type Stripping 标记为“稳定”）** —— 上周刚发完快报，Node.js 就把 v25.2.0 放出来了，而且还把 type stripping（类型剥离）功能标记为稳定，这代表现在主流服务端运行时都已经“官方支持” TypeScript（至少是类型剥离这个层面）。v25.2.1 紧接着修复了一个规范相关的 bug：`localStorage` 访问可能会抛异常，这个问题要等到 v26 再处理。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.2.1

Antoine du Hamel

**Electron 和 Tauri 桌面应用程序开发对比** —— 有开源团队一直用 JavaScript + Electron 做桌面应用程序，这次尝试改用基于 Rust 的 Tauri，结果有好有坏（不过总体上还是挺满意的），而且核心代码依旧大部分可以用 JavaScript 写。

**长按识别二维码查看原文**

[https://www.dolthub.com/blog/https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025-11-13-electron-vs-tauri/](https://www.dolthub.com/blog/https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025-11-13-electron-vs-tauri/)

Eric Richardson

**V8 垃圾回收器近年发展回顾** —— Andy 既做过 V8，也参与过 JavaScriptCore 研发，这次详细梳理了 V8 引擎近两年来垃圾回收器的发展，虽然很技术流，但对关注底层的同学很有参考价值，顺便也补点历史知识。

**长按识别二维码查看原文**

[https://wingolog.org/archives/https://openjsf.org/blog/openjs-security-update-oct-2025/11/13/the-last-couple-years-in-v8s-garbage-collector](https://wingolog.org/archives/https://openjsf.org/blog/openjs-security-update-oct-2025/11/13/the-last-couple-years-in-v8s-garbage-collector)

Andy Wingo

**在 GitHub Actions 自动轮换 NPM 密钥** —— 如果你在项目里用自动化脚本发布 npm 包，最近应该已经被 npm 新一波安全策略影响到。这篇文章讲了如果还没准备好用“信任发布”机制，怎么让自动发布的流程继续运转下去。

**长按识别二维码查看原文**

https://michaelheap.com/rotate-all-npm-tokens-github-actions/

Michael Heap

📄 **用 Node.js 工具“官方”地废弃方法** —— 你知道 Node 里有个 `deprecate` 方法吗？Stefan Judis

**长按识别二维码查看原文**

https://www.stefanjudis.com/today-i-learned/deprecate-method-in-node-js/

📄 **Tinyglobby：一次小项目的现代化与性能飞跃** Madeline Gurriarán

**长按识别二维码查看原文**

https://e18e.dev/blog/tinyglobby-migration.html

📄 **印尼食品 TEA 被盗事件：一起 NPM 垃圾包分析** Staicu 和 Raj（Endor Labs）

**长按识别二维码查看原文**

https://www.endorlabs.com/learn/the-great-indonesian-tea-theft-analyzing-a-npm-spam-campaign

📄 **JavaScript 安全编码实用小贴士** Tanya Janca

**长按识别二维码查看原文**

[https://stackoverflow.blog/https://openjsf.org/blog/openjs-security-update-oct-2025/10/15/secure-coding-in-javascript/](https://stackoverflow.blog/https://openjsf.org/blog/openjs-security-update-oct-2025/10/15/secure-coding-in-javascript/)

**快讯：**

- OpenJS 基金会发了 [https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025](https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025) 年 10 月安全动态，核心话题还是围绕 Node.js。
    
    **长按识别二维码查看原文**
    
    [https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025](https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025)
    

- 🗣️ Reddit 上的 `/r/node` 里，围绕 NestJS 展开了激烈讨论，优劣两派你来抬杠。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/node/comments/1ov6xrd/nestjs_is_bad_change_my_mind/
    

- 说到 Reddit，Josef Strzibny 把 Reddit 最近公开的“活跃度”数据抓出来对比了一把，不少语言讨论区 `/r/node` 居然比 `/r/javascript` 还活跃。

- Node.js 从 4.0 版本起就有 `Error.captureStackTrace` 这个老 API，最近它的 提案 已经在本周 TC39 达到 stage 2 进展，后续有望在更多环境落地。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/api/errors.html\#errorcapturestacktracetargetobject-constructoropt
    

- Node.js v24.11.1（LTS） 发布，修复了 `Buffer.allocUnsafe` 的 bug。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v24.11.1
    

🛠  代码与工具

**Inquirer.js 13.0：常用交互式 CLI 控件合集** —— 想让用户命令行里选项、输入密码、多选打勾，这种常见需求 Inquirer 都能解决。这次 v13 做了“现代化”升级：完全转向 ESM，抛弃 CommonJS，老接口也清理了一大堆。另外 Yoctocolors 相关的依赖被换成 Node 原生的 `styleText` 了。

**长按识别二维码查看原文**

https://github.com/SBoudrias/Inquirer.js

Simon Boudrias

**Globby v16.0：好用的 Glob 匹配库** —— 你只要传给它一组 glob 字符串，它就能返回全部匹配路径。支持各种否定模式（v16 新增纯否定），还能智能识别 `.gitignore`，而且现在还能“继承”父目录下的 `.gitignore` 配置。

**长按识别二维码查看原文**

https://github.com/sindresorhus/globby

Sindre Sorhus

**node-libcurl v5.0：Node 的** `**libcurl**` **绑定** —— libcurl 是个经典的强大库，能解析网址并支持 HTTP、IMAP、SCP、SFTP、LDAP 等众多协议。v5.0 升级到了 libcurl 8.17.0，而且官方预编译包也全面开启了 HTTP/3 支持。

**长按识别二维码查看原文**

https://github.com/JCMais/node-libcurl

Jonathan Cardoso Machado

**📊 Ackee v3.5：Node 自托管网页分析系统** —— 上周我们讲过 Umami，其实 Ackee 也是业内老牌 Node 驱动的自托管数据分析方案，GitHub 仓库点这里。

**长按识别二维码查看原文**

https://ackee.electerious.com/

Tobias Reich

**Marked.js v17.0：极速 Markdown 解析与编译** —— Marked.js 是一个极简但高性能的 Markdown 编译器，支持前端、服务端以及 CLI 多种用法。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

📢  其他生态

本周还有这些新鲜事，看看各路花边：

- Visual Studio Code 最新 v1.106 版来了：现在 diff 里能选中被删掉的代码，内联建议可以直接在边栏“打盹”关闭，跳转行命令支持按字节或列偏移跳，另外 终端 IntelliSense 也终于标记为稳定版啦。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_106
    

- Git 2.52 发布，新加了不少小特性，比如 `git last-modified` 能帮你查文件最近修改的提交。
    
    **长按识别二维码查看原文**
    
    https://github.blog/open-source/git/highlights-from-git-2-52/
    

- 你知道 LibreOffice 居然能用 JavaScript 脚本吗？甚至还能 复刻一个 Wordle 游戏。
    
    **长按识别二维码查看原文**
    
    [https://bojidar-bg.dev/blog/https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025-11-11-wordle-libreoffice/](https://bojidar-bg.dev/blog/https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-https://openjsf.org/blog/openjs-security-update-oct-2025-11-11-wordle-libreoffice/)
    

- JavaScript Engines Zoo 维护了一个 JS 引擎大数据表，收录 100 多个引擎，信息一览无余。
    
    **长按识别二维码查看原文**
    
    https://zoo.js.org/
    

- Visual Types 做了个很直观的类型系统可视化，有 TypeScript 基础的小伙伴可以进去玩玩。
    
    **长按识别二维码查看原文**
    
    https://types.kitlangton.com/
    

- 🔥 英国人民最近流行一种新取暖方式：让家里托管数据中心，服务器发热还能免费暖屋！这思路，有点皮。
    
    **长按识别二维码查看原文**
    
    https://www.bbc.co.uk/news/articles/c0rpy7envr5o
    

- Nginx 限流的简易教程。
    
    **长按识别二维码查看原文**
    
    https://joshtronic.com/2025/11/09/rate-limiting-nginx/
    

**版本发布：**

- **pnpm v10.22** —— 高速省空间的包管理器，这次加了 `trustPolicyExclude` 配置，你可以指定某些包无视信任策略也强行装。

- **MikroORM v6.6** —— 用 TypeScript 写的 Node.js ORM，采用数据映射、工作单元和身份映射等模式，现在可以更灵活地控制关联过滤，还支持私有属性。

- 🤖 **OpenAI Node v6.9** —— OpenAI 的官方 Node 库，这波已支持最新 GPT-5.1。

- **ESLint v10.0.0 Alpha 0** —— v10 首个 alpha 版放出，提前尝鲜破坏性升级。

- **LogTape v1.2** —— JS 全平台通用的简洁日志库，更新日志看这里。

- **pg-boss v12.2** —— 基于 Postgres 的 Node 任务队列。

- **Mercurius v16.6** —— 一款基于 Fastify 的 GraphQL 服务端实现。

- **FoalTS v5.1** —— 全能型 Node.js 应用程序框架。