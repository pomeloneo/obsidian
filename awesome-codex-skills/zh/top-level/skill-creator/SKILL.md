---
name: skill-creator
description: 创建高效 skills 的指南。当用户想创建新 skill（或更新现有 skill），用专门知识、workflow 或 tool integration 扩展 Codex 能力时，应使用此 skill。
metadata:
  short-description: 创建或更新 skill
---

# Skill 创建器

此 skill 提供创建高效 skills 的指导。

## 关于 Skills

Skills 是模块化、自包含的包，通过提供专门知识、workflows 和 tools 来扩展 Codex 的能力。可以把它们理解为特定领域或任务的“onboarding guides”，它们把 Codex 从通用 agent 转变为具备程序性知识的专门 agent，而这些知识不是任何模型都能完全具备的。

### Skills 提供什么

1. 专门 workflows - 面向特定领域的多步骤流程
2. Tool integrations - 与特定文件格式或 APIs 配合工作的说明
3. Domain expertise - 公司特定知识、schemas、business logic
4. Bundled resources - 用于复杂和重复任务的 scripts、references 和 assets

## 核心原则

### 简洁是关键

Context window 是公共资源。Skills 会和 Codex 需要的一切共享 context window：system prompt、conversation history、其他 Skills 的 metadata，以及实际的用户请求。

**默认假设：Codex 已经非常聪明。** 只添加 Codex 尚不具备的上下文。审视每一条信息：“Codex 真的需要这段解释吗？”以及“这段内容值得它消耗的 token 成本吗？”

优先使用简洁示例，而不是冗长解释。

### 设置合适的自由度

让具体程度匹配任务的脆弱性和可变性：

**高自由度（基于文本的说明）**：当多种方法都有效、决策依赖上下文，或使用启发式方法来指导时使用。

**中等自由度（带参数的 pseudocode 或 scripts）**：当存在首选模式、允许一些变化，或配置会影响行为时使用。

**低自由度（具体 scripts、少量参数）**：当操作脆弱且容易出错、一致性很关键，或必须遵循特定顺序时使用。

把 Codex 想成在探索路径：狭窄桥梁和悬崖需要明确护栏（低自由度），而开阔场地允许多条路线（高自由度）。

### Skill 的组成

每个 skill 都包含一个必需的 SKILL.md 文件和可选的 bundled resources：

```
skill-name/
├── SKILL.md (required)
│   ├── YAML frontmatter metadata (required)
│   │   ├── name: (required)
│   │   └── description: (required)
│   └── Markdown instructions (required)
└── Bundled Resources (optional)
    ├── scripts/          - Executable code (Python/Bash/etc.)
    ├── references/       - Documentation intended to be loaded into context as needed
    └── assets/           - Files used in output (templates, icons, fonts, etc.)
```

#### SKILL.md（必需）

每个 SKILL.md 包含：

- **Frontmatter**（YAML）：包含 `name` 和 `description` 字段。这些是 Codex 用于判断何时使用该 skill 的唯一字段，因此非常重要，要清晰且完整地描述该 skill 是什么，以及何时应该使用。
- **Body**（Markdown）：使用该 skill 的说明和指导。只有在 skill 触发之后才会加载（如果触发的话）。

#### Bundled Resources（可选）

##### Scripts（`scripts/`）

用于需要确定性可靠性或会反复重写的任务的可执行代码（Python/Bash/etc.）。

- **何时包含**：当同一段代码会被反复重写，或需要确定性可靠性时
- **示例**：用于 PDF 旋转任务的 `scripts/rotate_pdf.py`
- **收益**：节省 token、确定性强、无需加载到 context 中即可执行
- **注意**：Codex 仍可能需要读取 scripts，以便 patch 或做环境特定调整

##### References（`references/`）

用于按需加载到 context 中、帮助 Codex 的流程和思考的文档与参考材料。

