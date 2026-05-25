---
name: developer-growth-analysis
description: 分析你最近的 Codex chat history，识别 coding patterns、development gaps 和可改进领域，从 HackerNews 策划相关学习资源，并自动向你的 Slack DMs 发送个性化成长报告。
---

# Developer Growth Analysis

此 skill 会分析你的 Codex chat interactions，识别能揭示优势与成长空间的模式，从而对你最近的 coding work 提供个性化反馈。

## 何时使用此 Skill

当你想要：
- 从近期工作中理解自己的 development patterns 和 habits
- 识别具体的技术差距或反复出现的挑战
- 发现哪些主题值得更深入学习
- 获取根据你实际工作模式定制的学习资源
- 跟踪近期 projects 中的改进领域
- 找到直接对应你正在发展技能的高质量文章

此 skill 适合希望在不等待 code reviews 的情况下获得结构化成长反馈，并偏好从自身工作历史中获得 data-driven insights 的 developers。

## 此 Skill 做什么

此 skill 会对你的开发工作执行六步分析：

1. **读取你的 Chat History**：访问过去 24-48 小时的本地 Codex chat history，了解你一直在做什么。

2. **识别 Development Patterns**：分析你解决的问题类型、使用的 technologies、遇到的 challenges，以及处理不同任务的方式。

3. **检测改进领域**：识别暗示 skill gaps、反复卡住、低效方法，或你可能受益于更深入知识的模式。

4. **生成个性化报告**：创建综合报告，展示你的 work summary、识别出的 improvement areas，以及具体成长建议。

5. **寻找学习资源**：使用 HackerNews 策划与你改进领域直接相关的高质量文章和讨论，提供一份根据你实际 development work 定制的阅读清单。

6. **发送到你的 Slack DMs**：自动把完整报告发送到你自己的 Slack direct messages，方便你随时随地引用。

## 如何使用

让 Codex 分析你最近的 coding work：

```
Analyze my developer growth from my recent chats
```

或者更具体地说明时间范围：

```
Analyze my work from today and suggest areas for improvement
```

此 skill 会生成格式化报告，包含：
- 近期工作的概览
- 识别出的关键改进领域
- 每个领域的具体建议
- 来自 HackerNews 的精选学习资源
- 你可以关注的 action items

## 指令

当用户请求分析其 developer growth 或 recent work 中的 coding patterns 时：

1. **访问 Chat History**

   从 `$CODEX_HOME/history.jsonl` 读取 chat history（默认 `~/.codex/history.jsonl`）。该文件为 JSONL 格式，每一行包含：
   - `display`：用户的 message/request
   - `project`：正在处理的 project
   - `timestamp`：Unix timestamp（毫秒）
   - `pastedContents`：粘贴的任何 code 或 content

   根据当前 timestamp 过滤过去 24-48 小时的 entries。

2. **分析工作模式**

   从过滤后的 chats 中提取并分析：
   - **Projects and Domains**：用户在处理哪些类型的 projects？（例如 backend、frontend、DevOps、data 等）
   - **Technologies Used**：对话中出现了哪些 languages、frameworks 和 tools？
   - **Problem Types**：正在解决哪些类别的问题？（例如 performance optimization、debugging、feature implementation、refactoring、setup/configuration）
   - **Challenges Encountered**：用户在哪些问题上卡住了？寻找：
     - 对相似主题的重复提问
     - 需要多次尝试才解决的问题
     - 暗示 knowledge gaps 的问题
     - 复杂的 architectural decisions
   - **Approach Patterns**：用户如何解决问题？（例如 methodical、exploratory、experimental）

3. **识别改进领域**

   基于分析，识别 3-5 个用户可以改进的具体领域。这些领域应该：
   - **具体**（不要像 “improve coding skills” 这样模糊）
   - **基于证据**（扎根于实际 chat history）
   - **可行动**（能够实际改进）
   - **有优先级**（最有影响的排在前面）

   好的改进领域示例：
   - "Advanced TypeScript patterns (generics, utility types, type guards) - you struggled with type safety in [specific project]"
   - "Error handling and validation - I noticed you patched several bugs related to missing null checks"
   - "Async/await patterns - your recent work shows some race conditions and timing issues"
   - "Database query optimization - you rewrote the same query multiple times"

