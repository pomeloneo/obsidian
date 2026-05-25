---
name: scientific-writing
description: Deep research and writing tool 的 core skill。以完整段落撰写 scientific manuscripts（绝不用 bullet points 作为终稿）。使用两阶段流程：（1）通过 research-lookup 创建含 key points 的 section outlines；（2）转换为流畅 prose。涵盖 IMRAD structure、citations（APA/AMA/Vancouver）、figures/tables、reporting guidelines（CONSORT/STROBE/PRISMA），用于 research papers 和 journal submissions。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scientific Writing

## 概述

**这是 deep research and writing tool 的 core skill**，将 AI-driven deep research 与格式良好的 written outputs 结合。每份生成文档都通过 research-lookup skill 进行 comprehensive literature search 和 verified citations 支撑。

Scientific writing 是以 precision 和 clarity 传播 research 的过程。使用 IMRAD structure、citations（APA/AMA/Vancouver）、figures/tables 和 reporting guidelines（CONSORT/STROBE/PRISMA）撰写 manuscripts。将此 skill 用于 research papers 和 journal submissions。

**关键原则：始终使用完整段落和流畅 prose。终稿 manuscript 中绝不要提交 bullet points。** 使用两阶段流程：先用 research-lookup 创建带 key points 的 section outlines，再将这些 outlines 转换为完整 paragraphs。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 撰写或修改 scientific manuscript 的任意 section（abstract、introduction、methods、results、discussion）
- 使用 IMRAD 或其他 standard formats 组织 research paper
- 按特定 styles（APA、AMA、Vancouver、Chicago、IEEE）格式化 citations 和 references
- 创建、格式化或改进 figures、tables 和 data visualizations
- 应用 study-specific reporting guidelines（trials 用 CONSORT、observational studies 用 STROBE、reviews 用 PRISMA）
- 撰写符合 journal requirements 的 abstracts（structured 或 unstructured）
- 为特定 journals 准备 manuscripts
- 改进 writing clarity、conciseness 和 precision
- 确保正确使用 field-specific terminology 和 nomenclature
- 回应 reviewer comments 并修改 manuscripts

## 使用 Scientific Schematics 增强视觉表达

**⚠️ 强制要求：每篇 scientific paper 都必须包含 graphical abstract，并使用 scientific-schematics skill 额外生成 1-2 张 AI-generated figures。**

这不是可选项。没有视觉元素的 scientific papers 是不完整的。定稿任何文档前：
1. **始终先生成 graphical abstract** 作为第一个视觉元素
2. 至少再使用 scientific-schematics 生成一张 additional schematic 或 diagram
3. 对综合性 papers，优先使用 3-4 张 total figures（graphical abstract + methods flowchart + results visualization + conceptual diagram）

### Graphical Abstract（必需）

**每份 scientific writeup 都必须包含 graphical abstract。** 这是 paper 的视觉摘要，应：
- 出现在 text abstract 之前或之后
- 用一张 image 捕捉整篇 paper 的 key message
- 适合作为 journal table of contents display
- 使用 landscape orientation（通常 1200x600px）

**首先生成 graphical abstract：**
```bash
python scripts/generate_schematic.py "Graphical abstract for [paper title]: [brief description showing workflow from input → methods → key findings → conclusions]" -o figures/graphical_abstract.png
```

**Graphical Abstract Requirements：**
- **Content**：展示 workflow、key methods、main findings 和 conclusions 的视觉摘要
- **Style**：Clean、professional，适合 journal TOC
- **Elements**：包含 3-5 个 key steps/concepts，用 arrows 或 flow 连接
- **Text**：Minimal labels，大而可读的 fonts
- Log：`[HH:MM:SS] GENERATED: Graphical abstract for paper summary`

### Additional Figures（大量生成）

**⚠️ 关键：在所有 documents 中大量使用 scientific-schematics 和 generate-image。**

每份文档都应有丰富插图。大胆生成 figures；不确定时就添加 visual。

**MINIMUM Figure Requirements：**

