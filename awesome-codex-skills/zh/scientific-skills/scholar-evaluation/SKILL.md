---
name: scholar-evaluation
description: 使用 ScholarEval framework 系统评估 scholarly work，围绕 problem formulation、methodology、analysis 和 writing 等 research quality dimensions 提供结构化 assessment、quantitative scoring 和 actionable feedback。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scholar Evaluation

## 概述

应用 ScholarEval framework 系统评估 scholarly 和 research work。此 skill 提供基于 peer-reviewed research assessment criteria 的结构化 evaluation methodology，可对 academic papers、research proposals、literature reviews 和 scholarly writing 在多个 quality dimensions 上进行综合分析。

## 何时使用此 Skill

在以下情况使用此 skill：
- 评估 research papers 的 quality 和 rigor
- 评估 literature review 的 comprehensiveness 和 quality
- 审查 research methodology design
- 为 data analysis approaches 打分
- 评估 scholarly writing 和 presentation
- 对 academic work 提供 structured feedback
- 按 established criteria benchmark research quality
- 评估面向 target venues 的 publication readiness
- 提供 quantitative evaluation，以补充 qualitative peer review

## 使用 Scientific Schematics 增强视觉表达

**使用此 skill 创建文档时，应始终考虑添加 scientific diagrams 和 schematics，以增强 visual communication。**

如果你的文档尚未包含 schematics 或 diagrams：
- 使用 **scientific-schematics** skill 生成 AI-powered publication-quality diagrams
- 只需用自然语言描述所需 diagram
- Nano Banana Pro 会自动生成、审查并完善 schematic

**对于新文档：** 默认应生成 scientific schematics，以可视化表示文本中描述的 key concepts、workflows、architectures 或 relationships。

**如何生成 schematics：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI 会自动：
- 创建具有正确格式的 publication-quality images
- 通过多轮迭代 review 和 refine
- 确保 accessibility（colorblind-friendly、高对比度）
- 将输出保存到 figures/ 目录

**何时添加 schematics：**
- Evaluation framework diagrams
- Quality assessment criteria decision trees
- Scholarly workflow visualizations
- Assessment methodology flowcharts
- Scoring rubric visualizations
- Evaluation process diagrams
- 任何受益于 visualization 的复杂概念

创建 schematics 的详细指导请参考 scientific-schematics skill 文档。

---

## Evaluation Workflow

### Step 1: Initial Assessment and Scope Definition

首先识别被评估 scholarly work 的类型和 evaluation scope：

**Work Types：**
- Full research paper（empirical、theoretical 或 review）
- Research proposal 或 protocol
- Literature review（systematic、narrative 或 scoping）
- Thesis 或 dissertation chapter
- Conference abstract 或 short paper

**Evaluation Scope：**
- Comprehensive（所有 dimensions）
- Targeted（特定方面，如 methodology 或 writing）
- Comparative（与其他 work benchmark）

如果 scope 不明确，请让用户澄清。

### Step 2: Dimension-Based Evaluation

围绕 ScholarEval dimensions 系统评估工作。对每个适用 dimension，评估 quality、识别 strengths 和 weaknesses，并在适当时提供 scores。

每个 dimension 的详细 criteria 和 rubrics 见 `references/evaluation_framework.md`。

**Core Evaluation Dimensions：**

1. **Problem Formulation & Research Questions**
   - Research questions 的 clarity 和 specificity
   - Theoretical 或 practical significance
   - Feasibility 和 scope appropriateness
   - Novelty 和 contribution potential

2. **Literature Review**
   - Coverage 的 comprehensiveness
   - Critical synthesis vs. merely summarization
   - Research gaps 的识别
   - Sources 的 currency 和 relevance
   - Proper contextualization

3. **Methodology & Research Design**
   - 对 research questions 的 appropriateness
   - Rigor 和 validity
   - Reproducibility 和 transparency
   - Ethical considerations
   - Limitations acknowledgment

