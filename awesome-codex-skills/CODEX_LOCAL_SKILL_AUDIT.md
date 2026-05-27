# Codex 本机级 Skill 审计报告

审计日期：2026-05-26  
审计目录：`awesome-codex-skills`  
目标用户：软件开发工程师，主要使用 Codex，不能依赖 Claude Code。

## 结论摘要

- 目录中共有 430 个 `SKILL.md`，其中英文 215 个、中文 215 个；两套路径一一对应。报告按 215 个“逻辑 skill”审计，默认英文路径为 canonical，中文路径可按需替换 `awesome-codex-skills/en/...` 为 `awesome-codex-skills/zh/...`。
- 建议不要把 en/zh 两套都放入 `~/.codex/skills`，否则同一能力会重复触发。默认建议只放英文版；如果你更希望中文触发和中文说明，再用中文镜像版。
- 判定结果：`24` 个推荐放本机级，`55` 个条件放，`136` 个不建议放。
- 推荐优先纳入本机级能力的核心候选：`diagnose`, `grill-with-docs`, `improve-codebase-architecture`, `prototype`, `tdd`, `to-issues`, `to-prd`, `zoom-out`, `git-guardrails-codex`, `grill-me`, `handoff`, `write-a-skill`, `markdown-mermaid-writing`, `markitdown`, `pdf`, `polars`, `agent-deep-links`, `changelog-generator`, `gh-address-comments`, `gh-fix-ci`, `mcp-builder`, `skill-creator`, `skill-installer`, `webapp-testing`。其中和现有 `~/.codex/skills` 重复的项优先合并，不直接复制第二份。

## 判定标准

- **推荐放**：建议安装到本机全局 `~/.codex/skills`。这类 skill 覆盖通用软件工程高频场景，和 Codex 本机工作流契合，不依赖特定科研领域、公司系统或重型外部账号，放入全局目录后触发面可控。
- **条件放**：Codex 语义上可用，但依赖你的技术栈、外部 CLI/MCP/账号、项目管理系统或数据科学方向；只有命中你的实际工作流时，才按需安装到 `~/.codex/skills`，否则更保守地放到项目级说明里。
- **不放**：领域太窄、医学/科研/实验室高风险、营销/办公/个人生活类、旧 Claude/Rube 语义未迁移、模板/废弃/in-progress、或与本机已有通用 skill 明显重复。

## 本机已有技能的去重提醒

你的 `~/.codex/skills` 已经有一批工程基础技能，例如 `tdd-workflow`、`git-workflow`、`browser-qa`、`e2e-testing`、`mcp-server-patterns`、`coding-standards`、`python-patterns`、`security-review`、`deep-research`。本报告的“推荐放”表示源 skill 适合 Codex；真正安装时建议优先合并到已有同类 skill，避免触发重复或互相覆盖。也就是说，最终动作分三类：直接新增、并入现有 skill、或保留为项目级/按需 skill。

### 与现有 `~/.codex/skills` 的重复能力分析

当前本机全局目录已有 42 个 skill。下面只列和本报告候选 skill 有明显重复或相邻能力的项；未列出的多数属于完全不同领域，或只是语言/框架专用补充。

