---
name: scientific-visualization
description: 用于 publication-ready figures 的 meta-skill。用于创建 journal submission figures，要求 multi-panel layouts、significance annotations、error bars、colorblind-safe palettes 和特定 journal formatting（Nature、Science、Cell）。协调 matplotlib/seaborn/plotly 与 publication styles。快速探索可直接使用 seaborn 或 plotly。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Scientific Visualization

## 概述

Scientific visualization 将 data 转化为清晰、准确且可发表的 figures。使用 matplotlib、seaborn 和 plotly 为 manuscripts 创建 journal-ready plots，包括 multi-panel layouts、error bars、significance markers 和 colorblind-safe palettes，并导出为 PDF/EPS/TIFF。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 为 scientific manuscripts 创建 plots 或 visualizations
- 准备 journal submission figures（Nature、Science、Cell、PLOS 等）
- 确保 figures colorblind-friendly 且 accessible
- 创建 styling 一致的 multi-panel figures
- 以正确 resolution 和 format 导出 figures
- 遵循特定 publication guidelines
- 改进 existing figures 以符合 publication standards
- 创建同时适用于 color 和 grayscale 的 figures

## Quick Start Guide

### Basic Publication-Quality Figure

```python
import matplotlib.pyplot as plt
import numpy as np

# Apply publication style (from scripts/style_presets.py)
from style_presets import apply_publication_style
apply_publication_style('default')

# Create figure with appropriate size (single column = 3.5 inches)
fig, ax = plt.subplots(figsize=(3.5, 2.5))

# Plot data
x = np.linspace(0, 10, 100)
ax.plot(x, np.sin(x), label='sin(x)')
ax.plot(x, np.cos(x), label='cos(x)')

# Proper labeling with units
ax.set_xlabel('Time (seconds)')
ax.set_ylabel('Amplitude (mV)')
ax.legend(frameon=False)

# Remove unnecessary spines
ax.spines['top'].set_visible(False)
ax.spines['right'].set_visible(False)

# Save in publication formats (from scripts/figure_export.py)
from figure_export import save_publication_figure
save_publication_figure(fig, 'figure1', formats=['pdf', 'png'], dpi=300)
```

### Using Pre-configured Styles

使用 `assets/` 中的 matplotlib style files 应用 journal-specific styles：

```python
import matplotlib.pyplot as plt

# Option 1: Use style file directly
plt.style.use('assets/nature.mplstyle')

# Option 2: Use style_presets.py helper
from style_presets import configure_for_journal
configure_for_journal('nature', figure_width='single')

# Now create figures - they'll automatically match Nature specifications
fig, ax = plt.subplots()
# ... your plotting code ...
```

### Quick Start with Seaborn

对 statistical plots，将 seaborn 与 publication styling 结合使用：

```python
import seaborn as sns
import matplotlib.pyplot as plt
from style_presets import apply_publication_style

# Apply publication style
apply_publication_style('default')
sns.set_theme(style='ticks', context='paper', font_scale=1.1)
sns.set_palette('colorblind')

# Create statistical comparison figure
fig, ax = plt.subplots(figsize=(3.5, 3))
sns.boxplot(data=df, x='treatment', y='response', 
            order=['Control', 'Low', 'High'], palette='Set2', ax=ax)
sns.stripplot(data=df, x='treatment', y='response',
              order=['Control', 'Low', 'High'], 
              color='black', alpha=0.3, size=3, ax=ax)
ax.set_ylabel('Response (μM)')
sns.despine()

# Save figure
from figure_export import save_publication_figure
save_publication_figure(fig, 'treatment_comparison', formats=['pdf', 'png'], dpi=300)
```

## Core Principles and Best Practices

### 1. Resolution and File Format

**Critical requirements**（详见 `references/publication_guidelines.md`）：
- **Raster images**（photos、microscopy）：300-600 DPI
- **Line art**（graphs、plots）：600-1200 DPI 或 vector format
- **Vector formats**（首选）：PDF、EPS、SVG
- **Raster formats**：TIFF、PNG（scientific data 永不使用 JPEG）

