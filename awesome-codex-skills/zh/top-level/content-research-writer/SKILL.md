---
name: content-research-writer
description: 通过开展 research、添加 citations、改进 hooks、迭代 outlines，并对每个 section 提供实时 feedback，协助撰写高质量内容。把你的写作过程从单人努力转变为协作伙伴关系。
---

# Content Research Writer

此 skill 充当你的写作伙伴，帮助你 research、outline、draft 和 refine 内容，同时保持你独特的 voice 和 style。

## 何时使用此 Skill

- 撰写 blog posts、articles 或 newsletters
- 创建教育内容或 tutorials
- 起草 thought leadership pieces
- 研究并撰写 case studies
- 编写带 sources 的 technical documentation
- 使用恰当 citations 和 references 写作
- 改进 hooks 和 introductions
- 写作过程中逐 section 获取 feedback

## 此 Skill 会做什么

1. **协作式 Outlining**：帮助你将想法组织成 coherent outlines
2. **Research Assistance**：查找相关信息并添加 citations
3. **Hook Improvement**：强化开头以抓住注意力
4. **Section Feedback**：在你写作时审阅每个 section
5. **Voice Preservation**：保持你的写作风格和语气
6. **Citation Management**：正确添加并格式化 references
7. **Iterative Refinement**：通过多轮 drafts 帮助你改进

## 如何使用

### 设置你的写作环境

为你的文章创建专用文件夹：
```
mkdir ~/writing/my-article-title
cd ~/writing/my-article-title
```

创建你的 draft 文件：
```
touch article-draft.md
```

从此目录打开 Codex 并开始写作。

### 基本工作流

1. **从 outline 开始**：
```
Help me create an outline for an article about [topic]
```

2. **Research 并添加 citations**：
```
Research [specific topic] and add citations to my outline
```

3. **改进 hook**：
```
Here's my introduction. Help me make the hook more compelling.
```

4. **获取 section feedback**：
```
I just finished the "Why This Matters" section. Review it and give feedback.
```

5. **Refine 和 polish**：
```
Review the full draft for flow, clarity, and consistency.
```

## 说明

当用户请求写作协助时：

1. **理解写作项目**
   
   提出澄清问题：
   - 主题和核心论点是什么？
   - 目标受众是谁？
   - 期望长度/格式是什么？
   - 你的目标是什么？（educate、persuade、entertain、explain）
   - 是否有现有 research 或 sources 需要纳入？
   - 你的写作风格是什么？（formal、conversational、technical）

2. **协作式 Outlining**
   
   帮助组织内容：
   
   ```markdown
   # Article Outline: [Title]
   
   ## Hook
   - [Opening line/story/statistic]
   - [Why reader should care]
   
   ## Introduction
   - Context and background
   - Problem statement
   - What this article covers
   
   ## Main Sections
   
   ### Section 1: [Title]
   - Key point A
   - Key point B
   - Example/evidence
   - [Research needed: specific topic]
   
   ### Section 2: [Title]
   - Key point C
   - Key point D
   - Data/citation needed
   
   ### Section 3: [Title]
   - Key point E
   - Counter-arguments
   - Resolution
   
   ## Conclusion
   - Summary of main points
   - Call to action
   - Final thought
   
   ## Research To-Do
   - [ ] Find data on [topic]
   - [ ] Get examples of [concept]
   - [ ] Source citation for [claim]
   ```
   
   **迭代 outline**：
   - 根据 feedback 调整
   - 确保逻辑流清晰
   - 识别 research gaps
   - 标记需要 deep dives 的 sections

3. **开展 Research**
   
   当用户请求对某个 topic 进行 research 时：
   
   - 搜索相关信息
   - 找到可信 sources
   - 提取 key facts、quotes 和 data
   - 按请求的格式添加 citations
   
   示例输出：
   ```markdown
   ## Research: AI Impact on Productivity
   
   Key Findings:
   
   1. **Productivity Gains**: Studies show 40% time savings for 
      content creation tasks [1]
   
   2. **Adoption Rates**: 67% of knowledge workers use AI tools 
      weekly [2]
   
   3. **Expert Quote**: "AI augments rather than replaces human 
      creativity" - Dr. Jane Smith, MIT [3]
   
   Citations:
   [1] McKinsey Global Institute. (2024). "The Economic Potential 
       of Generative AI"
   [2] Stack Overflow Developer Survey (2024)
   [3] Smith, J. (2024). MIT Technology Review interview
   
   Added to outline under Section 2.
   ```

