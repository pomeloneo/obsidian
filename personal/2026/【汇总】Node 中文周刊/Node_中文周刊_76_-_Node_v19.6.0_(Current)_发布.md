# Node 中文周刊 #76 - Node v19.6.0 (Current) 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515895&idx=1&sn=0ba8c81513529053ebb300f42b70fd02&chksm=e921f515de567c039c619ee9a97ce16ba9c06fce0eab9be31c9d4834899673a2b05fc1e1cd22\#rd  
> 抓取时间: 2026/2/2 23:53:45

---

> 本期看点：Node v19 已升级到 npm v9.4。通过使用 `--install-strategy=linked` 可以实现类似 pnpm 的隔离模式，以及可以使用实验特性的 loader hooks。Node v18.14.0 (LTS) 也已发布，并且对 npm v9.3 进行了重大升级。

> 编辑：Yucohny、Otto-J

## 🔥 本周热门

**Node v19.6.0 (Current) 发布** — Node v19 已升级到 npm v9.4。通过使用 `--install-strategy=linked` 可以实现类似 pnpm 的 **隔离模式**，以及可以使用实验特性的 **loader hooks**。**Node v18.14.0 (LTS)** 也已发布，并且对 npm v9.3 进行了重大升级。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.6.0/

Node.js Project

**Ada v1.0：Node 即将推出的新 URL 解析器** — Ada 是 Node.js 生态中推出更新、更快的 URL 解析器。Ada 已经通过了完整的 WHATWG 和 Node 测试套件，但是在使用初期仍然可能出现一些问题。

**长按识别二维码查看原文**

https://github.com/ada-url/ada/releases/tag/v1.0.0

Ada Authors

**Node 中的 Puppeteer：避免常见错误** — **Puppeteer** 是一个功能强大的库，提供基于 Chromium 浏览器实现自动化功能，但有各种陷阱可能会让您陷入困境。这篇文章指出了一些常见错误。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/02/08/puppeteer-in-nodejs-common-mistakes-to-avoid.html

Greg Gorlen

**在 GitHub Actions 中使用 Playwright**。

**长按识别二维码查看原文**

https://radekmie.dev/blog/on-playwright-in-github-actions/

Radosław Miernik

**你应该在 Postgres 中使用** `**char**`**、**`**varchar**` **还是** `**text**`**？**

**长按识别二维码查看原文**

https://maximorlov.com/char-varchar-text-postgresql/

Maxim Orlov

**快讯：**

- ❤️ 准备好接受来自 Node.js 核心团队的情人节礼物：所有处于维护状态的发行版本将会进行 **预期安全发布**。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/february-2023-security-releases/
    

- **Lambda Cold Starts** 是一个简洁的页面，现场演示了不同的 _AWS Lambda_ 无服务器运行时的启动速度。考虑 Node 在 _Lambda_ 上的成熟地位，它的表现竟然出奇地差？
    
    **长按识别二维码查看原文**
    
    https://maxday.github.io/lambda-perf/
    

## 🛠 代码与工具

**Electron v23.0 发布** — 流行的跨平台 JavaScript、HTML + CSS 桌面应用程序框架已经升级到 Node v18.12.1、Chromium v110 和 V8 v11.0。同时，不再支持 Windows 7/8/8.1，因此可能很快会开始看到这些版本的 Windows 失去许多基于 Electron 的应用程序的支持。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-23-0

Electron Core Team

**resvg-js v2.4：高性能 SVG 渲染器与工具包** — resvg 由 Rust 在后端驱动，可以通过 WebAssembly 在 Node 与浏览器中工作，这里有 **现场演示** 将 SVG 转换为 PNG，同时具有高水平的 SVG 规范支持。**此版本** 拥有比以前“快 2-3 倍的性能”。

**长按识别二维码查看原文**

https://github.com/yisibl/resvg-js

Miscellaneous

**版本发布：**

- **ics v3.0**
    
    ↳ iCalendar (ICS) 文件生成器。
    

- **lowdb v5.1**
    
    ↳ 简单易用的本地 JSON 数据库。
    

- **RxDB v14.0**
    
    ↳ 适用于 JS 应用程序的离线优先反应式数据库。
    

- **AVA v5.2**
    
    ↳ 流行的 Node.js 测试运行器。
    

- **better-sqlite3 v8.1**
    
    ↳ 一个非常好的 SQLite3 库。
    

- **Pino v8.10**
    
    ↳ 面向 JSON 的快速记录器。
    

- **exiftool-vendored.js v21.0**
    
    ↳ 跨平台访问 **ExifTool**。
    

- **pg-boss v8.4**
    
    ↳ 基于 Postgres 的 Node.js 作业队列。
    

- **pnpm v7.27**
    
    ↳ 高效的包管理器。
    

## 🙋🏻‍♀️