- **何时包含**：当 Codex 工作时应参考某些文档时
- **示例**：金融 schemas 的 `references/finance.md`、公司 NDA 模板的 `references/mnda.md`、公司 policies 的 `references/policies.md`、API specifications 的 `references/api_docs.md`
- **使用场景**：Database schemas、API documentation、domain knowledge、company policies、详细 workflow guides
- **收益**：让 SKILL.md 保持精简，仅在 Codex 判断需要时加载
- **最佳实践**：如果文件很大（>10k words），在 SKILL.md 中包含 grep search patterns
- **避免重复**：信息应存在于 SKILL.md 或 references files 中，不要两处都有。除非信息确实是 skill 的核心，否则优先放入 references files，这样能让 SKILL.md 保持精简，同时使信息可发现而不占满 context window。SKILL.md 中只保留必要的程序性说明和 workflow guidance；把详细 reference material、schemas 和 examples 移到 references files。

##### Assets（`assets/`）

不打算加载到 context 中，而是供 Codex 产出的结果使用的文件。

- **何时包含**：当 skill 需要最终输出中会使用的文件时
- **示例**：品牌素材 `assets/logo.png`、PowerPoint 模板 `assets/slides.pptx`、HTML/React boilerplate `assets/frontend-template/`、字体 `assets/font.ttf`
- **使用场景**：Templates、images、icons、boilerplate code、fonts、会被复制或修改的 sample documents
- **收益**：将输出资源与文档分离，让 Codex 可以使用文件而不把它们加载到 context

#### Skill 中不应包含什么

Skill 应只包含直接支持其功能的必要文件。不要创建多余文档或辅助文件，包括：

- README.md
- INSTALLATION_GUIDE.md
- QUICK_REFERENCE.md
- CHANGELOG.md
- etc.

Skill 应只包含 AI agent 完成手头工作所需的信息。不应包含关于创建过程、设置和测试流程、面向用户的文档等辅助上下文。创建额外文档文件只会增加杂乱和困惑。

### Progressive Disclosure 设计原则

Skills 使用三级加载系统来高效管理 context：

1. **Metadata（name + description）** - 始终在 context 中（约 100 words）
2. **SKILL.md body** - skill 触发时加载（<5k words）
3. **Bundled resources** - Codex 按需使用（无限制，因为 scripts 可执行而无需读入 context window）

#### Progressive Disclosure Patterns

将 SKILL.md body 保持在必要内容内，并控制在 500 行以下，以最小化 context 膨胀。接近此限制时，将内容拆分到单独文件。把内容拆到其他文件时，非常重要的是在 SKILL.md 中引用它们，并清楚说明何时读取，确保 skill 的读者知道它们存在以及何时使用。

**关键原则：** 当一个 skill 支持多种 variations、frameworks 或 options 时，只在 SKILL.md 中保留核心 workflow 和 selection guidance。将 variant-specific details（patterns、examples、configuration）移入单独的 reference files。

**Pattern 1: High-level guide with references**

```markdown
# PDF Processing

## Quick start

Extract text with pdfplumber:
[code example]

## Advanced features

- **Form filling**: See [FORMS.md](FORMS.md) for complete guide
- **API reference**: See [REFERENCE.md](REFERENCE.md) for all methods
- **Examples**: See [EXAMPLES.md](EXAMPLES.md) for common patterns
```

Codex 只在需要时加载 FORMS.md、REFERENCE.md 或 EXAMPLES.md。

**Pattern 2: Domain-specific organization**

对于包含多个 domains 的 Skills，按 domain 组织内容，避免加载无关 context：

```
bigquery-skill/
├── SKILL.md (overview and navigation)
└── reference/
    ├── finance.md (revenue, billing metrics)
    ├── sales.md (opportunities, pipeline)
    ├── product.md (API usage, features)
    └── marketing.md (campaigns, attribution)
```

当用户询问 sales metrics 时，Codex 只读取 sales.md。

类似地，对于支持多个 frameworks 或 variants 的 skills，按 variant 组织：

```
cloud-deploy/
├── SKILL.md (workflow + provider selection)
└── references/
    ├── aws.md (AWS deployment patterns)
    ├── gcp.md (GCP deployment patterns)
    └── azure.md (Azure deployment patterns)
```

当用户选择 AWS 时，Codex 只读取 aws.md。

**Pattern 3: Conditional details**

展示基础内容，链接到高级内容：

```markdown
# DOCX Processing

## Creating documents

Use docx-js for new documents. See [DOCX-JS.md](DOCX-JS.md).

## Editing documents

For simple edits, modify the XML directly.

**For tracked changes**: See [REDLINING.md](REDLINING.md)
**For OOXML details**: See [OOXML.md](OOXML.md)
```