4. **改进 Hooks**
   
   当用户分享 introduction 时，分析并强化：
   
   **当前 Hook 分析**：
   - 有效之处：[positive elements]
   - 可以更强的地方：[areas for improvement]
   - 情绪影响：[current vs. potential]
   
   **建议替代方案**：
   
   Option 1：[大胆陈述]
   > [Example]
   *为什么有效：[explanation]*
   
   Option 2：[个人故事]
   > [Example]
   *为什么有效：[explanation]*
   
   Option 3：[惊人数据]
   > [Example]
   *为什么有效：[explanation]*
   
   **Hook questions**：
   - 它是否制造好奇？
   - 它是否承诺价值？
   - 它是否足够具体？
   - 它是否匹配受众？

5. **逐 Section 提供 Feedback**
   
   当用户写每个 section 时，从以下方面审阅：
   
   ```markdown
   # Feedback: [Section Name]
   
   ## What Works Well ✓
   - [Strength 1]
   - [Strength 2]
   - [Strength 3]
   
   ## Suggestions for Improvement
   
   ### Clarity
   - [Specific issue] → [Suggested fix]
   - [Complex sentence] → [Simpler alternative]
   
   ### Flow
   - [Transition issue] → [Better connection]
   - [Paragraph order] → [Suggested reordering]
   
   ### Evidence
   - [Claim needing support] → [Add citation or example]
   - [Generic statement] → [Make more specific]
   
   ### Style
   - [Tone inconsistency] → [Match your voice better]
   - [Word choice] → [Stronger alternative]
   
   ## Specific Line Edits
   
   Original:
   > [Exact quote from draft]
   
   Suggested:
   > [Improved version]
   
   Why: [Explanation]
   
   ## Questions to Consider
   - [Thought-provoking question 1]
   - [Thought-provoking question 2]
   
   Ready to move to next section!
   ```

6. **保留作者 Voice**
   
   重要原则：
   
   - **学习他们的 style**：阅读现有 writing samples
   - **建议，而不是替换**：提供 options，而不是 directives
   - **匹配 tone**：formal、casual、technical、friendly
   - **尊重选择**：如果他们更喜欢自己的版本，支持它
   - **增强，而不是覆盖**：让他们的写作更好，而不是变成另一种写法
   
   定期询问：
   - “这听起来像你吗？”
   - “这个 tone 合适吗？”
   - “我应该更/不那么 [formal/casual/technical] 吗？”

7. **Citation Management**
   
   根据用户偏好处理 references：
   
   **Inline Citations**：
   ```markdown
   Studies show 40% productivity improvement (McKinsey, 2024).
   ```
   
   **Numbered References**：
   ```markdown
   Studies show 40% productivity improvement [1].
   
   [1] McKinsey Global Institute. (2024)...
   ```
   
   **Footnote Style**：
   ```markdown
   Studies show 40% productivity improvement^1
   
   ^1: McKinsey Global Institute. (2024)...
   ```
   
   维护一个持续更新的 citations list：
   ```markdown
   ## References
   
   1. Author. (Year). "Title". Publication.
   2. Author. (Year). "Title". Publication.
   ...
   ```

8. **最终审阅和 Polish**
   
   当 draft 完成时，提供全面 feedback：
   
   ```markdown
   # Full Draft Review
   
   ## Overall Assessment
   
   **Strengths**:
   - [Major strength 1]
   - [Major strength 2]
   - [Major strength 3]
   
   **Impact**: [Overall effectiveness assessment]
   
   ## Structure & Flow
   - [Comments on organization]
   - [Transition quality]
   - [Pacing assessment]
   
   ## Content Quality
   - [Argument strength]
   - [Evidence sufficiency]
   - [Example effectiveness]
   
   ## Technical Quality
   - Grammar and mechanics: [assessment]
   - Consistency: [assessment]
   - Citations: [completeness check]
   
   ## Readability
   - Clarity score: [evaluation]
   - Sentence variety: [evaluation]
   - Paragraph length: [evaluation]
   
   ## Final Polish Suggestions
   
   1. **Introduction**: [Specific improvements]
   2. **Body**: [Specific improvements]
   3. **Conclusion**: [Specific improvements]
   4. **Title**: [Options if needed]
   
   ## Pre-Publish Checklist
   - [ ] All claims sourced
   - [ ] Citations formatted
   - [ ] Examples clear
   - [ ] Transitions smooth
   - [ ] Call to action present
   - [ ] Proofread for typos
   
   Ready to publish! 🚀
   ```

## 示例

### 示例 1：Teresa Torres 的工作流

**用户**："I'm writing an article about continuous discovery. Help me create an outline."

**流程**：
1. 协作完成 outline structure
2. 识别 research needs
3. 用户开始写 introduction
4. 审阅并改进 hook
5. 用户撰写每个 section
6. 每个 section 后提供 feedback
7. 开展 research 并添加 citations
8. 对完整 draft 做最终 review
9. Polish 并准备 publish

**结果**：一篇 research 充分、citation 恰当，并以 Teresa 的 voice 写成的文章，具有强结构和流畅度。

### 示例 2：Research-heavy Article

**用户**："I'm writing about AI's impact on product management. Help me find current data and examples."