| Document Type | Minimum | Recommended |
|--------------|---------|-------------|
| Research Papers | 5 | 6-8 |
| Literature Reviews | 4 | 5-7 |
| Market Research | 20 | 25-30 |
| Presentations | 1/slide | 1-2/slide |
| Posters | 6 | 8-10 |
| Grants | 4 | 5-7 |
| Clinical Reports | 3 | 4-6 |

**大量使用 scientific-schematics 生成 technical diagrams：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

- Study design 和 methodology flowcharts（CONSORT、PRISMA、STROBE）
- Conceptual framework diagrams
- Experimental workflow illustrations
- Data analysis pipeline diagrams
- Biological pathway 或 mechanism diagrams
- System architecture visualizations
- Neural network architectures
- Decision trees、algorithm flowcharts
- Comparison matrices、timeline diagrams
- 任何受益于 schematic visualization 的 technical concept

**大量使用 generate-image 生成 visual content：**
```bash
python scripts/generate_image.py "your image description" -o figures/output.png
```

- Concepts 的 photorealistic illustrations
- Medical/anatomical illustrations
- Environmental/ecological scenes
- Equipment 和 lab setup visualizations
- Artistic visualizations、infographics
- Cover images、header graphics
- Product mockups、prototype visualizations
- 任何增强理解或 engagement 的 visual

AI 会自动：
- 创建具有正确格式的 publication-quality images
- 通过多轮迭代 review 和 refine
- 确保 accessibility（colorblind-friendly、高对比度）
- 将输出保存到 figures/ 目录

**不确定时就生成 Figure：**
- Complex concept → generate a schematic
- Data discussion → generate a visualization
- Process description → generate a flowchart
- Comparison → generate a comparison diagram
- Reader benefit → generate a visual

详细指导请参考 scientific-schematics 和 generate-image skill 文档。

---

## 核心能力

### 1. Manuscript Structure and Organization

**IMRAD Format**：引导 papers 使用多数 scientific disciplines 的标准 Introduction、Methods、Results、And Discussion 结构。这包括：
- **Introduction**：建立 research context、识别 gaps、陈述 objectives
- **Methods**：详细说明 study design、populations、procedures 和 analysis approaches
- **Results**：客观呈现 findings，不做 interpretation
- **Discussion**：解释 results、承认 limitations、提出 future directions

IMRAD structure 的详细指导见 `references/imrad_structure.md`。

**Alternative Structures**：支持 discipline-specific formats，包括：
- Review articles（narrative、systematic、scoping）
- Case reports 和 case series
- Meta-analyses 和 pooled analyses
- Theoretical/modeling papers
- Methods papers 和 protocols

### 2. Section-Specific Writing Guidance

**Abstract Composition**：撰写 concise、standalone summaries（100-250 words），概括 paper 的 purpose、methods、results 和 conclusions。支持 structured abstracts（带 labeled sections）和 unstructured single-paragraph formats。

**Introduction Development**：构建有说服力的 introductions：
- 确立 research problem 的重要性
- 系统回顾 relevant literature
- 识别 knowledge gaps 或 controversies
- 陈述清晰 research questions 或 hypotheses
- 解释 study 的 novelty 和 significance

**Methods Documentation**：通过以下方式确保 reproducibility：
- 详细 participant/sample descriptions
- 清晰 procedural documentation
- 带 justification 的 statistical methods
- Equipment 和 materials specifications
- Ethical approval 和 consent statements

**Results Presentation**：呈现 findings 时：
- 从 primary 到 secondary outcomes 保持 logical flow
- 与 figures 和 tables 整合
- 报告 statistical significance 和 effect sizes
- 客观报告，不做 interpretation

**Discussion Construction**：通过以下方式综合 findings：
- 将 results 与 research questions 联系起来
- 与 existing literature 比较
- 诚实承认 limitations
- 提出 mechanistic explanations
- 建议 practical implications 和 future research

### 3. Citation and Reference Management

在不同 disciplines 中正确应用 citation styles。完整 style guides 见 `references/citation_styles.md`。

