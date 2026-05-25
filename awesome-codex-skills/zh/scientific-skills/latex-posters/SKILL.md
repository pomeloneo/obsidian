---
name: latex-posters
description: "使用beamerposter、tikzposter或baposter在LaTeX中创建专业研究海报。支持会议演示、学术海报和科学传播。包括布局设计、配色方案、多栏格式、图形集成以及针对视觉传达的海报特定最佳实践。"
allowed-tools: Read Write Edit Bash
---

# LaTeX研究海报

## 概述

研究海报是会议、研讨会和学术活动中科学交流的重要媒介。该技能为使用LaTeX包创建专业的、具有视觉吸引力的研究海报提供了全面的指导。生成具有适当布局、排版、配色方案和视觉层次结构的出版质量海报。

## 何时使用此技能

在以下情况下应使用此技能：
- 为会议、研讨会或海报会议制作研究海报
- 为大学活动或论文答辩设计学术海报
- 为公众参与准备研究的视觉摘要
- 转换将科学论文转化为海报格式
- 为研究小组或部门创建海报模板
- 设计符合特定会议尺寸要求（A0、A1、36×48" 等）的海报
- 构建具有复杂多栏布局的海报
- 以海报格式集成图形、表格、方程和引文

## AI 驱动的视觉元素生成

**标准工作流程：在创建LaTeX海报之前使用 AI 生成所有主要视觉元素。**

这是创建视觉上引人注目的海报的推荐方法：
1. 规划所需的所有视觉元素（标题、简介、方法、结果、结论）
2. 使用科学原理图或Nano Banana Pro
生成每个元素 3. 在LaTeX模板
中组装生成的图像 4. 在视觉效果

周围添加文本内容 **目标：海报区域的 60-70% 应为 AI 生成的视觉效果，30-40% 为文本。**

---

### 关键：防止内容溢出

**⚠️ 海报不得有文本或内容在边缘被切断。**

**常见溢出问题：**
1. **标题/页脚文本超出范围页面边界**
2. **过多的部分塞入可用空间**
3. **图形放置得太靠近边缘**
4. **文本块超过列宽**

**预防规则：**

**1. 限制内容部分（A0 最多 5-6 个部分）：**
```
✅ GOOD - 5 sections with room to breathe:
   - Title/Header
   - Introduction/Problem
   - Methods
   - Results (1-2 key findings)
   - Conclusions

❌ BAD - 8+ sections crammed together:
   - Overview, Introduction, Background, Methods, 
   - Results 1, Results 2, Discussion, Conclusions, Future Work
```

**2。在LaTeX中设置安全边距：**
```latex
% tikzposter - add generous margins
\documentclass[25pt, a0paper, portrait, margin=25mm]{tikzposter}

% baposter - ensure content doesn't touch edges
\begin{poster}{
  columns=3,
  colspacing=2em,           % Space between columns
  headerheight=0.1\textheight,  % Smaller header
  % Leave space at bottom
}
```

**3。身材尺寸 - 绝不是 100% 宽度：**
```latex
% Leave margins around figures
\includegraphics[width=0.85\linewidth]{figure.png}  % NOT 1.0\linewidth
```

**4。打印前检查是否溢出：**
```bash
# Compile and check PDF at 100% zoom
pdflatex poster.tex

# Look for:
# - Text cut off at any edge
# - Content touching page boundaries  
# - Overfull hbox warnings in .log file
grep -i "overfull" poster.log
```

**5。字数限制：**
- **A0 海报**：最多 300-800 个字
- **每节**：最多 50-100 个字
- **如果您有更多内容**：剪切或制作讲义

---

### 关键：海报大小字体要求

**⚠️ AI 生成的可视化中的所有文本必须是海报可读的。**

生成海报图形时，您必须在每个提示中包含字体大小规范。海报图形是从 4-6 英尺外观看的，因此文本必须很大。

**⚠️ 常见问题：内容溢出和密度**

AI 生成的海报图形的第一个问题是 **内容太多**。这会导致：
- 文本溢出超出边界
- 不可读的小字体
- 杂乱、压倒性的视觉效果
- 空白使用不佳

**解决方案：用最少的内容生成简单的图形。**

**每个海报图形的强制提示要求：**

```
POSTER FORMAT REQUIREMENTS (STRICTLY ENFORCE):
- ABSOLUTE MAXIMUM 3-4 elements per graphic (3 is ideal)
- ABSOLUTE MAXIMUM 10 words total in the entire graphic
- NO complex workflows with 5+ steps (split into 2-3 simple graphics instead)
- NO multi-level nested diagrams (flatten to single level)
- NO case studies with multiple sub-sections (one key point per case)
- ALL text GIANT BOLD (80pt+ for labels, 120pt+ for key numbers)
- High contrast ONLY (dark on white OR white on dark, NO gradients with text)
- MANDATORY 50% white space minimum (half the graphic should be empty)
- Thick lines only (5px+ minimum), large icons (200px+ minimum)
- ONE SINGLE MESSAGE per graphic (not 3 related messages)
```

**⚠️ 生成之前：检查您的提示并计算元素**
- 如果您的描述有 5 个以上项目 → 停止。拆分为多个图形
- 如果您的工作流程有 5 个以上阶段 → 停止。仅显示 3-4 个高级步骤
- 如果您的比较有 4 个以上方法 → 停止。仅显示前 3 个或我们与最佳基线

**每种图形类型的内容限制（严格）：**
|图形类型|最大元素 |最大字数 |拒绝如果 |好例子 |
|--------------|----------------|------------|------------|--------------|
|流程图| **最多 3-4 盒** | **8 个字** | 5+ 个阶段，嵌套步骤 | “发现→验证→批准”（3个字）|
|主要发现| **最多 3 件物品** | **9 个字** | 4+ 指标、段落 | “95% 准确”“2 倍更快”“FDA就绪”（6 个字）|
|比较图| **最多 3 条** | **6 个字** | 4+ 方法、图例文本 | “我们的：95%”“最好的：85%”（4 个字）|
|案例研究| **1 个案例，3 个元件** | **6 个字** |多个案件、子故事 |标志+“18个月”+“发现”（2个字）|
|时间轴 | **最多 3-4 分** | **8 个字** |逐年详细信息 | “2020 年开始”“2022 年试用”“2024 年批准”（6 个字）|

**示例 - 错误（7 阶段工作流程 - 太复杂）：**
```bash
# ❌ BAD - This creates tiny unreadable text like the drug discovery poster
python scripts/generate_schematic.py "Drug discovery workflow showing: Stage 1 Target Identification, Stage 2 Molecular Synthesis, Stage 3 Virtual Screening, Stage 4 AI Lead Optimization, Stage 5 Clinical Trial Design, Stage 6 FDA Approval. Include success metrics, timelines, and validation steps for each stage." -o figures/workflow.png
# Result: 7+ stages with tiny text, unreadable from 6 feet - POSTER FAILURE
```

**示例 - 正确（简化为 3 个关键阶段）：**
```bash
# ✅ GOOD - Same content, split into ONE simple high-level graphic
python scripts/generate_schematic.py "POSTER FORMAT for A0. ULTRA-SIMPLE 3-box workflow: 'DISCOVER' → 'VALIDATE' → 'APPROVE'. Each word in GIANT bold (120pt+). Thick arrows (10px). 60% white space. NO substeps, NO details. 3 words total. Readable from 10 feet." -o figures/workflow_overview.png
# Result: Clean, impactful, readable - can add detail graphics separately if needed
```

**示例 - 错误（具有多个部分的复杂案例研究）：**
```bash
# ❌ BAD - Creates cramped unreadable sections
python scripts/generate_schematic.py "Case studies: Insilico Medicine (drug candidate, discovery time, clinical trials), Recursion Pharma (platform, methodology, results), Exscientia (drug candidates, FDA status, timeline). Include company logos, metrics, and outcomes." -o figures/cases.png
# Result: 3 case studies with 4+ elements each = 12+ total elements, tiny text
```