**输出**：
```markdown
## Research Compiled

### Recent Data
- Gartner: 80% of PMs will use AI tools by 2025 [1]
- Survey: 45% report faster feature shipping [2]
- Case study: Airbnb's AI-assisted prioritization [3]

### Expert Quotes
- "AI amplifies PM judgment, not replaces it" - Marty Cagan
- [Additional quotes with citations]

### Real Examples
1. **Company A**: Used AI for user research synthesis
   - Result: 60% time savings
   - Source: [citation]

2. **Company B**: AI-powered roadmap analysis
   - Result: Better stakeholder alignment
   - Source: [citation]

All added to your outline with proper citations.
```

### 示例 3：Hook Improvement

**用户的原始 Hook**：
> “产品管理正在因为 AI 而变化。在这篇文章中，我会讨论 AI 影响产品经理的一些方式。”

**改进选项**：

**Option 1（Data-driven）**：
> “上个月，我让 AI 分析了 500 份客户访谈。它花了 30 分钟，而不是 3 周。产品管理再也不会一样了。”

**Option 2（Question）**：
> “如果你能在早咖啡前，就和每个客户交谈、阅读每条评论并分析每张 support ticket，会怎样？”

**Option 3（Story）**：
> “Sarah 花了两周做错了功能。不是因为她不了解用户，而是因为她无法足够快地处理数百次访谈，从中发现那个模式。”

### 示例 4：Section Feedback

**用户**：“刚写完我的 ‘Common Mistakes’ section。有什么想法？”

**Response**：
```markdown
# Feedback: Common Mistakes Section

## What Works Well ✓
- Strong examples (the Slack notification story)
- Clear structure (3 mistakes, clean layout)
- Practical advice for each mistake

## Suggestions

### Make It More Specific
Your second point says "Bad prioritization" but could be stronger:

Current:
> "Many teams prioritize badly by focusing on features instead of outcomes."

Suggested:
> "I've watched teams ship 14 features in a quarter yet move none of their key metrics. They prioritized activity over progress."

### Add Data
The third mistake would benefit from evidence:
> "[Add citation]: Studies show teams without regular user contact are 3x more likely to build unused features [needs source]"

### Flow Improvement
Consider reordering: Mistake 3 → Mistake 2 → Mistake 1
This builds from small to big impact.

Ready for the next section!
```

## 写作工作流

### Blog Post Workflow
1. 一起制定 outline
2. Research key points
3. 写 introduction → 获取 feedback
4. 写 body sections → 每个 section 获取 feedback
5. 写 conclusion → final review
6. Polish 和 edit

### Newsletter Workflow
1. 讨论 hook ideas
2. 快速 outline（更短格式）
3. 一次性 draft
4. 审阅 clarity 和 links
5. 快速 polish

### Technical Tutorial Workflow
1. Outline steps
2. 编写 code examples
3. 添加 explanations
4. 测试 instructions
5. 添加 troubleshooting section
6. 最终 review accuracy

### Thought Leadership Workflow
1. Brainstorm 独特 angle
2. Research existing perspectives
3. 发展你的 thesis
4. 以强 POV 写作
5. 添加 supporting evidence
6. 打磨 compelling conclusion

## Pro Tips

1. **在 VS Code 中工作**：比 web chat 更适合 long-form writing
2. **一次写一个 section**：incrementally 获取 feedback
3. **单独保存 research**：保留一个 research.md 文件
4. **为 drafts 做版本管理**：article-v1.md、article-v2.md 等
5. **大声读出来**：用 feedback 找出拗口句子
6. **设置 deadlines**：“I want to finish the draft today”
7. **休息**：写作、获取 feedback、暂停、revision

## 文件组织

写作项目的推荐结构：

```
~/writing/article-name/
├── outline.md          # Your outline
├── research.md         # All research and citations
├── draft-v1.md         # First draft
├── draft-v2.md         # Revised draft
├── final.md            # Publication-ready
├── feedback.md         # Collected feedback
└── sources/            # Reference materials
    ├── study1.pdf
    └── article2.md
```

## 最佳实践

### Research
- 引用前验证 sources
- 尽可能使用 recent data
- 平衡不同 perspectives
- 链接到 original sources

### Feedback
- 明确说明你想要什么：“Is this too technical?”
- 分享你的担忧：“I'm worried this section drags”
- 提问：“Does this flow logically?”
- 请求 alternatives：“What's another way to explain this?”

### Voice
- 分享你的 writing examples
- 指定 tone preferences
- 指出匹配良好的地方：“That sounds like me!”
- 标记不匹配：“Too formal for my style”

## 相关 Use Cases

- 从 articles 创建 social media posts
- 为不同 audiences 改写内容
- 撰写 email newsletters
- 起草 technical documentation
- 创建 presentation content
- 撰写 case studies
- 开发 course outlines
