像 [Claude Code](https://www.anthropic.com/claude-code) 这样的智能体编码工具帮助开发者加速工作流、自动化重复任务和处理复杂编程项目。随着领域的发展，我们每天都从用户（包括我们自己的员工）那里了解到新的应用场景。

我们与 Anthropic 各团队的员工交流，了解他们如何在工作中使用 Claude Code。

虽然许多用例是可预见的——调试、导航代码库、管理工作流——但也有一些令人惊讶。律师构建了电话树系统。营销人员在几秒钟内生成了数百个广告变体。数据科学家在不了解 JavaScript 的情况下创建了复杂的可视化。

模式变得清晰：**智能体编码不仅仅是加速传统开发。它正在消解技术和非技术工作之间的界限，将任何能描述问题的人变成能构建解决方案的人。**

## 代码库导航和理解

公司各团队使用 Claude Code 帮助新员工甚至资深员工快速熟悉代码库。

基础设施团队的数据科学家将整个代码库提供给 Claude Code 以快速上手。Claude 读取代码库的 [CLAUDE.md](http://CLAUDE.md) 文件，识别相关文件，解释数据管道依赖关系，并显示哪些上游源为仪表板提供数据。

产品工程团队将 Claude Code 称为任何编程任务的"第一站"。他们让它识别需要检查哪些文件来修复 Bug、开发功能或进行分析。

## 测试和代码审查

产品设计团队使用 Claude Code 为新功能编写全面的测试。他们通过 GitHub Actions 自动化了 PR 评论，Claude 自动处理格式问题和测试用例重构。

安全工程团队将工作流从"设计文档 → 粗糙代码 → 重构 → 放弃测试"转变为让 Claude 提供伪代码，引导它进行测试驱动开发，并定期检查。结果是更可靠、可测试的代码。

推理团队在需要测试不熟悉语言（如 Rust）的功能时，解释想测试什么，Claude 用代码库的原生语言编写逻辑。

## 调试和故障排除

在事件期间，安全工程团队向 Claude Code 提供堆栈跟踪和文档来追踪代码库中的控制流。通常需要 10-15 分钟手动扫描的问题现在**快 3 倍**解决。

产品工程团队获得了在不熟悉代码库中处理 Bug 的信心。他们问 Claude："你能修复这个 Bug 吗？这是我看到的行为"，然后审查建议的解决方案，无需依赖其他工程团队。

数据基础设施团队用 Claude Code 诊断 Kubernetes 集群停止调度 Pod 的问题。他们提供仪表板截图，Claude 逐步引导他们在 Google Cloud UI 中找到 Pod IP 地址耗尽的问题，并提供了创建新 IP 池的精确命令。

## 原型设计和功能开发

产品设计团队将 Figma 设计文件提供给 Claude Code，然后设置自主循环——Claude Code 编写代码、运行测试、持续迭代。他们给 Claude 抽象问题，让它自主工作，然后在最终细化前审查解决方案。

产品设计团队发现了一个意想不到的用途：映射错误状态、逻辑流和系统状态，在设计阶段而非开发阶段识别边缘情况。这从根本上提高了初始设计质量。

数据科学家尽管不精通 TypeScript，也使用 Claude Code 构建完整的 React 应用来可视化 RL 模型性能。

## 文档和知识管理

推理团队中没有 ML 背景的成员依靠 Claude 解释模型特定功能。通常需要一小时 Google 搜索的工作现在只需 10-20 分钟——**研究时间减少 80%**。

安全工程团队让 Claude 消化多个文档源，创建 Markdown 运行手册和故障排除指南。

## 自动化和工作流优化

增长营销团队构建了一个智能体工作流，处理包含数百个广告的 CSV 文件，识别表现不佳的广告，并在严格字符限制内生成新变体。使用两个专门的子智能体，系统在几分钟内而非几小时内生成数百个新广告。

他们还开发了一个 Figma 插件，识别画框并程序化地生成多达 100 个广告变体，将数小时的复制粘贴**缩短到每批广告半秒钟**。

法律团队创建了原型"电话树"系统，帮助团队成员联系到 Anthropic 的合适律师——展示了部门如何在没有传统开发资源的情况下构建自定义工具。

## 使用 Claude Code 解锁新可能

这些故事揭示了一个模式：Claude Code 在你专注于它可以增强的人类工作流时效果最好。最成功的团队将 Claude Code 视为思考伙伴而非代码生成器。他们探索可能性、快速原型设计，并在技术和非技术用户之间分享发现。

---

## 📄 原文（Original English）

How **Anthropic teams use Claude Code** across the company — from predictable dev workflows to surprising non-technical applications.

**Codebase navigation**: New hires get productive quickly. Claude reads [CLAUDE.md](http://CLAUDE.md) files, explains dependencies, identifies relevant files. Product Engineering's "first stop" for any task.

**Testing & code review**: Automated PR comments via GitHub Actions. Test-driven development guidance. Cross-language test translation (e.g., to Rust).

**Debugging**: 3x faster incident resolution via stack trace analysis. Kubernetes diagnosis from dashboard screenshots. Confidence to tackle unfamiliar codebases.

**Prototyping**: Autonomous code-test-iterate loops from Figma designs. Edge case identification during design phase. Full React apps built by non-TypeScript data scientists.

**Documentation**: 80% reduction in research time. Markdown runbooks from multiple doc sources.

**Automation**: Marketing workflows generating hundreds of ad variants in minutes. Figma plugin for 100 ad variations in 0.5 seconds. Legal team built phone tree systems.

**Key insight**: Agentic coding dissolves the boundary between technical and non-technical work.