**示例 - 正确（一个案例研究，一个关键指标）：**
```bash
# ✅ GOOD - Show ONE case with ONE key number
python scripts/generate_schematic.py "POSTER FORMAT for A0. ONE case study card: Company logo (large), '18 MONTHS' in GIANT text (150pt), 'to discovery' below (60pt). 3 elements total: logo + number + caption. 50% white space. Readable from 10 feet." -o figures/case_single.png
# Result: Clear, readable, impactful. Make 3 separate graphics if you need 3 cases.
```

**示例 - 错误（主要发现过于复杂）：**
```bash
# BAD - too many items, too much detail
python scripts/generate_schematic.py "Key findings showing 8 metrics: accuracy 95%, precision 92%, recall 94%, F1 0.93, AUC 0.97, training time 2.3 hours, inference 50ms, model size 145MB with comparison to 5 baseline methods" -o figures/findings.png
# Result: Cramped graphic with tiny numbers
```

**示例 - 正确（主要发现简单）：**
```bash
# GOOD - only 3 key items, giant numbers
python scripts/generate_schematic.py "POSTER FORMAT for A0. KEY FINDINGS with ONLY 3 large cards. Card 1: '95%' in GIANT text (120pt) with 'ACCURACY' below (48pt). Card 2: '2X' in GIANT text with 'FASTER' below. Card 3: checkmark icon with 'VALIDATED' in large text. 50% white space. High contrast colors. NO other text or details." -o figures/findings.png
# Result: Bold, readable impact statement
```

**海报提示字体大小参考：**
|元素|最小尺寸 |提示关键词|
|---------|--------------|-----------------|
|主要数字/指标 | 72pt+ | “巨大”、“非常大”、“巨大”、“海报大小”|
|章节标题 | 60pt+ | “大粗体”、“突出”|
|标签/标题 | 36点+ | “6 英尺处可读”、“清晰标签”|
|正文 | 24点+ | “海报可读”、“大文本”|

**始终包含在提示中：**
- “海报格式”或“A0 海报”或“从 6 英尺处可读”
- “非常大的文本”或“巨大的粗体字体”
- 应出现的特定文本（因此它会融入图像中）
- “最少的文本，最大的影响”
- “高对比度”以提高可读性
- “宽裕的边距”和“边缘附近没有文本”

---

### 关键：AI 生成的图形尺寸

**⚠️ 每个 AI 生成的图形应专注于具有最少内容的一个概念。**

**问题**：生成包含许多元素的复杂图表会导致文本较小。

**解决方案**：生成具有少量元素和大文本的简单图形。

**示例 - 错误（太复杂，文本会很小）：**
```bash
# BAD - too many elements in one graphic
python scripts/generate_schematic.py "Complete ML pipeline showing data collection, 
preprocessing with 5 steps, feature engineering with 8 techniques, model training 
with hyperparameter tuning, validation with cross-validation, and deployment with 
monitoring. Include all labels and descriptions." -o figures/pipeline.png
```

**示例 - 正确（简单、重点突出、大文本）：**
```bash
# GOOD - split into multiple simple graphics with large text

# Graphic 1: High-level overview (3-4 elements max)
python scripts/generate_schematic.py "POSTER FORMAT for A0: Simple 4-step pipeline. 
Four large boxes: DATA → PROCESS → MODEL → RESULTS. 
GIANT labels (80pt+), thick arrows, lots of white space. 
Only 4 words total. Readable from 8 feet." -o figures/overview.png

# Graphic 2: Key result (1 metric highlighted)
python scripts/generate_schematic.py "POSTER FORMAT for A0: Single key metric display.
Giant '95%' text (150pt+) with 'ACCURACY' below (60pt+).
Checkmark icon. Minimal design, high contrast.
Readable from 10 feet." -o figures/accuracy.png
```

**人工智能生成海报图形的规则：**
|规则|限制|原因 |
|------|--------|--------|
| **每个图形的元素** |最多 3-5 |更多元素 = 更小的文本 |
| **每个图形的字数** |最多 10-15 |最小文本 = 较大字体 |
| **流程图步骤** |最多 4-5 |保持标签可读 |
| **图表类别** |最多 3-4 |防止拥挤 |
| **嵌套级别** |最多 1-2 |避免复杂性 |

**将复杂内容分割成多个简单图形：**
```
Instead of 1 complex diagram with 12 elements:
→ Create 3 simple diagrams with 4 elements each
→ Each graphic can have LARGER text
→ Arrange in poster with clear visual flow
```

---

### 步骤 0：强制生成前审查（首先执行此操作）

**⚠️ 在生成任何图形之前，检查您的内容计划：**

**对于每个计划的图形，询问以下问题：**
1. **元素数量**：我可以用 3-4 个或更少的项目来描述吗？
- ❌ 否 → 简化或拆分为多个图形
- ✅ 是 → 继续

2. **复杂性检查**：这是多阶段工作流程（5 个以上步骤）还是嵌套图？
- ❌ 是 → 仅扁平化至 3-4 个高级步骤
- ✅ 否 → 继续

3. **字数统计**：我可以用 10 个字或更少的字数描述所有文本吗？
- ❌ 否 → 剪切文本，使用单字标签
- ✅ 是 → 继续

4. **消息清晰度**：该图形是否传达了一个明确的消息？
- ❌否 → 拆分为多个重点图形
- ✅ 是 → 继续生成

**总是失败的常见模式（拒绝这些）：**
- “显示阶段 1 到 7...” → 拆分为高级概述（3 个阶段）+ 详细图形
- “多个案例研究...” → 一个案例每个图形
- “从 2015 年到 2024 年的时间表，包含年度里程碑...”→ 仅显示 3-4 个关键年份
- “6 种方法的比较...”→ 仅显示前 3 种或我们的方法与最佳基线
- “具有所有层和连接的架构...”→ 仅高级（3-4 个组件）

### 步骤1：规划海报元素

通过预生成审核后，确定所需的视觉元素：

1. **标题块** - 带有机构品牌的风格化标题（可选 - 可以是LaTeX文本）
2. **介绍图** - 概念概述（最多 3 个元素）
3. **方法图** - 高级工作流程（最多 3-4 个步骤）
4. **结果图** - 主要发现（每个图最多 3 个指标，可能需要 2-3 个单独的图）
5. **结论图** - 视觉摘要（最多 3 个要点）
6. **补充图标** - 简单图标、QR 代码、徽标（最小）

### 步骤 2：生成每个元素（生成前审核后）

**⚠️ 关键：在继续之前查看步骤 0 检查表。**

对每种元素类型使用适当的工具：

**对于原理图和图表（科学原理图）：**
```bash
# Create figures directory
mkdir -p figures

# Drug discovery workflow - HIGH-LEVEL ONLY, 3 stages
# BAD: "Stage 1: Target ID, Stage 2: Molecular Synthesis, Stage 3: Virtual Screening, Stage 4: AI Lead Opt..."
# GOOD: Collapse to 3 mega-stages
python scripts/generate_schematic.py "POSTER FORMAT for A0. ULTRA-SIMPLE 3-box workflow: 'DISCOVER' (120pt bold) → 'VALIDATE' (120pt bold) → 'APPROVE' (120pt bold). Thick arrows (10px). 60% white space. ONLY these 3 words. NO substeps. Readable from 12 feet." -o figures/workflow_simple.png

# System architecture - MAXIMUM 3 components
python scripts/generate_schematic.py "POSTER FORMAT for A0. ULTRA-SIMPLE 3-component stack: 'DATA' box (120pt) → 'AI MODEL' box (120pt) → 'PREDICTION' box (120pt). Thick vertical arrows. 60% white space. 3 words only. Readable from 12 feet." -o figures/architecture.png

# Timeline - ONLY 3 key milestones (not year-by-year)
# BAD: "2018, 2019, 2020, 2021, 2022, 2023, 2024 with events"
# GOOD: Only 3 breakthrough moments
python scripts/generate_schematic.py "POSTER FORMAT for A0. Timeline with ONLY 3 points: '2018' + icon, '2021' + icon, '2024' + icon. GIANT years (120pt). Large icons. 60% white space. NO connecting lines or details. Readable from 12 feet." -o figures/timeline.png

# Case study - ONE case, ONE key metric
# BAD: "3 case studies: Insilico (details), Recursion (details), Exscientia (details)"
# GOOD: ONE case with ONE number
python scripts/generate_schematic.py "POSTER FORMAT for A0. ONE case study: Large logo + '18 MONTHS' (150pt bold) + 'to discovery' (60pt). 3 elements total. 60% white space. Readable from 12 feet." -o figures/case1.png

# If you need 3 cases → make 3 separate simple graphics (not one complex graphic)
```

