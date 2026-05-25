---
name: scientific-slides
description: 为 research talks 构建 slide decks 和 presentations。用于制作 PowerPoint slides、conference presentations、seminar talks、research presentations、thesis defense slides 或任何 scientific talk。提供 slide structure、design templates、timing guidance 和 visual validation。适用于 PowerPoint 和 LaTeX Beamer。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scientific Slides

## 概述

Scientific presentations 是传播 research、分享 findings 并与 academic 和 professional audiences 互动的重要媒介。此 skill 提供创建高效 scientific presentations 的完整指导，覆盖 structure、content development、visual design 和 delivery preparation。

**Key Focus**：面向 conferences、seminars、defenses 和 professional talks 的 oral presentations。

**CRITICAL DESIGN PHILOSOPHY**：Scientific presentations 应该 VISUALLY ENGAGING 且 RESEARCH-BACKED。务必避免干燥、文字过多的 slides。优秀的 scientific presentations 结合：
- **Compelling visuals**：高质量 figures、images、diagrams（不只是 bullet points）
- **Research context**：来自 research-lookup 的恰当 citations，以建立 credibility
- **Minimal text**：Bullet points 作为提示，解释由你口头完成
- **Professional design**：现代 color schemes、强 visual hierarchy、充足 white space
- **Story-driven**：清晰 narrative arc，而不是 data dumps

**记住**：无聊的 presentations = 被遗忘的 science。通过恰当 citations 保持 scientific rigor，同时让 slides 在视觉上令人难忘。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 准备 conference presentations（5-20 分钟）
- 开发 academic seminars（45-60 分钟）
- 创建 thesis 或 dissertation defense presentations
- 设计 grant pitch presentations
- 准备 journal club presentations
- 在 institutions 或 companies 做 research talks
- 针对 scientific topics 做 teaching 或 tutorial presentations

## 使用 Nano Banana Pro 生成 Slides

**此 skill 使用 Nano Banana Pro AI 自动生成出色 presentation slides。**

根据输出格式，有两种 workflow：

### Default Workflow: PDF Slides（推荐）

使用 Nano Banana Pro 将每张 slide 生成为完整 image，然后合并为 PDF。这会产生视觉效果最好的结果。

**工作方式：**
1. **Plan the deck**：为每张 slide 创建详细 plan（title、key points、visual elements）
2. **Generate slides**：为每张 slide 调用 Nano Banana Pro 创建完整 slide images
3. **Combine to PDF**：将 slide images 组合为单个 PDF presentation

**Step 1: Plan Each Slide**

生成前，为 presentation 创建详细 plan：

```markdown
# Presentation Plan: Introduction to Machine Learning

## Slide 1: Title Slide
- Title: "Machine Learning: From Theory to Practice"
- Subtitle: "AI Conference 2025"
- Speaker: Dr. Jane Smith, University of XYZ
- Visual: Modern abstract neural network background

## Slide 2: Introduction
- Title: "Why Machine Learning Matters"
- Key points: Industry adoption, breakthrough applications, future potential
- Visual: Icons showing different ML applications (healthcare, finance, robotics)

## Slide 3: Core Concepts
- Title: "The Three Types of Learning"
- Content: Supervised, Unsupervised, Reinforcement
- Visual: Three-part diagram showing each type with examples

... (continue for all slides)
```

**Step 2: Generate Each Slide**

使用 `generate_slide_image.py` script 创建每张 slide。

**CRITICAL: Formatting Consistency Protocol**

为确保 presentation 中所有 slides 格式统一：

1. **在 presentation 开始定义 Formatting Goal**，并包含在每个 prompt 中：
   - Color scheme（例如 "dark blue background, white text, gold accents"）
   - Typography style（例如 "bold sans-serif titles, clean body text"）
   - Visual style（例如 "minimal, professional, corporate aesthetic"）
   - Layout approach（例如 "generous white space, left-aligned content"）

2. **生成后续 slides 时，始终用 `--attach` 附上前一张 slide**：
   - 让 Nano Banana Pro 能看到并匹配已有 style
   - 在整个 deck 中建立 visual continuity
   - 确保 colors、fonts 和 design language 一致

3. **默认 author 是 "K-Dense"**，除非另有指定

4. **对于引用 research 的 slides，直接在 prompt 中包含 citations**：
   - 将 citations 加入 prompt text，使其出现在生成的 slide 上
   - 使用格式："Include citation: (Author et al., Year)" 或 "Show reference: Author et al., Year"
   - 多个 citations 时全部列出
   - Citations 应出现在 slide 底部小字或相关内容附近

5. **结果类 slides 附上已有 figures/data**（data-driven presentations 的关键要求）：
   - 创建 results slides 时，始终检查以下位置是否有 existing figures：
     - 工作目录（例如 `figures/`、`results/`、`plots/`、`images/`）
     - 用户提供的 input files 或 directories
     - 与 presentation 相关的任何 data visualizations、charts 或 graphs
   - 使用 `--attach` 包含这些 figures，让 Nano Banana Pro 能整合它们：
     - Results slides 附上实际 data figure/chart
     - Methodology slides 附上相关 diagrams
     - Title slides 附上 logos 或 institutional images
   - 附加 data figures 时，在 prompt 中说明你想要的处理方式：
     - "Create a slide presenting the attached results chart with key findings highlighted"
     - "Build a slide around this attached figure, add title and bullet points explaining the data"
     - "Incorporate the attached graph into a results slide with interpretation"
   - **生成 results slides 前**：列出工作目录文件，查找相关 figures
   - 可附加多个 figures：`--attach fig1.png --attach fig2.png`

**带格式一致性、citations 和 figure attachments 的示例：**

