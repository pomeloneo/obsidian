---
name: clinical-decision-support
description: 为制药和临床研究环境生成专业的临床决策支持 (CDS) 文件，包括患者队列分析（根据结果进行生物标志物分层）和治疗推荐报告（带有决策算法的循证指南）。支持GRADE证据分级、统计分析（风险比、生存曲线、瀑布图）、生物标志物整合和法规遵从性。输出针对药物开发、临床研究和证据合成进行优化的可发表的LaTeX/PDF格式。
allowed-tools: Read Write Edit Bash
license: MIT License
metadata:
    skill-author: K-Dense Inc.
---

# 临床决策支持文件

## 描述

为制药公司、临床研究人员、医疗决策者生成专业的临床决策支持（CDS）文档。该技能专门研究分析、循证文件，为治疗策略和药物开发提供信息：

1. **患者队列分析** - 生物标志物分层组分析与统计结果比较
2. **治疗建议报告** - 具有 GRADE 分级和决策算法的循证临床指南

所有文档均生成为可发布的 LaTeX/PDF 文件，针对药物研究、监管提交和临床指南开发进行了优化。

**注意**： 对于床边的个体患者治疗计划，请使用`treatment-plans`技能。该技能侧重于pharmaceutical/research设置的群体级别分析和证据合成。

**写作风格**： 对于针对医学期刊的可发表文档，请参阅**场地模板** 技能的`medical_journal_styles.md`，以获取有关结构化摘要、证据语言和CONSORT/STROBE 合规性的指导。

## 能力

### 文档类型

**患者队列分析**
- 基于生物标志物的患者分层（分子亚型、基因表达、IHC）
- 分子亚型分类（e.g.、GBM间充质免疫活性与原神经、乳腺癌亚型）
- 统计分析结果指标（OS、PFS、ORR、DOR、DCR）
- 亚组之间的统计比较（风险比、p 值、95% CI）
- 使用 Kaplan-Meier 曲线和对数秩检验进行生存分析
- 功效表和瀑布图
- 比较效果分析
- 制药队列报告（试验亚组，真实世界证据）

**治疗建议报告**
- 针对特定疾病状态的循证治疗指南
- 推荐强度分级（GRADE系统：1A、1B、2A、2B、2C）
- 证据质量评估（高、中、低、极低）
- 带有TikZ图的处理算法流程图
- 基于生物标志物的治疗线测序
- 具有临床和分子标准的决策途径
- 医药战略文件
- 医学会临床指南制定

### 临床特征

- **生物标记整合**：基因组改变（突变、CNV、融合）、基因表达特征、IHC标记、PD-L1评分
- **统计分析**：风险比、p 值、置信区间、生存曲线、Cox 回归、对数秩检验
- **证据分级**：GRADE系统（1A/1B/2A/2B/2C），牛津CEBM等级，证据质量评估
- **临床术语**：SNOMED-CT、LOINC、正确的医学术语、试验术语
- **监管合规性**：HIPAA去标识化、机密性标头、ICH-GCP对齐
- **专业格式**：紧凑的0.5in页边距，颜色编码建议，可出版，适合监管提交

## 制药和研究用例

该技能专为制药和临床研究应用而设计：

**药物开发**
- **阶段2/3试验分析**：生物标志物分层功效和安全性分析
- **亚组分析**：森林图显示不同患者亚组的治疗效果
- **伴随诊断开发**：将生物标志物与药物反应联系起来
- **监管提交**：IND/NDA 带有证据摘要的文档

**医疗事务**
- **KOL 教育材料**：针对思想领袖的循证治疗算法
- **医疗战略文件**：竞争格局和定位战略
- **顾问委员会材料**：队列分析和治疗建议框架
- **出版规划**：针对同行评审期刊的手稿分析

**临床指南**
- **指南制定**：使用 GRADE 方法论为专业协会进行证据合成
- **共识建议**：多利益相关者处理算法开发
- **实践标准**：基于生物标志物的治疗选择标准
- **质量衡量**：基于证据的绩效指标

