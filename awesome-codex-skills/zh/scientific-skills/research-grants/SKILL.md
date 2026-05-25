---
name: research-grants
description: 为 NSF、NIH、DOE、DARPA 和 Taiwan NSTC 撰写有竞争力的 research proposals。涵盖 agency-specific formatting、review criteria、budget preparation、broader impacts、significance statements、innovation narratives，以及满足 submission requirements。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Research Grant Writing

## 概述

Research grant writing 是为联邦机构和基金会开发有竞争力 funding proposals 的过程。掌握 NSF（National Science Foundation）、NIH（National Institutes of Health）、DOE（Department of Energy）、DARPA（Defense Advanced Research Projects Agency）和 Taiwan NSTC（National Science and Technology Council）申请中的 agency-specific requirements、review criteria、narrative structure、budget preparation 和 compliance。

**关键原则：Grant 是说服性文档，必须同时证明 scientific rigor、innovation、feasibility 和 broader impact。** 每个 agency 都有不同的 priorities、review criteria、formatting requirements 和 strategic goals，必须逐一回应。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 为 NSF、NIH、DOE、DARPA 或 NSTC 项目撰写 research proposals
- 准备 project descriptions、specific aims 或 technical narratives
- 开发 broader impacts 或 significance statements
- 创建 research timelines 和 milestone plans
- 准备 budget justifications 和 personnel allocation plans
- 回应 program solicitations 或 funding announcements
- 在 resubmissions 中回应 reviewer comments
- 规划 multi-institutional collaborative proposals
- 撰写 preliminary data 或 feasibility sections
- 准备 biosketches、CVs 或 facilities descriptions

## 使用 Scientific Schematics 增强视觉表达

**⚠️ 强制要求：每份 research grant proposal 都必须使用 scientific-schematics skill 包含至少 1-2 张 AI-generated figures。**

这不是可选项。没有视觉元素的 grant proposals 是不完整且竞争力较弱的。在定稿任何文档前：
1. 至少生成一张 schematic 或 diagram（例如 project timeline、methodology flowchart 或 conceptual framework）
2. 对完整 proposals，优先使用 2-3 张 figures（research workflow、Gantt chart、preliminary data visualization）

**如何生成 figures：**
- 使用 **scientific-schematics** skill 生成 AI-powered publication-quality diagrams
- 只需用自然语言描述所需 diagram
- Nano Banana Pro 会自动生成、审查并完善 schematic

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
- Research methodology 和 workflow diagrams
- Project timeline Gantt charts
- Conceptual framework illustrations
- System architecture diagrams（用于 technical proposals）
- Experimental design flowcharts
- Broader impacts activity diagrams
- Collaboration network diagrams
- 任何受益于 visualization 的复杂概念

创建 schematics 的详细指导请参考 scientific-schematics skill 文档。

---

## Agency-Specific Overview

### NSF (National Science Foundation)
**Mission**：促进科学进步，并推进 national health、prosperity 和 welfare

**关键特征**：
- Intellectual Merit + Broader Impacts（同等权重）
- 15 页 project description 限制（多数项目）
- 强调 education、diversity 和 societal benefit
- 鼓励 collaborative research
- 强调 open data 和 open science
- Merit review process 包含 panel + ad hoc reviewers

### NIH (National Institutes of Health)
**Mission**：增进健康、延长寿命、减少疾病和 disability

**关键特征**：
- Specific Aims（1 页）+ Research Strategy（R01 为 12 页）
- Significance、Innovation、Approach 是核心 review criteria
- R01 通常需要 preliminary data
- 强调 rigor、reproducibility 和 clinical relevance
- 大多数 R01 使用 modular budgets（$250K increments）
- 有多次 resubmission 机会

### DOE (Department of Energy)
**Mission**：通过 energy、environmental 和 nuclear challenges 保障美国安全与繁荣

**关键特征**：
- 聚焦 energy、climate、computational science、basic energy sciences
- 通常需要 cost sharing 或 industry partnerships
- 强调 national laboratory collaboration
- 强调 computational 和 experimental integration
- Energy innovation 和 commercialization pathways
- 因 office 而异（ARPA-E、Office of Science、EERE 等）

### DARPA (Defense Advanced Research Projects Agency)
**Mission**：为 national security 投资突破性技术

