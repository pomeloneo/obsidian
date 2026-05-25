---
name: scientific-schematics
description: 使用 Nano Banana 2 AI 和智能 iterative refinement 创建 publication-quality scientific diagrams。使用 Gemini 3.1 Pro Preview 进行 quality review。仅当质量低于你的 document type threshold 时重新生成。专长于 neural network architectures、system diagrams、flowcharts、biological pathways 和 complex scientific visualizations。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scientific Schematics and Diagrams

## 概述

Scientific schematics 和 diagrams 将复杂概念转化为适合发表的清晰 visual representations。**此 skill 使用 Nano Banana 2 AI 生成 diagrams，并用 Gemini 3.1 Pro Preview 做 quality review。**

**工作方式：**
- 用自然语言描述 diagram
- Nano Banana 2 自动生成 publication-quality images
- **Gemini 3.1 Pro Preview 会根据 document-type thresholds 审查质量**
- **Smart iteration**：仅当质量低于 threshold 时重新生成
- 几分钟内获得 publication-ready output
- 不需要 coding、templates 或手工绘图

**按 Document Type 的 Quality Thresholds：**
| Document Type | Threshold | Description |
|---------------|-----------|-------------|
| journal | 8.5/10 | Nature、Science、peer-reviewed journals |
| conference | 8.0/10 | Conference papers |
| thesis | 8.0/10 | Dissertations、theses |
| grant | 8.0/10 | Grant proposals |
| preprint | 7.5/10 | arXiv、bioRxiv 等 |
| report | 7.5/10 | Technical reports |
| poster | 7.0/10 | Academic posters |
| presentation | 6.5/10 | Slides、talks |
| default | 7.5/10 | General purpose |

**只需描述你想要的内容，Nano Banana 2 就会创建它。** 所有 diagrams 都存储在 figures/ 子文件夹，并在 papers/posters 中引用。

## 快速开始：生成任意 Diagram

只需描述 diagram，即可创建任意 scientific diagram。Nano Banana 2 会通过 **smart iteration** 自动处理所有步骤：

```bash
# Generate for journal paper (highest quality threshold: 8.5/10)
python scripts/generate_schematic.py "CONSORT participant flow diagram with 500 screened, 150 excluded, 350 randomized" -o figures/consort.png --doc-type journal

# Generate for presentation (lower threshold: 6.5/10 - faster)
python scripts/generate_schematic.py "Transformer encoder-decoder architecture showing multi-head attention" -o figures/transformer.png --doc-type presentation

# Generate for poster (moderate threshold: 7.0/10)
python scripts/generate_schematic.py "MAPK signaling pathway from EGFR to gene transcription" -o figures/mapk_pathway.png --doc-type poster

# Custom max iterations (max 2)
python scripts/generate_schematic.py "Complex circuit diagram with op-amp, resistors, and capacitors" -o figures/circuit.png --iterations 2 --doc-type journal
```

**幕后发生的步骤：**
1. **Generation 1**：Nano Banana 2 遵循 scientific diagram best practices 创建初始 image
2. **Review 1**：**Gemini 3.1 Pro Preview** 根据 document-type threshold 评估质量
3. **Decision**：如果 quality >= threshold → **DONE**（不需要更多 iterations）
4. **若低于 threshold**：基于 critique 改进 prompt 并重新生成
5. **Repeat**：直到质量达到 threshold 或达到 max iterations

**Smart Iteration Benefits：**
- ✅ 如果第一次 generation 足够好，可节省 API calls
- ✅ Journal papers 使用更高 quality standards
- ✅ Presentations/posters turnaround 更快
- ✅ 为每种 use case 匹配合适质量

**Output**：Versioned images，加上包含 quality scores、critiques 和 early-stop information 的详细 review log。

### Configuration

设置 OpenRouter API key：
```bash
export OPENROUTER_API_KEY='your_api_key_here'
```

获取 API key：https://openrouter.ai/keys

### AI Generation Best Practices

**Scientific Diagrams 的有效 Prompts：**

