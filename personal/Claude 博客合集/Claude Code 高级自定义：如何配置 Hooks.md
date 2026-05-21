即使是流畅的 [Claude Code](https://www.claude.com/product/claude-code) 工作流，随着时间推移也会积累摩擦点。每次 Claude 写文件时，都需要手动运行 [Prettier](https://prettier.io/)。每次运行 npm test 时，都会出现相同的权限提示。每次会话开始时，都要把相同的样板项目上下文粘贴到第一条消息中。

好消息是？[Hooks](https://code.claude.com/docs/en/hooks-guide) 可以消除这些摩擦点。它们充当可配置的触发器，在特定操作之前或之后触发，让你将自定义逻辑、脚本和命令直接注入到 Claude 的操作中。

本文面向已熟悉 Claude Code 基础的开发者，涵盖高级配置。读完后，你将理解八种 Hook 类型、何时使用、如何配置以及如何调试。

## 什么是 Hook？

Hook 是你创建的自定义 Shell 命令，在 Claude Code 会话中发生目标事件时自动执行，例如 Claude 即将写入文件或你提交提示时。你可以为大量场景指定 Hook：拦截操作、注入智能体上下文、自动化审批或阻止操作。

Hook 通过 JSON 结构在设置文件中配置，包含事件名称、匹配器（过滤触发 Hook 的工具）和要运行的命令。它们在你的本地环境中以你的用户权限执行，通过 stdin 接收触发事件的信息，通过退出码和 stdout 进行通信。

## 为什么使用 Hook？

Hook 解决三类问题：

**消除重复手动步骤**。PostToolUse Hook 在每次文件变更后自动运行格式化工具，PermissionRequest Hook 自动批准 npm test。

**自动执行项目特定规则**。阻止危险命令、验证文件路径、确保遵循命名约定。这些护栏每次都会运行。

**无需手动注入动态上下文**。SessionStart Hook 可以向 Claude 提供当前 git 状态和 TODO 列表。UserPromptSubmit Hook 可以在每个请求中附加 sprint 优先级。

## Claude Code Hook 类型及使用场景

Claude Code 提供八种 Hook 事件，覆盖会话的完整生命周期。

|Hook|触发时机|常见用途|
|---|---|---|
|PreToolUse|工具执行前|阻止危险命令、验证文件路径、自动批准安全操作|
|PermissionRequest|权限对话框出现前|自动批准测试命令、阻止敏感文件访问|
|PostToolUse|工具完成后|运行格式化工具、触发 linter、记录文件变更|
|PreCompact|上下文压缩前|备份转录、保留重要决策|
|SessionStart|会话开始或恢复时|注入 git 状态、加载 TODO 列表、设置环境上下文|
|Stop|Claude 完成响应时|验证任务完成、运行测试、生成摘要|
|SubagentStop|子智能体完成时|验证子智能体输出、触发后续操作|
|UserPromptSubmit|提交提示时|注入 sprint 上下文、验证请求、添加动态上下文|

### PreToolUse

最常用的 Hook，在 Claude 选择工具后、实际执行前触发。你的脚本可以检查计划的操作并批准、阻止、请求用户确认或修改参数。

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Write",
        "hooks": [
          {
            "type": "command",
            "command": "/path/to/validate-file-path.sh"
          }
        ]
      }
    ]
  }
}
```

使用场景：阻止 `rm -rf` 等危险命令、自动批准安全的重复操作、验证文件路径、修改工具输入注入项目默认值。

### PermissionRequest

在 Claude 正常显示权限对话框时触发。拦截确认提示，让脚本决定是否允许、拒绝或继续询问用户。

```json
{
  "hooks": {
    "PermissionRequest": [
      {
        "matcher": "Bash(npm test*)",
        "hooks": [
          {
            "type": "command",
            "command": "/path/to/validate-test-command.sh"
          }
        ]
      }
    ]
  }
}
```

使用场景：自动批准每会话运行数十次的测试命令、阻止对生产配置文件的写入访问、允许无提示的特定目录读操作。

### PostToolUse

在工具成功完成后立即触发。脚本接收关于发生了什么的信息，包括工具输出。

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit",
        "hooks": [
          {
            "type": "command",
            "command": "prettier --write \"$CLAUDE_TOOL_INPUT_FILE_PATH\""
          }
        ]
      }
    ]
  }
}
```

使用场景：每次文件写入后运行 Prettier/Black/gofmt、记录所有文件修改到审计日志、触发 linter、操作完成时发送通知。

### PreCompact

在 Claude 压缩对话上下文前触发。压缩会总结较早的对话部分，某些细节会丢失。此 Hook 让你在压缩前保留信息。

```json
{
  "hooks": {
    "PreCompact": [
      {
        "matcher": "auto",
        "hooks": [
          {
            "type": "command",
            "command": "/path/to/backup-transcript.sh"
          }
        ]
      }
    ]
  }
}
```

### SessionStart

Claude Code 启动新会话或恢复现有会话时触发。脚本输出会被添加到对话上下文中。

```json
{
  "hooks": {
    "SessionStart": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "git status --short && echo '---' && cat TODO.md"
          }
        ]
      }
    ]
  }
}
```

每次会话开始时 Claude 就知道你当前的 git 状态和 TODO 列表。