```bash
# Title slide (first slide - establishes the style)
python scripts/generate_slide_image.py "Title slide for presentation: 'Machine Learning: From Theory to Practice'. Subtitle: 'AI Conference 2025'. Speaker: K-Dense. FORMATTING GOAL: Dark blue background (#1a237e), white text, gold accents (#ffc107), minimal design, sans-serif fonts, generous margins, no decorative elements." -o slides/01_title.png

# Content slide with citations (attach previous slide for consistency)
python scripts/generate_slide_image.py "Presentation slide titled 'Why Machine Learning Matters'. Three key points with simple icons: 1) Industry adoption, 2) Breakthrough applications, 3) Future potential. CITATIONS: Include at bottom in small text: (LeCun et al., 2015; Goodfellow et al., 2016). FORMATTING GOAL: Match attached slide style - dark blue background, white text, gold accents, minimal professional design, no visual clutter." -o slides/02_intro.png --attach slides/01_title.png

# Background slide with multiple citations
python scripts/generate_slide_image.py "Presentation slide titled 'Deep Learning Revolution'. Key milestones: ImageNet breakthrough (2012), transformer architecture (2017), GPT models (2018-present). CITATIONS: Show references at bottom: (Krizhevsky et al., 2012; Vaswani et al., 2017; Brown et al., 2020). FORMATTING GOAL: Match attached slide style exactly - same colors, fonts, minimal design." -o slides/03_background.png --attach slides/02_intro.png

# RESULTS SLIDE - Attach actual data figure from working directory
# First, check what figures exist: ls figures/ or ls results/
python scripts/generate_slide_image.py "Presentation slide titled 'Model Performance Results'. Create a slide presenting the attached accuracy chart. Key findings to highlight: 1) 95% accuracy achieved, 2) Outperforms baseline by 12%, 3) Consistent across test sets. CITATIONS: Include at bottom: (Our results, 2025). FORMATTING GOAL: Match attached slide style exactly." -o slides/04_results.png --attach slides/03_background.png --attach figures/accuracy_chart.png

# RESULTS SLIDE - Multiple figures comparison
python scripts/generate_slide_image.py "Presentation slide titled 'Before vs After Comparison'. Build a side-by-side comparison slide using the two attached figures. Left: baseline results, Right: our improved results. Add brief labels explaining the improvement. FORMATTING GOAL: Match attached slide style exactly." -o slides/05_comparison.png --attach slides/04_results.png --attach figures/baseline.png --attach figures/improved.png

# METHODOLOGY SLIDE - Attach existing diagram
python scripts/generate_slide_image.py "Presentation slide titled 'System Architecture'. Present the attached architecture diagram with brief explanatory bullet points: 1) Input processing, 2) Model inference, 3) Output generation. FORMATTING GOAL: Match attached slide style exactly." -o slides/06_architecture.png --attach slides/05_comparison.png --attach diagrams/system_architecture.png
```

**重要：创建 results slides 前始终：**
1. 列出工作目录文件：`ls -la figures/` 或 `ls -la results/`
2. 检查用户提供的 directories 中是否有 relevant figures
3. 附上所有应出现在 slide 中的 relevant figures
4. 描述 Nano Banana Pro 应如何整合 attached figures

**Prompt Template：**

每个 prompt 都包含以下元素（按需定制）：
```
[Slide content description]
CITATIONS: Include at bottom: (Author1 et al., Year; Author2 et al., Year)
FORMATTING GOAL: [Background color], [text color], [accent color], minimal professional design, no decorative elements, consistent with attached slide style.
```

**Step 3: Combine to PDF**

```bash
# Combine all slides into a PDF presentation
python scripts/slides_to_pdf.py slides/*.png -o presentation.pdf
```

### PPT Workflow: PowerPoint with Generated Visuals

创建 PowerPoint presentations 时，用 Nano Banana Pro 为每张 slide 生成 images 和 figures，然后用 PPTX skill 单独添加 text。

**工作方式：**
1. **Plan the deck**：为每张 slide 创建 content plan
2. **Generate visuals**：使用带 `--visual-only` flag 的 Nano Banana Pro 为 slides 创建 images
3. **Build PPTX**：使用 PPTX skill（html2pptx 或 template-based）创建包含 generated visuals 和独立 text 的 slides

**Step 1: Generate Visuals for Each Slide**

```bash
# Generate a figure for the introduction slide
python scripts/generate_slide_image.py "Professional illustration showing machine learning applications: healthcare diagnosis, financial analysis, autonomous vehicles, and robotics. Modern flat design, colorful icons on white background." -o figures/ml_applications.png --visual-only

# Generate a diagram for the methods slide
python scripts/generate_slide_image.py "Neural network architecture diagram showing input layer, three hidden layers, and output layer. Clean, technical style with node connections. Blue and gray color scheme." -o figures/neural_network.png --visual-only

# Generate a conceptual graphic for results
python scripts/generate_slide_image.py "Before and after comparison showing improvement: left side shows cluttered data, right side shows organized insights. Arrow connecting them. Professional business style." -o figures/results_visual.png --visual-only
```

**Step 2: Build PowerPoint with PPTX Skill**

使用 PPTX skill 的 html2pptx workflow 创建 slides，包括：
- Step 1 生成的 images
- 单独添加的 title 和 body text
- Professional layout 和 formatting

完整 PPTX 创建文档见 `scientific-skills/pptx/SKILL.md`。

---

## Nano Banana Pro Script Reference

### generate_slide_image.py

使用 Nano Banana Pro AI 生成 presentation slides 或 visuals。

```bash
# Full slide (default) - generates complete slide as image
python scripts/generate_slide_image.py "slide description" -o output.png

# Visual only - generates just the image/figure for embedding in PPT
python scripts/generate_slide_image.py "visual description" -o output.png --visual-only

# With reference images attached (Nano Banana Pro will see these)
python scripts/generate_slide_image.py "Create a slide explaining this chart" -o slide.png --attach chart.png
python scripts/generate_slide_image.py "Combine these into a comparison slide" -o compare.png --attach before.png --attach after.png
```

**Options：**
- `-o, --output`：Output file path（required）
- `--attach IMAGE`：附加 image file(s) 作为 generation context（可多次使用）
- `--visual-only`：只生成 visual/figure，而不是完整 slide
- `--iterations`：Max refinement iterations（default: 2）
- `--api-key`：OpenRouter API key（或设置 OPENROUTER_API_KEY env var）
- `-v, --verbose`：Verbose output

