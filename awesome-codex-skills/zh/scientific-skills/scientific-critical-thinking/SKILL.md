---
name: scientific-critical-thinking
description: 评估 scientific claims 和 evidence quality。用于评估 experimental design validity、识别 biases 和 confounders、应用 evidence grading frameworks（GRADE、Cochrane Risk of Bias），或进行 critical analysis 教学。最适合理解 evidence quality、识别 flaws。正式 peer review 写作请使用 peer-review。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scientific Critical Thinking

## 概述

Critical thinking 是评估 scientific rigor 的系统化过程。使用 GRADE 和 Cochrane ROB frameworks 评估 methodology、experimental design、statistical validity、biases、confounding 和 evidence quality。将此 skill 用于 scientific claims 的 critical analysis。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 评估 research methodology 和 experimental design
- 评估 statistical validity 和 evidence quality
- 识别 studies 中的 biases 和 confounding
- 审查 scientific claims 和 conclusions
- 开展 systematic reviews 或 meta-analyses
- 应用 GRADE 或 Cochrane risk of bias assessments
- 对 research papers 提供 critical analysis

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
- Critical thinking framework diagrams
- Bias identification decision trees
- Evidence quality assessment flowcharts
- GRADE assessment methodology diagrams
- Risk of bias evaluation frameworks
- Validity assessment visualizations
- 任何受益于 visualization 的复杂概念

创建 schematics 的详细指导请参考 scientific-schematics skill 文档。

---

## 核心能力

### 1. Methodology Critique

评估 research methodology 的 rigor、validity 和 potential flaws。

**适用于：**
- 审查 research papers
- 评估 experimental designs
- 评估 study protocols
- 规划新研究

**Evaluation framework：**

1. **Study Design Assessment**
   - 设计是否适合 research question？
   - 设计能否支持所提出的 causal claims？
   - Comparison groups 是否合适且充分？
   - 考虑 experimental、quasi-experimental 或 observational design 是否有充分理由

2. **Validity Analysis**
   - **Internal validity：** 我们能否信任 causal inference？
     - 检查 randomization quality
     - 评估 confounding control
     - 评估 selection bias
     - 审查 attrition/dropout patterns
   - **External validity：** 结果是否可 generalize？
     - 评估 sample representativeness
     - 考虑 setting 的 ecological validity
     - 评估 conditions 是否匹配 target application
   - **Construct validity：** Measures 是否捕捉 intended constructs？
     - 审查 measurement validation
     - 检查 operational definitions
     - 评估 measures 是 direct 还是 proxy
   - **Statistical conclusion validity：** Statistical inferences 是否可靠？
     - 验证 adequate power/sample size
     - 检查 assumption compliance
     - 评估 test appropriateness

3. **Control and Blinding**
   - Randomization 是否正确实施（sequence generation、allocation concealment）？
   - Blinding 是否可行并已实施（participants、providers、assessors）？
   - Control conditions 是否合适（placebo、active control、no treatment）？
   - Performance 或 detection bias 是否可能影响结果？

4. **Measurement Quality**
   - Instruments 是否 validated 且 reliable？
   - Measures 是否尽可能 objective，或在 subjective 时承认 limitations？
   - Outcome assessment 是否 standardized？
   - 是否使用 multiple measures triangulate findings？

**参考：** 详细原则见 `references/scientific_method.md`，完整 design checklist 见 `references/experimental_design.md`。

### 2. Bias Detection

识别并评估可能扭曲 findings 的 bias 来源。

**适用于：**
- 审查 published research
- 设计新 studies
- 解读 conflicting evidence
- 评估 research quality

**Systematic bias review：**

1. **Cognitive Biases（Researcher）**
   - **Confirmation bias：** 是否只突出 supporting findings？
   - **HARKing：** Hypotheses 是 a priori 陈述，还是看到结果后形成？
   - **Publication bias：** Literature 中是否缺少 negative results？
   - **Cherry-picking：** Evidence 是否被选择性报告？
   - 检查 preregistration 和 analysis plan transparency

2. **Selection Biases**
   - **Sampling bias：** Sample 是否代表 target population？
   - **Volunteer bias：** Participants 是否以系统性方式 self-select？
   - **Attrition bias：** Dropout 是否在 groups 间不同？
   - **Survivorship bias：** Sample 中是否只看得到 "survivors"？
   - 检查 participant flow diagrams，并比较 baseline characteristics

