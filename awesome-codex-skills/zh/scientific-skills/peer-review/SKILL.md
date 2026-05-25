---
name: peer-review
description: 使用 checklist-based evaluation 进行结构化 manuscript/grant review。用于撰写正式 peer reviews，包含具体 criteria、methodology assessment、statistical validity、reporting standards compliance（CONSORT/STROBE）和 constructive feedback。最适合实际 review writing、manuscript revision。评估 claims/evidence quality 请用 scientific-critical-thinking；量化评分框架请用 scholar-evaluation。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# 科学批判性评估与同行评审

## 概览

Peer review 是评估 scientific manuscripts 的系统过程。评估 methodology、statistics、design、reproducibility、ethics 和 reporting standards。将此 skill 用于跨学科 manuscript 和 grant review，进行建设性且严谨的评估。

## 何时使用此 Skill

此 skill 应用于：
- 为 journals 进行 scientific manuscripts peer review
- 评估 grant proposals 和 research applications
- 评估 methodology 和 experimental design rigor
- 审阅 statistical analyses 和 reporting standards
- 评估 reproducibility 和 data availability
- 检查是否符合 reporting guidelines（CONSORT、STROBE、PRISMA）
- 对 scientific writing 提供 constructive feedback

## 使用 Scientific Schematics 增强视觉表达

**使用此 skill 创建文档时，始终考虑添加 scientific diagrams 和 schematics 来增强视觉沟通。**

如果你的文档尚未包含 schematics 或 diagrams：
- 使用 **scientific-schematics** skill 生成 AI-powered publication-quality diagrams
- 用自然语言简单描述你想要的 diagram
- Nano Banana Pro 会自动生成、审阅并完善 schematic

**对于新文档：** 默认应生成 scientific schematics，以可视化呈现文本中描述的 key concepts、workflows、architectures 或 relationships。

**如何生成 schematics：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI 会自动：
- 创建 formatting 正确的 publication-quality images
- 通过多轮迭代审阅和完善
- 确保 accessibility（colorblind-friendly、high contrast）
- 将输出保存到 figures/ directory

**何时添加 schematics：**
- Peer review workflow diagrams
- Evaluation criteria decision trees
- Review process flowcharts
- Methodology assessment frameworks
- Quality assessment visualizations
- Reporting guidelines compliance diagrams
- 任何适合用可视化帮助理解的复杂概念

关于创建 schematics 的详细指南，请参考 scientific-schematics skill documentation。

---

## Peer Review Workflow

通过以下阶段系统开展 peer review，并根据 manuscript type 和 discipline 调整深度与重点。

### 阶段 1：初步评估

从高层次评估开始，判断 manuscript 的范围、novelty 和整体质量。

**关键问题：**
- 中心 research question 或 hypothesis 是什么？
- 主要 findings 和 conclusions 是什么？
- 这项工作在科学上是否可靠且重要？
- 这项工作是否适合目标 venue？
- 是否存在会直接阻碍发表的重大缺陷？

**输出：** 简短 summary（2-3 句），概括 manuscript 的实质内容和初步印象。

### 阶段 2：逐节详细审阅

对 manuscript 每个 section 进行彻底评估，记录具体 concerns 和 strengths。

#### Abstract 和 Title
- **Accuracy：** abstract 是否准确反映 study 的内容和 conclusions？
- **Clarity：** title 是否具体、准确且信息充分？
- **Completeness：** key findings 和 methods 是否得到适当概括？
- **Accessibility：** abstract 是否能被广泛 scientific audience 理解？

#### Introduction
- **Context：** background information 是否充分且最新？
- **Rationale：** research question 的动机和依据是否清楚？
- **Novelty：** 工作的 originality 和 significance 是否阐述清楚？
- **Literature：** 相关 prior studies 是否得到适当引用？
- **Objectives：** research aims/hypotheses 是否明确陈述？

#### Methods
- **Reproducibility：** 其他研究者是否能根据提供的描述复现 study？
- **Rigor：** methods 是否适合回答 research questions？
- **Detail：** protocols、reagents、equipment 和 parameters 是否描述充分？
- **Ethics：** ethical approvals、consent 和 data handling 是否有适当记录？
- **Statistics：** statistical methods 是否合适、描述清楚且有依据？
- **Validation：** controls、replicates 和 validation approaches 是否充分？

**需要验证的关键元素：**
- Sample sizes 和 power calculations
- Randomization 和 blinding procedures
- Inclusion/exclusion criteria
- Data collection protocols
- Computational methods 和 software versions
- Statistical tests 以及 multiple comparisons correction