**真实世界的证据**
- **RWE 队列研究**：根据 EMR 数据对患者队列进行回顾性分析
- **比较有效性**：现实环境中的头对头治疗比较
- **结果研究**：临床实践中的长期生存和安全性
- **健康经济学**：生物标志物亚组的成本效益分析

## 何时使用

当您需要执行以下操作时使用此技能：

- **分析按生物标志物、分子亚型或临床特征分层的患者群体**
- **生成治疗推荐报告**以及临床指南或药物策略的证据分级
- **通过统计分析（生存率、缓解率、风险比）比较患者亚组之间的结果**
- **制作药物研究文件**用于药物开发、临床试验或监管提交
- **使用GRADE证据分级和决策算法制定临床实践指南**
- **在人群水平（而非个体患者）记录生物标志物引导的治疗选择**
- **从多个试验或真实世界数据源合成证据**
- **创建临床决策算法**以及治疗排序流程图

**请NOT将此技能用于**：
- 个体患者治疗计划（使用`treatment-plans`技能）
- 床边临床护理文件（使用`treatment-plans`技能）
- 简单的针对患者的治疗方案（使用`treatment-plans`技能）

## 用科学原理图增强视觉效果

**⚠️ MANDATORY：每个临床决策支持文档MUST至少包含1-2个使用科学原理图技能生成的AI图形。**

这不是可选的。临床决策文件需要清晰的视觉算法。在最终确定任何文件之前：
1. 生成至少 ONE 示意图或图表（e.g.、临床决策算法、治疗路径或生物标志物分层树）
2. 用于队列分析：包括患者流程图
3. 对于治疗建议：包括决策流程图

**如何生成数字**：
- 使用 **科学原理图** 技能生成 AI 驱动的出版质量图表
- 用自然语言简单描述您想要的图表
- Nano Banana Pro 将自动生成、审查和完善原理图

**如何生成原理图**：
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI 将自动：
- 使用正确的格式创建出版质量的图像
- 通过多次迭代进行审查和完善
- 确保可访问性（色盲友好，高对比度）
- 将输出保存在figures/目录中

**何时添加原理图**：
- 临床决策算法流程图
- 治疗途径图
- 生物标记分层树
- 患者队列流程图（CONSORT式）
- 生存曲线可视化
- 分子机制图
- 任何受益于可视化的复杂概念

有关创建原理图的详细指导，请参阅科学原理图技能文档。

---

## 文档结构

**CRITICAL REQUIREMENT：所有临床决策支持文件MUST均以第1页的完整执行摘要开始，该摘要横跨整个首页，然后位于任何目录或详细部分之前。**

### 第 1 页 执行摘要结构

每个CDS文档的首页应包含ONLY包含以下组成部分的执行摘要：

**必需的元素（全部位于第 1 页）**：
1. **文档标题和类型**
   - 主标题（e.g.，“生物标志物分层队列分析”或“循证治疗建议”）
   - 带有疾病状态和焦点的副标题
   
2. **报告信息框**（使用彩色tcolorbox）
   - 文档类型和用途
   - analysis/report 的日期
   - 疾病状况和患者群体
   - Author/institution（如果适用）
   - 分析框架或方法
   
3. **关键发现框**（使用 tcolorbox 的 3-5 个彩色框）
   - **初步结果**（蓝框）：主要efficacy/outcome发现
   - **生物标志物见解**（绿框）：关键分子亚型发现
   - **临床意义**（yellow/orange框）：可行的治疗意义
   - **统计摘要**（灰框）：风险比、p 值、关键统计数据
   - **安全亮点**（红色框，如果适用）：严重不良事件或警告

**视觉要求**：
- 使用 `\thispagestyle{empty}` 删除第 1 页的页码
- 所有内容必须适合第 1 页（`\newpage` 之前）
- 使用具有不同颜色的彩色 tcolorbox 环境来实现视觉层次结构
- 框应该是可扫描的并突出显示最关键的信息
- 使用要点，而不是叙述性段落
- 第 1 页结束，在目录或详细部分之前添加 `\newpage`