3. **Measurement Biases**
   - **Observer bias：** Expectations 是否可能影响 observations？
   - **Recall bias：** Retrospective reports 是否系统性不准确？
   - **Social desirability：** Responses 是否偏向可接受答案？
   - **Instrument bias：** Measurement tools 是否系统性出错？
   - 评估 blinding、validation 和 measurement objectivity

4. **Analysis Biases**
   - **P-hacking：** 是否进行了多次 analyses 直到出现 significance？
   - **Outcome switching：** 是否用 significant outcomes 替换 non-significant outcomes？
   - **Selective reporting：** 是否报告所有 planned analyses？
   - **Subgroup fishing：** Subgroup analyses 是否未经 correction？
   - 检查 study registration，并与 published outcomes 比较

5. **Confounding**
   - 哪些 variables 可能同时影响 exposure 和 outcome？
   - Confounders 是否被 measured 并 controlled（统计上或设计上）？
   - Unmeasured confounding 是否可能解释 findings？
   - 是否存在 plausible alternative explanations？

**参考：** 包含 detection 和 mitigation strategies 的完整 bias taxonomy 见 `references/common_biases.md`。

### 3. Statistical Analysis Evaluation

批判性评估 statistical methods、interpretation 和 reporting。

**适用于：**
- 审查 quantitative research
- 评估 data-driven claims
- 评估 clinical trial results
- 审查 meta-analyses

**Statistical review checklist：**

1. **Sample Size and Power**
   - 是否进行 a priori power analysis？
   - Sample 是否足以检测 meaningful effects？
   - Study 是否 underpowered（常见问题）？
   - Small samples 中的 significant results 是否提示 inflated effect sizes 风险？

2. **Statistical Tests**
   - Tests 是否适合 data type 和 distribution？
   - Test assumptions 是否 checked 且 met？
   - Parametric tests 是否有理由，还是应使用 non-parametric alternatives？
   - Analysis 是否匹配 study design（例如 paired vs. independent）？

3. **Multiple Comparisons**
   - 是否测试 multiple hypotheses？
   - 是否应用 correction（Bonferroni、FDR 或其他）？
   - Primary outcomes 是否与 secondary/exploratory 区分？
   - Findings 是否可能是 multiple testing 产生的 false positives？

4. **P-Value Interpretation**
   - P-values 是否正确解释（null 为真时观察到数据的概率）？
   - Non-significance 是否被错误解释为 "no effect"？
   - Statistical significance 是否与 practical importance 混同？
   - 是否报告 exact p-values，还是只报告 "p < .05"？
   - 是否存在刚好低于 .05 的 suspicious clustering？

5. **Effect Sizes and Confidence Intervals**
   - 是否在 significance 之外报告 effect sizes？
   - 是否提供 confidence intervals 以显示 precision？
   - Effect size 在实际意义上是否 meaningful？
   - Standardized effect sizes 是否结合 field-specific context 解读？

6. **Missing Data**
   - 缺失多少 data？
   - 是否考虑 missing data mechanism（MCAR、MAR、MNAR）？
   - 如何处理 missing data（deletion、imputation、maximum likelihood）？
   - Missing data 是否可能 bias results？

7. **Regression and Modeling**
   - Model 是否 overfitted（predictors 过多、无 cross-validation）？
   - 是否在 data range 外做 predictions（extrapolation）？
   - 是否处理 multicollinearity issues？
   - 是否检查 model assumptions？

8. **Common Pitfalls**
   - 将 correlation 视为 causation
   - 忽视 regression to the mean
   - Base rate neglect
   - Texas sharpshooter fallacy（在 noise 中找 pattern）
   - Simpson's paradox（由 subgroups 造成的 confounding）

**参考：** 详细 pitfalls 和 correct practices 见 `references/statistical_pitfalls.md`。

### 4. Evidence Quality Assessment

系统评估 evidence 的 strength 和 quality。

**适用于：**
- 为 decisions 权衡 evidence
- 开展 literature reviews
- 比较 conflicting findings
- 判断对 conclusions 的 confidence

**Evidence evaluation framework：**

1. **Study Design Hierarchy**
   - Systematic reviews/meta-analyses（对 intervention effects 通常最高）
   - Randomized controlled trials
   - Cohort studies
   - Case-control studies
   - Cross-sectional studies
   - Case series/reports
   - Expert opinion（最低）

   **重要：** 更高层级的 designs 并不总是质量更好。设计良好的 observational study 可能强于执行较差的 RCT。