**Attaching Reference Images：**

在希望 Nano Banana Pro 看见 existing images 作为 context 时使用 `--attach`：
- "Create a slide about this data" + attach data chart
- "Make a title slide with this logo" + attach logo
- "Combine these figures into one slide" + attach multiple images
- "Explain this diagram in a slide" + attach diagram

**Environment Setup：**
```bash
export OPENROUTER_API_KEY='your_api_key_here'
# Get key at: https://openrouter.ai/keys
```

### slides_to_pdf.py

将多个 slide images 合并为单个 PDF。

```bash
# Combine PNG files
python scripts/slides_to_pdf.py slides/*.png -o presentation.pdf

# Combine specific files in order
python scripts/slides_to_pdf.py title.png intro.png methods.png -o talk.pdf

# From directory (sorted by filename)
python scripts/slides_to_pdf.py slides/ -o presentation.pdf
```

**Options：**
- `-o, --output`：Output PDF path（required）
- `--dpi`：PDF resolution（default: 150）
- `-v, --verbose`：Verbose output

**Tip：** 用数字命名 slides 以保证顺序正确：`01_title.png`、`02_intro.png` 等。

---

## Prompt Writing for Slide Generation

### Full Slide Prompts（PDF Workflow）

完整 slides 应包含：
1. **Slide type**：Title slide、content slide、diagram slide 等
2. **Title**：Slide title text
3. **Content**：Key points、bullet items 或 descriptions
4. **Visual elements**：要包含哪些 imagery、icons 或 graphics
5. **Design style**：Color scheme、mood、aesthetic

**Example prompts：**

```
Title slide:
"Title slide for a medical research presentation. Title: 'Advances in Cancer Immunotherapy'. Subtitle: 'Clinical Trial Results 2024'. Professional medical theme with subtle DNA helix in background. Navy blue and white color scheme."

Content slide:
"Presentation slide titled 'Key Findings'. Three bullet points: 1) 40% improvement in response rate, 2) Reduced side effects, 3) Extended survival outcomes. Include relevant medical icons. Clean, professional design with green and white colors."

Diagram slide:
"Presentation slide showing the research methodology. Title: 'Study Design'. Flowchart showing: Patient Screening → Randomization → Treatment Groups (A, B, Control) → Follow-up → Analysis. CONSORT-style flow diagram. Professional academic style."
```

### Visual-Only Prompts（PPT Workflow）

嵌入 PowerPoint 的 images 只聚焦 visual element：

```
"Flowchart showing machine learning pipeline: Data Collection → Preprocessing → Model Training → Validation → Deployment. Clean technical style, blue and gray colors."

"Conceptual illustration of cloud computing with servers, data flow, and connected devices. Modern flat design, suitable for business presentation."

"Scientific diagram of cell division process showing mitosis phases. Educational style with labels, colorblind-friendly colors."
```

---

## 使用 Scientific Schematics 增强视觉表达

除了 slide generation，也可使用 **scientific-schematics** skill 生成 technical diagrams：

**何时改用 scientific-schematics：**
- Complex technical diagrams（circuit diagrams、chemical structures）
- 论文用 publication-quality figures（更高 quality threshold）
- 需要 scientific accuracy review 的 diagrams

**如何生成 schematics：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

创建 schematics 的详细指导请参考 scientific-schematics skill 文档。

---

## 核心能力

### 1. Presentation Structure and Organization

为不同 contexts 构建 narrative flow 清晰且结构合适的 presentations。详细指导见 `references/presentation_structure.md`。

**Universal Story Arc**：
1. **Hook**：吸引注意（30-60 秒）
2. **Context**：确立重要性（talk 的 5-10%）
3. **Problem/Gap**：指出未知内容（talk 的 5-10%）
4. **Approach**：解释你的 solution（talk 的 15-25%）
5. **Results**：呈现 key findings（talk 的 40-50%）
6. **Implications**：讨论意义（talk 的 15-20%）
7. **Closure**：令人记住的 conclusion（1-2 分钟）

**Talk-Specific Structures**：
- **Conference talks（15 min）**：聚焦 1-2 个 key findings，methods 简洁
- **Academic seminars（45 min）**：全面覆盖，详细 methods，多个 studies
- **Thesis defenses（60 min）**：完整 dissertation overview，覆盖所有 studies
- **Grant pitches（15 min）**：强调 significance、feasibility 和 impact
- **Journal clubs（30 min）**：对 published work 做 critical analysis

### 2. Slide Design Principles

创建 professional、readable 且 accessible 的 slides，以增强理解。完整 design guidelines 见 `references/slide_design_principles.md`。

**ANTI-PATTERN：避免干燥、文字过多的 Presentations**

❌ **让 Presentations 干燥且容易遗忘的因素：**
- 文字墙（每张 slide 超过 6 个 bullets）
- 小字体（body text <24pt）
- 只有白底黑字（没有 visual interest）
- 没有 images 或 graphics（只有 bullet points）
- 未定制的 generic templates
- 密集、段落式 bullet points
- 缺少 research context（无 citations）
- 所有 slides 看起来一样（重复）

✅ **让 Presentations 有吸引力且令人记住的因素：**
- HIGH-QUALITY VISUALS 占主导（figures、photos、diagrams、icons）
- 大而清晰的 text 作为 accent（不是主要内容）
- 现代、有目的的 color schemes（不是默认主题）
- 充足 white space（slides 会呼吸）
- Research-backed context（来自 research-lookup 的恰当 citations）
- 多样 slide layouts（不全是 bullet lists）
- 带 visual anchors 的 story-driven flow
- Professional、polished appearance

**Core Design Principles**：

**Visual-First Approach**（关键）：
- 从 visuals（figures、images、diagrams）开始，再添加 supporting text
- 每张 slide 都应有 STRONG visual element（figure、chart、photo、diagram）
- Text 用于解释或补充 visuals，而不是替代 visuals
- 思考："我如何展示它，而不只是说出来？"
- 目标：60-70% visual content，30-40% text

