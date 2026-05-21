# Node 中文周刊 #201 - Node v22 到 v24 升级指南

> 原文链接: [](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544428&idx=1&sn=6486059c4eb25785e71c7a4e6c9b8eed&chksm=e921658ede56ec9874deec315fca642a8c9a7b80dab175de200425075ae58fc35d0d2f88497a#rd)[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544428&idx=1&sn=6486059c4eb25785e71c7a4e6c9b8eed&chksm=e921658ede56ec9874deec315fca642a8c9a7b80dab175de200425075ae58fc35d0d2f88497a#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544428&idx=1&sn=6486059c4eb25785e71c7a4e6c9b8eed&chksm=e921658ede56ec9874deec315fca642a8c9a7b80dab175de200425075ae58fc35d0d2f88497a#rd): 2026/2/2 23:51:11

---

> 本期看点：Node v22 到 v24 升级指南发布，Node v25.1 发布，npm 安全升级即将失效所有经典 token，用 `URLPattern` 在 Node 24 里实现无框架路由，Electron v39.0 发布。

> 编辑：TimLi

🔥 本周热门

**Node v22 到 v24 升级指南** —— Node v24 现在已经成为新的 LTS 版本，如果你在用 v22，那就该考虑升级了。Node 团队专门整理了一份升级指南，帮你梳理重要的改动点。类似的升级手册还有 v20 到 v22、v14 到 16、v12 到 v14 都有，升级不迷路。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/migrations/v22-to-v24

Node.js Core Team

💡 此外还有 官方 userland 迁移 codemods 工具，辅助你自动完成部分升级工作。比如 v20 升 v22 的时候，能帮你把 `import ... assert` 自动换成 `import ... with`，非常方便。

**长按识别二维码查看原文**

https://nodejs.org/en/learn/getting-started/userland-migrations

**从 BitTorrent 导入 Node 模块** —— 这个点子不太适合生产，但确实挺酷！作者用 Node 的 customization hooks 玩了个花样，实现通过 BitTorrent 下载依赖并导入，既新颖又涨姿势。

**长按识别二维码查看原文**

https://evanhahn.com/node-torrent-import/

Evan Hahn

**Node.js 24 变为 LTS 你需要知道什么** —— Node v24.11.0 (LTS) 正式发布，Node 24 已成为新版 LTS。如果你打算从 22 升级，Lizz 总结了两者的区别。值得一看。

**长按识别二维码查看原文**

https://nodesource.com/blog/nodejs-24-becomes-lts

Lizz Parody

**在 Hugging Face Space 里跑 Node.js** —— 如果你和 Thomas 一样，因为 Glitch 关停 感到遗憾，可以看看他如何用 Hugging Face Spaces（以前主要做 ML 项目）来托管小型基于服务器的 Node 应用程序，另辟蹊径。

**长按识别二维码查看原文**

https://blog.tomayac.com/2025/11/03/running-nodejs-in-a-hugging-face-space/

Thomas Steiner

**📄 我们为什么从 Python 切换到 Node.js** —— 团队不能忍 Python 的异步体验，但用 Node.js 加上 MikroORM 玩得挺开心。Yakko Majuri

**长按识别二维码查看原文**

https://blog.yakkomajuri.com/blog/python-to-node

**📄 为什么** `**NaN !== NaN**`**（以及背后的 IEEE 754 故事）** —— NaN：既是数字，又不是数字，这就是它有趣的地方。Piotr Zarycki

**长按识别二维码查看原文**

https://pzarycki.com/en/posts/js-nan/

**📄 用** `**URLPattern**` **在 Node 24 里实现无框架路由** JSDev

**长按识别二维码查看原文**

https://jsdev.space/urlpattern-router-node24/

**快讯：**

- Node.js v25.1.0 (Current) 已经发布。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v25.1.0
    

- 提个醒！接下来一两周，npm 会吊销所有经典 npm token，旧 token 要失效，新 token 也将无法申请。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-09-29-strengthening-npm-security-important-changes-to-authentication-and-token-management/
    

- Vercel 以前不支持你尝试 Bun，现在 Vercel 原生支持 Bun 运行时了。如果你更喜欢 Node，也可以直接在 Vercel 上无配置部署 Fastify 应用程序，体验更顺畅了。查看详情
    
    **长按识别二维码查看原文**
    
    https://bun.sh/
    

🛠 代码与工具

**🖼️ image-dimensions：获取图片尺寸** —— 一个小巧工具，可以在任意 JS 环境下快速获得 JPEG、PNG/APNG、GIF、WebP、AVIF、HEIF 格式图片的宽高信息。

**长按识别二维码查看原文**

https://github.com/sindresorhus/image-dimensions

Sindre Sorhus

💡 想支持更多格式的话，image-size 这个包适合只在 Node 上用。

**长按识别二维码查看原文**

https://github.com/image-size/image-size

**type-flag：类型化命令行参数解析器** —— 可以直接定义命令行参数类型，并自动校验，让数据更稳妥。

**长按识别二维码查看原文**

https://github.com/privatenumber/type-flag

Hiroki Osame

**Electron v39.0：跨平台桌面应用程序开发框架** —— 上周简单提过，这回有了详细博客。升级到了 Chromium 142、V8 14.2，以及 Node 22.20。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-39-0

Charles Kerr

**on-change v6.0：监听对象或数组的变化** —— 用 Proxy 实现递归监听，敏感又高效。

**长按识别二维码查看原文**

https://github.com/sindresorhus/on-change

Sindre Sorhus

**sitemap.js v9.0：网站地图生成工具及 CLI** —— 自动帮你生成 XML 网站地图，便于搜索引擎（如 Googlebot）爬取你的网站。现在主推 ESM 模式。

**长按识别二维码查看原文**

https://github.com/ekalinin/sitemap.js

Eugene Kalinin

**版本发布：**

- **Dependency Cruiser v17.2** —— 依赖可视化工具（上图所示）。

- **pnpm v10.20** —— 更快、更省空间的包管理器。现在还能用 `pnpm help --all` 查看全部命令的帮助。

- **express-useragent v2.0** —— 高效的 Express 中间件，用来解析 user-agent。

- **jsdom v27.1** —— 纯 JS 实现 WHATWG DOM 和 HTML 标准。

- **Immer v10.2** —— 操作不可变数据的热门库。

- **express-rate-limit v8.2** —— Express 应用程序必备的基础限流方案。

- **npq v3.14** —— 帮你在安装 npm 包之前进行安全审查。

- **rimraf v6.1** —— 类似 `rm -rf`，但专为 Node 设计。

- **Ink v6.4** —— 用 React 写命令行应用程序，开发体验超棒。

- **ESLint v9.39.1**