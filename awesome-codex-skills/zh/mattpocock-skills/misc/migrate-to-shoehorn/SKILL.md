---
name: migrate-to-shoehorn
description: 将 test files 从 `as` type assertions 迁移到 @total-typescript/shoehorn。适用于用户提到 shoehorn、想替换 tests 中的 `as`，或需要 partial test data 时。
---

# 迁移到 Shoehorn

## 为什么使用 shoehorn？

`shoehorn` 允许你在 tests 中传入 partial data，同时让 TypeScript 满意。它用 type-safe alternatives 替代 `as` assertions。

**仅限 test code。** 永远不要在 production code 中使用 shoehorn。

tests 中 `as` 的问题：

- 被训练成不要使用它
- 必须手动指定 target type
- 对于故意错误的数据需要 double-as（`as unknown as Type`）

## 安装

```bash
npm i @total-typescript/shoehorn
```

## 迁移模式

### 只需要少数属性的大对象

迁移前：

```ts
type Request = {
  body: { id: string };
  headers: Record<string, string>;
  cookies: Record<string, string>;
  // ...20 more properties
};

it("gets user by id", () => {
  // Only care about body.id but must fake entire Request
  getUser({
    body: { id: "123" },
    headers: {},
    cookies: {},
    // ...fake all 20 properties
  });
});
```

迁移后：

```ts
import { fromPartial } from "@total-typescript/shoehorn";

it("gets user by id", () => {
  getUser(
    fromPartial({
      body: { id: "123" },
    }),
  );
});
```

### `as Type` → `fromPartial()`

迁移前：

```ts
getUser({ body: { id: "123" } } as Request);
```

迁移后：

```ts
import { fromPartial } from "@total-typescript/shoehorn";

getUser(fromPartial({ body: { id: "123" } }));
```

### `as unknown as Type` → `fromAny()`

迁移前：

```ts
getUser({ body: { id: 123 } } as unknown as Request); // wrong type on purpose
```

迁移后：

```ts
import { fromAny } from "@total-typescript/shoehorn";

getUser(fromAny({ body: { id: 123 } }));
```

## 何时使用

| 函数            | 使用场景                                           |
| --------------- | -------------------------------------------------- |
| `fromPartial()` | 传入仍能 type-check 的 partial data                |
| `fromAny()`     | 传入故意错误的数据（保留 autocomplete）            |
| `fromExact()`   | 强制完整对象（之后可换成 fromPartial）             |

## 工作流

1. **收集 requirements** - 询问用户：
   - 哪些 test files 中的 `as` assertions 正在造成问题？
   - 他们是否在处理只关心部分属性的大对象？
   - 他们是否需要为 error testing 传入故意错误的数据？

2. **安装并迁移**：
   - [ ] 安装：`npm i @total-typescript/shoehorn`
   - [ ] 查找包含 `as` assertions 的 test files：`grep -r " as [A-Z]" --include="*.test.ts" --include="*.spec.ts"`
   - [ ] 将 `as Type` 替换为 `fromPartial()`
   - [ ] 将 `as unknown as Type` 替换为 `fromAny()`
   - [ ] 添加来自 `@total-typescript/shoehorn` 的 imports
   - [ ] 运行 type check 验证