**Simplicity with Impact**：
- 每张 slide 一个 main idea
- MINIMAL text（首选 3-4 bullets，每条 4-6 个词）
- 充足 white space（slide 的 40-50%）
- 清晰 visual focus
- 大胆、自信的 design choices

**Typography for Engagement**：
- Sans-serif fonts（Arial、Calibri、Helvetica）
- LARGE fonts：body text 24-28pt（不只是 minimum 18pt）
- Slide titles 36-44pt（加粗）
- High contrast（minimum 4.5:1，prefer 7:1）
- 用 size 建立 hierarchy，而不只是 weight

**Color for Impact**：
- MODERN color palettes（不要默认 blue/gray）
- 考虑主题：biotech 用 vibrant colors，physics 用 sleek darks，health 用 warm tones
- Limited palette（总共 3-5 colors）
- High contrast combinations
- Color-blind safe（避免 red-green combinations）
- 有目的地使用 color（不是 decoration）

**Layout for Visual Interest**：
- 变化 layouts（不要全是 bullet lists）
- 使用 two-column layouts（text + figure）
- Key results 使用 full-slide figures
- Asymmetric compositions（比居中更有趣）
- 用 rule of thirds 安排 focal points
- Consistent 但不 repetitive

### 3. Data Visualization for Slides

为 presentation context 调整 scientific figures。详细指导见 `references/data_visualization_slides.md`。

**与 Journal Figures 的关键差异：**
- 简化，不要原样复制
- 更大 fonts（18-24pt minimum）
- 更少 panels（拆分到多张 slides）
- Direct labeling（不用 legends）
- 通过 color 和 size 强调
- 对复杂 data 使用 progressive disclosure

**Visualization Best Practices**：
- **Bar charts**：比较 discrete categories
- **Line graphs**：展示 trends 和 trajectories
- **Scatter plots**：展示 relationships 和 correlations
- **Heatmaps**：展示 matrix data 和 patterns
- **Network diagrams**：展示 relationships 和 connections

**应避免的常见错误**：
- 字体太小（<18pt）
- 一张 slide 上 panels 过多
- Legends 过于复杂
- Contrast 不足
- Layouts 混乱

### 4. Talk-Specific Guidance

不同 presentation contexts 需要不同方法。每种类型的完整指导见 `references/talk_types_guide.md`。

**Conference Talks**（10-20 分钟）：
- Structure：Brief intro → minimal methods → key results → quick conclusion
- Focus：只讲 1-2 个 main findings
- Style：Engaging、fast-paced、memorable
- Goal：激发兴趣、network、获得邀请

**Academic Seminars**（45-60 分钟）：
- Structure：Comprehensive coverage with detailed methods
- Focus：Multiple findings、depth of analysis
- Style：Scholarly、interactive、discussion-oriented
- Goal：展示 expertise、获得 feedback、collaborate

**Thesis Defenses**（45-60 分钟）：
- Structure：Complete dissertation overview、所有 studies
- Focus：展示 mastery 和 independent thinking
- Style：Formal、comprehensive、prepared for interrogation
- Goal：通过 examination、defend research decisions

**Grant Pitches**（10-20 分钟）：
- Structure：Problem → significance → approach → feasibility → impact
- Focus：Innovation、preliminary data、team qualifications
- Style：Persuasive、focused on outcomes and impact
- Goal：获得 funding、证明 viability

**Journal Clubs**（20-45 分钟）：
- Structure：Context → methods → results → critical analysis
- Focus：理解并 critique published work
- Style：Educational、critical、discussion-facilitating
- Goal：学习、critique、讨论 implications

### 5. Implementation Options

#### Nano Banana Pro PDF（Default - Recommended）

**最适合**：视觉出色的 slides、快速创建、non-technical audiences

**这是默认且推荐的方法。** 使用 AI 将每张 slide 生成为完整 image。

**Workflow**：
1. Plan each slide（title、content、visual elements）
2. 用 `generate_slide_image.py` 生成每张 slide
3. 用 `slides_to_pdf.py` 合并为 PDF

```bash
# Generate slides
python scripts/generate_slide_image.py "Title: Introduction..." -o slides/01.png
python scripts/generate_slide_image.py "Title: Methods..." -o slides/02.png

# Combine to PDF
python scripts/slides_to_pdf.py slides/*.png -o presentation.pdf
```

**Advantages**：
- 视觉效果最强
- 创建速度快（describe and generate）
- 不需要 design skills
- Consistent、professional appearance
- 适合 general audiences

**Best for**：
- Conference talks
- Business presentations
- General scientific talks
- Pitch presentations

#### PowerPoint via PPTX Skill

**最适合**：Editable slides、custom designs、template-based workflows

**Reference**：完整文档见 `scientific-skills/pptx/SKILL.md`

用带 `--visual-only` 的 Nano Banana Pro 生成 images，然后用 text 构建 PPTX。

**Key Resources**：
- `assets/powerpoint_design_guide.md`：完整 PowerPoint design guide
- PPTX skill 的 `html2pptx.md`：Programmatic creation workflow
- PPTX skill 的 scripts：`rearrange.py`、`inventory.py`、`replace.py`、`thumbnail.py`

**Workflow**：
1. 使用 `generate_slide_image.py --visual-only` 生成 visuals
2. 设计 HTML slides（programmatic）或使用 templates
3. 使用 html2pptx 或 template editing 创建 presentation
4. 添加 generated images 和 text content
5. 生成 thumbnails 做 visual validation
6. 基于 visual inspection 迭代

**Advantages**：
- Editable slides（之后可修改 text）
- Complex animations 和 transitions
- Interactive elements
- 兼容 company templates

#### LaTeX Beamer

**最适合**：Mathematical content、consistent formatting、version control

**Reference**：完整文档见 `references/beamer_guide.md`

**Templates Available**：
- `assets/beamer_template_conference.tex`：15-minute conference talk
- `assets/beamer_template_seminar.tex`：45-minute academic seminar
- `assets/beamer_template_defense.tex`：Dissertation defense

