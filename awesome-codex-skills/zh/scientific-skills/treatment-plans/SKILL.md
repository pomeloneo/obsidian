---
name: treatment-plans
description: 为所有临床专业生成 LaTeX/PDF 格式的简明（3-4 页）、重点突出的医疗计划。支持一般医疗、康复治疗、心理保健、慢性病管理、围手术期护理和疼痛管理。包括 SMART 目标框架、以最少文本引用的循证干预措施、法规遵从性 (HIPAA) 和专业格式。优先考虑简洁性和临床可操作性。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# 治疗计划撰写

## 概述

治疗计划的编写是临床护理策略的系统记录，旨在通过循证干预、可衡量的目标和结构化随访来解决患者的健康状况。该技能提供全面的 LaTeX 模板和验证工具，用于在所有医学专业中创建**简洁、有针对性的**治疗计划（标准 3-4 页），并完全符合法规要求。

**关键原则：**
1. **简洁且可操作**：治疗计划默认最多 3-4 页，仅关注影响护理决策的临床重要信息
2. **以患者为中心**：计划必须以证据为基础、可衡量，并符合医疗保健法规（HIPAA，文档标准）
3. **最少引用**：仅在需要支持临床建议时使用简短的文本引用；避免大量参考书目

每个治疗计划都应包括明确的目标、具体的干预措施、明确的时间表、监测参数以及符合患者偏好和当前临床指南的预期结果——所有这些都尽可能有效地呈现。

## 何时使用此技能

该技能应该在以下情况下使用：
- 为患者护理制定个性化治疗计划
- 记录慢性病管理的治疗干预措施
- 制定康复计划（物理治疗、职业治疗、心脏康复）
- 撰写心理健康和精神病治疗计划
- 规划围手术期和手术护理途径
- 建立疼痛管理方案
- 使用 SMART 标准设定以患者为中心的目标
- 协调跨专业的多学科护理
- 确保治疗文件符合法规
- 为病历生成专业的治疗计划

## 通过scientific-schematics增强视觉效果

**⚠️ 强制：每个治疗计划必须包含至少 1 个使用scientific-schematics技能由 AI 生成的图形。**

这不是可选的。治疗计划极大地受益于视觉元素。在最终确定任何文件之前：
1. 至少生成一张示意图或图表（例如，治疗路径流程图、护理协调图或治疗时间表）
2. 对于复杂的计划：包括决策算法流程图
3. 对于康复计划：包括里程碑进展图

**如何生成图形：**
- 使用**scientific-schematics**技能生成AI驱动的出版质量图表
- 用自然语言简单描述您想要的图表
- Nano Banana Pro 将自动生成、审查和完善原理图

**如何生成原理图：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI将自动：
- 使用正确的格式创建出版质量的图像
- 通过多次迭代进行审查和完善
- 确保可访问性（色盲友好、高对比度）
- 将输出保存在figures/目录中

**何时添加原理图：**
- 治疗途径流程图
- 护理协调图
- 治疗进展时间表
- 多学科团队交互图
- 药物管理流程图
- 康复方案可视化
- 临床决策算法图
- 任何受益于可视化的复杂概念

有关创建原理图的详细指导，请参阅scientific-schematics技能文档。

---

## 文档格式和最佳实践

### 文档长度选项

根据临床复杂性和用例，治疗计划有三种格式可供选择：

#### 选项 1：一页治疗计划（大多数情况下首选）

**何时使用**：简单的临床场景、标准协议、繁忙的临床环境

**格式**：单页包含可扫描部分中的所有基本治疗信息
- 无需目录
- 没有详尽的叙述
- 仅关注可操作的项目
- 类似于精准肿瘤学报告或治疗推荐卡

**必填部分**（全部在一页上）：
1. **标题框**：患者信息、诊断、日期、分子/风险概况（如果适用）
2. **治疗计划**：具体干预措施的编号列表
3. **支持护理**：简要要点
4. **基本原理**：1-2 句话理由（标准协议可选）
5. **监控**：关键参数和频率
6. **证据级别**：指南参考或证据等级（例如，“1 级，FDA 已批准”）
7. **预期结果**：时间表和成功指标

**设计原则**：
- 使用小框/表格进行组织（如临床治疗推荐卡格式）
- 删除所有非必要的文本
- 使用临床医生熟悉的缩写
- 密集的信息布局——最大化每平方英寸的信息
- 考虑“快速参考卡”而不是“综合文档”

**结构示例**：
```latex
[Patient ID/Diagnosis Box at top]

TARGET PATIENT POPULATION
  Number of patients, demographics, key features

PRIMARY TREATMENT REGIMEN
  • Medication 1: dose, frequency, duration
  • Procedure: specific details
  • Monitoring: what and when

SUPPORTIVE CARE
  • Key supportive medications

RATIONALE
  Brief clinical justification

MOLECULAR TARGETS / RISK FACTORS
  Relevant biomarkers or risk stratification

EVIDENCE LEVEL
  Guideline reference, trial data

MONITORING REQUIREMENTS
  Key labs/vitals, frequency

EXPECTED CLINICAL BENEFIT
  Primary endpoint, timeline
```

#### 选项 2：标准 3-4 页面格式

**何时使用**：中等复杂性、需要患者教育材料、多学科协调

使用基础医学首页摘要模型以及 2-3 页的附加详细信息。

#### 选项 3：扩展 5-6 页格式

**何时使用**：复杂的合并症、研究方案、需要广泛的安全监测

### 第一页摘要（基础医学模型）

**关键要求：所有治疗计划必须仅在首页、任何目录或详细部分之前有完整的执行摘要。**

遵循精准医学报告和临床摘要文件的基础医学模型，治疗计划以一页执行摘要开始，可立即访问关键的可操作信息。整个摘要必须适合第一页。

**所需的首页结构（按顺序）：**

1. **标题和副标题**
   - 主标题：治疗计划类型（例如“综合治疗计划”）
   - 副标题：具体情况或焦点（例如，“2 型糖尿病 - 年轻成人患者”）

2. **报告信息框**（使用`\begin{infobox}`或`\begin{patientinfo}`）
   - 报告类型/文件目的
   - 计划创建日期
   - 患者人口统计数据（年龄、性别、去识别化）
   - 使用 ICD-10 代码进行初步诊断
   - 报告作者/诊所（如果适用）
   - 使用的分析方法或框架

