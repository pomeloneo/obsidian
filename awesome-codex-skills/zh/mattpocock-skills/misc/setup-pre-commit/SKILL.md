---
name: setup-pre-commit
description: 在当前 repo 中设置 Husky pre-commit hooks，包含 lint-staged (Prettier)、type checking 和 tests。用于用户想要添加 pre-commit hooks、设置 Husky、配置 lint-staged，或添加提交时 formatting/typechecking/testing 的场景。
---

# 设置 Pre-Commit Hooks

## 这会设置什么

- **Husky** pre-commit hook
- **lint-staged** 对所有 staged files 运行 Prettier
- **Prettier** config（如果缺失）
- pre-commit hook 中的 **typecheck** 和 **test** scripts

## 步骤

### 1. 检测 package manager

检查 `package-lock.json` (npm)、`pnpm-lock.yaml` (pnpm)、`yarn.lock` (yarn)、`bun.lockb` (bun)。使用存在的那个。如果不明确，默认使用 npm。

### 2. 安装 dependencies

作为 devDependencies 安装：

```
husky lint-staged prettier
```

### 3. 初始化 Husky

```bash
npx husky init
```

这会创建 `.husky/` 目录，并向 package.json 添加 `prepare: "husky"`。

### 4. 创建 `.husky/pre-commit`

写入这个文件（Husky v9+ 不需要 shebang）：

```
npx lint-staged
npm run typecheck
npm run test
```

**调整**：将 `npm` 替换为检测到的 package manager。如果 repo 的 package.json 中没有 `typecheck` 或 `test` script，省略这些行并告知用户。

### 5. 创建 `.lintstagedrc`

```json
{
  "*": "prettier --ignore-unknown --write"
}
```

### 6. 创建 `.prettierrc`（如果缺失）

仅在不存在 Prettier config 时创建。使用这些默认值：

```json
{
  "useTabs": false,
  "tabWidth": 2,
  "printWidth": 80,
  "singleQuote": false,
  "trailingComma": "es5",
  "semi": true,
  "arrowParens": "always"
}
```

### 7. 验证

- [ ] `.husky/pre-commit` 存在且可执行
- [ ] `.lintstagedrc` 存在
- [ ] package.json 中的 `prepare` script 是 `"husky"`
- [ ] `prettier` config 存在
- [ ] 运行 `npx lint-staged` 验证其可用

### 8. Commit

Stage 所有已更改/新建的文件，并使用这个 message commit：`Add pre-commit hooks (husky + lint-staged + prettier)`

这会跑一遍新的 pre-commit hooks，是确认一切正常的良好 smoke test。

## 注意事项

- Husky v9+ 的 hook files 不需要 shebang
- `prettier --ignore-unknown` 会跳过 Prettier 无法解析的文件（图片等）
- pre-commit 会先运行 lint-staged（快速，仅 staged），然后运行完整的 typecheck 和 tests