✓ **Good prompts**（具体、详细）：
- "CONSORT flowchart showing participant flow from screening (n=500) through randomization to final analysis"
- "Transformer neural network architecture with encoder stack on left, decoder stack on right, showing multi-head attention and cross-attention connections"
- "Biological signaling cascade: EGFR receptor → RAS → RAF → MEK → ERK → nucleus, with phosphorylation steps labeled"
- "Block diagram of IoT system: sensors → microcontroller → WiFi module → cloud server → mobile app"

✗ **避免模糊 prompts**：
- "Make a flowchart"（过于泛泛）
- "Neural network"（哪种类型？哪些 components？）
- "Pathway diagram"（哪个 pathway？哪些 molecules？）

**需要包含的关键元素：**
- **Type**：Flowchart、architecture diagram、pathway、circuit 等
- **Components**：要包含的具体元素
- **Flow/Direction**：元素如何连接（left-to-right、top-to-bottom）
- **Labels**：关键 annotations 或 text
- **Style**：任何特定 visual requirements

**Scientific Quality Guidelines**（自动应用）：
- Clean white/light background
- High contrast 以保证 readability
- 清晰、可读 labels（minimum 10pt）
- Professional typography（sans-serif fonts）
- Colorblind-friendly colors（Okabe-Ito palette）
- 适当 spacing，防止 crowding
- 适用时包含 scale bars、legends、axes

## 何时使用此 Skill

在以下情况应使用此 skill：
- 创建 neural network architecture diagrams（Transformers、CNNs、RNNs 等）
- 展示 system architectures 和 data flow diagrams
- 为 study design 绘制 methodology flowcharts（CONSORT、PRISMA）
- 可视化 algorithm workflows 和 processing pipelines
- 创建 circuit diagrams 和 electrical schematics
- 描绘 biological pathways 和 molecular interactions
- 生成 network topologies 和 hierarchical structures
- 展示 conceptual frameworks 和 theoretical models
- 为 technical papers 设计 block diagrams

## 如何使用此 Skill

**只需用自然语言描述 diagram。** Nano Banana 2 会自动生成：

```bash
python scripts/generate_schematic.py "your diagram description" -o output.png
```

**就这样。** AI 会处理：
- ✓ Layout and composition
- ✓ Labels and annotations
- ✓ Colors and styling
- ✓ Quality review and refinement
- ✓ Publication-ready output

**适用于所有 diagram types：**
- Flowcharts（CONSORT、PRISMA 等）
- Neural network architectures
- Biological pathways
- Circuit diagrams
- System architectures
- Block diagrams
- 任意 scientific visualization

**无需 coding、templates 或手工绘图。**

---

# AI Generation Mode（Nano Banana 2 + Gemini 3.1 Pro Preview Review）

## Smart Iterative Refinement Workflow

AI generation system 使用 **smart iteration**：只有当 quality 低于你的 document type threshold 时才重新生成。

### Smart Iteration 的工作方式

```
┌─────────────────────────────────────────────────────┐
│  1. Generate image with Nano Banana 2             │
│                    ↓                                │
│  2. Review quality with Gemini 3.1 Pro Preview                │
│                    ↓                                │
│  3. Score >= threshold?                             │
│       YES → DONE! (early stop)                      │
│       NO  → Improve prompt, go to step 1            │
│                    ↓                                │
│  4. Repeat until quality met OR max iterations      │
└─────────────────────────────────────────────────────┘
```

### Iteration 1: Initial Generation
**Prompt Construction：**
```
Scientific diagram guidelines + User request
```

**Output：** `diagram_v1.png`

### Quality Review by Gemini 3.1 Pro Preview

Gemini 3.1 Pro Preview 从以下方面评估 diagram：
1. **Scientific Accuracy**（0-2 分）- 概念、notation、relationships 正确
2. **Clarity and Readability**（0-2 分）- 易理解，hierarchy 清晰
3. **Label Quality**（0-2 分）- labels 完整、可读、一致
4. **Layout and Composition**（0-2 分）- logical flow、balanced、无 overlaps
5. **Professional Appearance**（0-2 分）- publication-ready quality

