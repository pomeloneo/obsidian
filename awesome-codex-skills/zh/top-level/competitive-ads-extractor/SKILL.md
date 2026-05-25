---
name: competitive-ads-extractor
description: 从 ad libraries（Facebook、LinkedIn 等）提取并分析竞争对手广告，理解哪些 messaging、problems 和 creative approaches 正在奏效。帮助启发并改进你自己的 ad campaigns。
---

# Competitive Ads Extractor

此 skill 会从 ad libraries 中提取竞争对手广告，并分析哪些内容有效——他们强调的问题、瞄准的 use cases，以及正在产生共鸣的 copy/creative。

## 何时使用此 Skill

- 研究竞争对手广告策略
- 为自己的广告寻找灵感
- 理解市场定位
- 识别成功的广告模式
- 分析有效的 messaging
- 发现新的 use cases 或 pain points
- 使用经过验证的 concepts 规划 ad campaigns

## 此 Skill 会做什么

1. **提取 Ads**：从 Facebook Ad Library、LinkedIn 等抓取广告
2. **捕获 Screenshots**：保存所有广告的视觉副本
3. **分析 Messaging**：识别 problems、use cases 和 value props
4. **归类 Ads**：按主题、受众或格式分组
5. **识别 Patterns**：找出常见的成功方法
6. **提供 Insights**：解释某些广告可能表现良好的原因

## 如何使用

### 基本提取

```
Extract all current ads from [Competitor Name] on Facebook Ad Library
```

```
Scrape ads from [Company] and analyze their messaging
```

### 特定分析

```
Get all ads from [Competitor] focusing on their messaging 
about [specific problem]. What pain points are they highlighting?
```

### Competitive Set

```
Extract ads from these 5 competitors: [list]. 
Compare their approaches and tell me what's working.
```

### 特定平台

```
Get LinkedIn ads from [Competitor] and analyze their 
B2B positioning strategy
```

## 示例

**用户**："Extract ads from Notion on Facebook Ad Library and tell me what messaging is working for them."

**流程**：
```
Accessing Facebook Ad Library...
Searching for: Notion
Found: 23 active ads

Extracting screenshots...
[████████████████████] 100%

Saved to: competitor-ads/notion/
- ad-001-collaboration.png
- ad-002-productivity.png
- ad-003-templates.png
...

Analyzing messaging...
```

**输出**：
```
# Notion Ad Analysis

## Overview
- Total Ads: 23 active
- Primary Themes: Productivity (35%), Collaboration (30%), 
  Templates (20%), AI Features (15%)
- Ad Formats: Static images (60%), Video (40%)
- CTA Patterns: "Try for free", "Get started"

## Key Problems They're Highlighting

1. **Scattered Information** (8 ads)
   Copy: "Stop switching between 10 different tools"
   Why it works: Direct pain point many teams face

2. **Meeting Overload** (5 ads)
   Copy: "Replace unnecessary meetings with async updates"
   Why it works: Post-COVID remote work pain point

3. **Lost Documentation** (4 ads)
   Copy: "Never ask 'where is that doc?' again"
   Why it works: Universal workplace frustration

## Successful Creative Patterns

### Pattern 1: Before/After Split
- Shows chaotic tool landscape → Clean Notion workspace
- Used in 6 high-performing ads
- Visual metaphor is immediately clear

### Pattern 2: Feature Showcase
- GIF of actual product usage
- Shows specific feature in 5 seconds
- Used for new features (AI, templates)

### Pattern 3: Social Proof
- "Join 20M users" messaging
- Customer logos
- Used in 4 ads targeting enterprise

## Copy That's Working

Best Headlines:
1. "Your team's knowledge, finally in one place"
   → Benefit-focused, addresses pain directly
   
2. "The all-in-one workspace"
   → Clear positioning, broad appeal
   
3. "AI that actually helps you work"
   → Addresses AI skepticism, practical angle

Best Body Copy Patterns:
- Short sentences (under 10 words)
- Focus on outcomes not features
- Include specific numbers ("Cut meetings by 50%")

## Audience Targeting Insights

Based on ad variations:
- Startup founders: Solo productivity angle
- Team leads: Collaboration and alignment
- Enterprise: Security and compliance mentions
- Students: Free plan, templates, organization

## Recommendations for Your Ads

1. **Test the "tool sprawl" pain point**
   → Strong resonance based on their ad frequency

2. **Use product screenshots over abstract visuals**
   → All their top ads show actual UI

3. **Lead with the problem, not the solution**
   → "Tired of X?" performs better than "Introducing Y"

4. **Keep copy under 100 characters**
   → Their shortest ads seem most frequent

5. **Test before/after visual formats**
   → Proven pattern in their creative

## Files Saved
- All ads: ~/competitor-ads/notion/
- Analysis: ~/competitor-ads/notion/analysis.md
- Best performers: ~/competitor-ads/notion/top-10/
```

