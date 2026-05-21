# Node 中文周刊 #205 - Tinybench v6.0 超小巧基准测试库

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544934&idx=1&sn=99df7aa05e45e907f88116a5f4193bbc&chksm=e9217b84de56f292723cbf84a25c2ec472eb7c48ae68645ba7e63658dbc4b4e59de1238abf86#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544934&idx=1&sn=99df7aa05e45e907f88116a5f4193bbc&chksm=e9217b84de56f292723cbf84a25c2ec472eb7c48ae68645ba7e63658dbc4b4e59de1238abf86#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544934&idx=1&sn=99df7aa05e45e907f88116a5f4193bbc&chksm=e9217b84de56f292723cbf84a25c2ec472eb7c48ae68645ba7e63658dbc4b4e59de1238abf86#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544934&idx=1&sn=99df7aa05e45e907f88116a5f4193bbc&chksm=e9217b84de56f292723cbf84a25c2ec472eb7c48ae68645ba7e63658dbc4b4e59de1238abf86#rd)

---

> 本期看点：Tinybench v6.0 超小巧的基准测试库，Platformatic 的 Watt 应用程序服务器在 Kubernetes 中让 Next.js 性能提升 93%，JavaScript 开发者的范畴论入门。Voici.js v3.0：终端下优雅打印表格。

> 编辑：TimLi

🔥 本周热门

**Tinybench v6.0：超小巧的基准测试库** —— 这个库会用最精确的计时方式（比如 `process.hrtime` 或 `performance.now`），可以让你随意测试不同函数的性能，也能自定义测试时长或次数，测试后会给你一堆统计数据，而且支持多种运行环境。 GitHub 仓库在这。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinybench

Tinylibs

**在 Kubernetes 里 Next.js 性能提升 93%** —— Matteo Collina 介绍了 Platformatic 的 Watt 应用程序服务器 如何帮 Node 应用程序在 CPU 资源吃紧时加速扩展，非常适合需要高性能的场景。

**长按识别二维码查看原文**

https://blog.platformatic.dev/93-faster-nextjs-in-your-kubernetes

Matteo Collina（Platformatic）

**📈 对比 AWS Lambda ARM64 和 x86 不同运行环境与 Node 版本的性能** —— 作者在 Amazon 的 Serverless 环境下分别测试了 Node.js、Python 和 Rust。Node 这边，Node 22 比 Node 20 大概快 8-11%，而且在 ARM 上的表现比 x86 还要给力。Chris 总结说：**“切到 arm64 是最容易获得的性能提升。”** 不过每个人的测试结果可能不一样，毕竟性能评测向来水土不同。

**长按识别二维码查看原文**

https://chrisebert.net/comparing-aws-lambda-arm64-vs-x86_64-performance-across-multiple-runtimes-in-late-2025/

Chris Ebert

**Node.js v24 运行环境已登陆 AWS Lambda** —— 上周我们简单提到这个消息，现在 Amazon 发了完整博客，详细介绍了 Node.js 24 在 Lambda 上的改变。哪怕你不用 Lambda，这也相当于 Node.js 24 的快速更新手册。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/compute/node-js-24-runtime-now-available-in-aws-lambda/

Amorosi 和 Tuliani（Amazon）

💡 AWS Lambda 也 上线了 ‘Managed Instances’，方便你保留 Lambda 的无服务器体验，但是可以直接在你自己的 EC2 实例上跑。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/aws/introducing-aws-lambda-managed-instances-serverless-simplicity-with-ec2-flexibility/

**用 Claude Code 管理邮件** —— James 演示了如何用 Claude 的 “agent skills”，让一个 Node 应用程序自动抓取 Gmail 邮件，然后让 Claude Code 来分析。这功能最近我自己也玩了不少，是真的很强。

**长按识别二维码查看原文**

https://jlongster.com/wrangling-email-claude-code

James Long

**📄 用 HTTP Streaming 提升 TTFB 和用户体验** Mauro Bieg

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2025/improve-ttfb-and-ux-with-http-streaming/

**📄 cgroups v2 对 OpenShift 4 里的 Node.js 有啥影响？** Francisco De Melo Junior（Red Hat）

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/11/27/how-does-cgroups-v2-impact-java-net-and-nodejs-openshift-4

**📄 JavaScript 开发者的范畴论入门** Ibrahim Cesar

**长按识别二维码查看原文**

https://ibrahimcesar.cloud/blog/category-theory-for-javascript-typescript-developers/

**快讯：**

- Express v5.2 昨天刚发布，但注意今天马上就有了 v5.2.1，回滚了 5.2.0 的一个安全修复，否则某些应用程序会直接挂掉。 v4.22.0 和 v4.22.1 也一并发了，都是类似的情况。
    
    **长按识别二维码查看原文**
    
    https://github.com/expressjs/express/releases/tag/v5.2.0
    

- Node 24 LTS 已经可以在 Vercel 直接用来构建和部署函数啦。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-24-lts-is-now-generally-available-for-builds-and-functions
    

- 上周我们提过“Shai-Hulud 2.0”npm 蠕虫，现在 DataDog 总结了一篇很详细的梳理，可以看看事情的来龙去脉。
    
    **长按识别二维码查看原文**
    
    https://securitylabs.datadoghq.com/articles/shai-hulud-2.0-npm-worm/
    