3. **主要发现或治疗要点**（使用适当的盒子类型的 2-4 个彩色盒子）
   - **主要治疗目标**（使用 `\begin{goalbox}`）
     - 2-3 SMART 目标（项目符号格式）
   - **主要干预**（使用 `\begin{keybox}` 或 `\begin{infobox}`）
     - 2-3个关键干预措施（药理学、非药理学、监测）
   - **关键决策点**（紧急情况下使用 `\begin{warningbox}`）
     - 重要的监控阈值或安全注意事项
   - **时间线概述**（使用 `\begin{infobox}`）
     - 简短的治疗持续时间/阶段
     - 关键里程碑日期

**视觉格式要求：**
- 使用 `\thispagestyle{empty}` 从首页删除页码
- 所有内容必须适合第 1 页（`\newpage` 之前）
- 使用不同颜色的彩色框（tcolorbox包）来表示不同的信息类型
- 盒子应该在视觉上突出并且易于扫描
- 使用简洁的要点格式
- 目录（如果包含）从第 2 页开始
- 详细部分从第 3 页开始

**首页结构示例：**
```latex
\maketitle
\thispagestyle{empty}

% Report Information Box
\begin{patientinfo}
  Report Type, Date, Patient Info, Diagnosis, etc.
\end{patientinfo}

% Key Finding #1: Treatment Goals
\begin{goalbox}[Primary Treatment Goals]
  • Goal 1
  • Goal 2
  • Goal 3
\end{goalbox}

% Key Finding #2: Main Interventions
\begin{keybox}[Core Interventions]
  • Intervention 1
  • Intervention 2
  • Intervention 3
\end{keybox}

% Key Finding #3: Critical Monitoring (if applicable)
\begin{warningbox}[Critical Decision Points]
  • Decision point 1
  • Decision point 2
\end{warningbox}

\newpage
\tableofcontents  % TOC on page 2
\newpage  % Detailed content starts page 3
```

### 简洁的文档

**关键：治疗计划必须优先考虑简洁性和临床相关性。默认最多 3-4 页，除非临床复杂性绝对需要更多细节。**

治疗计划应优先考虑**清晰度和可操作性**，而不是详尽的细节：

- **重点**：仅包含影响护理决策的临床重要信息
- **可操作**：强调需要做什么、何时以及为什么
- **高效**：在不牺牲临床质量的情况下促进快速决策
- **目标长度选项**：
  - **1 页格式**（简单案例的首选）：包含所有基本信息的快速参考卡
  - **标准 3-4 页**：带有首页摘要 + 支持详细信息的标准格式
  - **5-6 页**（罕见）：仅适用于具有多种合并症或多学科干预的高度复杂的病例

**精简指南：**
- **首页摘要**：使用单独的彩色框来整合关键信息（目标、干预措施、决策点） - 仅此一项通常就可以传达基本的治疗计划
- **消除冗余**：如果信息位于第一页摘要中，请勿在详细部分逐字重复
- **患者教育部分**：仅针对关键主题和警告标志的 3-5 个关键要点
- **风险缓解部分**：仅突出显示关键的药物安全问题和紧急行动（并非详尽列表）
- **预期结果部分**：关于预期响应和时间表的 2-3 条简明陈述
- **干预措施**：重点关注主要干预措施；简短项目符号格式的次要/支持性措施
- **广泛使用表格和要点**以实现高效演示
- **避免叙事性散文**，结构化列表就足够了
- **适当时合并相关部分**以减少页数

### 质量重于数量

目标是提供专业、临床完整的文档，尊重临床医生的时间，同时确保全面的患者护理。每个部分都应该增加价值；删除或压缩不直接影响治疗决策的部分。

### 引文和证据支持

**使用最少的、有针对性的引用来支持临床建议：**

- **首选文本引用**：除非特别要求，否则使用简短的文本引用（作者年份）或简单的参考文献，而不是广泛的参考书目
- **何时引用**：
  - 临床实践指南建议（例如“根据 ADA 2024 指南”）
  - 具体药物剂量或方案（例如“ACC/AHA 建议”）
  - 需要证据支持的新颖或有争议的干预措施
  - 风险分层工具或经过验证的评估量表
- **何时不引用**：
  - 标准护理干预措施在该领域得到广泛接受
  - 基本医学事实和常规临床实践
  - 一般患者教育内容
- **引文格式**： 
  - 内联：“开始二甲双胍作为一线治疗（ADA 标准护理 2024 年）”
  - 最低限度：“治疗遵循 ACC/AHA 心力衰竭指南”
  - 除非文件用于学术/研究目的，否则避免使用正式编号的参考文献和大量的参考书目部分
- **保持简短**：3-4 页的治疗计划最多应有 0-3 次引用，仅在对临床可信度或新颖建议至关重要的情况下

## 核心能力

### 1. 一般医疗计划

一般医疗计划可解决常见的慢性病和需要结构化治疗干预的急性医疗问题。

#### 标准组件

**患者信息（去识别化）**
- 人口统计（年龄、性别、相关医学背景）
- 活跃的医疗状况和合并症
- 目前的药物和过敏情况
- 相关社会和家族史
- 特征状态和基线评估
- **HIPAA 合规性**：按照安全港方法删除所有 18 个标识符

**诊断和评估总结**
- 使用 ICD-10 代码进行初步诊断
- 二次诊断和合并症
- 严重程度分类和分期
- 特征限制和生活质量影响
- 风险分层（例如心血管风险、跌倒风险）
- 预后指标

**治疗目标（SMART 格式）**

短期目标（1-3个月）：
- **具体**：明确定义的结果（例如，“将 HbA1c 降低至 <7%”）
- **可测量**：可量化的指标（例如，“收缩压降低 10 mmHg”）
- **可实现**：考虑到患者的实际能力
- **相关**：与患者的优先事项和价值观保持一致
- **有时限**：特定时间范围（例如“8 周内”）

长期目标（6-12个月）：
- 疾病控制或缓解目标
- 特征改进目标
- 生活质量提高
- 预防并发症
- 维持独立性

