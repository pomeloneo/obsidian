---
name: pptx
description: "只要以任何方式涉及 .pptx file（作为 input、output 或两者兼有），都使用此 skill。这包括：创建 slide decks、pitch decks 或 presentations；读取、解析或从任何 .pptx file 提取 text（即使提取内容之后用于 email 或 summary 等其他地方）；编辑、修改或更新现有 presentations；合并或拆分 slide files；处理 templates、layouts、speaker notes 或 comments。只要用户提到 \"deck,\" \"slides,\" \"presentation,\" 或引用 .pptx 文件名，无论之后计划如何使用内容，都触发此 skill。如果 .pptx file 需要打开、创建或触碰，就使用此 skill。"
license: Proprietary. LICENSE.txt has complete terms
---

# PPTX Skill

## 快速参考

| 任务 | Guide |
|------|-------|
| 读取/分析 content | `python -m markitdown presentation.pptx` |
| 从 template 编辑或创建 | 阅读 [editing.md](editing.md) |
| 从零创建 | 阅读 [pptxgenjs.md](pptxgenjs.md) |

---

## 读取 Content

```bash
# Text extraction
python -m markitdown presentation.pptx

# Visual overview
python scripts/thumbnail.py presentation.pptx

# Raw XML
python scripts/office/unpack.py presentation.pptx unpacked/
```

---

## Editing Workflow

**完整细节请阅读 [editing.md](editing.md)。**

1. 使用 `thumbnail.py` 分析 template
2. Unpack → manipulate slides → edit content → clean → pack

---

## 从零创建

**完整细节请阅读 [pptxgenjs.md](pptxgenjs.md)。**

当没有 template 或 reference presentation 可用时使用。

---

## Design Ideas

**不要创建无聊的 slides。** 白底普通 bullets 不会打动任何人。为每张 slide 考虑此列表中的 ideas。

### 开始前

- **选择大胆且由内容驱动的 color palette**：palette 应该感觉是为当前主题设计的。如果把你的 colors 换到完全不同的 presentation 里仍然“可用”，说明选择还不够具体。
- **Dominance over equality**：一个 color 应占主导（60-70% visual weight），配 1-2 个 supporting tones 和一个鲜明 accent。不要让所有 colors 权重相等。
- **Dark/light contrast**：title + conclusion slides 用 dark backgrounds，content 用 light（"sandwich" structure）。也可以全程坚持 dark，以获得 premium feel。
- **坚持一个 visual motif**：选择一个 distinctive element 并重复使用，例如 rounded image frames、colored circles 中的 icons、thick single-side borders。贯穿每张 slide。

### Color Palettes

选择与主题匹配的 colors，不要默认 generic blue。使用这些 palettes 作为灵感：

| Theme | Primary | Secondary | Accent |
|-------|---------|-----------|--------|
| **Midnight Executive** | `1E2761` (navy) | `CADCFC` (ice blue) | `FFFFFF` (white) |
| **Forest & Moss** | `2C5F2D` (forest) | `97BC62` (moss) | `F5F5F5` (cream) |
| **Coral Energy** | `F96167` (coral) | `F9E795` (gold) | `2F3C7E` (navy) |
| **Warm Terracotta** | `B85042` (terracotta) | `E7E8D1` (sand) | `A7BEAE` (sage) |
| **Ocean Gradient** | `065A82` (deep blue) | `1C7293` (teal) | `21295C` (midnight) |
| **Charcoal Minimal** | `36454F` (charcoal) | `F2F2F2` (off-white) | `212121` (black) |
| **Teal Trust** | `028090` (teal) | `00A896` (seafoam) | `02C39A` (mint) |
| **Berry & Cream** | `6D2E46` (berry) | `A26769` (dusty rose) | `ECE2D0` (cream) |
| **Sage Calm** | `84B59F` (sage) | `69A297` (eucalyptus) | `50808E` (slate) |
| **Cherry Bold** | `990011` (cherry) | `FCF6F5` (off-white) | `2F3C7E` (navy) |

### 对每张 Slide

**每张 slide 都需要 visual element** — image、chart、icon 或 shape。Text-only slides 容易被遗忘。

**Layout options：**
- Two-column（text left，illustration on right）
- Icon + text rows（colored circle 中的 icon、bold header、下方 description）
- 2x2 或 2x3 grid（一侧 image，另一侧 content blocks grid）
- Half-bleed image（完整左侧或右侧）加 content overlay

**Data display：**
- Large stat callouts（60-72pt big numbers，下方 small labels）
- Comparison columns（before/after、pros/cons、side-by-side options）
- Timeline 或 process flow（numbered steps、arrows）

**Visual polish：**
- section headers 旁边 small colored circles 中的 icons
- key stats 或 taglines 使用 italic accent text

### Typography

**选择有趣的 font pairing**，不要默认 Arial。选择有个性的 header font，并搭配干净的 body font。

