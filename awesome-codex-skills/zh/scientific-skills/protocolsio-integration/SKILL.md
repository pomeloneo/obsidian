---
name: protocolsio-integration
description: 用于管理 scientific protocols 的 protocols.io API 集成。当使用 protocols.io 搜索、创建、更新或发布 protocols；管理 protocol steps 和 materials；处理 discussions 和 comments；组织 workspaces；上传和管理 files；或将 protocols.io 功能集成到 workflows 中时使用此 skill。适用于 protocol discovery、collaborative protocol development、experiment tracking、lab protocol management 和 scientific documentation。
license: Unknown
metadata:
    skill-author: K-Dense Inc.
---

# Protocols.io Integration

## 概览

Protocols.io 是用于开发、共享和管理 scientific protocols 的综合平台。此 skill 提供与 protocols.io API v3 的完整集成，支持以程序方式访问 protocols、workspaces、discussions、file management 和 collaboration features。

## 何时使用此 Skill

在以下任何场景中使用 protocols.io 时使用此 skill：

- **Protocol Discovery**：通过 keywords、DOI 或 category 搜索现有 protocols
- **Protocol Management**：创建、更新或发布 scientific protocols
- **Step Management**：添加、编辑或组织 protocol steps 和 procedures
- **Collaborative Development**：与团队成员共同处理 shared protocols
- **Workspace Organization**：管理 lab 或 institutional protocol repositories
- **Discussion & Feedback**：添加或回复 protocol comments
- **File Management**：向 protocols 上传 data files、images 或 documents
- **Experiment Tracking**：记录 protocol executions 和 results
- **Data Export**：备份或迁移 protocol collections
- **Integration Projects**：构建与 protocols.io 交互的 tools

## 核心能力

此 skill 围绕五个主要能力领域提供综合指导：

### 1. Authentication 与 Access

使用 access tokens 和 OAuth flows 管理 API authentication。包括 client access tokens（用于 personal content）和 OAuth tokens（用于 multi-user applications）。

**关键 operations：**
- 为 OAuth flow 生成 authorization links
- 将 authorization codes 交换为 access tokens
- 刷新 expired tokens
- 管理 rate limits 和 permissions

**参考：** 阅读 `references/authentication.md`，了解详细 authentication procedures、OAuth implementation 和 security best practices。

### 2. Protocol Operations

从创建到发布的完整 protocol lifecycle management。

**关键 operations：**
- 通过 keywords、filters 或 DOI 搜索和发现 protocols
- 取回包含所有 steps 的详细 protocol information
- 创建带 metadata 和 tags 的新 protocols
- 更新 protocol information 和 settings
- 管理 protocol steps（create、update、delete、reorder）
- 处理 protocol materials 和 reagents
- 通过 DOI issuance 发布 protocols
- Bookmark protocols 以便快速访问
- 生成 protocol PDFs

**参考：** 阅读 `references/protocols_api.md`，了解综合 protocol management guidance，包括 API endpoints、parameters、common workflows 和 examples。

### 3. Discussions 与 Collaboration

通过 comments 和 discussions 实现 community engagement。

**关键 operations：**
- 查看 protocol-level 和 step-level comments
- 创建新 comments 和 threaded replies
- 编辑或删除自己的 comments
- 分析 discussion patterns 和 feedback
- 回复用户 questions 和 issues

**参考：** 阅读 `references/discussions.md`，了解 discussion management、comment threading 和 collaboration workflows。

### 4. Workspace Management

使用 role-based permissions 在 team workspaces 中组织 protocols。

**关键 operations：**
- 列出并访问 user workspaces
- 取回 workspace details 和 member lists
- 请求 access 或加入 workspaces
- 列出 workspace-specific protocols
- 在 workspaces 内创建 protocols
- 管理 workspace permissions 和 collaboration

**参考：** 阅读 `references/workspaces.md`，了解 workspace organization、permission management 和 team collaboration patterns。

### 5. File Operations

上传、组织并管理与 protocols 相关的 files。

**关键 operations：**
- 搜索 workspace files 和 folders
- 上传带 metadata 和 tags 的 files
- 下载 files 并验证 uploads
- 将 files 组织到 folder hierarchies 中
- 更新 file metadata
- 删除和恢复 files
- 管理 storage 和 organization

**参考：** 阅读 `references/file_manager.md`，了解 file upload procedures、organization strategies 和 storage management。

### 6. Additional Features

包括 profiles、notifications 和 exports 在内的补充功能。

**关键 operations：**
- 管理 user profiles 和 settings
- 查询 recently published protocols
- 创建并跟踪 experiment records
- 接收并管理 notifications
- 导出 organization data 以归档

**参考：** 阅读 `references/additional_features.md`，了解 profile management、publication discovery、experiment tracking 和 data export。

## Getting Started

### Step 1：Authentication Setup

使用任何 protocols.io API 功能前：

