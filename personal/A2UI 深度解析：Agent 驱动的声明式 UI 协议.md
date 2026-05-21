## 一句话理解 A2UI

**A2UI（Agent-to-UI）是一个开源协议，让 AI Agent 能够安全地生成富交互界面，无需执行任意代码。**

Agent 不再只能返回文本——它可以「说出」一套通用的 UI 语言，客户端用自己的原生组件渲染，Web、Mobile、Desktop 通吃。

---

![[output.zip]]

## 为什么需要 A2UI？

> [!important]
> 
> **核心矛盾**：AI Agent 越来越强，但输出形式还停留在纯文本或 Markdown。用户需要表单、按钮、卡片、图表等富交互，传统方案要么让 Agent 生成前端代码（安全风险大），要么写死 UI 模板（灵活性差）。

A2UI 的回答：**Agent 只描述「要什么 UI」，不决定「怎么画」。**

|传统方案|A2UI 方案|
|---|---|
|Agent 生成 HTML/React 代码 → 客户端执行|Agent 发送 JSON 描述 → 客户端用原生组件渲染|
|安全隐患：XSS、注入攻击|声明式数据，无可执行代码|
|绑定特定前端框架|框架无关：Angular、Flutter、React 均可|
|必须一次生成完整 UI|流式增量构建，渐进式渲染|

---

## 核心架构

### 端到端数据流

```jsx
Agent (LLM) → A2UI Generator → Transport (SSE/WS/A2A)
                                        ↓
Native UI ← Renderer ← Message Parser ← Client (Stream Reader)
```

整个流程分 6 步：

1. **用户发送消息**给 AI Agent

1. **Agent 生成 A2UI 消息**（JSON 格式，描述 UI 结构 + 数据）

1. **消息流式传输**到客户端（支持 SSE、WebSocket、A2A 等协议）

1. **客户端用原生组件渲染**（Angular、Flutter、React 等）

1. **用户与 UI 交互**，将 action 回传给 Agent

1. **Agent 响应**，发送更新后的 A2UI 消息

---

## 三大设计理念

### 理念一：Streaming Messages — 流式消息

UI 更新以 **JSON Lines（JSONL）** 序列从 Agent 流向客户端，每行一个完整 JSON 对象。

```json
{"surfaceUpdate": {"surfaceId": "main", "components": [...]}}
{"dataModelUpdate": {"surfaceId": "main", "contents": [...]}}
{"beginRendering": {"surfaceId": "main", "root": "root-component"}}
```

**为什么用 JSONL？**

- **流式友好**：每行独立，无需等待完整响应

- **LLM 友好**：大模型可以逐步生成，不必一次输出完美 JSON

- **容错性强**：某行出错不影响其他消息

### 理念二：Declarative Components — 声明式组件

UI 是 **数据描述**，不是 **代码指令**。Agent 只能使用客户端预先批准的组件目录（Catalog），不存在注入攻击的可能。

```json
{
  "id": "title",
  "component": {
    "Text": {
      "text": {"literalString": "Welcome to A2UI"},
      "usageHint": "h1"
    }
  }
}
```

关键特征：**Agent 说「我要一个标题文本」，客户端决定用什么字体、什么颜色、什么动画来渲染。**

### 理念三：Data Binding — 数据绑定

UI 结构和应用状态 **彻底分离**，通过 JSON Pointer 路径（RFC 6901）连接。

**UI 结构（不变）**

```json
{"id": "username", "component": {
  "Text": {"text": {"path": "/user/name"}}
}}
```

**应用状态（可变）**

```json
{"user": {"name": "Alice"}}
```

→ 当 name 从 "Alice" 变为 "Bob"，UI **自动更新**

这意味着：

- **响应式更新**：数据变 → UI 自动变，无需重新生成组件

- **双向绑定**：用户在 TextField 输入内容 → 数据模型自动更新

- **模板复用**：一个组件模板 + 不同数据 = 不同 UI 实例

---

## 四种消息类型

A2UI 的全部通信由 4 种消息构成：

### 1. `surfaceUpdate` — 定义/更新 UI 组件

```json
{"surfaceUpdate": {
  "surfaceId": "main",
  "components": [
    {"id": "root", "component": {"Column": {"children": {"explicitList": ["header", "body"]}}}},
    {"id": "header", "component": {"Text": {"text": {"literalString": "Welcome"}}}},
    {"id": "body", "component": {"Card": {"child": "content"}}}
  ]
}}
```

组件用 **邻接表（Adjacency List）** 表示——扁平数组，通过 ID 引用子组件，而非嵌套树。

> [!important]
> 
> **为什么用邻接表而非嵌套树？**
> 
> - 扁平结构对 LLM 更友好，生成更简单
> 
> - 支持增量更新：只发送变更的组件，不需要重传整棵树
> 
> - 重发某个 ID 的组件 = 更新该组件（而非创建新的）

### 2. `dataModelUpdate` — 更新应用状态

```json
{"dataModelUpdate": {
  "surfaceId": "main",
  "path": "user",
  "contents": [
    {"key": "name", "valueString": "Alice"},
    {"key": "email", "valueString": "alice@example.com"}
  ]
}}
```

- 每个 Surface 有独立的数据模型（JSON 对象）

- `path` 指定更新位置，实现 **细粒度更新**（只改 `/user/name`，不动 `/cart`）

- 值类型显式声明（`valueString`、`valueNumber`、`valueBoolean`、`valueMap`），避免 LLM 类型推断错误

### 3. `beginRendering` — 触发渲染

```json
{"beginRendering": {
  "surfaceId": "main",
  "root": "root-component"
}}
```

告诉客户端：「组件和数据准备好了，可以开始渲染了。」