**Implementation：**
```python
# Use the figure_export.py script for correct settings
from figure_export import save_publication_figure

# Saves in multiple formats with proper DPI
save_publication_figure(fig, 'myfigure', formats=['pdf', 'png'], dpi=300)

# Or save for specific journal requirements
from figure_export import save_for_journal
save_for_journal(fig, 'figure1', journal='nature', figure_type='combination')
```

### 2. Color Selection - Colorblind Accessibility

**始终使用 colorblind-friendly palettes**（详见 `references/color_palettes.md`）：

**推荐：Okabe-Ito palette**（所有类型 color blindness 都可区分）：
```python
# Option 1: Use assets/color_palettes.py
from color_palettes import OKABE_ITO_LIST, apply_palette
apply_palette('okabe_ito')

# Option 2: Manual specification
okabe_ito = ['#E69F00', '#56B4E9', '#009E73', '#F0E442',
             '#0072B2', '#D55E00', '#CC79A7', '#000000']
plt.rcParams['axes.prop_cycle'] = plt.cycler(color=okabe_ito)
```

**Heatmaps/continuous data：**
- 使用 perceptually uniform colormaps：`viridis`、`plasma`、`cividis`
- 避免 red-green diverging maps（改用 `PuOr`、`RdBu`、`BrBG`）
- 永远不要使用 `jet` 或 `rainbow` colormaps

**始终在 grayscale 中测试 figures**，确保可解释。

### 3. Typography and Text

**Font guidelines**（详见 `references/publication_guidelines.md`）：
- Sans-serif fonts：Arial、Helvetica、Calibri
- **final print size** 下的最小字号：
  - Axis labels：7-9 pt
  - Tick labels：6-8 pt
  - Panel labels：8-12 pt（bold）
- Labels 使用 sentence case："Time (hours)" 而不是 "TIME (HOURS)"
- 始终在括号中包含 units

**Implementation：**
```python
# Set fonts globally
import matplotlib as mpl
mpl.rcParams['font.family'] = 'sans-serif'
mpl.rcParams['font.sans-serif'] = ['Arial', 'Helvetica']
mpl.rcParams['font.size'] = 8
mpl.rcParams['axes.labelsize'] = 9
mpl.rcParams['xtick.labelsize'] = 7
mpl.rcParams['ytick.labelsize'] = 7
```

### 4. Figure Dimensions

**Journal-specific widths**（详见 `references/journal_requirements.md`）：
- **Nature**：Single 89 mm，Double 183 mm
- **Science**：Single 55 mm，Double 175 mm
- **Cell**：Single 85 mm，Double 178 mm

**检查 figure size compliance：**
```python
from figure_export import check_figure_size

fig = plt.figure(figsize=(3.5, 3))  # 89 mm for Nature
check_figure_size(fig, journal='nature')
```

### 5. Multi-Panel Figures

**Best practices：**
- 使用 bold letters 标记 panels：**A**、**B**、**C**（多数 journals 用 uppercase，Nature 用 lowercase）
- 所有 panels 保持 consistent styling
- 尽可能沿边缘对齐 panels
- Panels 之间保留足够 white space

**Example implementation**（完整代码见 `references/matplotlib_examples.md`）：
```python
from string import ascii_uppercase

fig = plt.figure(figsize=(7, 4))
gs = fig.add_gridspec(2, 2, hspace=0.4, wspace=0.4)

ax1 = fig.add_subplot(gs[0, 0])
ax2 = fig.add_subplot(gs[0, 1])
# ... create other panels ...

# Add panel labels
for i, ax in enumerate([ax1, ax2, ...]):
    ax.text(-0.15, 1.05, ascii_uppercase[i], transform=ax.transAxes,
            fontsize=10, fontweight='bold', va='top')
```

## Common Tasks