**Major Citation Styles：**
- **AMA (American Medical Association)**：Numbered superscript citations，常见于 medicine
- **Vancouver**：方括号内 numbered citations，biomedical standard
- **APA (American Psychological Association)**：Author-date in-text citations，常见于 social sciences
- **Chicago**：Notes-bibliography 或 author-date，humanities 和 sciences
- **IEEE**：Numbered square brackets，engineering 和 computer science

**Best Practices：**
- 尽可能引用 primary sources
- 包含 recent literature（active fields 通常最近 5-10 年）
- 平衡 introduction 和 discussion 中的 citation distribution
- 对照 original sources 验证所有 citations
- 使用 reference management software（Zotero、Mendeley、EndNote）

### 4. Figures and Tables

创建增强理解的 effective data visualizations。详细 best practices 见 `references/figures_tables.md`。

**何时使用 Tables vs. Figures：**
- **Tables**：精确 numerical data、complex datasets、需要 exact values 的 multiple variables
- **Figures**：最好视觉理解的 trends、patterns、relationships、comparisons

**Design Principles：**
- 每个 table/figure 都用完整 caption 自解释
- 所有 display items 使用一致 formatting 和 terminology
- 所有 axes、columns 和 rows 标注 units
- 包含 sample sizes（n）和 statistical annotations
- 遵循 "one table/figure per 1000 words" 指南
- 避免在 text、tables 和 figures 之间重复信息

**Common Figure Types：**
- Bar graphs：比较 discrete categories
- Line graphs：显示 over time trends
- Scatterplots：展示 correlations
- Box plots：展示 distributions 和 outliers
- Heatmaps：可视化 matrices 和 patterns

### 5. Reporting Guidelines by Study Type

通过遵循 established reporting standards 确保 completeness 和 transparency。完整 guideline 细节见 `references/reporting_guidelines.md`。

**Key Guidelines：**
- **CONSORT**：Randomized controlled trials
- **STROBE**：Observational studies（cohort、case-control、cross-sectional）
- **PRISMA**：Systematic reviews 和 meta-analyses
- **STARD**：Diagnostic accuracy studies
- **TRIPOD**：Prediction model studies
- **ARRIVE**：Animal research
- **CARE**：Case reports
- **SQUIRE**：Quality improvement studies
- **SPIRIT**：Clinical trials 的 study protocols
- **CHEERS**：Economic evaluations

每个 guideline 都提供 checklist，确保所有 critical methodological elements 被报告。

### 6. Writing Principles and Style

应用 fundamental scientific writing principles。详细指导见 `references/writing_principles.md`。

**Clarity**：
- 使用 precise、unambiguous language
- 在首次使用时定义 technical terms 和 abbreviations
- 保持 paragraphs 内和 paragraphs 间的 logical flow
- 适当使用 active voice 以提高清晰度

**Conciseness**：
- 删除 redundant words 和 phrases
- 倾向较短 sentences（平均 15-20 words）
- 删除不必要 qualifiers
- 严格遵守 word limits

**Accuracy**：
- 用合适 precision 报告 exact values
- 全文使用一致 terminology
- 区分 observations 和 interpretations
- 恰当地承认 uncertainty

**Objectivity**：
- 不带 bias 地呈现 results
- 避免夸大 findings 或 implications
- 承认 conflicting evidence
- 保持 professional、neutral tone

### 7. Writing Process: From Outline to Full Paragraphs

**关键：始终写完整段落，scientific papers 中终稿不要提交 bullet points。**

Scientific papers 必须写成完整、流动的 prose。使用以下两阶段方法高效写作：

**Stage 1: Create Section Outlines with Key Points**

开始新 section 时：
1. 使用 research-lookup skill 收集 relevant literature 和 data
2. 创建 structured outline，用 bullet points 标记：
   - 要呈现的 main arguments 或 findings
   - 要引用的 key studies
   - 要包含的 data points 和 statistics
   - Logical flow 和 organization
3. 这些 bullet points 只是 scaffolding，不是最终 manuscript

**Example outline（Introduction section）：**
```
- Background: AI in drug discovery gaining traction
  * Cite recent reviews (Smith 2023, Jones 2024)
  * Traditional methods are slow and expensive
- Gap: Limited application to rare diseases
  * Only 2 prior studies (Lee 2022, Chen 2023)
  * Small datasets remain a challenge
- Our approach: Transfer learning from common diseases
  * Novel architecture combining X and Y
- Study objectives: Validate on 3 rare disease datasets
```

