---
name: file-organizer
description: 通过理解上下文、查找重复文件、建议更好的结构并自动化清理任务，智能整理你电脑上的 files 和 folders。减少认知负担，无需手动努力也能保持数字工作区整洁。
---

# 文件整理器

此 skill 充当你的个人整理助手，帮助你在电脑上维护清晰、符合逻辑的文件结构，而不必承担持续手动整理的心智负担。

## 何时使用此 Skill

- Downloads 文件夹混乱不堪
- 文件散落各处，导致你找不到
- 有占用空间的重复文件
- 文件夹结构已经不再合理
- 想建立更好的整理习惯
- 正在启动新项目，需要良好结构
- 在归档旧项目之前做清理

## 此 Skill 做什么

1. **分析当前结构**：审查 folders 和 files，理解你拥有的内容
2. **查找重复文件**：识别系统中的重复文件
3. **建议整理方式**：根据内容提出符合逻辑的 folder structures
4. **自动化清理**：在你批准后移动、重命名和整理 files
5. **维护上下文**：根据 file types、dates 和 content 做出智能决策
6. **减少杂乱**：识别你可能不再需要的旧文件

## 如何使用

### 从 Home Directory 开始

```
cd ~
```

然后运行 Codex 并请求帮助：

```
Help me organize my Downloads folder
```

```
Find duplicate files in my Documents folder
```

```
Review my project directories and suggest improvements
```

### 特定整理任务

```
Organize these downloads into proper folders based on what they are
```

```
Find duplicate files and help me decide which to keep
```

```
Clean up old files I haven't touched in 6+ months
```

```
Create a better folder structure for my [work/projects/photos/etc]
```

## 指令

当用户请求文件整理帮助时：

1. **理解范围**
   
   询问澄清问题：
   - 需要整理哪个目录？（Downloads、Documents、整个 home folder？）
   - 主要问题是什么？（找不到东西、重复文件、太乱、没有结构？）
   - 是否有要避开的 files 或 folders？（当前项目、敏感数据？）
   - 整理力度多大？（保守 vs. 全面清理）

2. **分析当前状态**
   
   审查目标目录：
   ```bash
   # Get overview of current structure
   ls -la [target_directory]
   
   # Check file types and sizes
   find [target_directory] -type f -exec file {} \; | head -20
   
   # Identify largest files
   du -sh [target_directory]/* | sort -rh | head -20
   
   # Count file types
   find [target_directory] -type f | sed 's/.*\.//' | sort | uniq -c | sort -rn
   ```
   
   总结发现：
   - 总 files 和 folders 数量
   - File type breakdown
   - Size distribution
   - Date ranges
   - 明显的整理问题

3. **识别整理模式**
   
   根据 files，确定逻辑分组：
   
   **按类型**：
   - Documents（PDFs、DOCX、TXT）
   - Images（JPG、PNG、SVG）
   - Videos（MP4、MOV）
   - Archives（ZIP、TAR、DMG）
   - Code/Projects（包含 code 的 directories）
   - Spreadsheets（XLSX、CSV）
   - Presentations（PPTX、KEY）
   
   **按用途**：
   - Work vs. Personal
   - Active vs. Archive
   - Project-specific
   - Reference materials
   - Temporary/scratch files
   
   **按日期**：
   - 当前 year/month
   - Previous years
   - 非常旧（archive candidates）

4. **查找重复文件**
   
   如果被要求，搜索重复文件：
   ```bash
   # Find exact duplicates by hash
   find [directory] -type f -exec md5 {} \; | sort | uniq -d
   
   # Find files with same name
   find [directory] -type f -printf '%f\n' | sort | uniq -d
   
   # Find similar-sized files
   find [directory] -type f -printf '%s %p\n' | sort -n
   ```
   
   对每一组重复文件：
   - 展示所有 file paths
   - 显示 sizes 和 modification dates
   - 建议保留哪个（通常是最新或命名最好的）
   - **重要**：删除前始终请求确认

5. **提出整理计划**
   
   在修改前给出清晰计划：
   
   ```markdown
   # Organization Plan for [Directory]
   
   ## Current State
   - X files across Y folders
   - [Size] total
   - File types: [breakdown]
   - Issues: [list problems]
   
   ## Proposed Structure
   
   ```
   [Directory]/
   ├── Work/
   │   ├── Projects/
   │   ├── Documents/
   │   └── Archive/
   ├── Personal/
   │   ├── Photos/
   │   ├── Documents/
   │   └── Media/
   └── Downloads/
       ├── To-Sort/
       └── Archive/
   ```
   
   ## Changes I'll Make
   
   1. **Create new folders**: [list]
   2. **Move files**:
      - X PDFs → Work/Documents/
      - Y images → Personal/Photos/
      - Z old files → Archive/
   3. **Rename files**: [any renaming patterns]
   4. **Delete**: [duplicates or trash files]
   
   ## Files Needing Your Decision
   
   - [List any files you're unsure about]
   
   Ready to proceed? (yes/no/modify)
   ```

6. **执行整理**
   
   批准后，系统化地整理：
   
   ```bash
   # Create folder structure
   mkdir -p "path/to/new/folders"
   
   # Move files with clear logging
   mv "old/path/file.pdf" "new/path/file.pdf"
   
   # Rename files with consistent patterns
   # Example: "YYYY-MM-DD - Description.ext"
   ```
   
   **重要规则**：
   - 删除任何内容前始终确认
   - 记录所有移动操作，以便潜在 undo
   - 保留原始 modification dates
   - 妥善处理 filename conflicts
   - 遇到意外情况时停止并询问