**对于风格化块和图形 (Nano Banana Pro)：**
```bash
# Title block - SIMPLE
python scripts/generate_schematic.py "POSTER FORMAT for A0. Title block: 'ML FOR DRUG DISCOVERY' in HUGE bold text (120pt+). Dark blue background. ONE subtle icon. NO other text. 40% white space. Readable from 15 feet." -o figures/title_block.png

# Introduction visual - SIMPLE, 3 elements only
python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE problem visual with ONLY 3 icons: drug icon, arrow, target icon. ONE label per icon (80pt+). 50% white space. NO detailed text. Readable from 8 feet." -o figures/intro_visual.png

# Conclusion/summary - ONLY 3 items, GIANT numbers
python scripts/generate_schematic.py "POSTER FORMAT for A0. KEY FINDINGS with EXACTLY 3 cards only. Card 1: '95%' (150pt font) with 'ACCURACY' (60pt). Card 2: '2X' (150pt) with 'FASTER' (60pt). Card 3: checkmark icon with 'READY' (60pt). 50% white space. NO other text. Readable from 10 feet." -o figures/conclusions_graphic.png

# Background visual - SIMPLE, 3 icons only
python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE visual with ONLY 3 large icons in a row: problem icon → challenge icon → impact icon. ONE word label each (80pt+). 50% white space. NO detailed text. Readable from 8 feet." -o figures/background_visual.png
```

**对于数据可视化 - 简单，最多 3 个条：**
```bash
# SIMPLE chart with ONLY 3 bars, GIANT labels
python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE bar chart with ONLY 3 bars: BASELINE (70%), EXISTING (85%), OURS (95%). GIANT percentage labels ON the bars (100pt+). NO axis labels, NO legend, NO gridlines. Our bar highlighted in different color. 40% white space. Readable from 8 feet." -o figures/comparison_chart.png
```

### 步骤 2b：强制生成后审核（组装前）

**⚠️ 关键：在添加到海报之前审核每个生成的图形。**

**对于每个生成的图形，以 25% 缩放打开并检查：**

1. **✅ 通过标准（全部必须为真）：**
- 可以在 25% 缩放下清晰阅读所有文本
- 元素计数：3-4 个或更少
- 空白：50% 以上的图像为空
- 足够简单，2 秒内即可理解
- 不是具有 5 个以上阶段的复杂工作流程
- 不是多个嵌套部分

2. **❌ 失败标准（如果任何为真则重新生成）：**
- 文本很小或在 25% 缩放时难以阅读 → 使用“150pt+”字体重新生成
- 超过 4 个元素 → 使用“仅 3 个元素”重新生成
- 空白少于 50% →使用“60% 空白”重新生成
- 复杂的多阶段工作流程 → 拆分为 2-3 个简单图形
- 多个案例研究挤在一起 → 拆分为单独的图形
- 需要 3 秒以上才能理解 → 简化并重新生成

**常见故障和修复：**
- “7 阶段工作流程带有微小文本” → 重新生成为“仅 3 个高级阶段”
- “一个图形中的 3 个案例研究” → 生成 3 个独立的简单图形
- “8 年时间线” → 重新生成为“仅 3 个关键里程碑”
- “5 种方法的比较” → 重新生成为“仅我们的方法与最佳基线（2 个条）”

**如果任何图形未通过上述检查，请勿继续组装。**

### 步骤 3：在LaTeX模板中组装

所有图形通过生成后审核后，将它们包含在您的海报模板中：

**tikzposter示例：**
```latex
\documentclass[25pt, a0paper, portrait]{tikzposter}

\begin{document}

\maketitle

\begin{columns}
\column{0.5}

\block{Introduction}{
  \centering
  \includegraphics[width=0.85\linewidth]{figures/intro_visual.png}
  
  \vspace{0.5em}
  Brief context text here (2-3 sentences max).
}

\block{Methods}{
  \centering
  \includegraphics[width=0.9\linewidth]{figures/methods_flowchart.png}
}

\column{0.5}

\block{Results}{
  \begin{minipage}{0.48\linewidth}
    \centering
    \includegraphics[width=\linewidth]{figures/result_1.png}
  \end{minipage}
  \hfill
  \begin{minipage}{0.48\linewidth}
    \centering
    \includegraphics[width=\linewidth]{figures/result_2.png}
  \end{minipage}
  
  \vspace{0.5em}
  Key findings in 3-4 bullet points.
}

\block{Conclusions}{
  \centering
  \includegraphics[width=0.8\linewidth]{figures/conclusions_graphic.png}
}

\end{columns}

\end{document}
```

**baposter示例：**
```latex
\headerbox{Methods}{name=methods,column=0,row=0}{
  \centering
  \includegraphics[width=0.95\linewidth]{figures/methods_flowchart.png}
}

\headerbox{Results}{name=results,column=1,row=0}{
  \includegraphics[width=\linewidth]{figures/comparison_chart.png}
  \vspace{0.3em}
  
  Key finding: Our method achieves 92% accuracy.
}
```

### 示例：完整的海报生成工作流程

**包含所有质量检查的完整工作流程：**

```bash
# STEP 0: Pre-Generation Review (MANDATORY)
# Content plan: Drug discovery poster
# - Workflow: 7 stages → ❌ TOO MANY → Reduce to 3 mega-stages ✅
# - 3 case studies → ❌ TOO MANY → One case per graphic (make 3 graphics) ✅
# - Timeline 2018-2024 → ❌ TOO DETAILED → Only 3 key years ✅

# STEP 1: Create figures directory
mkdir -p figures

# STEP 2: Generate ULTRA-SIMPLE graphics with strict limits

# Workflow - HIGH-LEVEL ONLY (collapsed from 7 stages to 3)
python scripts/generate_schematic.py "POSTER FORMAT for A0. ULTRA-SIMPLE 3-box workflow: 'DISCOVER' → 'VALIDATE' → 'APPROVE'. Each word 120pt+ bold. Thick arrows (10px). 60% white space. ONLY 3 words total. Readable from 12 feet." -o figures/workflow.png

# Case study 1 - ONE case, ONE metric (will make 3 separate graphics)
python scripts/generate_schematic.py "POSTER FORMAT for A0. ONE case: Company logo + '18 MONTHS' (150pt bold) + 'to drug discovery' (60pt). 3 elements only. 60% white space. Readable from 12 feet." -o figures/case1.png

python scripts/generate_schematic.py "POSTER FORMAT for A0. ONE case: Company logo + '95% SUCCESS' (150pt bold) + 'in trials' (60pt). 3 elements only. 60% white space." -o figures/case2.png

python scripts/generate_schematic.py "POSTER FORMAT for A0. ONE case: Company logo + 'FDA APPROVED' (150pt bold) + '2024' (60pt). 3 elements only. 60% white space." -o figures/case3.png

# Timeline - ONLY 3 key years (not 7 years)
python scripts/generate_schematic.py "POSTER FORMAT for A0. ONLY 3 years: '2018' (150pt) + icon, '2021' (150pt) + icon, '2024' (150pt) + icon. Large icons. 60% white space. NO lines or details. Readable from 12 feet." -o figures/timeline.png

# Results - ONLY 2 bars (our method vs best baseline, not 5 methods)
python scripts/generate_schematic.py "POSTER FORMAT for A0. TWO bars only: 'BASELINE 70%' and 'OURS 95%' (highlighted). GIANT percentages (150pt) ON bars. NO axis, NO legend. 60% white space. Readable from 12 feet." -o figures/results.png

# STEP 2b: Post-Generation Review (MANDATORY)
# Open each figure at 25% zoom:
# ✅ workflow.png: 3 elements, text readable, 60% white - PASS
# ✅ case1.png: 3 elements, giant numbers, clean - PASS
# ✅ case2.png: 3 elements, giant numbers, clean - PASS  
# ✅ case3.png: 3 elements, giant numbers, clean - PASS
# ✅ timeline.png: 3 elements, readable, simple - PASS
# ✅ results.png: 2 bars, giant percentages, clear - PASS
# ALL PASS → Proceed to assembly

# STEP 3: Compile LaTeX poster
pdflatex poster.tex

# STEP 4: PDF Overflow Check (see Section 11)
grep "Overfull" poster.log
# Open at 100% and check all 4 edges
```

