---
name: venue-templates
description: 访问主要科学出版场所（Nature、Science、PLOS、IEEE、ACM）、学术会议（NeurIPS、ICML、 CVPR、CHI）、研究海报和拨款提案（NSF、NIH、DOE、DARPA）。在准备期刊投稿、会议论文、研究海报或拨款提案的手稿并需要特定于场地的格式要求和模板时，应使用此技能。
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# 场地模板

## 概述

访问主要科学出版场所、学术会议、研究海报和资助提案的全面 LaTeX 模板、格式要求和提交指南。该技能为跨学科的成功学术提交提供了即用型模板和详细规范。

在准备期刊投稿、会议论文、研究海报或资助提案的手稿并需要特定于场地的格式要求和模板时，请使用此技能。

## 何时使用此技能

该技能应该在以下情况下使用：
- 准备稿件以提交给特定期刊（Nature、Science、PLOS、IEEE 等）
- 撰写具有特定格式要求的会议论文（NeurIPS、ICML、CHI 等）
- 为会议制作学术研究海报
- 为联邦机构（NSF、NIH、DOE、DARPA）或私人基金会起草拨款提案
- 检查目标场地的格式要求和页面限制
- 使用作者信息和项目详细信息自定义模板
- 验证文件是否符合场地规格

## 通过scientific-schematics增强视觉效果

**使用此技能创建文档时，请始终考虑添加科学图表和原理图以增强视觉传达。**

如果您的文档尚未包含原理图或图表：
- 使用**scientific-schematics**技能生成AI驱动的出版质量图表
- 用自然语言简单描述您想要的图表
- Nano Banana Pro 将自动生成、审查和完善原理图

**对于新文档：** 默认情况下应生成scientific-schematics，以直观地表示文本中描述的关键概念、工作流程、架构或关系。

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
- 论文方法流程图
- 概念框架图
- 系统架构插图
- 数据流程图
- 实验设计可视化
- 研究工作流程图
- 任何受益于可视化的复杂概念

有关创建原理图的详细指导，请参阅scientific-schematics技能文档。

---

## 核心能力

### 1.期刊文章模板

访问 50 多种跨学科主要科学期刊的 LaTeX 模板和格式指南：

**Nature 投资组合**：
- Nature、Nature 方法、Nature 生物技术、Nature 机器智能
- Nature 通信、Nature 协议
- 科学报告

**Science 系列**：
- Science、Science 进展、Science 转化医学
- Science 免疫学，Science 机器人

**PLOS（Science 公共图书馆）**：
- PLOS ONE、PLOS 生物学、PLOS 计算生物学
- PLOS 医学、PLOS 遗传学

**Cell 按**：
- Cell，神经元，免疫，Cell 报告
- 分子 Cell，发育 Cell

**IEEE 出版物**：
- IEEE 交易（各学科）
- IEEE 访问、IEEE 日记模板

**ACM 出版物**：
- ACM ACM 的交易、通信
- ACM 会议记录

**其他主要出版商**：
- 施普林格期刊（各学科）
- 爱思唯尔期刊（自定义模板）
- 威利期刊
- BMC期刊
- 前沿期刊

### 2. 会议论文模板

针对主要学术会议具有正确格式的会议特定模板：

**机器学习和AI**：
- NeurIPS（神经信息处理系统）
- ICML（机器学习国际会议）
- ICLR（学习表示国际会议）
- CVPR（计算机视觉与模式识别）
- AAAI（AI促进协会）

**计算机 Science**：
- ACM CHI（人机交互）
- SIGKDD（知识发现和数据挖掘）
- EMNLP（自然语言处理中的经验方法）
- SIGIR（信息检索）
- USENIX 会议

**生物学与生物信息学**：
- ISMB（分子生物学智能系统）
- RECOMB（计算分子生物学研究）
- PSB（太平洋生物计算研讨会）

**工程**：
- IEEE会议模板（各学科）
- ASME、AIAA 会议

### 3.研究海报模板

会议演示的学术海报模板：

**标准格式**：
- A0（841 × 1189 毫米/33.1 × 46.8 英寸）
- A1（594 × 841 毫米/23.4 × 33.1 英寸）
- 36" × 48" (914 × 1219 mm) - 常见美国尺寸
- 42 英寸 × 56 英寸（1067 × 1422 毫米）
- 48" × 36"（横向）

**模板包**：
- **beamerposter**：经典学术海报模板
- **tikzposter**：现代、色彩缤纷的海报设计
- **baposter**：结构化多列布局

