# Node 中文周刊 #211 - Node.js 25.5.0 发布，单文件可执行程序构建体验提升

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545848&idx=1&sn=9767ebe2505e3114ad15de4e9f3b826e&chksm=e921781ade56f10cfedce13ee72add03b8ca26237b9e15b6c241f48bb47ec26d0e4275820dd6#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545848&idx=1&sn=9767ebe2505e3114ad15de4e9f3b826e&chksm=e921781ade56f10cfedce13ee72add03b8ca26237b9e15b6c241f48bb47ec26d0e4275820dd6#rd): [https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga//2/2](https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga//2/2) 23:50:59

---

> 本期看点：Node.js 25.5.0 发布并带来 –build-sea 单文件可执行程序构建，Rafael Gonzaga 聊 [https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/](https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/) 年的 Node.js，Node.js 16~25 逐版本性能对比，Vercel、Netlify、Cloudflare 三大 Serverless 冷启动对比。

> 编辑：TimLi

🔥 本周热门

**Node 单文件可执行程序构建体验提升** —— 两年前，Node 推出了一个还在实验阶段的新特性，就是能打包生成单个可执行程序，即使目标机器没装 Node 也能直接跑。本周 Node.js 25.5 发布，带来了 `--build-sea` 新参数，把最后关键的注入步骤直接做到 Node 里，无需额外工具，以前需要手动分多步操作，现在一条命令就能搞定。

**长按识别二维码查看原文**

