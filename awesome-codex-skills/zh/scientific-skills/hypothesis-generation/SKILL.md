---
name: hypothesis-generation
description: 从 observations 进行结构化 hypothesis formulation。当你有 experimental observations 或 data，并需要提出带 predictions 的 testable hypotheses、提出 mechanisms，以及设计 experiments 来测试它们时使用。遵循 scientific method framework。Open-ended ideation 使用 scientific-brainstorming；datasets 上的 automated LLM-driven hypothesis testing 使用 hypogenic。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scientific Hypothesis Generation

## 概述

Hypothesis generation 是开发 testable explanations 的系统过程。从 observations 提出 evidence-based hypotheses、设计 experiments、探索 competing explanations，并形成 predictions。将此 skill 应用于跨领域 scientific inquiry。

## 何时使用此 Skill

以下情况应使用此 skill：
- 从 observations 或 preliminary data 发展 hypotheses
- 设计 experiments 来测试 scientific questions
- 探索 phenomena 的 competing explanations
- 为 research 形成 testable predictions
- 进行 literature-based hypothesis generation
- 规划跨 scientific domains 的 mechanistic studies

## 使用 Scientific Schematics 进行视觉增强

**⚠️ 强制要求：每份 hypothesis generation report 必须至少包含 1-2 个使用 scientific-schematics skill 生成的 AI-generated figures。**

这不是可选项。没有 visual elements 的 hypothesis reports 是不完整的。在最终确定任何文档前：
1. 至少生成一个 schematic 或 diagram（例如展示 competing explanations 的 hypothesis framework）
2. 对 comprehensive reports，优先使用 2-3 个 figures（mechanistic pathway、experimental design flowchart、prediction decision tree）

**如何生成 figures：**
- 使用 **scientific-schematics** skill 生成 AI-powered publication-quality diagrams
- 直接用自然语言描述你想要的 diagram
- Nano Banana Pro 会自动生成、review 并 refine schematic

**如何生成 schematics：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI 会自动：
- 创建带 proper formatting 的 publication-quality images
- 通过多次 iterations review 和 refine
- 确保 accessibility（colorblind-friendly、high contrast）
- 将 outputs 保存到 figures/ directory

**何时添加 schematics：**
- 展示 competing explanations 的 hypothesis framework diagrams
- Experimental design flowcharts
- Mechanistic pathway diagrams
- Prediction decision trees
- Causal relationship diagrams
- Theoretical model visualizations
- 任何受益于 visualization 的 complex concept

创建 schematics 的详细指导请参考 scientific-schematics skill 文档。

---

## 工作流

遵循此系统化过程生成 robust scientific hypotheses：

### 1. 理解 Phenomenon

先澄清需要解释的 observation、question 或 phenomenon：

- 识别需要解释的核心 observation 或 pattern
- 定义 phenomenon 的 scope 和 boundaries
- 记录任何 constraints 或 specific contexts
- 澄清已知内容和不确定内容
- 识别相关 scientific domain(s)

### 2. 进行综合 Literature Search

搜索现有 scientific literature，用当前证据支撑 hypotheses。对 biomedical topics 使用 PubMed，对更广泛 scientific domains 使用 general web search：

**对于 biomedical topics：**
- 使用 WebFetch 和 PubMed URLs 访问相关 literature
- 搜索 recent reviews、meta-analyses 和 primary research
- 查找相似 phenomena、related mechanisms 或 analogous systems

**对于所有 scientific domains：**
- 使用 WebSearch 查找 recent papers、preprints 和 reviews
- 搜索 established theories、mechanisms 或 frameworks
- 识别当前理解中的 gaps

**Search strategy：**
- 从 broad searches 开始理解 landscape
- 缩小到 specific mechanisms、pathways 或 theories
- 查找 contradictory findings 或 unresolved debates
- 详细搜索技巧见 `references/literature_search_strategies.md`

### 3. 综合 Existing Evidence

分析并整合 literature search 的 findings：

- 总结对 phenomenon 的 current understanding
- 识别可能适用的 established mechanisms 或 theories
- 记录 conflicting evidence 或 alternative viewpoints
- 识别 gaps、limitations 或 unanswered questions
- 从 related systems 或 domains 中识别 analogies

### 4. 生成 Competing Hypotheses

提出 3-5 个可解释该 phenomenon 的 distinct hypotheses。每个 hypothesis 应：

- 提供 mechanistic explanation（不只是描述）
- 能与其他 hypotheses 区分
- 基于 literature synthesis 的证据
- 考虑不同层级的 explanation（molecular、cellular、systemic、population 等）