2. **Quality Within Design Type**
   - Risk of bias assessment（使用合适工具：Cochrane ROB、Newcastle-Ottawa 等）
   - Methodological rigor
   - Transparency 和 reporting completeness
   - Conflicts of interest

3. **GRADE Considerations（如适用）**
   - 从 design type 开始（RCT = high，observational = low）
   - **Downgrade for：**
     - Risk of bias
     - Studies 间 inconsistency
     - Indirectness（错误 population/intervention/outcome）
     - Imprecision（wide confidence intervals、small samples）
     - Publication bias
   - **Upgrade for：**
     - Large effect sizes
     - Dose-response relationships
     - Confounders would reduce（not increase）effect

4. **Convergence of Evidence**
   - **更强，当：**
     - Multiple independent replications
     - 不同 research groups 和 settings
     - 不同 methodologies 指向同一 conclusion
     - Mechanistic 和 empirical evidence 对齐
   - **更弱，当：**
     - Single study 或 research group
     - Literature 中 findings 矛盾
     - Publication bias 明显
     - 无 replication attempts

5. **Contextual Factors**
   - Biological/theoretical plausibility
   - 与 established knowledge 的一致性
   - Temporality（cause precedes effect）
   - Relationship 的 specificity
   - Association 的 strength

**参考：** 详细 hierarchy、GRADE system 和 quality assessment tools 见 `references/evidence_hierarchy.md`。

### 5. Logical Fallacy Identification

检测并命名 scientific arguments 和 claims 中的 logical errors。

**适用于：**
- 评估 scientific claims
- 审查 discussion/conclusion sections
- 评估 popular science communication
- 识别 flawed reasoning

**科学中的常见 fallacies：**

1. **Causation Fallacies**
   - **Post hoc ergo propter hoc：** "B followed A, so A caused B"
   - **Correlation = causation：** 将 association 与 causality 混淆
   - **Reverse causation：** 将 cause 和 effect 颠倒
   - **Single cause fallacy：** 将复杂 outcomes 归因于一个 factor

2. **Generalization Fallacies**
   - **Hasty generalization：** 从 small samples 得出 broad conclusions
   - **Anecdotal fallacy：** 将 personal stories 当作 proof
   - **Cherry-picking：** 只选择 supporting evidence
   - **Ecological fallacy：** 将 group patterns 应用于 individuals

3. **Authority and Source Fallacies**
   - **Appeal to authority：** "Expert said it, so it's true"（没有 evidence）
   - **Ad hominem：** 攻击 person，而非 argument
   - **Genetic fallacy：** 按 origin 而非 merits 判断
   - **Appeal to nature：** "Natural = good/safe"

4. **Statistical Fallacies**
   - **Base rate neglect：** 忽视 prior probability
   - **Texas sharpshooter：** 在 random data 中寻找 patterns
   - **Multiple comparisons：** 未对 multiple tests 做 correction
   - **Prosecutor's fallacy：** 混淆 P(E|H) 和 P(H|E)

5. **Structural Fallacies**
   - **False dichotomy：** 当存在更多 options 时声称 "Either A or B"
   - **Moving goalposts：** 达到 evidence standards 后改变标准
   - **Begging the question：** Circular reasoning
   - **Straw man：** 歪曲 arguments 后攻击

6. **Science-Specific Fallacies**
   - **Galileo gambit：** "They laughed at Galileo, so my fringe idea is correct"
   - **Argument from ignorance：** "Not proven false, so true"
   - **Nirvana fallacy：** 拒绝 imperfect solutions
   - **Unfalsifiability：** 提出 untestable claims

**识别 fallacies 时：**
- 命名具体 fallacy
- 解释 reasoning 为何 flawed
- 识别 valid inference 需要什么 evidence
- 注意 fallacious reasoning 并不证明 conclusion 为假，只说明该 argument 不支持它

**参考：** 含 examples 和 detection strategies 的完整 fallacy catalog 见 `references/logical_fallacies.md`。

### 6. Research Design Guidance

为规划 rigorous studies 提供建设性指导。

**适用于：**
- 帮助设计新 experiments
- 规划 research projects
- 审查 research proposals
- 改进 study protocols

**Design process：**