1. 获取 access token（CLIENT_ACCESS_TOKEN 或 OAUTH_ACCESS_TOKEN）
2. 阅读 `references/authentication.md` 了解详细 authentication procedures
3. 安全存储 token
4. 在所有 requests 中包含：`Authorization: Bearer YOUR_TOKEN`

### Step 2：Identify Your Use Case

确定哪个 capability area 对应你的需求：

- **处理 protocols？** → 阅读 `references/protocols_api.md`
- **管理 team protocols？** → 阅读 `references/workspaces.md`
- **处理 comments/feedback？** → 阅读 `references/discussions.md`
- **上传 files/data？** → 阅读 `references/file_manager.md`
- **跟踪 experiments 或 profiles？** → 阅读 `references/additional_features.md`

### Step 3：Implement Integration

遵循相关 reference files 中的 guidance：

- 每个 reference 都包含详细 endpoint documentation
- 指定了 API parameters 和 request/response formats
- 提供带 examples 的 common use cases 和 workflows
- 包含 best practices 和 error handling guidance

## Base URL 与 Request Format

所有 API requests 使用 base URL：
```
https://protocols.io/api/v3
```

所有 requests 都需要 Authorization header：
```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

大多数 endpoints 支持 JSON request/response format，使用 `Content-Type: application/json`。

## Content Format Options

许多 endpoints 支持 `content_format` parameter，用于控制返回 protocol content 的方式：

- `json`: Draft.js JSON format (default)
- `html`: HTML format
- `markdown`: Markdown format

作为 query parameter 包含：`?content_format=html`

## Rate Limiting

注意 API rate limits：

- **Standard endpoints**：每用户每分钟 100 requests
- **PDF endpoint**：5 requests/minute（signed-in），3 requests/minute（unsigned）

对 rate limit errors（HTTP 429）实现 exponential backoff。

## 常见 Workflows

### Workflow 1：Import and Analyze Protocol

要分析 protocols.io 中的现有 protocol：

1. **Search**：使用带 keywords 的 `GET /protocols` 查找 relevant protocols
2. **Retrieve**：用 `GET /protocols/{protocol_id}` 获取完整 details
3. **Extract**：解析 steps、materials 和 metadata 进行分析
4. **Review discussions**：检查 `GET /protocols/{id}/comments` 获取 user feedback
5. **Export**：如需 offline reference，生成 PDF

**Reference files**：`protocols_api.md`、`discussions.md`

### Workflow 2：Create and Publish Protocol

要创建新 protocol 并带 DOI 发布：

1. **Authenticate**：确保有有效 access token（见 `authentication.md`）
2. **Create**：使用带 title 和 description 的 `POST /protocols`
3. **Add steps**：对每个 step，使用 `POST /protocols/{id}/steps`
4. **Add materials**：在 step components 中记录 reagents
5. **Review**：验证所有 content 完整且准确
6. **Publish**：使用 `POST /protocols/{id}/publish` 签发 DOI

**Reference files**：`protocols_api.md`、`authentication.md`

### Workflow 3：Collaborative Lab Workspace

要设置 team protocol management：

1. **Create/join workspace**：访问或请求 workspace membership（见 `workspaces.md`）
2. **Organize structure**：为 lab protocols 创建 folder hierarchy（见 `file_manager.md`）
3. **Create protocols**：对 team protocols 使用 `POST /workspaces/{id}/protocols`
4. **Upload files**：添加 experimental data 和 images
5. **Enable discussions**：团队成员可以 comment 并提供 feedback
6. **Track experiments**：使用 experiment records 记录 protocol executions

**Reference files**：`workspaces.md`、`file_manager.md`、`protocols_api.md`、`discussions.md`、`additional_features.md`

### Workflow 4：Experiment Documentation

要跟踪 protocol executions 和 results：

1. **Execute protocol**：在 laboratory 中执行 protocol
2. **Upload data**：使用 File Manager API 上传 results（见 `file_manager.md`）
3. **Create record**：使用 `POST /protocols/{id}/runs` 记录 execution
4. **Link files**：在 experiment record 中引用 uploaded data files
5. **Note modifications**：记录任何 protocol deviations 或 optimizations
6. **Analyze**：审阅 multiple runs 以进行 reproducibility assessment

**Reference files**：`additional_features.md`、`file_manager.md`、`protocols_api.md`

### Workflow 5：Protocol Discovery and Citation

要在 research 中查找和引用 protocols：

1. **Search**：使用 `GET /publications` 查询 published protocols
2. **Filter**：使用 category 和 keyword filters 查找 relevant protocols
3. **Review**：阅读 protocol details 和 community comments
4. **Bookmark**：使用 `POST /protocols/{id}/bookmarks` 保存有用 protocols
5. **Cite**：在 publications 中使用 protocol DOI（proper attribution）
6. **Export PDF**：生成 formatted PDF 作为 offline reference

**Reference files**：`protocols_api.md`、`additional_features.md`

## Python Request Examples

### Basic Protocol Search

```python
import requests