**关键特征**：
- High-risk、high-reward transformative research
- 聚焦 "DARPA-hard" problems（what if true、who cares）
- 强调 prototypes、demonstrations 和 transition paths
- 通常需要多个 phases（feasibility、development、demonstration）
- 强 project management 和 milestone tracking
- 通常需要 teaming 和 collaboration
- 随 program manager 和 BAA（Broad Agency Announcement）差异很大

### NSTC (National Science and Technology Council - Taiwan)
**Mission**：推动台湾的 scientific breakthrough、industrial application 和 societal impact。

**关键特征**：
- **CM03 Form**：核心 technical proposal 格式。
- **Bilingual**：Abstract 需同时提供中文和英文。
- **Innovation & Feasibility**：主要 review focus。
- **Preliminary Data**：对 credibility 非常关键。
- **Research Architecture Diagram**：用于清晰表达的强制视觉元素。

## Research Proposals 的核心组成

### 1. Executive Summary / Project Summary / Abstract

每份 proposal 都需要一个简洁 overview，向 technical reviewers 和 program officers 传达研究的核心要素。

**目的**：提供独立可读的 summary，概括 research vision、significance 和 approach

**长度**：
- NSF：1 页（Project Summary，含独立的 Overview、Intellectual Merit、Broader Impacts）
- NIH：30 行（Project Summary/Abstract）
- DOE：不定（通常 1 页）
- DARPA：不定（通常 1-2 页）

**必要元素**：
- 清楚陈述问题或 research question
- 说明该问题为何重要（significance、urgency、impact）
- Novel approach 或 innovation
- Expected outcomes 和 deliverables
- 团队资质
- Broader impacts 或 translational pathway

**写作策略**：
- 以有吸引力的开头确立重要性
- 使用易懂语言（开头句避免 jargon）
- 陈述具体、可衡量的 objectives
- 传达热情和信心
- 确保每句话都有价值（无 filler）
- 以 transformative vision 或 impact statement 收尾

**应避免的常见错误**：
- 过于技术化或过于详细（留给 project description）
- 未说明 "why now" 或 "why this team"
- Objectives 或 outcomes 模糊
- 忽视 broader impacts 或 significance
- 使用可套用于任何 proposal 的泛泛表述

### 2. Project Description / Research Strategy

详细呈现 research plan 的核心 technical narrative。

**结构因 agency 而异：**

**NSF Project Description**（通常 15 页）：
- Introduction 和 background
- Research objectives 和 questions
- Preliminary results（如适用）
- Research plan 和 methodology
- Timeline 和 milestones
- Broader impacts（贯穿全文或单独成节）
- Prior NSF support（如适用）

**NIH Research Strategy**（R01 为 12 页）：
- Significance（问题为何重要）
- Innovation（新颖性和 transformative 之处）
- Approach（详细 research plan）
  - Preliminary data
  - Research design and methods
  - Expected outcomes
  - Potential problems and alternative approaches

**DOE Project Narrative**（不定）：
- Background and significance
- Technical approach and innovation
- Qualifications and experience
- Facilities and resources
- Project management and timeline

**DARPA Technical Volume**（不定）：
- Technical challenge and innovation
- Approach and methodology
- Schedule and milestones
- Deliverables and metrics
- Team qualifications
- Risk assessment and mitigation

Agency-specific 详细指导请参考：
- `references/nsf_guidelines.md`
- `references/nih_guidelines.md`
- `references/doe_guidelines.md`
- `references/darpa_guidelines.md`
- `references/nstc_guidelines.md`

### 3. Specific Aims（NIH）或 Objectives（NSF/DOE/DARPA）

清晰、可测试的目标，用于组织 research plan。

**NIH Specific Aims Page**（1 页）：
- 开篇段落：knowledge gap 和 significance
- Long-term goal 和 immediate objectives
- Central hypothesis 或 research question
- 2-4 个 specific aims，含 sub-aims
- Expected outcomes 和 impact
- Payoff paragraph：说明为何重要

**每个 Aim 的结构：**
- Aim statement（1-2 句，以 action verb 开头）
- Rationale（为何是这个 aim，preliminary data support）
- Working hypothesis（可测试预测）
- Approach summary（简要 methods overview）
- Expected outcomes 和 interpretation