客户端在收到此消息前，会缓冲 `surfaceUpdate` 和 `dataModelUpdate`，避免不完整渲染。

### 4. `deleteSurface` — 删除 UI 界面

```json
{"deleteSurface": {"surfaceId": "modal"}}
```

清除指定 Surface 的所有组件和数据。幂等操作，删除不存在的 Surface 不会报错。

---

## 完整生命周期示例：餐厅预订

用一个端到端的例子串联所有概念：

### Step 1：用户发起请求

"帮我明天晚上 7 点订一桌 2 人位"

### Step 2：Agent 定义 UI 结构

Agent 发送 `surfaceUpdate`，包含：

- 一个 Column 根容器

- 标题文本 "Confirm Reservation"

- 一个 TextField 绑定到 `/reservation/guests`

- 一个 Button 触发 "confirm" action

### Step 3：Agent 填充数据

Agent 发送 `dataModelUpdate`，设置：

- `/reservation/datetime` = "2025-12-16T19:00:00Z"

- `/reservation/guests` = "2"

### Step 4：Agent 触发渲染

Agent 发送 `beginRendering`，客户端显示预订确认界面。

### Step 5：用户编辑并提交

用户将人数改为 3 → 客户端自动更新数据模型（双向绑定）。

用户点击确认 → 客户端发送 `userAction`，携带最新数据。

### Step 6：Agent 响应

Agent 可以更新 UI 显示确认信息，或发送 `deleteSurface` 清理界面。

---

## 组件体系

A2UI 提供标准组件目录（Standard Catalog），覆盖常见 UI 需求：

### 布局组件

|组件|用途|关键属性|
|---|---|---|
|**Row**|水平排列子组件|`distribution`（间距分布）、`alignment`（垂直对齐）|
|**Column**|垂直排列子组件|`distribution`、`alignment`|

### 展示组件

|组件|用途|
|---|---|
|**Text**|文本显示，支持 h1-h5、body、caption 等样式|
|**Image**|图片展示|
|**Icon**|Material Icons 图标|
|**Divider**|分隔线|

### 交互组件

|组件|用途|数据绑定|
|---|---|---|
|**Button**|按钮，支持 action 触发|通过 `action.context` 携带数据|
|**TextField**|文本输入（短文本/长文本/数字/日期/密码）|`text` 绑定到数据路径|
|**CheckBox**|布尔开关|`value` 绑定到数据路径|
|**MultipleChoice**|多选|`selections` 绑定到数据路径|

### 容器组件

|组件|用途|
|---|---|
|**Card**|卡片容器，有边框和内边距|
|**Modal**|弹窗对话框|
|**Tabs**|标签页切换|
|**List**|可滚动列表，支持动态模板渲染|

---

## 动态列表与模板

A2UI 最强大的特性之一：**用模板 + 数据绑定渲染动态数组**。

```json
// 组件定义：用模板渲染 /products 数组
{"id": "product-list", "component": {
  "Column": {
    "children": {"template": {"dataBinding": "/products", "componentId": "product-card"}}
  }
}}

// 模板内的子组件：路径自动 scope 到当前数组项
{"id": "product-name", "component": {
  "Text": {"text": {"path": "/name"}}
}}
```

当数据模型中 `/products` 有 3 个元素时，自动渲染 3 张卡片。添加/删除元素 → UI 自动增减。

---

## 性能与容错

### 渐进式渲染

用户看到 UI 逐步构建，而非盯着 loading spinner。Agent 可以先发 header，再发 body，最后发 footer。

### 性能优化策略

- **批量更新**：客户端缓冲 16ms 内的更新，合并渲染

- **Diffing**：比较新旧组件，只更新变更的属性

- **细粒度数据更新**：只改 `/user/name`，不刷新整个数据模型

### 错误处理

- **消息格式错误**：跳过继续处理，或回传给 Agent 纠正

- **网络中断**：显示错误状态，自动重连，Agent 重发或续传

---

## 传输层选项

A2UI 不绑定特定传输协议，当前支持：

- **A2A Protocol**：多 Agent 系统间通信，也可用于 Agent-to-UI

- **AG UI**：双向实时通信

- **SSE / WebSocket**：标准流式传输

---

## 技术定位与对比

> [!important]
> 
> **A2UI 不是前端框架，是一个协议。** 它定义的是 Agent 和 UI 之间的通信契约，类似于 HTTP 之于 Web、gRPC 之于微服务。

|维度|A2UI|Agent 生成 HTML|固定模板|
|---|---|---|---|
|安全性|✅ 声明式，无代码执行|❌ XSS/注入风险|✅ 安全|
|灵活性|✅ Agent 动态组合|✅ 完全自由|❌ 写死|
|跨平台|✅ 框架无关|❌ 绑定 Web|❌ 绑定特定实现|
|LLM 友好|✅ 扁平 JSON，可增量|⚠️ 嵌套 HTML 难生成|✅ 无需生成|
|渐进渲染|✅ 原生支持|❌ 需完整 DOM|❌ 通常不支持|

---

## 当前状态

- **版本**：v0.8 Public Preview

- **开源协议**：Apache 2.0

- **发起方**：Google，CopilotKit 等社区贡献

- **客户端渲染器**：Angular、Flutter 已有实现，React 等在开发中

- **GitHub**：[a2ui.org](http://a2ui.org)

---

## 总结

A2UI 解决了 AI Agent 时代的一个关键问题：**如何让 Agent 安全、高效、跨平台地生成富交互界面。**

三个关键词概括其设计哲学：

1. **声明式**：Agent 描述「要什么」，客户端决定「怎么画」

1. **流式**：JSON Lines 逐行传输，渐进式渲染，LLM 友好

1. **分离**：UI 结构与应用状态分离，数据绑定实现响应式更新