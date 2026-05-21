# Node 中文周刊 #36 - Node.js v18 (Current) 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247505202&idx=1&sn=b91e613bfddeb6334cada45f70fc3c04&chksm=e9219ed0de5617c60c621cb64923eeedc134a858dfbb7f1aecdb5d82bcd129190a5a49bc38ba\#rd  
> 抓取时间: 2026/2/2 23:54:37

---

> 本期看点：Node.js v18 (Current) 发布，包含可添加 test runner 模块等新功能！

> 编辑：辛宝、Yucohny

## 🔥 本周热门

**Node.js v18 (Current) 发布** — 在 Node v16 发布一年、Node v14 发布两年后，Node 的最新版到来了。现在发布的是 `current`（最新尝鲜版）分支，在今年 10 月份它将成为 `LTS`（长期维护）版本，该版本将支持到 2025 年。来看看有什么新功能吧：

**长按识别二维码查看原文**

https://nodeweekly.com/link/122584/web

- 作为最新的 `current` 版本，在 2022 年 10 月（开始稳定）前，Node v18 会一直做新功能的升级。

- 提供由 **Undici** 驱动的 `Fetch API`，目前默认全局可用。是时候拥抱 `fetch`、`Request`，以及 `Response` 等全新全局 API 了。

- **Web Streams API** 现在全局暴露，`Blob` 和 `BroadcastChannel` 也是如此。

- 现在可以在 `node:test` 中引入 **test runner 模块**。

- 如果你喜欢更全的清单，Beth Griggs 写的 **官方发布公告** 也值得一看。

The Node.js Team

**2022 年最流行的 Node.js 框架** — 作者根据问卷调查、Github Star 数量和主观感受得出的数据结论，整理了一份文章清单。这篇清单在当下很有参考价值，对比了不同领域的框架，包含后端、全栈，以及 CMS 网站等功能。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122590/web

Alex Ivanovs

**避免使用 `npm link` 的四个原因** — `npm link` 可以通过 symlink 的方式，在开发期间把本地的包作为项目的依赖项。作者创建了一个叫 `link` 的包，你可以通过 `npx link` 的方式使用。这个包是一个更安全、可预测的方式来替代，文章中有进一步的解释。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122591/web

Hiroki Osame

▶  **通过 ClojureScript 和 `nbb` 编写 Node 应用** — 如果你认为 Node 是一个运行时而不是必须基于 JS 的东西，这个标题是有意义的。视频中使用 **nbb** 开发一个基于 Node 的 ClojureScript 脚本环境。另外，两个程序员在镜头下合作是一件相当酷的事情。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122596/web

On The Code Again

**如何使用多个工具来调试 Node.js 代码** — 这是一份方便又高水平的调试指南。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122609/web

Craig Buckler

**快讯**

- OpenJS Foundation 发布了一篇更聚焦商业战略的文章：**关于 Node.js v18 发布**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/122592/web
    

- `JS Party` 最新一期播客：▶️ **采访 Postgres.js 作者：Rasmus Porsager**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/122593/web
    

## 🛠 代码与工具

**chalk-animation：在终端中输出绚丽动效** — 为你的文本输出提供了一系列的不同展示风格，包含彩虹效果、脉冲和突变效果。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122599/web

Boris K

**WebDAV v4.9：基于 TS 的 WebDAV 客户端** — **WebDAV** 是一个历史悠久的标准，可以使用 HTTP 在服务端编辑、移动，以及变更文件。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122600/web

Perry Mitchell

**Gladys Assistant：开源的隐私优先家庭助理** — 该项目基于 Node 开发，可以在任何 Linux 机器上运行（包括树莓派）。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122603/web

Pierre-Gilles Leymarie

**node-sqlite3 v5.0.4：异步 SQLite3 绑定** — 这是一个单点发布，添加了用于 Linux 中 musl 和 arm64 版本的预构建二进制文件。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122604/web

Ghost

**zx v6.1：利用 Node 编写更易用的 Shell 脚本的工具**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122605/web

Google

**Google Auth Library v8.0**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122606/web

Google APIs

**Mineflayer v4.3：创建 Minecraft 机器人的封装 API**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122607/web

PrismarineJS

**Gaxios v5.0：基于** `**node-fetch**` **封装工具，提供 Axios 风格类型接口**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122608/web

Google

## 🙋🏻‍♀️