**设计特点**：
- 远距离可读的最佳字体大小
- 配色方案（色盲安全调色板）
- 网格布局和列结构
- 补充材料二维码集成

### 4. 拨款提案模板

主要资助机构的模板和格式要求：

**NSF（国家 Science 基金会）**：
- 完整提案模板（15 页项目描述）
- 项目摘要（1 页：概述、智力优点、更广泛的影响）
- 预算和预算理由
- 个人简介（限3页）
- 设施、设备和其他资源
- 数据管理计划

**NIH（美国国立卫生研究院）**：
- R01 研究补助金（多年）
- R21 探索/发展补助金
- K 奖（职业发展）
- 具体目标页面（1 页，最关键的组成部分）
- 研究策略（意义、创新、方法）
- 传记概要（限 5 页）

**DOE（能源部）**：
- Science提案办公室
- ARPA-E 模板
- 技术就绪级别 (TRL) 描述
- 商业化和影响部分

**DARPA（国防高级研究计划局）**：
- BAA（广泛机构公告）回应
- 海尔迈尔教义问答框架
- 技术方法和里程碑
- 过渡规划

**私人基金会**：
- 盖茨基金会
- 惠康信托
- 霍华德休斯医学研究所 (HHMI)
- 陈·扎克伯格倡议 (CZI)

## 工作流程：查找和使用模板

### 第 1 步：确定目标地点

确定具体的出版地点、会议或资助机构：

```
Example queries:
- "I need to submit to Nature"
- "What are the requirements for NeurIPS 2025?"
- "Show me NSF proposal formatting"
- "I'm creating a poster for ISMB"
```

### 第2步：查询模板和要求

访问特定于场地的模板和格式指南：

**对于期刊**：
```bash
# Load journal formatting requirements
Reference: references/journals_formatting.md
Search for: "Nature" or specific journal name

# Retrieve template
Template: assets/journals/nature_article.tex
```

**对于会议**：
```bash
# Load conference formatting
Reference: references/conferences_formatting.md
Search for: "NeurIPS" or specific conference

# Retrieve template
Template: assets/journals/neurips_article.tex
```

**对于海报**：
```bash
# Load poster guidelines
Reference: references/posters_guidelines.md

# Retrieve template
Template: assets/posters/beamerposter_academic.tex
```

**对于补助金**：
```bash
# Load grant requirements
Reference: references/grants_requirements.md
Search for: "NSF" or specific agency

# Retrieve template
Template: assets/grants/nsf_proposal_template.tex
```

### 第 3 步：查看格式要求

定制前检查关键规格：

**验证的关键要求**：
- 页数限制（因场地而异）
- 字体大小和系列
- 保证金规格
- 行距
- 引文样式（APA、Vancouver、Nature 等）
- 图/表要求
- 文件格式（PDF、Word、LaTeX 源）
- 匿名（用于双盲审核）
- 补充材料限制

### 第 4 步：自定义模板

使用帮助程序脚本或手动自定义：

**选项 1：辅助脚本（推荐）**：
```bash
python scripts/customize_template.py \
  --template assets/journals/nature_article.tex \
  --title "Your Paper Title" \
  --authors "First Author, Second Author" \
  --affiliations "University Name" \
  --output my_nature_paper.tex
```

**选项 2：手动编辑**：
- 打开模板文件
- 替换占位符文本（用注释标记）
- 填写标题、作者、单位、摘要
- 将您的内容添加到每个部分

### 第 5 步：验证格式

检查是否符合场地要求：

```bash
python scripts/validate_format.py \
  --file my_paper.pdf \
  --venue "Nature" \
  --check-all
```

**验证检查**：
- 页数在限制范围内
- 字体大小正确
- 边距符合规格
- 参考文献格式正确
- 数字满足分辨率要求

### 第 6 步：编译和审查

编译 LaTeX 并查看输出：

```bash
# Compile LaTeX
pdflatex my_paper.tex
bibtex my_paper
pdflatex my_paper.tex
pdflatex my_paper.tex

# Or use latexmk for automated compilation
latexmk -pdf my_paper.tex
```

审查清单：
- [ ] 所有部分均已呈现且格式正确
- [ ] 引文正确呈现
- [ ] 数字带有正确的标题
- [ ] 页数在限制范围内
- [ ] 遵循作者指南
- [ ] 补充材料准备（如果需要）

## 与其他技能的整合