**Example Review Output：**
```
SCORE: 8.0

STRENGTHS:
- Clear flow from top to bottom
- All phases properly labeled
- Professional typography

ISSUES:
- Participant counts slightly small
- Minor overlap on exclusion box

VERDICT: ACCEPTABLE (for poster, threshold 7.0)
```

### Decision Point: Continue or Stop?

| If Score... | Action |
|-------------|--------|
| >= threshold | **STOP** - 对此 document type 已经足够好 |
| < threshold | 使用改进 prompt 进入下一 iteration |

**Example：**
- 对 **poster**（threshold 7.0）：Score 7.5 → **1 次 iteration 后 DONE**
- 对 **journal**（threshold 8.5）：Score 7.5 → 继续改进

### Subsequent Iterations（仅在需要时）

如果 quality 低于 threshold，系统会：
1. 从 Gemini 3.1 Pro Preview 的 review 中提取具体 issues
2. 用 improvement instructions 增强 prompt
3. 用 Nano Banana 2 重新生成
4. 再次用 Gemini 3.1 Pro Preview 审查
5. 重复直到达到 threshold 或 max iterations

### Review Log
所有 iterations 都会保存到一个 JSON review log，其中包含 early-stop information：
```json
{
  "user_prompt": "CONSORT participant flow diagram...",
  "doc_type": "poster",
  "quality_threshold": 7.0,
  "iterations": [
    {
      "iteration": 1,
      "image_path": "figures/consort_v1.png",
      "score": 7.5,
      "needs_improvement": false,
      "critique": "SCORE: 7.5\nSTRENGTHS:..."
    }
  ],
  "final_score": 7.5,
  "early_stop": true,
  "early_stop_reason": "Quality score 7.5 meets threshold 7.0 for poster"
}
```

**注意：** 使用 smart iteration 时，如果早期达到质量要求，可能只看到 1 次 iteration，而不是完整 2 次。

## Advanced AI Generation Usage

### Python API

```python
from scripts.generate_schematic_ai import ScientificSchematicGenerator

# Initialize generator
generator = ScientificSchematicGenerator(
    api_key="your_openrouter_key",
    verbose=True
)

# Generate with iterative refinement (max 2 iterations)
results = generator.generate_iterative(
    user_prompt="Transformer architecture diagram",
    output_path="figures/transformer.png",
    iterations=2
)

# Access results
print(f"Final score: {results['final_score']}/10")
print(f"Final image: {results['final_image']}")

# Review individual iterations
for iteration in results['iterations']:
    print(f"Iteration {iteration['iteration']}: {iteration['score']}/10")
    print(f"Critique: {iteration['critique']}")
```

### Command-Line Options

```bash
# Basic usage (default threshold 7.5/10)
python scripts/generate_schematic.py "diagram description" -o output.png

# Specify document type for appropriate quality threshold
python scripts/generate_schematic.py "diagram" -o out.png --doc-type journal      # 8.5/10
python scripts/generate_schematic.py "diagram" -o out.png --doc-type conference   # 8.0/10
python scripts/generate_schematic.py "diagram" -o out.png --doc-type poster       # 7.0/10
python scripts/generate_schematic.py "diagram" -o out.png --doc-type presentation # 6.5/10

# Custom max iterations (1-2)
python scripts/generate_schematic.py "complex diagram" -o diagram.png --iterations 2

# Verbose output (see all API calls and reviews)
python scripts/generate_schematic.py "flowchart" -o flow.png -v

# Provide API key via flag
python scripts/generate_schematic.py "diagram" -o out.png --api-key "sk-or-v1-..."

# Combine options
python scripts/generate_schematic.py "neural network" -o nn.png --doc-type journal --iterations 2 -v
```

### Prompt Engineering Tips

**1. 明确 Layout：**
```
✓ "Flowchart with vertical flow, top to bottom"
✓ "Architecture diagram with encoder on left, decoder on right"
✓ "Circular pathway diagram with clockwise flow"
```