#### Results
- **Presentation：** results 是否逻辑清楚地呈现？
- **Figures/Tables：** visualizations 是否合适、清楚且正确标注？
- **Statistics：** statistical results 是否正确报告（effect sizes、confidence intervals、p-values）？
- **Objectivity：** results 呈现是否避免过度解读？
- **Completeness：** 是否包含所有 relevant results，包括 negative results？
- **Reproducibility：** 是否提供 raw data 或 summary statistics？

**需要识别的常见问题：**
- 选择性报告 results
- 不恰当的 statistical tests
- 缺少 error bars 或 variability measures
- Over-fitting 或 circular analysis
- Batch effects 或 confounding variables
- 缺少 controls 或 validation experiments

#### Discussion
- **Interpretation：** conclusions 是否由 data 支持？
- **Limitations：** study limitations 是否被承认并讨论？
- **Context：** findings 是否被适当地置于 existing literature 中？
- **Speculation：** speculation 是否与 data-supported conclusions 清楚区分？
- **Significance：** implications 和 importance 是否阐述清楚？
- **Future directions：** 是否讨论了 next steps 或 unanswered questions？

**危险信号：**
- 夸大 conclusions
- 忽视 contradictory evidence
- 基于 correlational data 提出 causal claims
- limitations 讨论不足
- 在缺少 mechanistic evidence 时提出 mechanistic claims

#### References
- **Completeness：** 是否引用 key relevant papers？
- **Currency：** 是否纳入近期重要 studies？
- **Balance：** 是否适当引用 contrary viewpoints？
- **Accuracy：** citations 是否准确且合适？
- **Self-citation：** 是否存在过度或不恰当的 self-citation？

### 阶段 3：Methodological 与 Statistical Rigor

评估 research 的技术质量和严谨性，特别关注 common pitfalls。

**Statistical Assessment：**
- statistical assumptions 是否满足（normality、independence、homoscedasticity）？
- 是否在 p-values 之外同时报告 effect sizes？
- multiple testing correction 是否适当应用？
- 是否提供 confidence intervals？
- sample size 是否通过 power analysis 论证？
- parametric vs. non-parametric tests 的选择是否合适？
- missing data 是否妥善处理？
- 是否区分 exploratory vs. confirmatory analyses？

**Experimental Design：**
- controls 是否合适且充分？
- replication 是否充分（biological 和 technical）？
- potential confounders 是否被识别并控制？
- randomization 是否正确实施？
- blinding procedures 是否充分？
- experimental design 对 research question 是否最优？

**Computational/Bioinformatics：**
- computational methods 是否描述清楚且有依据？
- software versions 和 parameters 是否记录？
- code 是否可用以支持 reproducibility？
- algorithms 和 models 是否得到适当验证？
- computational methods 的 assumptions 是否满足？
- batch correction 是否适当应用？

### 阶段 4：Reproducibility 与 Transparency

评估 research 是否满足现代 reproducibility 和 open science 标准。

**Data Availability：**
- raw data 是否存放在合适 repositories？
- 是否为 public databases 提供 accession numbers？
- data sharing restrictions 是否有正当理由（例如 patient privacy）？
- data formats 是否标准且可访问？

**Code and Materials：**
- analysis code 是否可用（GitHub、Zenodo 等）？
- unique materials 是否可获取，或是否被充分描述以便重建？
- protocols 是否足够详细？

**Reporting Standards：**
- manuscript 是否遵循 discipline-specific reporting guidelines（CONSORT、PRISMA、ARRIVE、MIAME、MINSEQE 等）？
- 常见 guidelines 见 `references/reporting_standards.md`
- 对应 checklist 的所有元素是否都已处理？

### 阶段 5：Figure 与 Data Presentation

评估 data visualization 的质量、清晰度和完整性。

**Quality Checks：**
- figures 是否为 high resolution 且标注清楚？
- axes 是否正确标注并包含 units？
- error bars 是否定义（SD、SEM、CI）？
- statistical significance indicators 是否解释？
- color schemes 是否合适且 accessible（colorblind-friendly）？
- images 是否包含 scale bars？
- data visualization 是否适合 data type？

**Integrity Checks：**
- 是否存在 image manipulation 迹象（duplications、splicing）？
- Western blots 和 gels 是否适当呈现？
- representative images 是否真正具有代表性？
- 是否展示所有 conditions（无 selective presentation）？

