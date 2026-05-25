---
name: pptx-posters
description: 使用 HTML/CSS 创建可导出为 PDF 或 PPTX 的 research posters。仅当用户明确请求 PowerPoint/PPTX poster format 时使用此 skill。对于标准 research posters，请改用 latex-posters。此 skill 提供现代 web-based poster design，包含 responsive layouts 和便捷 visual integration。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# PPTX Research Posters（HTML-Based）

## 概览

**⚠️ 仅当用户明确请求 PPTX/POWERPOINT POSTER FORMAT 时使用此 Skill。**

对于标准 research posters，请改用 **latex-posters** skill；它提供更好的 typographic control，也是 academic conferences 的默认选择。

此 skill 使用 HTML/CSS 创建 research posters，随后可导出为 PDF 或转换为 PowerPoint format。web-based 方法提供：
- 现代 responsive layouts
- 便捷集成 AI-generated visuals
- 在 browser 中快速迭代和预览
- 通过 browser print function 导出到 PDF
- 如有明确需要，可转换为 PPTX

## 何时使用此 Skill

**仅在以下情况使用此 skill：**
- 用户明确请求 "PPTX poster"、"PowerPoint poster" 或 "PPT poster"
- 用户特别要求 HTML-based poster
- 用户需要创建后在 PowerPoint 中编辑 poster
- LaTeX 不可用，或用户请求 non-LaTeX solution

**不要在以下情况使用此 skill：**
- 用户要求 "poster" 但未指定格式 → 使用 latex-posters
- 用户要求 "research poster" 或 "conference poster" → 使用 latex-posters
- 用户提到 LaTeX、tikzposter、beamerposter 或 baposter → 使用 latex-posters

## AI-Powered Visual Element Generation

**标准 Workflow：创建 HTML poster 之前，使用 AI 生成所有主要 visual elements。**

这是创建视觉吸引力强的 posters 的推荐方法：
1. 规划所需全部 visual elements（hero image、intro、methods、results、conclusions）
2. 使用 scientific-schematics 或 Nano Banana Pro 生成每个 element
3. 在 HTML template 中组装生成的 images
4. 在 visuals 周围添加 text content

**目标：poster area 的 60-70% 应为 AI-generated visuals，30-40% 为 text。**

---

### 关键：Poster-Size Font Requirements

**⚠️ AI-generated visualizations 内所有 text 都必须达到 poster-readable。**

为 posters 生成 graphics 时，每个 prompt 都必须包含 font size specifications。Poster graphics 会从 4-6 feet 外观看，因此 text 必须很大。

**每个 poster graphic 的强制 prompt requirements：**

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

**⚠️ 生成前：审查 prompt 并计数 elements**
- 如果描述有 5+ items → 停止。拆成多个 graphics
- 如果 workflow 有 5+ stages → 停止。只展示 3-4 个 high-level steps
- 如果 comparison 有 4+ methods → 停止。只展示 top 3 或 Our vs Best Baseline

**示例 - 错误（7-stage workflow）：**
```bash
# ❌ Creates tiny unreadable text
python scripts/generate_schematic.py "Drug discovery workflow: Stage 1 Target ID, Stage 2 Synthesis, Stage 3 Screening, Stage 4 Lead Opt, Stage 5 Validation, Stage 6 Clinical Trial, Stage 7 FDA Approval with metrics." -o figures/workflow.png
```

**示例 - 正确（3 mega-stages）：**
```bash
# ✅ Same content, simplified to readable poster format
python scripts/generate_schematic.py "POSTER FORMAT for A0. ULTRA-SIMPLE 3-box workflow: 'DISCOVER' → 'VALIDATE' → 'APPROVE'. Each word in GIANT bold (120pt+). Thick arrows (10px). 60% white space. ONLY these 3 words. NO substeps. Readable from 12 feet." -o figures/workflow_simple.png
```

---

### 关键：防止 Content Overflow

**⚠️ Posters 不得在边缘截断 text 或 content。**

**预防规则：**

**1. 限制 Content Sections（最多 5-6 sections）：**
```
✅ GOOD - 5 sections with room to breathe:
   - Title/Header
   - Introduction/Problem
   - Methods
   - Results (1-2 key findings)
   - Conclusions

❌ BAD - 8+ sections crammed together
```

**2. Word Count Limits：**
- **每个 section**：最多 50-100 words
- **Total poster**：最多 300-800 words
- **如果内容更多**：删减，或制作 handout

---

## 核心能力

### 1. HTML/CSS Poster Design

HTML template（`assets/poster_html_template.html`）提供：
- 固定 poster dimensions（36×48 inches = 2592×3456 pt）
- 带 gradient styling 的专业 header
- Three-column content layout
- 具有现代 styling 的 block-based sections
- 包含 references 和 contact info 的 footer

### 2. Poster Structure