**Workflow**：
1. 选择合适 template
2. 定制 theme 和 colors
3. 添加 content（LaTeX native：equations、code、algorithms）
4. 编译为 PDF
5. 转换为 images 进行 visual validation

**Advantages**：
- 数学和 equations 效果好
- Consistent、professional appearance
- Version control friendly（plain text）
- 非常适合 algorithms 和 code
- Reproducible 且 programmatic

### 6. Visual Review and Iteration

通过 visual inspection 实施迭代改进。完整 workflow 见 `references/visual_review_workflow.md`。

**Visual Validation Workflow**：

**Step 1: Generate PDF**（如果还不是 PDF）
- PowerPoint：导出为 PDF
- Beamer：编译 LaTeX source

**Step 2: Convert to Images**
```bash
# Using the pdf_to_images script
python scripts/pdf_to_images.py presentation.pdf review/slide --dpi 150

# Or use pptx skill's thumbnail tool
python scientific-skills/pptx/scripts/thumbnail.py presentation.pptx review/thumb
```

**Step 3: Systematic Inspection**

逐张 slide 检查：
- **Text overflow**：Text 被边缘截断
- **Element overlap**：Text 与 images 或其他 text overlap
- **Font sizes**：Text 太小（<18pt）
- **Contrast**：Text 与 background contrast 不足
- **Layout issues**：Misalignment、spacing 差
- **Visual quality**：Pixelated images、rendering 差

**Step 4: Document Issues**

创建 issue log：
```
Slide # | Issue Type | Description | Priority
--------|-----------|-------------|----------
3       | Text overflow | Bullet 4 extends beyond box | High
7       | Overlap | Figure overlaps with caption | High
12      | Font size | Axis labels too small | Medium
```

**Step 5: Apply Fixes**

修改 source files：
- PowerPoint：编辑 text boxes，resize elements
- Beamer：调整 LaTeX code 并重新 compile

**Step 6: Re-Validate**

重复 Steps 1-5，直到没有 critical issues。

**Stopping Criteria**：
- 无 text overflow
- 无 inappropriate overlaps
- 所有 text 可读（≥18pt equivalent）
- Contrast 充分（≥4.5:1）
- Professional appearance

### 7. Timing and Pacing

确保 presentations 符合 allocated time。完整 timing guidance 见 `assets/timing_guidelines.md`。

**The One-Slide-Per-Minute Rule**：
- 通用指南：约 1 slide per minute
- 复杂 slides 调整为 2-3 minutes
- 简单 slides 调整为 15-30 seconds

**Time Allocation**：
- Introduction：15-20%
- Methods：15-20%
- Results：40-50%（MOST TIME）
- Discussion：15-20%
- Conclusion：5%

**Practice Requirements**：
- 5-minute talk：练习 5-7 次
- 15-minute talk：练习 3-5 次
- 45-minute talk：练习 3-4 次
- Defense：练习 4-6 次

**Timing Checkpoints**：

15-minute talk：
- 3-4 minutes：完成 introduction
- 7-8 minutes：Results 过半
- 12-13 minutes：开始 conclusions

**Emergency Strategies**：
- Running behind：跳过 backup slides（提前准备）
- Running ahead：扩展示例，稍微放慢
- 永远不要跳过 conclusions

### 8. Validation and Quality Assurance

**Automated Validation**：
```bash
# Validate slide count, timing, file size
python scripts/validate_presentation.py presentation.pdf --duration 15

# Generates report on:
# - Slide count vs. recommended range
# - File size warnings
# - Slide dimensions
# - Font size issues (PowerPoint)
# - Compilation success (Beamer)
```

**Manual Validation Checklist**：
- [ ] Slide count appropriate for duration
- [ ] Title slide complete（name、affiliation、date）
- [ ] Clear narrative flow
- [ ] One main idea per slide
- [ ] Font sizes ≥18pt（preferably 24pt+）
- [ ] High contrast colors
- [ ] Figures large and readable
- [ ] No text overflow or element overlap
- [ ] Consistent design throughout
- [ ] Slide numbers present
- [ ] Contact info on final slide
- [ ] Backup slides prepared
- [ ] Tested on projector（if possible）

## Workflow for Presentation Development

### Stage 1: Planning（Before Creating Slides）

**Define Context**：
1. Talk 类型是什么？（Conference、seminar、defense 等）
2. 多长？（Duration in minutes）
3. Audience 是谁？（Specialists、general、mixed）
4. Venue 是什么？（Room size、A/V setup、virtual/in-person）
5. 之后会发生什么？（Q&A、discussion、networking）

**Research and Literature Review**（使用 research-lookup skill）：
1. **Search for background literature**：查找 5-10 篇 key papers 建立 context
2. **Identify knowledge gaps**：使用 research-lookup 查找未知内容
3. **Locate comparison studies**：查找 methods 或 results 相似的 papers
4. **Gather supporting citations**：收集支持 interpretations 的 papers
5. **Build reference list**：为 slides 创建 .bib file 或 citation list
6. **Note key findings to cite**：记录要引用的 specific results

**Develop Content Outline**：
1. 识别 1-3 个 core messages
2. 选择 key findings 呈现
3. 选择 essential figures（15-min talk 通常 3-6 张）
4. 规划带 proper citations 的 narrative arc
5. 按 section 分配时间

**15-Minute Talk 示例 Outline**：
```
1. Title (30 sec)
2. Hook: Compelling problem (60 sec) [Cite 1-2 papers via research-lookup]
3. Background (90 sec) [Cite 3-4 key papers establishing context]
4. Research question (45 sec) [Cite papers showing gap]
5. Methods overview (2 min)
6-8. Main result 1 (3 min, 3 slides)
9-10. Main result 2 (2 min, 2 slides)
11-12. Result 3 or validation (2 min, 2 slides)
13-14. Discussion and implications (2 min) [Compare to 2-3 prior studies]
15. Conclusions (45 sec)
16. Acknowledgments (15 sec)

NOTE: Use research-lookup to find papers for background (slides 2-4) 
and discussion (slides 13-14) BEFORE creating slides.
```