**Stage 2: Convert Key Points to Full Paragraphs**

Outline 完成后，将每个 bullet point 扩展为 proper prose：

1. **将 bullet points 转换为 complete sentences**，包含 subjects、verbs 和 objects
2. **在 sentences 和 ideas 之间添加 transitions**（however、moreover、in contrast、subsequently）
3. **自然整合 citations**，不要写成列表
4. **补充 bullet points 省略的 context 和 explanation**
5. **确保每个 paragraph 中从一句到下一句 logical flow**
6. **变化 sentence structure**，保持 reader engagement

**Example conversion to prose：**

```
Artificial intelligence approaches have gained significant traction in drug discovery 
pipelines over the past decade (Smith, 2023; Jones, 2024). While these computational 
methods show promise for accelerating the identification of therapeutic candidates, 
traditional experimental approaches remain slow and resource-intensive, often requiring 
years of laboratory work and substantial financial investment. However, the application 
of AI to rare diseases has been limited, with only two prior studies demonstrating 
proof-of-concept results (Lee, 2022; Chen, 2023). The primary obstacle has been the 
scarcity of training data for conditions affecting small patient populations. 

To address this challenge, we developed a transfer learning approach that leverages 
knowledge from well-characterized common diseases to predict therapeutic targets for 
rare conditions. Our novel neural architecture combines convolutional layers for 
molecular feature extraction with attention mechanisms for protein-ligand interaction 
modeling. The objective of this study was to validate our approach across three 
independent rare disease datasets, assessing both predictive accuracy and biological 
interpretability of the results.
```

**Key Differences Between Outlines and Final Text：**

| Outline (Planning Stage) | Final Manuscript |
|--------------------------|------------------|
| Bullet points and fragments | Complete sentences and paragraphs |
| Telegraphic notes | Full explanations with context |
| List of citations | Citations integrated into prose |
| Abbreviated ideas | Developed arguments with transitions |
| For your eyes only | For publication and peer review |

**应避免的常见错误：**

- ❌ **绝不要**在 final manuscript 中保留 bullet points
- ❌ **绝不要**在应使用 paragraphs 的地方提交 lists
- ❌ **不要**在 Results 或 Discussion sections 中使用 numbered 或 bulleted lists（除 study hypotheses 或 inclusion criteria 等特定情况外）
- ❌ **不要**写 sentence fragments 或 incomplete thoughts
- ✅ **可以**仅在 Methods 中偶尔使用 lists（例如 inclusion/exclusion criteria、materials lists）
- ✅ **要**确保每个 section 都作为 connected prose 流动
- ✅ **要**朗读 paragraphs，检查自然 flow

**Lists 可接受的有限情况：**

Scientific papers 中 lists 只应出现在特定 contexts：
- **Methods**：Inclusion/exclusion criteria、materials and reagents、participant characteristics
- **Supplementary Materials**：Extended protocols、equipment lists、detailed parameters
- **绝不用于**：Abstract、Introduction、Results、Discussion、Conclusions

**Abstract Format Rule：**
- ❌ **绝不要**使用 labeled sections（Background:、Methods:、Results:、Conclusions:）
- ✅ **始终**写成带 natural transitions 的 flowing paragraph(s)
- 例外：只有当 journal author guidelines 明确要求 structured format 时才使用

**Integration with Research Lookup：**

Research-lookup skill 对 Stage 1（creating outlines）必不可少：
1. 使用 research-lookup 搜索 relevant papers
2. 提取 key findings、methods 和 data
3. 将 findings 组织为 outline 中的 bullet points
4. 然后在 Stage 2 中将 outline 转换为 full paragraphs

此两阶段流程确保你：
- 系统收集并组织 information
- 写作前创建 logical structure
- 产出 polished、publication-ready prose
- 保持 narrative flow

### 8. Professional Report Formatting（Non-Journal Documents）