| Header Font | Body Font |
|-------------|-----------|
| Georgia | Calibri |
| Arial Black | Arial |
| Calibri | Calibri Light |
| Cambria | Calibri |
| Trebuchet MS | Calibri |
| Impact | Arial |
| Palatino | Garamond |
| Consolas | Calibri |

| Element | Size |
|---------|------|
| Slide title | 36-44pt bold |
| Section header | 20-24pt bold |
| Body text | 14-16pt |
| Captions | 10-12pt muted |

### Spacing

- 最小 0.5" margins
- content blocks 之间 0.3-0.5"
- 留出 breathing room，不要填满每一寸

### 避免（Common Mistakes）

- **不要重复同一 layout** — 在 slides 中变化 columns、cards 和 callouts
- **不要居中 body text** — paragraphs 和 lists 左对齐；只居中 titles
- **不要吝惜 size contrast** — titles 需要 36pt+，才能从 14-16pt body 中突出
- **不要默认使用蓝色** — 选择能反映具体主题的 colors
- **不要随机混用 spacing** — 选择 0.3" 或 0.5" gaps 并一致使用
- **不要只设计一张 slide 而其他保持 plain** — 要么完全投入，要么全程保持简单
- **不要创建 text-only slides** — 添加 images、icons、charts 或 visual elements；避免普通 title + bullets
- **不要忘记 text box padding** — 将 lines 或 shapes 与 text edges 对齐时，在 text box 上设置 `margin: 0`，或偏移 shape 以考虑 padding
- **不要使用 low-contrast elements** — icons 和 text 都需要与 background 有强 contrast；避免 light backgrounds 上的 light text，或 dark backgrounds 上的 dark text
- **绝不要在 titles 下使用 accent lines** — 这是 AI-generated slides 的典型特征；改用 whitespace 或 background color

---

## QA（必需）

**假设存在问题。你的工作是找到它们。**

第一次 render 几乎不会完全正确。把 QA 当作 bug hunt，而不是确认步骤。如果第一次检查发现零问题，说明看得还不够仔细。

### Content QA

```bash
python -m markitdown output.pptx
```

检查 missing content、typos、wrong order。

**使用 templates 时，检查残留 placeholder text：**

```bash
python -m markitdown output.pptx | grep -iE "xxxx|lorem|ipsum|this.*(page|slide).*layout"
```

如果 grep 返回结果，在宣布成功前修复它们。

### Visual QA

**⚠️ 使用 SUBAGENTS** — 即使只有 2-3 张 slides。你已经盯着代码看太久，会看到自己预期的东西，而不是实际存在的问题。Subagents 有 fresh eyes。

将 slides 转为 images（见 [Converting to Images](#converting-to-images)），然后使用此 prompt：

```
Visually inspect these slides. Assume there are issues — find them.

Look for:
- Overlapping elements (text through shapes, lines through words, stacked elements)
- Text overflow or cut off at edges/box boundaries
- Decorative lines positioned for single-line text but title wrapped to two lines
- Source citations or footers colliding with content above
- Elements too close (< 0.3" gaps) or cards/sections nearly touching
- Uneven gaps (large empty area in one place, cramped in another)
- Insufficient margin from slide edges (< 0.5")
- Columns or similar elements not aligned consistently
- Low-contrast text (e.g., light gray text on cream-colored background)
- Low-contrast icons (e.g., dark icons on dark backgrounds without a contrasting circle)
- Text boxes too narrow causing excessive wrapping
- Leftover placeholder content

For each slide, list issues or areas of concern, even if minor.

Read and analyze these images:
1. /path/to/slide-01.jpg (Expected: [brief description])
2. /path/to/slide-02.jpg (Expected: [brief description])

Report ALL issues found, including minor ones.
```

### Verification Loop

1. Generate slides → Convert to images → Inspect
2. **List issues found**（如果没有发现，再更严格地看一遍）
3. Fix issues
4. **Re-verify affected slides** — 一个修复常常会产生另一个问题
5. 重复直到完整检查不再发现新问题

**在至少完成一次 fix-and-verify cycle 前，不要宣布成功。**

---

## Converting to Images

将 presentations 转换为单独 slide images，以便 visual inspection：

```bash
python scripts/office/soffice.py --headless --convert-to pdf output.pptx
pdftoppm -jpeg -r 150 output.pdf slide
```

这会创建 `slide-01.jpg`、`slide-02.jpg` 等。

修复后如需重新 render 特定 slides：

```bash
pdftoppm -jpeg -r 150 -f N -l N output.pdf slide-fixed
```

---

## Dependencies

- `pip install "markitdown[pptx]"` - text extraction
- `pip install Pillow` - thumbnail grids
- `npm install -g pptxgenjs` - creating from scratch
- LibreOffice（`soffice`）- PDF conversion（通过 `scripts/office/soffice.py` 为 sandboxed environments 自动配置）
- Poppler（`pdftoppm`）- PDF to images