**2. 包含 Quantitative Details：**
```
✓ "Neural network with input layer (784 nodes), hidden layer (128 nodes), output (10 nodes)"
✓ "Flowchart showing n=500 screened, n=150 excluded, n=350 randomized"
✓ "Circuit with 1kΩ resistor, 10µF capacitor, 5V source"
```

**3. 指定 Visual Style：**
```
✓ "Minimalist block diagram with clean lines"
✓ "Detailed biological pathway with protein structures"
✓ "Technical schematic with engineering notation"
```

**4. 要求 Specific Labels：**
```
✓ "Label all arrows with activation/inhibition"
✓ "Include layer dimensions in each box"
✓ "Show time progression with timestamps"
```

**5. 提及 Color Requirements：**
```
✓ "Use colorblind-friendly colors"
✓ "Grayscale-compatible design"
✓ "Color-code by function: blue for input, green for processing, red for output"
```

## AI Generation Examples

### Example 1: CONSORT Flowchart
```bash
python scripts/generate_schematic.py \
  "CONSORT participant flow diagram for randomized controlled trial. \
   Start with 'Assessed for eligibility (n=500)' at top. \
   Show 'Excluded (n=150)' with reasons: age<18 (n=80), declined (n=50), other (n=20). \
   Then 'Randomized (n=350)' splits into two arms: \
   'Treatment group (n=175)' and 'Control group (n=175)'. \
   Each arm shows 'Lost to follow-up' (n=15 and n=10). \
   End with 'Analyzed' (n=160 and n=165). \
   Use blue boxes for process steps, orange for exclusion, green for final analysis." \
  -o figures/consort.png
```

### Example 2: Neural Network Architecture
```bash
python scripts/generate_schematic.py \
  "Transformer encoder-decoder architecture diagram. \
   Left side: Encoder stack with input embedding, positional encoding, \
   multi-head self-attention, add & norm, feed-forward, add & norm. \
   Right side: Decoder stack with output embedding, positional encoding, \
   masked self-attention, add & norm, cross-attention (receiving from encoder), \
   add & norm, feed-forward, add & norm, linear & softmax. \
   Show cross-attention connection from encoder to decoder with dashed line. \
   Use light blue for encoder, light red for decoder. \
   Label all components clearly." \
  -o figures/transformer.png --iterations 2
```

### Example 3: Biological Pathway
```bash
python scripts/generate_schematic.py \
  "MAPK signaling pathway diagram. \
   Start with EGFR receptor at cell membrane (top). \
   Arrow down to RAS (with GTP label). \
   Arrow to RAF kinase. \
   Arrow to MEK kinase. \
   Arrow to ERK kinase. \
   Final arrow to nucleus showing gene transcription. \
   Label each arrow with 'phosphorylation' or 'activation'. \
   Use rounded rectangles for proteins, different colors for each. \
   Include membrane boundary line at top." \
  -o figures/mapk_pathway.png
```

### Example 4: System Architecture
```bash
python scripts/generate_schematic.py \
  "IoT system architecture block diagram. \
   Bottom layer: Sensors (temperature, humidity, motion) in green boxes. \
   Middle layer: Microcontroller (ESP32) in blue box. \
   Connections to WiFi module (orange box) and Display (purple box). \
   Top layer: Cloud server (gray box) connected to mobile app (light blue box). \
   Show data flow arrows between all components. \
   Label connections with protocols: I2C, UART, WiFi, HTTPS." \
  -o figures/iot_architecture.png
```

---

## Command-Line Usage

生成 scientific schematics 的主要入口：

```bash
# Basic usage
python scripts/generate_schematic.py "diagram description" -o output.png

# Custom iterations (max 2)
python scripts/generate_schematic.py "complex diagram" -o diagram.png --iterations 2

# Verbose mode
python scripts/generate_schematic.py "diagram" -o out.png -v
```

**注意：** Nano Banana 2 AI generation system 在 iterative refinement process 中包含 automatic quality review。每次 iteration 都会评估 scientific accuracy、clarity 和 accessibility。

