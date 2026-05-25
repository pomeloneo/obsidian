---
name: tailored-resume-generator
description: 分析 job descriptions 并生成量身定制的 resumes，突出相关经验、技能和成就，以最大化面试机会
---

# Tailored Resume Generator

## 何时使用此 Skill

- 申请特定职位
- 针对不同行业或角色定制 resume
- 为职业转型突出相关经验
- 针对 ATS（Applicant Tracking Systems）优化 resume
- 为不同 job applications 创建多个 resume 版本
- 强调 job postings 中提到的特定技能

## 此 Skill 做什么

1. **分析 Job Descriptions**：从 job postings 中提取关键要求、技能、资质和关键词
2. **识别优先级**：根据 job description 的语言和结构判断雇主最看重什么
3. **定制内容**：重新组织并强调相关经验、技能和成就
4. **优化关键词**：在 resume 中自然融入 ATS-friendly keywords
5. **专业排版**：创建干净、专业、适合多种格式的 resume layouts
6. **提供建议**：提出改进建议，并指出需要补足的 gaps

## 如何使用

### 基本用法
提供 job description 和你的背景信息：

```
I'm applying for this job:

[paste job description]

Here's my background:
- 5 years as software engineer at TechCorp
- Led team of 3 developers on mobile app project
- Expert in Python, JavaScript, React
- Computer Science degree from State University
```

### 使用现有 Resume
上传或粘贴你的当前 resume，并附上 job description：

```
Please tailor my resume for this position:

Job Description:
[paste job description]

My Current Resume:
[paste resume content]
```

### 职业转型
当转换行业或角色时：

```
I'm transitioning from marketing to product management.
Here's the job I'm applying for:

[paste job description]

My transferable experience:
- 7 years in digital marketing
- Led cross-functional teams
- Managed product launches
- Data analysis and A/B testing
```

## 示例

**用户请求：**
```
I need a tailored resume for this job:

Senior Data Analyst Position

Requirements:
- 5+ years experience in data analysis
- Expert in SQL, Python, and data visualization tools
- Experience with A/B testing and statistical analysis
- Strong communication skills to present findings
- Healthcare industry experience preferred

My background:
- Data Analyst at RetailCo (2019-2024)
- Created dashboards using Tableau and Power BI
- Built Python scripts for data automation
- Worked with marketing team on campaign analysis
- Business Analytics degree
- Also did 1 year internship at HealthPlus clinic
```

**生成输出：**

```markdown
# JOHN DOE
Email: john.doe@email.com | Phone: (555) 123-4567 | LinkedIn: linkedin.com/in/johndoe

## PROFESSIONAL SUMMARY
Results-driven Data Analyst with 5+ years of experience leveraging SQL, Python, and advanced
visualization tools to deliver actionable insights. Proven track record in statistical analysis,
A/B testing, and cross-functional collaboration. Healthcare industry experience with strong
ability to communicate complex data findings to stakeholders.

## TECHNICAL SKILLS
- **Data Analysis & Programming**: SQL, Python, Statistical Analysis, A/B Testing
- **Visualization Tools**: Tableau, Power BI, Advanced Dashboard Development
- **Data Management**: Data Automation, ETL Processes, Database Optimization
- **Business Intelligence**: Campaign Analytics, Performance Metrics, KPI Tracking

## PROFESSIONAL EXPERIENCE

**Data Analyst** | RetailCo | 2019 - 2024
- Designed and implemented 50+ SQL queries and Python automation scripts, reducing manual
  data processing time by 60%
- Conducted rigorous A/B testing and statistical analysis for marketing campaigns,
  improving campaign ROI by 35%
- Built interactive Tableau and Power BI dashboards for executive team, enabling
  data-driven decision making
- Presented analytical findings to cross-functional stakeholders including marketing,
  operations, and executive leadership
- Collaborated with marketing team to analyze customer behavior patterns and optimize
  targeting strategies

**Data Analysis Intern** | HealthPlus Clinic | 2018 - 2019
- Supported healthcare analytics initiatives by analyzing patient data and operational metrics
- Gained exposure to healthcare industry data management and HIPAA compliance requirements
- Assisted in creating reports for clinical staff to improve patient care workflows

## EDUCATION

**Bachelor of Science in Business Analytics**
State University | Graduated 2018

## KEY ACHIEVEMENTS
- Reduced data processing time by 60% through Python automation
- Improved marketing campaign ROI by 35% through A/B testing and optimization
- Created data visualization system now used across entire organization
```