[https://joyeecheung.github.io/blog/https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga//01/26/improving-single-executable-application-building-for-node-js/](https://joyeecheung.github.io/blog/https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga//01/26/improving-single-executable-application-building-for-node-js/)

Joyee Cheung

**Node.js 25.5.0（当前版）发布** —— 本次的重磅特性就是新加入的 `--build-sea` 命令行参数（见上文）。同时，`node:sqlite` 现在默认开启了 defensive mode，能更好保护数据安全；`fs.watch` 新增了 ignore 选项，方便你过滤掉不关心的文件变化事件。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.5.0

Antoine du Hamel

📊 **Node.js 16~25 逐版本性能对比** —— 对比不同版本的性能变化很有意思，某些任务在 Node 25 时直接起飞，其他部分则是稳步提升。

**长按识别二维码查看原文**

https://www.repoflow.io/blog/node-js-16-to-25-benchmarks-how-performance-evolved-over-time

RepoFlow

- **Rafael Gonzaga 聊 [https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/](https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/) 年的 Node.js** —— Node.js TSC 成员 Rafael 深入聊了运行时内部、V8 性能优化、基准测试常见误区、以及哪些“看似简单”的优化其实不能直接上线，否则会影响生态。

**长按识别二维码查看原文**

[https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/](https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/)

Software Engineering Daily 播客

🔒 **Node 的 OpenSSL 安全通报解读** —— OpenSSL 最近发布了一份安全公告，总共涵盖 12 个 CVE。Node.js 团队判定其中有 3 个跟 Node 相关，但受影响面有限，计划在常规版本中修复，不用特别紧急。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/vulnerability/openssl-fixes-in-regular-releases-jan2026](https://nodejs.org/en/blog/vulnerability/openssl-fixes-in-regular-releases-jan2026)

The Node.js Team

📄 **Node.js 各主流 Redis/Valkey 客户端性能大比拼** —— **“我基准测试了所有主流 Node.js 的 Redis 客户端……看看还要不要继续用 ioredis，还是迁移更有优势……”** Frank Fiegel

**长按识别二维码查看原文**

[https://glama.ai/blog/https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-01-26-redis-vs-ioredis-vs-valkey-glide](https://glama.ai/blog/https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-https://softwareengineeringdaily.com/https://openjsf.org/blog/openjs-security-annual-report-2025/12/23/node-js-in-2026-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-with-rafael-gonzaga/-01-26-redis-vs-ioredis-vs-valkey-glide)

📄 **让 GitHub Actions 没那么糟，自动重试方案** —— 用个超简单的自动重试 workflow，就能帮你绕过那些随机失败的小毛病。Jonathan Milgrom

**长按识别二维码查看原文**

https://softwarefordays.com/post/github-actions-auto-retry/

📄 **Vercel、Netlify、Cloudflare 三大 Serverless 冷启动对比** Punit Sethi

**长按识别二维码查看原文**

https://punits.dev/blog/vercel-netlify-cloudflare-serverless-cold-starts/

**快讯：**

- NodeSource 推荐你立即运行一次 `npx is-my-node-vulnerable`，这是官方背书的一个小工具，可以检测你的 Node.js 安装是否有已知安全问题。

- 别再傻傻地用原生 npm script 了，试试 `nr` —— 这个用 Rust 写的零开销 npm script 执行器，据说能帮你省下 2ms 到 260ms。
    
    **长按识别二维码查看原文**
    
    https://github.com/dawsbot/nr
    

- Reddit 的 `/r/node` 上出现了一个超火讨论：如果你现在重新开始做项目，还会选 Express 吗？ 下面有评论表示，**“我甚至不会选 Node。”** 这回答有点狠啊！
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/node/comments/1qkipnn/if_youre_starting_fresh_today_would_you_still/
    

- 🔒 OpenJS 基金会刚发了年度安全报告，介绍他们在保障 Node.js 及其它 OpenJS 项目的安全方面都做了哪些努力。
    
    **长按识别二维码查看原文**
    
    [https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025](https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-https://openjsf.org/blog/openjs-security-annual-report-2025)
    

- 想测下自己的打字速度？直接 `npx typex-cli` 秒测！

🛠 代码和工具

**LibPDF：TypeScript 下的 PDF 解析和生成库** —— LibPDF 号称 **“TypeScript 应得的 PDF 库”**，支持解析、修改、签名、生成 PDF，API 设计非常现代，Node、Bun 和浏览器都能直接用。GitHub 仓库在这。

**长按识别二维码查看原文**

https://documenso.com/blog/introducing-libpdf-the-pdf-library-typescript-deserves

Documenso

🤖 **用 GitHub Copilot SDK 把智能 agent 集成到任何应用程序里** —— GitHub 官方发布了一个 SDK，让你可以直接在 Node 应用程序调用 Copilot 的 “agentic core” 和工作流。

**长按识别二维码查看原文**

https://github.blog/news-insights/company-news/build-an-agent-into-any-app-with-the-github-copilot-sdk/

Mario Rodriguez (GitHub)

📋 **clipboardy：系统剪贴板读写 API** —— 一套统一的接口让你可以跨平台（包括 Windows、macOS、Linux 等）读写系统剪贴板。

**长按识别二维码查看原文**

https://github.com/sindresorhus/clipboardy

Sindre Sorhus

**network-default-gateway：查找默认网关工具** —— 一行代码查出你当前网络设备连接的默认网关，Node、Deno、Bun 都能用，兼容 Linux、macOS、Windows。

**长按识别二维码查看原文**

https://github.com/lucafornerone/network-default-gateway

Luca Fornerone

📢 生态系统其他有趣的故事

盘点下最近 JavaScript 圈的一些趣事：

- Bun 最近连发了两个更新：Bun v1.3.7 升级了 JavaScriptCore，`async`/`await` 性能提升高达 35%，ARM64 跑得更快，还原生支持 JSON5 和 JSONL 解析。Bun v1.3.8 则内置了 Markdown 解析。顺便放个科普，▶️ 100 秒看懂 Bun。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-v1.3.7
    

- Christopher Chedeau 分享了他如何用 Claude Code 把 10 万行 TypeScript 代码迁移到 Rust，里面讲了不少用 agentic 工具炮制大型迁移任务的心得。
    
    **长按识别二维码查看原文**
    
    https://blog.vjeux.com/2026/analysis/porting-100k-lines-from-typescript-to-rust-using-claude-code-in-a-month.html
    

- 一年前 Node.js: The Documentary 上线，如果你还没看过，这片还是挺有意思的。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=LB8KwiiUGy0
    

- 一个月造一个全新 JavaScript 运行时的故事。
    
    **长按识别二维码查看原文**
    
    https://themackabu.dev/blog/js-in-one-month
    

**版本发布：**

- **Lodash v4.17.23** —— 虽然是个看起来很小的更新，但是修复了一个重要安全漏洞，OpenJS 专门发了篇博文。

- **github-webhook-handler v2.1** —— 接收和验证 GitHub webhook 请求用的中间件，适合你的仓库自动化需求。

- **CMake.js v8.0.0** —— 构建 Node 原生插件的新工具，感觉有点像 node-gyp，但是底层技术换成了 CMake。

-  **create-dmg v8.0** —— 用来给 macOS 应用程序快速生成 DMG 安装包，颜值还很高。

- **FoalTS 5.2** —— TypeScript 的 Node.js Web 框架新版本。（官网点这）

- **Neutralinojs v6.5.0**

- **Emscripten v5.0**

- **pnpm v10.28.2**

- **npm v11.8.0**