## Best Practices Summary

### Design Principles

1. **Clarity over complexity** - 简化并移除不必要元素
2. **Consistent styling** - 使用 templates 和 style files
3. **Colorblind accessibility** - 使用 Okabe-Ito palette 和 redundant encoding
4. **Appropriate typography** - Sans-serif fonts，minimum 7-8 pt
5. **Vector format** - Publication 始终使用 PDF/SVG

### Technical Requirements

1. **Resolution** - 优先 vector，或 raster 使用 300+ DPI
2. **File format** - LaTeX 用 PDF，web 用 SVG，PNG 作为 fallback
3. **Color space** - Digital 用 RGB，print 用 CMYK（需要时转换）
4. **Line weights** - Minimum 0.5 pt，典型 1-2 pt
5. **Text size** - Final size 下 minimum 7-8 pt

### Integration Guidelines

1. **Include in LaTeX** - 对生成 images 使用 `\includegraphics{}`
2. **Caption thoroughly** - 描述所有 elements 和 abbreviations
3. **Reference in text** - 在 narrative flow 中解释 diagram
4. **Maintain consistency** - Paper 中所有 figures 保持同一 style
5. **Version control** - 将 prompts 和 generated images 保存在 repository

## Troubleshooting Common Issues

### AI Generation Issues

**Problem**：Text 或 elements overlap
- **Solution**：AI generation 会自动处理 spacing
- **Solution**：提高 iterations：`--iterations 2` 以获得更好 refinement

**Problem**：Elements 连接不正确
- **Solution**：让 prompt 对 connections 和 layout 更具体
- **Solution**：增加 iterations 以获得更好 refinement

### Image Quality Issues

**Problem**：Export quality poor
- **Solution**：AI generation 会自动生成 high-quality images
- **Solution**：增加 iterations 获得更好结果：`--iterations 2`

**Problem**：生成后 elements overlap
- **Solution**：AI generation 会自动处理 spacing
- **Solution**：增加 iterations：`--iterations 2` 以获得更好 refinement
- **Solution**：让 prompt 对 layout 和 spacing requirements 更具体

### Quality Check Issues

**Problem**：False positive overlap detection
- **Solution**：调整 threshold：`detect_overlaps(image_path, threshold=0.98)`
- **Solution**：在 visual report 中手动 review flagged regions

**Problem**：Generated image quality is low
- **Solution**：AI generation 默认生成 high-quality images
- **Solution**：增加 iterations 获得更好结果：`--iterations 2`

**Problem**：Colorblind simulation shows poor contrast
- **Solution**：在 code 中显式切换到 Okabe-Ito palette
- **Solution**：添加 redundant encoding（shapes、patterns、line styles）
- **Solution**：增加 color saturation 和 lightness differences

**Problem**：High-severity overlaps detected
- **Solution**：查看 overlap_report.json 获取 exact positions
- **Solution**：增加这些 specific regions 的 spacing
- **Solution**：使用调整后的参数重新运行并再次 verify

**Problem**：Visual report generation fails
- **Solution**：检查 Pillow 和 matplotlib installations
- **Solution**：确保 image file 可读：`Image.open(path).verify()`
- **Solution**：检查是否有足够 disk space 生成 report

### Accessibility Problems

**Problem**：Colors 在 grayscale 中不可区分
- **Solution**：运行 accessibility checker：`verify_accessibility(image_path)`
- **Solution**：添加 patterns、shapes 或 line styles 作为 redundancy
- **Solution**：增加 adjacent elements 间的 contrast

**Problem**：打印时 text 太小
- **Solution**：运行 resolution validator：`validate_resolution(image_path)`
- **Solution**：按 final size 设计，使用 minimum 7-8 pt fonts
- **Solution**：在 resolution report 中检查 physical dimensions

**Problem**：Accessibility checks 持续失败
- **Solution**：查看 accessibility_report.json 获取具体 failures
- **Solution**：将 color contrast 至少提高 20%
- **Solution**：Finalizing 前用实际 grayscale conversion 测试

## Resources and References