**标准 Layout：**
```
┌─────────────────────────────────────────┐
│  HEADER: Title, Authors, Hero Image     │
├─────────────┬─────────────┬─────────────┤
│ Introduction│   Results   │  Discussion │
│             │             │             │
│   Methods   │   (charts)  │ Conclusions │
│             │             │             │
│  (diagram)  │   (data)    │   (summary) │
├─────────────┴─────────────┴─────────────┤
│  FOOTER: References & Contact Info      │
└─────────────────────────────────────────┘
```

### 3. Visual Integration

每个 section 都应突出展示 AI-generated visuals：

**Hero Image（Header）：**
```html
<img src="figures/hero.png" class="hero-image">
```

**Section Graphics：**
```html
<div class="block">
  <h2 class="block-title">Methods</h2>
  <div class="block-content">
    <img src="figures/workflow.png" class="block-image">
    <ul>
      <li>Brief methodology point</li>
    </ul>
  </div>
</div>
```

### 4. 生成 Visual Elements

**创建 HTML 前，生成所有 visual elements：**

```bash
# Create figures directory
mkdir -p figures

# Hero image - SIMPLE, impactful
python scripts/generate_schematic.py "POSTER FORMAT for A0. Hero banner: '[TOPIC]' in HUGE text (120pt+). Dark blue gradient background. ONE iconic visual. Minimal text. Readable from 15 feet." -o figures/hero.png

# Introduction visual - ONLY 3 elements
python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE visual with ONLY 3 icons: [icon1] → [icon2] → [icon3]. ONE word labels (80pt+). 50% white space. Readable from 8 feet." -o figures/intro.png

# Methods flowchart - ONLY 4 steps
python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE flowchart with ONLY 4 boxes: STEP1 → STEP2 → STEP3 → STEP4. GIANT labels (100pt+). Thick arrows. 50% white space. NO sub-steps." -o figures/workflow.png

# Results visualization - ONLY 3 bars
python scripts/generate_schematic.py "POSTER FORMAT for A0. SIMPLE bar chart with ONLY 3 bars: BASELINE (70%), EXISTING (85%), OURS (95%). GIANT percentages ON bars (120pt+). NO axis, NO legend. 50% white space." -o figures/results.png

# Conclusions - EXACTLY 3 key findings
python scripts/generate_schematic.py "POSTER FORMAT for A0. EXACTLY 3 cards: '95%' (150pt) 'ACCURACY' (60pt), '2X' (150pt) 'FASTER' (60pt), checkmark 'READY' (60pt). 50% white space. NO other text." -o figures/conclusions.png
```

---

## PPTX Poster Creation Workflow

### 阶段 1：Planning

1. **确认已明确请求 PPTX**
2. **确定 poster requirements：**
   - Size：36×48 inches（最常见）或 A0
   - Orientation：Portrait（最常见）
3. **制定 content outline：**
   - 识别 1-3 个 core messages
   - 规划 3-5 个 visual elements
   - 起草最少 text（总计 300-800 words）

### 阶段 2：生成 Visual Elements（AI-Powered）

**关键：生成 SIMPLE figures，内容最少化。**

```bash
mkdir -p figures

# Generate each element with POSTER FORMAT specifications
# (See examples in Section 4 above)
```

### 阶段 3：创建 HTML Poster

1. **复制 template：**
   ```bash
   cp skills/pptx-posters/assets/poster_html_template.html poster.html
   ```

2. **更新 content：**
   - 替换 placeholder title 和 authors
   - 插入 AI-generated images
   - 添加最少 supporting text
   - 更新 references 和 contact info

3. **在 browser 中预览：**
   ```bash
   open poster.html  # macOS
   # or
   xdg-open poster.html  # Linux
   ```

### 阶段 4：导出为 PDF

**Browser Print Method：**
1. 在 Chrome 或 Firefox 中打开 poster.html
2. Print（Cmd/Ctrl + P）
3. 选择 "Save as PDF"
4. 将 paper size 设置为匹配 poster dimensions
5. 移除 margins
6. 启用 "Background graphics"

**Command Line（如果 Chrome 可用）：**
```bash
# Chrome headless PDF export
google-chrome --headless --print-to-pdf=poster.pdf \
  --print-to-pdf-no-header \
  --no-margins \
  poster.html
```

### 阶段 5：转换为 PPTX（如需要）

**Option 1：PDF to PPTX conversion**
```bash
# Using LibreOffice
libreoffice --headless --convert-to pptx poster.pdf

# Or use online converters for simple cases
```

**Option 2：使用 python-pptx 直接创建 PPTX**
```python
from pptx import Presentation
from pptx.util import Inches, Pt

prs = Presentation()
prs.slide_width = Inches(48)
prs.slide_height = Inches(36)

slide = prs.slides.add_slide(prs.slide_layouts[6])  # Blank

# Add images from figures/
slide.shapes.add_picture("figures/hero.png", Inches(0), Inches(0), width=Inches(48))
# ... add other elements

prs.save("poster.pptx")
```