**写作策略**：
- 让 aims 相互独立但互补
- 确保每个 aim 在 timeline 和 budget 内可完成
- 提供足够细节以判断 feasibility
- 包含 contingency plans 或 alternative approaches
- 各 aims 使用平行结构
- 清楚说明每个 aim 将产生什么知识

详细指导见 `references/specific_aims_guide.md`。

### 4. Broader Impacts（NSF）/ Significance（NIH）

阐明研究的 societal、educational 或 translational value。

**NSF Broader Impacts**（关键组成，与 Intellectual Merit 同等权重）：

NSF 会明确评估 broader impacts。至少回应以下一个方面：
1. **在促进 teaching、training 和 learning 的同时推进 discovery and understanding**
   - Research 和 education 的 integration
   - Students 和 postdocs training
   - Curriculum development
   - Educational materials 和 resources

2. **扩大 underrepresented groups 的 participation**
   - Recruitment 和 retention strategies
   - 与 minority-serving institutions 建立 partnerships
   - 面向 underrepresented communities 的 outreach
   - Mentoring programs

3. **增强 research 和 education infrastructure**
   - Shared facilities 或 instrumentation
   - Cyberinfrastructure 和 data resources
   - Community-wide tools 或 databases
   - Open-source software 或 methods

4. **广泛 dissemination 以增强 scientific and technological understanding**
   - Public outreach 和 science communication
   - K-12 educational programs
   - Museum exhibits 或 media engagement
   - Policy briefs 或 stakeholder engagement

5. **对 society 的 benefits**
   - Economic impact 或 commercialization
   - Health、environment 或 national security benefits
   - Informed decision-making
   - Workforce development

**NSF Broader Impacts 写作策略**：
- 使用具体 activities，而不是模糊陈述
- 为 broader impacts activities 提供 timeline 和 milestones
- 说明 impacts 如何 measurement 和 assessment
- 连接 institutional resources 和 existing programs
- 通过 preliminary efforts 或 partnerships 展示 commitment
- 与 research plan 整合（不要附加式拼接）

**NIH Significance**：
- 回应重要问题或阻碍进展的 critical barrier
- 改善 scientific knowledge、technical capability 或 clinical practice
- 有潜力带来更好的 outcomes、interventions 或 understanding
- 体现该领域 prior research 的 rigor
- 与 NIH mission 和 institute priorities 对齐

详细指导见 `references/broader_impacts.md`。

### 5. Innovation and Transformative Potential

阐明研究的新颖性、创造性和 paradigm-shifting 之处。

**需要突出的 Innovation Elements**：
- **Conceptual Innovation**：新 frameworks、models 或 theories
- **Methodological Innovation**：新 techniques、approaches 或 technologies
- **Integrative Innovation**：以新方式结合 disciplines 或 approaches
- **Translational Innovation**：从 discovery 到 application 的新 pathways
- **Scale Innovation**：前所未有的 scope 或 resolution

**写作策略**：
- 清楚说明创新点（不要假设显而易见）
- 解释当前 approaches 为何不足
- 描述你的 innovation 如何克服 limitations
- 提供 innovation 可行的 evidence（preliminary data、proof-of-concept）
- 区分 incremental 和 transformative advances
- 平衡 innovation 与 feasibility（不要风险过高）

**常见错误**：
- 声称 novelty 但未展示对 prior work 的了解
- 将 "new to me" 混同为 "new to the field"
- 缺少 supporting evidence 却 over-promising
- 过于 incremental（只是 existing work 的小变体）
- 过于 speculative（没有成功路径）

### 6. Research Approach and Methods

详细描述研究将如何开展。

**必要组成**：
- Overall research design 和 framework
- 每个 aim/objective 的详细 methods
- Sample sizes、statistical power 和 analysis plans
- Timeline 和 activities sequence
- Data collection、management 和 analysis
- Quality control 和 validation approaches
- Potential problems 和 alternative strategies
- Rigor 和 reproducibility measures

**写作策略**：
- 提供足够细节，以便评估 reproducibility 和 feasibility
- 使用 subheadings 和 figures 改善组织
- 论证 methods 和 approaches 的选择
- 主动回应 potential limitations
- 包含证明 feasibility 的 preliminary data
- 展示你已充分考虑 research process
- 在细节与 readability 间平衡（大量细节放入 supplementary materials）