### Detailed References

加载这些文件以获取特定主题的完整信息：

- **`references/best_practices.md`** - Publication standards 和 accessibility guidelines

### External Resources

**Python Libraries**
- Schemdraw Documentation: https://schemdraw.readthedocs.io/
- NetworkX Documentation: https://networkx.org/documentation/
- Matplotlib Documentation: https://matplotlib.org/

**Publication Standards**
- Nature Figure Guidelines: https://www.nature.com/nature/for-authors/final-submission
- Science Figure Guidelines: https://www.science.org/content/page/instructions-preparing-initial-manuscript
- CONSORT Diagram: http://www.consort-statement.org/consort-statement/flow-diagram

## 与其他 Skills 的集成

此 skill 可与以下 skill 协同使用：

- **Scientific Writing** - Diagrams 遵循 figure best practices
- **Scientific Visualization** - 共享 color palettes 和 styling
- **LaTeX Posters** - 为 poster presentations 生成 diagrams
- **Research Grants** - 为 proposals 生成 methodology diagrams
- **Peer Review** - 评估 diagram clarity 和 accessibility

## Quick Reference Checklist

提交 diagrams 前验证：

### Visual Quality
- [ ] High-quality image format（AI generation 输出 PNG）
- [ ] 无 overlapping elements（AI 自动处理）
- [ ] 所有 components 间 spacing 充分（AI 优化）
- [ ] Clean、professional alignment
- [ ] 所有 arrows 正确连接到 intended targets

### Accessibility
- [ ] 使用 colorblind-safe palette（Okabe-Ito）
- [ ] Grayscale 中可用（用 accessibility checker 测试）
- [ ] Elements 间 contrast 充分（已验证）
- [ ] 适当使用 redundant encoding（shapes + colors）
- [ ] Colorblind simulation 通过所有 checks

### Typography and Readability
- [ ] Final size 下 text minimum 7-8 pt
- [ ] 所有 elements 清晰、完整标注
- [ ] Font family 和 sizing 一致
- [ ] 无 text overlaps 或 cutoffs
- [ ] 适用时包含 units

### Publication Standards
- [ ] 与 manuscript 中其他 figures 保持 consistent styling
- [ ] Caption 完整，所有 abbreviations 已定义
- [ ] 在 manuscript text 中适当引用
- [ ] 满足 journal-specific dimension requirements
- [ ] 按 journal 要求导出格式（PDF/EPS/TIFF）

### Quality Verification（Required）
- [ ] 运行 `run_quality_checks()` 并达到 PASS status
- [ ] 审查 overlap detection report（zero high-severity overlaps）
- [ ] 通过 accessibility verification（grayscale 和 colorblind）
- [ ] Target DPI 下 resolution validated（print 为 300+）
- [ ] Visual quality report 已生成并审查
- [ ] 所有 quality reports 与 figure files 一起保存

### Documentation and Version Control
- [ ] Source files（.tex、.py）已保存，便于 future revision
- [ ] Quality reports 已归档到 `quality_reports/` directory
- [ ] Configuration parameters 已记录（colors、spacing、sizes）
- [ ] Git commit 包含 source、output 和 quality reports
- [ ] README 或 comments 解释如何 regenerate figure

### Final Integration Check
- [ ] Figure 在 compiled manuscript 中显示正确
- [ ] Cross-references 正常（`\ref{}` 指向正确 figure）
- [ ] Figure number 与 text citations 匹配
- [ ] Caption 出现在相对 figure 正确的页面
- [ ] 无与 figure 相关的 compilation warnings 或 errors

## Environment Setup

```bash
# Required
export OPENROUTER_API_KEY='your_api_key_here'

# Get key at: https://openrouter.ai/keys
```

## Getting Started

**最简单用法：**
```bash
python scripts/generate_schematic.py "your diagram description" -o output.png
```

---

使用此 skill 创建清晰、accessible、publication-quality diagrams，以有效传达复杂 scientific concepts。带 iterative refinement 的 AI-powered workflow 可确保 diagrams 符合 professional standards。