### Task 1: Create a Publication-Ready Line Plot

完整代码见 `references/matplotlib_examples.md` Example 1。

**Key steps：**
1. 应用 publication style
2. 为 target journal 设置合适 figure size
3. 使用 colorblind-friendly colors
4. 添加正确表示的 error bars（SEM、SD 或 CI）
5. 带 units 标注 axes
6. 移除不必要 spines
7. 保存为 vector format

**使用 seaborn 自动生成 confidence intervals：**
```python
import seaborn as sns
fig, ax = plt.subplots(figsize=(5, 3))
sns.lineplot(data=timeseries, x='time', y='measurement',
             hue='treatment', errorbar=('ci', 95), 
             markers=True, ax=ax)
ax.set_xlabel('Time (hours)')
ax.set_ylabel('Measurement (AU)')
sns.despine()
```

### Task 2: Create a Multi-Panel Figure

完整代码见 `references/matplotlib_examples.md` Example 2。

**Key steps：**
1. 使用 `GridSpec` 做 flexible layout
2. 确保所有 panels styling 一致
3. 添加 bold panel labels（A、B、C 等）
4. 对齐相关 panels
5. 验证所有 text 在 final size 下可读

### Task 3: Create a Heatmap with Proper Colormap

完整代码见 `references/matplotlib_examples.md` Example 4。

**Key steps：**
1. 使用 perceptually uniform colormap（`viridis`、`plasma`、`cividis`）
2. 包含 labeled colorbar
3. Diverging data 使用 colorblind-safe diverging map（`RdBu_r`、`PuOr`）
4. 为 diverging maps 设置合适 center value
5. 测试 grayscale 外观

**使用 seaborn 绘制 correlation matrices：**
```python
import seaborn as sns
fig, ax = plt.subplots(figsize=(5, 4))
corr = df.corr()
mask = np.triu(np.ones_like(corr, dtype=bool))
sns.heatmap(corr, mask=mask, annot=True, fmt='.2f',
            cmap='RdBu_r', center=0, square=True,
            linewidths=1, cbar_kws={'shrink': 0.8}, ax=ax)
```

### Task 4: Prepare Figure for Specific Journal

**Workflow：**
1. 检查 journal requirements：`references/journal_requirements.md`
2. 为 journal 配置 matplotlib：
   ```python
   from style_presets import configure_for_journal
   configure_for_journal('nature', figure_width='single')
   ```
3. 创建 figure（会自动正确 sizing）
4. 按 journal specifications 导出：
   ```python
   from figure_export import save_for_journal
   save_for_journal(fig, 'figure1', journal='nature', figure_type='line_art')
   ```

### Task 5: Fix an Existing Figure to Meet Publication Standards

**Checklist approach**（完整 checklist 见 `references/publication_guidelines.md`）：

1. **Check resolution**：验证 DPI 是否满足 journal requirements
2. **Check file format**：Plots 用 vector，images 用 TIFF/PNG
3. **Check colors**：确保 colorblind-friendly
4. **Check fonts**：Final size 下 minimum 6-7 pt，sans-serif
5. **Check labels**：所有 axes 带 units
6. **Check size**：匹配 journal column width
7. **Test grayscale**：不用 color 也能解释 figure
8. **Remove chart junk**：去除不必要 grids、3D effects、shadows

### Task 6: Create Colorblind-Friendly Visualizations

**Strategy：**
1. 使用 `assets/color_palettes.py` 中的 approved palettes
2. 添加 redundant encoding（line styles、markers、patterns）
3. 用 colorblind simulator 测试
4. 确保 grayscale compatibility

**Example：**
```python
from color_palettes import apply_palette
import matplotlib.pyplot as plt

apply_palette('okabe_ito')

# Add redundant encoding beyond color
line_styles = ['-', '--', '-.', ':']
markers = ['o', 's', '^', 'v']

for i, (data, label) in enumerate(datasets):
    plt.plot(x, data, linestyle=line_styles[i % 4],
             marker=markers[i % 4], label=label)
```

