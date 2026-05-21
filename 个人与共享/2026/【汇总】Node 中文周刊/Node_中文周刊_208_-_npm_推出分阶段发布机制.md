# Node 中文周刊 #208 - npm 推出”分阶段发布”机制

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545441&idx=1&sn=9e25d6603b42ce899bf2f24ac0b48e82&chksm=e9217983de56f095d1855ea18f9ec693286c87ff62a80c94ad05fa22774eb0f9de94388dc41e#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545441&idx=1&sn=9e25d6603b42ce899bf2f24ac0b48e82&chksm=e9217983de56f095d1855ea18f9ec693286c87ff62a80c94ad05fa22774eb0f9de94388dc41e#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545441&idx=1&sn=9e25d6603b42ce899bf2f24ac0b48e82&chksm=e9217983de56f095d1855ea18f9ec693286c87ff62a80c94ad05fa22774eb0f9de94388dc41e#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545441&idx=1&sn=9e25d6603b42ce899bf2f24ac0b48e82&chksm=e9217983de56f095d1855ea18f9ec693286c87ff62a80c94ad05fa22774eb0f9de94388dc41e#rd)

---

> 本期看点：npm 推出”分阶段发布”机制以加强供应链安全，require(esm) 在 Node.js 从实验特性到稳定，TypeScript 大型 monorepo 优化实战，npmgraph 提供 npm 依赖关系可视化工具，Fabric.js v7 发布并支持 HTML5 Canvas 和 Node.js。

> 编辑：TimLi

🔥 本周热门

**npm 推出“分阶段发布”机制，解决令牌系统变动后的一系列问题** —— 2025 年 npm 生态真是跌宕起伏，既有钓鱼攻击，也有 Shai Hulud 事件，再加上 npm 令牌系统 的调整。2026 年，GitHub 宣布会增加更多 npm 包发布的安全机制，比如全新的“分阶段发布”（staged publishing）模式，今后每个包上线前都将有一个审核期，来进一步确保安全。

**长按识别二维码查看原文**

https://nodeweekly.com/link/178928/web

Sarah Gooding (Socket)

**require(esm) 在 Node：实验到稳定的蜕变** —— Joyee Cheung 是 Node.js 核心贡献者，也是推动 `require(esm)`（即用 require 加载 ES module）落地的关键人物。她最新的两篇博客详细讲了功能从实验到成为官方特性的心路历程，以及 背后的技术实现细节。

**长按识别二维码查看原文**

https://joyeecheung.github.io/blog/2025/12/30/require-esm-in-node-js-from-experiment-to-stability/

Joyee Cheung

📺 Joyee 还专门在 Nordic.js 做了相关主题分享 **Shipping Node.js packages in 2025**，强烈推荐观看。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=I0jvOJW7NaI

**TypeScript 性能问题大揭秘：一个案例分析** —— Solomon 团队负责的一个超大型 monorepo TypeScript 项目，编辑器提示卡慢、类型检查和构建都很慢，但是他们通过一系列改造，成功搞定了这些性能难题。

**长按识别二维码查看原文**

https://www.viget.com/articles/fixing-typescript-performance-problems

Solomon Hawk

📄 **Node 脚本自动加载 .env 文件的正确姿势** —— Node 24 起，加载 `.env` 已经是内置功能啦，无需第三方库。Stefan Judis

**长按识别二维码查看原文**

https://www.stefanjudis.com/today-i-learned/load-env-files-in-node-js-scripts/

📄 **Express 4 vs Express 5，到底谁更快？** —— 各类基准测试结果仅供参考，数据只作辅助，建议还是亲自多跑几组结果。RepoFlow

**长按识别二维码查看原文**

https://www.repoflow.io/blog/express-4-vs-express-5-benchmark-node-18-24

📄 **V8 里的 Pre-Tenuring 机制是什么？** Andy Wingo

**长按识别二维码查看原文**

https://wingolog.org/archives/2026/01/05/pre-tenuring-in-v8

📄 **用 Static Hermes 把 JavaScript 编译为 C** Devon Govett

**长按识别二维码查看原文**

https://devongovett.me/blog/static-hermes.html

