[![](https://static001.geekbang.org/resource/image/3b/f3/3b015b8865d4e8a19ab3c82462ac58f3.png)](https://static001.geekbang.org/resource/image/3b/f3/3b015b8865d4e8a19ab3c82462ac58f3.png)

你好，我是黄佳。

和 AI 协作，不知道你有没有这样的经历：

> [!important]
> 
> **第一次对话：**
> 
> - 你：帮我写一个用户登录接口
> 
> - Claude：好的，这是一个基础的登录接口…（使用 Express + JavaScript）
> 
> - 你：我们项目用的是 Fastify 和 TypeScript
> 
> - Claude：好的，让我重新写…
> 
> **第二次对话：**
> 
> - 你：帮我写一个订单创建接口
> 
> - Claude：好的，这是一个基础的订单接口…（又用 Express + JavaScript）
> 
> - 你：（崩溃）我们用 Fastify 和 TypeScript！

我在刚刚开始使用 Claude Code 时，这种情况常见。对于小项目，我多说几次需求，倒也无所谓。但是时间长了，项目逐渐复杂的时候，如果每次新对话，Claude 都让我从零开始，如果它不记得你的项目用什么技术栈、什么代码风格、什么团队规范——**那这种"失忆症"让人抓狂**。

[![](https://static001.geekbang.org/resource/image/42/6b/42e4743df41a306cc58379f5bd41bb6b.jpg?wh=4266x2582)](https://static001.geekbang.org/resource/image/42/6b/42e4743df41a306cc58379f5bd41bb6b.jpg?wh=4266x2582)

> [!important]
> 
> **[CLAUDE.md](http://CLAUDE.md) 就是治疗这种失忆症的药。**
> 
> 它是一份给 Claude 的"项目入职手册"——Claude 每次开始对话时，都会自动阅读这份手册，了解你的项目背景，明确它在干活时应该遵循的一系列底层规则。

---

## Claude Code 记忆系统的工作原理

这一讲，我们就来学习 Claude Code 如何对抗"失忆症"，记住必要信息。

当你在项目目录启动 Claude Code 时，发生的"记忆系统初始化"过程如下：

[![](https://static001.geekbang.org/resource/image/d1/c0/d1a847a91839b94cdd4dc7aac5fdacc0.jpg?wh=2548x1574)](https://static001.geekbang.org/resource/image/d1/c0/d1a847a91839b94cdd4dc7aac5fdacc0.jpg?wh=2548x1574)

这就像你给新员工一份入职手册，他读完之后就知道公司的规矩。不同的是，**Claude 每次对话都会重新"入职"**——所以这份手册必须简洁有效。

### 记忆获取方式对比

[![](https://static001.geekbang.org/resource/image/2b/2a/2b3ab9a326f6816e32280d6d3801882a.jpg?wh=4109x1892)](https://static001.geekbang.org/resource/image/2b/2a/2b3ab9a326f6816e32280d6d3801882a.jpg?wh=4109x1892)

> [!important]
> 
> **关键洞察**
> 
> [CLAUDE.md](http://CLAUDE.md) 的内容会**每次对话都加载**，所以要精简。把"每次都需要"的内容放这里，把"偶尔需要"的内容放到 Skills 或文档里。

---

## Claude Code 的五层记忆架构

Claude Code 支持**五个层级**的记忆，就像洋葱一样，从外到内，按层级结构组织——高层级的文件优先加载，为底层文件提供基础：

[![](https://static001.geekbang.org/resource/image/77/35/77cc990d2b8c5d906e82e9abd17c3835.jpg?wh=4108x1868)](https://static001.geekbang.org/resource/image/77/35/77cc990d2b8c5d906e82e9abd17c3835.jpg?wh=4108x1868)

### 完整记忆类型表

[![](https://static001.geekbang.org/resource/image/02/55/02bb1bd6ba02853c3f314f66d54f8155.jpg?wh=5827x3096)](https://static001.geekbang.org/resource/image/02/55/02bb1bd6ba02853c3f314f66d54f8155.jpg?wh=5827x3096)

[![](https://static001.geekbang.org/resource/image/95/03/959a4a571c8ed86d932dd11e35b1f503.jpg?wh=3469x955)](https://static001.geekbang.org/resource/image/95/03/959a4a571c8ed86d932dd11e35b1f503.jpg?wh=3469x955)

---

### 1️⃣ 企业策略级记忆设定

**作用**：组织范围内的指令，由 IT/DevOps 统一管理和部署

**适合内容**：公司编码标准、安全策略、合规要求、禁止使用的库或模式

**位置**：

- macOS: `/Library/Application Support/ClaudeCode/``[CLAUDE.md](http://CLAUDE.md)`

- Linux: `/etc/claude-code/``[CLAUDE.md](http://CLAUDE.md)`

- Windows: `C:\Program Files\ClaudeCode\``[CLAUDE.md](http://CLAUDE.md)`

```markdown
# 公司开发策略

## 安全要求
- 禁止在代码中硬编码任何密钥或敏感信息
- 所有 API 调用必须使用 HTTPS
- 用户输入必须经过验证和清理

## 合规要求
- 所有日志必须排除 PII（个人身份信息）
- 数据库连接必须使用加密传输

## 禁止事项
- 禁止使用未经审批的第三方库
- 禁止直接访问生产数据库
```

> [!important]
> 
> 如果你是个人或小团队，可以直接跳过企业级设定这一层，不影响任何使用。

---

### 2️⃣ 用户级内容设定

**作用**：跨所有项目生效的个人偏好

**适合内容**：个人代码风格、沟通语言设置、通用工作习惯

**位置**：`~/.claude/``[CLAUDE.md](http://CLAUDE.md)`

```markdown
# 个人偏好

## 语言设置
- 使用中文回复
- 代码注释使用英文
- 解释简洁直接，不要过多铺垫

## 代码风格
- 缩进使用 2 空格
- 优先使用 async/await
- 变量命名使用 camelCase
- 常量命名使用 UPPER_SNAKE_CASE

## 工具偏好
- 包管理器: uv
- 编辑器: VS Code
- 终端: zsh
```

> [!important]
> 
> 用户级记忆会被项目级覆盖。如果你个人喜欢 2 空格缩进，但项目要求 4 空格，那就用 4 空格。

---

### 3️⃣ 项目级团队共享规范

**作用**：团队共享的项目知识，应该提交到 Git

**适合内容**：项目架构和技术栈、团队编码规范、重要的设计决策、常用命令

**位置**：项目根目录的 `./``[CLAUDE.md](http://CLAUDE.md)`

```markdown
## 技术栈
- Node.js 20 + TypeScript
- Fastify（Web 框架）
- Prisma（ORM）
- PostgreSQL + Redis
- Zod（数据验证）

## 项目结构
src/
├── routes/
├── controllers/
├── services/
├── repositories/
├── schemas/
└── types/

## 响应格式
```

interface ApiResponse<T> {

success: boolean;

data?: T;

error?: { code: string; message: string };

}

```jsx

## 编码规范
- TypeScript strict 模式
- 禁止使用 any，使用 unknown + 类型守卫
- 所有 API 端点必须有 Zod schema 验证
- 业务错误使用自定义 Error 类

## 常用命令
- `pnpm dev` - 启动开发服务器
- `pnpm test` - 运行测试
- `pnpm prisma migrate dev` - 运行数据库迁移
```

---

### 4️⃣ 本地级个人工作空间

**作用**：个人工作笔记，不提交到 Git

**适合内容**：本地环境配置、个人调试技巧、当前工作备注、敏感信息（测试账号等）

**位置**：项目根目录的 `./``[CLAUDE.local.md](http://CLAUDE.local.md)`

```markdown
# 本地开发笔记

## 环境配置
- 本地 API: http://localhost:3000
- 测试数据库: order_service_dev
- Redis: localhost:6379

## 测试账号
- admin@test.com / test123
- user@test.com / test123

## 当前任务
- 正在重构支付模块
- 参考 PR #234 的讨论
- 周五前完成

## 调试技巧
- 订单状态机日志: LOG_LEVEL=debug pnpm dev
- 查看 Redis 缓存: redis-cli KEYS "order:*"
```

> [!important]
> 
> **重要提醒**：记得把 `[CLAUDE.local.md](http://CLAUDE.local.md)` 加入 `.gitignore`！
> 
> ```bash
> echo "CLAUDE.local.md" >> .gitignore
> ```

---

### 5️⃣ 规则目录：分类组织

**作用**：按主题组织的规则文件，支持条件作用域

**适合场景**：[CLAUDE.md](http://CLAUDE.md) 变得太长时、不同文件类型需要不同规范时、前后端分离的项目

**位置**：`.claude/rules/*.md`

```jsx
.claude/
└── rules/
    ├── typescript.md
    ├── testing.md
    ├── api-design.md
    └── security.md
```

**条件作用域示例**：`.claude/rules/``[testing.md](http://testing.md)`

```markdown
---
appliesTo:
  paths:
    - "src/**/*.test.ts"
    - "tests/**/*.ts"
---

# 测试规范

## 命名
- 单元测试: `*.test.ts`
- 集成测试: `*.integration.test.ts`

## 结构
使用 Arrange-Act-Assert 模式：
```

describe('OrderService', () => {

describe('createOrder', () => {

it('should create order when stock is available', async () => {

// Arrange

const mockProduct = createMockProduct({ stock: 10 });

// Act

const order = await orderService.createOrder([mockProduct.id](http://mockProduct.id), 1);

// Assert

expect(order.status).toBe('created');

});

});

});

```jsx

## 覆盖率要求
- 业务逻辑: > 80%
- 工具函数: > 90%
- 路由/控制器: 可以较低
```

> [!important]
> 
> **关键特性**：`paths` 字段让这个规则**只在编辑测试文件时生效**，不会浪费其他场景的上下文空间。

---

## 编写高效的 CLAUDE.md

> [!important]
> 
> **核心原则**
> 
> [CLAUDE.md](http://CLAUDE.md) 写得好不好，直接决定了 Claude 是**靠谱同事**，还是**每次都要重新培训的实习生**。

### 原则 1：Less is More

[CLAUDE.md](http://CLAUDE.md) 的每一行，都会在每一次对话开始时被自动注入上下文。这意味着：**冗余不是无害的，而是持续消耗的**。

### 原则 2：具体优于泛泛

❌ **无效的写法**：

```markdown
# 项目规范

## 代码质量
请写出高质量的代码。代码应该是可读的。使用有意义的变量名。
保持代码整洁。遵循最佳实践。不要写重复的代码。
```

✅ **有效的写法**：

```markdown
## TypeScript 规范
- 使用 `interface` 定义对象结构，`type` 用于联合类型
- 禁止 `any`，使用 `unknown` + 类型守卫
- 函数参数 > 3 个时，使用对象参数

## 错误处理模式
```

// 业务错误

throw new BusinessError('ORDER_NOT_FOUND', '订单不存在');

// 验证错误（Zod 自动抛出）

const data = orderSchema.parse(input);

// controller 中不要 try-catch

// 由全局错误中间件统一处理

### 原则 3：关键三问题 WHY / WHAT / HOW

#### WHY —— 为什么要这样做？

```markdown
## 为什么使用 Zod
- TypeScript 只有编译时类型检查
- API 输入需要运行时验证
- Zod 可以同时生成 TS 类型和验证逻辑
- 错误信息自动生成，对用户友好
```

#### WHAT —— 具体要做什么，不要做什么？

```markdown
## 数据库访问规则
- 所有查询通过 Prisma ORM
- 复杂查询封装在 `src/repositories/`
- 禁止在 controller/service 中直接写 SQL
- 事务使用 `prisma.$transaction()`
```

#### HOW —— 按什么步骤去做？

```markdown
## 创建新 API 端点
1. 在 `src/schemas/` 创建请求/响应 Zod schema
2. 在 `src/routes/` 添加路由定义
3. 在 `src/controllers/` 实现请求处理
4. 在 `src/services/` 实现业务逻辑
5. 在 `tests/` 添加测试用例

示例参考: `src/routes/orders.ts`
```

### 原则 4：渐进式披露

[CLAUDE.md](http://CLAUDE.md) 的职责是定义默认决策，而不是承载全部知识。对于非核心、但可能被用到的内容，正确的做法是**引用，而不是复制**。

```markdown
[精简的核心规范]

## 详细文档
- 数据库设计: 见 `docs/database.md`
- API 规范: 见 `docs/api-spec.md`
- 部署流程: 见 `docs/deployment.md`
```

---

## CLAUDE.md 实战演练

### 场景一：为新项目创建记忆

**Step 1：创建基础 [CLAUDE.md](http://CLAUDE.md)**

```bash
touch CLAUDE.md
```

```markdown
## 技术栈
- React 18 + TypeScript
- Vite 构建
- TanStack Query（数据获取）
- Zustand（状态管理）
- Tailwind CSS

## 项目结构
src/
├── components/
│   ├── ui/
│   └── features/
├── pages/
├── hooks/
├── stores/
├── api/
└── types/

## 组件规范
- 函数组件 + Hooks
- Props 接口命名: `XxxProps`
- 一个组件一个目录: `Button/index.tsx`

## 状态管理
- 服务端状态: TanStack Query
- 客户端状态: Zustand
- 本地状态: useState

## 常用命令
- `pnpm dev` - 开发服务器
- `pnpm build` - 构建
- `pnpm test` - 测试
```

**Step 2：创建本地记忆**

```bash
touch CLAUDE.local.md
echo "CLAUDE.local.md" >> .gitignore
```

```markdown
# 本地笔记

## 环境
- API: http://localhost:8080
- Mock: 使用 MSW

## 当前任务
- 重构购物车组件
- 截止: 本周五
```

**Step 3：添加条件规则（可选）**

```bash
mkdir -p .claude/rules
```

创建 `.claude/rules/``[testing.md](http://testing.md)`：

```markdown
---
appliesTo:
  paths:
    - "src/**/*.test.tsx"
    - "src/**/*.test.ts"
---

# 测试规范

- 使用 Vitest + React Testing Library
- 测试文件放在同目录: `Button.test.tsx`
- 优先测试用户行为，而非实现细节
```

// ✅ 好

expect(screen.getByRole('button')).toBeEnabled();

// ❌ 不好

expect(component.state.isLoading).toBe(false);

---

### 场景二：优化已有的 [CLAUDE.md](http://CLAUDE.md)

假设你的 [CLAUDE.md](http://CLAUDE.md) 已经有 500 行，Claude 开始变慢。此时需要**瘦身**。

**Step 1：识别核心内容**

[![](https://static001.geekbang.org/resource/image/78/0c/78b409e82f2626e31c205a9aea644c0c.jpg?wh=4114x2079)](https://static001.geekbang.org/resource/image/78/0c/78b409e82f2626e31c205a9aea644c0c.jpg?wh=4114x2079)

**Step 2：拆分成独立文件**

```markdown
[精简内容]

## 详细文档引用
- API 端点清单: @docs/api.md
- 数据库 Schema: @prisma/schema.prisma
- 部署配置: @docs/deploy.md
```

**Step 3：使用条件规则**

把测试规范、前端规范、后端规范拆分到 `.claude/rules/`，并设置 `paths` 条件。

---

### 场景三：记忆管理命令

**查看当前记忆**：

```jsx
/memory
```

**编辑记忆**：

```jsx
/memory edit         # 编辑项目级
/memory edit user    # 编辑用户级
/memory edit local   # 编辑本地级
```

> [!important]
> 
> **自然语言更新**
> 
> 你也可以通过自然语言指令，让 Claude 帮你更新记忆！
> 
> > 你：请记住，我们项目使用 pnpm 而不是 npm
> 
> > Claude：好的，我可以将这个信息添加到项目的 [CLAUDE.md](http://CLAUDE.md) 中。要我现在更新吗？

---

## 本讲小结

> [!important]
> 
> **[CLAUDE.md](http://CLAUDE.md) 是有层次的记忆**
> 
> 它的意义，是把项目规范、编码风格和团队约定中反复强调的共识，从对话中抽离出来，变成**一次配置、长期生效**的默认规则。

### 瘦身三步法

当 Claude 响应明显变慢、经常出现上下文长度警告、Claude"忘记"对话早期的内容时：

[![](https://static001.geekbang.org/resource/image/c8/f7/c81b252f29a7ef345eb0e99dd17ef3f7.jpg?wh=3858x2005)](https://static001.geekbang.org/resource/image/c8/f7/c81b252f29a7ef345eb0e99dd17ef3f7.jpg?wh=3858x2005)

```jsx
精简 → 拆分 → 条件规则
```

从更高的层面看，这一讲讨论的并不只是一个配置文件，而是**一种新的协作方式**：把隐性的经验、默认的判断和反复纠正的规则，提前固化成结构。这样，Claude 才能从一个需要不断校准的工具，逐渐变成一个行为稳定、风格一致的协作伙伴。

---

## 思考题

1. 看看你现在项目的 [CLAUDE.md](http://CLAUDE.md)（如果有），有哪些内容可以精简或移出去？

1. 如果团队有 5 个不同技术栈的项目，你会如何设计用户级记忆？

1. 什么内容适合放在 [CLAUDE.local.md](http://CLAUDE.local.md) 而不是 [CLAUDE.md](http://CLAUDE.md)？

---

## 下一讲预告

> [!important]
> 
> **下一讲：Sub-Agents（子代理）**
> 
> 记忆系统可以让 Claude "知道"你的项目，但当任务变复杂时，一个 Claude 可能不够用。
> 
> 你将学会：
> 
> - 为什么需要子代理？
> 
> - 隔离执行的工程价值
> 
> - 如何设计子代理的权限边界

欢迎你在留言区和我交流讨论。如果这一讲对你有启发，别忘了分享给身边更多朋友。