**对于 Experimental Research**：
- 描述 experimental design（controls、replicates、blinding）
- 指定 materials、reagents 和 equipment
- 详细说明 data collection protocols
- 解释 statistical analysis plans
- 回应 rigor 和 reproducibility

**对于 Computational Research**：
- 描述 algorithms、models 和 software
- 指定 datasets 和 validation approaches
- 解释所需 computational resources
- 回应 code availability 和 documentation
- 描述 benchmarking 和 performance metrics

**对于 Clinical 或 Translational Research**：
- 描述 study population 和 recruitment
- 详细说明 intervention 或 treatment protocols
- 解释 outcome measures 和 assessments
- 回应 regulatory approvals（IRB、IND、IDE）
- 描述 clinical trial design 和 monitoring


### 7. Preliminary Data and Feasibility

证明研究可实现且团队有能力完成。

**目的**：
- 证明 proposed approach 可行
- 展示团队具备必要 expertise
- 证明可访问 required resources
- 降低 reviewers 感知到的 risk
- 为 proposed work 提供基础

**应包含内容**：
- Pilot studies 或 proof-of-concept results
- Method development 或 optimization
- 访问 unique resources（samples、data、collaborators）
- 团队相关 publications
- Preliminary models 或 simulations
- Feasibility assessments 或 power calculations

**NIH 要求**：
- R01 applications 通常需要 substantial preliminary data
- R21 applications 可能要求较宽松
- New investigators 的 preliminary data 可以较少
- Preliminary data 应直接支持 proposed aims

**NSF Approach**：
- Preliminary data 要求通常少于 NIH
- 对 high-risk 或 novel approaches 可能很重要
- 可增强 competitive programs 的 proposal

**写作策略**：
- 呈现最有说服力且支持 approach 的数据
- 清楚连接 preliminary data 与 proposed aims
- 承认 limitations，并说明 proposed work 如何回应
- 有效使用 figures 和 data visualizations
- 避免过度解释或夸大 preliminary findings
- 展示 research program 的发展轨迹

### 8. Timeline, Milestones, and Management Plan

证明项目规划充分，并可在 proposed timeframe 内完成。

**必要元素**：
- 带清晰 milestones 的 phased timeline
- 合理 sequence 和 dependencies
- 每项 activity 的 realistic timeframes
- Decision points 和 go/no-go criteria
- Risk mitigation strategies
- 跨时间的 resource allocation
- Multi-institutional teams 的 coordination plan

**Presentation Formats**：
- 展示 overlapping activities 的 Gantt charts
- 按 year-by-year 拆分 activities
- Quarterly milestones 和 deliverables
- 含 timeline 和 personnel 的 aims/tasks 表

**写作策略**：
- 对可完成内容保持现实
- 为 unexpected delays 或 setbacks 预留时间
- 展示 timeline 与 budget 和 personnel 对齐
- 体现对 regulatory timelines（IRB、IACUC）的理解
- 包含 dissemination 和 broader impacts 的时间
- 说明如何 monitor 和 assess progress

**DARPA Emphasis**：
- 对 DARPA proposals 尤其重要
- 带 measurable metrics 的清晰 technical milestones
- Quarterly deliverables 和 reporting
- 带 exit criteria 的 phase-based structure
- Demonstration 和 transition planning


### 9. Team Qualifications and Collaboration

证明团队具备成功所需的 expertise、experience 和 resources。

**必要元素**：
- PI qualifications 和 relevant expertise
- Co-I 和 collaborator roles 及 contributions
- 研究领域 track record
- 团队内 complementary expertise
- Institutional support 和 resources
- Prior collaboration history（如适用）
- Students/postdocs 的 mentoring 和 training plan

**写作策略**：
- 突出最相关 publications 和 accomplishments
- 清楚定义 roles 和 responsibilities
- 展示 team composition 是必要的（不只是方便）
- 证明 prior collaborations 成功
- 回应 team 如何 managed 和 coordinated
- 解释 institutional commitment 和 support

**Biosketches / CVs**：
- 遵循 agency-specific formats（NSF、NIH、DOE、DARPA 不同）
- 突出最相关 publications 和 accomplishments
- 包含 synergistic activities 和 collaborations
- 展示 trajectory 和 productivity
- 回应任何 career gaps 或 interruptions