📄 **纯 JavaScript 实现流式 JSON：200 行代码做出来** Krasimir Tsonev

**长按识别二维码查看原文**

https://krasimirtsonev.com/blog/article/streaming-json-in-just-200-lines-of-javascript

**快讯：**

- Reddit 上 `/r/node` 板块在讨论 为什么 Node.js 没有被视为“企业级”，比如跟 C\#、Java 相比。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/node/comments/1plnmqb/why_nodejs_is_not_considered_enterprise_like_c/
    

- pnpm 主要维护者 Zoltan Kochan 发文聊了下 2025 年 pnpm 拥有了哪些重大变化。
    
    **长按识别二维码查看原文**
    
    https://pnpm.io/
    

🛠  代码与工具

**npmgraph：npm 依赖关系可视化神器** —— 这个 Web 工具只需输入一个或多个 npm 包名称（或直接上传 `package.json` 文件），就能帮你生成依赖图谱，直观展现包之间的连接关系。还能根据维护者数量等属性上色，支持导出成 SVG 图片，非常适合做依赖梳理。

**长按识别二维码查看原文**

https://npmgraph.js.org/

Kieffer、Brigante 及其他开发者

**Fabric.js v7：老牌 HTML5 Canvas 库迎来大升级** —— 既能跑在浏览器，也兼容 Node（多亏了 node-canvas）。Fabric 在 canvas 元素上构建了丰富的对象模型，还提供 SVG 转 canvas、canvas 转 SVG 等能力。官网上有大量 demo，代码都有，值得一试。

**长按识别二维码查看原文**

https://fabricjs.com/

Bogazzi、Nen 等开发者

📢  其他生态

来看看本周在更广泛圈子的一些有趣动态：

- MicroQuickJS：QuickJS 作者 Fabrice Bellard 新推出的 JavaScript 引擎，专注极致小巧的嵌入式场景，能在仅 10KB 内存下运行。
    
    **长按识别二维码查看原文**
    
    https://github.com/bellard/mquickjs/blob/main/README.md
    

- **Ultimate Linux**：这个项目非常有意思，尝试 用 JavaScript 写个极简 Linux 用户空间（底层同样基于 QuickJS）。
    
    **长按识别二维码查看原文**
    
    https://github.com/popovicu/ultimate-linux
    

- Addy Osmani 总结了 他在 Google 工作 14 年得到的 21 条经验，这些建议对工程师职业生涯稳步成长格外有用。
    
    **长按识别二维码查看原文**
    
    https://addyosmani.com/blog/21-lessons/
    

- **State of HTML 2025** 调查结果 已经发布，感兴趣可以围观下趋势。
    
    **长按识别二维码查看原文**
    
    https://2025.stateofhtml.com/en-US/
    

- TIL（今日一课）：只要在你的 GitHub 主页地址后加 `.png`，比如 `github.com/USERNAMEHERE.png`，就能直链自己的头像哦！还可以用 `.keys` 获取公钥，用 `.atom` 获取时间线 feed，很有趣！

**版本发布：**

- **pnpm v10.27** —— 这个主打高效与安全的包管理器迎来细致更新，比如可以忽略「已发布超过指定天数的包」的信任校验。

- 🔎 **file-type v21.2** —— 自动识别 `Buffer`、`Uint8Array`、`ArrayBuffer` 的文件类型。v21.2 加了对 Mach-O Universal 二进制的支持。

- **Fast HTML Parser v7.0.2** —— 性能极高的 HTML 解析器，能生成简化版 DOM，支持基础元素查询。

- **Middy v7.0** —— 专为 AWS Lambda 设计的 Node.js 中间件引擎，现在支持 Durable Functions。

- **Node File Trace v1.2** —— 帮你精准分析应用程序实际运行所需的文件，做体积优化必备。

- **Orange ORM v4.8** —— 跨 Node、Bun、Deno 的对象关系映射（ORM）工具。

- **Repomix v1.11** —— 可以把整个代码仓库打包成一个适合 LLM 消化的文件。

- **hot-shots v12.0 & v12.1** —— statsd、DogStatsD 和 Telegraf 的 Node.js 客户端。