**首页示例 LaTeX 结构**：
```latex
\maketitle
\thispagestyle{empty}

% Report Information Box
\begin{tcolorbox}[colback=blue!5!white, colframe=blue!75!black, title=Report Information]
\textbf{Document Type:} Patient Cohort Analysis\\
\textbf{Disease State:} HER2-Positive Metastatic Breast Cancer\\
\textbf{Analysis Date:} \today\\
\textbf{Population:} 60 patients, biomarker-stratified by HR status
\end{tcolorbox}

\vspace{0.3cm}

% Key Finding #1: Primary Results
\begin{tcolorbox}[colback=blue!5!white, colframe=blue!75!black, title=Primary Efficacy Results]
\begin{itemize}
    \item Overall ORR: 72\% (95\% CI: 59-83\%)
    \item Median PFS: 18.5 months (95\% CI: 14.2-22.8)
    \item Median OS: 35.2 months (95\% CI: 28.1-NR)
\end{itemize}
\end{tcolorbox}

\vspace{0.3cm}

% Key Finding #2: Biomarker Insights
\begin{tcolorbox}[colback=green!5!white, colframe=green!75!black, title=Biomarker Stratification Findings]
\begin{itemize}
    \item HR+/HER2+: ORR 68\%, median PFS 16.2 months
    \item HR-/HER2+: ORR 78\%, median PFS 22.1 months
    \item HR status significantly associated with outcomes (p=0.041)
\end{itemize}
\end{tcolorbox}

\vspace{0.3cm}

% Key Finding #3: Clinical Implications
\begin{tcolorbox}[colback=orange!5!white, colframe=orange!75!black, title=Clinical Recommendations]
\begin{itemize}
    \item Strong efficacy observed regardless of HR status (Grade 1A)
    \item HR-/HER2+ patients showed numerically superior outcomes
    \item Treatment recommended for all HER2+ MBC patients
\end{itemize}
\end{tcolorbox}

\newpage
\tableofcontents  % TOC on page 2
\newpage  % Detailed content starts page 3
```

### 患者队列分析（详细部分 - 第 3 页以上）
- **队列特征**：人口统计、基线特征、患者选择标准
- **生物标志物分层**：分子亚型、基因组改变、IHC概况
- **治疗暴露**：按亚组列出的接受的治疗、剂量、治疗持续时间
- **结果分析**：响应率 (ORR、DCR)、生存数据 (OS、PFS)、DOR
- **统计方法**：Kaplan-Meier 生存曲线、风险比、对数秩检验、Cox 回归
- **亚组比较**：生物标志物分层功效、森林图、统计显着性
- **安全概况**：按亚组划分的不良事件、剂量修改、停药
- **临床建议**：基于生物标志物概况的治疗影响
- **数字**：瀑布图、游泳者图、生存曲线、森林图
- **表格**：人口统计表、生物标志物频率、按亚组划分的结果

### 治疗建议报告（详细部分 - 第 3 页以上）

**第 1 页治疗建议执行摘要应包括**：
1. **报告信息框**：疾病状态、指南version/date、目标人群
2. **关键建议框**（绿色）：按治疗方案排名前 3-5 GRADE 分级的建议
3. **生物标志物决策标准框**（蓝色）：影响治疗选择的关键分子标志物
4. **证据摘要框**（灰色）：支持建议的主要试验（e.g.、KEYNOTE-189、FLAURA）
5. **关键监控盒** (orange/red)：基本安全监控要求

**详细部分（第 3 页以上）**：
- **临床背景**：疾病状态、流行病学、当前治疗情况
- **目标人群**：患者特征、生物标志物标准、分期
- **证据审查**：系统文献综合、指南摘要、试验数据
- **治疗方案**：具有作用机制的可用疗法
- **证据分级**：每项建议的GRADE评估（1A、1B、2A、2B、2C）
- **按线路推荐**：一线、二线、后续治疗
- **生物标志物引导选择**：基于分子谱的决策标准
- **处理算法**：TikZ显示决策路径的流程图
- **监测方案**：安全评估、功效监测、剂量修改
- **特殊人群**：老年人、renal/hepatic损伤、合并症
- **参考文献**：包含试验名称和引文的完整参考书目