- Electron 官方宣布 进入“安静月”，维护者们年底休息下，明年一月就会满血复活，帖子里也复盘了 2025 年 Electron 的一些情况。
    
    **长按识别二维码查看原文**
    
    https://www.electronjs.org/blog/dec-quiet-period-25
    

- 最近 Prisma 7 发布了，我们上期只简单提一下，这次 官方博客 更详细地解释了新版本的亮点。
    
    **长按识别二维码查看原文**
    
    https://www.prisma.io/blog/announcing-prisma-orm-7-0-0
    

🛠  代码与工具

**Voici.js v3.0：终端下优雅打印表格** —— 你要在终端打印一堆大对象，用这个非常合适。可以自动把数据排表格、动态调整列宽、支持输出排序甚至还能加点样式（包括各种颜色），很适合做可视化展示。 GitHub 仓库

**长按识别二维码查看原文**

https://voici.larswaechter.dev/

Lars Waechter

**Chokidar v5.0：高效多平台文件监听库** —— 封装了 `fs.watch` / `fs.watchFile` 并统一了各种系统上的事件表现，还处理了许多平台专属的坑点（比如 macOS 文件名问题），不管在哪个平台用 API 都一套。5.0 版本全面转向 ESM。

**长按识别二维码查看原文**

https://github.com/paulmillr/chokidar

Paul Miller

**readdirp v5.0：流式递归读取目录内容** —— 这个库能递归读取目录和所有子目录里的文件数据，用流式 API 很高效，非常方便批量操作文件。

**长按识别二维码查看原文**

https://github.com/paulmillr/readdirp

Paul Miller

**binary-parser v2.3：声明式二进制解析器** —— 可以链式写法定义各类二进制结构，再用来解析真实数据，比如实现 IP 包头解析只要 `.endianness("big").bit4("version").bit4("headerLength")` 一步步加功能即可。

**长按识别二维码查看原文**

https://github.com/keichi/binary-parser

Keichi Takahashi

**Better Auth：TypeScript 的通用认证框架** —— 一个不用绑定特定框架的认证与授权库，支持邮箱+密码、OAuth、社交账号登录、账号/会话管理、2FA 多因子等， v1.4 新增数据库无关的无状态会话功能。

**长按识别二维码查看原文**

https://www.better-auth.com/

Better Auth

📢  其他生态系统

这里就是最近圈子里一些有意思的消息汇总：

- DepX 徽章生成器 能给你生成漂亮小徽章 **(就在上面那张图)**，可以直接放进 README 或项目主页，显示 npm 包依赖数目，轻松展示“零依赖”或“极简依赖”。
    
    **长按识别二维码查看原文**
    
    https://depx.co/badge
    

- 🎄 谜题控又有节日活动啦！**Advent of Code** 今年又上线，这次只出 12 天挑战，而不是传统的 25 天，解完估计比以前容易多了，你敢来试试不？
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

- 🔒 **Let’s Encrypt** 最近宣布未来两年要逐步缩短证书有效期，从 90 天降到 45 天。要是你有自动申请证书的流程，最好提前适配下别翻车。
    
    **长按识别二维码查看原文**
    
    https://letsencrypt.org/2025/12/02/from-90-to-45.html
    

- JavaScript 各类算法和数据结构演示，超 150 个例子，还有详细注释，支持十八种语言，学习算法的绝佳入门资料。
    
    **长按识别二维码查看原文**
    
    https://github.com/trekhleb/javascript-algorithms
    

- Piccalilli 团队把 JavaScript for Everyone 课程里的“异步 JS 入门”这一章 免费对外开放，想学异步不用花钱啦！
    
    **长按识别二维码查看原文**
    
    https://piccalil.li/javascript-for-everyone/lessons
    

- Brimstone 又一个新生代 JavaScript 引擎（现在已经有 一堆 了），不过这个支持力度很猛（已实现 97% 规范），用 Rust 写的，而且体积超级小，非常适合嵌入式场景。
    
    **长按识别二维码查看原文**
    
    https://github.com/Hans-Halverson/brimstone
    

**版本发布：**

- **Playwright v1.57** —— 微软的浏览器/Web 自动化库 HTML 报告新增了“速度板”功能，可以直接看到哪些测试最慢；主力浏览器也从 Chromium 切换成了 Chrome for Testing。

- **pnpm v10.24** —— 这个高效率包管理器又升级了，现在下载依赖能更智能动态调整并发，提高速度。

- **Sidequest v1.13** —— Node 应用程序的可扩展后台任务处理利器，注意使用的是 LGPL 协议。

- **better-sqlite3 v12.5.0** —— 流行的本地 SQLite3 库升级，内嵌 SQLite3.51.1 了。

- **node-rate-limiter-flexible v9.0** —— 新增对 Mongoose 9 的支持。

- **Neutralinojs v6.4** —— 更轻量的 Electron 替代品，适合做小型桌面应用程序。

- **NodeBB v4.7** —— 基于 Node.js 的社区论坛系统更新。

- **ESLint v10.0.0 Alpha 1**