**Letters of Collaboration**：
- 具体 commitments 和 contributions
- 证明 genuine partnership
- 包含 resource sharing 或 access agreements
- 签字并使用 letterhead


### 10. Budget and Budget Justification

制定与 proposed work 和 agency guidelines 对齐的 realistic budgets。

**Budget Categories**（典型）：
- **Personnel**：PI、co-Is、postdocs、students、staff 的 salary 和 fringe
- **Equipment**：>$5,000 的 items（因 agency 而异）
- **Travel**：Conferences、collaborations、fieldwork
- **Materials and Supplies**：Consumables、reagents、software
- **Other Direct Costs**：Publication costs、participant incentives、consulting
- **Indirect Costs (F&A)**：Institutional overhead（rates 不同）
- **Subawards**：Collaborating institutions 的 costs

**Agency-Specific Considerations**：

**NSF**：
- 需要完整 budget justification
- 通常不要求 cost sharing（但可能增强 proposal）
- Faculty 最多 2 个月 summer salary
- 鼓励 graduate student support

**NIH**：
- ≤$250K direct costs per year（R01）使用 modular budgets
- >$250K 或复杂 awards 使用 detailed budgets
- Salary cap 适用（2024 年约 $221,900）
- 大多数 PIs 限制为 1 个月（8.33% FTE）

**DOE**：
- 通常需要 cost sharing（尤其 ARPA-E）
- 带 quarterly breakdown 的 detailed budget
- 需要 institutional commitment letters
- National laboratory collaboration budgets 单独处理

**DARPA**：
- 按 phase 和 task 细分的 detailed budgets
- 大型 procurements 需要 supporting cost data
- 通常需要 cost-plus 或 firm-fixed-price structures
- Program meetings 的 travel budget

**Budget Justification Writing**：
- 按 research plan 论证每个 line item
- 解释 personnel 的 effort percentages
- 描述 specific equipment 及其必要性
- 论证 travel（conferences、collaborations）
- 解释 consultant roles 和 rates
- 展示 budget 如何与 timeline 对齐


## 各 Agency 的 Review Criteria

理解 proposals 如何被评估，是写出有竞争力 applications 的关键。

### NSF Review Criteria

**Intellectual Merit**（主要）：
- Proposed activity 推进知识的潜力是什么？
- Proposed activity 的构想和组织是否充分？
- 是否有足够 resources access？
- Individual、team 或 institution 是否有足够资质开展 proposed activities？

**Broader Impacts**（同等重要）：
- Proposed activity 造福 society 的潜力是什么？
- Proposal 在多大程度上以有意义的方式回应 broader impacts？

**Additional Considerations**：
- Research 和 education 的 integration
- Diversity 和 inclusion
- Prior NSF support 的 results（如适用）

### NIH Review Criteria

**Scored Criteria**（1-9 分，1 = exceptional，9 = poor）：

1. **Significance**
   - 回应重要问题或 critical barrier
   - 改善 scientific knowledge、technical capability 或 clinical practice
   - 与 NIH mission 对齐

2. **Investigator(s)**
   - 适合该项目
   - 有 accomplishments track record
   - 具备 adequate training 和 expertise

3. **Innovation**
   - Novel concepts、approaches、methodologies 或 interventions
   - 挑战 existing paradigms
   - 以创造性方式回应重要问题

4. **Approach**
   - Well-reasoned 且 appropriate
   - Rigorous 且 reproducible
   - 充分考虑 potential problems
   - 在 timeline 内 feasible

5. **Environment**
   - Institutional support 和 resources
   - Scientific environment 有助于 success probability

**Additional Review Considerations**（不评分但会讨论）：
- Human subjects protections
- Inclusion of women、minorities 和 children
- Vertebrate animal welfare
- Biohazards
- Resubmission response（如适用）
- Budget 和 timeline appropriateness

### DOE Review Criteria

因 program office 而异，但通常包括：
- Scientific and/or technical merit
- Proposed method 或 approach 的适切性
- Personnel competency 和 facilities adequacy
- Budget 的 reasonableness 和 appropriateness
- 与 DOE mission 和 program goals 的 relevance

### DARPA Review Criteria

**DARPA-specific considerations**：
- Overall scientific and technical merit
- 对 DARPA mission 的 potential contribution
- Proposed costs 的 realism 和 funds availability