**如果任何图形失败第 2b 步审核：**
- 元素过多 → 使用“仅 3 个元素”重新生成
- 小文本 → 使用“150pt+”或“GIANT BOLD (150pt+)”重新生成
- 混乱 → 使用“60% 空白”和“超简单”重新生成
- 复杂的工作流程 → 分割成多个简单的 3 元素图形

### 视觉元素指南

**⚠️ 关键：每个图形必须有一条消息和最多 3-4 个元素。**

**绝对限制 - 这些不是指南，这些都是硬性的限制：**
- **每个图形最多 3-4 个元素**（3 个为理想）
- **每个图形总共最多 10 个单词**
- **最小 50% 空白**（60% 更好）
- **关键数字/指标最小 120 pt**
- **最小 80 pt**对于标签

**对于每个海报部分 - 严格要求：**

|部分|最大元素 |最大字数 |提示示例（必需模式）|
|---------|--------------|------------------------|----------------------------------------|
| **简介** | 3 个图标 | 6 个字 | “A0 的海报格式：超简单 3 个图标：[icon1] [icon2] [icon3]。一个字标签（100pt 粗体）。60% 空白。总共 3 个字。” |
| **方法** | 3盒| 6 个字 | “A0 的海报格式：超简单的 3 框工作流程：‘STEP1’→‘STEP2’→‘STEP3’。巨型标签 (120pt+)。60% 空白。仅 3 个单词。” |
| **结果** | 2-3 条 | 6 个字 | “A0 的海报格式：两个条：‘基线 70%’‘我们的 95%’。条上有巨大的百分比 (150pt+)。没有轴。60% 空白。” |
| **结论** | 3 张卡 | 9 个字 | “A0 的海报格式：三张卡片：‘95%’（150 磅）‘准确’、‘2X’（150 磅）‘更快’、复选标记‘就绪’。60% 空白。” |
| **案例研究** | 3 个元素 | 5 个字 | “A0 的海报格式：一种情况：徽标 + '18 个月' (150pt) + '发现' (60pt)。60% 空白。” |
| **时间表** | 3分| 3 个字 | “A0 的海报格式：仅限三年：‘2018’‘2021’‘2024’（每张 150 磅）。大图标。60% 空白。没有细节。” |

**强制提示元素（全部必需，无例外）：**
1. **“A0 的海报格式”** - 必须位于第一个
2. **“超简单”** 或 **“仅 X 元素”** - 内容限制
3. **“GIANT (120pt+)”** 或特定字体大小- 可读性
4. **“60% 空白”** - 强制呼吸空间
5. **“从 10-12 英尺处可读”** - 观看距离
6. **单词/元素的精确计数** - “总共 3 个单词”或“只有 3 个图标”

**总是失败的模式（立即拒绝）：**
- ❌“7 阶段药物发现工作流程”→ 拆分为“3 个巨型阶段”
- ❌“2015-2024 年时间表，每年更新”→“仅 3 个关键年份”
- ❌“3 个详细案例研究”→ 制作 3 个独立的简单图形
- ❌“5 种方法与指标的比较”→“仅 2：我们的方法与最佳方法”
- ❌“显示所有层的完整架构”→“仅 3 个组件”
- ❌“显示阶段 1,2,3,4,5,6”→“3 个高级阶段”

**有效的模式：**
- ✅ “从 7 个大型阶段崩溃” → 适当简化
- ✅ “一个案例有一个指标” → 如果需要，将制作多个
- ✅ “只有 3 个里程碑” → 有选择性、集中
- ✅ “2 个条形图：我们的与基线” → 直接比较
- ✅ “3 个组成部分的高级视图” → 适当简化的

---

## 科学原理图集成

有关创建原理图的详细指导，请参阅 **科学原理图** 技能文档。

**关键功能：**
- Nano Banana Pro自动生成、审查和细化图表
- 创建具有正确格式的出版物质量图像
- 确保可访问性（色盲友好，高对比度）
- 支持复杂图表的迭代细化

---

## 核心功能

### 1.LaTeX海报包

支持三大主流LaTeX海报包，各有各的优势。有关详细比较和特定于封装的指南，请参阅`references/latex_poster_packages.md`。

**beamerposter**：
- Beamer 演示类的扩展
- Beamer 用户熟悉的语法
- 出色的主题支持和定制
- 最适合：传统学术海报、机构品牌

**tikzposter**：
- 现代、灵活的设计，集成TikZ
- 内置颜色主题和布局模板
- 通过TikZ命令进行广泛定制
- 最适合：多彩、现代设计、自定义图形

**baposter**：
- 基于盒子的布局系统
- 自动间距和定位
- 专业外观的默认样式
- 最适合：多列布局、一致间距

### 2. 海报布局和结构

按照视觉传达原则创建有效的海报布局。有关全面的布局指南，请参阅`references/poster_layout_design.md`。

**常见海报部分**：
- **标题/标题**：标题、作者、隶属关系、徽标
- **简介/背景**：研究背景和动机
- **方法/途径**：方法和实验设计
- **结果**：图形和数据可视化的主要发现
- **结论**：主要要点和影响
- **参考文献**：关键引文（通常缩写）
- **致谢**：资金、合作者、机构

**布局策略**：
- **基于列的布局**：2 列， 3 列或 4 列网格
- **基于块的布局**：内容块的灵活排列
- **Z 模式流**：引导读者逻辑地浏览内容
- **视觉层次**：使用大小、颜色和间距来强调关键点

### 3. 研究海报的设计原则

应用基于证据的设计原则以实现最大影响。详细设计指导请参考`references/poster_design_principles.md`。

**版式**：
- 标题：72-120 磅，从远处可见
- 节标题：48-72 磅
- 正文：最小 24-36 磅，以便在 4-6 英尺处阅读
- 为了清晰起见，使用无衬线字体（Arial、Helvetica、Calibri）
- 最多限制 2-3 个字体系列

**颜色和对比度**：
- 使用高对比度配色方案以提高可读性
- 用于品牌推广的机构调色板
- 色盲友好调色板（避免红绿组合）
- 空白是活动空间 - 不要过度拥挤

**视觉元素**：
- 高分辨率图形（打印最少 300DPI）
- 所有图形上大而清晰的标签
- 整个图形风格一致
- 图标和图标的策略性使用图形
- 平衡文本与视觉内容（建议 40-50% 视觉内容）

