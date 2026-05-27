# Codex 本机级 Skill 审计报告

审计日期：2026-05-26  
审计目录：`awesome-codex-skills`  
目标用户：软件开发工程师，主要使用 Codex，不能依赖 Claude Code。

## 结论摘要

- 目录中共有 430 个 `SKILL.md`，其中英文 215 个、中文 215 个；两套路径一一对应。报告按 215 个“逻辑 skill”审计，默认英文路径为 canonical，中文路径可按需替换 `awesome-codex-skills/en/...` 为 `awesome-codex-skills/zh/...`。
- 建议不要把 en/zh 两套都放入 `~/.codex/skills`，否则同一能力会重复触发。默认建议只放英文版；如果你更希望中文触发和中文说明，再用中文镜像版。
- 判定结果：`24` 个推荐放本机级，`55` 个条件放，`136` 个不建议放。
- 推荐优先安装的核心候选：`diagnose`, `grill-with-docs`, `improve-codebase-architecture`, `prototype`, `tdd`, `to-issues`, `to-prd`, `zoom-out`, `git-guardrails-codex`, `grill-me`, `handoff`, `write-a-skill`, `markdown-mermaid-writing`, `markitdown`, `pdf`, `polars`, `agent-deep-links`, `changelog-generator`, `gh-address-comments`, `gh-fix-ci`, `mcp-builder`, `skill-creator`, `skill-installer`, `webapp-testing`。

## 判定标准

- **推荐放**：通用软件工程高频场景，和 Codex 本机工作流契合，不依赖特定科研领域、公司系统或重型外部账号；放入全局目录后触发面可控。
- **条件放**：Codex 语义上可用，但依赖你的技术栈、外部 CLI/MCP/账号、项目管理系统或数据科学方向；适合按需复制到 `~/.codex/skills`，或更保守地放到项目级说明里。
- **不放**：领域太窄、医学/科研/实验室高风险、营销/办公/个人生活类、旧 Claude/Rube 语义未迁移、模板/废弃/in-progress、或与本机已有通用 skill 明显重复。

## 本机已有技能的去重提醒

你的 `~/.codex/skills` 已经有一批工程基础技能，例如 `tdd-workflow`、`git-workflow`、`browser-qa`、`e2e-testing`、`mcp-server-patterns`、`coding-standards`、`python-patterns`、`security-review`、`deep-research`。本报告的“推荐放”表示源 skill 适合 Codex；真正安装时建议优先合并到已有同类 skill，避免触发重复或互相覆盖。

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

