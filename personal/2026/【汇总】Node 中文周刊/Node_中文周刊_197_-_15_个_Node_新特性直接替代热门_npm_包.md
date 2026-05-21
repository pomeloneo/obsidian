# Node 中文周刊 #197 - 15 个 Node 新特性直接替代热门 npm 包

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543993&idx=1&sn=42ca799c53b4c69710ca0f2ff234415b&chksm=e921675bde56ee4dd01ab1d8709faed07083e2f441a18a99043230da9bb0c5d52d47d3907319#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543993&idx=1&sn=42ca799c53b4c69710ca0f2ff234415b&chksm=e921675bde56ee4dd01ab1d8709faed07083e2f441a18a99043230da9bb0c5d52d47d3907319#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543993&idx=1&sn=42ca799c53b4c69710ca0f2ff234415b&chksm=e921675bde56ee4dd01ab1d8709faed07083e2f441a18a99043230da9bb0c5d52d47d3907319#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543993&idx=1&sn=42ca799c53b4c69710ca0f2ff234415b&chksm=e921675bde56ee4dd01ab1d8709faed07083e2f441a18a99043230da9bb0c5d52d47d3907319#rd)

---

> 本期看点：Node.js 运行时新增多个特性可替代常用第三方包减少依赖，npm 安全最佳实践，Buffer 优化技术让大文件处理性能提升 78%，ESLint v10.0 带来 JSX 引用追踪支持，pnpm 10.18 新增网络性能监控功能。

> 编辑：TimLi

🔥 本周热门

**15 个 Node 新特性，能直接替代热门 npm 包** —— 现在很多以前需要三方包才能实现的功能，Node 运行时本身就自带了。这里盘点了一些值得你尝试的新特性，或许能帮你减少不必要的依赖。

**长按识别二维码查看原文**

https://nodesource.com/blog/nodejs-features-replacing-npm-packages

Lizz Parody

**npm 安全最佳实践** —— Web 安全专家 Liran Tal 整理了一份 npm 生态下的安全最佳实践，无论你用不用官方的 `npm` 工具，这些建议都很实用，强烈推荐收藏。

**长按识别二维码查看原文**

https://github.com/lirantal/npm-security-best-practices

Liran Tal

**📉 用 Buffer 优化让 14GB 文件处理快了 78%** —— 作者出于好奇，挑战用 Node 处理近 15GB 的气象数据，结果周末一折腾，性能提升了 78%。不过，比数字更有意思的是他优化的过程和思路，值得一看。

**长按识别二维码查看原文**

https://pmbanugo.me/blog/nodejs-1brc

Peter Mbanugo

**Deno 如何防范 npm 漏洞** —— Deno 团队针对最近 npm 生态的安全事件，分享了 Deno 的“默认安全”模型是如何帮你规避风险的。Deno 的权限机制很严格，适合对安全有要求的场景。

**长按识别二维码查看原文**

https://deno.com/blog/deno-protects-npm-exploits

Andy Jiang (Deno)

**🧹 Nx Monorepo 大扫除：我如何安全移除 120 个无用依赖** —— Knip 又立功了！这是一个帮你找出项目里没用到的依赖的工具，作者用它把 Monorepo 里 120 个废弃依赖都清理掉了，项目瞬间清爽。

**长按识别二维码查看原文**

https://johnjames.blog/posts/cleaning-house-in-nx-monorepo-how-i-removed-120-unused-deps-safely

John James

**📄 [https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-2025](https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-2025) 年 Node.js 包发布趋势** —— 这是 Joyee Cheung 在 NordicJS 上的演讲 PPT，内容很扎实，讲了 Node.js 包未来的发布方式。等视频出来我们也会第一时间分享。

**长按识别二维码查看原文**