1. **Research Question Refinement**
   - 确保问题 specific、answerable 且 falsifiable
   - 验证它回应 literature 中的 gap 或 contradiction
   - 确认 feasibility（resources、ethics、time）
   - Operationally 定义 variables

2. **Design Selection**
   - 将 design 匹配 question（causal → experimental；associational → observational）
   - 考虑 feasibility 和 ethical constraints
   - 在 between-subjects、within-subjects 或 mixed designs 中选择
   - 如需测试多个 factors，规划 factorial designs

3. **Bias Minimization Strategy**
   - 尽可能实施 randomization
   - 在所有可行层级规划 blinding（participants、providers、assessors）
   - 识别并规划控制 confounds（randomization、matching、stratification、statistical adjustment）
   - 标准化所有 procedures
   - 规划以最小化 attrition

4. **Sample Planning**
   - 进行 a priori power analysis（指定 expected effect、desired power、alpha）
   - 在 sample size 中考虑 attrition
   - 定义清晰 inclusion/exclusion criteria
   - 考虑 recruitment strategy 和 feasibility
   - 规划 sample representativeness

5. **Measurement Strategy**
   - 选择 validated、reliable instruments
   - 尽可能使用 objective measures
   - 规划 key constructs 的 multiple measures（triangulation）
   - 确保 measures 对 expected changes 敏感
   - 建立 inter-rater reliability procedures

6. **Analysis Planning**
   - 预先指定所有 hypotheses 和 analyses
   - 明确指定 primary outcome
   - 规划 statistical tests 和 assumption checks
   - 指定如何处理 missing data
   - 计划报告 effect sizes 和 confidence intervals
   - 考虑 multiple comparison corrections

7. **Transparency and Rigor**
   - Preregister study 和 analysis plan
   - 使用 reporting guidelines（CONSORT、STROBE、PRISMA）
   - 计划报告所有 outcomes，而不只是 significant ones
   - 区分 confirmatory 和 exploratory analyses
   - 承诺 data/code sharing

**参考：** 从 question 到 dissemination 的完整 design checklist 见 `references/experimental_design.md`。

### 7. Claim Evaluation

系统评估 scientific claims 的 validity 和 support。

**适用于：**
- 评估 papers 中的 conclusions
- 评估媒体对 research 的报道
- 审查 abstract 或 introduction claims
- 检查 data 是否支持 conclusions

**Claim evaluation process：**

1. **Identify the Claim**
   - 具体 claim 是什么？
   - 它是 causal claim、associational claim 还是 descriptive claim？
   - Claim 强度如何（proven、likely、suggested、possible）？

2. **Assess the Evidence**
   - 提供了什么 evidence？
   - Evidence 是 direct 还是 indirect？
   - Evidence 是否足以支持 claim strength？
   - Alternative explanations 是否被排除？

3. **Check Logical Connection**
   - Conclusions 是否来自 data？
   - 是否存在 logical leaps？
   - 是否用 correlational data 支持 causal claims？
   - 是否承认 limitations？

4. **Evaluate Proportionality**
   - Confidence 是否与 evidence strength 成比例？
   - Hedging words 是否使用恰当？
   - Limitations 是否被淡化？
   - Speculation 是否明确标注？

5. **Check for Overgeneralization**
   - Claims 是否超出 studied sample？
   - 是否承认 population restrictions？
   - 是否识别 context-dependence？
   - 是否包含关于 generalization 的 caveats？

6. **Red Flags**
   - Correlational studies 中使用 causal language
   - "Proves" 或 absolute certainty
   - Cherry-picked citations
   - 忽视 contradictory evidence
   - Dismissing limitations
   - 超出 data 的 extrapolation

**提供具体 feedback：**
- 引用 problematic claim
- 解释需要什么 evidence 才能支持它
- 如有必要，建议适当 hedging language
- 区分 data（发现了什么）和 interpretation（它意味着什么）

## Application Guidelines

### General Approach

1. **Be Constructive**
   - 识别 strengths 以及 weaknesses
   - 提出 improvements，而不只是 criticize
   - 区分 fatal flaws 和 minor limitations
   - 承认所有 research 都有 limitations

2. **Be Specific**
   - 指向具体 instances（例如 "Table 2 shows..." 或 "In the Methods section..."）
   - 引用 problematic statements
   - 提供 issues 的 concrete examples
   - 引用被违反的具体 principles 或 standards

