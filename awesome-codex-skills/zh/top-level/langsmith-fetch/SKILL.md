---
name: langsmith-fetch
description: 通过从 LangSmith Studio 获取 execution traces 来 debug LangChain 和 LangGraph agents。用于 debugging agent behavior、调查 errors、分析 tool calls、检查 memory operations 或审查 agent performance。自动获取 recent traces 并分析 execution patterns。需要已安装 langsmith-fetch CLI。
---

# LangSmith Fetch - Agent Debugging Skill

通过在 terminal 中直接从 LangSmith Studio 获取 execution traces，debug LangChain 和 LangGraph agents。

## 何时使用此 Skill

当用户提到以下内容时自动激活：
- 🐛 "Debug my agent" 或 "What went wrong?"
- 🔍 "Show me recent traces" 或 "What happened?"
- ❌ "Check for errors" 或 "Why did it fail?"
- 💾 "Analyze memory operations" 或 "Check LTM"
- 📊 "Review agent performance" 或 "Check token usage"
- 🔧 "What tools were called?" 或 "Show execution flow"

## 前置条件

### 1. 安装 langsmith-fetch
```bash
pip install langsmith-fetch
```

### 2. 设置 Environment Variables
```bash
export LANGSMITH_API_KEY="your_langsmith_api_key"
export LANGSMITH_PROJECT="your_project_name"
```

**验证 setup：**
```bash
echo $LANGSMITH_API_KEY
echo $LANGSMITH_PROJECT
```

## 核心工作流

### Workflow 1：快速 Debug Recent Activity

**用户询问：** "What just happened?" 或 "Debug my agent"

**执行：**
```bash
langsmith-fetch traces --last-n-minutes 5 --limit 5 --format pretty
```

**分析并报告：**
1. ✅ 找到的 traces 数量
2. ⚠️ 任何 errors 或 failures
3. 🛠️ 被调用的 tools
4. ⏱️ Execution times
5. 💰 Token usage

**示例 response format：**
```
Found 3 traces in the last 5 minutes:

Trace 1: ✅ Success
- Agent: memento
- Tools: recall_memories, create_entities
- Duration: 2.3s
- Tokens: 1,245

Trace 2: ❌ Error
- Agent: cypher
- Error: "Neo4j connection timeout"
- Duration: 15.1s
- Failed at: search_nodes tool

Trace 3: ✅ Success
- Agent: memento
- Tools: store_memory
- Duration: 1.8s
- Tokens: 892

💡 Issue found: Trace 2 failed due to Neo4j timeout. Recommend checking database connection.
```

---

### Workflow 2：深入分析特定 Trace

**用户提供：** Trace ID 或说 "investigate that error"

**执行：**
```bash
langsmith-fetch trace <trace-id> --format json
```

**分析 JSON 并报告：**
1. 🎯 agent 试图完成什么
2. 🛠️ 调用了哪些 tools（按顺序）
3. ✅ Tool results（success/failure）
4. ❌ Error messages（如有）
5. 💡 Root cause analysis
6. 🔧 Suggested fix

**示例 response format：**
```
Deep Dive Analysis - Trace abc123

Goal: User asked "Find all projects in Neo4j"

Execution Flow:
1. ✅ search_nodes(query: "projects")
   → Found 24 nodes

2. ❌ get_node_details(node_id: "proj_123")
   → Error: "Node not found"
   → This is the failure point

3. ⏹️ Execution stopped

Root Cause:
The search_nodes tool returned node IDs that no longer exist in the database,
possibly due to recent deletions.

Suggested Fix:
1. Add error handling in get_node_details tool
2. Filter deleted nodes in search results
3. Update cache invalidation strategy

Token Usage: 1,842 tokens ($0.0276)
Execution Time: 8.7 seconds
```

---

### Workflow 3：导出 Debug Session

**用户说：** "Save this session" 或 "Export traces"

**执行：**
```bash
# Create session folder with timestamp
SESSION_DIR="langsmith-debug/session-$(date +%Y%m%d-%H%M%S)"
mkdir -p "$SESSION_DIR"

# Export traces
langsmith-fetch traces "$SESSION_DIR/traces" --last-n-minutes 30 --limit 50 --include-metadata

# Export threads (conversations)
langsmith-fetch threads "$SESSION_DIR/threads" --limit 20
```

