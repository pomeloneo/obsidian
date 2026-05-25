---
name: market-research-reports
description: "以顶级咨询公司（McKinsey、BCG、Gartner）的风格生成全面的市场研究报告（50 多页）。具有专业的LaTeX格式、具有科学原理图和生成图像的广泛视觉生成、与数据收集的研究查找的深度集成以及多框架战略分析，包括Porter五力、PESTLE、SWOT、TAM/SAM/SOM和BCG Matrix。"
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# 市场研究报告

## 概述

市场研究报告是综合性战略文件，分析行业、市场和竞争格局，为业务决策、投资策略和战略规划提供信息。该技能可生成 **50 多页的专业级报告**，具有丰富的视觉内容，以McKinsey、BCG、Bain、Gartner和Forrester等顶级咨询公司的交付成果为蓝本。

**主要特点：**
- **综合长度**：报告设计为 50 多页，没有代币限制
- **视觉丰富的内容**：开始时生成 5-6 个关键图表（在编写过程中根据需要添加更多）
- **数据驱动分析**：与市场数据研究查找深度集成
- **多框架方法**：Porter的五力、PESTLE、SWOT、BCG Matrix、TAM/SAM/SOM
- **专业格式化**：咨询公司质量排版、颜色和布局
- **可行的建议**：实施路线图的战略重点

**输出格式：**LaTeX具有专业造型，编译为PDF。使用`market_research.sty`样式包来实现一致、专业的格式设置。

## 何时使用此技能

在以下情况下应使用此技能：
- 为投资决策创建全面的市场分析
- 为战略规划制定行业报告
- 分析竞争格局和市场动态
- 进行市场规模调整练习(TAM/SAM/SOM)
- 评估市场进入机会
- 为并购活动准备尽职调查材料
- 为行业定位创建思想领导力内容
- 制定进入市场战略文档
- 分析监管和政策对市场的影响
- 为新产品发布构建业务案例

## 视觉增强要求

**关键：市场研究报告应包括关键视觉内容。**

每个报告应在开始时生成 **6 个基本视觉效果**，并在编写过程中根据需要添加其他视觉效果。从最关键的可视化开始建立报告框架。

### 可视化生成工具

**使用`scientific-schematics`用于：**
- 市场增长轨迹图
- TAM/SAM/SOM细分图（同心圆）
- Porter的五力图
- 竞争定位矩阵
- 市场细分图表
- 价值链图
- 技术路线图
- 风险热图
- 战略优先顺序矩阵
- 实施时间表/甘特图
- SWOT分析图
- BCG 增长份额矩阵

```bash
# Example: Generate a TAM/SAM/SOM diagram
python skills/scientific-schematics/scripts/generate_schematic.py \
  "TAM SAM SOM concentric circle diagram showing Total Addressable Market $50B outer circle, Serviceable Addressable Market $15B middle circle, Serviceable Obtainable Market $3B inner circle, with labels and arrows pointing to each segment" \
  -o figures/tam_sam_som.png --doc-type report

# Example: Generate Porter's Five Forces
python skills/scientific-schematics/scripts/generate_schematic.py \
  "Porter's Five Forces diagram with center box 'Competitive Rivalry' connected to four surrounding boxes: 'Threat of New Entrants' (top), 'Bargaining Power of Suppliers' (left), 'Bargaining Power of Buyers' (right), 'Threat of Substitutes' (bottom). Each box should show High/Medium/Low rating" \
  -o figures/porters_five_forces.png --doc-type report
```

**使用`generate-image`用于：**
- 执行摘要英雄信息图表
- 行业/部门概念插图
- 抽象技术可视化
- 封面图像

```bash
# Example: Generate executive summary infographic
python skills/generate-image/scripts/generate_image.py \
  "Professional executive summary infographic for market research report, showing key metrics in modern data visualization style, blue and green color scheme, clean minimalist design with icons representing market size, growth rate, and competitive landscape" \
  --output figures/executive_summary.png
```

### 按部分推荐的视觉效果（根据需要生成）