**补充建议：**
- 考虑添加任何具体 healthcare projects 或 certifications
- 尽可能用 metrics 量化更多成就
- 如果有 R 或 advanced statistical methods 经验，请加入
- 考虑提及对 healthcare regulations（HIPAA 等）的熟悉程度

---

## Instructions

当用户请求定制 resume 时：

### 1. 收集信息

**Job Description 分析**：
- 如果未提供，请请求完整 job description
- 询问 company name 和 job title

**Candidate Background**：
- 如果用户提供现有 resume，以它为基础
- 如果没有，请请求：
  - Work history（job titles、companies、dates、responsibilities）
  - Education background
  - Key skills 和 technical proficiencies
  - Notable achievements 和 metrics
  - Certifications 或 awards
  - 任何其他相关信息

### 2. 分析 Job Requirements

提取并排序：
- **Must-have qualifications**：Years of experience、required skills、education
- **Key skills**：Technical tools、methodologies、competencies
- **Soft skills**：Communication、leadership、teamwork
- **Industry knowledge**：Domain-specific experience
- **Keywords**：用于 ATS optimization 的重复 terms、phrases 和 buzzwords
- **Company values**：来自 job description 的 cultural fit indicators

创建心智映射：
- Priority 1：关键要求（deal-breakers）
- Priority 2：重要资质（strongly desired）
- Priority 3：Nice-to-have skills（bonus points）

### 3. 将 Candidate Experience 映射到 Requirements

针对每个 job requirement：
- 从 candidate background 中识别匹配经验
- 如果没有直接匹配，寻找 transferable skills
- 记录需要处理或弱化的 gaps
- 识别要突出的独特优势

### 4. 构建 Tailored Resume

**Professional Summary**（3-4 行）：
- 以目标 role/field 的 years of experience 开头
- 包含 job description 中最重要的 3-4 个 required skills
- 如相关，提及 industry experience
- 突出 unique value proposition

**Technical/Core Skills Section**：
- 按匹配 job requirements 的类别分组 skills
- 首先列出 required tools 和 technologies
- 使用 job description 中的确切术语
- 只包含可由经验支撑的 skills

**Professional Experience**：
- 对每个 role，强调与 job requirements 对齐的 responsibilities 和 achievements
- 使用 action verbs：Led、Developed、Implemented、Optimized、Managed、Created、Analyzed
- **量化成就**：包含 numbers、percentages、timeframes、scale
- 重新排序 bullet points，优先展示最相关经验
- 自然使用 job description 中的 keywords
- 格式：**[Action Verb] + [What] + [How/Why] + [Result/Impact]**

**Education**：
- 列出与职位相关的 degrees、certifications
- 如果是早期职业阶段，包含 relevant coursework
- 添加匹配 job requirements 的 certifications

**Optional Sections**（如适用）：
- Certifications & Licenses
- Publications or Speaking Engagements
- Awards & Recognition
- Volunteer Work（如果与 role 相关）
- Projects（尤其是 technical roles）

### 5. 针对 ATS（Applicant Tracking Systems）优化

- 使用标准 section headings（Professional Experience、Education、Skills）
- 自然融入 job description 中的精确 keywords
- 避免 tables、graphics、headers/footers 或复杂格式
- 使用标准 fonts 和 bullet points
- 同时包含 acronyms 和 full terms（例如 "SQL (Structured Query Language)"）
- 在真实的前提下匹配 job title terminology