这项技能与其他科学技能无缝配合：

### 科学写作
- 使用**科学写作**技巧进行内容指导（IMRaD 结构、清晰度、精确性）
- 应用此技能中的特定场地模板进行格式化
- 结合起来完成原稿准备

### 文献综述
- 使用**文献综述**技巧进行系统的文献检索和综合
- 根据场地要求应用适当的引文风格
- 根据模板规范格式化参考文献

### 同行评审
- 使用**同行评审**技能来评估稿件质量
- 使用此技能来验证格式合规性
- 确保遵守报告准则（CONSORT、STROBE 等）

### 研究资助
- 内容策略与**研究资助**技能的交叉引用
- 使用此技能进行机构特定的模板和格式设置
- 结合起来进行全面的赠款提案准备

### LaTeX 海报
- 这项技能提供了与场地无关的海报模板
- 用于会议特定的海报要求
- 与图形创建的可视化技能相结合

## 模板类别

### 按文件类型

| 类别 | 模板计数 | 共同场地 |
|----------|---------------|---------------|
| **期刊文章** | 30+ | Nature、Science、PLOS、IEEE、ACM、Cell 按 |
| **会议论文** | 20+ | NeurIPS、ICML、CVPR、CHI、ISMB |
| **研究海报** | 10+ | A0、A1、36×48、各种封装 |
| **拨款提案** | 15+ | NSF、NIH、DOE、DARPA、基金会 |

### 按纪律

| 纪律 | 支持场地 |
|------------|------------------|
| **寿命 Sciences** | Nature、Cell 新闻、PLOS、ISMB、RECOMB |
| **物理 Sciences** | Science，物理评论，ACS，APS |
| **工程** | IEEE、ASME、AIAA、ACM |
| **计算机 Science** | ACM、IEEE、NeurIPS、ICML、ICLR |
| **医学** | NEJM、柳叶刀、JAMA、BMJ |
| **跨学科** | PNAS，Nature 通信，Science 进展 |

## 帮助脚本

### query_template.py

按场地名称、类型或关键字搜索和检索模板：

```bash
# Find templates for a specific journal
python scripts/query_template.py --venue "Nature" --type "article"

# Search by keyword
python scripts/query_template.py --keyword "machine learning"

# List all available templates
python scripts/query_template.py --list-all

# Get requirements for a venue
python scripts/query_template.py --venue "NeurIPS" --requirements
```

### customize_template.py

使用作者和项目信息自定义模板：

```bash
# Basic customization
python scripts/customize_template.py \
  --template assets/journals/nature_article.tex \
  --output my_paper.tex

# With author information
python scripts/customize_template.py \
  --template assets/journals/nature_article.tex \
  --title "Novel Approach to Protein Folding" \
  --authors "Jane Doe, John Smith, Alice Johnson" \
  --affiliations "MIT, Stanford, Harvard" \
  --email "[email protected]" \
  --output my_paper.tex

# Interactive mode
python scripts/customize_template.py --interactive
```

### validate_format.py

检查文件是否符合场地要求：

```bash
# Validate a compiled PDF
python scripts/validate_format.py \
  --file my_paper.pdf \
  --venue "Nature" \
  --check-all

# Check specific aspects
python scripts/validate_format.py \
  --file my_paper.pdf \
  --venue "NeurIPS" \
  --check page-count,margins,fonts

# Generate validation report
python scripts/validate_format.py \
  --file my_paper.pdf \
  --venue "Science" \
  --report validation_report.txt
```

## 最佳实践

### 模板选择
1. **验证货币**：检查模板日期并与最新的作者指南进行比较
2. **查看官方来源**：许多期刊提供官方 LaTeX 课程
3. **测试编译**：添加内容之前编译模板
4. **阅读评论**：模板包含有用的内嵌评论

### 定制化
1. **保留结构**：不要删除所需的部分或包
2. **遵循占位符**：系统地替换标记的占位符文本
3. **保持格式**：不要覆盖特定于场地的格式
4. **保留备份**：定制前保存原始模板

### 合规性
1. **检查页面限制**：最终提交前验证
2. **验证引文**：针对地点使用正确的引文样式
3. **测试图形**：确保图形满足分辨率要求
4. **审查匿名化**：如果需要，删除识别信息

### 提交
1. **遵循说明**：阅读完整的作者指南
2. **包括所有文件**：LaTeX 来源、图表、参考书目
3. **正确生成**：使用推荐的编译方法
4. **检查输出**：验证 PDF 是否符合预期