|部分|优先视觉效果|可选视觉效果|
|---------|-----------------|--------------------|
|执行摘要|执行信息图（开始）| - |
|市场规模与增长|成长轨迹（开始），TAM/SAM/SOM（开始）|区域细分、细分市场增长 |
|竞争格局|Porter的五力（START），定位矩阵（START）|市场份额图表，战略群体|
|风险分析|风险热图（开始）|缓解矩阵|
|战略建议|机会矩阵|优先框架|
|实施路线图|时间线/甘特图 |里程碑追踪器|
|投资论文|财务预测|情景分析|

**从 6 个优先视觉效果开始**（上面标记为“开始”），然后在编写特定部分并需要视觉支持时生成其他视觉效果。

---

## 报告结构（50+ 页）

### 前言（约 5 页）

#### 封面页（1 页）
- 报告标题和副标题
- 英雄可视化（生成）
- 日期和分类
- 由
准备/准备
#### 目录（1-2 页）
- 从LaTeX自动生成
- 图表列表
- 表格列表

#### 执行摘要（2-3 页）
- **市场快照框**：关键指标一览
- **投资论文**：3-5 个要点摘要
- **主要发现**：主要发现和见解
- **战略建议**：前 3-5 个可操作建议
- **执行摘要信息图**：报告要点的可视化综合

---

### 核心分析（~35 页）

#### 第 1 章：市场概述和定义（4-5 页）

**内容要求：**
- 市场定义和范围
- 行业生态系统映射
- 主要利益相关者及其角色
- 市场边界和邻接
- 历史背景和演变

**所需视觉效果 (2)：**
1. 市场生态系统/价值链图
2. 行业结构图

**关键数据点：**
- 市场定义标准
- 包含/排除的细分市场
- 地理范围
- 分析时间范围

---

#### 第 2 章：市场规模和增长分析（6-8 页）

**内容要求：**
- 总可寻址市场 (TAM) 计算
- 可服务可寻址市场 (SAM) 定义
- 可服务可获得市场 (SOM) 估计
- 历史增长分析（5-10 年）
- 增长预测（未来 5-10 年）
- 增长驱动因素和抑制剂
- 区域市场细分
- 细分市场分析

**所需视觉效果 (4):**
1. 市场增长轨迹图（历史 + 预测）
2. TAM/SAM/SOM同心圆图
3. 区域市场细分（饼图或树状图）
4. 细分市场增长比较（条形图）

**关键数据点：**
- 当前市场规模（含来源）
- CAGR（历史和预测）
- 按地区划分的市场规模
- 按细分市场划分的市场规模
- 预测的关键假设

**数据来源：**
使用`research-lookup`查找：
- 市场研究报告（Gartner、Forrester、IDC 等）
- 行业协会数据
- 政府统计数据
- 公司财务报告
- 学术研究

---

#### 第 3 章：行业驱动因素和趋势（5-6 页）

**内容要求：**
- 宏观经济因素
- 技术趋势
- 监管驱动因素
- 社会和人口变化
- 环境因素
- 行业特定趋势

**分析框架：**
- **PESTLE 分析**：政治、经济、社会、技术、法律、环境
- **趋势影响评估**：可能性与影响矩阵

**所需的视觉效果(3):**
1. 行业趋势时间表或雷达图
2. 驱动因素影响矩阵
3. PESTLE 分析图

**关键数据点：**
- 具有量化影响的前 5-10 个增长驱动因素
- 带有时间表的新兴趋势
- 干扰因素

---

#### 第 4 章：竞争格局（6-8 页）

**内容要求：**
- 市场结构分析
- 主要参与者概况
- 市场份额分析
- 竞争定位
- 进入壁垒
- 竞争动态

**分析框架：**
- **Porter的五力**：全面的行业分析
- **竞争定位矩阵**：关键维度上的 2x2 矩阵
- **战略集团映射**：按战略对竞争对手进行集群