## Statistical Rigor

**始终包含：**
- Error bars（SD、SEM 或 CI，应在 caption 中说明）
- Figure 或 caption 中的 sample size（n）
- Statistical significance markers（*、**、***）
- 尽可能显示 individual data points（不只是 summary statistics）

**Example with statistics：**
```python
# Show individual points with summary statistics
ax.scatter(x_jittered, individual_points, alpha=0.4, s=8)
ax.errorbar(x, means, yerr=sems, fmt='o', capsize=3)

# Mark significance
ax.text(1.5, max_y * 1.1, '***', ha='center', fontsize=8)
```

## Working with Different Plotting Libraries

### Matplotlib
- 对 publication details 控制最多
- 最适合 complex multi-panel figures
- 使用提供的 style files 保持 formatting 一致
- 丰富示例见 `references/matplotlib_examples.md`

### Seaborn

Seaborn 是构建在 matplotlib 上的 high-level、dataset-oriented statistical graphics 接口。它能用少量代码创建 publication-quality statistical visualizations，同时保持与 matplotlib customization 的完全兼容。

**Scientific visualization 的关键优势：**
- 自动 statistical estimation 和 confidence intervals
- 内置支持 multi-panel figures（faceting）
- 默认提供 colorblind-friendly palettes
- 使用 pandas DataFrames 的 dataset-oriented API
- 将 variables 语义映射到 visual properties

#### Quick Start with Publication Style

始终先应用 matplotlib publication styles，再配置 seaborn：

```python
import seaborn as sns
import matplotlib.pyplot as plt
from style_presets import apply_publication_style

# Apply publication style
apply_publication_style('default')

# Configure seaborn for publication
sns.set_theme(style='ticks', context='paper', font_scale=1.1)
sns.set_palette('colorblind')  # Use colorblind-safe palette

# Create figure
fig, ax = plt.subplots(figsize=(3.5, 2.5))
sns.scatterplot(data=df, x='time', y='response', 
                hue='treatment', style='condition', ax=ax)
sns.despine()  # Remove top and right spines
```

#### Common Plot Types for Publications

**Statistical comparisons：**
```python
# Box plot with individual points for transparency
fig, ax = plt.subplots(figsize=(3.5, 3))
sns.boxplot(data=df, x='treatment', y='response', 
            order=['Control', 'Low', 'High'], palette='Set2', ax=ax)
sns.stripplot(data=df, x='treatment', y='response',
              order=['Control', 'Low', 'High'], 
              color='black', alpha=0.3, size=3, ax=ax)
ax.set_ylabel('Response (μM)')
sns.despine()
```

**Distribution analysis：**
```python
# Violin plot with split comparison
fig, ax = plt.subplots(figsize=(4, 3))
sns.violinplot(data=df, x='timepoint', y='expression',
               hue='treatment', split=True, inner='quartile', ax=ax)
ax.set_ylabel('Gene Expression (AU)')
sns.despine()
```

**Correlation matrices：**
```python
# Heatmap with proper colormap and annotations
fig, ax = plt.subplots(figsize=(5, 4))
corr = df.corr()
mask = np.triu(np.ones_like(corr, dtype=bool))  # Show only lower triangle
sns.heatmap(corr, mask=mask, annot=True, fmt='.2f',
            cmap='RdBu_r', center=0, square=True,
            linewidths=1, cbar_kws={'shrink': 0.8}, ax=ax)
plt.tight_layout()
```

**Time series with confidence bands：**
```python
# Line plot with automatic CI calculation
fig, ax = plt.subplots(figsize=(5, 3))
sns.lineplot(data=timeseries, x='time', y='measurement',
             hue='treatment', style='replicate',
             errorbar=('ci', 95), markers=True, dashes=False, ax=ax)
ax.set_xlabel('Time (hours)')
ax.set_ylabel('Measurement (AU)')
sns.despine()
```