**干预**

*药理*：
- 具有特定剂量、途径、频率的药物
- 滴定时间表和目标剂量
- 药物相互作用注意事项
- 监测不良反应
- 药物协调

*非药理学*：
- 改变生活方式（饮食、锻炼、戒烟）
- 行为干预
- 患者教育和自我管理
- 监测和自我跟踪（血糖、血压、体重）
- 辅助器具或适应性设备

*程序*：
- 计划的程序或干预措施
- 转介专家
- 诊断测试时间表
- 预防保健（疫苗接种、筛查）

**时间表和时间表**
- 具有特定时间范围的治疗阶段
- 预约频率（每周、每月、每季度）
- 里程碑评估和目标评估
- 药物调整时间表
- 预计治疗持续时间

**监控参数**
- 跟踪临床结果（生命体征、实验室值、症状）
- 评估工具和量表（例如 PHQ-9、疼痛量表）
- 监测频率
- 干预或升级的阈值
- 患者报告的结果

**预期结果**
- 主要结果指标
- 成功标准和基准
- 预计改进时间表
- 治疗修改标准
- 长期预后

**后续计划**
- 预定的约会和重新评估
- 沟通计划（电话、安全消息传递）
- 紧急联络程序
- 紧急评估标准
- 过渡或出院计划

**患者教育**
- 了解病情和治疗原理
- 自我管理技能训练
- 药物管理和依从性
- 警告信号以及何时寻求帮助
- 资源和支持服务

**风险缓解**
- 潜在的不利影响和管理
- 药物相互作用和禁忌证
- 预防跌倒、预防感染
- 紧急行动计划
- 安全监控

#### 常见应用

- 糖尿病管理
- 高血压控制
- 心力衰竭治疗
- 慢性阻塞性肺病管理
- 哮喘护理计划
- 高脂血症治疗
- 骨关节炎管理
- 慢性肾脏病

### 2. 康复治疗计划

康复计划的重点是通过结构化的治疗计划恢复特征、改善活动能力和提高生活质量。

#### 核心组件

**特征评估**
- 基线特征状态（ADL、IADL）
- 运动范围、力量、平衡、耐力
- 步态分析和行动能力评估
- 标准化测量（FIM、Barthel 指数、Berg 平衡量表）
- 环境评估（家庭安全、无障碍）

**康复目标**

*减值水平目标*：
- 将肩部屈曲提高至 140 度
- 将股四头肌力量增加 2/5 MMT 等级
- 增强平衡性（伯格分数 >45/56）

*活动级别目标*：
- 借助辅助装置独立行走 150 英尺
- 在扶手监督下爬 12 级楼梯
- 独立地将床转移到椅子上

*参与级目标*：
- 修改后返回工作
- 恢复娱乐活动
- 独立社区流动性

**治疗干预**

*物理治疗*：
- 治疗性练习（力量、伸展、耐力）
- 手法治疗技术
- 步态训练和平衡活动
- 方式（热、冰、电刺激、超声波）
- 辅助器具训练

*职业治疗*：
- ADL 训练（洗澡、穿衣、梳洗、进食）
- 上肢力量和协调性
- 适应性设备和修改
- 节能技术
- 认知康复

*言语病理学*：
- 吞咽治疗和吞咽困难管理
- 沟通策略和增强设备
- 认知语言治疗
- 声音治疗

*其他服务*：
- 休闲疗法
- 水生疗法
- 心脏康复
- 肺康复
- 前庭康复

**治疗时间表**
- 频率：每周 3 次 PT，2 次/周 OT（示例）
- 课程时长：45-60 分钟
- 治疗阶段持续时间（急性、亚急性、维持）
- 预计总持续时间：8-12周
- 重新评估间隔

**进度监控**
- 每周特征评估
- 标准化结果衡量
- 目标达成规模
- 疼痛和症状追踪
- 患者满意度

**家庭锻炼计划**
- 具有重复次数/组数/频率的特定练习
- 注意事项和安全说明
- 进展标准
- 自我监控策略

#### 专业康复

- 中风后康复
- 骨科康复（关节置换、骨折）
- 心脏康复（心梗后、手术后）
- 肺康复
- 前庭康复
- 神经康复
- 运动损伤康复

### 3. 心理健康治疗计划

心理健康治疗计划通过综合心理治疗、药物和心理社会干预来解决精神疾病。

#### 基本组件

**精神评估**
- 初级精神病学诊断（DSM-5 标准）
- 症状严重程度和特征障碍
- 同时发生的心理健康状况
- 物质使用评估
- 自杀/他杀风险评估
- 创伤史和 PTSD 筛查
- 心理健康的社会决定因素

**治疗目标**

*症状减轻*：
- 降低抑郁严重程度（PHQ-9 评分从 18 降至 <10）
- 减轻焦虑症状（GAD-7 评分<5）
- 改善睡眠质量（匹兹堡睡眠质量指数）
- 稳定情绪（减少情绪发作）

*特征改进*：
- 返回工作或学校
- 改善社会关系和支持
- 增强应对技巧和情绪调节
- 增加对有意义的活动的参与

*以恢复为导向的目标*：
- 建立韧性和自我效能
- 培养危机管理技能
- 建立可持续的健康习惯
- 实现个人康复目标

**治疗干预**

*心理治疗*：
- 循证模式（CBT、DBT、ACT、心理动力学、IPT）
- 会议频率（每周、每两周）
- 治疗持续时间（12-16 周，持续）
- 具体技术和目标
- 团体治疗参与

*精神药理学*：
- 药物类别和基本原理
- 起始剂量和滴定时间表
- 目标症状
- 预期反应时间（抗抑郁药 2-4 周）
- 副作用监测
- 联合治疗注意事项

*心理干预*：
- 案件管理服务
- 同伴支持计划
- 家庭治疗或心理教育
- 职业康复
- 支持性住房或社区融合
- 药物滥用治疗

**安全规划**
- 危机联系人和紧急服务
- 警告信号和触发因素
- 应对策略和自我安抚技巧
- 安全环境改造
- 手段限制（枪支、药物）
- 支持系统激活

**监测和评估**
- 症状评定量表（每周或每两周）
- 药物依从性和副作用
- 自杀意念筛查
- 特征状态评估
- 治疗参与和治疗联盟

