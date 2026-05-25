---
name: meeting-insights-analyzer
description: 分析会议转录和录音，以发现行为模式、沟通洞察和可执行反馈。识别你何时回避冲突、使用 filler words、主导对话或错过倾听机会。非常适合希望提升沟通和领导力技能的 professionals。
---

# 会议洞察分析器

此技能会将你的会议转录转化为关于沟通模式的可执行洞察，帮助你成为更有效的沟通者和领导者。

## 何时使用此技能

- 分析多场会议中的沟通模式
- 获取关于 leadership 和 facilitation style 的反馈
- 识别何时回避困难对话
- 理解你的 speaking habits 和 filler words
- 随时间跟踪 communication skills 的提升
- 用具体示例准备 performance reviews
- 指导团队成员改善 communication style

## 此技能做什么

1. **模式识别**：识别会议中的重复行为，例如：
   - Conflict avoidance 或 indirect communication
   - Speaking ratios 和 turn-taking
   - Question-asking vs. statement-making patterns
   - Active listening indicators
   - Decision-making approaches

2. **沟通分析**：评估沟通有效性：
   - Clarity 和 directness
   - Filler words 和 hedging language 的使用
   - Tone 和 sentiment patterns
   - Meeting control 和 facilitation

3. **可执行反馈**：提供具体、带 timestamp 的示例，包含：
   - 发生了什么
   - 为什么重要
   - 如何改进

4. **趋势跟踪**：分析多场会议时比较随时间变化的模式

## 如何使用

### 基础设置

1. 将会议转录下载到一个文件夹（例如 `~/meetings/`）
2. 在 Codex 中导航到该文件夹
3. 请求你想要的分析

### 快速开始示例

```
Analyze all meetings in this folder and tell me when I avoided conflict.
```

```
Look at my meetings from the past month and identify my communication patterns.
```

```
Compare my facilitation style between these two meeting folders.
```

### 高级分析

```
Analyze all transcripts in this folder and:
1. Identify when I interrupted others
2. Calculate my speaking ratio
3. Find moments I avoided giving direct feedback
4. Track my use of filler words
5. Show examples of good active listening
```

## 指令

当用户请求 meeting analysis 时：

1. **发现可用数据**
   - 扫描文件夹中的 transcript files（.txt、.md、.vtt、.srt、.docx）
   - 检查文件是否包含 speaker labels 和 timestamps
   - 确认会议日期范围
   - 识别转录中的用户姓名/标识符

2. **澄清分析目标**
   
   如果未指定，询问他们想了解什么：
   - 特定行为（conflict avoidance、interruptions、filler words）
   - 沟通有效性（clarity、directness、listening）
   - Meeting facilitation skills
   - Speaking patterns 和 ratios
   - 需要改进的 growth areas
   
3. **分析模式**

   对每个请求的 insight：
   
   **Conflict Avoidance**：
   - 查找 hedging language（"maybe", "kind of", "I think"）
   - 用间接措辞代替直接请求
   - 紧张出现时改变话题
   - 没有承诺地表示同意（"yeah, but..."）
   - 没有处理明显问题
   
   **Speaking Ratios**：
   - 计算会议中发言时间占比
   - 统计 interruptions（用户打断他人和被他人打断）
   - 测量平均 speaking turn length
   - 跟踪 question vs. statement ratios
   
   **Filler Words**：
   - 统计 "um", "uh", "like", "you know", "actually" 等
   - 记录每分钟或每个 speaking turn 的频率
   - 识别它们增加的情境（nervous、uncertain）
   
   **Active Listening**：
   - 引用他人前面观点的问题
   - 复述或总结他人的想法
   - 在他人贡献基础上延展
   - 提出澄清问题
   
   **Leadership & Facilitation**：
   - Decision-making approach（directive vs. collaborative）
   - 如何处理 disagreements
   - 是否纳入较少发言的参与者
   - Time management 和 agenda control
   - Follow-up 和 action item clarity

4. **提供具体示例**

   对每个发现的模式，包含：
   
   ```markdown
   ### [Pattern Name]
   
   **Finding**: [One-sentence summary of the pattern]
   
   **Frequency**: [X times across Y meetings]
   
   **Examples**:
   
   1. **[Meeting Name/Date]** - [Timestamp]
      
      **What Happened**:
      > [Actual quote from transcript]
      
      **Why This Matters**:
      [Explanation of the impact or missed opportunity]
      
      **Better Approach**:
      [Specific alternative phrasing or behavior]
   
   [Repeat for 2-3 strongest examples]
   ```