---

## HTML Template Structure

提供的 template（`assets/poster_html_template.html`）包括：

### 用于 Customization 的 CSS Variables

```css
/* Poster dimensions */
body {
  width: 2592pt;   /* 36 inches */
  height: 3456pt;  /* 48 inches */
}

/* Color scheme - customize these */
.header {
  background: linear-gradient(135deg, #1a365d 0%, #2b6cb0 50%, #3182ce 100%);
}

/* Typography */
.poster-title { font-size: 108pt; }
.authors { font-size: 48pt; }
.block-title { font-size: 52pt; }
.block-content { font-size: 34pt; }
```

### Key Classes

| Class | 用途 | Font Size |
|-------|---------|-----------|
| `.poster-title` | Main title | 108pt |
| `.authors` | Author names | 48pt |
| `.affiliations` | Institutions | 38pt |
| `.block-title` | Section headers | 52pt |
| `.block-content` | Body text | 34pt |
| `.key-finding` | Highlight box | 36pt |

---

## Quality Checklist

### Step 0：Pre-Generation Review（强制）

**对每个 planned graphic，验证：**
- [ ] 能否用 3-4 items 或更少描述？（不是 5+）
- [ ] 是否是 simple workflow（3-4 steps，不是 7+）？
- [ ] 是否能用 10 words 或更少描述所有 text？
- [ ] 是否只传达 ONE message（不是多个）？

**拒绝这些 patterns：**
- ❌ "7-stage workflow" → Simplify to "3 mega-stages"
- ❌ "Multiple case studies" → One case per graphic
- ❌ "Timeline 2015-2024 annual" → "ONLY 3 key years"
- ❌ "Compare 6 methods" → "ONLY 2: ours vs best"

### Step 2b：Post-Generation Review（强制）

**对每个 generated figure，在 25% zoom 下检查：**

**✅ PASS criteria（全部必须为真）：**
- [ ] 能清楚读取所有 text
- [ ] Count：3-4 elements 或更少
- [ ] White space：50%+ empty
- [ ] 2 秒内理解
- [ ] 不是复杂的 5+ stage workflow
- [ ] 没有 multiple nested sections

**❌ FAIL criteria（任一为真则 regenerate）：**
- [ ] Text small/hard to read → Regenerate with "150pt+"
- [ ] More than 4 elements → Regenerate "ONLY 3 elements"
- [ ] Less than 50% white space → Regenerate "60% white space"
- [ ] Complex multi-stage → SPLIT into 2-3 graphics
- [ ] Multiple cases cramped → SPLIT into separate graphics

### Export 后

- [ ] 4 条边任意位置都没有 content cut off（仔细检查）
- [ ] 所有 images 正确显示
- [ ] Colors 按预期渲染
- [ ] Text 在 25% scale 下可读
- [ ] Graphics 看起来 SIMPLE（不像复杂 7-stage workflows）

---

## 需要避免的常见陷阱

**AI-Generated Graphics Mistakes：**
- ❌ elements 太多（10+ items）→ 最多保持 3-5 个
- ❌ Text 太小 → 在 prompts 中指定 "GIANT (100pt+)"
- ❌ 没有 white space → 每个 prompt 都添加 "50% white space"
- ❌ 复杂 flowcharts（8+ steps）→ 限制为 4-5 steps

**HTML/Export Mistakes：**
- ❌ Content 超出 poster dimensions → 在 browser 中检查 overflow
- ❌ PDF 中缺少 background graphics → 在 print settings 中启用
- ❌ PDF paper size 错误 → 精确匹配 poster dimensions
- ❌ Low-resolution images → 使用最低 300 DPI

**Content Mistakes：**
- ❌ Text 太多（超过 1000 words）→ 削减到 300-800 words
- ❌ Sections 太多（7+）→ 合并到 5-6 个
- ❌ 没有清楚 visual hierarchy → 突出 key findings

---

## 与其他 Skills 的集成

此 skill 可与以下配合：
- **Scientific Schematics**：生成所有 poster diagrams 和 flowcharts
- **Generate Image / Nano Banana Pro**：创建 stylized graphics 和 hero images
- **LaTeX Posters**：poster creation 的默认 skill（除非明确请求 PPTX，否则用它）

---

## Template Assets

位于 `assets/` directory：

- `poster_html_template.html`：Main HTML poster template（36×48 inches）
- `poster_quality_checklist.md`：Pre-submission validation checklist

## 参考资料

位于 `references/` directory：

- `poster_content_guide.md`：Content organization 和 writing guidelines
- `poster_design_principles.md`：Typography、color theory 和 visual hierarchy
- `poster_layout_design.md`：Layout principles 和 grid systems