## 常见格式要求

### 页数限制（典型）

| 场地类型 | 典型限值 | 注释 |
|------------|---------------|-------|
| **Nature 文章** | 5页 | 约 3000 字（不包括参考文献） |
| **Science 报告** | 5页 | 数字计入限制 |
| **公共图书馆一** | 无限制 | 无限长度 |
| **NeurIPS** | 8页 | + 无限的参考文献/附录 |
| **ICML** | 8页 | + 无限的参考文献/附录 |
| **美国国家科学基金会提案** | 15页 | 仅项目描述 |
| **美国国立卫生研究院R01** | 12页 | 研究策略 |

### 按地点划分的引文风格

| 场地 | 引文风格 | 格式 |
|-------|---------------|--------|
| **Nature** | 编号（上标） | Nature款式 |
| **Science** | 编号（上标） | Science款式 |
| **公共科学图书馆** | 编号（括号） | Vancouver |
| **Cell 按** | Author-year | Cell款式 |
| **ACM** | 编号 | ACM款式 |
| **IEEE** | 编号（括号） | IEEE款式 |
| **APA 期刊** | Author-year | APA 7号 |

### 身材要求

| 场地 | 分辨率 | 格式 | 颜色 |
|-------|-----------|--------|-------|
| **Nature** | 300+ dpi | TIFF、EPS、PDF | RGB 或 CMYK |
| **Science** | 300+ dpi | TIFF、PDF | RGB |
| **公共科学图书馆** | 300-600 dpi | TIFF、EPS | RGB |
| **IEEE** | 300+ dpi | 每股收益、PDF | RGB 或灰度 |

## 写作风格指南

除了格式之外，这项技能还提供了全面的**写作风格指南**，捕捉论文在不同场合应该如何“阅读”——而不仅仅是它们的外观。

### 为什么风格很重要

为 Nature 编写的相同研究与为 NeurIPS 编写的相同研究读起来有很大不同：
- **Nature/Science**：非专业人士也可以使用，故事驱动，意义广泛
- **Cell Press**：机制深度，全面数据，需要图形摘要
- **医学期刊**：以患者为中心、证据分级、结构化摘要
- **机器学习会议**：贡献要点、消融研究、可重复性焦点
- **CS会议**：特定领域的会议，不同的评估标准

### 可用的风格指南

| 指南 | 封面 | 重点议题 |
|-------|--------|------------|
| `venue_writing_styles.md` | 大师概览 | 风格谱，快速参考 |
| `nature_science_style.md` | Nature、Science、PNAS | 无障碍、讲故事、影响广泛 |
| `cell_press_style.md` | Cell，神经元，免疫 | 图解摘要、eTOC、亮点 |
| `medical_journal_styles.md` | NEJM、柳叶刀、JAMA、BMJ | 结构化摘要，证据语言 |
| `ml_conference_style.md` | NeurIPS、ICML、ICLR、CVPR | 贡献子弹、消融 |
| `cs_conference_style.md` | ACL、EMNLP、CHI、SIGKDD | 特定领域的约定 |
| `reviewer_expectations.md` | 所有场馆 | 审稿人寻找什么，反驳技巧 |

### 写作范例

具体例子见`assets/examples/`：
- `nature_abstract_examples.md`：高影响力期刊的流畅段落摘要
- `neurips_introduction_example.md`：ML 会议介绍及贡献项目符号
- `cell_summary_example.md`：Cell 新闻摘要、亮点、eTOC 格式
- `medical_structured_abstract.md`：NEJM、Lancet、JAMA 结构化格式

### 工作流程：适应场地

1. **确定目标场地**并加载适当的风格指南
2. **复习写作惯例**：语气、语气、摘要格式、结构
3. **检查示例**以获得特定部分的指导
4. **审核期望**：该场所的审核者优先考虑什么？
5. **应用格式**：使用 `assets/` 中的 LaTeX 模板

---

## 资源

### 捆绑资源

**写作风格指南**（`references/`）：
- `venue_writing_styles.md`：大师风格概述与比较
- `nature_science_style.md`：Nature/Science 书写约定
- `cell_press_style.md`：Cell 新闻日志样式
- `medical_journal_styles.md`：医学期刊写作指南
- `ml_conference_style.md`：ML会议写作约定
- `cs_conference_style.md`：CS会议写作指南
- `reviewer_expectations.md`：审稿人按地点寻找什么