### Stage 2: Design and Creation

**Choose Implementation Method**：

**Option A: PowerPoint（via PPTX skill）**
1. 阅读 `assets/powerpoint_design_guide.md`
2. 阅读 `scientific-skills/pptx/SKILL.md`
3. 选择 approach（programmatic 或 template-based）
4. 创建 consistent design 的 master slides
5. 按 outline 构建 presentation

**Option B: LaTeX Beamer**
1. 阅读 `references/beamer_guide.md`
2. 从 `assets/` 选择合适 template
3. 定制 theme 和 colors
4. 在 LaTeX 中写入 content
5. 编译为 PDF

**Design Considerations**（让它有视觉吸引力）：
- **选择 MODERN color palette**：匹配 topic（biotech=vibrant，physics=sleek，health=warm）
  - 使用 pptx skill 的 color palette examples（Teal & Coral、Bold Red、Deep Purple & Emerald 等）
  - 不要只用默认 blue/gray themes
  - 3-5 colors，high contrast
- **选择 clean fonts**：Sans-serif，大字号（body 24pt+）
- **规划 visual elements**：每张 slide 用什么 images、diagrams、icons？
- **创建 varied layouts**：混合 full-figure、two-column、text-overlay（不要全是 bullets）
- **设计 section dividers**：用 striking graphics 做 visual breaks
- **规划 animations/builds**：为复杂 slides 控制 information flow
- **增加 visual interest**：Background images、color blocks、shapes、icons

### Stage 3: Content Development

**Populate Slides**（Visual-First Strategy）：
1. **Start with visuals**：为每个 key point 规划 figures、images、diagrams
2. **大量使用 research-lookup**：查找 8-15 篇 papers 以获得 proper citations
3. **先创建 visual backbone**：加入所有 figures、charts、images、diagrams
4. **添加 minimal text 作为支持**：Bullet points 补充 visuals，而不替代 visuals
5. **设计 section dividers**：用 images 或 graphics 作为 visual breaks（不只是 text）
6. **打磨 title/closing**：让视觉有冲击力，包含 contact info
7. **添加 transitions/builds**：控制 information flow

**VISUAL CONTENT REQUIREMENTS**（让 Slides 有吸引力）：
- **Images**：使用 high-quality photos、illustrations、conceptual graphics
- **Icons**：概念的 visual representations（不是 decoration）
- **Diagrams**：Flowcharts、schematics、process diagrams
- **Figures**：简化 research figures，使用 LARGE labels（18-24pt）
- **Charts**：带清晰 messages 的 clean data visualizations
- **Graphics**：Visual metaphors、conceptual illustrations
- **Color blocks**：用 colored shapes 视觉化组织内容
- 目标：每张 slide 至少 1-2 个 strong visual elements

**Scientific Content**（Research-Backed）：
- **Citations**：大量使用 research-lookup 查找 relevant papers
  - Introduction：引用 3-5 篇 papers 建立 context 和 gap
  - Background：视觉化展示 key prior work（不只是引用）
  - Discussion：引用 3-5 篇 papers 与你的 results 比较
  - 使用 author-year format（Smith et al., 2023）提升 readability
  - Citations 建立 credibility 和 scientific rigor
- **Figures**：从 papers 简化，LARGE labels（18-24pt minimum）
- **Equations**：大而清晰，解释每个 term（谨慎使用）
- **Tables**：最小化，突出 key comparisons（不要 data dumps）
- **Code/Algorithms**：使用 syntax highlighting，保持简短

**Text Guidelines**（Less is More）：
- Bullet points，绝不要 paragraphs
- 每张 slide 3-4 bullets（最多 6，仅在必要时）
- 每个 bullet 4-6 words（比 6×6 rule 更短）
- Key terms 加粗
- Text 是 SUPPORTING ROLE，visuals 才是主角
- 使用 builds 控制 pacing

### Stage 4: Visual Validation

**Generate Images**：
```bash
# Convert PDF to images
python scripts/pdf_to_images.py presentation.pdf review/slides

# Or create thumbnail grid
python scientific-skills/pptx/scripts/thumbnail.py presentation.pptx review/grid
```

**Systematic Review**：
1. 查看每张 slide image
2. 按 issue checklist 检查
3. 记录问题和 slide numbers
4. 远距离测试 readability（以 50% size 查看）

**Common Issues to Fix**：
- Text 超出边界
- Figures 与 text overlap
- Font sizes 太小
- Poor contrast
- Misalignment

**Iteration**：
1. 在 source 中修复 identified issues
2. 重新生成 PDF/presentation
3. 再次转换为 images
4. Re-inspect
5. 重复直到 clean

### Stage 5: Practice and Refinement

**Practice Schedule**：
- Run 1：Rough draft（通常会超时）
- Run 2：Smooth transitions
- Run 3：Exact timing
- Run 4：Final polish
- Run 5+：Maintenance（前一天、当天早上）

**What to Practice**：
- Full talk with timer
- Difficult explanations
- Sections 之间的 transitions
- Opening 和 closing（练到 flawless）
- Anticipated questions

**Refinement Based on Practice**：
- 如果超时，删 slides
- 如果不清楚，扩展 explanations
- 调整 wording 提高清晰度
- 标记 timing checkpoints
- 准备 backup slides

### Stage 6: Final Preparation

**Technical Checks**：
- [ ] Multiple copies saved（laptop、cloud、USB）
- [ ] Works on presentation computer
- [ ] Adapters/cables available
- [ ] Backup PDF version
- [ ] Tested with projector（if possible）

**Content Final**：
- [ ] No typos or errors
- [ ] All figures high quality
- [ ] Slide numbers correct
- [ ] Contact info on final slide
- [ ] Backup slides ready

**Delivery Prep**：
- [ ] Notes prepared（if using）
- [ ] Timer/phone ready
- [ ] Water available
- [ ] Business cards/handouts
- [ ] Comfortable with material（3+ practices）

## 与其他 Skills 的集成