**Clarity：**
- figures 能否与 legends 一起独立理解？
- 每个 figure 的信息是否一目了然？
- 是否存在冗余 figures 或 panels？
- data 是否更适合用 tables 或 figures 呈现？

### 阶段 6：Ethical Considerations

验证 research 是否符合 ethical standards 和 guidelines。

**Human Subjects：**
- 是否记录 IRB/ethics approval？
- 是否描述 informed consent？
- vulnerable populations 是否得到适当保护？
- patient privacy 是否得到充分保护？
- potential conflicts of interest 是否披露？

**Animal Research：**
- 是否记录 IACUC 或等效 approval？
- procedures 是否 humane 且有依据？
- 是否考虑 3Rs（replacement、reduction、refinement）？
- euthanasia methods 是否合适？

**Research Integrity：**
- 是否存在 data fabrication 或 falsification 方面的担忧？
- authorship 是否合适且有依据？
- competing interests 是否披露？
- funding source 是否披露？
- 是否存在 plagiarism 或 duplicate publication 方面的担忧？

### 阶段 7：Writing Quality 与 Clarity

评估 manuscript 的清晰度、组织结构和可理解性。

**Structure and Organization：**
- manuscript 组织是否合乎逻辑？
- sections 之间是否连贯？
- ideas 之间的 transitions 是否清楚？
- narrative 是否有说服力且清晰？

**Writing Quality：**
- language 是否清楚、精确且简洁？
- jargon 和 acronyms 是否最少化并被定义？
- grammar 和 spelling 是否正确？
- sentences 是否不必要地复杂？
- passive voice 是否过度使用？

**Accessibility：**
- non-specialist 是否能理解 main findings？
- technical terms 是否解释？
- significance 对广泛受众是否清楚？

## 组织 Peer Review Reports

以分层结构组织 feedback，按优先级排列问题并提供 actionable guidance。

### Summary Statement

提供简洁的整体评估（1-2 段）：
- research 的简短 synopsis
- overall recommendation（accept、minor revisions、major revisions、reject）
- key strengths（2-3 个 bullet points）
- key weaknesses（2-3 个 bullet points）
- 对 significance 和 soundness 的底线评估

### Major Comments

列出会显著影响 manuscript validity、interpretability 或 significance 的关键问题。按顺序编号，方便引用。

**Major comments 通常包括：**
- fundamental methodological flaws
- inappropriate statistical analyses
- unsupported 或 overstated conclusions
- 缺少 critical controls 或 experiments
- serious reproducibility concerns
- literature coverage 中的重大缺口
- ethical concerns

**每条 major comment 应：**
1. 清楚陈述问题
2. 解释为什么有问题
3. 建议具体解决方案或 additional experiments
4. 指明解决它是否是发表的必要条件

### Minor Comments

列出较不关键、但会改善 clarity、completeness 或 presentation 的问题。按顺序编号。

**Minor comments 通常包括：**
- 不清楚的 figure labels 或 legends
- 缺少 methodological details
- typographical 或 grammatical errors
- 改进 data presentation 的建议
- minor statistical reporting issues
- 可加强 conclusions 的 supplementary analyses
- 请求澄清

**每条 minor comment 应：**
1. 标明具体位置（section、paragraph、figure）
2. 清楚说明问题
3. 建议如何处理

### 具体逐行 Comments（可选）

对于需要详细反馈的 manuscripts，提供 section-specific 或 line-by-line comments：
- 引用具体 page/line numbers 或 sections
- 记录 factual errors、unclear statements 或 missing citations
- 建议具体 edits 以提升 clarity

### 给作者的问题

列出需要澄清的具体问题：
- 不清楚的 methodological details
- 表面上相互矛盾的 results
- 评估该工作所需但缺失的信息
- 对 additional data 或 analyses 的请求

## 语气与方法

在整个 review 中保持建设性、专业且 collegial 的语气。

**Best Practices：**
- **Be constructive：** 将批评表述为改进机会
- **Be specific：** 提供具体 examples 和 actionable suggestions
- **Be balanced：** 同时承认 strengths 和 weaknesses
- **Be respectful：** 记住作者投入了大量努力
- **Be objective：** 聚焦 science，而不是 scientists
- **Be thorough：** 不遗漏问题，但要适当排序优先级
- **Be clear：** 避免含糊或笼统的批评

