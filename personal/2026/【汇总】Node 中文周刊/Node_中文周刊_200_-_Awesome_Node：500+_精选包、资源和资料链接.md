# Node 中文周刊 #200 - Awesome Node：500+ 精选包、资源和资料链接

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544300&idx=1&sn=0b9fe963d190a00b73bb9e96d2661231&chksm=e921660ede56ef181d9c12c19a546082e4cb5fe26ec0e3450dac172e9909c482a2f7ae0dd7e7#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544300&idx=1&sn=0b9fe963d190a00b73bb9e96d2661231&chksm=e921660ede56ef181d9c12c19a546082e4cb5fe26ec0e3450dac172e9909c482a2f7ae0dd7e7#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544300&idx=1&sn=0b9fe963d190a00b73bb9e96d2661231&chksm=e921660ede56ef181d9c12c19a546082e4cb5fe26ec0e3450dac172e9909c482a2f7ae0dd7e7#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544300&idx=1&sn=0b9fe963d190a00b73bb9e96d2661231&chksm=e921660ede56ef181d9c12c19a546082e4cb5fe26ec0e3450dac172e9909c482a2f7ae0dd7e7#rd)

---

> 本期看点：Awesome Node 超全 Node.js 资源库，Mastro 从 Deno 迁移到 Node 的实践总结，AdonisJS 推出重构的新手包并内置认证，vite 插件让你直接在 js 里写 go 代码。

> 编辑：TimLi

🔥 本周热门

**Awesome Node：500+ 精选包、资源和资料链接** —— Sindre 维护的这个超全 Node.js 资源库，我们已经四年多没推过了，不过它最近一直持续更新，如果你有好东西也可以来贡献，不过审核门槛确实挺高的。

**长按识别二维码查看原文**

https://github.com/sindresorhus/awesome-nodejs

Sindre Sorhus

💡 还有不少类似的精选列表，比如 Awesome Node.js Security resources、Awesome SaaS Templates、Awesome npm Security Best Practices 以及 Awesome Regex，用起来也很顺手。

**长按识别二维码查看原文**

https://github.com/lirantal/awesome-nodejs-security

**Mastro 从 Deno 移植到 Node 的经验小记** —— Mastro 原本是基于 Deno 的 Web 框架和站点生成器，作者记录了迁移到 Node 过程中碰到的坑。Deno 和 Node 虽然目标接近，但代码迁移不算无脑搬，还是有不少细节要注意，不过想实现也不难。

**长按识别二维码查看原文**