token = "YOUR_ACCESS_TOKEN"
headers = {"Authorization": f"Bearer {token}"}

# Search for CRISPR protocols
response = requests.get(
    "https://protocols.io/api/v3/protocols",
    headers=headers,
    params={
        "filter": "public",
        "key": "CRISPR",
        "page_size": 10,
        "content_format": "html"
    }
)

protocols = response.json()
for protocol in protocols["items"]:
    print(f"{protocol['title']} - {protocol['doi']}")
```

### Create New Protocol

```python
import requests

token = "YOUR_ACCESS_TOKEN"
headers = {
    "Authorization": f"Bearer {token}",
    "Content-Type": "application/json"
}

# Create protocol
data = {
    "title": "CRISPR-Cas9 Gene Editing Protocol",
    "description": "Comprehensive protocol for CRISPR gene editing",
    "tags": ["CRISPR", "gene editing", "molecular biology"]
}

response = requests.post(
    "https://protocols.io/api/v3/protocols",
    headers=headers,
    json=data
)

protocol_id = response.json()["item"]["id"]
print(f"Created protocol: {protocol_id}")
```

### Upload File to Workspace

```python
import requests

token = "YOUR_ACCESS_TOKEN"
headers = {"Authorization": f"Bearer {token}"}

# Upload file
with open("data.csv", "rb") as f:
    files = {"file": f}
    data = {
        "folder_id": "root",
        "description": "Experimental results",
        "tags": "experiment,data,2025"
    }

    response = requests.post(
        "https://protocols.io/api/v3/workspaces/12345/files/upload",
        headers=headers,
        files=files,
        data=data
    )

file_id = response.json()["item"]["id"]
print(f"Uploaded file: {file_id}")
```

## Error Handling

为 API requests 实现健壮的 error handling：

```python
import requests
import time

def make_request_with_retry(url, headers, max_retries=3):
    for attempt in range(max_retries):
        try:
            response = requests.get(url, headers=headers)

            if response.status_code == 200:
                return response.json()
            elif response.status_code == 429:  # Rate limit
                retry_after = int(response.headers.get('Retry-After', 60))
                time.sleep(retry_after)
                continue
            elif response.status_code >= 500:  # Server error
                time.sleep(2 ** attempt)  # Exponential backoff
                continue
            else:
                response.raise_for_status()

        except requests.exceptions.RequestException as e:
            if attempt == max_retries - 1:
                raise
            time.sleep(2 ** attempt)

    raise Exception("Max retries exceeded")
```

## Reference Files

根据任务加载合适的 reference file：

- **`authentication.md`**：OAuth flows、token management、rate limiting
- **`protocols_api.md`**：Protocol CRUD、steps、materials、publishing、PDFs
- **`discussions.md`**：Comments、replies、collaboration
- **`workspaces.md`**：Team workspaces、permissions、organization
- **`file_manager.md`**：File upload、folders、storage management
- **`additional_features.md`**：Profiles、publications、experiments、notifications

如需加载 reference file，在需要特定功能时从 `references/` directory 读取该文件。

## Best Practices

1. **Authentication**：安全存储 tokens，绝不要放入 code 或 version control
2. **Rate Limiting**：实现 exponential backoff 并遵守 rate limits
3. **Error Handling**：适当处理所有 HTTP error codes
4. **Data Validation**：API calls 前验证 input
5. **Documentation**：彻底记录 protocol steps
6. **Collaboration**：使用 comments 和 discussions 进行 team communication
7. **Organization**：保持一致的 naming 和 tagging conventions
8. **Versioning**：更新时跟踪 protocol versions
9. **Attribution**：使用 DOIs 正确引用 protocols
10. **Backup**：定期导出 important protocols 和 workspace data

## 其他资源

- **Official API Documentation**：https://apidoc.protocols.io/
- **Protocols.io Platform**：https://www.protocols.io/
- **Support**：联系 protocols.io support 处理 API access 和 technical issues
- **Community**：参与 protocols.io community，获取 best practices

## Troubleshooting

**Authentication Issues：**
- 验证 token 有效且未过期
- 检查 Authorization header format：`Bearer YOUR_TOKEN`
- 确保 token type 合适（CLIENT vs OAUTH）

**Rate Limiting：**
- 对 429 errors 实现 exponential backoff
- 监控 request frequency
- 考虑缓存 frequent requests

**Permission Errors：**
- 验证 workspace/protocol access permissions
- 检查 workspace 中的 user role
- 如果无权限访问，确保 protocol 不是 private

**File Upload Failures：**
- 根据 workspace limits 检查 file size
- 验证 file type 受支持
- 确保 multipart/form-data encoding 正确

详细 troubleshooting guidance 请参考覆盖各 capability area 的具体 reference files。