**患者和家庭教育**
- 诊断心理教育
- 治疗理由和期望
- 用药信息
- 预防复发策略
- 社区资源

#### 心理健康状况

- 重度抑郁症
- 焦虑症（广泛性焦虑症、恐慌、社交焦虑）
- 双相情感障碍
- 精神分裂症和精神障碍
- PTSD 和创伤相关疾病
- 饮食失调
- 物质使用障碍
- 人格障碍

### 4. 慢性病管理计划

针对需要持续监测、治疗调整和多学科协调的慢性病的综合长期护理计划。

#### 主要特点

**特定疾病目标**
- 根据指南的循证治疗目标
- 适合阶段的干预措施
- 并发症预防策略
- 疾病进展监测

**自我管理支持**
- 患者的激活和参与
- 共同决策
- 针对症状变化的行动计划
- 技术支持的监控（应用程序、远程监控）

**护理协调**
- 初级保健医生的监督
- 专家咨询和共同管理
- 护理过渡（医院到家庭）
- 跨提供商的药物管理
- 通讯协议

**人口健康一体化**
- 注册跟踪和外展
- 预防保健和筛查时间表
- 质量测量报告
- 护理差距识别

#### 适用条件

- 1 型和 2 型糖尿病
- 心血管疾病（CHF、CAD）
- 慢性呼吸道疾病（慢性阻塞性肺病、哮喘）
- 慢性肾脏病
- 炎症性肠病
- 类风湿性关节炎和自身免疫性疾病
- HIV/AIDS
- 癌症生存护理

### 5. 围手术期护理计划

为手术和手术患者制定结构化计划，涵盖术前准备、术中管理和术后恢复。

#### 组件

**术前评估**
- 手术指征和计划程序
- 术前风险分层（ASA分级，心脏风险）
- 优化医疗条件
- 药物管理（继续、停药）
- 术前测试和许可
- 知情同意和患者教育

**围手术期干预**
- 加速康复外科 (ERAS) 方案
- 静脉血栓栓塞的预防
- 抗生素预防
- 血糖控制策略
- 疼痛管理计划（multimodal镇痛）

**术后护理**
- 立即恢复目标（24-48 小时）
- 早期活动方案
- 饮食进步
- 伤口护理和引流管理
- 疼痛控制方案
- 并发症监测

**出院计划**
- 活动限制和进展
- 药物协调
- 后续预约
- 家庭健康或康复服务
- 重返工作岗位时间表

### 6. 疼痛管理计划

使用循证干预措施和阿片类药物节约策略来治疗急性和慢性疼痛。

#### 全面的组件

**疼痛评估**
- 疼痛位置、性质、强度（0-10 级）
- 时间模式（持续、间歇、突破）
- 加重和减轻因素
- 特征影响（睡眠、活动、情绪）
- 既往治疗和反应
- 社会心理贡献者

**多模式干预**

*药理*：
- 非阿片类镇痛药（对乙酰氨基酚、NSAID）
- 辅助药物（抗抑郁药、抗惊厥药、肌肉松弛药）
- 局部用药（利多卡因、辣椒素、双氯芬酸）
- 阿片类药物治疗（适当时，降低风险）
- 滴定和旋转策略

*干预程序*：
- 神经阻滞和注射
- 射频消融术
- 脊髓刺激
- 鞘内给药

*非药理学*：
- 物理治疗和锻炼
- 疼痛的认知行为疗法
- 正念和放松技巧
- 针灸
- 十位单位

**阿片类药物安全性（处方时）**
- 指示和计划持续时间
- 处方药监测计划（PDMP）检查
- 阿片类药物风险评估工具
- 纳洛酮处方
- 治疗协议
- 随机尿液药物筛查
- 经常跟进和重新评估

**特征目标**
- 具体活动的改进
- 睡眠质量提升
- 减少疼痛干扰
- 提高生活质量
- 返回工作岗位或有意义的活动

## 最佳实践

### 简洁和重点（最高优先级）

**治疗计划必须简洁并侧重于可操作的临床信息：**

- **首选 1 页格式**：对于大多数临床情况，单页治疗计划（如精准肿瘤学报告）提供了所有必要的信息
- **默认为可能的最短格式**：从 1 页开始；仅在临床复杂性确实需要时才扩展
- **每句话都必须增加价值**：如果某个部分不会改变临床决策，则完全省略它
- **认为“快速参考卡”而不是“综合教科书”**：忙碌的临床医生需要可扫描的、密集的信息
- **避免学术冗长**：这是临床文档，而不是文献综述或教学文档
- **按复杂程度划分的最大长度**：
  - 简单/标准案例：1页
  - 中等复杂度：3-4页（首页摘要+详细信息）
  - 高复杂性（罕见）：最多 5-6 页

### 第一页摘要（最重要）

**始终创建单页执行摘要作为第一页：**
- 第一页必须仅包含：标题、报告信息框和主要调查结果框
- 这提供了类似于精准医学报告的概览
- 目录和详细部分从第 2 页或更高版本开始
- 将其视为忙碌的临床医生可以在 30 秒内扫描的“临床亮点”页面
- 使用 2-4 个彩色框表示不同的关键发现（目标、干预措施、决策点）
- **强大的首页通常可以独立** - 后续页面用于详细信息，而不是重复

### SMART 目标设定

所有治疗目标应满足 SMART 标准：

- **具体**：“将 HbA1c 提高至 <7%”而不是“更好地控制糖尿病”
- **可衡量**：使用可量化的指标、经过验证的尺度、客观的衡量标准
- **可实现**：考虑患者的能力、资源、社会支持
- **相关**：与患者价值观、优先事项和生活环境保持一致
- **有时限**：为目标实现和重新评估定义明确的时间表

### 以患者为中心的护理

✓ **共同决策**：让患者参与目标设定和治疗选择  
✓ **文化能力**：尊重文化信仰、语言偏好、健康素养  
✓ **患者偏好**：尊重治疗偏好和个人价值观  
✓ **个性化**：根据患者的独特情况定制计划  
✓ **赋权**：支持患者激活和自我管理  

### 循证实践

