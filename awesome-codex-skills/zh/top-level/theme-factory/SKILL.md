---
name: theme-factory
description: 用于为 artifacts 应用 theme 的样式工具包。这些 artifacts 可以是 slides、docs、reports、HTML landing pages 等。提供 10 个带 colors/fonts 的预设 themes，可应用到任何已创建的 artifact，也可以即时生成新 theme。
license: 完整条款见 LICENSE.txt
---


# Theme Factory Skill

此 skill 提供一组精选的专业 font 和 color themes，每个 theme 都包含精心选择的 color palettes 和 font pairings。选择 theme 后，可将其应用到任何 artifact。

## 目的

要为 presentation slide decks 应用一致、专业的样式，请使用此 skill。每个 theme 包含：
- 带 hex codes 的协调 color palette
- 用于 headers 和 body text 的互补 font pairings
- 适合不同 contexts 和 audiences 的独特 visual identity

## 使用说明

要将样式应用到 slide deck 或其他 artifact：

1. **展示 theme showcase**：显示 `theme-showcase.pdf` 文件，让用户直观看到所有可用 themes。不要对它做任何修改；只需展示文件供查看。
2. **询问选择**：询问要将哪个 theme 应用到 deck
3. **等待选择**：获取对所选 theme 的明确确认
4. **应用 theme**：一旦选定 theme，将所选 theme 的 colors 和 fonts 应用到 deck/artifact

## 可用 Themes

以下 10 个 themes 可用，每个都展示在 `theme-showcase.pdf` 中：

1. **Ocean Depths** - 专业且平静的海洋主题
2. **Sunset Boulevard** - 温暖而鲜明的日落色彩
3. **Forest Canopy** - 自然而沉稳的大地色调
4. **Modern Minimalist** - 干净且现代的灰阶风格
5. **Golden Hour** - 丰富而温暖的秋日调色板
6. **Arctic Frost** - 清冷明快的冬季灵感主题
7. **Desert Rose** - 柔和且精致的 dusty tones
8. **Tech Innovation** - 大胆现代的 tech aesthetic
9. **Botanical Garden** - 清新有机的花园色彩
10. **Midnight Galaxy** - 戏剧化且宇宙感的深色调

## Theme 详情

每个 theme 都在 `themes/` 目录中定义，包含完整 specifications，包括：
- 带 hex codes 的协调 color palette
- 用于 headers 和 body text 的互补 font pairings
- 适合不同 contexts 和 audiences 的独特 visual identity

## 应用流程

选择首选 theme 后：
1. 从 `themes/` 目录读取对应 theme file
2. 在整个 deck 中一致应用指定 colors 和 fonts
3. 确保适当 contrast 和 readability
4. 在所有 slides 中保持该 theme 的 visual identity

## 创建你自己的 Theme
当现有 themes 都不适合某个 artifact 时，创建 custom theme。基于提供的输入，生成一个与上述 themes 类似的新 theme。给 theme 起一个类似的名称，用来描述 font/color combinations 所表达的内容。使用提供的任何基本描述来选择合适的 colors/fonts。生成 theme 后，展示它以供 review 和 verification。随后按上文所述应用 theme。