**生成 hypotheses 的策略：**
- 应用 analogous systems 中的 known mechanisms
- 考虑多个 causative pathways
- 探索不同 scales of explanation
- 质疑 existing explanations 中的 assumptions
- 以新方式组合 mechanisms

### 5. 评估 Hypothesis Quality

根据 `references/hypothesis_quality_criteria.md` 中的 established quality criteria 评估每个 hypothesis：

**Testability：** 该 hypothesis 能否 empirically tested？
**Falsifiability：** 哪些 observations 会反证它？
**Parsimony：** 它是否是符合证据的最简单解释？
**Explanatory Power：** 它能解释多少 phenomenon？
**Scope：** 它覆盖哪些范围的 observations？
**Consistency：** 它是否与 established principles 一致？
**Novelty：** 它是否提供超出现有 explanations 的新 insights？

明确记录每个 hypothesis 的 strengths 和 weaknesses。

### 6. 设计 Experimental Tests

对每个可行 hypothesis，提出具体 experiments 或 studies 来测试它。常见方法见 `references/experimental_design_patterns.md`：

**Experimental design elements：**
- 将测量或观察什么？
- 需要哪些 comparisons 或 controls？
- 将使用哪些 methods 或 techniques？
- 合适的 sample sizes 或 statistical approaches 是什么？
- 有哪些 potential confounds，如何处理？

**考虑多种 approaches：**
- Laboratory experiments（in vitro、in vivo、computational）
- Observational studies（cross-sectional、longitudinal、case-control）
- Clinical trials（如适用）
- Natural experiments 或 quasi-experimental designs

### 7. 形成 Testable Predictions

为每个 hypothesis 生成具体、quantitative predictions：

- 说明如果 hypothesis 正确，应观察到什么
- 尽可能指定 effects 的 expected direction 和 magnitude
- 识别 predictions 成立的 conditions
- 区分 competing hypotheses 之间的 predictions
- 记录会 falsify hypothesis 的 predictions

### 8. 呈现 Structured Output

使用 `assets/hypothesis_report_template.tex` 中的 template 生成专业 LaTeX document。Report 应有良好格式，用 colored boxes 组织视觉结构，并分为简洁 main text 与综合 appendices。

**Document Structure：**

**Main Text（最多 4 pages）：**
1. **Executive Summary** - Summary box 中的简短概述（0.5-1 page）
2. **Competing Hypotheses** - 每个 hypothesis 放在自己的 colored box 中，包含简短 mechanistic explanation 和 key evidence（3-5 个 hypotheses 共 2-2.5 pages）
   - **IMPORTANT:** 在每个 hypothesis box 前使用 `\newpage`，防止 content overflow
   - 每个 box 应 ≤0.6 pages
3. **Testable Predictions** - Amber boxes 中的 key predictions（0.5-1 page）
4. **Critical Comparisons** - Priority comparison boxes（0.5-1 page）

保持 main text 高度简洁，只保留最核心信息。所有细节放入 appendices。

**Page Break Strategy：**
- 始终在 hypothesis boxes 前使用 `\newpage`，确保其从新页面开始
- 这可防止 content 溢出 page boundaries
- LaTeX boxes（tcolorbox）不会自动跨页断开

**Appendices（Comprehensive, Detailed）：**
- **Appendix A:** Comprehensive literature review，含 extensive citations
- **Appendix B:** Detailed experimental designs，含 full protocols
- **Appendix C:** Quality assessment tables 和 detailed evaluations
- **Appendix D:** Supplementary evidence 和 analogous systems

**Colored Box Usage：**

使用 `hypothesis_generation.sty` 中的 custom box environments：

- `hypothesisbox1` through `hypothesisbox5` - 用于各 competing hypothesis（blue、green、purple、teal、orange）
- `predictionbox` - 用于 testable predictions（amber）
- `comparisonbox` - 用于 critical comparisons（steel gray）
- `evidencebox` - 用于 supporting evidence highlights（light blue）
- `summarybox` - 用于 executive summary（blue）

**每个 hypothesis box 应包含（为 4-page limit 保持简洁）：**
- **Mechanistic Explanation:** 1-2 个简短 paragraphs（最多 6-10 sentences）解释 HOW 和 WHY
- **Key Supporting Evidence:** 带 citations 的 2-3 个 bullet points（仅最重要 evidence）
- **Core Assumptions:** 1-2 个 critical assumptions

所有详细 explanations、additional evidence 和 comprehensive discussions 都应放在 appendices。