对于 research reports、technical reports、white papers 和其他非 journal manuscripts 的 professional documents，使用 `scientific_report.sty` LaTeX style package，以获得 polished、professional appearance。

**何时使用 Professional Report Formatting：**
- Research reports 和 technical reports
- White papers 和 policy briefs
- Grant reports 和 progress reports
- Industry reports 和 technical documentation
- Internal research summaries
- Feasibility studies 和 project deliverables

**何时不使用（改用 Venue-Specific Formatting）：**
- Journal manuscripts → 使用 `venue-templates` skill
- Conference papers → 使用 `venue-templates` skill
- Academic theses → 使用 institutional templates

**`scientific_report.sty` Style Package 提供：**

| Feature | Description |
|---------|-------------|
| Typography | Helvetica font family，现代 professional appearance |
| Color Scheme | Professional blues、greens 和 accent colors |
| Box Environments | Key findings、methods、recommendations、limitations 的 colored boxes |
| Tables | Alternating row colors、professional headers |
| Figures | Consistent caption formatting |
| Scientific Commands | P-values、effect sizes、confidence intervals 的 shortcuts |

**用于 Content Organization 的 Box Environments：**

```latex
% Key findings (blue) - for major discoveries
\begin{keyfindings}[Title]
Content with key findings and statistics.
\end{keyfindings}

% Methodology (green) - for methods highlights
\begin{methodology}[Study Design]
Description of methods and procedures.
\end{methodology}

% Recommendations (purple) - for action items
\begin{recommendations}[Clinical Implications]
\begin{enumerate}
    \item Specific recommendation 1
    \item Specific recommendation 2
\end{enumerate}
\end{recommendations}

% Limitations (orange) - for caveats and cautions
\begin{limitations}[Study Limitations]
Description of limitations and their implications.
\end{limitations}
```

**Professional Table Formatting：**

```latex
\begin{table}[htbp]
\centering
\caption{Results Summary}
\begin{tabular}{@{}lccc@{}}
\toprule
\textbf{Variable} & \textbf{Treatment} & \textbf{Control} & \textbf{p} \\
\midrule
Outcome 1 & \meansd{42.5}{8.3} & \meansd{35.2}{7.9} & <.001\sigthree \\
\rowcolor{tablealt} Outcome 2 & \meansd{3.8}{1.2} & \meansd{3.1}{1.1} & .012\sigone \\
Outcome 3 & \meansd{18.2}{4.5} & \meansd{17.8}{4.2} & .58\signs \\
\bottomrule
\end{tabular}

{\small \siglegend}
\end{table}
```

**Scientific Notation Commands：**

| Command | Output | Purpose |
|---------|--------|---------|
| `\pvalue{0.023}` | *p* = 0.023 | P-values |
| `\psig{< 0.001}` | ***p* = < 0.001** | Significant p-values (bold) |
| `\CI{0.45}{0.72}` | 95% CI [0.45, 0.72] | Confidence intervals |
| `\effectsize{d}{0.75}` | d = 0.75 | Effect sizes |
| `\samplesize{250}` | *n* = 250 | Sample sizes |
| `\meansd{42.5}{8.3}` | 42.5 ± 8.3 | Mean with SD |
| `\sigone`, `\sigtwo`, `\sigthree` | *, **, *** | Significance stars |

**Getting Started：**

```latex
\documentclass[11pt,letterpaper]{report}
\usepackage{scientific_report}

\begin{document}
\makereporttitle
    {Report Title}
    {Subtitle}
    {Author Name}
    {Institution}
    {Date}

% Your content with professional formatting
\end{document}
```

**Compilation**：使用 XeLaTeX 或 LuaLaTeX 以正确渲染 Helvetica font：
```bash
xelatex report.tex
```

完整文档请参考：
- `assets/scientific_report.sty`：Style package
- `assets/scientific_report_template.tex`：完整 template example
- `assets/REPORT_FORMATTING_GUIDE.md`：Quick reference guide
- `references/professional_report_formatting.md`：Comprehensive formatting guide

### 9. Journal-Specific Formatting

