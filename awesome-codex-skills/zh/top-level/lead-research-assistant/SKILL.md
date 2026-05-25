---
name: lead-research-assistant
description: 通过分析你的业务、搜索目标公司并提供可执行的联系策略，为你的产品或服务识别高质量 leads。非常适合 sales、business development 和 marketing professionals。
---

# 线索研究助手

此技能通过分析你的产品/服务、理解你的理想客户画像，并提供可执行的 outreach strategies，帮助你识别和筛选潜在 leads。

## 何时使用此技能

- 为你的产品/服务寻找潜在 customers 或 clients
- 构建用于 partnership outreach 的公司列表
- 为 sales outreach 识别 target accounts
- 研究符合 ideal customer profile 的公司
- 准备 business development 活动

## 此技能做什么

1. **理解你的业务**：分析你的产品/服务、value proposition 和 target market
2. **识别目标公司**：基于以下因素找到符合 ideal customer profile 的公司：
   - Industry 和 sector
   - Company size 和 location
   - Technology stack 及其使用的 tools
   - Growth stage 和 funding
   - 你的产品解决的 pain points
3. **优先排序 Leads**：根据 fit score 和 relevance 对公司排序
4. **提供联系策略**：建议如何用个性化信息接触每个 lead
5. **丰富数据**：收集有关 decision-makers 和 company context 的相关信息

## 如何使用

### 基本用法

只需描述你的产品/服务以及你要找什么：

```
I'm building [product description]. Find me 10 companies in [location/industry] 
that would be good leads for this.
```

### 结合你的代码库

为了获得更好的结果，可以在你的产品源代码目录中运行：

```
Look at what I'm building in this repository and identify the top 10 companies 
in [location/industry] that would benefit from this product.
```

### 高级用法

进行更有针对性的研究：

```
My product: [description]
Ideal customer profile:
- Industry: [industry]
- Company size: [size range]
- Location: [location]
- Current pain points: [pain points]
- Technologies they use: [tech stack]

Find me 20 qualified leads with contact strategies for each.
```

## 指令

当用户请求 lead research 时：

1. **理解产品/服务**
   - 如果在代码目录中，分析 codebase 以理解产品
   - 询问有关 value proposition 的澄清问题
   - 识别关键 features 和 benefits
   - 理解它解决了哪些问题

2. **定义 Ideal Customer Profile**
   - 确定目标 industries 和 sectors
   - 识别 company size ranges
   - 考虑 geographic preferences
   - 理解相关 pain points
   - 记录任何 technology requirements

3. **研究并识别 Leads**
   - 搜索符合条件的公司
   - 寻找需求信号（job postings、tech stack、recent news）
   - 考虑增长指标（funding、expansion、hiring）
   - 识别拥有互补 products/services 的公司
   - 检查 budget indicators

4. **优先级排序和评分**
   - 为每个 lead 创建 fit score（1-10）
   - 考虑以下因素：
     - 与 ICP 的匹配度
     - 即时需求信号
     - Budget availability
     - Competitive landscape
     - Timing indicators

5. **提供可执行输出**
   
   对每个 lead，提供：
   - **Company Name** 和 website
   - **Why They're a Good Fit**：基于其业务的具体理由
   - **Priority Score**：1-10，并附解释
   - **Decision Maker**：要触达的 role/title（例如 "VP of Engineering"）
   - **Contact Strategy**：个性化接触建议
   - **Value Proposition**：你的产品如何解决其具体问题
   - **Conversation Starters**：outreach 中可提及的具体要点
   - **LinkedIn URL**：如果可用，便于连接

6. **格式化输出**

   用清晰、易扫读的格式呈现结果：

   ```markdown
   # Lead Research Results
   
   ## Summary
   - Total leads found: [X]
   - High priority (8-10): [X]
   - Medium priority (5-7): [X]
   - Average fit score: [X]
   
   ---
   
   ## Lead 1: [Company Name]
   
   **Website**: [URL]
   **Priority Score**: [X/10]
   **Industry**: [Industry]
   **Size**: [Employee count/revenue range]
   
   **Why They're a Good Fit**:
   [2-3 specific reasons based on their business]
   
   **Target Decision Maker**: [Role/Title]
   **LinkedIn**: [URL if available]
   
   **Value Proposition for Them**:
   [Specific benefit for this company]
   
   **Outreach Strategy**:
   [Personalized approach - mention specific pain points, recent company news, or relevant context]
   
   **Conversation Starters**:
   - [Specific point 1]
   - [Specific point 2]
   
   ---
   
   [Repeat for each lead]
   ```

7. **提供下一步**
   - 建议将结果保存为 CSV，便于 CRM import
   - 提议起草个性化 outreach messages
   - 建议基于 timing 做优先级排序
   - 建议对 top leads 做 follow-up research 以获得更深 insights

## 示例

### 示例 1：来自 Lenny's Newsletter

**User**: "I'm building a tool that masks sensitive data in AI coding assistant queries. Find potential leads."

**Output**: 创建一个优先级排序后的公司列表，这些公司：
- 使用 AI coding assistants（Copilot、Cursor 等）
- 处理 sensitive data（fintech、healthcare、legal）
- 在其 GitHub repos 中有使用 coding agents 的证据
- 可能曾在代码中意外暴露 sensitive data
- 包含相关 decision-makers 的 LinkedIn URLs

### 示例 2：本地业务

**User**: "I run a consulting practice for remote team productivity. Find me 10 companies in the Bay Area that recently went remote."

**Output**: 识别以下公司：
- 最近发布 remote job listings
- 宣布 remote-first policies
- 正在招聘 distributed teams
- 显示出 remote work challenges 的迹象
- 为每家公司提供个性化 outreach strategies

## 获得最佳结果的技巧

- **具体说明**你的产品及其 unique value
- 如果适用，**从你的 codebase 运行**以获得自动上下文
- **提供 context** 说明你的 ideal customer profile
- **指定 constraints**，例如 industry、location 或 company size
- **请求 follow-up**，对有前景的 leads 做更深入研究

## 相关使用场景

- 识别 leads 后起草个性化 outreach emails
- 构建 CRM-ready CSV 的 qualified prospects
- 详细研究特定公司
- 分析 competitor customer bases
- 识别 partnership opportunities