4. **Data Collection & Sources**
   - Data 的 quality 和 appropriateness
   - Sample size 和 representativeness
   - Data collection procedures
   - Source credibility 和 reliability

5. **Analysis & Interpretation**
   - Analytical methods 的 appropriateness
   - Analysis 的 rigor
   - Logical coherence
   - 是否考虑 alternative explanations
   - Results-claims alignment

6. **Results & Findings**
   - Presentation 的 clarity
   - Statistical 或 qualitative rigor
   - Visualization quality
   - Interpretation accuracy
   - Implications discussion

7. **Scholarly Writing & Presentation**
   - Clarity 和 organization
   - Academic tone 和 style
   - Grammar 和 mechanics
   - Logical flow
   - 对 target audience 的 accessibility

8. **Citations & References**
   - Citation completeness
   - Source quality 和 appropriateness
   - Citation accuracy
   - Perspectives 的 balance
   - 遵守 citation standards

### Step 3: Scoring and Rating

为每个 evaluated dimension 提供：

**Qualitative Assessment：**
- Key strengths（2-3 个具体点）
- Areas for improvement（2-3 个具体点）
- Critical issues（如有）

**Quantitative Scoring（可选）：**
适用时使用 5-point scale：
- 5：Excellent - Exemplary quality，可发表于 top venues
- 4：Good - 质量较强，仅需 minor improvements
- 3：Adequate - 质量可接受，但有明显 areas for improvement
- 2：Needs Improvement - 需要 significant revisions
- 1：Poor - 存在 fundamental issues，需要 major revision

如需以编程方式计算 aggregate scores，使用 `scripts/calculate_scores.py`。

### Step 4: Synthesize Overall Assessment

提供 integrated evaluation summary：

1. **Overall Quality Assessment** - 对 work's scholarly merit 的 holistic judgment
2. **Major Strengths** - 跨 dimensions 的 3-5 个 key strengths
3. **Critical Weaknesses** - 需要关注的 3-5 个主要 areas
4. **Priority Recommendations** - 按 impact 排序的 improvements 列表
5. **Publication Readiness**（如适用）- 对 target venues 适配性的 assessment

### Step 5: Provide Actionable Feedback

将 evaluation findings 转化为建设性、可执行的 feedback：

**Feedback Structure：**
- **Specific** - 引用确切 sections、paragraphs 或 page numbers
- **Actionable** - 提供具体 improvement suggestions
- **Prioritized** - 按 importance 和 feasibility 排序 recommendations
- **Balanced** - 承认 strengths，同时回应 weaknesses
- **Evidence-based** - 将 feedback 建立在 evaluation criteria 上

**Feedback Format Options：**
- 按 dimension-by-dimension analysis 的 structured report
- 映射到具体 document sections 的 annotated comments
- 含 key findings 和 recommendations 的 executive summary
- 与 benchmark standards 的 comparative analysis

### Step 6: Contextual Considerations

根据以下因素调整 evaluation approach：

**Stage of Development：**
- Early draft：聚焦 conceptual 和 structural issues
- Advanced draft：聚焦 refinement 和 polish
- Final submission：comprehensive quality check

**Purpose and Venue：**
- Journal article：对 rigor 和 contribution 要求高
- Conference paper：平衡 novelty 与 presentation clarity
- Student work：以 development 为重点的 educational feedback
- Grant proposal：强调 feasibility 和 impact

**Discipline-Specific Norms：**
- STEM fields：强调 reproducibility 和 statistical rigor
- Social sciences：平衡 quantitative 和 qualitative standards
- Humanities：聚焦 argumentation 和 scholarly interpretation

## 资源

### references/evaluation_framework.md

每个 ScholarEval dimension 的详细 evaluation criteria、rubrics 和 quality indicators。进行 evaluations 时加载此 reference，以访问具体 assessment guidelines 和 scoring rubrics。