**内容指南**：
- **少即是多**：建议总共 300-800 字
- 段落上的项目符号以提高可浏览性
- 清晰、简洁的消息传递
- 不言自明的图形，带有最少的文字解释
- 补充材料或在线资源的二维码

### 4. 标准海报尺寸

支持国际和会议特定海报尺寸：

**国际标准**：
- A0 (841 × 1189 mm / 33.1 × 46.8 英寸） - 最常见的欧洲标准
- A1（594 × 841 毫米/23.4 × 33.1 英寸） - 较小格式
- A2（420 × 594 毫米/16.5 × 23.4 英寸） - 紧凑型海报

**北美标准**：
- 36 × 48 英寸（914 × 1219 毫米） - 常见美国会议尺寸
- 42 × 56 英寸（1067 × 1422 毫米） - 大尺寸
- 48 × 72 英寸（1219 × 1829 毫米） - 超大

**方向**：
- 纵向（垂直） - 最常见的传统
- 横向（水平） - 更适合广泛的内容、时间线

### 5. 包特定模板

为每个主要包提供即用型模板。`assets/`目录中提供了模板。

**beamerposter模板**：
- `beamerposter_template.tex`- 可定制的beamerposter模板

**tikzposter模板**：
- `tikzposter_template.tex`- 可定制的tikzposter模板

**baposter模板**：
- `baposter_template.tex`- 可定制的baposter模板

### 6. 图形和图像集成

优化海报演示的视觉内容：

**最佳实践**：
- 尽可能使用矢量图形（PDF、SVG）以实现可扩展性
- 光栅图像：最终打印尺寸至少 300 个DPI
- 一致的图像样式（边框、标题、尺寸）
- 将相关图形分组在一起
- 使用子图进行比较

**LaTeX图形命令**：
```latex
% Include graphics package
\usepackage{graphicx}

% Simple figure
\includegraphics[width=0.8\linewidth]{figure.pdf}

% Figure with caption in tikzposter
\block{Results}{
  \begin{tikzfigure}
    \includegraphics[width=0.9\linewidth]{results.png}
  \end{tikzfigure}
}

% Multiple subfigures
\usepackage{subcaption}
\begin{figure}
  \begin{subfigure}{0.48\linewidth}
    \includegraphics[width=\linewidth]{fig1.pdf}
    \caption{Condition A}
  \end{subfigure}
  \begin{subfigure}{0.48\linewidth}
    \includegraphics[width=\linewidth]{fig2.pdf}
    \caption{Condition B}
  \end{subfigure}
\end{figure}
```

### 7. 配色方案和主题

为各种环境提供专业调色板：

**学术机构颜色**：
- 匹配大学或部门品牌
- 使用官方颜色代码（RGB、CMYK或LaTeX颜色定义)

**科学调色板**（色盲友好）：
- Viridis：从紫色到黄色的专业渐变
- ColorBrewer：经过研究测试的数据可视化调色板
- IBM Color Blind Safe：可访问的企业调色板

**特定于包的主题选择**：

**beamerposter**：
```latex
\usetheme{Berlin}
\usecolortheme{beaver}
```

**tikzposter**：
```latex
\usetheme{Rays}
\usecolorstyle{Denmark}
```

**baposter**：
```latex
\begin{poster}{
  background=plain,
  bgColorOne=white,
  headerColorOne=blue!70,
  textborder=rounded
}
```

### 8. 版式和文本格式

确保可读性和视觉吸引力：

**字体选择**：
```latex
% Sans-serif fonts recommended for posters
\usepackage{helvet}      % Helvetica
\usepackage{avant}       % Avant Garde
\usepackage{sfmath}      % Sans-serif math fonts

% Set default to sans-serif
\renewcommand{\familydefault}{\sfdefault}
```

**文本大小调整**：
```latex
% Adjust text sizes for visibility
\setbeamerfont{title}{size=\VeryHuge}
\setbeamerfont{author}{size=\Large}
\setbeamerfont{institute}{size=\normalsize}
```

**强调和突出显示**：
- 对关键术语使用粗体：`\textbf{important}`
- 谨慎地用颜色突出显示：`\textcolor{blue}{highlight}`
- 关键信息框
- 避免斜体（从远处难以阅读）

### 9. QR 码和互动元素

增强现代会议的海报互动性：

**二维码集成**：
```latex
\usepackage{qrcode}

% Link to paper, code repository, or supplementary materials
\qrcode[height=2cm]{https://github.com/username/project}

% QR code with caption
\begin{center}
  \qrcode[height=3cm]{https://doi.org/10.1234/paper}\\
  \small Scan for full paper
\end{center}
```

**数字增强**：
- 链接到代码的 GitHub 存储库
- 链接到视频演示或演示
- 链接到交互式 Web 可视化
- 链接到补充数据或附录

### 10. 编译和输出

生成高质量的PDF输出用于打印或数字显示：

**编译命令**：
```bash
# Basic compilation
pdflatex poster.tex

# With bibliography
pdflatex poster.tex
bibtex poster
pdflatex poster.tex
pdflatex poster.tex

# For beamer-based posters
lualatex poster.tex  # Better font support
xelatex poster.tex   # Unicode and modern fonts
```

**确保整页覆盖**：

海报应使用整个页面，没有过多的边距。正确配置包：

**beamerposter- 整页设置**：
```latex
\documentclass[final,t]{beamer}
\usepackage[size=a0,scale=1.4,orientation=portrait]{beamerposter}

% Remove default beamer margins
\setbeamersize{text margin left=0mm, text margin right=0mm}

% Use geometry for precise control
\usepackage[margin=10mm]{geometry}  % 10mm margins all around

% Remove navigation symbols
\setbeamertemplate{navigation symbols}{}

% Remove footline and headline if not needed
\setbeamertemplate{footline}{}
\setbeamertemplate{headline}{}
```

**tikzposter- 整页设置**：
```latex
\documentclass[
  25pt,                      % Font scaling
  a0paper,                   % Paper size
  portrait,                  % Orientation
  margin=10mm,               % Outer margins (minimal)
  innermargin=15mm,          % Space inside blocks
  blockverticalspace=15mm,   % Space between blocks
  colspace=15mm,             % Space between columns
  subcolspace=8mm            % Space between subcolumns
]{tikzposter}

% This ensures content fills the page
```

**baposter- 整页设置**：
```latex
\documentclass[a0paper,portrait,fontscale=0.285]{baposter}

\begin{poster}{
  grid=false,
  columns=3,
  colspacing=1.5em,          % Space between columns
  eyecatcher=true,
  background=plain,
  bgColorOne=white,
  borderColor=blue!50,
  headerheight=0.12\textheight,  % 12% for header
  textborder=roundedleft,
  headerborder=closed,
  boxheaderheight=2em        % Consistent box header heights
}
% Content here
\end{poster}
```

**常见问题和修复**：

**问题**：海报周围有较大的白边
```latex
% Fix for beamerposter
\setbeamersize{text margin left=5mm, text margin right=5mm}

% Fix for tikzposter
\documentclass[..., margin=5mm, innermargin=10mm]{tikzposter}

% Fix for baposter - adjust in document class
\documentclass[a0paper, margin=5mm]{baposter}
```

**问题**：内容未填充垂直空间
```latex
% Use \vfill between sections to distribute space
\block{Introduction}{...}
\vfill
\block{Methods}{...}
\vfill
\block{Results}{...}

% Or manually adjust block spacing
\vspace{1cm}  % Add space between specific blocks
```

**问题**：海报超出页面边界
```latex
% Check total width calculation
% For 3 columns with spacing:
% Total = 3×columnwidth + 2×colspace + 2×margins
% Ensure this equals \paperwidth

% Debug by adding visible page boundary
\usepackage{eso-pic}
\AddToShipoutPictureBG{
  \AtPageLowerLeft{
    \put(0,0){\framebox(\LenToUnit{\paperwidth},\LenToUnit{\paperheight}){}}
  }
}
```