### Stop

Claude 完成响应并等待下一个输入时触发。脚本可以检查 Claude 的输出并决定任务是否真正完成。可以返回 `"continue": true` 的 JSON 让 Claude 继续工作。

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "prompt",
            "prompt": "Review whether the task is complete. If all requirements are met, respond with 'complete'. If work remains, respond with 'continue' and specify what still needs to be done."
          }
        ]
      }
    ]
  }
}
```

### SubagentStop

子智能体完成时触发。与 Stop 工作方式相同，但专门在子智能体完成操作时触发。

### UserPromptSubmit

提交提示时、Claude 处理之前触发。脚本通过 stdout 输出的内容会与提示一起添加到 Claude 的上下文中。

```json
{
  "hooks": {
    "UserPromptSubmit": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "cat ./current-sprint-context.md"
          }
        ]
      }
    ]
  }
}
```

## 配置和文件位置

Hook 存在于三个级别的 JSON 设置文件中：

- **项目级**：`.claude/settings.json`（可与团队共享）

- **用户级**：`~/.claude/settings.json`（跨所有项目生效）

- **本地项目**：`.claude/settings.local.json`（不想提交的个人配置）

项目级设置优先于用户级设置。企业还有组织级托管策略设置。

## 匹配器语法

匹配器过滤哪些工具可以触发 Hook，仅适用于 PreToolUse、PostToolUse 和 PermissionRequest。

- 简单字符串匹配：`"Write"` 只匹配 Write 工具

- 管道语法匹配多个工具：`"Write|Edit"`

- 通配符匹配所有：`"*"` 或空字符串

- 参数模式：`"Bash(npm test*)"` 匹配特定命令参数

- MCP 工具模式：`"mcp__memory__.*"`

**注意**：匹配器区分大小写。

## 输入、输出和结构化响应

### Hook 接收什么

所有 Hook 通过 stdin 接收包含会话信息和事件特定数据的 JSON。常见字段包括：`session_id`、`transcript_path`、`cwd`、`permission_mode`、`hook_event_name`。工具相关 Hook 还接收 `tool_name` 和 `tool_input`。

### Hook 如何响应

- 退出码 0：成功，stdout 被处理为 JSON 或添加到上下文

- 退出码 2：阻塞错误，stderr 成为错误消息，操作被阻止

- 其他退出码：非阻塞错误

结构化 JSON 响应字段包括：`decision`（approve/block/allow/deny）、`reason`、`continue`（Stop Hook）、`updatedInput`（修改工具参数）。

## 环境和执行

Hook 可访问环境变量：`CLAUDE_PROJECT_DIR`（项目根路径）、`CLAUDE_CODE_REMOTE`（web 环境为 true）、`CLAUDE_ENV_FILE`（SessionStart Hook 持久化变量）。

Hook 默认 60 秒超时（可配置）。多个匹配的 Hook 并行运行。相同命令自动去重。

## 安全考量

Hook 以你的用户权限执行任意 Shell 命令。Claude Code 包含保护措施：对 Hook 配置文件的直接编辑需要在 `/hooks` 菜单中审查后才能生效。

**最佳实践**：验证和清理 stdin 输入、引用 Shell 变量防止注入、使用绝对路径、避免处理 `.env` 或凭证等敏感文件。

## 调试和测试

Claude Code 将所有内容记录到转录文件中。每个 Hook 接收一个 `transcript_path` 字段指向包含完整会话历史的 JSONL 文件。

```json
{
  "hooks": {
    "SessionStart": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '\"Session:\" + .transcript_path' >> ~/.claude/sessions.log"
          }
        ]
      }
    ]
  }
}
```

然后实时监控：`tail -f /path/to/transcript.jsonl | jq`

对于 Hook 特定调试，可以添加日志包装脚本记录额外信息。

## 构建你自己的 Hook

从解决工作流中一个实际摩擦点的简单 Hook 开始。PostToolUse 格式化 Hook 是一个好的起步选择。一旦工作正常，基于所学扩展。

查看官方 [Hooks 文档](https://code.claude.com/docs/en/hooks-guide)获取完整参考。

_立即使用 Hook 自定义你的 [Claude Code](https://www.claude.com/product/claude-code) 工作流。_

---

## 📄 原文（Original English）

**Hooks** are custom shell commands that execute automatically on targeted events in Claude Code sessions. They solve three problems: eliminating repetitive steps, enforcing project rules automatically, and injecting dynamic context.

**8 Hook types**: PreToolUse (before tool execution), PermissionRequest (before permission dialog), PostToolUse (after tool completes), PreCompact (before context compaction), SessionStart (session begins/resumes), Stop (Claude finishes responding), SubagentStop (subagent completes), UserPromptSubmit (prompt submitted).

**Configuration**: JSON settings files at project (`.claude/settings.json`), user (`~/.claude/settings.json`), or local (`.claude/settings.local.json`) levels. Matchers filter which tools trigger hooks (case-sensitive).

**I/O**: Hooks receive JSON via stdin with session/event data. Respond via exit codes (0=success, 2=block) and structured JSON (decision, reason, continue, updatedInput).

**Security**: Hooks execute with user permissions. Direct config edits require review in `/hooks` menu. 60s default timeout, parallel execution for multiple matches.