### 6. 格式化并呈现

**格式选项**：
- **Markdown**：干净、可读、易复制
- **Plain Text**：ATS-optimized，适用于所有系统
- **Tips for Word/PDF**：提供格式指导

**Resume 结构指南**：
- <10 年经验控制在 1 页，10+ 年经验控制在 2 页
- 使用一致的格式和间距
- 确保 contact information 醒目
- 使用 reverse chronological order（最近经历在前）
- 保持干净、可扫读、留白适当的布局

### 7. 提供战略建议

呈现 tailored resume 后，提供：

**Strengths Analysis**：
- 该 candidate 具备竞争力的原因
- 可在 cover letter 或 interview 中强调的独特资质

**Gap Analysis**：
- 尚未完全满足的要求
- 处理 gaps 的建议（courses、projects、reframing experience）

**Interview Preparation Tips**：
- 与 resume 对齐的关键 talking points
- 基于 job requirements 准备的 stories
- 能体现匹配度的问题

**Cover Letter Hooks**：
- 建议 2-3 个 cover letter 开头句
- 可展开的关键 achievements

### 8. 迭代和细化

询问用户是否想：
- 调整重点或语气
- 添加或删除 sections
- 为不同 roles 生成替代版本
- 创建格式变体（traditional vs. modern）
- 开发 role-specific versions（如果申请多个相似职位）

### 9. 遵循最佳实践

**Do**：
- 真实准确，不要编造经验
- 使用行业标准术语
- 用具体 metrics 量化成就
- 为具体职位定制每份 resume
- 校对语法和一致性
- 保持语言简洁有力

**Don't**：
- 包含个人信息（年龄、婚姻状况、照片，除非被要求）
- 使用第一人称代词（I、me、my）
- 包含 references（"available upon request" 已过时）
- 如果职业经历超过 20 年，不要列出每份工作（聚焦相关和近期经验）
- 使用未定制的通用 templates
- 除非非常资深的 role，否则不要超过 2 页

### 10. 特殊考虑

**Career Changers**：
- 使用 functional 或 hybrid resume format
- 强调 transferable skills
- 在 summary 中创建有说服力的叙事
- 聚焦相关 projects 和 coursework

**Recent Graduates**：
- 以 education 开头
- 包含 relevant coursework、projects、internships
- 强调学生组织中的 leadership
- 如果 GPA 为 3.5+，则包含 GPA

**Senior Executives**：
- 以 executive summary 开头
- 聚焦 leadership 和 strategic impact
- 包含 board memberships、speaking engagements
- 强调 revenue growth、team building、vision

**Technical Roles**：
- 显著包含 technical skills section
- 列出 programming languages、frameworks、tools
- 包含 GitHub、portfolio 或 project links
- 提及 methodologies（Agile、Scrum 等）

**Creative Roles**：
- 包含 portfolio 链接
- 突出 creative achievements 和 campaigns
- 提及 tools 和 software proficiencies
- 考虑更有创意的 formatting（同时保持 ATS compatibility）

---

## 获得最佳结果的提示

- **具体**：提供完整 job descriptions 和详细 background information
- **分享 metrics**：描述经验时包含 numbers、percentages 和 quantifiable achievements
- **说明格式偏好**：让 skill 知道你需要 ATS-optimized、creative 还是 traditional format
- **提及约束**：分享任何具体要求（page limits、sections to include/exclude）
- **迭代**：可以要求 revisions 或 alternative approaches
- **多份申请**：为不同 roles 生成单独的 tailored versions

## 隐私说明

此 skill 会处理你的个人和职业信息来生成 tailored resumes。提交前务必审阅输出，确保准确且适当。删除或修改你不希望与潜在雇主分享的任何信息。
