---
name: seaborn
description: 带 pandas integration 的 statistical visualization。用于快速探索 distributions、relationships 和 categorical comparisons，并提供美观默认值。最适合 box plots、violin plots、pair plots、heatmaps。构建在 matplotlib 之上。Interactive plots 使用 plotly；publication styling 使用 scientific-visualization。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# Seaborn 统计可视化

## 概述

Seaborn 是一个用于创建 publication-quality statistical graphics 的 Python visualization library。将此 skill 用于 dataset-oriented plotting、multivariate analysis、automatic statistical estimation，以及用少量代码创建 complex multi-panel figures。

## 设计理念

Seaborn 遵循以下核心原则：

1. **Dataset-oriented**：直接使用 DataFrames 和 named variables，而不是 abstract coordinates
2. **Semantic mapping**：自动将 data values 转换为 visual properties（colors、sizes、styles）
3. **Statistical awareness**：内置 aggregation、error estimation 和 confidence intervals
4. **Aesthetic defaults**：开箱即用的 publication-ready themes 和 color palettes
5. **Matplotlib integration**：需要时完全兼容 matplotlib customization

## 快速开始

```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# Load example dataset
df = sns.load_dataset('tips')

# Create a simple visualization
sns.scatterplot(data=df, x='total_bill', y='tip', hue='day')
plt.show()
```

## 核心绘图接口

### Function interface（传统）

Function interface 按 visualization type 提供 specialized plotting functions。每个 category 都有 **axes-level** functions（绘制到单个 axes）和 **figure-level** functions（管理整个 figure 和 faceting）。

**何时使用：**
- 快速 exploratory analysis
- 单一用途 visualizations
- 需要特定 plot type 时

### Objects interface（现代）

`seaborn.objects` interface 提供类似 ggplot2 的 declarative、composable API。通过链式方法指定 data mappings、marks、transformations 和 scales 来构建 visualizations。

**何时使用：**
- Complex layered visualizations
- 需要对 transformations 做 fine-grained control
- 构建 custom plot types
- Programmatic plot generation

```python
from seaborn import objects as so

# Declarative syntax
(
    so.Plot(data=df, x='total_bill', y='tip')
    .add(so.Dot(), color='day')
    .add(so.Line(), so.PolyFit())
)
```

## 按类别的绘图函数

### Relational plots（变量之间的关系）

**用途：** 探索两个或更多 variables 的关系

- `scatterplot()` - 以 points 显示 individual observations
- `lineplot()` - 展示 trends 和 changes（自动 aggregate 并计算 CI）
- `relplot()` - 带 automatic faceting 的 figure-level interface

**关键参数：**
- `x`, `y` - primary variables
- `hue` - 额外 categorical/continuous variable 的 color encoding
- `size` - point/line size encoding
- `style` - marker/line style encoding
- `col`, `row` - facet 到多个 subplots（仅 figure-level）

```python
# Scatter with multiple semantic mappings
sns.scatterplot(data=df, x='total_bill', y='tip',
                hue='time', size='size', style='sex')

# Line plot with confidence intervals
sns.lineplot(data=timeseries, x='date', y='value', hue='category')

# Faceted relational plot
sns.relplot(data=df, x='total_bill', y='tip',
            col='time', row='sex', hue='smoker', kind='scatter')
```

### Distribution plots（单变量和双变量分布）

**用途：** 理解 data spread、shape 和 probability density

- `histplot()` - 具有 flexible binning 的 bar-based frequency distributions
- `kdeplot()` - 使用 Gaussian kernels 的 smooth density estimates
- `ecdfplot()` - empirical cumulative distribution（无需调整参数）
- `rugplot()` - individual observation tick marks
- `displot()` - univariate 和 bivariate distributions 的 figure-level interface
- `jointplot()` - 带 marginal distributions 的 bivariate plot
- `pairplot()` - dataset 中 pairwise relationships 的矩阵

**关键参数：**
- `x`, `y` - variables（univariate 时 y 可选）
- `hue` - 按 category 分离 distributions
- `stat` - normalization："count", "frequency", "probability", "density"
- `bins` / `binwidth` - histogram binning control
- `bw_adjust` - KDE bandwidth multiplier（越高越平滑）
- `fill` - 填充曲线下区域
- `multiple` - 如何处理 hue："layer", "stack", "dodge", "fill"