#### Multi-Panel Figures with Seaborn

**使用 FacetGrid 自动 faceting：**
```python
# Create faceted plot
g = sns.relplot(data=df, x='dose', y='response',
                hue='treatment', col='cell_line', row='timepoint',
                kind='line', height=2.5, aspect=1.2,
                errorbar=('ci', 95), markers=True)
g.set_axis_labels('Dose (μM)', 'Response (AU)')
g.set_titles('{row_name} | {col_name}')
sns.despine()

# Save with correct DPI
from figure_export import save_publication_figure
save_publication_figure(g.figure, 'figure_facets', 
                       formats=['pdf', 'png'], dpi=300)
```

**Combining seaborn with matplotlib subplots：**
```python
# Create custom multi-panel layout
fig, axes = plt.subplots(2, 2, figsize=(7, 6))

# Panel A: Scatter with regression
sns.regplot(data=df, x='predictor', y='response', ax=axes[0, 0])
axes[0, 0].text(-0.15, 1.05, 'A', transform=axes[0, 0].transAxes,
                fontsize=10, fontweight='bold')

# Panel B: Distribution comparison
sns.violinplot(data=df, x='group', y='value', ax=axes[0, 1])
axes[0, 1].text(-0.15, 1.05, 'B', transform=axes[0, 1].transAxes,
                fontsize=10, fontweight='bold')

# Panel C: Heatmap
sns.heatmap(correlation_data, cmap='viridis', ax=axes[1, 0])
axes[1, 0].text(-0.15, 1.05, 'C', transform=axes[1, 0].transAxes,
                fontsize=10, fontweight='bold')

# Panel D: Time series
sns.lineplot(data=timeseries, x='time', y='signal', 
             hue='condition', ax=axes[1, 1])
axes[1, 1].text(-0.15, 1.05, 'D', transform=axes[1, 1].transAxes,
                fontsize=10, fontweight='bold')

plt.tight_layout()
sns.despine()
```

#### Color Palettes for Publications

Seaborn 包含多个 colorblind-safe palettes：

```python
# Use built-in colorblind palette (recommended)
sns.set_palette('colorblind')

# Or specify custom colorblind-safe colors (Okabe-Ito)
okabe_ito = ['#E69F00', '#56B4E9', '#009E73', '#F0E442',
             '#0072B2', '#D55E00', '#CC79A7', '#000000']
sns.set_palette(okabe_ito)

# For heatmaps and continuous data
sns.heatmap(data, cmap='viridis')  # Perceptually uniform
sns.heatmap(corr, cmap='RdBu_r', center=0)  # Diverging, centered
```

#### Choosing Between Axes-Level and Figure-Level Functions

**Axes-level functions**（例如 `scatterplot`、`boxplot`、`heatmap`）：
- 构建 custom multi-panel layouts 时使用
- 接受 `ax=` 参数以便 precise placement
- 更好地整合 matplotlib subplots
- 对 figure composition 控制更多

```python
fig, ax = plt.subplots(figsize=(3.5, 2.5))
sns.scatterplot(data=df, x='x', y='y', hue='group', ax=ax)
```

**Figure-level functions**（例如 `relplot`、`catplot`、`displot`）：
- 按 categorical variables 自动 faceting 时使用
- 创建 styling 一致的完整 figures
- 非常适合 exploratory analysis
- 使用 `height` 和 `aspect` 控制 sizing

```python
g = sns.relplot(data=df, x='x', y='y', col='category', kind='scatter')
```

#### Statistical Rigor with Seaborn

Seaborn 会自动计算并展示 uncertainty：

```python
# Line plot: shows mean ± 95% CI by default
sns.lineplot(data=df, x='time', y='value', hue='treatment',
             errorbar=('ci', 95))  # Can change to 'sd', 'se', etc.

# Bar plot: shows mean with bootstrapped CI
sns.barplot(data=df, x='treatment', y='response',
            errorbar=('ci', 95), capsize=0.1)

# Always specify error type in figure caption:
# "Error bars represent 95% confidence intervals"
```