**所需视觉效果 (4)：**
1. Porter的五力图
2. 市场份额饼图或条形图
3. 竞争定位矩阵 (2x2)
4. 战略集团地图

**关键数据点：**
- 按公司划分的市场份额（前 10 名）
- 竞争强度评级
- 进入壁垒评估
- 供应商/买方实力评估

---

#### 第 5 章：客户分析和细分（4-5 页）

**内容要求：**
- 客户细分定义
- 细分市场规模和增长
- 购买行为分析
- 客户需求和痛点
- 决策过程
- 按细分市场划分的价值驱动因素

**分析框架：**
- **客户细分矩阵**：规模与增长
- **价值主张画布**：工作、痛苦、收益
- **客户旅程图**：宣传意识

**所需的视觉效果 (3)：**
1. 客户细分细分（饼图/树形图）
2. 细分吸引力矩阵
3. 客户旅程或价值主张图

**关键数据点：**
- 细分市场规模和百分比
- 按细分市场划分的增长率
- 每个客户的平均交易规模/收入
- 按细分市场划分的客户获取成本

---

#### 第 6 章：技术与创新格局（4-5 页）

**内容要求：**
- 当前技术堆栈
- 新兴技术
- 创新趋势
- 技术采用曲线
- 研发投资分析
- 专利格局

**分析框架：**
- **技术就绪评估**：TRL 级别
- **技术成熟度曲线定位**：技术所在
- **技术路线图**：随时间的演变

**所需视觉效果 (2)：**
1. 技术路线图
2. 创新/采用曲线或炒作周期

**关键数据点：**
- 行业研发支出
- 关键技术里程碑
- 专利申请趋势
- 技术采用率

---

#### 第 7 章：监管和政策环境（3-4 页）

**内容要求：**
- 当前监管框架
- 主要监管机构
- 合规要求
- 即将发生的监管变化
- 政策趋势
- 影响评估

**所需视觉效果 (1)：**
1. 监管时间表或框架图

**关键数据点：**
- 关键法规和生效日期
- 合规成本
- 监管风险
- 政策变更概率

---

#### 第 8 章：风险分析（3-4 页）

**内容要求：**
- 市场风险
- 竞争风险
- 监管风险
- 技术风险
- 操作风险
- 财务风险
- 风险缓解策略

**分析框架：**
- **风险热图**：概率与影响
- **风险登记册**：综合风险清单
- **缓解矩阵**：风险与缓解策略

**所需视觉效果 (2)：**
1. 风险热图（概率与影响）
2. 风险缓解矩阵

**关键数据点：**
- 排名前 10 的风险
- 风险概率评分
- 影响严重性评分
- 缓解成本估算

---

### 战略建议（约 10 页）

#### 第 9 章：战略机会和建议（4-5 页）

**内容要求：**
- 机会识别
- 机会大小
- 战略选择分析
- 优先级框架
- 详细建议
- 成功因素

**分析框架：**
- **机会吸引力矩阵**：吸引力与获胜能力
- **战略选项框架**：构建、购买、合作、忽略
- **优先级矩阵**：影响与努力

**所需视觉效果 (3)：**
1. 机会矩阵
2. 战略选项框架
3. 优先级/推荐矩阵

**关键数据点：**
- 机会规模
- 投资要求
- 预期回报
- 价值时间表

---

#### 第 10 章：实施路线图（3-4 页）

**内容要求：**
- 分阶段实施计划
- 关键里程碑和可交付成果
- 资源要求
- 时间表和排序
- 依赖性和关键路径
- 治理结构

**所需的视觉效果 (2)：**
1. 实施时间表/甘特图
2. 里程碑跟踪器或阶段图

**关键数据点：**
- 阶段持续时间
- 资源要求
- 带日期的关键里程碑
- 按阶段分配预算

---

#### 第 11 章：投资论文和财务预测（3-4 页）

**内容要求：**
- 投资摘要
- 财务预测
- 情景分析
- 回报预期
- 关键假设
- 敏感性分析

**所需的视觉效果 (2)：**
1. 财务预测图（收入、增长）
2. 情景分析比较