## 输出格式

**MANDATORY FIRST PAGE REQUIREMENT:**
- **第 1 页**：包含 3-5 个彩色 tcolorbox 元素的整页执行摘要
- **第 2 页**： Table 内容（可选）
- **第 3 页+**：包含方法、结果、图形、表格的详细部分

**文档规范**：
- **Primary**：LaTeX/PDF，具有 0.5in 边距，用于紧凑、数据密集的演示
- **长度**：通常为 5-15 页（1 页执行摘要 + 4-14 页详细内容）
- **风格**：可出版，医药级，适合监管提交
- **第一页**：始终是跨越整个第 1 页的完整执行摘要（请参阅文档结构部分）

**视觉元素**：
- **颜色**：
  - 第 1 页框：蓝色=data/information，绿色=biomarkers/recommendations，yellow/orange=临床意义，红色=警告
  - 推荐框（绿色=强烈推荐，黄色=有条件，蓝色=需要研究）
  - 生物标志物分层（颜色编码的分子亚型）
  - 统计显着性（颜色编码的 p 值、风险比）
- **表格**：
  - 具有基线特征的人口统计数据
  - 按亚组划分的生物标志物频率
  - 结果表（ORR、PFS、OS、DOR 按分子亚型）
  - 队列中的不良事件
  - 具有GRADE评级的证据汇总表
- **数字**：
  - Kaplan-Meier 生存曲线，带有对数秩 p 值和风险数表
  - 瀑布图显示患者的最佳反应
  - 用于带置信区间的亚组分析的森林图
  - TikZ 决策算法流程图
  - 个体患者时间线的游泳者图
- **统计**：95% CI 的风险比、p 值、中位生存时间、里程碑生存率
- **合规**：根据 HIPAA 安全港进行去标识化，专有数据的保密声明

## 整合

该技能集成了：
- **科学写作**：引文管理、统计报告、证据综合
- **临床报告**：医学术语、HIPAA合规性、监管文件
- **科学原理图**：TikZ决策算法和治疗路径的流程图
- **治疗计划**：队列衍生见解的个体患者应用（双向）

## 治疗计划技能的关键区别

**临床决策支持（此技能）**：
- **受众**：制药公司、临床研究人员、指导委员会、医学事务
- **范围**：人群层面分析、证据综合、指南制定
- **焦点**：生物标志物分层、统计比较、证据分级
- **输出**：带有大量图形和表格的多页分析文档（通常为 5-15 页）
- **用例**：药物开发、监管提交、临床实践指南、医疗策略
- **示例**：“根据激素受体状态和生存结果分析 60 HER2+ 乳腺癌患者”

**治疗计划技能**：
- **观众**：临床医生、患者、护理团队
- **范围**：个体患者护理计划
- **焦点**：SMART目标、针对患者的干预测量指标、监测计划
- **输出**：简明的 1-4 页可操作的护理计划
- **用例**：床边临床护理、EMR 文档、以患者为中心的规划
- **示例**：“为一名新诊断的 2 型糖尿病的 55 岁患者制定治疗计划”

**何时使用每个**：
- 使用**临床决策支持**：队列分析、生物标志物分层研究、治疗指南制定、药物策略文件
- 使用**治疗计划**：个体患者护理计划、特定患者的治疗方案、床旁临床文件

## 示例用法

### 患者队列分析

**示例 1：NSCLC 生物标志物分层**
```
> Analyze a cohort of 45 NSCLC patients stratified by PD-L1 expression (<1%, 1-49%, ≥50%) 
> receiving pembrolizumab. Include outcomes: ORR, median PFS, median OS with hazard ratios 
> comparing PD-L1 ≥50% vs <50%. Generate Kaplan-Meier curves and waterfall plot.
```