#### Best Practices for Publication-Ready Seaborn Figures

1. **始终先设置 publication theme：**
   ```python
   sns.set_theme(style='ticks', context='paper', font_scale=1.1)
   ```

2. **使用 colorblind-safe palettes：**
   ```python
   sns.set_palette('colorblind')
   ```

3. **移除不必要元素：**
   ```python
   sns.despine()  # Remove top and right spines
   ```

4. **适当控制 figure size：**
   ```python
   # Axes-level: use matplotlib figsize
   fig, ax = plt.subplots(figsize=(3.5, 2.5))
   
   # Figure-level: use height and aspect
   g = sns.relplot(..., height=3, aspect=1.2)
   ```

5. **尽可能展示 individual data points：**
   ```python
   sns.boxplot(...)  # Summary statistics
   sns.stripplot(..., alpha=0.3)  # Individual points
   ```

6. **包含带 units 的正确 labels：**
   ```python
   ax.set_xlabel('Time (hours)')
   ax.set_ylabel('Expression (AU)')
   ```

7. **以正确 resolution 导出：**
   ```python
   from figure_export import save_publication_figure
   save_publication_figure(fig, 'figure_name', 
                          formats=['pdf', 'png'], dpi=300)
   ```

#### Advanced Seaborn Techniques

**用于 exploratory analysis 的 pairwise relationships：**
```python
# Quick overview of all relationships
g = sns.pairplot(data=df, hue='condition', 
                 vars=['gene1', 'gene2', 'gene3'],
                 corner=True, diag_kind='kde', height=2)
```

**Hierarchical clustering heatmap：**
```python
# Cluster samples and features
g = sns.clustermap(expression_data, method='ward', 
                   metric='euclidean', z_score=0,
                   cmap='RdBu_r', center=0, 
                   figsize=(10, 8), 
                   row_colors=condition_colors,
                   cbar_kws={'label': 'Z-score'})
```

**Joint distributions with marginals：**
```python
# Bivariate distribution with context
g = sns.jointplot(data=df, x='gene1', y='gene2',
                  hue='treatment', kind='scatter',
                  height=6, ratio=4, marginal_kws={'kde': True})
```

#### Common Seaborn Issues and Solutions

**Issue: Legend outside plot area**
```python
g = sns.relplot(...)
g._legend.set_bbox_to_anchor((0.9, 0.5))
```

**Issue: Overlapping labels**
```python
plt.xticks(rotation=45, ha='right')
plt.tight_layout()
```

**Issue: Text too small at final size**
```python
sns.set_context('paper', font_scale=1.2)  # Increase if needed
```

#### Additional Resources

更多 seaborn 详细信息见：
- `scientific-skills/seaborn/SKILL.md` - Comprehensive seaborn documentation
- `scientific-skills/seaborn/references/examples.md` - Practical use cases
- `scientific-skills/seaborn/references/function_reference.md` - Complete API reference
- `scientific-skills/seaborn/references/objects_interface.md` - Modern declarative API

### Plotly
- 用于 exploration 的 interactive figures
- 可导出 static images 用于 publication
- 配置 publication quality：
```python
fig.update_layout(
    font=dict(family='Arial, sans-serif', size=10),
    plot_bgcolor='white',
    # ... see matplotlib_examples.md Example 8
)
fig.write_image('figure.png', scale=3)  # scale=3 gives ~300 DPI
```

## 资源

### References Directory

**按需加载这些文件以获取详细信息：**

- **`publication_guidelines.md`**：Comprehensive best practices
  - Resolution 和 file format requirements
  - Typography guidelines
  - Layout 和 composition rules
  - Statistical rigor requirements
  - Complete publication checklist

- **`color_palettes.md`**：Color usage guide
  - 带 RGB values 的 colorblind-friendly palette specifications
  - Sequential 和 diverging colormap recommendations
  - Accessibility testing procedures
  - Domain-specific palettes（genomics、microscopy）