Codex 只在用户需要这些功能时读取 REDLINING.md 或 OOXML.md。

**重要指南：**

- **避免深层嵌套 references** - 保持 references 与 SKILL.md 只有一层距离。所有 reference files 都应从 SKILL.md 直接链接。
- **组织较长 reference files** - 对于超过 100 行的文件，在顶部包含目录，让 Codex 预览时能看到完整范围。

## Skill 创建流程

Skill 创建包含以下步骤：

1. 用具体示例理解 skill
2. 规划可复用 skill contents（scripts、references、assets）
3. 初始化 skill（运行 init_skill.py）
4. 编辑 skill（实现 resources 并编写 SKILL.md）
5. 打包 skill（运行 package_skill.py）
6. 基于真实使用迭代

按顺序执行这些步骤；只有在有明确原因说明某步不适用时才跳过。

### Skill 命名

- 只使用小写字母、数字和连字符；将用户提供的标题标准化为 hyphen-case（例如 "Plan Mode" -> `plan-mode`）。
- 生成名称时，生成 64 个字符以内的名称（字母、数字、连字符）。
- 优先使用简短、动词开头、描述动作的短语。
- 当有助于清晰度或触发时，按 tool 命名空间划分（例如 `gh-address-comments`、`linear-address-issue`）。
- Skill folder 的名称必须与 skill name 完全一致。

### Step 1: 用具体示例理解 Skill

仅当 skill 的使用模式已经非常清楚时才跳过此步骤。即使处理现有 skill，这一步仍然有价值。

要创建高效 skill，需要清楚理解该 skill 将如何被使用的具体示例。这种理解可以来自用户直接提供的示例，也可以来自生成并经过用户反馈验证的示例。

例如，构建 image-editor skill 时，相关问题包括：

- “image-editor skill 应支持哪些功能？编辑、旋转，还有其他吗？”
- “能否给一些这个 skill 会如何被使用的示例？”
- “我能想象用户会提出类似 ‘Remove the red-eye from this image’ 或 ‘Rotate this image’ 的请求。你还会设想它以其他方式使用吗？”
- “用户会说什么来触发这个 skill？”

为避免让用户不知所措，不要在一条消息中问太多问题。从最重要的问题开始，并根据需要跟进，以提升效果。

当已经清楚该 skill 应支持哪些功能时，结束此步骤。

### Step 2: 规划可复用 Skill Contents

要把具体示例转化为高效 skill，请按以下方式分析每个示例：

1. 思考如何从零执行该示例
2. 识别重复执行这些 workflows 时哪些 scripts、references 和 assets 会有帮助

示例：构建处理 “Help me rotate this PDF” 等请求的 `pdf-editor` skill 时，分析结果显示：

1. 旋转 PDF 每次都需要重写同一段代码
2. 将 `scripts/rotate_pdf.py` script 存在 skill 中会有帮助

示例：设计处理 “Build me a todo app” 或 “Build me a dashboard to track my steps” 等请求的 `frontend-webapp-builder` skill 时，分析结果显示：

1. 编写 frontend webapp 每次都需要相同的 HTML/React boilerplate
2. 将包含 HTML/React project files boilerplate 的 `assets/hello-world/` template 存在 skill 中会有帮助

示例：构建处理 “How many users have logged in today?” 等请求的 `big-query` skill 时，分析结果显示：

1. 查询 BigQuery 每次都需要重新发现 table schemas 和 relationships
2. 将记录 table schemas 的 `references/schema.md` 文件存在 skill 中会有帮助

要确定 skill 的 contents，请分析每个具体示例，创建要包含的可复用 resources 列表：scripts、references 和 assets。

### Step 3: 初始化 Skill

此时应实际创建 skill。

仅当正在开发的 skill 已经存在，并且只需要迭代或打包时才跳过此步骤。在这种情况下，继续下一步。

从零创建新 skill 时，始终运行 `init_skill.py` script。该 script 会方便地生成一个新的 template skill directory，自动包含 skill 所需的一切，使 skill 创建过程更高效、更可靠。

用法：

```bash
scripts/init_skill.py <skill-name> --path <output-directory> [--resources scripts,references,assets] [--examples]
```

示例：