**避免：**
- personal attacks 或 dismissive language
- sarcasm 或 condescension
- 没有具体 examples 的笼统批评
- 要求超出 scope 的不必要 experiments
- 要求遵循个人偏好而非 best practices
- 如果是 double-blind review，不要暴露自己的身份

## 按 Manuscript Type 的特殊考量

### Original Research Articles
- 强调 rigor、reproducibility 和 novelty
- 评估 significance 和 impact
- 验证 conclusions 是否 data-driven
- 检查 methods 是否完整且 controls 是否适当

### Reviews and Meta-Analyses
- 评估 literature coverage 的全面性
- 评估 search strategy 和 inclusion/exclusion criteria
- 验证 systematic approach 和是否缺少 bias
- 检查是否有 critical analysis，而不只是 summary
- 对 meta-analyses，评估 statistical approach 和 heterogeneity

### Methods Papers
- 强调 validation 以及与 existing methods 的比较
- 评估 reproducibility 以及 protocols/code 的可用性
- 评估相对 existing approaches 的改进
- 检查是否有足够细节可供实现

### Short Reports/Letters
- 根据篇幅简短调整期望
- 确保 core findings 仍然 rigorous 且 significant
- 验证 format 是否适合 findings

### Preprints
- 认识到它们尚未经过正式 peer review
- 可能比 journal submissions 打磨程度更低
- 仍需对 scientific validity 应用严格标准
- 考虑提供 constructive feedback，帮助作者在 journal submission 前改进

### Presentations 和 Slide Decks

**⚠️ 关键：对于 presentations，绝不要直接读取 PDF。始终先转换为 images。**

审阅 scientific presentations（PowerPoint、Beamer、slide decks）时：

#### 强制 Image-Based Review Workflow

**绝不要尝试直接读取 presentation PDFs** - 这会导致 buffer overflow errors，并且无法显示 visual formatting issues。

**必需流程：**
1. 使用 Python 将 PDF 转换为 images：
   ```bash
   python skills/scientific-slides/scripts/pdf_to_images.py presentation.pdf review/slide --dpi 150
   # Creates: review/slide-001.jpg, review/slide-002.jpg, etc.
   ```
2. 按顺序读取并检查每一个 slide image file
3. 用具体 slide numbers 记录问题
4. 提供关于 visual formatting 和 content 的 feedback

**开始 review 时打印：**
```
[HH:MM:SS] PEER REVIEW: Presentation detected - converting to images for review
[HH:MM:SS] PDF REVIEW: NEVER reading PDF directly - using image-based inspection
```

#### Presentation-Specific Evaluation Criteria

**Visual Design and Readability：**
- [ ] Text 足够大（body text 最小 18pt，理想为 24pt+）
- [ ] text 与 background 之间有 high contrast（最低 4.5:1，首选 7:1）
- [ ] Color scheme 专业且 colorblind-accessible
- [ ] 所有 slides 的 visual design 一致
- [ ] White space 充分（不拥挤）
- [ ] Fonts 清楚且专业

**Layout and Formatting（检查每张 Slide Image）：**
- [ ] slide edges 处没有 text overflow 或 truncation
- [ ] 没有 element overlaps（text over images、overlapping shapes）
- [ ] Titles 位置一致
- [ ] Content 正确对齐
- [ ] Bullets 和 text 没有被截断
- [ ] Figures 位于 slide boundaries 内
- [ ] Captions 和 labels 可见且可读

**Content Quality：**
- [ ] 每张 slide 一个 main idea（不过载）
- [ ] Text 最少化（每张 slide 最多 3-6 个 bullets）
- [ ] Bullet points 简洁（每条 5-7 个词）
- [ ] Figures 简化且清楚（不是从论文中 copy-pasted）
- [ ] Data visualizations 具有大且可读的 labels
- [ ] Citations 存在且格式正确
- [ ] Results/data slides 在 presentation 中占主导（40-50% 的内容）

**Structure and Flow：**
- [ ] 清楚的 narrative arc（introduction → methods → results → discussion）
- [ ] slides 之间逻辑递进
- [ ] slide count 适合 talk duration（约每分钟 1 张 slide）
- [ ] Title slide 包含 authors、affiliation、date
- [ ] Introduction 引用相关 background literature（3-5 papers）
- [ ] Discussion 引用 comparison papers（3-5 papers）
- [ ] Conclusions slide 总结 key findings
- [ ] 末尾有 acknowledgments/funding slide

