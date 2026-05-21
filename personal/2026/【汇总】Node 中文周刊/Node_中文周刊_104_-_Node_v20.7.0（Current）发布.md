# Node 中文周刊 #104 - Node v20.7.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523943&idx=1&sn=196527ac004e43b9c45774c74560b4ad&chksm=e921d585de565c93a8b673d28b6ce67edfa3719453dbfa37690aad3f070587d52c35e535d9d7\#rd  
> 抓取时间: 2026/2/2 23:53:07

---

> 本期看点：Node v20.7.0（Current）发布了。这次发布比以往的版本少了一些功能，但 `npm` 升级到了最近发布的 v10.1。现在可以使用 `process.getSourceMapsEnabled` 检测是否启用了源映射，还支持多个 `--env-file` 声明（每个文件将根据需要覆盖前一个文件），以及一系列常规的错误修复。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Node.js 是否需要一个吉祥物？** —— Go 有可爱的 gopher、Deno 有一只恐龙、Bun 有一个包子，但是 Node 却没有官方吉祥物，Matteo Collina 在思考是否应该改变这一情况。大多数建议似乎都有点开玩笑，但 **Node 官网** 确实感觉有点空荡荡的，似乎需要点什么……

**长按识别二维码查看原文**

https://github.com/nodejs/admin/issues/828

Matteo Collina et al.

**Node v20.7.0（Current）发布** —— 这次发布比以往的版本少了一些功能，但 `npm` 升级到了最近发布的 v10.1。现在可以使用 `process.getSourceMapsEnabled` 检测是否启用了源映射，还支持多个 `--env-file` 声明（每个文件将根据需要覆盖前一个文件），以及一系列常规的错误修复。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.7.0

Ulises Gascón

💡 **Node v18.18.0（LTS）** 也已发布，该版本引入了 `--import` 标志，用于预加载 ESM 模块，类似于 `--require` 用于 CommonJS 模块。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.18.0

**Matteo 对 Bun 的看法** —— 作为 Fastify 的创作者和 Node.js TSC 成员，看到 Matteo 对替代运行时 **Bun** 的看法是很有趣的。他觉得很令人兴奋，但并不认为它已经是一个“即插即用的替代品”，特别是因为它 **不支持Fastify**。不过随后发布的 **Bun v1.0.2 已经开始支持 Fastify 了**。

**长按识别二维码查看原文**

https://adventures.nodeland.dev/archive/my-thoughts-on-bun/

Matteo Collina

**通过分析真实的命令注入案例来保护 Node 应用** —— 如果 npm 包中存在漏洞，就会有坏人想要利用它。一种特别危险的漏洞是当代码可以被操纵以运行意外和任意的命令时。Liran 解释了这种命令注入的后果，并展示了一个实际的例子。

**长按识别二维码查看原文**

https://www.nodejs-security.com/blog/securing-your-nodejs-apps-by-analyzing-real-world-command-injection-examples

Liran Tal

**Serverless Bun vs Node：在 AWS Lambda 上进行基准测试** —— 在 Bun v1.0 最近发布后，Mitchell 进行了一些测试，以确定更新后的运行时是否是 AWS Lambda 等无服务器环境中 Node 的有力竞争对手。

**长按识别二维码查看原文**

https://medium.com/@mitchellkossoris/serverless-bun-vs-node-benchmarking-on-aws-lambda-ecd4fe7c2fc2

Mitchell Kossoris

**使用 Zod 进行 Playwright API 测试** —— Zod 是一个以 TypeScript 为首选的模式声明和验证库。

**长按识别二维码查看原文**

https://timdeschryver.dev/blog/playwright-api-testing-with-zod

Tim Deschryver

**▶ 为什么不应该将 EventEmitter 用于异步操作**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Ra7Ji9LmG9o

Matteo Collina

**使用 Node.js 通过 SSH 连接远程服务器**

**长按识别二维码查看原文**

https://bipinparajuli.com.np/blog/shh-node

Bipin Parajuli

**快讯：**

- 你对于 **在 Node 中嵌入 SQLite** 有什么看法？目前还没有太多一致意见，但这是一个有趣的讨论。

**长按识别二维码查看原文**

https://github.com/nodejs/node/issues/49663

- 如果你想要 🐦**支持某人** 为 Node.js 做重要的性能工作，可以提名 Yagiz Nizipli（GitHub ID `anonrig`）成为 **GitHub 明星**。

**长按识别二维码查看原文**

https://twitter.com/yagiznizipli/status/1703813607127978133

- 在寻找更好的编程字体吗？Matej Latin 对 **包含编程连字的 5 种等宽字体进行了分析**。

**长按识别二维码查看原文**

https://betterwebtype.com/5-monospaced-fonts-with-coding-ligatures/

## 🛠 代码与工具

**Chrono v2.7：自然语言日期解析器** —— 给它一个字符串，比如“today”，“last Friday”，“2 weeks from now”，甚至一个完整的日期和时间，它都能生成一个合适的日期对象。如果需要对简体中文进行支持，可以考虑给项目提交 pr。

**长按识别二维码查看原文**

https://github.com/wanasit/chrono

Wanasit Tanakitrungruang

**depcheck：检查未使用的依赖的工具** —— 一个命令行工具，用于分析项目中的依赖项。用来查看每个依赖项的使用方式，包括未使用的依赖项和 `package.json` 中缺失的依赖。现在可以使用 `npx depcheck` 运行。

**长按识别二维码查看原文**

https://github.com/depcheck/depcheck

Djordje Lukic 与 Junle Li

**node-diskusage v1.2：跨平台磁盘使用统计** —— 实现了获取 Windows 和 POSIX 平台上的磁盘使用信息（可用空间、物理空间和总空间）的特定于平台的绑定。

**长按识别二维码查看原文**

https://github.com/jduncanator/node-diskusage

jduncanator

**workerpool v6.5：将任务分配给工作池** —— 一个长期存在的线程池库，可同时用于 Node 和浏览器。

**长按识别二维码查看原文**

https://github.com/josdejong/workerpool

Jos de Jong

**SMOB：对象和数组的安全合并** —— 一个零依赖的库，用于安全合并对象和数组，并具有可定制的行为。

**长按识别二维码查看原文**

https://github.com/tada5hi/smob

Peter Placzek

**i18n-iso-countries：ISO 3166-1 国家代码的国际化支持** —— 支持 75 种不同的语言，可以在字母和数字形式之间进行转换，包括 **ISO 3166 的表示形式**。

**长按识别二维码查看原文**

https://github.com/michaelwittig/node-i18n-iso-countries

Michael Wittig

**fusion.ssg v1.2：静态站点的极简框架** —— 如果 React 对于简单静态项目可能过于繁重，但仍希望使用 JSX/TSX 组件，那么这个框架可能是所需的一切。这里有一个 **视频演示**。

**长按识别二维码查看原文**

https://fusionssg.com/

Jeff Schwartz

**stale-dep：检查 `node_modules` 是否过时** —— 可以直接使用 `npx stale-dep` 来进行检查。

**长按识别二维码查看原文**

https://github.com/sxzz/stale-dep

Kevin Deng

**版本发布：**

- **node-google-spreadsheet v4.1**
    
    ↳ Google Sheets API 包装器.
    

- **ics v3.5**
    
    ↳ iCalendar（ics）生成库。
    

- **MongoDB Driver for Node v6.1**

- **Stripe Node.js Library v13.6**

## 🙋🏻‍♀️