[https://mastrojs.github.io/blog/https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025-10-27-what-learned-porting-from-deno-to-node-js/](https://mastrojs.github.io/blog/https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025-10-27-what-learned-porting-from-deno-to-node-js/)

Mauro Bieg

**AdonisJS 新手包新思路——从底层重新定义** —— Adonis 是个上手体验很棒的 Node 框架，最新的“新手包”不仅整合了按钮、表单、布局等基础组件，还带了现成的注册/登录系统，让你能更快搭起自己的应用程序。

**长按识别二维码查看原文**

https://adonisjs.com/blog/rethinking-starter-kits

Harminder Virk

📄 **重新思考 JavaScript 中的异步循环** —— `await` 放在循环或 `map()` 里会踩哪些坑，有哪些写法其实才是你真正想要的，这篇梳理得很清晰。Matt Smith

**长按识别二维码查看原文**

[https://allthingssmitty.com/https://voidzero.dev/posts/whats-new-viteconf-2025/10/20/rethinking-async-loops-in-javascript/](https://allthingssmitty.com/https://voidzero.dev/posts/whats-new-viteconf-2025/10/20/rethinking-async-loops-in-javascript/)

📺 **用 Node 搭建的月均 19 亿登录的认证系统是怎么炼成的** Sergio Salcedo

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=qYczG3j_FDo

📄 **npm 新安全举措能拦住下一个 Shai-Hulud 吗** ReversingLabs

**长按识别二维码查看原文**

https://www.reversinglabs.com/blog/npm-security-shai-hulud

**快讯：**

- **LTS 到底算不算 LTS？** 这两周 Node.js 的 LTS 版本出现了个小尴尬：眼下还没有被正式标记为“活动”LTS，导致 下载页面直接挂了。现在 Node v24.10.0 被指定为新 LTS，虽然它原先其实是“current”版本（现在这个标签已经让位给了 v25）。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/nodejs.org/pull/8251
    

- Lizz Parody 发了一则 Express.js 项目的最新现状更新，最近这个老牌框架也有不少新动作。
    
    **长按识别二维码查看原文**
    
    https://nodesource.com/blog/express-6-modernizig-nodejs-frameworks
    

- Node-RED 作为基于 Node 的 “低代码” 平台，快举办 Node-RED Con [https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025](https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025) 活动啦，11 月 4 号免费线上开搞，主题横跨工业、智能家居、甚至还有用 Node-RED 玩 Factorio！
    
    **长按识别二维码查看原文**
    
    https://nodered.org/
    

🛠  代码与工具

**Vitest v4.0 发布：Vite 原生测试框架** —— 这款由 Vite 驱动、兼容 Jest 的测试框架，4.0 加了可视化回归测试，Browser Mode 实现稳定，支持直接用浏览器跑测试，还有 Playwright Traces 等新特性。可以点这里和其它测试框架对比。

**长按识别二维码查看原文**

https://vitest.dev/blog/vitest-4

VoidZero 团队和社区

💡 VoidZero 的 Alexander Lichter 还专门写了ViteConf [https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025](https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025) 的总结文章，带你梳理 Vite+、Oxlint 支持 JS 插件、Nitro v3 等一堆新鲜事。

**长按识别二维码查看原文**

[https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025](https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-https://voidzero.dev/posts/whats-new-viteconf-2025)

👍 **emoji-regex：能匹配所有 Emoji 的正则表达式** —— 想用正则高效匹配各种 Emoji（包括表情本体和各种组合文本），这个库依照 Unicode 标准，超全。

**长按识别二维码查看原文**

https://github.com/mathiasbynens/emoji-regex

Mathias Bynens

💬 **GramIO：多平台 Telegram 机器人开发框架** —— 这个框架支持 Node、Bun 和 Deno 平台，让你无痛开发 Telegram 机器人，用的也是 Telegram 官方 Bot API。——GitHub 仓库戳这里。

**长按识别二维码查看原文**

https://gramio.dev/

Kravets

💡 还有一个同类的老牌框架 telegraf.js，专注 Node，值得一试。

**长按识别二维码查看原文**

https://github.com/telegraf/telegraf

**Gasket：自动发现 JS 和原生代码桥接点的 CLI 工具** —— 这个小众分析工具能动态地扫描 JS 函数对象的内存布局，找出那些 JS 和原生代码间的“桥”。作者团队还专门发了论文，主要是为安全分析服务。

**长按识别二维码查看原文**

https://github.com/gasket-tools/gasket

Alexopoulos 和 Sotiropoulos

**workerpool v10.0：任务线程池库** —— 这个久经验证的线程池库，不止可用于 Node，也能跑在浏览器环境。

**长按识别二维码查看原文**

https://github.com/josdejong/workerpool

Jos de Jong

📢  其他生态

圈内最近还有这些值得一看的新鲜事：

- vite-plugin-use-golang 出了个很猎奇的新插件，你只要在 JS 文件顶部加一句 `"use golang"`，后面就能直接写 Go 代码，最后自动编译成 WebAssembly。
    
    **长按识别二维码查看原文**
    
    https://www.npmjs.com/package/vite-plugin-use-golang
    

- 前端领域里，“import vs fetch 加载 JSON”的探讨最近又火了一把，Jake Archibald 分析了这两种方式的优劣。随着浏览器支持度提升，直接 `import` JSON 也更普遍了。
    
    **长按识别二维码查看原文**
    
    https://jakearchibald.com/2025/importing-vs-fetching-json/
    

- 在 **X** （原推特）上，Tzvetan Milkov 展示了一个非常有意思的 POC：直接用 React 驱动 Dear ImGui GUI 库，底层用的还是 Hermes JS 引擎，居然能做全平台原生应用程序。
    
    **长按识别二维码查看原文**
    
    https://x.com/tmikov/status/1979771014340047088
    

- 你其实已经有了 Git 服务器，这篇文章从 SSH 的角度重温了 Git 去中心化的强大。
    
    **长按识别二维码查看原文**
    
    https://maurycyz.com/misc/easy_git/
    

- CascadiaJS 大会上，Annie Sexton 带来了 ▶️ JavaScript 起源故事主题演讲，有兴趣的可以瞅一眼。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=Sl3XUmg4LBk
    

**版本发布：**

- **OpenAI Node v6.7** —— OpenAI 家族 API 的官方 Node 库，这次加了 Zod 4 schema 支持。

- **Electron v39.0** —— 跨平台桌面应用程序框架，Chromium 升级到 142。

- **vm2 v3.10** —— Node 下可以安全运行不信任代码的沙盒库，支持增加白名单模块。

- **ESLint Markdown Language Plugin v7.5** —— 专治 Markdown 文档中的 JS/TSX 代码块校验。

- **pnpm v10.19** —— 极速、省空间的包管理器。

- **Prisma v6.18** —— 新一代 Node.js + TypeScript ORM。

- **node-soap v1.6** —— SOAP 协议客户端和服务端库。

- **Hexo v8.1** —— 超高人气的博客框架/生成器。

- **node-redis v5.9** —— Redis/Valkey 客户端库。

- **ini v6.0** —— npm 官方的 INI 文件解析/序列化库。