### NSTC Review Criteria

**核心 Evaluation Dimensions**：
1. **Innovation (創新性)**：Concept 和 approach 的 novelty。
2. **Feasibility (可行性)**：Methodology rigor 和 preliminary data。
3. **PI Capability (主持人能力)**：Track record 和 expertise。
4. **Value (價值)**：Academic contribution 和 societal/industrial impact。

详细 review criteria 见 `references/nstc_guidelines.md`。
- **What if you succeed?**（如果研究成功，impact 是什么）
- **What if you're right?**（你的 hypothesis 的 implications）
- **Who cares?**（为什么它对 national security 重要）


## 有竞争力 Proposal 的写作原则

### Clarity and Accessibility

**面向多个受众写作**：
- 你领域内的 technical reviewers（会细查 methods）
- 相关但不完全相同领域的 reviewers（需要 context）
- Program officers（关注与 agency goals 的 alignment）
- 阅读 15+ proposals 的 panel members（需要清晰组织）

**策略**：
- 使用清楚的 section headings 和 subheadings
- Sections 以 overview paragraphs 开始
- 定义 technical terms 和 abbreviations
- 使用 figures、diagrams 和 tables 澄清复杂想法
- 尽量避免 jargon；必要时解释
- 使用 topic sentences 引导读者

### Persuasive Argumentation

**构建有说服力的 Narrative**：
- 确立问题及其重要性
- 展示 current knowledge 或 approaches 的 gaps
- 将你的 solution 呈现为 innovative 且 feasible
- 证明你们是合适团队
- 展示成功会带来 significant impact

**说服结构**：
1. **Hook**：用 significance 吸引注意
2. **Problem**：说明未知或不起作用之处
3. **Solution**：提出 innovative approach
4. **Evidence**：用 preliminary data 支撑
5. **Impact**：展示 transformative potential
6. **Team**：证明交付能力

**语言选择**：
- 使用 active voice 增强清晰度和信心
- 选择强动词（investigate、elucidate、discover，而不是 look at、study）
- 自信但不傲慢（避免 "obviously," "clearly"）
- 适当地承认 uncertainty
- 使用 precise language（避免 "several," "various" 等模糊词）

### Visual Communication

**有效使用 Figures**：
- 展示 research framework 的 conceptual diagrams
- 证明 feasibility 的 preliminary data
- Timelines 和 Gantt charts
- 展示 methodology 的 workflow diagrams
- Expected results 或 predictions

**Design Principles**：
- 通过完整 captions 让 figures 可自解释
- 使用一致 color schemes 和 fonts
- 确保 readability（足够大的 fonts、清楚 labels）
- 将 figures 与正文整合（引用具体 figures）
- 遵守 agency-specific formatting requirements

### Addressing Risk and Feasibility

**平衡 Innovation 和 Risk**：
- 承认 potential challenges
- 提供 alternative approaches
- 展示降低 risk 的 preliminary data
- 证明 expertise 可处理 challenges
- 包含 contingency plans

**常见担忧**：
- 对 timeline/budget 来说过于 ambitious
- 技术上 infeasible
- 团队缺少必要 expertise
- Preliminary data 不足
- Methods 描述不充分
- 缺少 innovation 或 significance

### Integration and Coherence

**确保所有部分对齐**：
- Budget 支持 project description 中的 activities
- Timeline 匹配 aims 和 milestones
- Team composition 匹配 required expertise
- Broader impacts 连接 research plan
- Letters of support 确认所述 collaborations

**避免矛盾**：
- Preliminary data 与 stated gaps
- Claimed expertise 与 publication record
- Stated aims 与 actual methods
- Budget 与 stated activities

## 常见 Proposal Types

### NSF Proposal Types

- **Standard Research Proposals**：最常见，最高 $500K、5 年
- **CAREER Awards**：Early career faculty，整合 research/education，5 年 $400-500K
- **Collaborative Research**：多个 institutions，分别提交，共享 research plan
- **RAPID**：紧急 research opportunities，最高 $200K，不要求 preliminary data
- **EAGER**：High-risk、high-reward exploratory research，最高 $300K
- **EArly-concept Grants for Exploratory Research (EAGER)**：早期 exploratory work

### NIH Award Mechanisms