- **`journal_requirements.md`**：Journal-specific specifications
  - 各 publisher 的 technical requirements
  - File format 和 DPI specifications
  - Figure dimension requirements
  - Quick reference table

- **`matplotlib_examples.md`**：Practical code examples
  - 10 个完整 working examples
  - Line plots、bar plots、heatmaps、multi-panel figures
  - Journal-specific figure examples
  - 各 library tips（matplotlib、seaborn、plotly）

### Scripts Directory

**使用这些 helper scripts 自动化：**

- **`figure_export.py`**：Export utilities
  - `save_publication_figure()`：以正确 DPI 保存多种 formats
  - `save_for_journal()`：自动使用 journal-specific requirements
  - `check_figure_size()`：验证 dimensions 是否符合 journal specs
  - 直接运行：`python scripts/figure_export.py` 查看 examples

- **`style_presets.py`**：Pre-configured styles
  - `apply_publication_style()`：应用 preset styles（default、nature、science、cell）
  - `set_color_palette()`：快速切换 palette
  - `configure_for_journal()`：一条命令完成 journal configuration
  - 直接运行：`python scripts/style_presets.py` 查看 examples

### Assets Directory

**在 figures 中使用这些文件：**

- **`color_palettes.py`**：可导入 color definitions
  - 所有 recommended palettes 作为 Python constants
  - `apply_palette()` helper function
  - 可直接导入 notebooks/scripts

- **Matplotlib style files**：配合 `plt.style.use()` 使用
  - `publication.mplstyle`：General publication quality
  - `nature.mplstyle`：Nature journal specifications
  - `presentation.mplstyle`：Posters/slides 的 larger fonts

## Workflow Summary

**创建 publication figures 的推荐 workflow：**

1. **Plan**：确定 target journal、figure type 和 content
2. **Configure**：为 journal 应用合适 style
   ```python
   from style_presets import configure_for_journal
   configure_for_journal('nature', 'single')
   ```
3. **Create**：构建带正确 labels、colors、statistics 的 figure
4. **Verify**：检查 size、fonts、colors、accessibility
   ```python
   from figure_export import check_figure_size
   check_figure_size(fig, journal='nature')
   ```
5. **Export**：保存为 required formats
   ```python
   from figure_export import save_for_journal
   save_for_journal(fig, 'figure1', 'nature', 'combination')
   ```
6. **Review**：在 manuscript context 中以 final size 查看

## 应避免的常见陷阱

1. **Font too small**：Final size 打印时 text 不可读
2. **JPEG format**：Graphs/plots 永不使用 JPEG（会产生 artifacts）
3. **Red-green colors**：约 8% 男性无法区分
4. **Low resolution**：Publication 中 figures 像素化
5. **Missing units**：Axes 始终带 units
6. **3D effects**：扭曲 perception，应完全避免
7. **Chart junk**：移除不必要 gridlines 和 decorations
8. **Truncated axes**：除非有科学理由，bar charts 从 zero 开始
9. **Inconsistent styling**：同一 manuscript 中 figures 字体/颜色不一致
10. **No error bars**：始终显示 uncertainty

## Final Checklist

提交 figures 前验证：

- [ ] Resolution meets journal requirements（300+ DPI）
- [ ] File format is correct（plots 用 vector，images 用 TIFF）
- [ ] Figure size matches journal specifications
- [ ] All text readable at final size（≥6 pt）
- [ ] Colors are colorblind-friendly
- [ ] Figure works in grayscale
- [ ] All axes labeled with units
- [ ] Error bars present with definition in caption
- [ ] Panel labels present and consistent
- [ ] No chart junk or 3D effects
- [ ] Fonts consistent across all figures
- [ ] Statistical significance clearly marked
- [ ] Legend is clear and complete

使用此 skill 确保 scientific figures 达到最高 publication standards，同时对所有读者保持 accessible。