**示例2：GBM分子亚型分析**
```
> Generate cohort analysis for 30 GBM patients classified into Cluster 1 (Mesenchymal-Immune-Active) 
> and Cluster 2 (Proneural) molecular subtypes. Compare outcomes including median OS, 6-month PFS rate, 
> and response to TMZ+bevacizumab. Include biomarker profile table and statistical comparison.
```

**示例 3：乳腺癌 HER2 队列**
```
> Analyze 60 HER2-positive metastatic breast cancer patients treated with trastuzumab-deruxtecan, 
> stratified by prior trastuzumab exposure (yes/no). Include ORR, DOR, median PFS with forest plot 
> showing subgroup analyses by hormone receptor status, brain metastases, and number of prior lines.
```

### 治疗建议报告

**示例 1：HER2+ 转移性乳腺癌指南**
```
> Create evidence-based treatment recommendations for HER2-positive metastatic breast cancer including 
> biomarker-guided therapy selection. Use GRADE system to grade recommendations for first-line 
> (trastuzumab+pertuzumab+taxane), second-line (trastuzumab-deruxtecan), and third-line options. 
> Include decision algorithm flowchart based on brain metastases, hormone receptor status, and prior therapies.
```

**示例2：高级NSCLC处理算法**
```
> Generate treatment recommendation report for advanced NSCLC based on PD-L1 expression, EGFR mutation, 
> ALK rearrangement, and performance status. Include GRADE-graded recommendations for each molecular subtype, 
> TikZ flowchart for biomarker-directed therapy selection, and evidence tables from KEYNOTE-189, FLAURA, 
> and CheckMate-227 trials.
```

**示例 3：多发性骨髓瘤治疗线测序**
```
> Create treatment algorithm for newly diagnosed multiple myeloma through relapsed/refractory setting. 
> Include GRADE recommendations for transplant-eligible vs ineligible, high-risk cytogenetics considerations, 
> and sequencing of daratumumab, carfilzomib, and CAR-T therapy. Provide flowchart showing decision points 
> at each line of therapy.
```

## 主要特点

### 生物标志物分类
- 基因组：突变、CNV、基因融合
- 表达式：RNA-seq，IHC分数
- 分子亚型：疾病特异性分类
- 临床可操作性：治疗选择指南

### 结果指标
- 生存：OS（总体生存），PFS（无进展生存）
- 回复：ORR（客观回复率）、DOR（回复持续时间）、DCR（疾病控制率）
- 质量：ECOG 表现状态、症状负担
- 安全性：不良事件、剂量调整

### 统计方法
- 生存分析：Kaplan-Meier 曲线、对数秩检验
- 组比较：t 检验、卡方、费舍尔精确
- 效应大小：风险比、比值比 95% CI
- 显着性：p 值、多重测试修正

### 证据分级

**GRADE系统**
- **1A**：强烈推荐，高质量证据
- **1B**：强烈推荐，中等质量证据
- **2A**：弱推荐，高质量证据
- **2B**：推荐弱，证据质量中等
- **2C**：推荐弱，证据质量低

**推荐强度**
- **强**：收益明显大于风险
- **有条件**：权衡存在，患者价值观很重要
- **研究**：证据不足，需要临床试验

## 最佳实践

### 用于群组分析

1. **患者选择透明度**：清楚记录inclusion/exclusion标准、患者流程和排除原因
2. **生物标志物清晰度**：指定assay方法、平台（e.g.、FoundationOne、Caris）、切点和验证状态
3. **统计严谨性**：
   - 报告具有 95% 置信区间的风险比，而不仅仅是 p 值
   - 包括生存分析的中位随访时间
   - 指定使用的统计检验（对数秩、Cox 回归、Fisher 精确）
   - 在适当的时候考虑多重比较
4. **结果定义**：使用标准标准：
   - 回复：RECIST1.1，iRECIST用于免疫治疗
   - 不良事件：CTCAE版本5.0
   - 表现状态：ECOG 或卡诺夫斯基
5. **生存数据演示**：
   - 中值 OS/PFS 95% CI
   - 里程碑式的存活率（6 个月、12 个月、24 个月）
   - Kaplan-Meier 曲线下方的风险人数表
   - 审查明确表明