✓ **临床指南**：遵循当前专业协会的建议  
✓ **质量衡量**：纳入 HEDIS、CMS 质量衡量  
✓ **比较有效性**：使用已证明有效的治疗方法  
✓ **避免低价值护理**：消除不必要的测试和干预  
✓ **保持最新**：根据新出现的证据更新计划  

### 文件标准

✓ **完整性**：包括所有必需的元素  
✓ **清晰**：使用清晰、专业的医学语言  
✓ **准确性**：确保事实正确性和最新信息  
✓ **及时性**：及时记录计划  
✓ **易读性**：专业的格式和组织  
✓ **签名和日期**：验证所有治疗计划  

### 监管合规性

✓ **HIPAA 隐私**：取消识别所有受保护的健康信息  
✓ **知情同意**：记录患者的理解和同意  
✓ **计费支持**：包括支持医疗必要性的文件  
✓ **质量报告**：启用质量指标提取  
✓ **法律保护**：维护有依据的临床文件  

### 多学科协调

✓ **团队沟通**：在护理团队中共享计划  
✓ **角色清晰**：定义每个团队成员的职责  
✓ **护理过渡**：确保跨环境的连续性  
✓ **专科整合**：与亚专科护理协调  
✓ **以患者为中心的医疗之家**：符合 PCMH 原则  

## LaTeX 模板用法

### 模板选择

根据临床情况和所需长度选择适当的模板：

#### 简洁的模板（首选）

1. **one_page_treatment_plan.tex** - 大多数情况下的**第一选择**
   - 所有临床专科
   - 标准协议和简单案例
   - 类似于精准肿瘤学报告的快速参考格式
   - 密集、可扫描、以临床医生为中心
   - 除非复杂性需要更多细节，否则使用此选项

#### 标准模板（3-4页）

仅当一页格式因复杂性而不够时使用：

2. **general_medical_treatment_plan.tex** - 初级保健、慢性病、普通医学
3. **rehabilitation_treatment_plan.tex** - PT/OT、术后、损伤恢复
4. **mental_health_treatment_plan.tex** - 精神疾病、行为健康
5. **chronic_disease_management_plan.tex** - 复杂的慢性疾病，多种情况
6. **perioperative_care_plan.tex** - 手术患者、手术护理
7. **pain_management_plan.tex** - 急性或慢性疼痛状况

**注意**：即使使用标准模板，也可以通过删除非必要部分来使其简洁（最多 3-4 页）。

### 模板结构

所有 LaTeX 模板包括：
- 具有适当边距和字体的专业格式
- 所有必需组件的结构化部分
- 药物、干预措施、时间表的表格
- 具有 SMART 标准的目标跟踪部分
- 提供者签名和日期的空间
- 符合 HIPAA 的去识别化指南
- 评论有详细说明

### 生成 PDF

```bash
# Compile LaTeX template to PDF
pdflatex general_medical_treatment_plan.tex

# For templates with references
pdflatex treatment_plan.tex
bibtex treatment_plan
pdflatex treatment_plan.tex
pdflatex treatment_plan.tex
```

## 验证和质量保证

### 完整性检查

使用验证脚本确保所有必需的部分都存在：

```bash
python check_completeness.py my_treatment_plan.tex
```

该脚本检查：
- 患者信息部分
- 诊断与评估
- SMART 目标（短期和长期）
- 干预措施（药理学、非药理学）
- 时间表和时间表
- 监测参数
- 预期成果
- 后续计划
- 患者教育
- 风险缓解

### 治疗计划验证

治疗计划质量的综合验证：

```bash
python validate_treatment_plan.py my_treatment_plan.tex
```

验证包括：
- SMART 目标标准评估
- 循证干预验证
- 时间表可行性检查
- 监控参数充足性
- 安全和风险缓解审查
- 监管合规性检查

### 质量检查表

根据质量检查表 (`quality_checklist.md`) 审查治疗计划：

**临床质量**
- [ ] 诊断准确且编码正确 (ICD-10)
- [ ] 目标是 SMART 并以患者为中心
- [ ] 干预措施基于证据且符合指南
- [ ] 时间表现实且明确
- [ ] 监测计划全面
- [ ] 解决了安全考虑

**以患者为中心的护理**
- [ ] 纳入患者偏好和价值观
- [ ] 共同决策记录在案
- [ ] 健康素养适当的语言
- [ ] 涉及文化因素
- [ ] 包括患者教育计划

**监管合规性**
- [ ] 符合HIPAA的去标识化
- [ ] 记录医疗必要性
- [ ] 已注明知情同意书
- [ ] 提供者签名和凭证
- [ ] 计划创建/修订日期

**协调与沟通**
- [ ] 记录专家推荐
- [ ] 护理团队角色定义
- [ ] 后续时间表明确
- [ ] 提供紧急联系人
- [ ] 解决过渡计划

## 与其他技能的整合

### 临床报告整合

治疗计划通常附有其他临床文件：

- **SOAP 注释**（`clinical-reports` 技能）：记录正在进行的实施
- **H&P**（`clinical-reports` 技能）：初步评估告知治疗计划
- **出院总结**（`clinical-reports` 技能）：总结治疗计划执行情况
- **进度注释**：跟踪目标实现和计划修改

### 科学写作整合

循证治疗计划需要文献支持：

- **引文管理**（`citation-management` 技能）：参考临床指南
- **文献综述**（`literature-review` 技能）：了解治疗证据基础
- **研究查找**（`research-lookup` 技能）：查找当前最佳实践

### 研究整合

可以为临床试验或研究制定治疗计划：

- **研究资助**（`research-grants` 技能）：资助研究的治疗计划
- **临床试验报告**（`clinical-reports` 技能）：干预文档

## 常见用例

### 示例 1：2 型糖尿病管理

**场景**：58岁新诊断2型糖尿病患者，HbA1c 8.5%，BMI 32

**模板**：`general_medical_treatment_plan.tex`

**目标**：
- 短期：3个月内将HbA1c降低至<7.5%
- 长期：实现 HbA1c <7%，6 个月内减掉 15 磅

**干预**：
- 药理学：二甲双胍 500mg BID，滴定至 1000mg BID
- 生活方式：地中海饮食、每周 150 分钟适度运动
- 教育：糖尿病自我管理教育、血糖监测