4. **生成报告**

   使用此结构创建综合报告：

   ```markdown
   # Your Developer Growth Report

   **Report Period**: [Yesterday / Today / [Custom Date Range]]
   **Last Updated**: [Current Date and Time]

   ## Work Summary

   [2-3 paragraphs summarizing what the user worked on, projects touched, technologies used, and overall focus areas]

   Example:
   "Over the past 24 hours, you focused primarily on backend development with three distinct projects. Your work involved TypeScript, React, and deployment infrastructure. You tackled a mix of feature implementation, debugging, and architectural decisions, with a particular focus on API design and database optimization."

   ## Improvement Areas (Prioritized)

   ### 1. [Area Name]

   **Why This Matters**: [Explanation of why this skill is important for the user's work]

   **What I Observed**: [Specific evidence from chat history showing this gap]

   **Recommendation**: [Concrete step(s) to improve in this area]

   **Time to Skill Up**: [Brief estimate of effort required]

   ---

   [Repeat for 2-4 additional areas]

   ## Strengths Observed

   [2-3 bullet points highlighting things you're doing well - things to continue doing]

   ## Action Items

   Priority order:
   1. [Action item derived from highest priority improvement area]
   2. [Action item from next area]
   3. [Action item from next area]

   ## Learning Resources

   [Will be populated in next step]
   ```

5. **搜索学习资源**

   使用 Rube MCP 在 HackerNews 中搜索与每个改进领域相关的文章：

   - 对每个改进领域，构造面向高质量资源的 search query
   - 使用 RUBE_SEARCH_TOOLS 在 HackerNews 中搜索，例如：
     - "Learn [Technology/Pattern] best practices"
     - "[Technology] advanced patterns and techniques"
     - "Debugging [specific problem type] in [language]"
   - 优先选择高 engagement（comments、upvotes）的 posts
   - 对每个领域，包含 2-3 篇最相关的文章，并提供：
     - Article title
     - Publication date
     - 简短说明它为什么相关
     - 文章链接

   将此 section 添加到报告：

   ```markdown
   ## Curated Learning Resources

   ### For: [Improvement Area]

   1. **[Article Title]** - [Date]
      [Description of what it covers and why it's relevant to your improvement area]
      [Link]

   2. **[Article Title]** - [Date]
      [Description]
      [Link]

   [Repeat for other improvement areas]
   ```

6. **呈现完整报告**

   用干净、易读的格式交付报告，方便用户：
   - 快速浏览 key takeaways
   - 用于 focused learning planning
   - 在接下来一周处理改进时引用
   - 如需外部反馈，可分享给 mentors

7. **将报告发送到 Slack DMs**

   使用 Rube MCP 将完整报告发送到用户自己的 Slack DMs：

   - 通过 RUBE_SEARCH_TOOLS 检查 Slack connection 是否 active
   - 如果未连接，使用 RUBE_MANAGE_CONNECTIONS 发起 Slack auth
   - 使用 RUBE_MULTI_EXECUTE_TOOL 将报告作为格式化消息发送：
     - 第一条消息发送 report title 和 period
     - 将报告拆分为逻辑 sections（Summary、Improvements、Strengths、Actions、Resources）
     - 使用合适的 markdown 将每个 section 格式化为结构清晰的 Slack message
     - 为学习资源包含 clickable links
   - 在 CLI output 中确认 delivery

   这能确保用户在常看的地方收到报告，并能在一周内随时引用。

## 示例用法

### 输入

```
Analyze my developer growth from my recent chats
```

### 输出