3. **Be Proportionate**
   - 让 criticism severity 与 issue importance 匹配
   - 区分对 validity 的 major threats 和 minor concerns
   - 考虑 issues 是否影响 primary conclusions
   - 承认你自己 assessments 中的不确定性

4. **Apply Consistent Standards**
   - 对所有 studies 使用相同 criteria
   - 不要对你不喜欢的 findings 使用更严格 standards
   - 承认自己的 potential biases
   - 基于 methodology 而不是 results 做判断

5. **Consider Context**
   - 承认 practical 和 ethical constraints
   - 考虑 effect sizes 和 methods 的 field-specific norms
   - 识别 exploratory vs. confirmatory contexts
   - 评估 studies 时考虑 resource limitations

### When Providing Critique

**按以下结构组织 feedback：**

1. **Summary：** 简要概述评估内容
2. **Strengths：** 做得好的地方（对 credibility 和 learning 很重要）
3. **Concerns：** 按 severity 组织 issues
   - Critical issues（威胁 main conclusions 的 validity）
   - Important issues（影响 interpretation 但不致命）
   - Minor issues（值得注意但不改变 conclusions）
4. **Specific Recommendations：** 可执行 improvement suggestions
5. **Overall Assessment：** 对 evidence quality 和可得 conclusions 的 balanced conclusion

**使用 precise terminology：**
- 命名具体 biases、fallacies 和 methodological issues
- 引用 established standards 和 guidelines
- 引用 scientific methodology 原则
- 准确使用 technical terms

### When Uncertain

- **承认 uncertainty：** "This could be X or Y; additional information needed is Z"
- **提出 clarifying questions：** "Was [methodological detail] done? This affects interpretation."
- **提供 conditional assessments：** "If X was done, then Y follows; if not, then Z is concern"
- **说明什么 additional information 可解决 uncertainty**

## Reference Materials

此 skill 包含 comprehensive reference materials，为 critical evaluation 提供详细 frameworks：

- **`references/scientific_method.md`** - Scientific methodology 的核心原则、scientific process、critical evaluation criteria、scientific claims 中的 red flags、causal inference standards、peer review 和 open science principles

- **`references/common_biases.md`** - Cognitive、experimental、methodological、statistical 和 analysis biases 的完整 taxonomy，含 detection 和 mitigation strategies

- **`references/statistical_pitfalls.md`** - 常见 statistical errors 和 misinterpretations，包括 p-value misunderstandings、multiple comparisons problems、sample size issues、effect size mistakes、correlation/causation confusion、regression pitfalls 和 meta-analysis issues

- **`references/evidence_hierarchy.md`** - Traditional evidence hierarchy、GRADE system、study quality assessment criteria、domain-specific considerations、evidence synthesis principles 和 practical decision frameworks

- **`references/logical_fallacies.md`** - Scientific discourse 中常见 logical fallacies，按类型（causation、generalization、authority、relevance、structure、statistical）组织，含 examples 和 detection strategies

- **`references/experimental_design.md`** - Comprehensive experimental design checklist，覆盖 research questions、hypotheses、study design selection、variables、sampling、blinding、randomization、control groups、procedures、measurement、bias minimization、data management、statistical planning、ethical considerations、validity threats 和 reporting standards

**何时查阅 references：**
- 需要 detailed frameworks 时将 references 加载到 context
- 使用 grep 搜索 specific topics：`grep -r "pattern" references/`
- References 提供深度；SKILL.md 提供 procedural guidance
- 需要 comprehensive lists、detailed criteria 和 specific examples 时查阅 references

## Remember

**Scientific critical thinking 关注：**
- 使用 established principles 进行 systematic evaluation
- 改善 science 的 constructive critique
- Confidence 与 evidence strength 成比例
- 对 uncertainty 和 limitations 保持透明
- 一致应用 standards
- 承认所有 research 都有 limitations
- 在 skepticism 与对 evidence 开放之间保持平衡

**始终区分：**
- Data（观察到了什么）和 interpretation（它意味着什么）
- Correlation 和 causation
- Statistical significance 和 practical importance
- Exploratory 和 confirmatory findings
- What is known 和 what is uncertain
- Evidence against a claim 和 evidence for the null

**Critical thinking 的目标：**
1. 准确识别 strengths 和 weaknesses
2. 判断哪些 conclusions 得到支持
3. 识别 limitations 和 uncertainties
4. 为 future work 建议 improvements
5. 推进 scientific understanding