| 现有本机 skill | 本报告相关 skill | 重复/相邻能力 | 哪个更适合作为基座 | 建议处理方式 |
|---|---|---|---|---|
| `tdd-workflow`, `python-testing`, `golang-testing`, `rust-testing`, `kotlin-testing` | `mattpocock-skills/engineering/tdd` | 都覆盖 TDD、测试先行、红绿重构和覆盖率要求。 | 现有 `tdd-workflow` 更适合做全局执行基座，因为它已经绑定 80%+ coverage、unit/integration/E2E 和检查点；`mattpocock` 的 `tdd` 更强在测试设计哲学，例如 public interface、vertical tracer bullet、避免过度 mock。 | 不建议再独立安装 `tdd`。把 `tdd` 里关于行为测试、垂直切片、可测试性边界、mock 克制的内容合并进 `tdd-workflow`；语言细节继续留在各 `*-testing` skill。 |
| `browser-qa`, `e2e-testing` | `top-level/webapp-testing` | 都覆盖 Playwright/浏览器自动化、本地 WebApp 验证、交互和视觉检查。 | 现有 `browser-qa` + `e2e-testing` 拆分更清楚：一个偏人工/视觉 QA 报告，一个偏可维护 E2E 测试体系；`webapp-testing` 的优势是本地 dev server 生命周期和 `with_server.py` 辅助脚本。 | 不建议直接全局再装同名能力。把 `webapp-testing` 的“先侦察再执行”、本地服务器管理、截图/控制台日志收集流程合并到 `browser-qa` 或 `e2e-testing`；若单独保留，应重命名成 `local-webapp-testing`，触发范围限定为本地调试。 |
| `mcp-server-patterns` | `top-level/mcp-builder` | 都覆盖 MCP server 构建、工具/资源/提示、schema、传输方式和测试。 | 现有 `mcp-server-patterns` 更适合作为 Codex 全局基座，因为它短、明确、偏 Node/TypeScript SDK，并提醒查官方最新文档；`mcp-builder` 更全面，包含 Python/FastMCP、评估和工具设计，但仍有 `WebFetch`/Claude 残留。 | 不建议两个都全局触发。保留 `mcp-server-patterns`，从 `mcp-builder` 合并 Python FastMCP、agent-centric tool design、eval checklist、常见 reference；合并前删除 Claude/WebFetch 语义。 |
| `deep-research`, `documentation-lookup`, `search-first` | `scientific-skills/research-lookup`, `paper-lookup`, `literature-review`, `database-lookup`, `bgpt-paper-search`, `citation-management` | 都覆盖“先查资料再回答/编码”，以及文档、论文、数据库检索。 | 对软件开发日常，现有 `search-first` + `documentation-lookup` + `deep-research` 更好：一个管编码前找现成方案，一个管库/框架官方文档，一个管带引用的深入研究。科学类 skill 更强在论文库、BibTeX、PubMed/ArXiv/Google Scholar 等科研入口。 | 不建议默认全装科学检索类。若你经常做论文/技术研究，把 `paper-lookup`、`database-lookup` 的数据库选择表和引用输出规范并入 `deep-research`；`citation-management` 保持条件安装。 |
| `git-workflow` | `top-level/gh-address-comments`, `top-level/gh-fix-ci`, `top-level/changelog-generator`, `top-level/pr-review-ci-fix` | 都和 Git/GitHub/PR/CI/发布记录有关。 | 现有 `git-workflow` 更适合作为基础规则：分支、commit、merge/rebase、协作约定。报告里的 GitHub skill 更适合作为具体操作型 workflow。 | `gh-address-comments`、`gh-fix-ci` 可独立保留，因为它们是高频、清晰、可触发的 PR/CI 工作流；`changelog-generator` 可独立保留或把 release note 模板合并进 `git-workflow`；`pr-review-ci-fix` 依赖 Composio/GitHub/GitLab 权限，建议条件安装。 |
| `deployment-patterns` | `top-level/deploy-pipeline`, `top-level/datadog-logs`, `top-level/sentry-triage` | 都覆盖上线、回滚、生产排障、CI/CD 和可观测性。 | 现有 `deployment-patterns` 更适合作为通用部署/生产就绪基座；这些 top-level skill 更偏具体外部系统操作。 | 不默认安装外部账号类 skill。若你有对应账号和权限，把 `datadog-logs`、`sentry-triage` 作为条件独立 skill；从 `deploy-pipeline` 抽取发布前检查/回滚门禁并入 `deployment-patterns`。 |
| `agentic-engineering`, `prompt-optimizer` | `mattpocock-skills/productivity/grill-me`, `mattpocock-skills/engineering/grill-with-docs`, `top-level/create-plan` | 都覆盖计划、追问、方案压力测试、提示改写和执行策略。 | 现有 `agentic-engineering` 更适合作为全局工作方式基座；`grill-me`/`grill-with-docs` 的优势是把方案“拷问”成独立触发动作；`create-plan` 和 Codex 自带规划能力重复度最高。 | 建议保留 `grill-me` 和 `grill-with-docs` 为显式评审触发，或把它们的质询清单合并进 `agentic-engineering`；`create-plan` 不建议全局安装，除非你想固定“用户明确要求才出计划”的行为。 |
| `strategic-compact`, `verification-loop` | `mattpocock-skills/productivity/handoff` | 都覆盖长任务交接、上下文压缩、阶段性总结和继续执行。 | 现有 `strategic-compact` 更适合管理压缩时机，`verification-loop` 更适合作为收尾验证门禁；`handoff` 更强在交接文档结构。 | 不需要独立安装 `handoff`，除非你经常跨会话交接任务。更推荐把 `handoff` 的“当前状态、已改文件、剩余风险、下一步”模板并入 `strategic-compact`。 |
| `repo-scan`, `codebase-onboarding`, `coding-standards`, `backend-patterns`, `frontend-patterns` | `mattpocock-skills/engineering/improve-codebase-architecture`, `mattpocock-skills/engineering/zoom-out`, `mattpocock-skills/engineering/diagnose`, `mattpocock-skills/engineering/prototype` | 都会分析代码库、架构、可维护性和局部实现质量。 | 现有 skill 更适合做“理解和规范基座”；`diagnose`、`prototype`、`zoom-out`、`improve-codebase-architecture` 更像任务型工作流，能补齐从分析到行动的步骤。 | 可以并存，但要明确触发边界：`repo-scan`/`codebase-onboarding` 用于进入新仓库；`diagnose` 用于 bug/perf；`prototype` 用于试验方案；`improve-codebase-architecture` 用于架构改进。不要把这些全塞进一个超大 skill。 |
| `api-design`, `api-connector-builder`, `documentation-lookup` | `top-level/connect`, `top-level/codebase-migrate`, `top-level/paperjsx`, `scientific-skills/docx`, `pptx`, `xlsx` | 都涉及外部 API、连接器、文档/Office 生成或迁移。 | 对日常后端/集成开发，现有 `api-design` 和 `api-connector-builder` 更稳定；报告里的 skill 多数依赖 Composio、Office/PaperJSX 或具体账号。 | 不默认安装。`connect` 和 `codebase-migrate` 只有明确使用 Composio/Rube 迁移后的 Codex 工具链时再放；Office 类按文件处理频率条件安装。 |
| `design-system`, `frontend-patterns` | `scientific-skills/markdown-mermaid-writing`, `top-level/webapp-testing`, 以及不建议区里的 brand/theme/canvas 类 skill | 都触及前端 UI、一致性、文档图示和视觉产物。 | 现有 `design-system`/`frontend-patterns` 更适合软件产品 UI；`markdown-mermaid-writing` 是文档图示补充；brand/theme/canvas 更偏营销或视觉素材。 | `markdown-mermaid-writing` 可独立保留；`webapp-testing` 的测试部分按上文合并；brand/theme/canvas 类不建议放全局，避免和工程 UI 指南混淆。 |
| `python-patterns` | `scientific-skills/polars`, `dask`, `matplotlib`, `seaborn`, `scikit-learn`, `statsmodels`, `transformers`, `networkx` 等 | 都在 Python 生态，但层级不同：一个是语言/工程惯例，另一个是库专用 playbook。 | `python-patterns` 是基础；科学/数据类 skill 只有在对应库是你的常用工具时才更有价值。 | 不是直接重复，不要合并成一个巨型 Python skill。推荐只把常用库独立安装，比如当前报告推荐的 `polars`；其余按项目或技术栈条件安装。 |
| `security-review`, `security-scan` | `mattpocock-skills/misc/git-guardrails-codex` | 都和安全有关，但层次不同：安全审查/扫描 vs 防止危险 git 操作。 | 现有 `security-review`/`security-scan` 适合代码和配置风险；`git-guardrails-codex` 适合本机操作安全护栏。 | 可以并存。`git-guardrails-codex` 不应并入安全审查 skill，因为它的触发点是 git 命令风险；但安装前应确认规则不会挡住你常用的合法 git 流程。 |
| `close-reading-book`, `weread-skills` | `mattpocock-skills/personal/obsidian-vault`, 科研写作/文献类 skill | 都和阅读、知识库、笔记和长文档处理相关。 | 现有 `weread-skills`/`close-reading-book` 更偏个人阅读；`obsidian-vault` 更偏本地知识库维护；论文类更偏科研写作。 | 不建议默认混在工程全局 skill 里。若你希望 Codex 维护 Obsidian，可条件安装 `obsidian-vault`，但要限制文件操作范围；科研写作类按需独立安装。 |