**打印准备**：
- 生成PDF/X-1a 以进行专业打印
- 嵌入所有字体
- 如果需要，将颜色转换为CMYK
- 检查所有图像的分辨率（至少 300DPI）
- 如果需要，添加出血区域打印机（通常为 3-5 毫米）
- 验证页面尺寸完全符合要求

**数字显示器**：
- 用于屏幕显示的RGB色彩空间
- 优化电子邮件/网页的文件大小
- 测试不同屏幕上的可读性

### 11.PDF审核和质量控制

**关键**：在打印或演示之前始终审核生成的PDF。使用此系统检查表：

**步骤 1：页面大小验证**
```bash
# Check PDF dimensions (should match poster size exactly)
pdfinfo poster.pdf | grep "Page size"

# Expected outputs:
# A0: 2384 x 3370 points (841 x 1189 mm)
# 36x48": 2592 x 3456 points
# A1: 1684 x 2384 points (594 x 841 mm)
```

**第 2 步：溢出检查（关键） - 编译后立即执行此操作**

**⚠️ 这是海报失败的第一大原因。在继续操作之前进行检查。**

**步骤 2a：检查LaTeX日志文件**
```bash
# Check for overflow warnings (these are ERRORS, not suggestions)
grep -i "overfull\|underfull\|badbox" poster.log

# ANY "Overfull" warning = content is cut off or extending beyond boundaries
# FIX ALL OF THESE before proceeding
```

**常见溢出警告及其含义：**
- `Overfull \hbox (15.2pt too wide)`→ 文本或图形比列宽 15.2pt
- `Overfull \vbox (23.5pt too high)`→ 内容比可用空间高 23.5pt
- `Badbox`→LaTeX努力将内容容纳在边界内

**步骤 2b：视觉边缘检查（PDF查看器中 100% 缩放）**

**系统检查所有四个边缘：**

1. **顶部边缘：**
- [ ] 标题完全可见（未截断）
- [ ] 作者姓名完全可见
- [ ] 无图形触及上边距
- [ ] 安全区域内的标题内容

2. **底部边缘：**
- [ ] 参考文献完全可见（未切断）
- [ ] 致谢完整
- [ ] 联系信息可读
- [ ] 底部没有图形被切断

3. **左边缘：**
- [ ] 没有文字触及左边距
- [ ] 所有项目符号点完全可见
- [ ] 图形有左边距（不渗出）
- [ ] 列内容在边界内

4. **右边缘：**
- [ ] 没有文字超出右边距
- [ ] 图形没有在右侧被切断
- [ ] 列内容保持在边界内
- [ ] 二维码完全可见

5. **BETWEEN列：**
- [ ] 内容保留在各个列中
- [ ] 没有文本渗入相邻列
- [ ] 数字尊重列边界

**如果任何检查失败，则有溢出。在继续之前立即修复：**

**修复层次结构（按顺序尝试）：**
1. **首先检查 AI 生成的图形：**
- 它们是否太复杂（5 个以上元素）？ → 重新生成更简单的
- 它们的文本很小吗？ → 使用“150pt+”字体重新生成
- 是否太多？ → 减少图形数量

2. **减少部分：**
- 超过 5-6 个部分？ → 合并或删除
- 示例：将“讨论”合并为“结论”

3. **剪切文本内容：**
- 总共超过800字？ → 削减到 300-500
- 每部分超过 100 个单词？ → 剪切至 50-80

4. **调整图形尺寸：**
- 使用`width=\linewidth`？ → 更改为`width=0.85\linewidth`
- 使用`width=1.0\columnwidth`？ → 更改为`width=0.9\columnwidth`

5. **增加利润（最后手段）：**
   ```latex
   \documentclass[25pt, a0paper, portrait, margin=25mm]{tikzposter}
   ```

**如果存在任何溢出，请勿继续执行步骤 3。**

**步骤 3：目视检查清单**

以 100% 缩放打开PDF并检查：

**布局和间距**：
- [ ] 内容填充整个页面（无大白边距）
- [ ] 列之间的间距一致
- [ ] 块/部分之间的间距一致
- [ ] 所有元素正确对齐（使用标尺工具）
- [ ] 无重叠的文本或图形
- [ ] 空白均匀分布

**版式**：
- [ ] 标题清晰可见且大 (72pt+)
- [ ] 节标题可读 (48-72pt)
- [ ] 正文在 100% 缩放时可读（最小 24-36pt）
- [ ] 无文本截断或超出边缘
- [ ] 始终使用一致的字体
- [ ] 所有特殊字符正确渲染（符号、希腊字母）

**视觉元素**：
- [ ] 所有图形正确显示
- [ ] 无像素化或模糊图像
- [ ] 图形标题存在且可读
- [ ] 颜色按预期渲染（未褪色或太暗）
- [ ] 徽标清晰显示
- [ ] QR 码可见且可扫描

**内容完整性**：
- [ ] 标题和作者完整
- [ ] 所有章节（简介、方法、结果、结论）
- [ ] 包含参考文献
- [ ] 联系信息可见
- [ ] 致谢（如果适用）
- [ ] 没有剩余占位符文本（Lorem ipsum、TODO 等）

**技术质量**：
- [ ] 重要区域没有LaTeX编译警告
- [ ] 所有引用均已解决（无 [?] 标记）
- [ ] 所有交叉引用正常工作
- [ ] 页面边界正确（无内容被截断）

**步骤 4：缩小比例打印测试**

**基本预打印测试**：
```bash
# Create reduced-size test print (25% of final size)
# This simulates viewing full poster from ~8-10 feet

# For A0 poster, print on A4 paper (24.7% scale)
# For 36x48" poster, print on letter paper (~25% scale)
```

**打印测试清单**：
- [ ] 标题在 6 英尺外可读
- [ ] 节标题在 4 英尺外可读
- [ ] 正文在 2 英尺外可读
- [ ] 数字清晰易懂
- [ ] 打印颜色准确
- [ ]无明显设计缺陷

**第 5 步：数字质量检查**

**字体嵌入验证**：
```bash
# Check that all fonts are embedded (required for printing)
pdffonts poster.pdf

# All fonts should show "yes" in "emb" column
# If any show "no", recompile with:
pdflatex -dEmbedAllFonts=true poster.tex
```

**图像分辨率检查**：
```bash
# Extract image information
pdfimages -list poster.pdf

# Check that all images are at least 300 DPI
# Formula: DPI = pixels / (inches in poster)
# For A0 width (33.1"): 300 DPI = 9930 pixels minimum
```

**文件大小优化**：
```bash
# For email/web, compress if needed (>50MB)
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 \
   -dPDFSETTINGS=/printer -dNOPAUSE -dQUIET -dBATCH \
   -sOutputFile=poster_compressed.pdf poster.pdf

# For printing, keep original (no compression)
```

**第 6 步：辅助功能检查**

**颜色对比度验证**：
- [ ] 文本背景对比度 ≥ 4.5:1 (WCAG AA)
- [ ] 重要元素对比度 ≥ 7:1 (WCAG AAA)
- 在线测试：https://webaim.org/resources/contrastchecker/

**色盲模拟**：
- [ ] 通过色盲模拟器查看PDF
- [ ] 红绿模拟不会丢失信息
- [ ] 使用 Coblis (color-blindness.com) 或类似工具

**第 7 步：内容校对**

**系统审查**：
- [ ] 对所有文本进行拼写检查
- [ ] 验证所有作者姓名和单位
- [ ] 检查所有数字和统计数据的准确性
- [ ] 确认所有引文均正确
- [ ] 审查图表标签和标题
- [ ] 检查标题和标题中的拼写错误

**同行评审**：
- [ ] 请同事审阅海报
- [ ] 30 秒测试：他们能识别主要信息吗？
- [ ] 5分钟回顾：他们理解结论吗？
- [ ] 注意任何令人困惑的元素

