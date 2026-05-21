# Node 中文周刊 #132 - Node.js 22.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531445&idx=1&sn=915aa5a093e5c1e2fe8d418fce9c4aec&chksm=e9213057de56b9411072e3b92d59e6703c5e8a8f7316c0a48e22c5421ab160c815ae6b15fe7c\#rd  
> 抓取时间: 2026/2/2 23:52:33

---

> 本期看点：Node.js 的最新主要版本已经发布。需要注意的是，目前它是 Current 发布版本，但预计将在今年十月成为 Node.js 的 LTS 发布版本。作为一个偶数版本，Node 22 将会持续维护很长时间，很可能一直到 2027 年左右。

> 编辑：Yucohny、loveloki、TimLi

🔥 本周热门

**Node.js 22.0（Current）发布** —— Node.js 的最新主要版本已经发布。需要注意的是，目前它是 Current 发布版本，但预计将在今年十月成为 Node.js 的 LTS 发布版本。作为一个偶数版本，Node 22 将会持续维护很长时间，很可能一直到 2027 年左右。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/v22-release-announce

那么 Node 22 有什么新特性呢？

- V8 的 Maglev 编译器 现已默认启用，为更短寿命的程序带来了性能提升。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/maglev
    

- V8 已更新至版本 v12.4，最新版本引入了 iterator helpers、Set 方法 和 Array.fromAsync。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-iterator-helpers
    

- 现在 `node` 支持运行 npm 脚本，例如 `node --run test`。

- `node --watch` 现已稳定。
    
    **长按识别二维码查看原文**
    
    https://www.jamesqquick.com/blog/using-node-watch-instead-of-nodemon/
    

- 之前试验性的集成 WebSocket 客户端现已默认启用。

- 开始 支持 require(esm)。
    
    **长按识别二维码查看原文**
    
    https://joyeecheung.github.io/blog/2024/03/18/require-esm-in-node-js/
    

**Node 22 开始原生支持 CJS/ESM 互操作性** —— 一个关于 Node 在处理 CommonJS 和 ECMAScript 模块时进入新时代的概述。

**长按识别二维码查看原文**

https://medium.com/gitconnected/native-support-for-cjs-esm-interoperability-begins-in-node-js-22-1da33368a628

Zachary Lee

**JSR 不是“又一个包管理器”** —— Node.js、npm 和 CommonJS 为 JavaScript 带来了一个包标准，而像 Yarn 或 pnpm 这样的工具则在这个过程中添加了自己的特色，Ryan 表示现在是进行转变的时候了。JSR 不是“一个新的 npm”，而是对包分发方式进行了重新设计，专为 ESM 时代而设计。

**长按识别二维码查看原文**

https://deno.com/blog/jsr-is-not-another-package-manager

Ryan Dahl

**你也许不需要** `**dotenv**`**：Node 现在本地支持** `**.env**` **文件加载** —— 这并不是一个全新的功能（自 Node v20.6.0 起就已经存在），但这是一个方便的提醒，如果你有基本的 `.env` 环境变量读取需求，你可以省去另一个依赖。

**长按识别二维码查看原文**

https://javascript.plainenglish.io/ditch-dotenv-node-js-now-natively-supports-env-file-loading-8b9b2d49b2d2?gi=ba98bf0c2b8d

Zachary Lee

**📄 像专业人士一样进行网络抓取：解锁模拟的威力**

**长按识别二维码查看原文**

https://lev.engineer/blog/web-scraping-like-a-pro-unlocking-the-power-of-impersonation

Lev Gelfenbuim

🛠 代码与工具

**📺 YouTube.js：一个非官方的 YouTube API 客户端库** —— ‘InnerTube’ 是 YouTube 使用的客户端 API，你也可以使用它（虽然他们可能不喜欢这样）。它可以运行在 Node.js、Deno 和 现代浏览器中。

**长按识别二维码查看原文**

https://github.com/LuanRT/YouTube.js

LuanRT

**get-windows：获取激活且打开的桌面客户端窗口的元数据** —— 获取标题、id、边界矩形大小位置等信息。支持 Windows 7+、macOS 10.14+ 以及 Linux（不支持 Wayland)。

**长按识别二维码查看原文**

https://github.com/sindresorhus/get-windows

Sindre Sorhus

**browser-or-node v3.0：识别代码运行环境** —— 提供一个简单的方式判断代码是运行于浏览器、Node、Web Worker 还是 Deno。支持 ESM 和 CJS。

**长按识别二维码查看原文**

https://www.npmjs.com/package/browser-or-node

Dinesh Pandiyan

**cron-schedule v5.0：Cron 解析器和调度程序** —— 在浏览器、Node 或 Deno 中解析和查询 cron 样式表达式。

**长按识别二维码查看原文**

https://github.com/P4sca1/cron-schedule

Pascal Sthamer

**Odiff：一种快速逐像素图像差异分析工具和库** —— Odiff 声称可以在毫秒级别提供结果。你可以通过 CLI 或 Node 使用 API 处理 PNG、JPG 和 BMP，同时支持跨文件比较。

**长按识别二维码查看原文**

https://github.com/dmtrKovalenko/odiff

Dmitriy Kovalenko

**rcompat** —— 用于服务器的 JS 互操作性和运行时兼容性层。

**长按识别二维码查看原文**

https://primatejs.com/blog/introducing-rcompat

Terrablue

**TsumiLink** —— 一个 Lava/NodeLink 兼容客户端。

**长按识别二维码查看原文**

https://github.com/Fyphen1223/TsumiLink

Fyphen

**x-crawl** —— 由人工智能辅助的网络爬虫库。

**长按识别二维码查看原文**

https://github.com/coder-hxl/x-crawl

CoderHXL

**版本发布：**

- **Knip v5.11.0** – 查询项目中未使用的文件、依赖和导出项，现在支持缓存和监听模式。

- **better-sqlite v9.6** – 一种巧妙的 SQLite v3.45.3 使用方式。

- **TestCafe v3.6** – 自动化的端到端网络测试框架。

- **exiftool-vendored v26.0** – 用于跨平台访问 ExifTool，管理多媒体文件中的元数据的工具。

- **JSPyBridge v1.2** – 从 Node 运行 Python，反之亦然。

- **Slonik v41.1** – 类型安全的 Postgres 客户端。

- **ws v8.17** – 快速的 WebSocket 库。

- **Pino v9.0** – 快速的 JSON 日志记录器。

🙋🏻‍♀️