### 去重后的安装建议

- **优先合并，不直接复制**：`tdd` 合并进 `tdd-workflow`；`webapp-testing` 合并进 `browser-qa`/`e2e-testing`；`mcp-builder` 合并进 `mcp-server-patterns`；`handoff` 合并进 `strategic-compact`；科研检索类按需合并进 `deep-research`。
- **适合独立保留的新增 skill**：`gh-address-comments`、`gh-fix-ci`、`changelog-generator`、`git-guardrails-codex`、`markdown-mermaid-writing`、`markitdown`、`pdf`、`polars`、`agent-deep-links`、`skill-installer`。这些触发边界相对清楚，不太会和现有基础 skill 抢同一个任务。
- **继续条件安装**：Composio/Rube/外部账号类、Office 文件类、Notion/Linear/Datadog/Sentry 类、科学计算库类。它们不是 Codex 不可用，而是不适合放成所有仓库都会看到的默认能力。
- **需要先清理再作为合并基座**：现有本机 skill 中仍能看到一些 Claude 历史文案，例如 `codebase-onboarding`、`eval-harness`、`security-scan`、`verification-loop`、`deep-research`、`search-first` 的描述或正文。它们可以作为能力基座，但正式合并前建议把这些遗留语义迁到 Codex。

## 推荐放入 ~/.codex/skills