```python
# Histogram with density normalization
sns.histplot(data=df, x='total_bill', hue='time',
             stat='density', multiple='stack')

# Bivariate KDE with contours
sns.kdeplot(data=df, x='total_bill', y='tip',
            fill=True, levels=5, thresh=0.1)

# Joint plot with marginals
sns.jointplot(data=df, x='total_bill', y='tip',
              kind='scatter', hue='time')

# Pairwise relationships
sns.pairplot(data=df, hue='species', corner=True)
```

### Categorical plots（跨类别比较）

**用途：** 比较 discrete categories 间的 distributions 或 statistics

**Categorical scatterplots：**
- `stripplot()` - 带 jitter 的 points，显示所有 observations
- `swarmplot()` - non-overlapping points（beeswarm algorithm）

**Distribution comparisons：**
- `boxplot()` - quartiles 和 outliers
- `violinplot()` - KDE + quartile information
- `boxenplot()` - 适合 larger datasets 的增强 boxplot

**Statistical estimates：**
- `barplot()` - mean/aggregate 和 confidence intervals
- `pointplot()` - point estimates 和 connecting lines
- `countplot()` - 每个 category 的 observations count

**Figure-level：**
- `catplot()` - Faceted categorical plots（设置 `kind` parameter）

**关键参数：**
- `x`, `y` - variables（通常一个是 categorical）
- `hue` - additional categorical grouping
- `order`, `hue_order` - 控制 category ordering
- `dodge` - 将 hue levels side-by-side 分开
- `orient` - "v"（vertical）或 "h"（horizontal）
- `kind` - catplot 的 plot type："strip", "swarm", "box", "violin", "bar", "point"

```python
# Swarm plot showing all points
sns.swarmplot(data=df, x='day', y='total_bill', hue='sex')

# Violin plot with split for comparison
sns.violinplot(data=df, x='day', y='total_bill',
               hue='sex', split=True)

# Bar plot with error bars
sns.barplot(data=df, x='day', y='total_bill',
            hue='sex', estimator='mean', errorbar='ci')

# Faceted categorical plot
sns.catplot(data=df, x='day', y='total_bill',
            col='time', kind='box')
```

### Regression plots（线性关系）

**用途：** 可视化 linear regressions 和 residuals

- `regplot()` - Axes-level regression plot，包含 scatter + fit line
- `lmplot()` - 支持 faceting 的 figure-level
- `residplot()` - 用于评估 model fit 的 residual plot

**关键参数：**
- `x`, `y` - 要回归的 variables
- `order` - polynomial regression order
- `logistic` - 拟合 logistic regression
- `robust` - 使用 robust regression（对 outliers 不敏感）
- `ci` - confidence interval width（默认 95）
- `scatter_kws`, `line_kws` - 定制 scatter 和 line properties

```python
# Simple linear regression
sns.regplot(data=df, x='total_bill', y='tip')

# Polynomial regression with faceting
sns.lmplot(data=df, x='total_bill', y='tip',
           col='time', order=2, ci=95)

# Check residuals
sns.residplot(data=df, x='total_bill', y='tip')
```

### Matrix plots（矩形数据）

**用途：** 可视化 matrices、correlations 和 grid-structured data

- `heatmap()` - 带 annotations 的 color-encoded matrix
- `clustermap()` - Hierarchically-clustered heatmap

**关键参数：**
- `data` - 2D rectangular dataset（DataFrame 或 array）
- `annot` - 在 cells 中显示 values
- `fmt` - annotations 的 format string（例如 ".2f"）
- `cmap` - colormap name
- `center` - colormap center 的 value（用于 diverging colormaps）
- `vmin`, `vmax` - color scale limits
- `square` - 强制 square cells
- `linewidths` - cells 间距

```python
# Correlation heatmap
corr = df.corr()
sns.heatmap(corr, annot=True, fmt='.2f',
            cmap='coolwarm', center=0, square=True)

# Clustered heatmap
sns.clustermap(data, cmap='viridis',
               standard_scale=1, figsize=(10, 10))
```

## Multi-Plot Grids