**灵感来源：** Sumant Subrahmanya 在 Lenny's Newsletter 中的 use case

## 你能学到什么

### Messaging Analysis
- 他们强调哪些问题
- 他们如何相对于竞争对手定位
- 能产生共鸣的 value propositions
- 目标受众细分

### Creative Patterns
- 有效的视觉风格
- Video vs. static image performance
- 配色方案和 branding
- Layout patterns

### Copy Formulas
- Headline structures
- Call-to-action patterns
- 长度和语气
- 情绪触发点

### Campaign Strategy
- Seasonal campaigns
- Product launch approaches
- Feature announcement tactics
- Retargeting patterns

## 最佳实践

### 法律与伦理
✓ 只用于研究和灵感
✓ 不要直接复制广告
✓ 尊重 intellectual property
✓ 使用 insights 来指导原创 creative
✗ 不要 plagiarize copy 或 steal designs

### 分析提示
1. **寻找 patterns**：哪些主题反复出现？
2. **长期追踪**：每月保存广告，观察演变
3. **测试 hypotheses**：为你的品牌适配成功模式
4. **按受众分组**：不同目标使用不同 messages
5. **比较平台**：LinkedIn 与 Facebook 的 messaging 不同

## 高级功能

### Trend Tracking
```
Compare [Competitor]'s ads from Q1 vs Q2. 
What messaging has changed?
```

### Multi-Competitor Analysis
```
Extract ads from [Company A], [Company B], [Company C]. 
What are the common patterns? Where do they differ?
```

### Industry Benchmarks
```
Show me ad patterns across the top 10 project management 
tools. What problems do they all focus on?
```

### Format Analysis
```
Analyze video ads vs static image ads from [Competitor]. 
Which gets more engagement? (if data available)
```

## 常见工作流

### Ad Campaign Planning
1. 提取竞争对手广告
2. 识别成功 patterns
3. 记录他们 messaging 中的 gaps
4. Brainstorm 独特 angles
5. 起草 test ad variations

### Positioning Research
1. 获取 5 个竞争对手的广告
2. 映射他们的 positioning
3. 找到未被充分服务的 angles
4. 发展差异化 messaging
5. 与他们的方法对照测试

### Creative Inspiration
1. 按主题提取广告
2. 分析视觉 patterns
3. 记录 color 和 layout trends
4. 适配成功 patterns
5. 创建原创 variations

## 成功提示

1. **Regular Monitoring**：每月检查变化
2. **Broad Research**：也查看相邻竞争对手
3. **Save Everything**：建立 reference library
4. **Test Insights**：运行你自己的 experiments
5. **Track Performance**：A/B test 受启发的 concepts
6. **Stay Original**：用于灵感，而非复制
7. **Multiple Platforms**：比较 Facebook、LinkedIn、TikTok 等

## 输出格式

- **Screenshots**：所有广告保存为 images
- **Analysis Report**：insights 的 Markdown summary
- **Spreadsheet**：包含 ad copy、CTAs、themes 的 CSV
- **Presentation**：top performers 的 visual deck
- **Pattern Library**：按 approach 分类

## 相关 Use Cases

- 为你的 campaigns 写出更好的 ad copy
- 理解市场定位
- 找到 messaging 中的 content gaps
- 发现产品的新 use cases
- 规划 product marketing strategy
- 激发 social media content 灵感