**关键数据点：**
- 收入预测（3-5 年）
- CAGR预测
- ROI/IRR 预期
- 关键财务假设

---

### 返回事项（~5 页）

#### 附录 A：方法和数据源（1-2 页）
- 研究方法
- 数据收集方法
- 数据源和引文
- 局限性和假设

#### 附录 B：详细市场数据表（2-3 页）
- 综合市场数据表
- 区域细分
- 细分市场详细信息
- 历史数据系列

#### 附录 C：公司简介（1-2 页）
- 简要简介主要竞争对手
- 财务摘要
- 战略重点领域

#### 参考文献/书目
- 引用的所有来源
- LaTeXBibTeX格式

---

## 工作流程

### 第 1 阶段：研究和数据收集

**第 1 步：定义范围**
- 明确市场定义
- 设定地理边界
- 确定时间范围
- 确定要回答的关键问题

**第 2 步：深入开展研究**

广泛使用`research-lookup`收集市场数据：

```bash
# Market size and growth data
python skills/research-lookup/scripts/research_lookup.py \
  "What is the current market size and projected growth rate for [MARKET] industry? Include TAM, SAM, SOM estimates and CAGR projections"

# Competitive landscape
python skills/research-lookup/scripts/research_lookup.py \
  "Who are the top 10 competitors in the [MARKET] market? What is their market share and competitive positioning?"

# Industry trends
python skills/research-lookup/scripts/research_lookup.py \
  "What are the major trends and growth drivers in the [MARKET] industry for 2024-2030?"

# Regulatory environment
python skills/research-lookup/scripts/research_lookup.py \
  "What are the key regulations and policy changes affecting the [MARKET] industry?"
```

**步骤 3：数据组织**
- 创建包含研究笔记的`sources/`文件夹
- 按部分组织数据
- 识别数据差距
- 根据需要进行后续研究

### 第 2 阶段：分析和框架应用

**步骤 4：应用分析框架**

对于每个框架，进行结构化分析：

- **市场规模**：TAM→SAM→SOM具有明确的假设
- **Porter的五种力量**：对每种力量进行高/中/低评级，并给出理由
- **PESTLE**：分析每个维度的趋势和影响
- **SWOT**：内部优势/劣势、外部机会/威胁
- **竞争定位**：定义轴、绘制竞争对手

**步骤 5：开发见解**
- 将发现结果综合为关键见解
- 确定战略影响
- 制定建议
- 优先考虑机会

### 第 3 阶段：视觉生成

**第 6 步：生成所有视觉效果**

在编写报告之前生成视觉效果。使用批量生成脚本：

```bash
# Generate all standard market report visuals
python skills/market-research-reports/scripts/generate_market_visuals.py \
  --topic "[MARKET NAME]" \
  --output-dir figures/
```

或单独生成：

```bash
# 1. Market growth trajectory
python skills/scientific-schematics/scripts/generate_schematic.py \
  "Bar chart showing market growth from 2020 to 2034, with historical bars in dark blue (2020-2024) and projected bars in light blue (2025-2034). Y-axis shows market size in billions USD. Include CAGR annotation" \
  -o figures/01_market_growth.png --doc-type report

# 2. TAM/SAM/SOM breakdown
python skills/scientific-schematics/scripts/generate_schematic.py \
  "TAM SAM SOM concentric circles diagram. Outer circle TAM Total Addressable Market, middle circle SAM Serviceable Addressable Market, inner circle SOM Serviceable Obtainable Market. Each labeled with acronym and description. Blue gradient" \
  -o figures/02_tam_sam_som.png --doc-type report

# 3. Porter's Five Forces
python skills/scientific-schematics/scripts/generate_schematic.py \
  "Porter's Five Forces diagram with center box 'Competitive Rivalry' connected to four surrounding boxes: Threat of New Entrants (top), Bargaining Power of Suppliers (left), Bargaining Power of Buyers (right), Threat of Substitutes (bottom). Color code by rating: High=red, Medium=yellow, Low=green" \
  -o figures/03_porters_five_forces.png --doc-type report

# 4. Competitive positioning matrix
python skills/scientific-schematics/scripts/generate_schematic.py \
  "2x2 competitive positioning matrix with X-axis 'Market Focus (Niche to Broad)' and Y-axis 'Solution Approach (Product to Platform)'. Plot 8-10 competitors as labeled circles of varying sizes. Include quadrant labels" \
  -o figures/04_competitive_positioning.png --doc-type report

# 5. Risk heatmap
python skills/scientific-schematics/scripts/generate_schematic.py \
  "Risk heatmap matrix. X-axis Impact (Low to Critical), Y-axis Probability (Unlikely to Very Likely). Color gradient: Green (low risk) to Red (critical risk). Plot 10-12 risks as labeled points" \
  -o figures/05_risk_heatmap.png --doc-type report

# 6. (Optional) Executive summary infographic
python skills/generate-image/scripts/generate_image.py \
  "Professional executive summary infographic for market research report, modern data visualization style, blue and green color scheme, clean minimalist design" \
  --output figures/06_exec_summary.png
```

