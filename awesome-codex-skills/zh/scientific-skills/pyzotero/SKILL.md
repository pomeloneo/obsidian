---
name: pyzotero
description: 使用 pyzotero Python client 与 Zotero reference management libraries 交互。通过 Zotero Web API v3 检索、创建、更新和删除 items、collections、tags 和 attachments。在需要以编程方式处理 Zotero libraries、管理 bibliographic references、导出 citations、搜索 library 内容、上传 PDF attachments，或构建集成 Zotero 的 research automation workflow 时使用此 skill。
allowed-tools: Read Write Edit Bash
license: MIT License
metadata:
    skill-author: K-Dense Inc.
---

# Pyzotero

Pyzotero 是 [Zotero API v3](https://www.zotero.org/support/dev/web_api/v3/start) 的 Python wrapper。可用它以编程方式管理 Zotero libraries：读取 items 和 collections，创建和更新 references，上传 attachments，管理 tags，并导出 citations。

## Authentication Setup

**必需 credentials** — 从 https://www.zotero.org/settings/keys 获取：
- **User ID**：显示为 "Your userID for use in API calls"
- **API Key**：在 https://www.zotero.org/settings/keys/new 创建
- **Library ID**：对于 group libraries，是 group URL 中 `/groups/` 后面的整数

将 credentials 存储在环境变量或 `.env` 文件中：
```
ZOTERO_LIBRARY_ID=your_user_id
ZOTERO_API_KEY=your_api_key
ZOTERO_LIBRARY_TYPE=user  # or "group"
```

完整设置细节见 [references/authentication.md](references/authentication.md)。

## 安装

```bash
uv add pyzotero
# or with CLI support:
uv add "pyzotero[cli]"
```

## 快速开始

```python
from pyzotero import Zotero

zot = Zotero(library_id='123456', library_type='user', api_key='ABC1234XYZ')

# Retrieve top-level items (returns 100 by default)
items = zot.top(limit=10)
for item in items:
    print(item['data']['title'], item['data']['itemType'])

# Search by keyword
results = zot.items(q='machine learning', limit=20)

# Retrieve all items (use everything() for complete results)
all_items = zot.everything(zot.items())
```

## 核心概念

- 一个 `Zotero` instance 绑定到单个 library（user 或 group）。所有方法都作用于该 library。
- Item data 位于 `item['data']`。访问字段如 `item['data']['title']`、`item['data']['creators']`。
- Pyzotero 默认返回 100 个 items（API 默认是 25）。使用 `zot.everything(zot.items())` 获取全部 items。
- Write methods 成功时返回 `True`，失败时抛出 `ZoteroError`。

## Reference Files

| File | Contents |
|------|----------|
| [references/authentication.md](references/authentication.md) | Credentials、library types、local mode |
| [references/read-api.md](references/read-api.md) | 检索 items、collections、tags、groups |
| [references/search-params.md](references/search-params.md) | Filtering、sorting、search parameters |
| [references/write-api.md](references/write-api.md) | 创建、更新、删除 items |
| [references/collections.md](references/collections.md) | Collection CRUD operations |
| [references/tags.md](references/tags.md) | Tag retrieval and management |
| [references/files-attachments.md](references/files-attachments.md) | File retrieval and attachment uploads |
| [references/exports.md](references/exports.md) | BibTeX、CSL-JSON、bibliography export |
| [references/pagination.md](references/pagination.md) | follow()、everything()、generators |
| [references/full-text.md](references/full-text.md) | Full-text content indexing and retrieval |
| [references/saved-searches.md](references/saved-searches.md) | Saved search management |
| [references/cli.md](references/cli.md) | Command-line interface usage |
| [references/error-handling.md](references/error-handling.md) | Errors and exception handling |

## 常见 Patterns

### 获取并修改 item
```python
item = zot.item('ITEMKEY')
item['data']['title'] = 'New Title'
zot.update_item(item)
```

### 从 template 创建 item
```python
template = zot.item_template('journalArticle')
template['title'] = 'My Paper'
template['creators'][0] = {'creatorType': 'author', 'firstName': 'Jane', 'lastName': 'Doe'}
zot.create_items([template])
```

### 导出为 BibTeX
```python
zot.add_parameters(format='bibtex')
bibtex = zot.top(limit=50)
# bibtex is a bibtexparser BibDatabase object
print(bibtex.entries)
```

### Local mode（read-only，无需 API key）
```python
zot = Zotero(library_id='123456', library_type='user', local=True)
items = zot.items()
```