### 示例2：中风后康复

**场景**：70 岁患者左 MCA 中风伴右侧偏瘫

**模板**：`rehabilitation_treatment_plan.tex`

**目标**：
- 短期：4周内将右臂力量提高2/5至3/5
- 长期：12 周内拄着拐杖独立行走 150 英尺

**干预**：
- PT 3 次/周：步态训练、平衡、强化
- OT 3 次/周：ADL 训练、上肢特征
- SLP 2 次/周：吞咽困难治疗

### 示例 3：重度抑郁症

**场景**：35 岁，患有中度抑郁症，PHQ-9 评分 16

**模板**：`mental_health_treatment_plan.tex`

**目标**：
- 短期：8周内将PHQ-9降低至<10
- 长期：达到缓解（PHQ-9 <5），重返工作岗位

**干预**：
- 心理治疗：CBT 每周课程
- 药物治疗：舍曲林每日 50 毫克，滴定至 100 毫克
- 生活方式：睡眠卫生、锻炼 30 分钟，每周 5 次

### 示例 4：全膝关节置换术

**场景**：68 岁的患者因骨关节炎计划接受右侧 TKA

**模板**：`perioperative_care_plan.tex`

**术前目标**：
- 优化糖尿病控制（血糖<180）
- 按照方案停止抗凝治疗
- 完成体检

**术后目标**：
- 通过 POD 1 行走 50 英尺
- POD 3 使膝关节弯曲 90 度
- 通过 POD 2-3 接受 PT 服务出院回家

### 示例 5：慢性腰痛

**场景**：45岁，患有慢性非特异性腰痛，疼痛7/10

**模板**：`pain_management_plan.tex`

**目标**：
- 短期：6 周内将疼痛减轻至 4/10
- 长期：恢复全职工作，疼痛 2-3/10

**干预**：
- 药理学：加巴喷丁 300mg TID，度洛西汀 60mg 每日
- PT：核心强化，麦肯齐练习 2 次/周 x 8 周
- 行为：针对疼痛的 CBT、正念冥想
- 介入治疗：如果反应不足，请考虑腰椎 ESI

## 专业标准和指南

治疗计划应符合：

### 全科医学
- 美国糖尿病协会 (ADA) 护理标准
- ACC/AHA 心血管指南
- 慢性阻塞性肺病黄金指南
- JNC-8 高血压指南
- KDIGO 慢性肾脏病指南

### 康复治疗
- APTA 临床实践指南
- AOTA实践指南
- 心脏康复指南 (AHA/AACVPR)
- 中风康复指南

### 心理健康
- APA 实践指南
- 退伍军人管理局/国防部临床实践指南
- NICE 指南（国家健康与护理研究所 Excellence）
- Cochrane 精神科干预评论

### 疼痛管理
- CDC 阿片类药物处方指南
- AAPM/APS 慢性疼痛指南
- 世界卫生组织 痛苦阶梯
- 多模式镇痛最佳实践

## 时间线生成

使用时间线生成器脚本创建视觉治疗时间线：

```bash
python timeline_generator.py --plan my_treatment_plan.tex --output timeline.pdf
```

生成：
- 治疗阶段甘特图
- 目标评估的里程碑标记
- 药物滴定时间表
- 后续预约日历
- 随时间变化的干预强度

## 支持和资源

### 模板生成

交互式模板选择：

```bash
cd .claude/skills/treatment-plans/scripts
python generate_template.py

# Or specify type directly
python generate_template.py --type mental_health --output depression_treatment_plan.tex
```

### 验证工作流程

1. **使用适当的 LaTeX 模板创建治疗计划**
2. **检查完整性**：`python check_completeness.py plan.tex`
3. **验证质量**：`python validate_treatment_plan.py plan.tex`
4. **审查清单**：与 `quality_checklist.md` 进行比较
5. **生成PDF**：`pdflatex plan.tex`
6. **与患者一起审查**：确保理解和同意
7. **实施和记录**：跟踪临床记录中的进展

### 其他资源

- 专业协会的临床实践指南
- AHRQ 有效的医疗保健计划
- 干预证据 Cochrane 图书馆
- UpToDate 和 DynaMed 提供治疗建议
- CMS 质量措施和 HEDIS 规范

## 专业文档样式

### 概述

使用 `medical_treatment_plan.sty` LaTeX 包可以通过专业的医疗文档样式来增强治疗计划。这种定制风格将简单的学术文档转换为视觉上吸引人的、颜色编码的临床文档，在保持科学严谨性的同时提高可读性和可用性。

### 医疗计划式套餐

`medical_treatment_plan.sty` 封装（位于 `assets/medical_treatment_plan.sty`）提供：

**专业配色方案**
- **原色蓝色**（RGB：0、102、153）：标题、章节标题、主要强调色
- **次要蓝色**（RGB：102、178、204）：浅色背景，微妙的强调
- **强调蓝色**（RGB：0、153、204）：超链接、关键亮点
- **成功绿色**（RGB：0、153、76）：目标、积极成果
- **警告红色** (RGB: 204, 0, 0)：警告，关键信息
- **深灰色**（RGB：64、64、64）：正文
- **浅灰色**（RGB：245、245、245）：背景填充

**样式元素**
- 具有专业规则的自定义彩色页眉和页脚
- 带下划线的蓝色部分标题，层次结构清晰
- 使用彩色标题和交替行增强表格格式
- 使用彩色项目符号和编号优化列表间距
- 专业的页面布局，具有适当的边距

### 定制信息盒

该样式包包括五个用于组织临床信息的专用盒子环境：

#### 1.信息框（蓝色边框，浅灰色背景）

有关一般信息、临床评估和测试时间表：

```latex
\begin{infobox}[Title]
  \textbf{Key Information:}
  \begin{itemize}
    \item Clinical assessment details
    \item Testing schedules
    \item General guidance
  \end{itemize}
\end{infobox}
```

**使用案例**：代谢状态、基线评估、监测计划、滴定方案

#### 2. 警告框（红框黄底）

对于关键决策点、安全协议和警报：

```latex
\begin{warningbox}[Alert Title]
  \textbf{Important Safety Information:}
  \begin{itemize}
    \item Critical drug interactions
    \item Safety monitoring requirements
    \item Red flag symptoms requiring immediate action
  \end{itemize}
\end{warningbox}
```

