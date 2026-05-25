---
name: obsidian-vault
description: 在 Obsidian vault 中使用 wikilinks 和 index notes 搜索、创建并管理 notes。用于用户想要在 Obsidian 中查找、创建或组织 notes 的场景。
---

# Obsidian Vault

## Vault 位置

`/mnt/d/Obsidian Vault/AI Research/`

根层级基本保持扁平。

## 命名约定

- **Index notes**：聚合相关主题（例如 `Ralph Wiggum Index.md`、`Skills Index.md`、`RAG Index.md`）
- 所有 note names 使用 **Title case**
- 不用文件夹做组织 - 改用 links 和 index notes

## 链接

- 使用 Obsidian `[[wikilinks]]` 语法：`[[Note Title]]`
- Notes 在底部链接到 dependencies/related notes
- Index notes 只是 `[[wikilinks]]` 列表

## 工作流

### 搜索 notes

```bash
# Search by filename
find "/mnt/d/Obsidian Vault/AI Research/" -name "*.md" | grep -i "keyword"

# Search by content
grep -rl "keyword" "/mnt/d/Obsidian Vault/AI Research/" --include="*.md"
```

或者直接在 vault path 上使用 Grep/Glob tools。

### 创建新 note

1. filename 使用 **Title Case**
2. 将内容写成一个学习单元（遵循 vault rules）
3. 在底部添加指向 related notes 的 `[[wikilinks]]`
4. 如果属于编号序列的一部分，使用分层编号方案

### 查找 related notes

在整个 vault 中搜索 `[[Note Title]]` 来查找 backlinks：

```bash
grep -rl "\\[\\[Note Title\\]\\]" "/mnt/d/Obsidian Vault/AI Research/"
```

### 查找 index notes

```bash
find "/mnt/d/Obsidian Vault/AI Research/" -name "*Index*"
```