```markdown
# Your Developer Growth Report

**Report Period**: November 9-10, 2024
**Last Updated**: November 10, 2024, 9:15 PM UTC

## Work Summary

Over the past two days, you focused on backend infrastructure and API development. Your primary project was an open-source showcase application, where you made significant progress on connections management, UI improvements, and deployment configuration. You worked with TypeScript, React, and Node.js, tackling challenges ranging from data security to responsive design. Your work shows a balance between implementing features and addressing technical debt.

## Improvement Areas (Prioritized)

### 1. Advanced TypeScript Patterns and Type Safety

**Why This Matters**: TypeScript is central to your work, but leveraging its advanced features (generics, utility types, conditional types, type guards) can significantly improve code reliability and reduce runtime errors. Better type safety catches bugs at compile time rather than in production.

**What I Observed**: In your recent chats, you were working with connection data structures and struggled a few times with typing auth configurations properly. You also had to iterate on union types for different connection states. There's an opportunity to use discriminated unions and type guards more effectively.

**Recommendation**: Study TypeScript's advanced type system, particularly utility types (Omit, Pick, Record), conditional types, and discriminated unions. Apply these patterns to your connection configuration handling and auth state management.

**Time to Skill Up**: 5-8 hours of focused learning and practice

### 2. Secure Data Handling and Information Hiding in UI

**Why This Matters**: You identified and fixed a security concern where sensitive connection data was being displayed in your console. Preventing information leakage is critical for applications handling user credentials and API keys. Good practices here prevent security incidents and user trust violations.

**What I Observed**: You caught that your "Your Apps" page was showing full connection data including auth configs. This shows good security instincts, and the next step is building this into your default thinking when handling sensitive information.

**Recommendation**: Review security best practices for handling sensitive data in frontend applications. Create reusable patterns for filtering/masking sensitive information before displaying it. Consider implementing a secure data layer that explicitly whitelist what can be shown in the UI.

**Time to Skill Up**: 3-4 hours

### 3. Component Architecture and Responsive UI Patterns

**Why This Matters**: You're designing UIs that need to work across different screen sizes and user interactions. Strong component architecture makes it easier to build complex UIs without bugs and improves maintainability.

**What I Observed**: You worked on the "Marketplace" UI (formerly Browse Tools), recreating it from a design image. You also identified and fixed scrolling issues where content was overflowing containers. There's an opportunity to strengthen your understanding of layout containment and responsive design patterns.

**Recommendation**: Study React component composition patterns and CSS layout best practices (especially flexbox and grid). Focus on container queries and responsive patterns that prevent overflow issues. Look into component composition libraries and design system approaches.

**Time to Skill Up**: 6-10 hours (depending on depth)

## Strengths Observed

- **Security Awareness**: You proactively identified data leakage issues before they became problems
- **Iterative Refinement**: You worked through UI requirements methodically, asking clarifying questions and improving designs
- **Full-Stack Capability**: You comfortably work across backend APIs, frontend UI, and deployment concerns
- **Problem-Solving Approach**: You break down complex tasks into manageable steps

## Action Items

Priority order:
1. Spend 1-2 hours learning TypeScript utility types and discriminated unions; apply to your connection data structures
2. Document security patterns for your project (what data is safe to display, filtering/masking functions)
3. Study one article on advanced React patterns and apply one pattern to your current UI work
4. Set up a code review checklist focused on type safety and data security for future PRs

## Curated Learning Resources

### For: Advanced TypeScript Patterns

1. **TypeScript's Advanced Types: Generics, Utility Types, and Conditional Types** - HackerNews, October 2024
   Deep dive into TypeScript's type system with practical examples and real-world applications. Covers discriminated unions, type guards, and patterns for ensuring compile-time safety in complex applications.
   [Link to discussion]

2. **Building Type-Safe APIs in TypeScript** - HackerNews, September 2024
   Practical guide to designing APIs with TypeScript that catch errors early. Particularly relevant for your connection configuration work.
   [Link to discussion]

### For: Secure Data Handling in Frontend

1. **Preventing Information Leakage in Web Applications** - HackerNews, August 2024
   Comprehensive guide to data security in frontend applications, including filtering sensitive information, secure logging, and audit trails.
   [Link to discussion]

2. **OAuth and API Key Management Best Practices** - HackerNews, July 2024
   How to safely handle authentication tokens and API keys in applications, with examples for different frameworks.
   [Link to discussion]

### For: Component Architecture and Responsive Design

1. **Advanced React Patterns: Composition Over Configuration** - HackerNews
   Explores component composition strategies that scale, with examples using modern React patterns.
   [Link to discussion]

2. **CSS Layout Mastery: Flexbox, Grid, and Container Queries** - HackerNews, October 2024
   Learn responsive design patterns that prevent overflow issues and work across all screen sizes.
   [Link to discussion]
```

## 提示和最佳实践

- 每周运行一次此分析，以跟踪你的改进轨迹
- 一次选择一个改进领域，专注几天后再转向下一个
- 将学习资源当作 study guide；阅读推荐材料并练习应用其中 patterns
- 专注某个领域一周后重新查看报告，观察你的工作模式如何变化
- 学习资源会根据你的实际工作专门策划，而不是泛泛的主题，因此会与你正在构建的内容高度相关

## 如何维护准确性和质量

此 skill：
- 从带 timestamp 的 chat history 分析你的实际工作模式
- 生成扎根于真实 projects 的 evidence-based recommendations
- 策划直接对应已识别 gaps 的学习资源
- 专注于 actionable improvements，而不是模糊反馈
- 根据复杂度提供具体时间估算
- 优先关注对 development velocity 影响最大的领域