**Critical Overflow Prevention：**
- 在每个 hypothesis box 前插入 `\newpage`，从新页面开始
- 每个完整 hypothesis box 控制在 ≤0.6 pages（约 15-20 行内容）
- 如果 content 超出，将 additional details 移至 Appendix A
- 绝不要让 boxes 溢出 page boundaries，这会生成不可读 PDFs

**Citation Requirements：**

目标是用 extensive citation 支撑所有 claims：
- **Main text:** 对最重要 evidence 使用 10-15 个 key citations（为 4-page limit 保持简洁）
- **Appendix A:** 覆盖所有相关 literature 的 40-70+ comprehensive citations
- **Total target:** Bibliography 中 50+ references

Main text citations 应有选择性，只引用最关键 papers。所有 comprehensive citation 和 detailed literature discussion 放在 appendices。Parenthetical citations 使用 `\citep{author2023}`。

**LaTeX Compilation：**

Template 需要 XeLaTeX 或 LuaLaTeX 才能正确渲染：

```bash
xelatex hypothesis_report.tex
bibtex hypothesis_report
xelatex hypothesis_report.tex
xelatex hypothesis_report.tex
```

**Required packages:** `hypothesis_generation.sty` style package 必须在同一 directory 或 LaTeX path 中。它需要：tcolorbox、xcolor、fontspec、fancyhdr、titlesec、enumitem、booktabs、natbib。

**Page Overflow Prevention：**

为防止 content 在页面上溢出，遵循这些关键指南：

1. **Monitor Box Content Length:** 每个 hypothesis box 应舒适地放在单页内。如果 content 超过约 0.7 pages，很可能 overflow。

2. **Use Strategic Page Breaks:** 在包含大量内容的 boxes 前插入 `\newpage`：
   ```latex
   \newpage
   \begin{hypothesisbox1}[Hypothesis 1: Title]
   % Long content here
   \end{hypothesisbox1}
   ```

3. **Keep Main Text Boxes Concise:** 对于 4-page main text limit：
   - 每个 hypothesis box：最多 0.5-0.6 pages
   - Mechanistic explanation：仅 1-2 个简短 paragraphs（最多 6-10 sentences）
   - Key evidence：仅 2-3 个 bullet points
   - Core assumptions：仅 1-2 项
   - 如果 content 更长，将细节移到 appendices

4. **Break Long Content:** 如果一个 hypothesis 需要大量解释，将其拆分到 main text 和 appendix：
   - Main text box：简要 mechanistic overview + 2-3 个 key evidence points
   - Appendix A：Detailed mechanism explanation、comprehensive evidence、extended discussion

5. **Test Page Boundaries:** 在每个新 box 前，考虑剩余 page space 是否足够。如果剩余不足 0.6 pages，使用 `\newpage` 从新页面开始 box。

6. **Appendix Page Management:** 在 appendices 中，major sections 之间使用 `\newpage`，避免 detailed content areas 中 overflow。

**Quick Reference：** 所有 box types、color schemes 和 common formatting patterns 的详细示例见 `assets/FORMATTING_GUIDE.md`。

## Quality Standards

确保所有生成 hypotheses 满足这些标准：

- **Evidence-based:** 基于现有 literature，并带 citations
- **Testable:** 包含具体、可测量 predictions
- **Mechanistic:** 解释 how/why，而不只是 what
- **Comprehensive:** 考虑 alternative explanations
- **Rigorous:** 包含用于测试 predictions 的 experimental designs

## 资源

### references/

- `hypothesis_quality_criteria.md` - 评估 hypothesis quality 的 framework（testability、falsifiability、parsimony、explanatory power、scope、consistency）
- `experimental_design_patterns.md` - 跨 domains 的常见 experimental approaches（RCTs、observational studies、lab experiments、computational models）
- `literature_search_strategies.md` - PubMed 和 general scientific sources 的有效 search techniques

### assets/

- `hypothesis_generation.sty` - LaTeX style package，提供 colored boxes、professional formatting，以及 hypothesis reports 的 custom environments
- `hypothesis_report_template.tex` - 完整 LaTeX template，包含 main text structure 和 comprehensive appendix sections
- `FORMATTING_GUIDE.md` - Quick reference guide，包含所有 box types、color schemes、citation practices 和 troubleshooting tips 示例

### Related Skills

准备 hypothesis-driven research 用于 publication 时，请查阅 **venue-templates** skill 获取 writing style guidance：
- `venue_writing_styles.md` - 比较不同 venues 风格的 master guide
- Nature/Science、Cell Press、medical journals 和 ML/CS conferences 的 venue-specific guides
- `reviewer_expectations.md` - Reviewers 在评估 research hypotheses 时关注什么