**报告：**
```
✅ Session exported successfully!

Location: langsmith-debug/session-20251224-143022/
- Traces: 42 files
- Threads: 8 files

You can now:
1. Review individual trace files
2. Share folder with team
3. Analyze with external tools
4. Archive for future reference

Session size: 2.3 MB
```

---

### Workflow 4：Error Detection

**用户询问：** "Show me errors" 或 "What's failing?"

**执行：**
```bash
# Fetch recent traces
langsmith-fetch traces --last-n-minutes 30 --limit 50 --format json > recent-traces.json

# Search for errors
grep -i "error\|failed\|exception" recent-traces.json
```

**分析并报告：**
1. 📊 找到的 errors 总数
2. ❌ Error types 和 frequency
3. 🕐 Errors 发生时间
4. 🎯 哪些 agents/tools failed
5. 💡 Common patterns

**示例 response format：**
```
Error Analysis - Last 30 Minutes

Total Traces: 50
Failed Traces: 7 (14% failure rate)

Error Breakdown:
1. Neo4j Connection Timeout (4 occurrences)
   - Agent: cypher
   - Tool: search_nodes
   - First occurred: 14:32
   - Last occurred: 14:45
   - Pattern: Happens during peak load

2. Memory Store Failed (2 occurrences)
   - Agent: memento
   - Tool: store_memory
   - Error: "Pinecone rate limit exceeded"
   - Occurred: 14:38, 14:41

3. Tool Not Found (1 occurrence)
   - Agent: sqlcrm
   - Attempted tool: "export_report" (doesn't exist)
   - Occurred: 14:35

💡 Recommendations:
1. Add retry logic for Neo4j timeouts
2. Implement rate limiting for Pinecone
3. Fix sqlcrm tool configuration
```

---

## 常见用例

### Use Case 1："Agent Not Responding"

**用户说：** "My agent isn't doing anything"

**步骤：**
1. 检查 traces 是否存在：
   ```bash
   langsmith-fetch traces --last-n-minutes 5 --limit 5
   ```

2. **如果没有找到 traces：**
   - Tracing 可能已禁用
   - 检查 environment 中的 `LANGCHAIN_TRACING_V2=true`
   - 检查 `LANGCHAIN_API_KEY` 是否已设置
   - 验证 agent 确实运行过

3. **如果找到 traces：**
   - 检查 errors
   - 检查 execution time（是否 hanging？）
   - 验证 tool calls 已完成

---

### Use Case 2："Wrong Tool Called"

**用户说：** "Why did it use the wrong tool?"

**步骤：**
1. 获取 specific trace
2. 审查 execution time 可用的 tools
3. 检查 agent 选择 tool 的 reasoning
4. 检查 tool descriptions/instructions
5. 建议 prompt 或 tool config 改进

---

### Use Case 3："Memory Not Working"

**用户说：** "Agent doesn't remember things"

**步骤：**
1. 搜索 memory operations：
   ```bash
   langsmith-fetch traces --last-n-minutes 10 --limit 20 --format raw | grep -i "memory\|recall\|store"
   ```

2. 检查：
   - 是否调用了 memory tools？
   - recall 是否返回 results？
   - memories 是否确实被 stored？
   - retrieved memories 是否被使用？

---

### Use Case 4："Performance Issues"

**用户说：** "Agent is too slow"

**步骤：**
1. 带 metadata 导出：
   ```bash
   langsmith-fetch traces ./perf-analysis --last-n-minutes 30 --limit 50 --include-metadata
   ```

2. 分析：
   - 每个 trace 的 execution time
   - Tool call latencies
   - Token usage（context size）
   - Number of iterations
   - Slowest operations

3. 识别 bottlenecks 并建议 optimizations

---

## 输出格式指南

### Pretty Format（默认）
```bash
langsmith-fetch traces --limit 5 --format pretty
```
**用于：** 快速视觉检查、展示给用户

### JSON Format
```bash
langsmith-fetch traces --limit 5 --format json
```
**用于：** 详细分析、syntax-highlighted review