**Research Lookup**（Scientific Presentations 的关键）：
- **Background development**：搜索 literature 构建 introduction context
- **Citation gathering**：查找 talk 中要引用的 key papers
- **Gap identification**：识别 unknowns 以驱动 research motivation
- **Prior work comparison**：查找与你 results 对比的 papers
- **Supporting evidence**：定位支持 interpretations 的 literature
- **Question preparation**：查找可能帮助 Q&A responses 的 papers
- 开发任何 scientific presentation 时**始终使用 research-lookup**，以确保 proper context 和 citations

**Scientific Writing**：
- 将 paper content 转换为 presentation format
- 提取 key findings 并简化
- 使用相同 figures（但为 slides 重新设计）
- 保持 terminology 一致

**PPTX Skill**：
- 用于 PowerPoint creation 和 editing
- 利用 scripts 进行 template workflows
- 使用 thumbnail generation 做 validation
- 参考 html2pptx 进行 programmatic creation

**Data Visualization**：
- 创建适合 presentation 的 figures
- 简化 complex visualizations
- 确保远距离可读
- 使用 progressive disclosure

## 应避免的常见陷阱

### Content Mistakes

**Dry, Boring Presentations**（务必避免）：
- Problem：文字过多且没有 visual interest 的 slides，缺少 research context
- Signs：全是 bullet points、无 images、默认 templates、无 citations
- Solution：
  - 使用 research-lookup 查找 8-15 篇 papers，建立可信 context
  - 每张 slide 添加 high-quality visuals（figures、photos、diagrams、icons）
  - 选择反映 topic 的 modern color palette
  - 变化 slide layouts（不要全是 bullet lists）
  - 用 visuals 讲故事，少用 text

**Too Much Content**：
- Problem：试图包含 paper 中所有内容
- Solution：短 talks 聚焦 1-2 个 key findings，并视觉化呈现

**Too Much Text**：
- Problem：Slides 上有完整 paragraphs、密集 bullet points、照读
- Solution：3-4 bullets，每条 4-6 words，让 visuals 承载 message

**Missing Research Context**：
- Problem：无 citations、claims 无支持、positioning 不清
- Solution：使用 research-lookup 查找 papers，在 intro 引用 3-5 篇，在 discussion 引用 3-5 篇

**Poor Narrative**：
- Problem：主题跳跃、故事不清、无 flow
- Solution：遵循 story arc，使用 visual transitions，保持主线

**Rushing Through Results**：
- Problem：methods 简短、results 简短、discussion 很长
- Solution：花 40-50% 时间在 results 上，视觉化展示 data

### Design Mistakes

**Generic, Default Appearance**：
- Problem：直接使用默认 PowerPoint/Beamer themes 而不定制，显得过时
- Solution：选择 modern color palette，定制 fonts/layouts，增加 visual personality

**Text-Heavy, Visual-Poor**：
- Problem：全是 bullet point slides，无 images 或 graphics，看起来无聊
- Solution：每张 slide 加 figures、photos、diagrams、icons，让视觉更有趣

**Small Fonts**：
- Problem：Body text <18pt，后排读不清，显得不专业
- Solution：body 用 24-28pt（不只是 minimum 18pt），titles 用 36-44pt

**Low Contrast**：
- Problem：浅色文字配浅色背景，visibility 差，难读
- Solution：高 contrast（prefer 7:1，不只是 minimum 4.5:1），用 contrast checker 测试

**Cluttered Slides**：
- Problem：元素过多，无 white space，令人 overwhelmed
- Solution：每张 slide 一个 idea，40-50% white space，充足 spacing

**Inconsistent Formatting**：
- Problem：不同 slides 使用不同 fonts、colors、layouts，显得业余
- Solution：使用 master slides，维护 design system，保持 professional consistency

**Missing Visual Hierarchy**：
- Problem：所有内容大小和颜色相同，无 emphasis，focus 不清
- Solution：使用 size differences（titles 大，body 中等）、color emphasis 和清晰 focal point

### Timing Mistakes

**Not Practicing**：
- Problem：第一次完整讲就是正式 presentation
- Solution：至少用 timer 练习 3 次

**No Time Checkpoints**：
- Problem：太晚才发现超时
- Solution：设置 3-4 个 checkpoints，并全程监控

**Going Over Time**：
- Problem：非常不专业，还会挤占 Q&A
- Solution：练到准确时间，准备 Plan B（可跳过 slides）

**Skipping Conclusions**：
- Problem：时间不够时匆忙讲完或跳过 ending
- Solution：永远不要跳过 conclusions，改为删减前面内容

## Tools and Scripts

### Nano Banana Pro Scripts

**generate_slide_image.py** - 使用 AI 生成 slides 或 visuals：
```bash
# Full slide (for PDF workflow)
python scripts/generate_slide_image.py "Title: Introduction\nContent: Key points" -o slide.png

# Visual only (for PPT workflow)
python scripts/generate_slide_image.py "Diagram description" -o figure.png --visual-only

# Options:
# -o, --output       Output file path (required)
# --visual-only      Generate just the visual, not complete slide
# --iterations N     Max refinement iterations (default: 2)
# -v, --verbose      Verbose output
```

**slides_to_pdf.py** - 将 slide images 合并为 PDF：
```bash
# From glob pattern
python scripts/slides_to_pdf.py slides/*.png -o presentation.pdf

# From directory (sorted by filename)
python scripts/slides_to_pdf.py slides/ -o presentation.pdf

# Options:
# -o, --output    Output PDF path (required)
# --dpi N         PDF resolution (default: 150)
# -v, --verbose   Verbose output
```

### Validation Scripts

**validate_presentation.py**：
```bash
python scripts/validate_presentation.py presentation.pdf --duration 15

# Checks:
# - Slide count vs. recommended range
# - File size warnings
# - Slide dimensions
# - Font sizes (PowerPoint)
# - Compilation (Beamer)
```

**pdf_to_images.py**：
```bash
python scripts/pdf_to_images.py presentation.pdf output/slide --dpi 150

# Converts PDF to images for visual inspection
# Supports: JPG, PNG
# Adjustable DPI
# Page range selection
```