使 manuscripts 适配 journal requirements：
- 遵循 author guidelines 中的 structure、length 和 format
- 应用 journal-specific citation styles
- 满足 figure/table specifications（resolution、file formats、dimensions）
- 包含 required statements（funding、conflicts of interest、data availability、ethical approval）
- 遵守各 section 的 word limits
- 如提供 template，则按 template requirements 格式化

### 10. Field-Specific Language and Terminology

根据具体 scientific discipline 调整 language、terminology 和 conventions。每个 field 都有 established vocabulary、preferred phrasings 和 domain-specific conventions，用于传达 expertise 并确保 target audience 清楚理解。

**识别 Field-Specific Linguistic Conventions：**
- Review target journal 近期 high-impact papers 中使用的 terminology
- 注意 field-specific abbreviations、units 和 notation systems
- 识别 preferred terms（例如 "participants" vs. "subjects," "compound" vs. "drug," "specimens" vs. "samples"）
- 观察 methods、organisms 或 techniques 通常如何描述

**Biomedical and Clinical Sciences：**
- 使用精确 anatomical 和 clinical terminology（例如正式写作中用 "myocardial infarction" 而不是 "heart attack"）
- 遵循 standardized disease nomenclature（ICD、DSM、SNOMED-CT）
- Drug names 先使用 generic names，必要时括号中加 brand names
- Clinical studies 用 "patients"，community-based research 用 "participants"
- Genetic variants 遵循 Human Genome Variation Society（HGVS）nomenclature
- 使用 standard units 报告 lab values（多数 international journals 使用 SI units）

**Molecular Biology and Genetics：**
- Gene symbols 使用 italics（例如 *TP53*），proteins 使用 regular font（例如 p53）
- 遵循 species-specific gene nomenclature（human 大写：*BRCA1*；mouse sentence case：*Brca1*）
- Organism names 首次出现时写全，之后使用 accepted abbreviations（例如 *Escherichia coli*，之后 *E. coli*）
- 使用 standard genetic notation（例如 +/+、+/-、-/- 表示 genotypes）
- 对 molecular techniques 使用 established terminology（例如 "quantitative PCR" 或 "qPCR"，而不是 "real-time PCR"）

**Chemistry and Pharmaceutical Sciences：**
- 化合物遵循 IUPAC nomenclature
- Novel compounds 使用 systematic names，well-known substances 使用 common names
- 用 standard notation 指定 chemical structures（例如 databases 用 SMILES、InChI）
- 用合适 units 报告 concentrations（mM、μM、nM 或 % w/v、v/v）
- 使用 accepted reaction nomenclature 描述 synthesis routes
- 使用 "bioavailability," "pharmacokinetics," "IC50" 等术语时保持与 field definitions 一致

**Ecology and Environmental Sciences：**
- Species 使用 binomial nomenclature（italicized：*Homo sapiens*）
- 相关时在首次 species mention 指定 taxonomic authorities
- 使用 standardized habitat 和 ecosystem classifications
- 对 ecological metrics 使用一致 terminology（例如 "species richness," "Shannon diversity index"）
- 用 field-standard terms 描述 sampling methods（例如 "transect," "quadrat," "mark-recapture"）

**Physics and Engineering：**
- 除非 field conventions 另有要求，始终使用 SI units
- 使用 standard notation 表示 physical quantities（scalars vs. vectors、tensors）
- 使用 established terminology 描述 phenomena（例如 "quantum entanglement," "laminar flow"）
- 相关时指定 equipment 的 model numbers 和 manufacturers
- 使用与 field standards 一致的 mathematical notation（例如 ℏ 表示 reduced Planck constant）

**Neuroscience：**
- 使用 standardized brain region nomenclature（例如参考 Allen Brain Atlas 等 atlases）
- 使用 established stereotaxic systems 指定 brain regions 的 coordinates
- 遵循 neural terminology conventions（例如 formal writing 中用 "action potential" 而不是 "spike"）
- 根据 measurement method 恰当使用 "neural activity," "neuronal firing," "brain activation"
- 以恰当 specificity 描述 recording techniques（例如 "whole-cell patch clamp," "extracellular recording"）

