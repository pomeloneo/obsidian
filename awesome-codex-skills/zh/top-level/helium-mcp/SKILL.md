---
name: helium-mcp
description: 通过 Helium MCP server 搜索带 bias scoring 的实时新闻，获取带 AI 分析的实时 stock/ETF/crypto 数据、ML options pricing、balanced news synthesis，以及 meme search。
---

# Helium MCP — 新闻、市场与 AI Intelligence

当你需要搜索新闻、分析媒体 bias、获取 stock/crypto 市场数据、给 options 定价，或寻找关于时事的平衡视角时，使用此 skill。

## 前置条件

必须已配置 Helium MCP server。添加到你的 MCP settings：

```json
{
  "mcpServers": {
    "helium": {
      "url": "https://heliumtrades.com/mcp"
    }
  }
}
```

免费层级：50 次查询，无需注册或 API key。

## 可用工具

### News & Bias Analysis
- **search_news** — 从 5,000+ sources 的 3.2M+ articles 中搜索，并提供跨 15+ 维度的 bias scores（political lean、emotionality、factfulness、prescriptiveness 等）
- **search_balanced_news** — 获取 AI 合成的 balanced articles，聚合任意 topic 的 left/right/center 视角
- **get_trending_topics** — 获取所有 sources 当前 trending 的 news topics
- **get_source_bias** — 获取任意 news source（例如 CNN、Fox News、Reuters）的详细 bias profile
- **get_article_bias** — 获取特定 article 的完整多维度 bias analysis

### Market Data & Analysis
- **get_ticker** — 实时 stock/ETF/crypto price data，包含 AI 生成的 bull/bear cases、5 个 probability-weighted scenarios 和 price forecasts
- **get_option_price** — 任意 option contract 的 ML-predicted fair value 和 probability ITM
- **get_top_trading_strategies** — 带 risk/reward analysis 的 top-ranked options strategies

### 其他
- **search_memes** — 对 trending memes 进行 semantic search，包含 OCR text 和 engagement data

## 使用模式

- **比较媒体报道**：用 `search_news` 输入 topic query，然后比较不同 sources 的 bias scores
- **获取平衡视角**：用 `search_balanced_news` 对任意有争议 topic 做多视角综合
- **Stock research**：用 `get_ticker` 获取 price + AI analysis + probability-weighted scenarios，然后用 `get_option_price` 做 derivatives pricing
- **发现 trades**：用 `get_top_trading_strategies` 获取带完整 Greeks 的 AI-ranked options setups
- **Bias audit**：用 `get_source_bias` 理解某个 source 的典型 framing patterns

## 备注

- 所有 tools 均为只读
- 更多信息：https://heliumtrades.com/mcp-page/