```bash
scripts/init_skill.py my-skill --path skills/public
scripts/init_skill.py my-skill --path skills/public --resources scripts,references
scripts/init_skill.py my-skill --path skills/public --resources scripts --examples
```

该 script 会：

- 在指定 path 创建 skill directory
- 生成带有正确 frontmatter 和 TODO placeholders 的 SKILL.md template
- 根据 `--resources` 可选创建 resource directories
- 当设置 `--examples` 时，可选添加 example files

初始化后，根据需要自定义 SKILL.md 并添加 resources。如果使用了 `--examples`，请替换或删除 placeholder files。

### Step 4: 编辑 Skill

编辑（新生成或现有的）skill 时，请记住该 skill 是为另一个 Codex 实例使用而创建的。包含对 Codex 有益且非显而易见的信息。考虑哪些 procedural knowledge、domain-specific details 或 reusable assets 能帮助另一个 Codex 实例更有效地执行这些任务。

#### 学习经过验证的设计模式

根据 skill 的需求查阅这些有用指南：

- **多步骤流程**：查看 references/workflows.md，了解 sequential workflows 和 conditional logic
- **特定输出格式或质量标准**：查看 references/output-patterns.md，了解 template 和 example patterns

这些文件包含高效 skill 设计的既定最佳实践。

#### 从可复用 Skill Contents 开始

开始实现时，从上面识别出的 reusable resources 开始：`scripts/`、`references/` 和 `assets/` 文件。注意此步骤可能需要用户输入。例如，实现 `brand-guidelines` skill 时，用户可能需要提供要存储在 `assets/` 中的 brand assets 或 templates，或要存储在 `references/` 中的 documentation。

新增 scripts 必须通过实际运行来测试，以确保没有 bug 且输出符合预期。如果有许多类似 scripts，只需测试有代表性的样本，以在完成时间和信心之间取得平衡。

如果使用了 `--examples`，删除 skill 不需要的任何 placeholder files。只创建实际需要的 resource directories。

#### 更新 SKILL.md

**写作指南：** 始终使用祈使/不定式形式。

##### Frontmatter

使用 `name` 和 `description` 编写 YAML frontmatter：

- `name`：skill name
- `description`：这是 skill 的主要触发机制，帮助 Codex 理解何时使用该 skill。
  - 同时包含 Skill 做什么，以及何时使用它的具体 triggers/contexts。
  - 将所有 “when to use” 信息放在这里，而不是 body 中。Body 只有在触发后才会加载，因此 body 中的 “When to Use This Skill” sections 对 Codex 没有帮助。
  - `docx` skill 的示例 description："全面的文档创建、编辑和分析，支持 tracked changes、comments、formatting preservation 和 text extraction。当 Codex 需要处理 professional documents（.docx files）时使用，包括：(1) 创建新文档，(2) 修改或编辑内容，(3) 处理 tracked changes，(4) 添加 comments，或任何其他文档任务"

不要在 YAML frontmatter 中包含任何其他字段。

##### Body

编写使用该 skill 及其 bundled resources 的说明。

### Step 5: 打包 Skill

Skill 开发完成后，必须打包为可分发的 .skill 文件并分享给用户。打包流程会先自动验证 skill，确保它满足所有要求：

```bash
scripts/package_skill.py <path/to/skill-folder>
```

可选的输出目录指定：

```bash
scripts/package_skill.py <path/to/skill-folder> ./dist
```

打包 script 会：

1. **自动验证** skill，检查：

   - YAML frontmatter 格式和必需字段
   - Skill 命名约定和目录结构
   - Description 完整性和质量
   - 文件组织和 resource references

2. **打包** skill（如果验证通过），创建一个以 skill 命名的 .skill 文件（例如 `my-skill.skill`），该文件包含所有文件并保留用于分发的正确目录结构。.skill 文件是带有 .skill 扩展名的 zip 文件。

如果验证失败，script 会报告错误并退出，不创建 package。修复所有验证错误后，再次运行打包命令。

### Step 6: 迭代

测试 skill 后，用户可能会请求改进。这通常发生在刚使用 skill 后，仍有关于 skill 表现的新鲜上下文。

**迭代 workflow：**

1. 在真实任务中使用 skill
2. 注意遇到的困难或低效之处
3. 识别应如何更新 SKILL.md 或 bundled resources
4. 实现更改并再次测试