### 第 4 阶段：报告编写

**第 7 步：初始化项目结构**

创建标准项目结构：

```
writing_outputs/YYYYMMDD_HHMMSS_market_report_[topic]/
├── progress.md
├── drafts/
│   └── v1_market_report.tex
├── references/
│   └── references.bib
├── figures/
│   └── [all generated visuals]
├── sources/
│   └── [research notes]
└── final/
```

**步骤 8：使用模板编写报告**

使用`market_report_template.tex`作为起点。按照结构指南编写每个部分，确保：

- **全面覆盖**：每个小节都涉及
- **数据驱动的内容**：研究支持的声明
- **视觉集成**：引用所有生成的图形
- **专业语气**：咨询式写作
- **无令牌限制**：完整书写，不要缩写

**写作指南：**
- 尽可能使用主动语态
- 以见解引导，以数据支持
- 使用编号列表提出建议
- 包括所有统计数据的数据源
- 在各部分之间创建平滑过渡

### 第 5 阶段：编译和审查

**第 9 步：编译LaTeX**

```bash
cd writing_outputs/[project_folder]/drafts/
xelatex v1_market_report.tex
bibtex v1_market_report
xelatex v1_market_report.tex
xelatex v1_market_report.tex
```

**第 10 步：质量审核**

验证报告是否符合质量标准：

- [ ] 总页数为 50 多页
- [ ] 包含所有基本视觉效果（5-6 核心 + 任何附加内容）并正确呈现
- [ ] 执行摘要捕获主要发现
- [ ] 所有数据点均引用了来源
- [ ] 正确应用了分析框架
- [ ] 建议具有可操作性并具有优先顺序
- [ ] 没有孤立的图形或表格
- [ ] 目录、图形列表、表格列表准确
- [ ] 参考书目完整
- [ ]PDF渲染无错误

**步骤 11：同行评审**

使用同行评审技能评估报告：
- 评估全面性
- 验证数据准确性
- 检查逻辑流程
- 评估推荐质量

---

## 质量标准

### 页数目标

|部分|最小页数 |目标页面 |
|---------|----------------|----------------|
|前线事项 | 4 | 5 |
|市场概况 | 4 | 5 |
|市场规模与增长| 5 | 7 |
|行业驱动力| 4 | 6 |
|竞争格局| 5 | 7 |
|客户分析| 3 | 5 |
|技术景观| 3 | 5 |
|监管环境| 2 | 4 |
|风险分析| 2 | 4 |
|战略建议| 3 | 5 |
|实施路线图| 2 | 4 |
|投资论文| 2 | 4 |
|返回事项 | 4 | 5 |
| **总计** | **43** | **66** |

### 视觉质量要求

- **分辨率**：所有图像最低分辨率为 300DPI
- **格式**：PNG 用于光栅，PDF用于矢量
- **辅助功能**：色盲友好调色板
- **一致性**：整个颜色方案相同
- **标签**：所有轴、图例和数据点都标记为
- **来源归属**：图形标题中引用的来源