**第 8 步：技术验证**

**LaTeX编译日志审查**：
```bash
# Check for warnings in .log file
grep -i "warning\|error\|overfull\|underfull" poster.log

# Common issues to fix:
# - Overfull hbox: Text extending beyond margins
# - Underfull hbox: Excessive spacing
# - Missing references: Citations not resolved
# - Missing figures: Image files not found
```

**修复常见警告**：
```latex
% Overfull hbox (text too wide)
\usepackage{microtype}  % Better spacing
\sloppy  % Allow slightly looser spacing
\hyphenation{long-word}  % Manual hyphenation

% Missing fonts
\usepackage[T1]{fontenc}  % Better font encoding

% Image not found
% Ensure paths are correct and files exist
\graphicspath{{./figures/}{./images/}}
```

**第 9 步：最终预打印检查表**

**发送到打印机之前**：
- [ ]PDF尺寸完全符合要求（使用 pdfinfo 检查）
- [ ] 嵌入所有字体（使用 pdffonts 检查）
- [ ] 颜色模式正确（如果需要，RGB用于屏幕，CMYK用于打印）
- [ ] 如果需要，添加出血区域（通常为 3-5 毫米）
- [ ] 如果需要，裁剪标记可见
- [ ] 测试打印已完成并审核
- [ ] 文件命名清晰：[姓氏]_[会议]_Poster.pdf
- [ ] 已保存备份副本

**要确认的打印规格**：
- [ ] 纸张类型（哑光与光面）
- [ ] 打印方法（喷墨、大幅面、织物）
- [ ] 颜色配置文件（如果需要，可提供给打印机）
- [ ] 交货期限和送货地址
- [ ] 管状或扁平包装偏好

**数字演示清单**：
- [ ]PDF尺寸优化（电子邮件 <10MB）
- [ ] 在多个PDF查看器（Adobe、预览等）上测试
- [ ] 在不同屏幕上正确显示
- [ ] QR 码经过测试并可正常使用
- [ ] 准备替代格式（社交媒体为 PNG）

**审查脚本**（在`scripts/review_poster.sh`中提供）：
```bash
#!/bin/bash
# Automated poster PDF review script

echo "Poster PDF Quality Check"
echo "======================="

# Check file exists
if [ ! -f "$1" ]; then
    echo "Error: File not found"
    exit 1
fi

echo "File: $1"
echo ""

# Check page size
echo "1. Page Dimensions:"
pdfinfo "$1" | grep "Page size"
echo ""

# Check fonts
echo "2. Font Embedding:"
pdffonts "$1" | head -20
echo ""

# Check file size
echo "3. File Size:"
ls -lh "$1" | awk '{print $5}'
echo ""

# Count pages (should be 1 for poster)
echo "4. Page Count:"
pdfinfo "$1" | grep "Pages"
echo ""

echo "Manual checks required:"
echo "- Visual inspection at 100% zoom"
echo "- Reduced-scale print test (25%)"
echo "- Color contrast verification"
echo "- Proofreading for typos"
```

**常见的PDF问题和解决方案**：

|问题 |原因 |解决方案 |
|-------|--------|----------|
|大白边|边距设置不正确 |减少文档类中的边距 |
|内容被截断 |超出页面边界 |检查总宽度/高度计算 |
|图像模糊 |低分辨率（<300DPI）|替换为更高分辨率的图像 |
|缺少字体 |未嵌入字体 |使用 -dEmbedAllFonts=true 进行编译 |
|页面尺寸错误 |纸张尺寸设置不正确 |验证文档类纸张尺寸 |
|颜色看起来不对 |RGB与CMYK不匹配 |转换打印色彩空间 |
|文件太大 (>50MB) |未压缩的图像 |优化图像或压缩PDF|
|二维码不起作用 |太小或分辨率低|最小2×2cm，高对比度|

### 11. 常见海报内容模式

针对不同研究类型的有效内容组织：

**实验研究海报**：
1. 标题和作者
2. 简介：问题和假设
3. 方法：实验设计（使用图表）
4. 结果：主要发现（2-4 个主要数字）
5. 结论：主要要点（3-5 个要点）
6. 未来工作（可选）
7. 参考文献和致谢

**计算/建模海报**：
1. 标题和作者
2. 动机：问题陈述
3. 方法：算法或模型（带流程图）
4. 实现：技术细节
5. 结果：性能指标和比较
6. 应用：用例
7. 代码可用性（GitHub 的 QR 代码）
8. 参考文献

**评论/调查海报**：
1. 标题和作者
2. 范围：主题概述
3. 方法：文献检索策略
4. 主要发现：主要主题（按类别组织）
5. 趋势：出版模式的可视化
6. 差距：确定的研究需求
7. 结论：总结和影响
8. 参考文献

### 12. 无障碍和包容性设计

设计可供不同受众使用的海报：

**色盲注意事项**：
- 避免红绿组合（最常见的色盲）
- 除颜色外还使用图案或形状
- 使用色盲模拟器进行测试
- 提供高对比度（WCAG AA 标准：最低 4.5:1）

**视觉障碍调节**：
- 大而清晰的字体（正文至少 24 磅）
- 高对比度文本和背景
- 清晰的视觉层次
- 避免背景中的复杂纹理或图案

**语言和内容**：
- 清晰、简洁的语言
- 定义首字母缩略词和术语
- 国际受众考虑因素
- 考虑全球会议的多语言 QR 码选项

### 13. 海报展示最佳实践

超越LaTeX的有效海报会议指南：

**内容策略**：
- 讲一个故事，不要只列出事实
- 专注于 1-3 个主要信息
- 使用视觉摘要或图形摘要
- 留出对话空间（不要过度解释）

**实物演示技巧**：
- 带上打印的讲义或带有二维码的名片
- 准备 30 秒、2 分钟和 5 分钟的口头摘要
- 站在一边，不要挡住海报
- 用开放式问题吸引观众

**数字备份**：
- 在移动设备上将海报保存为PDF
- 准备用于电子邮件共享的数字版本
- 创建社交媒体友好的图像版本
- 拥有备份打印副本或数字显示选项

## 海报创建工作流程

### 第 1 阶段：规划和内容开发

1. **确定海报要求**：
- 会议尺寸规格（A0、36×48"等）
- 方向（纵向与横向）
- 提交截止日期和格式要求

2. **制定内容大纲**：
- 识别1-3 个核心信息
- 选择关键人物（通常为 3-6 个主要视觉效果）
- 为每个部分起草简洁的文本（首选要点）
- 目标为总共 300-800 个单词

3. **选择LaTeX包**：
-beamerposter：如果熟悉 Beamer，需要机构主题
-tikzposter：用于灵活的现代、多彩设计
-baposter：用于结构化、专业的多列布局

### 第 2 阶段：生成视觉元素（AI 驱动）

**关键：使用以下命令生成简单图形最小内容。每个图形 = 一条消息。**

**内容限制：**
- 每个图形最多 4-5 个元素
- 每个图形总共最多 15 个单词
- 最少 50% 空白
- GIANT 字体（标签 80pt+，关键数字 120pt+）

1. **创建图形目录**：
   ```bash
   mkdir -p figures
   ```

2. **生成简单的视觉元素**：
   ```bash
   # Introduction - ONLY 3 icons/elements
   python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE visual with ONLY 3 elements: [icon1] [icon2] [icon3]. ONE word labels (80pt+). 50% white space. Readable from 8 feet." -o figures/intro.png
   
   # Methods - ONLY 4 steps maximum
   python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE flowchart with ONLY 4 boxes: STEP1 → STEP2 → STEP3 → STEP4. GIANT labels (100pt+). 50% white space. NO sub-steps." -o figures/methods.png
   
   # Results - ONLY 3 bars/comparisons
   python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE chart with ONLY 3 bars. GIANT percentages ON bars (120pt+). NO axis, NO legend. 50% white space." -o figures/results.png
   
   # Conclusions - EXACTLY 3 items with GIANT numbers
   python scripts/generate_schematic.py "POSTER FORMAT for A0. EXACTLY 3 key findings: '[NUMBER]' (150pt) '[LABEL]' (60pt) for each. 50% white space. NO other text." -o figures/conclusions.png
   ```