| Skill | 判定理由 | 备注 |
|---|---|---|
| `mattpocock-skills/engineering/diagnose` | 通用调试闭环，适合任何代码库的 bug/perf regression 诊断。 | - |
| `mattpocock-skills/engineering/grill-with-docs` | 能把方案审查和 ADR/CONTEXT 文档同步起来，适合长期维护的工程项目。 | - |
| `mattpocock-skills/engineering/improve-codebase-architecture` | 面向架构改进、耦合梳理和可测试性，符合软件工程师本机全局使用场景。 | - |
| `mattpocock-skills/engineering/prototype` | 适合快速验证数据模型、状态机或 UI 方案，是通用工程探索技能。 | - |
| `mattpocock-skills/engineering/tdd` | 通用 TDD/red-green-refactor 工作流；若本机已有 tdd-workflow，应合并避免重复触发。 | - |
| `mattpocock-skills/engineering/to-issues` | 把计划拆成可执行 issue，对工程项目管理有直接价值。 | - |
| `mattpocock-skills/engineering/to-prd` | 从对话沉淀 PRD，适合需求澄清和工程规划。 | - |
| `mattpocock-skills/engineering/zoom-out` | 小而通用，帮助从局部代码切回系统上下文，适合全局保留。 | - |
| `mattpocock-skills/misc/git-guardrails-codex` | 保护本机 Codex 免于危险 git 命令，适合全局安全护栏。 | - |
| `mattpocock-skills/productivity/grill-me` | 方案压力测试和需求追问通用，对工程设计评审有价值。 | - |
| `mattpocock-skills/productivity/handoff` | 长任务交接/压缩上下文有用，适合本机全局。 | - |
| `mattpocock-skills/productivity/write-a-skill` | 创建/维护 Codex skills 的元技能；若已有 skill-creator，可二选一或合并。 | - |
| `scientific-skills/markdown-mermaid-writing` | Markdown/Mermaid 文档和图示对架构设计、技术方案、README 很有用。 | 37 files |
| `scientific-skills/markitdown` | 文件/Office/PDF 转 Markdown 对代码审阅、资料消化、文档迁移通用。 | MCP/外部服务; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/pdf` | PDF 读写拆合转换是通用工程文档任务，适合全局。 | - |
| `scientific-skills/polars` | 现代高速 DataFrame/ETL 能力，对软件工程和数据处理都常见。 | - |
| `top-level/agent-deep-links` | 面向 Codex/IDE 深链，软件工程沟通和调试链接很实用。 | 仍含 Claude 文案，安装前需复核 |
| `top-level/changelog-generator` | 从 git commit 生成 changelog 是通用发布工程任务。 | - |
| `top-level/gh-address-comments` | GitHub PR 评论处理是高频工程工作流。 | - |
| `top-level/gh-fix-ci` | GitHub Actions CI 诊断/修复对软件工程师很实用。 | - |
| `top-level/mcp-builder` | MCP server 构建是 Codex 扩展和工具集成核心能力。 | MCP/外部服务; 仍含 Claude 文案，安装前需复核 |
| `top-level/skill-creator` | 创建/维护 Codex skill 的核心元技能。 | - |
| `top-level/skill-installer` | 安装 curated/GitHub skills 到 CODEX_HOME，和本次任务直接相关。 | - |
| `top-level/webapp-testing` | Playwright 本地 WebApp 测试对前端/全栈开发非常有用。 | - |

## 条件放入 ~/.codex/skills

这些 skill 不是“不适合 Codex”，而是不适合默认全装。命中你的实际技术栈或账号体系时可以放。

| Skill                                         | 判定理由                                                         | 备注                            |
| --------------------------------------------- | ------------------------------------------------------------ | ----------------------------- |
| `mattpocock-skills/engineering/triage`        | 工程 issue triage 有用，但依赖团队的 issue tracker/标签体系；最好配项目规则使用。      | -                             |
| `mattpocock-skills/misc/setup-pre-commit`     | 适合 JS/TS 仓库的 Husky/lint-staged；若经常做前端项目可放，否则项目级即可。           | -                             |
| `mattpocock-skills/personal/obsidian-vault`   | 你当前工作区就是 Obsidian Vault；若希望 Codex 管理个人知识库，可放本机级，否则会扩大文件操作范围。 | -                             |
| `scientific-skills/aeon`                      | 时间序列 ML 对数据工程/预测任务有用，但不是普通软件开发默认技能。                          | -                             |
| `scientific-skills/bgpt-paper-search`         | Codex 可配置 MCP 使用，但主要是科学论文检索；只有你经常做论文/证据检索才放。                 | MCP/外部服务                      |
| `scientific-skills/citation-management`       | 学术引用/BibTeX 管理有用，但偏论文写作；软件工程默认不装。                            | -                             |
| `scientific-skills/dask`                      | 对大数据/并行 Python 工作流有用；做数据工程时可放。                               | -                             |
| `scientific-skills/database-lookup`           | 覆盖大量科研/API 数据库，体积大且触发面宽；只有经常做数据/文献/公共 API 查询才放。              | 79 files                      |
| `scientific-skills/docx`                      | Office 文档自动化通用，但附件多、触发面大；若常处理 Word 文档可放。                     | 61 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/exploratory-data-analysis` | 通用 EDA 对数据文件分析有用；数据工程/分析频繁时可放。                               | -                             |
| `scientific-skills/geopandas`                 | 如果做 GIS/地理数据工程可放；普通工程不需要。                                    | -                             |
| `scientific-skills/get-available-resources`   | 适合本机重计算/ML 前的资源探测；普通代码任务不需要频繁触发。                             | 仍含 Claude 文案，安装前需复核           |
| `scientific-skills/literature-review`         | 系统综述/文献调研有用，但偏科研写作；如你常做技术研究报告可放。                             | -                             |
| `scientific-skills/matlab`                    | 只有维护 MATLAB/Octave 代码时需要。                                    | -                             |
| `scientific-skills/matplotlib`                | Python 可视化常用；如果经常做数据分析/报告可放。                                 | -                             |
| `scientific-skills/modal`                     | 做 Python serverless/GPU/模型部署时有价值；不用 Modal 则不装。               | -                             |
| `scientific-skills/networkx`                  | 图算法/依赖图/知识图谱任务常用；若常处理 graph 数据可放。                            | -                             |
| `scientific-skills/optimize-for-gpu`          | CUDA/GPU 加速 Python 优化对 ML/数值计算工程有用；普通后端不需要。                  | -                             |
| `scientific-skills/paper-lookup`              | 学术论文数据库查询有用，但和现有 deep-research/search 能力有重叠；科研/论文任务多再放。      | -                             |
| `scientific-skills/pptx`                      | PowerPoint 自动化通用但附件多；常做汇报/文档交付可放。                            | 59 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/pymc`                      | 贝叶斯建模/概率编程有通用数据科学价值；不做统计建模则不装。                               | -                             |
| `scientific-skills/pymoo`                     | 多目标优化可用于工程设计/调参；不是日常开发默认。                                    | -                             |
| `scientific-skills/pytorch-lightning`         | 深度学习工程常用；如果本机经常写 PyTorch 可放。                                 | -                             |
| `scientific-skills/research-lookup`           | 研究检索可用，但依赖 external search/API；如果已有 deep-research 可不重复安装。    | -                             |
| `scientific-skills/scientific-visualization`  | 发表级图表规范偏科研；做数据报告/论文图时可放。                                     | -                             |
| `scientific-skills/scikit-learn`              | 经典 ML 通用；如果常做数据建模/实验可放。                                      | -                             |
| `scientific-skills/seaborn`                   | 快速统计可视化有用；数据分析频繁时可放。                                         | -                             |
| `scientific-skills/shap`                      | 模型解释工具；做 ML/风控/推荐等可放。                                        | -                             |
| `scientific-skills/simpy`                     | 离散事件仿真对系统容量/排队建模有用；不常用则项目级。                                  | -                             |
| `scientific-skills/statistical-analysis`      | 统计检验/功效分析对数据分析有用；不是普通开发默认。                                   | -                             |
| `scientific-skills/statsmodels`               | 严肃统计/时间序列建模有用；数据科学场景可放。                                      | -                             |
| `scientific-skills/sympy`                     | 符号数学/公式推导/代码生成有用；数学计算频繁时可放。                                  | -                             |
| `scientific-skills/timesfm-forecasting`       | 时间序列预测有工程价值，但依赖模型/资源；只在预测业务中放。                               | 27 files                      |
| `scientific-skills/torch-geometric`           | 图神经网络项目可放；普通工程不需要。                                           | -                             |
| `scientific-skills/transformers`              | LLM/NLP/多模态工程常用；若经常做 AI 应用/模型微调可放。                           | -                             |
| `scientific-skills/umap-learn`                | 降维/可视化/聚类辅助，数据科学场景可放。                                        | -                             |
| `scientific-skills/vaex`                      | 超大表格 out-of-core 分析有用；数据工程场景可放。                              | -                             |
| `scientific-skills/xlsx`                      | Excel/CSV 自动化通用但附件多；经常处理表格交付时可放。                             | 54 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/zarr-python`               | 大规模数组/云存储数据工程可放；普通开发不需要。                                     | -                             |
| `top-level/codebase-migrate`                  | 大规模迁移有价值，但依赖 Composio/issue/CI 工作流；确认工具链后再放。                 | Composio/Rube 依赖              |
| `top-level/connect`                           | Codex+Composio 外部 app 动作能力强，但权限面大；只在你明确使用 Composio 时放。       | Composio/Rube 依赖              |
| `top-level/create-plan`                       | 轻量计划 skill；Codex 已有规划能力，只有想固定“明确要求才出计划”时放。                   | -                             |
| `top-level/datadog-logs`                      | 生产排障有用，但依赖 Datadog/Composio；有账号和 CLI 再放。                     | Composio/Rube 依赖              |
| `top-level/deploy-pipeline`                   | Stripe/Supabase/Vercel 栈有用；否则过窄且可能触发高风险部署动作。                 | Composio/Rube 依赖              |
| `top-level/issue-triage`                      | Linear/Jira backlog triage 有用，但依赖 Composio 和团队流程。            | Composio/Rube 依赖              |
| `top-level/langsmith-fetch`                   | LangChain/LangGraph agent 调试很有用；仅在使用 LangSmith CLI 时放。       | 仍含 Claude 文案，安装前需复核           |
| `top-level/linear`                            | 如果团队用 Linear，可以全局放；否则不需要。                                    | MCP/外部服务                      |
| `top-level/notion-knowledge-capture`          | 如果 Notion 是团队知识库可放；否则外部依赖和触发面偏大。                             | MCP/外部服务                      |
| `top-level/notion-research-documentation`     | 如果技术资料在 Notion，可作为文档研究工具；否则不放。                               | MCP/外部服务; 20 files            |
| `top-level/notion-spec-to-implementation`     | 如果 PRD/spec 在 Notion，这对工程落地有价值；否则不装。                         | MCP/外部服务                      |
| `top-level/paperjsx`                          | 结构化生成 Office/PDF 有用，但依赖 PaperJSX；需要该工具链再放。                   | -                             |
| `top-level/pr-review-ci-fix`                  | PR review+CI 修复强工程价值，但依赖 Composio/GitHub/GitLab 权限；建议确认后放。   | Composio/Rube 依赖              |
| `top-level/sentry-triage`                     | 生产错误排障有用，但依赖 Sentry/Composio；使用 Sentry 时放。                   | Composio/Rube 依赖              |
| `top-level/spreadsheet-formula-helper`        | 表格公式常见但非核心开发；如果经常处理 Excel/Sheets 可放。                         | -                             |
| `top-level/support-ticket-triage`             | 支持工程/值班角色可用；普通开发不必全局放。                                       | -                             |