| Skill | 判定理由 | 备注 |
|---|---|---|
| `mattpocock-skills/engineering/triage` | 工程 issue triage 有用，但依赖团队的 issue tracker/标签体系；最好配项目规则使用。 | - |
| `mattpocock-skills/misc/setup-pre-commit` | 适合 JS/TS 仓库的 Husky/lint-staged；若经常做前端项目可放，否则项目级即可。 | - |
| `mattpocock-skills/personal/obsidian-vault` | 你当前工作区就是 Obsidian Vault；若希望 Codex 管理个人知识库，可放本机级，否则会扩大文件操作范围。 | - |
| `scientific-skills/aeon` | 时间序列 ML 对数据工程/预测任务有用，但不是普通软件开发默认技能。 | - |
| `scientific-skills/bgpt-paper-search` | Codex 可配置 MCP 使用，但主要是科学论文检索；只有你经常做论文/证据检索才放。 | MCP/外部服务 |
| `scientific-skills/citation-management` | 学术引用/BibTeX 管理有用，但偏论文写作；软件工程默认不装。 | - |
| `scientific-skills/dask` | 对大数据/并行 Python 工作流有用；做数据工程时可放。 | - |
| `scientific-skills/database-lookup` | 覆盖大量科研/API 数据库，体积大且触发面宽；只有经常做数据/文献/公共 API 查询才放。 | 79 files |
| `scientific-skills/docx` | Office 文档自动化通用，但附件多、触发面大；若常处理 Word 文档可放。 | 61 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/exploratory-data-analysis` | 通用 EDA 对数据文件分析有用；数据工程/分析频繁时可放。 | - |
| `scientific-skills/geopandas` | 如果做 GIS/地理数据工程可放；普通工程不需要。 | - |
| `scientific-skills/get-available-resources` | 适合本机重计算/ML 前的资源探测；普通代码任务不需要频繁触发。 | 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/literature-review` | 系统综述/文献调研有用，但偏科研写作；如你常做技术研究报告可放。 | - |
| `scientific-skills/matlab` | 只有维护 MATLAB/Octave 代码时需要。 | - |
| `scientific-skills/matplotlib` | Python 可视化常用；如果经常做数据分析/报告可放。 | - |
| `scientific-skills/modal` | 做 Python serverless/GPU/模型部署时有价值；不用 Modal 则不装。 | - |
| `scientific-skills/networkx` | 图算法/依赖图/知识图谱任务常用；若常处理 graph 数据可放。 | - |
| `scientific-skills/optimize-for-gpu` | CUDA/GPU 加速 Python 优化对 ML/数值计算工程有用；普通后端不需要。 | - |
| `scientific-skills/paper-lookup` | 学术论文数据库查询有用，但和现有 deep-research/search 能力有重叠；科研/论文任务多再放。 | - |
| `scientific-skills/pptx` | PowerPoint 自动化通用但附件多；常做汇报/文档交付可放。 | 59 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/pymc` | 贝叶斯建模/概率编程有通用数据科学价值；不做统计建模则不装。 | - |
| `scientific-skills/pymoo` | 多目标优化可用于工程设计/调参；不是日常开发默认。 | - |
| `scientific-skills/pytorch-lightning` | 深度学习工程常用；如果本机经常写 PyTorch 可放。 | - |
| `scientific-skills/research-lookup` | 研究检索可用，但依赖 external search/API；如果已有 deep-research 可不重复安装。 | - |
| `scientific-skills/scientific-visualization` | 发表级图表规范偏科研；做数据报告/论文图时可放。 | - |
| `scientific-skills/scikit-learn` | 经典 ML 通用；如果常做数据建模/实验可放。 | - |
| `scientific-skills/seaborn` | 快速统计可视化有用；数据分析频繁时可放。 | - |
| `scientific-skills/shap` | 模型解释工具；做 ML/风控/推荐等可放。 | - |
| `scientific-skills/simpy` | 离散事件仿真对系统容量/排队建模有用；不常用则项目级。 | - |
| `scientific-skills/statistical-analysis` | 统计检验/功效分析对数据分析有用；不是普通开发默认。 | - |
| `scientific-skills/statsmodels` | 严肃统计/时间序列建模有用；数据科学场景可放。 | - |
| `scientific-skills/sympy` | 符号数学/公式推导/代码生成有用；数学计算频繁时可放。 | - |
| `scientific-skills/timesfm-forecasting` | 时间序列预测有工程价值，但依赖模型/资源；只在预测业务中放。 | 27 files |
| `scientific-skills/torch-geometric` | 图神经网络项目可放；普通工程不需要。 | - |
| `scientific-skills/transformers` | LLM/NLP/多模态工程常用；若经常做 AI 应用/模型微调可放。 | - |
| `scientific-skills/umap-learn` | 降维/可视化/聚类辅助，数据科学场景可放。 | - |
| `scientific-skills/vaex` | 超大表格 out-of-core 分析有用；数据工程场景可放。 | - |
| `scientific-skills/xlsx` | Excel/CSV 自动化通用但附件多；经常处理表格交付时可放。 | 54 files; 仍含 Claude 文案，安装前需复核 |
| `scientific-skills/zarr-python` | 大规模数组/云存储数据工程可放；普通开发不需要。 | - |
| `top-level/codebase-migrate` | 大规模迁移有价值，但依赖 Composio/issue/CI 工作流；确认工具链后再放。 | Composio/Rube 依赖 |
| `top-level/connect` | Codex+Composio 外部 app 动作能力强，但权限面大；只在你明确使用 Composio 时放。 | Composio/Rube 依赖 |
| `top-level/create-plan` | 轻量计划 skill；Codex 已有规划能力，只有想固定“明确要求才出计划”时放。 | - |
| `top-level/datadog-logs` | 生产排障有用，但依赖 Datadog/Composio；有账号和 CLI 再放。 | Composio/Rube 依赖 |
| `top-level/deploy-pipeline` | Stripe/Supabase/Vercel 栈有用；否则过窄且可能触发高风险部署动作。 | Composio/Rube 依赖 |
| `top-level/issue-triage` | Linear/Jira backlog triage 有用，但依赖 Composio 和团队流程。 | Composio/Rube 依赖 |
| `top-level/langsmith-fetch` | LangChain/LangGraph agent 调试很有用；仅在使用 LangSmith CLI 时放。 | 仍含 Claude 文案，安装前需复核 |
| `top-level/linear` | 如果团队用 Linear，可以全局放；否则不需要。 | MCP/外部服务 |
| `top-level/notion-knowledge-capture` | 如果 Notion 是团队知识库可放；否则外部依赖和触发面偏大。 | MCP/外部服务 |
| `top-level/notion-research-documentation` | 如果技术资料在 Notion，可作为文档研究工具；否则不放。 | MCP/外部服务; 20 files |
| `top-level/notion-spec-to-implementation` | 如果 PRD/spec 在 Notion，这对工程落地有价值；否则不装。 | MCP/外部服务 |
| `top-level/paperjsx` | 结构化生成 Office/PDF 有用，但依赖 PaperJSX；需要该工具链再放。 | - |
| `top-level/pr-review-ci-fix` | PR review+CI 修复强工程价值，但依赖 Composio/GitHub/GitLab 权限；建议确认后放。 | Composio/Rube 依赖 |
| `top-level/sentry-triage` | 生产错误排障有用，但依赖 Sentry/Composio；使用 Sentry 时放。 | Composio/Rube 依赖 |
| `top-level/spreadsheet-formula-helper` | 表格公式常见但非核心开发；如果经常处理 Excel/Sheets 可放。 | - |
| `top-level/support-ticket-triage` | 支持工程/值班角色可用；普通开发不必全局放。 | - |

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