7. **提供总结和维护提示**
   
   整理完成后：
   
   ```markdown
   # Organization Complete! ✨
   
   ## What Changed
   
   - Created [X] new folders
   - Organized [Y] files
   - Freed [Z] GB by removing duplicates
   - Archived [W] old files
   
   ## New Structure
   
   [Show the new folder tree]
   
   ## Maintenance Tips
   
   To keep this organized:
   
   1. **Weekly**: Sort new downloads
   2. **Monthly**: Review and archive completed projects
   3. **Quarterly**: Check for new duplicates
   4. **Yearly**: Archive old files
   
   ## Quick Commands for You
   
   ```bash
   # Find files modified this week
   find . -type f -mtime -7
   
   # Sort downloads by type
   [custom command for their setup]
   
   # Find duplicates
   [custom command]
   ```
   
   Want to organize another folder?
   ```

## 示例

### 示例 1：整理 Downloads（来自 Justin Dielmann）

**User**: "My Downloads folder is a mess with 500+ files. Help me organize it."

**Process**:
1. 分析 Downloads folder
2. 找出 patterns：work docs、personal photos、installers、random PDFs
3. 提出结构：
   - Downloads/
     - Work/
     - Personal/
     - Installers/（DMG、PKG files）
     - Archive/
     - ToSort/（需要决策的内容）
4. 请求确认
5. 根据内容和名称智能移动 files
6. 结果：500 files → 5 个有序 folders

### 示例 2：查找并移除重复文件

**User**: "Find duplicate files in my Documents and help me decide which to keep."

**Output**:
```markdown
# Found 23 Sets of Duplicates (156 MB total)

## Duplicate Set 1: "proposal.pdf"
- `/Documents/proposal.pdf` (2.3 MB, modified: 2024-03-15)
- `/Documents/old/proposal.pdf` (2.3 MB, modified: 2024-03-15)
- `/Desktop/proposal.pdf` (2.3 MB, modified: 2024-03-10)

**Recommendation**: Keep `/Documents/proposal.pdf` (most recent in correct location)
Delete the other 2 copies?

[Continue for all duplicates...]
```

### 示例 3：重构 Projects Folder

**User**: "Review my ~/Projects directory and suggest improvements."

**Output**:
```markdown
# Analysis of ~/Projects

## Current Structure Issues
- Mix of active and archived projects (3+ years old)
- No consistent naming convention
- Some projects at root, others in random subfolders
- Duplicate folders (project-name, project-name-old, project-name-v2)

## Proposed Structure

```
Projects/
├── Active/
│   ├── client-work/
│   ├── side-projects/
│   └── learning/
├── Archive/
│   ├── 2022/
│   ├── 2023/
│   └── 2024/
└── Templates/
```

## Specific Changes
1. Move 12 projects not touched since 2022 → Archive/
2. Consolidate 4 duplicate project folders
3. Rename projects to consistent format: "client-name-project-name"
4. Create Archive for old work

Want me to implement this?
```

### 示例 4：按日期整理照片

**User**: "Organize my photo folders by year and month."

**Output**：创建如下结构：
```
Photos/
├── 2023/
│   ├── 01-January/
│   ├── 02-February/
│   └── ...
├── 2024/
│   ├── 01-January/
│   └── ...
└── Unsorted/
```

然后根据 EXIF data 或 file modification dates 移动 photos。

## 常见整理任务

### Downloads Cleanup
```
Organize my Downloads folder - move documents to Documents, 
images to Pictures, keep installers separate, and archive files 
older than 3 months.
```

### Project Organization
```
Review my Projects folder structure and help me separate active 
projects from old ones I should archive.
```

### Duplicate Removal
```
Find all duplicate files in my Documents folder and help me 
decide which ones to keep.
```

### Desktop Cleanup
```
My Desktop is covered in files. Help me organize everything into 
my Documents folder properly.
```

### Photo Organization
```
Organize all photos in this folder by date (year/month) based 
on when they were taken.
```

### Work/Personal Separation
```
Help me separate my work files from personal files across my 
Documents folder.
```

## Pro Tips

1. **从小处开始**：先从一个混乱 folder（如 Downloads）开始建立信任
2. **定期维护**：每周清理 Downloads
3. **一致命名**：重要文件使用 "YYYY-MM-DD - Description" 格式
4. **积极归档**：将旧 projects 移到 Archive，而不是删除
5. **Active 独立**：在 active 和 archived work 之间保持清晰边界
6. **信任流程**：让 Codex 承担“东西该放哪里”的认知负担

## 最佳实践

### Folder Naming
- 使用清晰、有描述性的名称
- 避免空格（使用 hyphens 或 underscores）
- 要具体："client-proposals" 而不是 "docs"
- 使用 prefixes 来排序："01-current"、"02-archive"

### File Naming
- 包含日期："2024-10-17-meeting-notes.md"
- 具备描述性："q3-financial-report.xlsx"
- 避免在名称中使用 version numbers（改用 version control）
- 移除 download artifacts："document-final-v2 (1).pdf" → "document.pdf"

### 何时归档
- 6+ 个月未触碰的 projects
- 完成后未来可能需要引用的 work
- 迁移到新系统后的旧版本
- 你不舍得删除的 files（先归档）

## 相关用例

- 为新电脑建立整理结构
- 为 backup/archiving 准备 files
- 在 storage cleanup 前清理
- 整理 shared team folders
- 结构化 new project directories