**Social and Behavioral Sciences：**
- 适当时使用 person-first language（例如 "people with schizophrenia" 而不是 "schizophrenics"）
- 使用 standardized psychological constructs 和 validated assessment names
- 遵循 APA guidelines 以减少 bias in language
- 使用 established terminology 指定 theoretical frameworks
- Human research 使用 "participants" 而非 "subjects"

**General Principles：**

**Match Audience Expertise：**
- Specialized journals：可自由使用 field-specific terminology，仅定义高度 specialized 或 novel terms
- Broad-impact journals（例如 *Nature*、*Science*）：定义更多 technical terms，为 specialized concepts 提供 context
- Interdisciplinary audiences：平衡 precision 与 accessibility，在首次使用时定义 terms

**Define Technical Terms Strategically：**
- 首次使用时定义 abbreviations："messenger RNA (mRNA)"
- 面向 broader audiences 写作时，对 specialized techniques 给出简短解释
- 避免过度定义 target audience 熟知的 terms（会显得不熟悉该领域）
- 如 unavoidable specialized terms 很多，可创建 glossary

**Maintain Consistency：**
- 全文对同一概念使用同一 term（不要在 "medication," "drug," 和 "pharmaceutical" 间切换）
- 对 abbreviations 使用一致系统（首次定义后决定用 "PCR" 或 "polymerase chain reaction"）
- 全文应用同一 nomenclature system（尤其是 genes、species、chemicals）

**Avoid Field Mixing Errors：**
- 不要将 clinical terminology 用于 basic science（例如不要称 mice 为 "patients"）
- 避免用 colloquialisms 或过于笼统 terms 取代 precise field terminology
- 不要从相邻 fields 引入 terminology，除非确认用法正确

**Verify Terminology Usage：**
- 查阅 field-specific style guides 和 nomenclature resources
- 检查 target journal 近期 papers 如何使用 terms
- 使用 domain-specific databases 和 ontologies（例如 Gene Ontology、MeSH terms）
- 不确定时，引用确立 terminology 的 key reference

### 11. Common Pitfalls to Avoid

**Top Rejection Reasons：**
1. Statistics 不合适、不完整或描述不足
2. 对 results 过度解释或 unsupported conclusions
3. Methods 描述差，影响 reproducibility
4. Samples 小、有 bias 或不合适
5. Writing quality 差或 text 难以跟随
6. Literature review 或 context 不充分
7. Figures 和 tables 不清楚或设计差
8. 未遵循 reporting guidelines

**Writing Quality Issues：**
- 不恰当地混用 tenses（methods/results 用 past tense，established facts 用 present）
- Excessive jargon 或 undefined acronyms
- Paragraph breaks 破坏 logical flow
- Sections 间缺少 transitions
- Notation 或 terminology 不一致

## Workflow for Manuscript Development

**Stage 1: Planning**
1. 确定 target journal 并审查 author guidelines
2. 确定适用 reporting guideline（CONSORT、STROBE 等）
3. Outline manuscript structure（通常 IMRAD）
4. 将 figures 和 tables 作为 paper backbone 来规划

**Stage 2: Drafting**（每个 section 使用 two-stage writing process）
1. 从 figures 和 tables 开始（core data story）
2. 对下面每个 section 遵循两阶段流程：
   - **First**：使用 research-lookup 创建 bullet points outline
   - **Second**：将 bullet points 转换为流畅 prose 的 full paragraphs
3. 写 Methods（通常最容易先 draft）
4. Draft Results（客观描述 figures/tables）
5. Compose Discussion（解释 findings）
6. Write Introduction（建立 research question）
7. Craft Abstract（综合完整 story）
8. Create Title（concise and descriptive）

**记住**：Bullet points 只用于规划，final manuscript 必须是完整 paragraphs。

**Stage 3: Revision**
1. 检查全文 logical flow 和 "red thread"
2. 验证 terminology 和 notation 一致性
3. 确保 figures/tables 可自解释
4. 确认遵循 reporting guidelines
5. 验证所有 citations 准确且格式正确
6. 检查每个 section 的 word counts
7. 校对 grammar、spelling 和 clarity