快速访问的 search patterns：
- "Problem Formulation criteria"
- "Literature Review rubric"
- "Methodology assessment"
- "Data quality indicators"
- "Analysis rigor standards"
- "Writing quality checklist"

### scripts/calculate_scores.py

Python script，用于根据 dimension-level ratings 计算 aggregate evaluation scores。支持 weighted averaging、threshold analysis 和 score visualization。

Usage：
```bash
python scripts/calculate_scores.py --scores <dimension_scores.json> --output <report.txt>
```

## Best Practices

1. **保持 Objectivity** - 基于 established criteria，而非个人偏好
2. **做到 Comprehensive** - 系统评估所有适用 dimensions
3. **提供 Evidence** - 用 work 中的具体 examples 支撑 assessments
4. **保持 Constructive** - 将 weaknesses 表述为 improvement opportunities
5. **考虑 Context** - 根据 work stage 和 purpose 调整期望
6. **记录 Rationale** - 解释 assessments 和 scores 背后的 reasoning
7. **鼓励 Strengths** - 明确承认 work 做得好的地方
8. **优先反馈** - 首先关注 high-impact improvements

## Example Evaluation Workflow

**User Request：** "Evaluate this research paper on machine learning for drug discovery"

**Response Process：**
1. 识别 work type（empirical research paper）和 scope（comprehensive evaluation）
2. 加载 `references/evaluation_framework.md` 以获取 detailed criteria
3. 系统评估每个 dimension：
   - Problem formulation：关于 ML model performance 的清晰 research question
   - Literature review：全面覆盖 recent ML 和 drug discovery work
   - Methodology：带 validation procedures 的合适 deep learning architecture
   - [继续遍历所有 dimensions...]
4. 计算 dimension scores 和 overall assessment
5. 综合 findings 为 structured report，突出：
   - Strong methodology 和 reproducible code
   - 需要更多 diverse dataset evaluation
   - Results section 的 writing clarity 可改进
6. 提供带具体建议的 prioritized recommendations

## 与 Scientific Writer 的集成

此 skill 可与 scientific writer workflow 无缝集成：

**After Paper Generation：**
- 将 Scholar Evaluation 用作 peer review 的替代或补充
- 与 `PEER_REVIEW.md` 一起生成 `SCHOLAR_EVALUATION.md`
- 提供 quantitative scores 以跟踪 revisions 间的 improvement

**During Revision：**
- 回应 feedback 后重新评估特定 dimensions
- 跟踪多个 versions 的 score improvements
- 识别需要关注的 persistent weaknesses

**Publication Preparation：**
- 评估 target journal/conference 的 readiness
- Submission 前识别 gaps
- 与 publication standards benchmark

## Notes

- Evaluation rigor 应匹配 work 的 purpose 和 stage
- 某些 dimensions 可能不适用于所有 work types（例如纯理论论文中的 data collection）
- 应考虑 scholarly norms 中的 cultural 和 disciplinary differences
- 此 framework 补充而不是替代 domain-specific expertise
- 与 peer-review skill 结合使用可获得 comprehensive assessment

## Citation

此 skill 基于以下论文提出的 ScholarEval framework：

**Moussa, H. N., Da Silva, P. Q., Adu-Ampratwum, D., East, A., Lu, Z., Puccetti, N., Xue, M., Sun, H., Majumder, B. P., & Kumar, S. (2025).** _ScholarEval: Research Idea Evaluation Grounded in Literature_. arXiv preprint arXiv:2510.16234. [https://arxiv.org/abs/2510.16234](https://arxiv.org/abs/2510.16234)

**Abstract：** ScholarEval 是一个 retrieval augmented evaluation framework，基于两个基本标准评估 research ideas：soundness（基于 existing literature 的 proposed methods empirical validity）和 contribution（idea 相对于 prior research 在不同 dimensions 上产生的 advancement 程度）。该 framework 对 expert-annotated evaluation points 的 coverage 显著更高，并在 evaluation actionability、depth 和 evidence support 方面始终优于 baseline systems。