Seaborn 提供 grid objects，用于创建 complex multi-panel figures：

### FacetGrid

基于 categorical variables 创建 subplots。通过 figure-level functions（`relplot`、`displot`、`catplot`）调用时最有用，也可直接用于 custom plots。

```python
g = sns.FacetGrid(df, col='time', row='sex', hue='smoker')
g.map(sns.scatterplot, 'total_bill', 'tip')
g.add_legend()
```

### PairGrid

展示 dataset 中所有 variables 的 pairwise relationships。

```python
g = sns.PairGrid(df, hue='species')
g.map_upper(sns.scatterplot)
g.map_lower(sns.kdeplot)
g.map_diag(sns.histplot)
g.add_legend()
```

### JointGrid

将 bivariate plot 与 marginal distributions 组合。

```python
g = sns.JointGrid(data=df, x='total_bill', y='tip')
g.plot_joint(sns.scatterplot)
g.plot_marginals(sns.histplot)
```

## Figure-Level vs Axes-Level Functions

理解这一区分对高效使用 seaborn 很关键：

### Axes-Level Functions
- 绘制到单个 matplotlib `Axes` object
- 容易整合进 complex matplotlib figures
- 接受 `ax=` 参数进行 precise placement
- 返回 `Axes` object
- Examples：`scatterplot`、`histplot`、`boxplot`、`regplot`、`heatmap`

**When to use：**
- 构建 custom multi-plot layouts
- 组合不同 plot types
- 需要 matplotlib-level control
- 与 existing matplotlib code 集成

```python
fig, axes = plt.subplots(2, 2, figsize=(10, 10))
sns.scatterplot(data=df, x='x', y='y', ax=axes[0, 0])
sns.histplot(data=df, x='x', ax=axes[0, 1])
sns.boxplot(data=df, x='cat', y='y', ax=axes[1, 0])
sns.kdeplot(data=df, x='x', y='y', ax=axes[1, 1])
```

### Figure-Level Functions
- 管理整个 figure，包括所有 subplots
- 通过 `col` 和 `row` parameters 内置 faceting
- 返回 `FacetGrid`、`JointGrid` 或 `PairGrid` objects
- 使用 `height` 和 `aspect` 控制 sizing（per subplot）
- 不能放入 existing figure
- Examples：`relplot`、`displot`、`catplot`、`lmplot`、`jointplot`、`pairplot`

**When to use：**
- Faceted visualizations（small multiples）
- Quick exploratory analysis
- Consistent multi-panel layouts
- 不需要与其他 plot types 组合

```python
# Automatic faceting
sns.relplot(data=df, x='x', y='y', col='category', row='group',
            hue='type', height=3, aspect=1.2)
```

## Data Structure Requirements

### Long-Form Data（首选）

每个 variable 是一列，每个 observation 是一行。这种 "tidy" format 提供最大灵活性：

```python
# Long-form structure
   subject  condition  measurement
0        1    control         10.5
1        1  treatment         12.3
2        2    control          9.8
3        2  treatment         13.1
```

**Advantages：**
- 适用于所有 seaborn functions
- 容易将 variables 重新映射到 visual properties
- 支持任意 complexity
- 对 DataFrame operations 自然

### Wide-Form Data

Variables 分布在多列。适合简单 rectangular data：

```python
# Wide-form structure
   control  treatment
0     10.5       12.3
1      9.8       13.1
```

**Use cases：**
- Simple time series
- Correlation matrices
- Heatmaps
- Array data 的 quick plots

**Converting wide to long：**
```python
df_long = df.melt(var_name='condition', value_name='measurement')
```

## Color Palettes

Seaborn 为不同 data types 提供精心设计的 color palettes：

### Qualitative Palettes（Categorical Data）

通过 hue variation 区分类别：
- `"deep"` - 默认，颜色鲜明
- `"muted"` - 更柔和、低饱和
- `"pastel"` - 浅色、低饱和
- `"bright"` - 高饱和
- `"dark"` - 暗色值
- `"colorblind"` - 对 color vision deficiency 安全

```python
sns.set_palette("colorblind")
sns.color_palette("Set2")
```

### Sequential Palettes（Ordered Data）