## 不建议放入 ~/.codex/skills

| Skill | 判定理由 | 备注 |
|---|---|---|
| `mattpocock-skills/deprecated/design-an-interface` | 位于 deprecated；API/interface exploration 思路有价值，但应并入 architecture/prototype 类技能而不是安装废弃副本。 | - |
| `mattpocock-skills/deprecated/qa` | 位于 deprecated，且偏 GitHub issue 访谈工作流；可由 triage/issue-triage 替代。 | - |
| `mattpocock-skills/deprecated/request-refactor-plan` | 位于 deprecated；refactor planning 能力可由 diagnose/improve-codebase-architecture/to-issues 覆盖。 | - |
| `mattpocock-skills/deprecated/ubiquitous-language` | 位于 deprecated；DDD 术语提取有用，但更适合作为项目文档规则，不适合直接装废弃 skill。 | - |
| `mattpocock-skills/engineering/setup-matt-pocock-skills` | Matt Pocock 专用 bootstrap，仍涉及 AGENTS/CLAUDE.md；只在采用整套技能时项目级运行。 | 仍含 Claude 文案，安装前需复核 |
| `mattpocock-skills/in-progress/review` | 位于 in-progress；且 Codex 自带 review/本机已有 review 类规范，等稳定后再考虑合并。 | 仍含 Claude 文案，安装前需复核 |
| `mattpocock-skills/in-progress/writing-beats` | 文章写作流程，非软件开发核心；需要时项目/个人写作场景单独安装。 | - |
| `mattpocock-skills/in-progress/writing-fragments` | 创作素材采集，不适合作为工程师本机全局 Codex skill。 | - |
| `mattpocock-skills/in-progress/writing-shape` | 长文成稿技能，非工程默认需求。 | - |
| `mattpocock-skills/misc/migrate-to-shoehorn` | @total-typescript/shoehorn 迁移很窄，只有特定 TS 课程/测试数据场景需要。 | - |
| `mattpocock-skills/misc/scaffold-exercises` | 课程练习脚手架，不是通用软件开发工作流。 | - |
| `mattpocock-skills/personal/edit-article` | 文章编辑，不是工程全局 skill。 | - |
| `mattpocock-skills/productivity/caveman` | 沟通风格偏好，不应作为 skill 污染触发面；更适合写入个人指令。 | - |
| `scientific-skills/adaptyv` | 蛋白实验平台 API，生命科学实验场景过窄。 | - |
| `scientific-skills/anndata` | 单细胞 .h5ad 数据结构，生信专用。 | - |
| `scientific-skills/arboreto` | 基因调控网络推断，生信研究专用。 | - |
| `scientific-skills/astropy` | 天文/天体物理专用库，不适合软件工程师全局默认。 | - |
| `scientific-skills/autoskill` | 依赖 screenpipe 读取屏幕活动且面向科研 workflow 自动发现，隐私/依赖成本高。 | 28 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/benchling-integration` | Benchling R&D/lab 平台专用。 | - |
| `scientific-skills/bids` | 神经影像 BIDS 数据集标准，领域过窄。 | - |
| `scientific-skills/biopython` | 分子生物学/生信工具箱，非通用软件开发。 | - |
| `scientific-skills/bioservices` | 生信数据库聚合查询，领域过窄。 | - |
| `scientific-skills/cellxgene-census` | 单细胞图谱查询，生物研究专用。 | - |
| `scientific-skills/cirq` | Google 量子计算框架，除量子项目外不适合全局。 | - |
| `scientific-skills/clinical-decision-support` | 临床决策文档，高风险医疗领域，不适合作为普通工程全局 skill。 | 22 files |
| `scientific-skills/clinical-reports` | 医疗/临床报告，高风险且合规要求强。 | 32 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/cobrapy` | 代谢网络建模，系统生物学专用。 | - |
| `scientific-skills/consciousness-council` | 多视角思考模板，不是工程执行技能；容易增加无谓触发。 | - |
| `scientific-skills/datamol` | 药物发现/分子处理专用。 | - |
| `scientific-skills/deepchem` | 分子机器学习专用。 | - |
| `scientific-skills/deeptools` | NGS/测序可视化专用。 | - |
| `scientific-skills/depmap` | 癌症依赖图谱查询，生物医药专用。 | - |
| `scientific-skills/dhdna-profiler` | 认知/写作风格画像，不是软件开发核心且容易越界。 | - |
| `scientific-skills/diffdock` | 分子 docking 专用。 | - |
| `scientific-skills/dnanexus-integration` | DNAnexus 云基因组平台专用。 | - |
| `scientific-skills/esm` | 蛋白语言模型专用。 | - |
| `scientific-skills/etetoolkit` | 系统发育树工具，生物研究专用。 | - |
| `scientific-skills/exa-search` | 外部 Exa 搜索依赖，Codex 已有 web/search 能力；除非明确使用 Exa。 | - |
| `scientific-skills/flowio` | 流式细胞 FCS 文件专用。 | - |
| `scientific-skills/fluidsim` | 流体仿真科研专用。 | - |
| `scientific-skills/generate-image` | 图像生成已有 Codex/image 工具，且非工程核心。 | - |
| `scientific-skills/geniml` | 基因组 interval ML 专用。 | - |
| `scientific-skills/geomaster` | 地理/几何资料包较大且元数据不完整；不适合默认全局。 | - |
| `scientific-skills/gget` | 生信快速查询工具，领域过窄。 | - |
| `scientific-skills/ginkgo-cloud-lab` | Ginkgo 云实验室/自动化实验专用。 | - |
| `scientific-skills/glycoengineering` | 蛋白糖基化工程专用。 | - |
| `scientific-skills/gtars` | 基因组 interval Rust/Python 工具，领域过窄。 | - |
| `scientific-skills/histolab` | 病理切片处理专用。 | - |
| `scientific-skills/hugging-science` | 科学 AI 资源导航，不是软件工程默认 skill。 | - |
| `scientific-skills/hypogenic` | 科研假设生成框架，非工程默认。 | 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/hypothesis-generation` | 科研实验假设设计，不适合普通工程全局。 | - |
| `scientific-skills/imaging-data-commons` | 癌症影像数据平台专用。 | 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/infographics` | 信息图生成，非工程核心且依赖外部图像模型。 | - |
| `scientific-skills/iso-13485-certification` | 医疗器械 QMS/ISO 合规专用，高领域门槛。 | - |
| `scientific-skills/labarchive-integration` | 电子实验记录本 API 专用。 | - |
| `scientific-skills/lamindb` | 生物数据管理框架专用。 | - |
| `scientific-skills/latchbio-integration` | Latch 生信 workflow 平台专用。 | - |
| `scientific-skills/latex-posters` | 科研海报排版，不是软件工程默认。 | - |
| `scientific-skills/market-research-reports` | 市场研究报告，非工程开发核心。 | - |
| `scientific-skills/matchms` | 质谱/代谢组学专用。 | - |
| `scientific-skills/medchem` | 药物化学过滤专用。 | - |
| `scientific-skills/molecular-dynamics` | 分子动力学专用。 | - |
| `scientific-skills/molfeat` | 分子 ML 特征工程专用。 | - |
| `scientific-skills/neurokit2` | 生理信号处理专用。 | - |
| `scientific-skills/neuropixels-analysis` | 神经电生理分析专用。 | 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/omero-integration` | 显微图像管理平台专用。 | - |
| `scientific-skills/open-notebook` | 特定自托管研究笔记应用，不是工程全局 skill。 | 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/opentrons-integration` | Opentrons 实验机器人专用。 | - |
| `scientific-skills/pacsomatic` | nf-core/pacsomatic 肿瘤基因组 workflow 专用。 | - |
| `scientific-skills/paperzilla` | Paperzilla 应用专用。 | - |
| `scientific-skills/parallel-web` | 依赖 parallel-cli，且和 Codex web search/本机 deep-research 重叠。 | - |
| `scientific-skills/pathml` | 计算病理 WSI/医学影像专用。 | - |
| `scientific-skills/peer-review` | 学术同行评审，不是软件开发默认。 | - |
| `scientific-skills/pennylane` | 量子 ML 专用。 | - |
| `scientific-skills/phylogenetics` | 系统发育分析专用。 | - |
| `scientific-skills/polars-bio` | 生信 interval 操作专用。 | - |
| `scientific-skills/pptx-posters` | 科研 PPTX poster 专用。 | - |
| `scientific-skills/primekg` | 医学知识图谱查询专用。 | - |
| `scientific-skills/protocolsio-integration` | protocols.io 科研协议平台专用。 | - |
| `scientific-skills/pufferlib` | 强化学习框架，领域过窄。 | - |
| `scientific-skills/pydeseq2` | RNA-seq 差异表达专用。 | - |
| `scientific-skills/pydicom` | DICOM 医学影像文件专用。 | - |
| `scientific-skills/pyhealth` | 医疗深度学习专用，高领域风险。 | - |
| `scientific-skills/pylabrobot` | 实验室自动化硬件专用。 | - |
| `scientific-skills/pymatgen` | 材料科学专用。 | - |
| `scientific-skills/pyopenms` | 质谱/蛋白组学专用。 | - |
| `scientific-skills/pysam` | SAM/BAM/VCF 基因组文件专用。 | - |
| `scientific-skills/pytdc` | 药物发现 benchmark 数据集专用。 | - |
| `scientific-skills/pyzotero` | Zotero 文献库 API，偏学术资料管理。 | - |
| `scientific-skills/qiskit` | IBM 量子计算框架专用。 | - |
| `scientific-skills/qutip` | 量子物理仿真专用。 | - |
| `scientific-skills/rdkit` | 化学信息学专用。 | - |
| `scientific-skills/research-grants` | 科研基金申请写作，非工程默认。 | - |
| `scientific-skills/rowan` | 分子建模云平台专用。 | - |
| `scientific-skills/scanpy` | 单细胞 RNA-seq 分析专用。 | - |
| `scientific-skills/scholar-evaluation` | 学者/论文评价，非软件工程开发场景。 | - |
| `scientific-skills/scientific-brainstorming` | 科研创意发散，不是工程执行技能。 | - |
| `scientific-skills/scientific-critical-thinking` | 科学证据评估，偏科研/医学，不适合默认触发。 | - |
| `scientific-skills/scientific-schematics` | 科研图示生成，非工程核心且依赖图像模型。 | - |
| `scientific-skills/scientific-slides` | 科研演讲幻灯片，非工程默认。 | - |
| `scientific-skills/scientific-writing` | 科研论文写作，不是软件开发默认。 | - |
| `scientific-skills/scikit-bio` | 生物数据分析专用。 | - |
| `scientific-skills/scikit-survival` | 生存分析专用统计领域。 | - |
| `scientific-skills/scvelo` | RNA velocity 单细胞分析专用。 | - |
| `scientific-skills/scvi-tools` | 单细胞深度生成模型专用。 | - |
| `scientific-skills/stable-baselines3` | 强化学习实验框架，非日常工程。 | - |
| `scientific-skills/tiledbvcf` | 群体基因组 VCF 存储专用。 | - |
| `scientific-skills/torchdrug` | 药物/蛋白 GNN 专用。 | - |
| `scientific-skills/treatment-plans` | 医疗治疗计划，高风险医疗内容。 | 23 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/usfiscaldata` | 美国财政数据 API，非软件开发默认。 | - |
| `scientific-skills/venue-templates` | 科研投稿模板，非工程默认。 | 33 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/what-if-oracle` | 泛场景思考模板，容易和普通推理重复，不建议全局触发。 | - |
| `top-level/brand-guidelines` | OpenAI/Codex 视觉品牌指南，非开发核心。 | - |
| `top-level/canvas-design` | 静态艺术/设计资源庞大，非工程默认。 | 83 files; 仍含 Claude 文案，安装前需复核 |
| `top-level/competitive-ads-extractor` | 广告/营销分析，非软件开发。 | - |
| `top-level/connect-apps` | 仍是 Claude/Rube/Composio 旧语义，且被 connect 替代。 | Composio/Rube 依赖; 仍含 Claude 文案，安装前需复核 |
| `top-level/content-research-writer` | 内容写作，不是工程默认。 | - |
| `top-level/developer-growth-analysis` | 读取 Codex 历史并发 Slack，隐私/外部发送风险高，不建议全局。 | Composio/Rube 依赖; MCP/外部服务 |
| `top-level/domain-name-brainstormer` | 域名创意/查询，非工程核心。 | - |
| `top-level/email-draft-polish` | 邮件写作，不是开发 skill。 | - |
| `top-level/file-organizer` | 会跨本机整理文件，权限面大；不适合作为默认工程 skill。 | - |
| `top-level/helium-mcp` | 新闻/金融/ meme MCP，非开发核心。 | MCP/外部服务 |
| `top-level/image-enhancer` | 图片增强非软件开发默认。 | - |
| `top-level/internal-comms` | 仍含 Claude 指代且公司格式私有化强；需要迁移后项目/团队级使用。 | 仍含 Claude 文案，安装前需复核 |
| `top-level/invoice-organizer` | 发票整理，非工程开发且文件权限面大。 | - |
| `top-level/lead-research-assistant` | 销售线索研究，非软件开发。 | - |
| `top-level/meeting-insights-analyzer` | 会议行为分析，非工程开发默认。 | - |
| `top-level/meeting-notes-and-actions` | 会议纪要泛办公技能，不建议放开发全局。 | - |
| `top-level/notion-meeting-intelligence` | 会议材料准备，非工程默认。 | MCP/外部服务 |
| `top-level/raffle-winner-picker` | 抽奖工具，非软件开发。 | - |
| `top-level/skill-share` | Claude/Rube/Slack 分享旧语义，未迁移到 Codex。 | Composio/Rube 依赖; 仍含 Claude 文案，安装前需复核 |
| `top-level/slack-gif-creator` | Slack GIF 制作，非开发默认。 | 23 files |
| `top-level/tailored-resume-generator` | 简历生成，非工程开发 skill。 | - |
| `top-level/template-skill` | 模板占位且仍写 Claude，不应安装。 | 仍含 Claude 文案，安装前需复核 |
| `top-level/theme-factory` | 视觉主题/制品美化，非工程核心。 | - |
| `top-level/video-downloader` | YouTube 下载，非开发且可能涉及版权/站点政策风险。 | - |

## 建议执行顺序

1. 先只迁移“推荐放”中的工程核心 skill，并与现有 `~/.codex/skills` 做同名/同能力去重。
2. 对“条件放”按你真实项目栈选择：GitHub/CI/Sentry/Datadog/Linear/Notion/Composio、ML/Data、Office 文档处理分别成组安装。
3. 不迁移“不放”列表；如果未来出现对应项目，把它们作为项目级 skill 或临时参考资料使用，不放到本机全局。
4. 安装前再做一次 Codex 兼容检查：frontmatter、`allowed-tools`、MCP/TOML 配置、Claude/Rube/Composio 旧文案、以及脚本是否假设 Claude Code 的环境变量或 hook stdin。