### 数据质量要求

- **货币**：不超过 2 年的数据（首选当前年份）
- **来源**：全部归因于特定来源的统计数据
- **验证**：尽可能交叉引用多个来源
- **假设**：所有预测均陈述基本假设
- **限制**：承认数据限制和差距

### 编写质量要求

- **客观性**：呈现平衡分析，承认不确定性
- **清晰度**：避免行话，定义技术术语
- **精确**：使用具体数字而不是模糊限定符
- **结构**：清晰的标题、逻辑流程、平滑过渡
- **可操作性**：建议具体且可实施

---

## LaTeX格式化

### 使用样式包

`market_research.sty`包提供专业格式化。将其包含在您的文档中：

```latex
\documentclass[11pt,letterpaper]{report}
\usepackage{market_research}
```

### 框环境

使用彩色框突出显示关键内容：

```latex
% Key insight box (blue)
\begin{keyinsightbox}[Key Finding]
The market is projected to grow at 15.3% CAGR through 2030.
\end{keyinsightbox}

% Market data box (green)
\begin{marketdatabox}[Market Snapshot]
\begin{itemize}
    \item Market Size (2024): \$45.2B
    \item Projected Size (2030): \$98.7B
    \item CAGR: 15.3%
\end{itemize}
\end{marketdatabox}

% Risk box (orange/warning)
\begin{riskbox}[Critical Risk]
Regulatory changes could impact 40% of market participants.
\end{riskbox}

% Recommendation box (purple)
\begin{recommendationbox}[Strategic Recommendation]
Prioritize market entry in the Asia-Pacific region.
\end{recommendationbox}

% Callout box (gray)
\begin{calloutbox}[Definition]
TAM (Total Addressable Market) represents the total revenue opportunity.
\end{calloutbox}
```

### 图形格式

```latex
\begin{figure}[htbp]
\centering
\includegraphics[width=0.9\textwidth]{../figures/market_growth.png}
\caption{Market Growth Trajectory (2020-2030). Source: Industry analysis, company data.}
\label{fig:market_growth}
\end{figure}
```

### 表格式

```latex
\begin{table}[htbp]
\centering
\caption{Market Size by Region (2024)}
\begin{tabular}{@{}lrrr@{}}
\toprule
\textbf{Region} & \textbf{Size (USD)} & \textbf{Share} & \textbf{CAGR} \\
\midrule
North America & \$18.2B & 40.3\% & 12.5\% \\
\rowcolor{tablealt} Europe & \$12.1B & 26.8\% & 14.2\% \\
Asia-Pacific & \$10.5B & 23.2\% & 18.7\% \\
\rowcolor{tablealt} Rest of World & \$4.4B & 9.7\% & 11.3\% \\
\midrule
\textbf{Total} & \textbf{\$45.2B} & \textbf{100\%} & \textbf{15.3\%} \\
\bottomrule
\end{tabular}
\label{tab:market_by_region}
\end{table}
```

有关完整格式参考，请参阅`assets/FORMATTING_GUIDE.md`。

---

## 与其他技能集成

该技能与以下技能协同工作：

- **研究查找**：对于收集市场数据、统计数据和竞争情报至关重要
- **科学原理图**：生成所有图表、图表和可视化
- **生成图像**：创建信息图表和概念插图
- **同行评审**：评估报告质量和完整性
- **引文管理**：管理BibTeX引用

---

## 示例提示

### 市场概览部分

```
Write a comprehensive market overview section for the [Electric Vehicle Charging Infrastructure] market. Include:
- Clear market definition and scope
- Industry ecosystem with key stakeholders
- Value chain analysis
- Historical evolution of the market
- Current market dynamics

Generate 2 supporting visuals using scientific-schematics.
```

### 竞争格局部分