### Raw Format
```bash
langsmith-fetch traces --limit 5 --format raw
```
**用于：** pipe 到其他 commands、automation

---

## 高级功能

### Time-Based Filtering
```bash
# After specific timestamp
langsmith-fetch traces --after "2025-12-24T13:00:00Z" --limit 20

# Last N minutes (most common)
langsmith-fetch traces --last-n-minutes 60 --limit 100
```

### Include Metadata
```bash
# Get extra context
langsmith-fetch traces --limit 10 --include-metadata

# Metadata includes: agent type, model, tags, environment
```

### Concurrent Fetching（更快）
```bash
# Speed up large exports
langsmith-fetch traces ./output --limit 100 --concurrent 10
```

---

## Troubleshooting

### "No traces found matching criteria"

**可能原因：**
1. 该 timeframe 内没有 agent activity
2. Tracing 已禁用
3. Project name 错误
4. API key 问题

**解决方案：**
```bash
# 1. Try longer timeframe
langsmith-fetch traces --last-n-minutes 1440 --limit 50

# 2. Check environment
echo $LANGSMITH_API_KEY
echo $LANGSMITH_PROJECT

# 3. Try fetching threads instead
langsmith-fetch threads --limit 10

# 4. Verify tracing is enabled in your code
# Check for: LANGCHAIN_TRACING_V2=true
```

### "Project not found"

**解决方案：**
```bash
# View current config
langsmith-fetch config show

# Set correct project
export LANGSMITH_PROJECT="correct-project-name"

# Or configure permanently
langsmith-fetch config set project "your-project-name"
```

### Environment variables not persisting

**解决方案：**
```bash
# Add to shell config file (~/.bashrc or ~/.zshrc)
echo 'export LANGSMITH_API_KEY="your_key"' >> ~/.bashrc
echo 'export LANGSMITH_PROJECT="your_project"' >> ~/.bashrc

# Reload shell config
source ~/.bashrc
```

---

## 最佳实践

### 1. Regular Health Checks
```bash
# Quick check after making changes
langsmith-fetch traces --last-n-minutes 5 --limit 5
```

### 2. Organized Storage
```
langsmith-debug/
├── sessions/
│   ├── 2025-12-24/
│   └── 2025-12-25/
├── error-cases/
└── performance-tests/
```

### 3. Document Findings
发现 bugs 时：
1. 导出 problematic trace
2. 保存到 `error-cases/` folder
3. 在 README 中记录出错原因
4. 与团队分享 trace ID

### 4. Integration with Development
```bash
# Before committing code
langsmith-fetch traces --last-n-minutes 10 --limit 5

# If errors found
langsmith-fetch trace <error-id> --format json > pre-commit-error.json
```

---

## Quick Reference

```bash
# Most common commands

# Quick debug
langsmith-fetch traces --last-n-minutes 5 --limit 5 --format pretty

# Specific trace
langsmith-fetch trace <trace-id> --format pretty

# Export session
langsmith-fetch traces ./debug-session --last-n-minutes 30 --limit 50

# Find errors
langsmith-fetch traces --last-n-minutes 30 --limit 50 --format raw | grep -i error

# With metadata
langsmith-fetch traces --limit 10 --include-metadata
```

---

## 资源

- **LangSmith Fetch CLI:** https://github.com/langchain-ai/langsmith-fetch
- **LangSmith Studio:** https://smith.langchain.com/
- **LangChain Docs:** https://docs.langchain.com/
- **This Skill Repo:** https://github.com/OthmanAdi/langsmith-fetch-skill

---

## Claude 备注

- 运行 commands 前始终检查是否已安装 `langsmith-fetch`
- 验证 environment variables 已设置
- 用 `--format pretty` 获取 human-readable output
- 需要 parse 和分析 data 时用 `--format json`
- 导出 sessions 时，创建有组织的 folder structures
- 始终提供清晰分析和可执行 insights
- 如果 commands 失败，帮助排查 configuration issues

---

**Version:** 0.1.0
**Author:** Ahmad Othman Ammar Adi
**License:** MIT
**Repository:** https://github.com/OthmanAdi/langsmith-fetch-skill