### PPTX Skill Scripts

来自 `scientific-skills/pptx/scripts/`：
- `thumbnail.py`：创建 thumbnail grids
- `rearrange.py`：Duplicate and reorder slides
- `inventory.py`：Extract text content
- `replace.py`：Programmatically update text

### External Tools

**Recommended**：
- PDF viewer：用于 review presentations
- Color contrast checker：WebAIM Contrast Checker
- Color blindness simulator：Coblis
- Timer app：用于 practice sessions
- Screen recorder：用于 self-review

## Reference Files

特定方面的 comprehensive guides：

- **`references/presentation_structure.md`**：所有 talk types 的 detailed structure、timing allocation、opening/closing strategies、transition techniques
- **`references/slide_design_principles.md`**：Typography、color theory、layout、accessibility、visual hierarchy、design workflow
- **`references/data_visualization_slides.md`**：Simplifying figures、chart types、progressive disclosure、common mistakes、recreation workflow
- **`references/talk_types_guide.md`**：Conferences、seminars、defenses、grants、journal clubs 的具体指导和 examples
- **`references/beamer_guide.md`**：完整 LaTeX Beamer documentation、themes、customization、advanced features、compilation
- **`references/visual_review_workflow.md`**：PDF to images conversion、systematic inspection、issue documentation、iterative improvement

## Assets

### Templates

- **`assets/beamer_template_conference.tex`**：15-minute conference talk template
- **`assets/beamer_template_seminar.tex`**：45-minute academic seminar template
- **`assets/beamer_template_defense.tex`**：Dissertation defense template

### Guides

- **`assets/powerpoint_design_guide.md`**：完整 PowerPoint design 和 implementation guide
- **`assets/timing_guidelines.md`**：完整 timing、pacing 和 practice strategies

## Quick Start Guide

### For a 15-Minute Conference Talk（PDF Workflow - Recommended）

1. **Research & Plan**（45 分钟）：
   - **使用 research-lookup** 查找 8-12 篇 relevant papers 作为 citations
   - 构建 reference list（background、comparison studies）
   - Outline content（intro → methods → 2-3 key results → conclusion）
   - **为每张 slide 创建 detailed plan**（title、key points、visual elements）
   - 目标 15-18 slides

2. **Generate Slides with Nano Banana Pro**（1-2 小时）：

   **重要：使用 consistent formatting，附加 previous slides，并包含 citations！**

   ```bash
   # Title slide (establishes style - default author: K-Dense)
   python scripts/generate_slide_image.py "Title slide: 'Your Research Title'. Conference name, K-Dense. FORMATTING GOAL: [your color scheme], minimal professional design, no decorative elements, clean and corporate." -o slides/01_title.png
   
   # Introduction slide with citations (attach previous for consistency)
   python scripts/generate_slide_image.py "Slide titled 'Why This Matters'. Three key points with simple icons. CITATIONS: Include at bottom: (Smith et al., 2023; Jones et al., 2024). FORMATTING GOAL: Match attached slide style exactly." -o slides/02_intro.png --attach slides/01_title.png
   
   # Continue for each slide (always attach previous, include citations where relevant)
   python scripts/generate_slide_image.py "Slide titled 'Methods'. Key methodology points. CITATIONS: (Based on Chen et al., 2022). FORMATTING GOAL: Match attached slide style exactly." -o slides/03_methods.png --attach slides/02_intro.png
   
   # Combine to PDF
   python scripts/slides_to_pdf.py slides/*.png -o presentation.pdf
   ```

3. **Review & Iterate**（30 分钟）：
   - 打开 PDF 并 review 每张 slide
   - 重新生成任何需要改进的 slides
   - 重新合并为 PDF

4. **Practice**（2-3 小时）：
   - 用 timer 练习 3-5 次
   - 目标 13-14 分钟（留 buffer）
   - 录制自己并回看
   - **准备 questions**（用 research-lookup 预判）

5. **Finalize**（30 分钟）：
   - 如需，生成 backup/appendix slides
   - 保存 multiple copies
   - 在 presentation computer 上测试

总时间：约 5-6 小时，完成 quality AI-generated presentation

### Alternative: PowerPoint Workflow

如果需要 editable slides（例如 company templates）：

1. **Plan slides** 如上
2. 使用 `--visual-only` flag **生成 visuals**：
   ```bash
   python scripts/generate_slide_image.py "diagram description" -o figures/fig1.png --visual-only
   ```
3. 使用 PPTX skill 和 generated images **构建 PPTX**
4. 使用 PPTX workflow 单独 **添加 text**

完整 PowerPoint workflow 见 `scientific-skills/pptx/SKILL.md`。

## Summary: Key Principles

1. **Visual-First Design**：每张 slide 需要 strong visual element（figure、image、diagram），避免 text-only slides
2. **Research-Backed**：使用 research-lookup 查找 8-15 篇 papers，在 intro 引用 3-5 篇，在 discussion 引用 3-5 篇
3. **Modern Aesthetics**：选择匹配 topic 的 contemporary color palette，不要默认 themes
4. **Minimal Text**：3-4 bullets，每条 4-6 words（24-28pt font），让 visuals 讲故事
5. **Structure**：遵循 story arc，将 40-50% 时间放在 results
6. **High Contrast**：prefer 7:1，以获得 professional appearance
7. **Varied Layouts**：混合 full-figure、two-column、visual overlays（不要全是 bullets）
8. **Timing**：练习 3-5 次，约 1 slide per minute，永远不要跳过 conclusions
9. **Validation**：使用 visual review workflow 捕获 overflow 和 overlap
10. **White Space**：Slide 保留 40-50% 空白以获得视觉呼吸感

**记住**：
- **Boring = Forgotten**：干燥、文字过多的 slides 无法传播你的 science
- **Visual + Research = Impact**：将 compelling visuals 与 research-backed context 结合
- **你才是 presentation，slides 是 visual support**：它们应该增强而不是替代你的 talk