**用例**：用药安全、决策点、禁忌证、紧急方案

#### 3. 目标框（绿色边框，绿色背景）

对于治疗目的、目标和成功标准：

```latex
\begin{goalbox}[Treatment Goals]
  \textbf{Primary Objectives:}
  \begin{itemize}
    \item Reduce HbA1c to <7\% within 3 months
    \item Achieve 5-7\% weight loss in 12 weeks
    \item Complete diabetes education program
  \end{itemize}
\end{goalbox}
```

**用例**：SMART 目标、目标结果、成功指标、CGM 目标

#### 4. 要点框（蓝色背景）

对于执行摘要、要点和重要建议：

```latex
\begin{keybox}[Key Highlights]
  \textbf{Essential Points:}
  \begin{itemize}
    \item Main therapeutic approach
    \item Critical patient instructions
    \item Priority interventions
  \end{itemize}
\end{keybox}
```

**使用案例**：计划概述、平板方法说明、重要饮食指南

#### 5. 应急箱（大红色设计）

对于紧急联系人和紧急协议：

```latex
\begin{emergencybox}
  \begin{itemize}
    \item \textbf{Emergency Services:} 911
    \item \textbf{Endocrinology Office:} [Phone] (business hours)
    \item \textbf{After-Hours Hotline:} [Phone] (nights/weekends)
    \item \textbf{Pharmacy:} [Phone and location]
  \end{itemize}
\end{emergencybox}
```

**用例**：紧急联系人、关键热线、紧急资源信息

#### 6. 患者信息框（白色，蓝色边框）

对于患者人口统计数据和基线信息：

```latex
\begin{patientinfo}
  \begin{tabular}{ll}
    \textbf{Age:} & 23 years \\
    \textbf{Sex:} & Male \\
    \textbf{Diagnosis:} & Type 2 Diabetes Mellitus \\
    \textbf{Plan Start Date:} & \today \\
  \end{tabular}
\end{patientinfo}
```

**用例**：患者信息部分、人口统计数据

### 专业表格格式设置

具有医疗风格的增强桌面环境：

```latex
\begin{medtable}{Caption Text}
\begin{tabular}{|p{5cm}|p{4cm}|p{4.5cm}|}
\hline
\tableheadercolor  % Blue header with white text
\textcolor{white}{\textbf{Column 1}} & 
\textcolor{white}{\textbf{Column 2}} & 
\textcolor{white}{\textbf{Column 3}} \\
\hline
Data row 1 content & Value 1 & Details 1 \\
\hline
\tablerowcolor  % Alternating light gray row
Data row 2 content & Value 2 & Details 2 \\
\hline
Data row 3 content & Value 3 & Details 3 \\
\hline
\end{tabular}
\caption{Table caption}
\end{medtable}
```

**特点：**
- 蓝色标题和白色文本，视觉上突出
- 交替行颜色 (`\tablerowcolor`) 以提高可读性
- 自动居中和间距
- 专业的边框和内边距

### 使用样式包

#### 基本设置

1. **添加到文档序言：**

```latex
% !TEX program = xelatex
\documentclass[11pt,letterpaper]{article}

% Use custom medical treatment plan style
\usepackage{medical_treatment_plan}
\usepackage{natbib}

\begin{document}
\maketitle
% Your content here
\end{document}
```

2. **确保样式文件与 `.tex` 文件位于同一目录**，或安装到 LaTeX 路径

3. **使用 XeLaTeX 进行编译**（建议获得最佳结果）：

```bash
xelatex treatment_plan.tex
bibtex treatment_plan
xelatex treatment_plan.tex
xelatex treatment_plan.tex
```

#### 自定义标题页

该包会自动使用专业的蓝色标题来格式化标题：

```latex
\title{\textbf{Individualized Diabetes Treatment Plan}\\
\large{23-Year-Old Male Patient with Type 2 Diabetes}}
\author{Comprehensive Care Plan}
\date{\today}

\begin{document}
\maketitle
```

这将创建一个带有白色文本和清晰层次结构的引人注目的蓝色框。

### 编译要求

**所需的LaTeX包**（由样式自动加载）：
- `geometry` - 页面布局和边距
- `xcolor` - 颜色支持
- `tcolorbox` 与 `[most]` 库 - 自定义彩色框
- `tikz` - 图形和绘图
- `fontspec` - 字体管理（XeLaTeX/LuaLaTeX）
- `fancyhdr` - 自定义页眉和页脚
- `titlesec` - 剖面样式
- `enumitem` - 增强列表格式
- `booktabs` - 专业桌规则
- `longtable` - 多页表
- `array` - 增强的表格特征
- `colortbl` - 彩色表格单元格
- `hyperref` - 超链接和 PDF 元数据
- `natbib` - 书目管理

**推荐编译：**

```bash
# Using XeLaTeX (best font support)
xelatex document.tex
bibtex document
xelatex document.tex
xelatex document.tex

# Using PDFLaTeX (alternative)
pdflatex document.tex
bibtex document
pdflatex document.tex
pdflatex document.tex
```

### 定制选项

#### 改变颜色

编辑样式文件修改配色方案：

```latex
% In medical_treatment_plan.sty
\definecolor{primaryblue}{RGB}{0, 102, 153}      % Modify these
\definecolor{secondaryblue}{RGB}{102, 178, 204}
\definecolor{accentblue}{RGB}{0, 153, 204}
\definecolor{successgreen}{RGB}{0, 153, 76}
\definecolor{warningred}{RGB}{204, 0, 0}
```

#### 调整页面布局

修改样式文件中的几何设置：

```latex
\RequirePackage[margin=1in, top=1.2in, bottom=1.2in]{geometry}
```

#### 自定义字体（仅限 XeLaTeX）

在样式文件中取消注释并修改：

```latex
\setmainfont{Your Preferred Font}
\setsansfont{Your Sans-Serif Font}
```

#### 页眉/页脚定制

在样式文件中修改：

```latex
\fancyhead[L]{\color{primaryblue}\sffamily\small\textbf{Treatment Plan Title}}
\fancyhead[R]{\color{darkgray}\sffamily\small Patient Info}
```