- **R01**：Research Project Grant，每年 $250K+，3-5 年，最常见
- **R21**：Exploratory/Developmental Research，2 年最高 $275K，无 preliminary data
- **R03**：Small Grant Program，2 年最高 $100K
- **R15**：Academic Research Enhancement Awards（AREA），面向 primarily undergraduate institutions
- **R35**：MIRA（Maximizing Investigators' Research Award），program-specific
- **P01**：Program Project Grant，multi-project integrated research
- **U01**：Research Project Cooperative Agreement，NIH 参与执行

**Fellowship Mechanisms**：
- **F30**：Predoctoral MD/PhD Fellowship
- **F31**：Predoctoral Fellowship
- **F32**：Postdoctoral Fellowship
- **K99/R00**：Pathway to Independence Award
- **K08**：Mentored Clinical Scientist Research Career Development Award

### DOE Programs

- **Office of Science**：Physical sciences、biological sciences、computing 的 basic research
- **ARPA-E**：Transformative energy technologies，需要 cost sharing
- **EERE**：Renewable energy 和 energy efficiency 的 applied research
- **National Laboratories**：与 DOE labs 的 collaborative research

### DARPA Programs

- **Varies by Office**：BTO、DSO、I2O、MTO、STO、TTO
- **Program-Specific BAAs**：特定 thrusts 的 Broad Agency Announcements
- **Young Faculty Award (YFA)**：Early career researchers，最高 $500K
- **Director's Fellowship**：High-risk、paradigm-shifting research


## Resubmission Strategies

### NIH Resubmission (A1)

**Introduction to Resubmission**（1 页）：
- 总结 previous review 的主要 criticisms
- 描述回应这些 criticisms 所做的具体修改
- 使用 bullet points 提高清晰度
- 尊重 reviewer comments
- 突出 substantial improvements

**策略**：
- 回应每一项 major criticism
- 让修改可见（但 final 中不要使用 track changes）
- 加强薄弱区域（preliminary data、methods、significance）
- 如果 aims 存在根本缺陷，考虑修改 aims
- Resubmitting 前获取 external feedback
- 如需新数据，可使用完整 37-month window

**何时不应 Resubmit**：
- Fundamental conceptual flaws
- 缺少 innovation 或 significance
- 缺少 key expertise 或 resources
- 需要 extensive revisions（考虑 new submission）

### NSF Resubmission

**NSF 允许 revision 后 resubmission**：
- 在 revised proposal 中回应 reviewer concerns
- 无正式 "introduction to resubmission" section
- 可能由相同或不同 panel review
- 考虑 program officer feedback
- 可能需要等待下一个 submission cycle


## 应避免的常见错误

### Conceptual Mistakes

1. **未回应 Review Criteria**：未明确讨论 significance、innovation、approach 等
2. **与 Agency Mission 不匹配**：提出与 agency goals 不一致的研究
3. **Significance 不清楚**：未说明研究为何重要
4. **Innovation 不足**：将 incremental work 描述为 transformative
5. **Objectives 模糊**：目标不具体或不可衡量

### Writing Mistakes

1. **组织较差**：缺少清晰 structure 和 flow
2. **Jargon 过多**：broader review panel 难以理解
3. **冗长**：写作不必要地复杂或啰嗦
4. **缺少 Context**：假设 reviewers 对你的领域非常熟悉
5. **Terminology 不一致**：同一概念使用不同术语

### Technical Mistakes

1. **Methods 不充分**：细节不足，无法判断 feasibility
2. **过于 Ambitious**：相对 timeline/budget 提出过多内容
3. **无 Preliminary Data**：对需要证明 feasibility 的 mechanisms 不足
4. **Timeline 较差**：schedule 不现实或论证不足
5. **Budget 不匹配**：budget 不支持 proposed activities

### Formatting Mistakes

1. **超过 Page Limits**：自动拒绝
2. **错误 Font 或 Margins**：格式不合规
3. **缺少 Required Sections**：application 不完整
4. **Figure Quality 较差**：不可读或不专业
5. **Citations 不一致**：references 中 formatting errors

### Strategic Mistakes

1. **Program 或 Mechanism 错误**：投向不合适 opportunity
2. **Team 较弱**：expertise 不足或缺少 key collaborators
3. **No Broader Impacts**：对 NSF 未充分回应
4. **忽视 Program Priorities**：未与当前 emphasis areas 对齐
5. **Late Submission**：技术问题或准备仓促