6. **子组分析**：预先指定子组；明确标记探索性分析与预先计划的分析
7. **数据完整性**：报告丢失的数据及其处理方式

### 用于治疗建议报告

1. **证据分级透明度**：
   - 一致使用GRADE系统（1A、1B、2A、2B、2C）
   - 记录每个等级的理由
   - 明确说明证据质量（高、中、低、非常低）
2. **全面证据审查**：
   - 包括 3 期随机试验作为主要证据
   - 补充新兴疗法的二期数据
   - 注意现实世界的证据和荟萃分析
   - 引用试验名称（e.g.、KEYNOTE-189、CheckMate-227）
3. **生物标志物引导的建议**：
   - 将特定生物标志物与治疗建议联系起来
   - 指定测试方法并验证assays
   - 包括 FDA/EMA 伴随诊断的批准状态
4. **临床可操作性**：每项建议都应该有明确的实施指南
5. **决策算法清晰度**：TikZ流程图应明确，并具有清晰的yes/no决策点
6. **特殊人群**：解决老年人、renal/hepatic损伤、怀孕、药物相互作用
7. **监控指南**：指定安全实验室、成像和频率
8. **更新频率**：定期更新的日期建议和计划

### 一般最佳实践

1. **首页执行摘要 (MANDATORY)**：
   - ALWAYS 在第 1 页上创建涵盖整个第一页的完整执行摘要
   - 使用 3-5 个彩色 tcolorbox 元素来突出显示关键发现
   - 第 1 页没有目录或详细部分
   - 使用`\thispagestyle{empty}` 并以`\newpage` 结尾
   - 这是最重要的页面 - 应该可以在 60 秒内完成扫描
2. **去标识**：在文档生成之前删除所有 18 个HIPAA 标识符（安全港方法）
3. **监管合规性**：包括专有药品数据的保密声明
4. **出版就绪格式**：使用 0.5in 页边距、专业字体、颜色编码部分
5. **再现性**：记录所有统计方法以实现复制
6. **利益冲突**：披露制药资金或关系（如适用）
7. **视觉层次结构**：一致使用彩色框（蓝色=数据，绿色=生物标记，yellow/orange=建议，红色=警告）

## 参考文献

请参阅 `references/` 目录以获取有关以下内容的详细指导：
- 患者队列分析和分层方法
- 治疗建议制定
- 临床决策算法
- 生物标志物分类和解释
- 结果分析和统计方法
- 证据合成和分级系统

## 模板

请参阅`assets/`目录中的LaTeX模板：
- `cohort_analysis_template.tex` - 生物标志物分层患者队列分析与统计比较
- `treatment_recommendation_template.tex` - 循证临床实践指南，GRADE 分级
- `clinical_pathway_template.tex` - TikZ 治疗排序决策算法流程图
- `biomarker_report_template.tex` - 分子亚型分类和基因组概况报告

**模板功能**：
- 0.5in 紧凑演示的边距
- 颜色编码的推荐框
- 人口统计、生物标志物、结果的专业表格
- 对 Kaplan-Meier 曲线、瀑布图、森林图的内置支持
- GRADE 证据分级表
- 药品文档的机密性标头

## 脚本

分析和可视化工具请参见`scripts/`目录：
- `generate_survival_analysis.py` - 通过对数秩检验生成 Kaplan-Meier 曲线，风险比，95% CI
- `create_waterfall_plot.py` - 队列分析的最佳响应可视化
- `create_forest_plot.py` - 具有置信区间的子组分析可视化
- `create_cohort_tables.py` - 人口统计、生物标志物频率和结果表
- `build_decision_tree.py` - TikZ 治疗算法流程图生成
- `biomarker_classifier.py` - 按分子亚型的患者分层算法
- `calculate_statistics.py` - 风险比、Cox 回归、对数秩检验、Fisher 精确
- `validate_cds_document.py` - 质量和合规性检查（HIPAA，统计报告标准）
- `grade_evidence.py` - 自动GRADE 治疗建议评估助手


