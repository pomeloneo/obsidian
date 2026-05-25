---
name: webapp-testing
description: 使用 Playwright 与本地 web applications 交互并进行测试的工具包。支持验证 frontend functionality、调试 UI behavior、捕获 browser screenshots 和查看 browser logs。
license: 完整条款见 LICENSE.txt
---

# Web Application Testing

要测试本地 web applications，请编写原生 Python Playwright scripts。

**可用 Helper Scripts**：
- `scripts/with_server.py` - 管理 server lifecycle（支持多个 servers）

**始终先用 `--help` 运行 scripts** 以查看用法。在先尝试运行 script 并发现确实必须自定义方案之前，不要读取 source。这些 scripts 可能非常大，会污染你的 context window。它们的存在是为了作为 black-box scripts 被直接调用，而不是被读入你的 context window。

## Decision Tree: Choosing Your Approach

```
User task → Is it static HTML?
    ├─ Yes → Read HTML file directly to identify selectors
    │         ├─ Success → Write Playwright script using selectors
    │         └─ Fails/Incomplete → Treat as dynamic (below)
    │
    └─ No (dynamic webapp) → Is the server already running?
        ├─ No → Run: python scripts/with_server.py --help
        │        Then use the helper + write simplified Playwright script
        │
        └─ Yes → Reconnaissance-then-action:
            1. Navigate and wait for networkidle
            2. Take screenshot or inspect DOM
            3. Identify selectors from rendered state
            4. Execute actions with discovered selectors
```

## 示例：使用 with_server.py

要启动 server，请先运行 `--help`，然后使用 helper：

**单个 server：**
```bash
python scripts/with_server.py --server "npm run dev" --port 5173 -- python your_automation.py
```

**多个 servers（例如 backend + frontend）：**
```bash
python scripts/with_server.py \
  --server "cd backend && python server.py" --port 3000 \
  --server "cd frontend && npm run dev" --port 5173 \
  -- python your_automation.py
```

创建 automation script 时，只包含 Playwright 逻辑（servers 会自动管理）：
```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=True) # Always launch chromium in headless mode
    page = browser.new_page()
    page.goto('http://localhost:5173') # Server already running and ready
    page.wait_for_load_state('networkidle') # CRITICAL: Wait for JS to execute
    # ... your automation logic
    browser.close()
```

## Reconnaissance-Then-Action Pattern

1. **检查 rendered DOM**：
   ```python
   page.screenshot(path='/tmp/inspect.png', full_page=True)
   content = page.content()
   page.locator('button').all()
   ```

2. **识别 selectors**，依据 inspection results

3. **使用发现的 selectors 执行动作**

## 常见陷阱

❌ **不要** 在 dynamic apps 上等待 `networkidle` 之前检查 DOM
✅ **要** 在检查前等待 `page.wait_for_load_state('networkidle')`

## 最佳实践

- **将 bundled scripts 作为 black boxes 使用** - 为完成任务，考虑 `scripts/` 中的某个可用 script 是否有帮助。这些 scripts 能可靠处理常见复杂 workflows，而不会弄乱 context window。使用 `--help` 查看用法，然后直接调用。
- 使用 `sync_playwright()` 编写 synchronous scripts
- 完成后始终关闭 browser
- 使用描述性 selectors：`text=`、`role=`、CSS selectors 或 IDs
- 添加适当 waits：`page.wait_for_selector()` 或 `page.wait_for_timeout()`

## Reference Files

- **examples/** - 展示常见 patterns 的示例：
  - `element_discovery.py` - 发现页面上的 buttons、links 和 inputs
  - `static_html_automation.py` - 使用 file:// URLs 处理 local HTML
  - `console_logging.py` - 在 automation 期间捕获 console logs