```
Analyze the competitive landscape for the [Cloud Computing] market. Include:
- Porter's Five Forces analysis with High/Medium/Low ratings
- Top 10 competitors with market share
- Competitive positioning matrix
- Strategic group mapping
- Barriers to entry analysis

Generate 4 supporting visuals including Porter's Five Forces diagram and positioning matrix.
```

### 战略建议部分

```
Develop strategic recommendations for entering the [Renewable Energy Storage] market. Include:
- 5-7 prioritized recommendations
- Opportunity sizing for each
- Implementation considerations
- Risk factors and mitigations
- Success criteria

Generate 3 supporting visuals including opportunity matrix and priority framework.
```

---

## 检查清单：50+ 页面验证

在完成报告之前，请验证：

### 结构完整性
- [ ] 带有英雄视觉效果的封面页
- [ ] 目录（自动生成）
- [ ] 图列表（自动生成）
- [ ] 表格列表（自动生成）
- [ ] 执行摘要（2-3 页）
- [ ] 共有 11 个核心章节
- [ ] 附录 A：方法
- [ ] 附录 B：数据表
- [ ] 附录 C：公司简介
- [ ] 参考文献/参考书目

### 视觉完整性（核心 5-6）
- [ ] 市场增长轨迹图（优先级 1）
- [ ]TAM/SAM/SOM图（优先级 2）
- [ ]Porter的五种力量（优先级 3）
- [ ] 竞争定位矩阵（优先级 4）
- [ ] 风险热图（优先级 5）
- [ ] 执行摘要信息图（优先级 6，可选）

### 其他视觉效果（根据需要生成）
- [ ] 市场生态系统图
- [ ] 区域细分图
- [ ] 细分市场增长图
- [ ] 行业趋势/PESTLE 图
- [ ] 市场份额图
- [ ] 客户细分图
- [ ] 技术路线图
- [ ] 监管时间表
- [ ] 机会矩阵
- [ ] 实施时间表
- [ ] 财务预测图表
- [ ] 其他特定部分的视觉效果

### 内容质量
- [ ] 所有统计数据都有来源
- [ ] 预测包括假设
- [ ] 正确应用框架
- [ ] 建议可行
- [ ] 写作具有专业品质
- [ ] 无占位符或不完整部分

### 技术质量
- [ ]PDF编译无错误
- [ ] 所有数字正确渲染
- [ ] 交叉引用工作
- [ ] 参考书目完成
- [ ] 页数超过 50

---

## 资源

### 参考文件

加载这些有关详细指导的文件：

- **`references/report_structure_guide.md`**：详细的逐节内容要求
- **`references/visual_generation_guide.md`**：生成所有视觉类型的完整提示
- **`references/data_analysis_patterns.md`**：Porter、PESTLE、SWOT等的模板

### 资源

- **`assets/market_research.sty`**：LaTeX样式包
- **`assets/market_report_template.tex`**：完整的LaTeX模板
- **`assets/FORMATTING_GUIDE.md`**：盒子环境和样式的快速参考

### 脚本

- **`scripts/generate_market_visuals.py`**：批量生成所有报告视觉效果

---

## 故障排除

### 常见问题

**问题**：报告不足 50 页
- **解决方案**：扩展附录中的数据表，添加更详细的公司简介，包括其他区域细分

**问题**：视觉效果未渲染
- **解决方案**：检查LaTeX中的文件路径，确保图像位于图形/文件夹中，验证文件扩展名

**问题**：参考书目缺少条目
- **解决方案**：在第一次 xelatex 传递后运行 bibtex，检查 .bib 文件是否有语法错误

**问题**：表格/图形溢出
- **解决方案**：使用`\resizebox`或`adjustbox`封装，减少图像宽度百分比

**问题**：一代视觉质量较差
- **解决方案**：使用`--doc-type report`标志，使用`--iterations 5`增加迭代

---

使用此技能创建全面、视觉丰富的市场研究报告，可与顶级咨询公司的交付成果相媲美。深入研究、结构化框架和广泛可视化的结合产生了为战略决策提供信息并展示分析严谨性的文档。

