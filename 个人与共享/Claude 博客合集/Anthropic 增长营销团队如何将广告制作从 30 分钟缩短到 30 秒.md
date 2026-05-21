在使用 Claude Code 之前，Austin Lau 一生中从未写过一行代码。当产品首次推出时，他不得不在 Google 上搜索如何在电脑上打开终端。

"我对 Claude Code 的第一反应是，我完全不知道这个产品是干什么的，"Anthropic 的增长营销人员 Austin 说。"作为营销人员，用例对我来说并不明显。"

但好奇心赢了。

一位 Anthropic 同事在公司 Slack 中发布了一份非技术员工安装 Claude Code 的指南。Austin 决定按照指引操作。

一周后，Austin 构建了两个从根本上改变了工作方式的工作流：一个 Figma 插件（一键生成广告创意变体）和一个 Google Ads 文案工作流（帮助头脑风暴和精炼广告文案，然后导出为可上传的 CSV 文件）。**原来每个广告需要 30 分钟，现在只需 30 秒。**

## 问题：淹没在文案和创意变体中

大规模运营效果营销需要持续产出新鲜创意。仅 Google 响应式搜索广告就需要 15 个独特标题。每隔几周，文案就需要刷新——同时保持品牌调性和传达价值主张。

旧流程是：打开 Google Sheets → 头脑风暴标题和描述 → 手动检查字符数 → 复制粘贴到 Google Ads → 重复。

对于视觉广告，过程更加复杂。Austin 需要在 Figma 中复制现有画框、切换到 Google Doc 获取标题文案、切换回 Figma 粘贴——跨十个以上变体和多种宽高比。

## 解决方案：两个消除营销繁忙工作的工作流

### Figma 插件用于创意变体

Austin 用 Claude Code 构建了一个 Figma 插件，花了约 45 分钟到 1 小时构建，但现在每次更新大批量跨多种宽高比的创意时节省近 30 分钟。

[![](https://www.notion.so)](https://www.notion.so)

_Austin 的插件让他只需粘贴标题文案，一键生成数十个广告变体。_

"我只需要指定创意的画框，然后复制粘贴一次所有不同的变体和文案，点击按钮，Figma 插件就会为该单一图像创建所有不同的排列组合。"

### Google Ads 文案生成

对于响应式搜索广告，Austin 构建了一个工作流，帮助头脑风暴和创建可上传的广告文案。他输入 `/rsa`（自定义斜杠命令），Claude Code 请求活动数据、现有文案和关键词，然后交叉引用 Anthropic 品牌调性、产品准确性和 Google Ads RSA 最佳实践的 Agent Skills。

[![](https://www.notion.so)](https://www.notion.so)

_工作流将相关活动和广告组列、15 个标题和 4 个描述导出为可直接上传到 Google Ads 的 CSV 文件。_

## 构建自己工作流的最佳实践

**从小型、重复的步骤开始**。"想想工作中哪些领域是重复的或你认为可以自动化的，从一个非常小且简单的事情开始。"

**让好奇心驱动工作**。Austin 将自己描述为"如果对某事非常好奇，会执着到必须找到答案的人。"

**像向同事解释问题一样与 Claude 交谈**。"你不需要知道如何编码。你只需要知道如何清晰简洁地解释你的挑战和你想解决的问题。"

**基于已有资源构建**。Austin 将 Claude Code 指向现有的 Figma API 文档，Claude 自行研究并构建了原型。

## 更大的图景

"几年前，如果你有构建这样工作流的想法，你可能需要一个工程师团队来支持。现在，使用 Claude Code，作为非技术营销人员，我实际上可以自己构建这些东西。所以'我希望这个存在'和'我实际上可以自己构建这个'之间的差距比人们意识到的要小得多。"

Anthropic 其他营销团队也在用 Claude 取得类似成果：

- **网红营销**：使用 Claude 为网红和播客撰写脚本，每月释放 100+ 小时

- **客户营销**：30 分钟而非 2.5 小时起草案例研究，每周节省 10 小时

- **数字营销**：构建 Web 开发工作流，团队生产力同比提升 5 倍

- **产品营销**：使用 Skills 和 Projects 创建发布简报，每次发布节省 5-10 小时

- **合作伙伴营销**：构建销售自助展会支持，展会准备时间减少 40%

_立即开始使用 [Claude Code](https://www.anthropic.com/claude-code)。_

---

## 📄 原文（Original English）

How Anthropic growth marketer **Austin Lau** — with zero coding experience — used Claude Code to **cut ad creation from 30 minutes to 30 seconds**.

**Two workflows built**: (1) Figma plugin generating ad creative variations with one click across multiple aspect ratios. (2) Google Ads RSA copy workflow with custom `/rsa` slash command, cross-referencing brand Skills, exporting upload-ready CSVs.

**Best practices**: Start with small repetitive tasks, let curiosity drive, talk to Claude like a colleague, build on existing resources (API docs, etc.).

**Broader Anthropic marketing impact**: Influencer (100+ hrs/month saved), Customer Marketing (case studies in 30 min vs 2.5 hrs), Digital (5x productivity YoY), Product Marketing (5-10 hrs saved per launch), Partner Marketing (40% less trade show prep time).