**格式要求**（`references/`）：
- `journals_formatting.md`：综合期刊格式要求
- `conferences_formatting.md`：会议论文规格
- `posters_guidelines.md`：研究海报设计和尺寸
- `grants_requirements.md`：机构拨款提案要求

**编写示例**（`assets/examples/`）：
- `nature_abstract_examples.md`：高影响力期刊摘要示例
- `neurips_introduction_example.md`：ML会议介绍格式
- `cell_summary_example.md`：Cell 新闻摘要/亮点/eTOC
- `medical_structured_abstract.md`：NEJM/Lancet/JAMA 摘要格式

**模板**（`assets/`）：
- `journals/`：期刊文章 LaTeX 模板
- `posters/`：研究海报模板
- `grants/`：拨款提案模板

**脚本**（`scripts/`）：
- `query_template.py`：搜索和检索模板
- `customize_template.py`：使用作者信息自定义
- `validate_format.py`：检查是否符合要求

### 外部资源

**期刊作者指南**：
- Nature: https://www.nature.com/nature/for-authors
- Science: https://www.science.org/content/page/instructions-authors
- 公开公共图书馆：https://plos.org/resources/for-authors/
- Cell 按：https://www.cell.com/author-guidelines

**会议格式**：
- NeurIPS: https://neurips.cc/Conferences/2024/CallForPapers
- ICML: https://icml.cc/Conferences/2024/StyleAuthorInstructions
- CVPR: https://cvpr.thecvf.com/Conferences/2024/AuthorGuidelines

**拨款资源**：
- NSF PAPPG：https://www.nsf.gov/publications/pub_summ.jsp?ods_key=pappg
- NIH 表格：https://grants.nih.gov/grants/how-to-apply-application-guide.html
- 美国能源部资助：https://science.osti.gov/grants

## 用法示例

### 示例1：Nature 文章提交

```markdown
User: "I need to prepare a manuscript for Nature"

Response:
1. Load Nature formatting requirements (references/journals_formatting.md)
2. Retrieve Nature template (assets/journals/nature_article.tex)
3. Key requirements:
   - Length: ~3000 words, ~5 pages
   - Format: Single column, 12pt font
   - Citations: Numbered superscript (Nature style)
   - Figures: 300+ dpi, RGB color
4. Customize template with your title, authors, affiliations
5. Compile and validate against requirements
```

### 示例2：NeurIPS 会议论文

```markdown
User: "What are the formatting requirements for NeurIPS?"

Response:
From references/conferences_formatting.md:
- Page limit: 8 pages main text + unlimited references/appendix
- Format: Two-column, 10pt font
- Template: neurips_2024.sty (official style file)
- Anonymization: Required for initial submission
- Citations: Numbered (brackets)
- Figures: High resolution, colorblind-safe recommended
```

### 示例 3：NSF 提案

```markdown
User: "Help me format an NSF proposal"

Response:
NSF requirements (from references/grants_requirements.md):
- Project Description: 15 pages maximum
- Project Summary: 1 page (Overview, Intellectual Merit, Broader Impacts)
- Budget Justification: 3-5 pages
- Biographical Sketch: 3 pages per senior personnel
- Font: Minimum 10pt, Times Roman or similar
- Margins: 1 inch all sides
Template: assets/grants/nsf_proposal_template.tex
```

### 示例4：会议海报

```markdown
User: "I need to create a poster for ISMB"

Response:
ISMB poster specifications:
- Size: Typically A0 portrait (33.1 × 46.8 inches)
- Recommended template: beamerposter or tikzposter
- Font sizes: Title 60-85pt, Headers 36-48pt, Body 24-32pt
- Include: QR code for paper/supplementary materials
Available templates:
- assets/posters/beamerposter_academic.tex
```

## 更新和维护

**模板货币**：
- 模板每年更新或在场馆发布新指南时更新
- 最后更新时间：2024 年
- 查看官方场地网站了解最新要求

**报告问题**：
- 模板编译错误
- 过时的格式要求
- 缺少场地模板
- 规格不正确

## 总结

场地模板技能提供对以下内容的全面访问：

1. **50 多个跨学科的出版场所模板**
2. **期刊、会议、海报、赠款的详细格式要求**
3. **用于模板发现、自定义和验证的帮助脚本**
4. **与其他科学写作技能的整合**
5. **成功学术提交的最佳实践**

每当您需要针对特定场地的格式指导或学术出版模板时，请使用此技能。