**Stage 4: Final Preparation**
1. 按 journal requirements 格式化
2. 准备 supplementary materials
3. 撰写突出 significance 的 cover letter
4. 完成 submission checklists
5. 收集所有 required statements 和 forms

## 与其他 Scientific Skills 的集成

此 skill 可与以下能力高效配合：
- **Data analysis skills**：生成要报告的 results
- **Statistical analysis**：确定合适 statistical presentations
- **Literature review skills**：为 research 提供 context
- **Figure creation tools**：开发 publication-quality visualizations
- **Venue-templates skill**：用于 venue-specific writing styles 和 formatting（journal manuscripts）
- **scientific_report.sty**：用于 professional reports、white papers 和 technical documents

### Professional Reports vs. Journal Manuscripts

**选择正确 formatting approach：**

| Document Type | Formatting Approach |
|---------------|---------------------|
| Journal manuscripts | Use `venue-templates` skill |
| Conference papers | Use `venue-templates` skill |
| Research reports | Use `scientific_report.sty` (this skill) |
| White papers | Use `scientific_report.sty` (this skill) |
| Technical reports | Use `scientific_report.sty` (this skill) |
| Grant reports | Use `scientific_report.sty` (this skill) |

### Venue-Specific Writing Styles

**为特定 venue 写作前，查阅 venue-templates skill 中的 writing style guides：**

不同 venues 的 writing expectations 差异很大：
- **Nature/Science**：Accessible、story-driven、broad significance
- **Cell Press**：Mechanistic depth、graphical abstracts、Highlights
- **Medical journals（NEJM、Lancet）**：Structured abstracts、evidence language
- **ML conferences（NeurIPS、ICML）**：Contribution bullets、ablation studies
- **CS conferences（CHI、ACL）**：Field-specific conventions

Venue-templates skill 提供：
- `venue_writing_styles.md`：Master style comparison
- Venue-specific guides：`nature_science_style.md`、`cell_press_style.md`、`medical_journal_styles.md`、`ml_conference_style.md`、`cs_conference_style.md`
- `reviewer_expectations.md`：各 venue 的 reviewers 关注点

**Workflow**：先使用此 skill 掌握 general scientific writing principles（IMRAD、clarity、citations），再查阅 venue-templates 进行 venue-specific style adaptation。

## References

此 skill 包含覆盖 scientific writing 特定方面的完整 reference files：

- `references/imrad_structure.md`：IMRAD format 和 section-specific content 的详细指南
- `references/citation_styles.md`：完整 citation style guides（APA、AMA、Vancouver、Chicago、IEEE）
- `references/figures_tables.md`：创建 effective data visualizations 的 best practices
- `references/reporting_guidelines.md`：Study-specific reporting standards 和 checklists
- `references/writing_principles.md`：Effective scientific communication 的核心原则
- `references/professional_report_formatting.md`：使用 `scientific_report.sty` 进行 professional report styling 的指南

## Assets

此 skill 包含用于 professional report formatting 的 LaTeX style packages 和 templates：

- `assets/scientific_report.sty`：Professional LaTeX style package，含 Helvetica fonts、colored boxes 和 attractive tables
- `assets/scientific_report_template.tex`：展示所有 style features 的完整 report template
- `assets/REPORT_FORMATTING_GUIDE.md`：Style package 的 quick reference guide

**`scientific_report.sty` 的 Key Features：**
- Helvetica font family，现代 professional appearance
- Professional color scheme（blues、greens、oranges、purples）
- Box environments：`keyfindings`、`methodology`、`resultsbox`、`recommendations`、`limitations`、`criticalnotice`、`definition`、`executivesummary`、`hypothesis`
- 带 alternating row colors 和 professional headers 的 tables
- P-values、effect sizes、confidence intervals 的 scientific notation commands
- Professional headers and footers

**Venue-specific writing styles**（tone、voice、abstract format、reviewer expectations）见 **venue-templates** skill；其中提供 Nature/Science、Cell Press、medical journals、ML conferences 和 CS conferences 的完整 style guides。

处理 scientific writing 的特定方面时，按需加载这些 references。