3. **查看生成的图形 - 检查是否溢出：**
- **以 25% 缩放查看**：所有文本仍然可读？
- **计数元素**：超过 5 个？ → 重新生成更简单的
- **检查空白**：小于 40%？ → 添加“60%空白”提示
- **字体太小？**：添加“甚至更大”或增加 pt 大小
- **仍然溢出？**：减少到 3 个元素，而不是 4-5

### 第 3 阶段：设计和布局

1. **选择或创建模板**：
- 从`assets/`中提供的模板开始
- 自定义配色方案以匹配品牌
- 配置页面大小和方向

2. **设计布局结构**：
- 规划列结构（2、3 或 4 列）
- 地图内容流（通常从左到右，从上到下）
- 为标题 (10-15%)、内容 (70-80%)、页脚 (5-10%) 分配空间

3. **设置版式**：
- 为不同层次结构级别配置字体大小
- 确保最小 24pt 正文
- 测试从4-6 英尺距离

### 第 4 阶段：内容集成

1. **创建海报标题**：
- 标题（简洁、描述性、10-15 个单词）
- 作者和隶属关系
- 机构徽标（高分辨率）
- 会议徽标必需

2. **集成 AI 生成的图形**：
- 将第 2 阶段的所有图形添加到适当的部分
- 使用`\includegraphics`并调整适当的大小
- 确保图形主导每个部分（视觉效果第一，文本第二）
- 块内的中心图形以产生视觉影响

3. **添加最少的支持文本**：
- 保持文本最少且可扫描（总共 300-800 个字）
- 使用项目符号，而不是段落
- 用主动语态书写
- 文本应该补充数字，而不是重复它们

4. **添加补充元素**：
- 补充材料的 QR 代码
- 参考文献（仅引用关键论文，典型 5-10 篇）
- 联系信息和致谢

### 第 5 阶段：细化和测试

1. **审查和迭代**：
- 检查打字错误和错误
- 验证所有图形都是高分辨率的
- 确保格式一致
- 确认配色方案能够很好地配合

2. **测试可读性**：
- 以 25% 比例打印并从 2-3 英尺读取（模拟 8-12 英尺的海报）
- 检查不同显示器上的颜色
- 验证 QR 码功能是否正确
- 请同事检查

3. **优化打印**：
- 在PDF中嵌入所有字体
- 验证图像分辨率
- 检查PDF尺寸要求
- 如果需要，包括出血区域

### 第 6 阶段：编译交付

1. **编译最终的PDF**：
   ```bash
   pdflatex poster.tex
   # Or for better font support:
   lualatex poster.tex
   ```

2. **验证输出质量**：
- 检查所有元素是否可见且位置正确
- 缩放至 100% 并检查图形质量
- 验证颜色是否符合预期
- 确认PDF在不同查看器上正确打开

3. **准备打印**：
- 如果需要，导出为PDF/X-1a
- 保存备份副本
- 首先在普通纸上进行测试打印
- 在截止日期前 2-3 天订购专业打印

4. **创建补充材料**：
- 保存 PNG/JPG 版本用于社交媒体
-创建讲义版本（8.5×11" 摘要）
- 准备用于电子邮件共享的数字版本

## 与其他技能集成

此技能有效地适用于：
- **科学示意图**：关键 - 用于生成所有海报图表和流程图
- **生成图像/Nano Banana Pro**：用于风格化图形、概念插图和摘要视觉效果
- **科学写作**：用于根据论文开发海报内容
- **文献评论**：用于情境化研究
- **数据分析**：用于创建结果图形和图表

**推荐工作流程**：始终使用科学原理图和生成图像技能在创建LaTeX海报以生成所有视觉元素之前

## 要避免的常见陷阱

**AI 生成的图形错误（最常见）：**
- ❌ 一张图形中的元素过多（10 多个项目）→ 最多保持 3-5 个
- ❌ AI 图形中的文字太小 → 指定“GIANT (100pt+)”或“HUGE (150pt+)”
- ❌ 提示中的细节过多 → 使用“SIMPLE”和“ONLY X elements”
- ❌ 无空白规范 → 在每个提示中添加“50% 空白”
- ❌ 具有 8 个以上步骤的复杂流程图 → 限制为最多 4-5 个步骤
- ❌ 包含 6 个以上项目的比较图表 → 最多限制 3 个项目
- ❌ 包含 5 个以上指标的主要发现 → 仅显示前 3 个

**修复 AI 图形中的溢出：**
如果您的 AI 生成的图形溢出或文本较小：
1. 添加“SIMPLER”或“只有 3 个元素”来提示
2. 增加字体大小：“150pt+”而不是“80pt+”
3. 添加“60% 空白”而不是“50%”
4. 删除子细节：“无子步骤”、“无轴标签”、“无图例”
5. 用更少的元素重新生成

**设计错误**：
- ❌ 文本太多（超过 1000 个单词）
- ❌ 字体太小（正文文本低于 24 磅）
- ❌ 低对比度颜色组合
- ❌ 布局混乱，没有空白
- ❌ 各个部分的样式不一致
- ❌ 质量差或像素化图像

**内容错误**：
- ❌ 没有清晰的叙述或信息
- ❌ 太多研究问题或目标
- ❌ 过度使用没有定义的行话
- ❌ 没有上下文的结果或解释
- ❌ 缺少作者联系信息

**技术错误**：
- ❌ 会议要求的海报尺寸错误
- ❌ 将RGB颜色发送到CMYK打印机（色移）
- ❌ 字体未嵌入PDF
- ❌ 文件大小对于提交门户来说太大
- ❌ QR 码太小或未经测试

**最佳实践**：
- ✅ 生成最多 3-5 个元素的简单 AI 图形
- ✅ 对图形中的关键数字使用 GIANT 字体 (100pt+)
- ✅ 在每个 AI 提示中指定“50% 空白”
- ✅严格遵循会议规模规格
- ✅ 在最终打印之前以缩小比例测试打印
- ✅ 使用高对比度、易于理解的配色方案
- ✅ 保持文本最小化并高度可扫描
- ✅ 包含清晰的联系信息和二维码
- ✅ 仔细校对（错误在海报上被放大！）

## 软件包安装

确保安装了所需的LaTeX软件包：

```bash
# For TeX Live (Linux/Mac)
tlmgr install beamerposter tikzposter baposter

# For MiKTeX (Windows)
# Packages typically auto-install on first use

# Additional recommended packages
tlmgr install qrcode graphics xcolor tcolorbox subcaption
```

## 脚本和自动化

`scripts/`目录中提供的帮助程序脚本：

- `review_poster.sh`：海报审查和验证
- `generate_schematic.py`：生成科学图表和原理图

## 参考文献

详细指导的综合参考文件：

- `references/latex_poster_packages.md`：beamerposter、tikzposter和baposter的详细比较与示例
- `references/poster_layout_design.md`：布局原理、网格系统和视觉流程
- `references/poster_design_principles.md`：版式、色彩理论、视觉层次结构和可访问性
- `references/poster_content_guide.md`：内容组织、写作风格和特定部分的指导

## 模板

`assets/`目录中的即用海报模板：

- beamerposter模板（经典、现代、多彩）
- tikzposter模板（默认、射线、波浪、信封）
- baposter模板（肖像、风景、简约）
- 来自各个科学学科的示例海报
- 配色方案定义和机构模板

加载这些模板并根据您的具体研究和会议要求进行定制。