[https://github.com/joyeecheung/talks/blob/master/nordic_js_https://svelte.dev/blog/whats-new-in-svelte-october-2025/shipping-nodejs-packages-in-https://svelte.dev/blog/whats-new-in-svelte-october-2025.pdf](https://github.com/joyeecheung/talks/blob/master/nordic_js_https://svelte.dev/blog/whats-new-in-svelte-october-2025/shipping-nodejs-packages-in-https://svelte.dev/blog/whats-new-in-svelte-october-2025.pdf)

**📄 不用** `**reduce()**`**，如何优雅地分组数组** —— 介绍了 `Object.groupBy()` 和 `Map.groupBy()` 的用法，让数组分组变得更简单。

**长按识别二维码查看原文**

[https://allthingssmitty.com/https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/06/grouping-arrays-in-modern-javascript-object-groupby-and-map-groupby/](https://allthingssmitty.com/https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/06/grouping-arrays-in-modern-javascript-object-groupby-and-map-groupby/)

**📄 Eleventy/11ty 的趣味与性能小技巧** —— Eleventy 是一个很火的 Node 静态站点生成器，这里有一些提升性能和开发乐趣的小技巧。

**长按识别二维码查看原文**

[https://infrequently.org/https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/11ty-hacks-for-fun-and-performance/](https://infrequently.org/https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/11ty-hacks-for-fun-and-performance/)

**快讯：**

- Nicholas C. Zakas 带来了 ESLint v10.0 新特性预览，包括 Node.js 兼容性调整、一些移除和废弃项，以及 JSX 引用追踪的支持。
    
    **长按识别二维码查看原文**
    
    [https://eslint.org/blog/https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/whats-coming-in-eslint-10.0.0/](https://eslint.org/blog/https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/whats-coming-in-eslint-10.0.0/)
    

- pnpm 10.18 发布，新增了网络性能监控功能，能在请求变慢时提醒你。
    
    **长按识别二维码查看原文**
    
    https://pnpm.io/blog/releases/10.18
    

- Bun 1.3 今天就要发布了，不过我们发稿时还没上线。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/
    

🛠  代码与工具

**Javet v5.0：在 Java 里嵌入 Node.js 和 V8 的新方式** —— 你可以直接在 JVM 里用 Node 和 V8，虽然不同平台支持情况不一，但思路很有意思，文档也很详细。GitHub 仓库在这里。

**长按识别二维码查看原文**

https://www.caoccao.com/Javet/

Sam Cao

**Cap’n Web：面向浏览器和 Web 服务器的新 RPC 系统** —— 这是 Cap’n Proto 的“精神兄弟”，同一作者打造。Cap’n Web 的序列化格式更易读，专为 JS 运行时设计，支持 HTTP、WebSocket 和 `postMessage()`，开箱即用。

**长按识别二维码查看原文**

https://blog.cloudflare.com/capnweb-javascript-rpc-library/

Varda 和 Faulkner (Cloudflare)

- **.* Globby 15.0：更友好的 Glob 匹配工具** —— 你只要传一组 glob，它就能返回所有匹配路径，还支持否定和 `.gitignore` 文件，写脚本很方便。

**长按识别二维码查看原文**

https://github.com/sindresorhus/globby

Sindre Sorhus

**Icebird：用 JavaScript 读 Apache Iceberg 表** —— **Iceberg** 是一个高性能的大型分析表开源格式，这个库让你用 JS 直接读取 Iceberg 表。

**长按识别二维码查看原文**

https://github.com/hyparam/icebird

Hyperparam

**🖼️ Odiff v4.0：超快的图片像素级对比工具** —— 声称毫秒级出结果，可以作为 CLI 工具或在 Node 里用（主要用 OCaml 写的）。支持 PNG、JPG、BMP 格式，还能跨文件对比。

**长按识别二维码查看原文**

https://github.com/dmtrKovalenko/odiff

Dmitriy Kovalenko

📢  其他生态

这里是本周其他值得关注的动态：

- React 19.2 发布。
    
    **长按识别二维码查看原文**
    
    [https://react.dev/blog/https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/01/react-19-2](https://react.dev/blog/https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-2025/10/01/react-19-2)
    

- Svelte 项目、Astro 团队 和 void(0)（关注 Vite 相关项目） 都发布了月度动态。
    
    **长按识别二维码查看原文**
    
    [https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-2025](https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-https://svelte.dev/blog/whats-new-in-svelte-october-2025)
    

- 🤖 Google AI Studio 现在 可以直接生成 Angular 应用程序了。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/175282/web
    

- 重启的 **JSConf** 下周将在马里兰举办，门票还没卖完，输入 `JSCONF25NEWSLETTER` 还能打折。（友情提示：我们和活动方没金钱关系哈。）
    
    **长按识别二维码查看原文**
    
    https://events.linuxfoundation.org/jsconf-north-america/
    

- PostgreSQL 18 两周前发布，Tudor Golubenco 带你深入了解 Postgres 18 的新特性。
    
    **长按识别二维码查看原文**
    
    https://www.postgresql.org/about/news/postgresql-18-released-3142/
    

**版本发布：**

- **isomorphic-git v1.34** —— 纯 JS 实现的 `git`，支持 Node 和浏览器。

- **node-llama-cpp v3.14** —— 本地运行 LLM，绑定 `llama.cpp`。

- **pg-promise v12.2** —— Node 的 Postgres 接口，现在正式支持 Postgres 18。

- **BullMQ v5.61** —— 基于 Redis 的分布式队列，可靠性高。

- **node-mssql v12.0** —— Microsoft SQL Server 客户端。

- **node-soap v1.5** —— SOAP 客户端和服务端库。

- **Pino v10.0** —— Node 的高速 HTTP 日志库。

- **NodeBB v4.6** —— 基于 Node.js 的论坛系统。

- **ESLint v9.37.0**