### 样式包下载与安装

#### 选项 1：复制到项目目录

将 `assets/medical_treatment_plan.sty` 复制到 `.tex` 文件所在的目录中。

#### 选项 2：安装到用户 TeX 目录

```bash
# Find your local texmf directory
kpsewhich -var-value TEXMFHOME

# Copy to appropriate location (usually ~/texmf/tex/latex/)
mkdir -p ~/texmf/tex/latex/medical_treatment_plan
cp assets/medical_treatment_plan.sty ~/texmf/tex/latex/medical_treatment_plan/

# Update TeX file database
texhash ~/texmf
```

#### 选项 3：系统范围安装

```bash
# Copy to system texmf directory (requires sudo)
sudo cp assets/medical_treatment_plan.sty /usr/local/texlive/texmf-local/tex/latex/
sudo texhash
```

### 其他专业风格（可选）

CTAN 提供的其他医疗/临床文档样式：

**期刊风格：**
```bash
# Install via TeX Live Manager
tlmgr install nejm        # New England Journal of Medicine
tlmgr install jama        # JAMA style
tlmgr install bmj         # British Medical Journal
```

**一般专业风格：**
```bash
tlmgr install apa7        # APA 7th edition (health sciences)
tlmgr install IEEEtran    # IEEE (medical devices/engineering)
tlmgr install springer    # Springer journals
```

**从 CTAN 下载：**
- 访问：https://ctan.org/
- 搜索医疗文档类别
- 下载并安装每个包的说明

### 故障排查

**问题：找不到包**
```bash
# Install missing packages via TeX Live Manager
sudo tlmgr update --self
sudo tlmgr install tcolorbox tikz pgf
```

**问题：缺少字符（✓、≥ 等）**
- 使用 XeLaTeX 代替 PDFLaTeX
- 或者用LaTeX命令替换：`$\checkmark$`、`$\geq$`
- 需要 `amssymb` 数学符号包

**问题：标题高度警告**
- 样式文件集 `\setlength{\headheight}{22pt}`
- 根据您的内容需要进行调整

**问题：盒子未渲染**
```bash
# Ensure complete tcolorbox installation
sudo tlmgr install tcolorbox tikz pgf
```

**问题：找不到字体 (XeLaTeX)**
- 注释掉 .sty 文件中的自定义字体行
- 或者在您的系统上安装指定的字体

### 样式化文档的最佳实践

1. **适当的盒子用途**
   - 将框类型与内容目的相匹配（目标→绿色，警告→黄色/红色）
   - 不要过度使用盒子；保留真正重要的信息
   - 保持盒子内容简洁、重点突出

2. **视觉层次**
   - 使用结构的剖面样式
   - 用于强调和组织的方框
   - 比较数据表
   - 顺序或分组项目的列表

3. **颜色一致性**
   - 坚持定义的配色方案
   - 使用 `\textcolor{primaryblue}{\textbf{Text}}` 进行强调
   - 保持一致的含义（红色=警告，绿色=目标）

4. **空白空间**
   - 不要用盒子使页面过度拥挤
   - 主要部分之间使用 `\vspace{0.5cm}`
   - 在彩色元素周围留出呼吸空间

5. **专业外观**
   - 保持可读性为首要任务
   - 确保足够的对比度以实现可访问性
   - 测试灰度打印输出
   - 在整个文档中保持样式一致

6. **表格格式**
   - 对所有标题行使用 `\tableheadercolor`
   - 将 `\tablerowcolor` 应用于表中超过 3 行的交替行
   - 保持列宽平衡
   - 对于大型表使用 `\small\sffamily`

### 示例：风格化的治疗计划结构

```latex
% !TEX program = xelatex
\documentclass[11pt,letterpaper]{article}
\usepackage{medical_treatment_plan}
\usepackage{natbib}

\title{\textbf{Comprehensive Treatment Plan}\\
\large{Patient-Centered Care Strategy}}
\author{Multidisciplinary Care Team}
\date{\today}

\begin{document}
\maketitle

\section*{Patient Information}
\begin{patientinfo}
  % Demographics table
\end{patientinfo}

\section{Executive Summary}
\begin{keybox}[Plan Overview]
  % Key highlights
\end{keybox}

\section{Treatment Goals}
\begin{goalbox}[SMART Goals - 3 Months]
  \begin{medtable}{Primary Treatment Targets}
    % Goals table with colored headers
  \end{medtable}
\end{goalbox}

\section{Medication Plan}
\begin{infobox}[Titration Schedule]
  % Medication instructions
\end{infobox}

\begin{warningbox}[Critical Decision Point]
  % Important safety information
\end{warningbox}

\section{Emergency Protocols}
\begin{emergencybox}
  % Emergency contacts
\end{emergencybox}

\bibliographystyle{plainnat}
\bibliography{references}
\end{document}
```

### 专业造型的好处

**临床实践：**
- 在患者就诊期间更快地扫描信息
- 关键信息与常规信息的清晰视觉层次结构
- 专业外观适合面向患者的文档
- 颜色编码部分可减少认知负荷

**教育用途：**
- 增强教材的可读性
- 概念类型的视觉区分（目标、警告、程序）
- 案例讨论的专业演示
- 印刷和数字格式

**文档质量：**
- 现代、抛光的外观
- 保持临床准确性，同时提高美观度
- 治疗计划的标准化格式
- 轻松定制机构品牌

**患者参与：**
- 比密集的文本文档更平易近人
- 颜色编码可帮助患者识别关键部位
- 专业的外表建立信任
- 清晰的组织有助于理解

## 道德考虑

### 知情同意书
所有治疗计划都应让患者理解并自愿同意所提议的干预措施。

### 文化敏感性
治疗计划必须尊重不同的文化信仰、健康习惯和沟通方式。

### 健康公平
制定计划时考虑健康的社会决定因素、获取障碍和健康差异。

### 隐私保护
保持严格的 HIPAA 合规性；取消共享文档中所有受保护健康信息的标识。

### 自主与行善
在医疗建议与患者自主权和价值观之间取得平衡，同时促进患者福利。

## 许可证

克劳德科学作家项目的一部分。请参阅主许可证文件。