**Scientific Content：**
- [ ] Research question 清楚陈述
- [ ] Methods 适当概括（不过度详细）
- [ ] Results 以清楚 visualizations 逻辑呈现
- [ ] Statistical significance 标注合适
- [ ] Conclusions 由所展示 data 支持
- [ ] 在合适位置承认 limitations
- [ ] 讨论 future directions 或 broader impact

**需要标记的常见 Presentation Issues：**

**Critical Issues（必须修复）：**
- Text overflow 导致内容不可读
- Font sizes 太小（<18pt）
- Element overlaps 遮挡 data
- Contrast 不足（text 难以阅读）
- Figures 过于复杂或不可辨认
- 无 citations（claims 完全无支持）
- Slide count 与 duration 严重不匹配

**Major Issues（应修复）：**
- slides 之间 design 不一致
- text 过多（大段文字，而不是 bullets）
- figures 简化不足（axis labels 太小）
- layout 拥挤，white space 不足
- 缺少关键 structural elements（没有 conclusion slide）
- color choices 不佳（非 colorblind-safe）
- results content 过少（<30% slides）

**Minor Issues（改进建议）：**
- 可使用更多 visuals/diagrams
- 部分 slides text 稍多
- 轻微 alignment inconsistencies
- 可从更多 white space 中受益
- additional citations 会加强 claims
- color scheme 可更现代

#### Presentations 的 Review Report Format

**Summary Statement：**
- 对 presentation quality 的 overall impression
- 对 target audience 和 duration 的适配性
- Key strengths（visual design、content、clarity）
- Key weaknesses（formatting issues、content gaps）
- Recommendation（ready to present、minor revisions、major revisions）

**Layout and Formatting Issues（按 Slide Number）：**
```
Slide 3: Text overflow - bullet point 4 extends beyond right margin
Slide 7: Element overlap - figure overlaps with caption text
Slide 12: Font size - axis labels too small to read from distance
Slide 18: Alignment - title not centered
```

**Content and Structure Feedback：**
- background context 和 citations 是否充分
- research question 和 objectives 是否清楚
- methods summary 的质量
- results presentation 的有效性
- conclusions 和 implications 的力度

**Design and Accessibility：**
- 整体 visual appeal 和 professionalism
- Color contrast 和 readability
- Colorblind accessibility
- slides 之间的一致性

**Timing and Scope：**
- slide count 是否匹配 intended duration
- detail level 是否适合 talk type
- sections 之间的平衡

#### Image-Based Review Process 示例

```
[14:30:00] PEER REVIEW: Starting review of presentation
[14:30:05] PEER REVIEW: Presentation detected - converting to images
[14:30:10] PDF REVIEW: Running pdf_to_images.py on presentation.pdf
[14:30:15] PDF REVIEW: Converted 25 slides to images in review/ directory
[14:30:20] PDF REVIEW: Inspecting slide 1/25 - title slide
[14:30:25] PDF REVIEW: Inspecting slide 2/25 - introduction
...
[14:35:40] PDF REVIEW: Inspecting slide 25/25 - acknowledgments
[14:35:45] PDF REVIEW: Completed image-based review
[14:35:50] PEER REVIEW: Found 8 layout issues, 3 content issues
[14:35:55] PEER REVIEW: Generating structured feedback by slide number
```

**记住：** 对于 presentations，通过 images 进行 visual inspection 是强制性的。绝不要尝试把 presentation PDFs 当作 text 阅读，这会失败并漏掉所有 visual formatting issues。

## 资源

此 skill 包含支持 comprehensive peer review 的参考材料：

### references/reporting_standards.md
跨学科 major reporting standards（CONSORT、PRISMA、ARRIVE、MIAME、STROBE 等）的 guidelines，用于评估 methods 和 results reporting 的完整性。

### references/common_issues.md
peer review 中常见 methodological 和 statistical issues 的目录，并提供识别和处理这些问题的指南。

## 最终 Checklist

在完成 review 前，验证：

- [ ] Summary statement 清楚传达 overall assessment
- [ ] Major concerns 被清楚识别并论证
- [ ] Suggested revisions 具体且可执行
- [ ] Minor issues 已记录且分类恰当
- [ ] Statistical methods 已评估
- [ ] Reproducibility 和 data availability 已评估
- [ ] Ethical considerations 已验证
- [ ] Figures 和 tables 的 quality 与 integrity 已评估
- [ ] Writing quality 已评估
- [ ] 全文 tone 建设性且专业
- [ ] Review 彻底，但与 manuscript scope 成比例
- [ ] Recommendation 与已识别问题一致