## Grant Development Workflow

### Phase 1: Planning and Preparation（deadline 前 2-6 个月）

**Activities**：
- Identify appropriate funding opportunities
- Review program announcements and requirements
- Consult with program officers（if appropriate）
- Assemble team and confirm collaborations
- Develop preliminary data（if needed）
- Outline research plan and specific aims
- Review successful proposals（if available）

**Outputs**：
- Selected funding opportunity
- 已组建且 roles 明确的 team
- Specific aims 初步 outline
- 所需 preliminary data 的 gap analysis

### Phase 2: Drafting（deadline 前 2-3 个月）

**Activities**：
- Write specific aims or objectives（从这里开始！）
- Develop project description/research strategy
- Create figures and data visualizations
- Draft timeline and milestones
- Prepare preliminary budget
- Write broader impacts or significance sections
- Request letters of support/collaboration

**Outputs**：
- Narrative sections 的完整 first draft
- 带 justification 的 preliminary budget
- Timeline 和 management plan
- 已向 collaborators 请求的 letters

### Phase 3: Internal Review（deadline 前 1-2 个月）

**Activities**：
- Circulate draft to co-investigators
- Seek feedback from colleagues and mentors
- Request institutional review（if required）
- Mock review session（if possible）
- Revise based on feedback
- Refine budget and budget justification

**Outputs**：
- 纳入 feedback 的 revised draft
- 与 revised plan 对齐的 refined budget
- 已识别 weaknesses 和 mitigation strategies

### Phase 4: Finalization（deadline 前 2-4 周）

**Activities**：
- Narrative final revisions
- Prepare all required forms and documents
- Finalize budget and budget justification
- Compile biosketches、CVs 和 current & pending
- Collect letters of support
- Prepare data management plan（if required）
- Write project summary/abstract
- Proofread all materials

**Outputs**：
- 完整、polished proposal
- 所有 required supplementary documents
- 按 agency requirements 格式化

### Phase 5: Submission（deadline 前 1 周）

**Activities**：
- Institutional review and approval
- Upload to submission portal
- Verify all documents and formatting
- Submit 24-48 hours before deadline
- Confirm successful submission
- Receive confirmation and proposal number

**Outputs**：
- Submitted proposal
- Submission confirmation
- 所有 materials 的 archived copy

**关键建议**：不要等到 deadline。Portals 会崩溃，files 会损坏，也会出现 emergencies。目标是提前 48 小时提交。

## 与其他 Skills 的集成

此 skill 可与以下 skill 高效配合：
- **Scientific Writing**：用于清晰、有说服力的 prose
- **Literature Review**：用于完整 background sections
- **Peer Review**：用于 submission 前 self-assessment
- **Research Lookup**：用于查找 relevant citations 和 prior work
- **Data Visualization**：用于创建有效 figures

## 资源

此 skill 包含覆盖 grant writing 特定方面的完整 reference files：

- `references/nsf_guidelines.md`：NSF-specific requirements、formatting 和 strategies
- `references/nih_guidelines.md`：NIH mechanisms、review criteria 和 submission requirements
- `references/doe_guidelines.md`：DOE programs、emphasis areas 和 application procedures
- `references/darpa_guidelines.md`：DARPA BAAs、program offices 和 proposal strategies
- `references/broader_impacts.md`：compelling broader impacts statements 的策略
- `references/specific_aims_guide.md`：撰写 effective specific aims pages
- `references/nstc_guidelines.md`：NSTC-specific guidelines 和 review criteria

处理 grant writing 的特定方面时，按需加载这些 references。

## Templates and Assets

- `assets/nsf_project_summary_template.md`：NSF project summary structure
- `assets/nih_specific_aims_template.md`：NIH specific aims page template
- `assets/budget_justification_template.md`：Budget justification structure

## Scripts and Tools

- `scripts/generate_schematic.py`：生成 scientific diagrams 和 schematics

---

**Final Note**：Grant writing 既是 art 也是 science。成功不仅需要优秀 research ideas，还需要清晰 communication、strategic positioning 和对细节的严谨关注。尽早开始，寻求 feedback，并记住即使最优秀的 researchers 也会遭遇 rejection；persistence 和 revision 是获得 funding success 的关键。