显示从 low 到 high values 的 progression：
- `"rocket"`, `"mako"` - 宽 luminance range（适合 heatmaps）
- `"flare"`, `"crest"` - 受限 luminance（适合 points/lines）
- `"viridis"`, `"magma"`, `"plasma"` - Matplotlib perceptually uniform

```python
sns.heatmap(data, cmap='rocket')
sns.kdeplot(data=df, x='x', y='y', cmap='mako', fill=True)
```

### Diverging Palettes（Centered Data）

强调相对 midpoint 的 deviations：
- `"vlag"` - Blue to red
- `"icefire"` - Blue to orange
- `"coolwarm"` - Cool to warm
- `"Spectral"` - Rainbow diverging

```python
sns.heatmap(correlation_matrix, cmap='vlag', center=0)
```

### Custom Palettes

```python
# Create custom palette
custom = sns.color_palette("husl", 8)

# Light to dark gradient
palette = sns.light_palette("seagreen", as_cmap=True)

# Diverging palette from hues
palette = sns.diverging_palette(250, 10, as_cmap=True)
```

## Theming and Aesthetics

### Set Theme

`set_theme()` 控制整体外观：

```python
# Set complete theme
sns.set_theme(style='whitegrid', palette='pastel', font='sans-serif')

# Reset to defaults
sns.set_theme()
```

### Styles

控制 background 和 grid 外观：
- `"darkgrid"` - 灰色 background 和白色 grid（默认）
- `"whitegrid"` - 白色 background 和灰色 grid
- `"dark"` - 灰色 background，无 grid
- `"white"` - 白色 background，无 grid
- `"ticks"` - 带 axis ticks 的白色 background

```python
sns.set_style("whitegrid")

# Remove spines
sns.despine(left=False, bottom=False, offset=10, trim=True)

# Temporary style
with sns.axes_style("white"):
    sns.scatterplot(data=df, x='x', y='y')
```

### Contexts

为不同 use cases 缩放元素：
- `"paper"` - 最小（默认）
- `"notebook"` - 稍大
- `"talk"` - Presentation slides
- `"poster"` - Large format

```python
sns.set_context("talk", font_scale=1.2)

# Temporary context
with sns.plotting_context("poster"):
    sns.barplot(data=df, x='category', y='value')
```

## Best Practices

### 1. Data Preparation

始终使用结构良好且 column names 有意义的 DataFrames：

```python
# Good: Named columns in DataFrame
df = pd.DataFrame({'bill': bills, 'tip': tips, 'day': days})
sns.scatterplot(data=df, x='bill', y='tip', hue='day')

# Avoid: Unnamed arrays
sns.scatterplot(x=x_array, y=y_array)  # Loses axis labels
```

### 2. Choose the Right Plot Type

**Continuous x, continuous y：** `scatterplot`, `lineplot`, `kdeplot`, `regplot`
**Continuous x, categorical y：** `violinplot`, `boxplot`, `stripplot`, `swarmplot`
**One continuous variable：** `histplot`, `kdeplot`, `ecdfplot`
**Correlations/matrices：** `heatmap`, `clustermap`
**Pairwise relationships：** `pairplot`, `jointplot`

### 3. Use Figure-Level Functions for Faceting

```python
# Instead of manual subplot creation
sns.relplot(data=df, x='x', y='y', col='category', col_wrap=3)

# Not: Creating subplots manually for simple faceting
```

### 4. Leverage Semantic Mappings

使用 `hue`、`size` 和 `style` 编码额外 dimensions：

```python
sns.scatterplot(data=df, x='x', y='y',
                hue='category',      # Color by category
                size='importance',    # Size by continuous variable
                style='type')         # Marker style by type
```

### 5. Control Statistical Estimation

许多 functions 会自动计算 statistics。理解并定制这些行为：

```python
# Lineplot computes mean and 95% CI by default
sns.lineplot(data=df, x='time', y='value',
             errorbar='sd')  # Use standard deviation instead

# Barplot computes mean by default
sns.barplot(data=df, x='category', y='value',
            estimator='median',  # Use median instead
            errorbar=('ci', 95))  # Bootstrapped CI
```

### 6. Combine with Matplotlib