5. **综合洞察**

   分析所有模式后，提供：
   
   ```markdown
   # Meeting Insights Summary
   
   **Analysis Period**: [Date range]
   **Meetings Analyzed**: [X meetings]
   **Total Duration**: [X hours]
   
   ## Key Patterns Identified
   
   ### 1. [Primary Pattern]
   - **Observed**: [What you saw]
   - **Impact**: [Why it matters]
   - **Recommendation**: [How to improve]
   
   ### 2. [Second Pattern]
   [Same structure]
   
   ## Communication Strengths
   
   1. [Strength 1 with example]
   2. [Strength 2 with example]
   3. [Strength 3 with example]
   
   ## Growth Opportunities
   
   1. **[Area 1]**: [Specific, actionable advice]
   2. **[Area 2]**: [Specific, actionable advice]
   3. **[Area 3]**: [Specific, actionable advice]
   
   ## Speaking Statistics
   
   - Average speaking time: [X% of meeting]
   - Questions asked: [X per meeting average]
   - Filler words: [X per minute]
   - Interruptions: [X given / Y received per meeting]
   
   ## Next Steps
   
   [3-5 concrete actions to improve communication]
   ```

6. **提供后续选项**
   - 在未来会议中跟踪相同 metrics
   - 深入分析特定 meetings 或 patterns
   - 与 industry benchmarks 比较
   - 创建个人 communication development plan
   - 生成用于 performance reviews 的摘要

## 示例

### 示例 1：Conflict Avoidance Analysis（受 Dan Shipper 启发）

**User**: "I download all of my meeting recordings and put them in a folder. Tell me all the times I've subtly avoided conflict."

**Output**: 
```markdown
# Conflict Avoidance Patterns

Found 23 instances across 15 meetings where you used indirect 
communication or avoided addressing tensions directly.

## Pattern: Hedging on Critical Feedback

**Frequency**: 8 times across 7 meetings

**Example 1: 1:1 with Sarah** - 00:14:32

**What Happened**:
> "So, I was thinking... maybe we could, like, potentially 
> consider looking at the timeline again? I mean, if you 
> think that makes sense. But whatever you think is best!"

**Why This Matters**:
You needed to address that Sarah's project was behind schedule, 
but the hedging language ("maybe", "potentially", "if you think") 
and the deflection at the end ("whatever you think") made it easy 
for her to miss the urgency.

**Better Approach**:
"Sarah, the project is two weeks behind schedule. We need to 
discuss what's blocking progress and create a new timeline 
today."

[Additional examples...]

## Recommendations

1. **Name the issue directly** in the first sentence
2. **Remove hedging words** like "maybe," "kind of," "sort of"
3. **Ask specific questions** instead of hinting
4. **Schedule difficult conversations** instead of raising them casually
```

### 示例 2：Leadership Facilitation

**User**: "Analyze my team meetings and tell me about my facilitation style."

**Output**: 提供以下洞察：
- 你与团队成员的发言比例（60% vs. 40%）
- 你是提问还是陈述（3:1 ratio）
- 你如何处理 disagreements（倾向于过快解决）
- 谁发言最少，以及你是否引导他们参与
- 良好和错过的 facilitation moments 示例

### 示例 3：Personal Development Tracking

**User**: "Compare my meetings from Q1 vs. Q2 to see if I've improved my listening skills."

**Output**: 创建对比分析，展示：
- Interruptions 减少（8 per meeting → 3 per meeting）
- Clarifying questions 增加（2 → 7 per meeting）
- 在他人想法基础上延展的能力提升
- 展示差异的具体示例
- 剩余 growth areas

## 设置技巧

### 获取会议转录

**From Granola**（订阅 Lenny's newsletter 可免费使用）：
- Granola 会自动转录你的会议
- 将 transcripts 导出到文件夹：[Instructions on how]
- 将 Codex 指向该文件夹

**From Zoom**：
- 启用带 transcription 的 cloud recording
- 会后下载 VTT 或 SRT 文件
- 存放在专用文件夹中

**From Google Meet**：
- 使用 Google Docs auto-transcription
- 将 transcript docs 保存到文件夹
- 下载为 .txt 文件或授予 Codex 访问权限

**From Fireflies.ai, Otter.ai, etc.**：
- 批量导出 transcripts
- 存放在本地文件夹
- 对该文件夹运行分析

### 最佳实践

1. **Consistent naming**：使用 `YYYY-MM-DD - Meeting Name.txt` 格式
2. **Regular analysis**：每月或每季度回顾趋势
3. **Specific queries**：一次询问一个行为，以获得深度分析
4. **Privacy**：将敏感会议数据保留在本地
5. **Action-oriented**：一次聚焦一个改进领域

## 常见分析请求

- "When do I avoid difficult conversations?"
- "How often do I interrupt others?"
- "What's my speaking vs. listening ratio?"
- "Do I ask good questions?"
- "How do I handle disagreement?"
- "Am I inclusive of all voices?"
- "Do I use too many filler words?"
- "How clear are my action items?"
- "Do I stay on agenda or get sidetracked?"
- "How has my communication changed over time?"

## 相关使用场景

- 从 insights 创建个人 development plan
- 用示例准备 performance review materials
- 指导 direct reports 改善沟通
- 分析 customer calls 中的 sales 或 support patterns
- 研究 negotiation tactics 和 outcomes
