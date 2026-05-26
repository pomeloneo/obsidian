---
name: git-guardrails-codex
description: 设置 Codex hooks，在危险 git commands（push、reset --hard、clean、branch -D 等）执行前阻止它们。适用于用户想防止破坏性 git 操作、添加 git safety hooks，或在 Codex 中阻止 git push/reset 时。
---

# 设置 Git Guardrails

设置一个 PreToolUse hook，在 Codex 执行危险 git commands 之前拦截并阻止它们。

## 会阻止什么

- `git push` (all variants including `--force`)
- `git reset --hard`
- `git clean -f` / `git clean -fd`
- `git branch -D`
- `git checkout .` / `git restore .`

被阻止时，Codex 会看到一条消息，说明它没有权限访问这些 commands。

## 步骤

### 1. 询问范围

询问用户：是为 **this project only**（`.codex/hooks.json`）安装，还是为 **all projects**（`~/.codex/hooks.json`）安装？

### 2. 复制 hook script

内置 script 位于：[scripts/block-dangerous-git.sh](scripts/block-dangerous-git.sh)

根据范围将它复制到目标位置：

- **Project**: `.codex/hooks/block-dangerous-git.sh`
- **Global**: `~/.codex/hooks/block-dangerous-git.sh`

用 `chmod +x` 使它可执行。

### 3. 将 hook 添加到 settings

添加到相应的 hooks 文件：

**Project** (`.codex/hooks.json`):

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": ".codex/hooks/block-dangerous-git.sh"
          }
        ]
      }
    ]
  }
}
```

**Global** (`~/.codex/hooks.json`):

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "~/.codex/hooks/block-dangerous-git.sh"
          }
        ]
      }
    ]
  }
}
```

如果 hooks 文件已经存在，将 hook 合并到现有 `hooks.PreToolUse` array 中 — 不要覆盖其他 hooks。

### 4. 询问是否定制

询问用户是否想从 blocked list 中添加或移除任何 patterns。相应地编辑复制后的 script。

### 5. 验证

运行一次快速测试：

```bash
echo '{"tool_input":{"command":"git push origin main"}}' | <path-to-script>
```

应以 code 2 退出，并向 stderr 打印一条 BLOCKED message。