Seaborn 可与 matplotlib 无缝集成以进行 fine-tuning：

```python
ax = sns.scatterplot(data=df, x='x', y='y')
ax.set(xlabel='Custom X Label', ylabel='Custom Y Label',
       title='Custom Title')
ax.axhline(y=0, color='r', linestyle='--')
plt.tight_layout()
```

### 7. Save High-Quality Figures

```python
fig = sns.relplot(data=df, x='x', y='y', col='group')
fig.savefig('figure.png', dpi=300, bbox_inches='tight')
fig.savefig('figure.pdf')  # Vector format for publications
```

## Common Patterns

### Exploratory Data Analysis

```python
# Quick overview of all relationships
sns.pairplot(data=df, hue='target', corner=True)

# Distribution exploration
sns.displot(data=df, x='variable', hue='group',
            kind='kde', fill=True, col='category')

# Correlation analysis
corr = df.corr()
sns.heatmap(corr, annot=True, cmap='coolwarm', center=0)
```

### Publication-Quality Figures

```python
sns.set_theme(style='ticks', context='paper', font_scale=1.1)

g = sns.catplot(data=df, x='treatment', y='response',
                col='cell_line', kind='box', height=3, aspect=1.2)
g.set_axis_labels('Treatment Condition', 'Response (μM)')
g.set_titles('{col_name}')
sns.despine(trim=True)

g.savefig('figure.pdf', dpi=300, bbox_inches='tight')
```

### Complex Multi-Panel Figures

```python
# Using matplotlib subplots with seaborn
fig, axes = plt.subplots(2, 2, figsize=(12, 10))

sns.scatterplot(data=df, x='x1', y='y', hue='group', ax=axes[0, 0])
sns.histplot(data=df, x='x1', hue='group', ax=axes[0, 1])
sns.violinplot(data=df, x='group', y='y', ax=axes[1, 0])
sns.heatmap(df.pivot_table(values='y', index='x1', columns='x2'),
            ax=axes[1, 1], cmap='viridis')

plt.tight_layout()
```

### Time Series with Confidence Bands

```python
# Lineplot automatically aggregates and shows CI
sns.lineplot(data=timeseries, x='date', y='measurement',
             hue='sensor', style='location', errorbar='sd')

# For more control
g = sns.relplot(data=timeseries, x='date', y='measurement',
                col='location', hue='sensor', kind='line',
                height=4, aspect=1.5, errorbar=('ci', 95))
g.set_axis_labels('Date', 'Measurement (units)')
```

## Troubleshooting

### Issue: Legend Outside Plot Area

Figure-level functions 默认将 legends 放在外部。移到内部：

```python
g = sns.relplot(data=df, x='x', y='y', hue='category')
g._legend.set_bbox_to_anchor((0.9, 0.5))  # Adjust position
```

### Issue: Overlapping Labels

```python
plt.xticks(rotation=45, ha='right')
plt.tight_layout()
```

### Issue: Figure Too Small

对于 figure-level functions：
```python
sns.relplot(data=df, x='x', y='y', height=6, aspect=1.5)
```

对于 axes-level functions：
```python
fig, ax = plt.subplots(figsize=(10, 6))
sns.scatterplot(data=df, x='x', y='y', ax=ax)
```

### Issue: Colors Not Distinct Enough

```python
# Use a different palette
sns.set_palette("bright")

# Or specify number of colors
palette = sns.color_palette("husl", n_colors=len(df['category'].unique()))
sns.scatterplot(data=df, x='x', y='y', hue='category', palette=palette)
```

### Issue: KDE Too Smooth or Jagged

```python
# Adjust bandwidth
sns.kdeplot(data=df, x='x', bw_adjust=0.5)  # Less smooth
sns.kdeplot(data=df, x='x', bw_adjust=2)    # More smooth
```

## 资源

此 skill 包含可用于深入探索的 reference materials：

### references/

- `function_reference.md` - 所有 seaborn functions 的完整列表，含 parameters 和 examples
- `objects_interface.md` - 现代 seaborn.objects API 的详细指南
- `examples.md` - 不同 analysis scenarios 的常见 use cases 和 code patterns

按需加载 reference files，以获取详细 function signatures、advanced parameters 或具体 examples。
