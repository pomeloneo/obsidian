---
name: statsmodels
description: Python 的统计模型库。当您需要具有详细诊断、残差和 inference 的特定模型类（OLS、GLM、混合模型、ARIMA）时使用。最适合计量经济学，time series，严格的 inference 带系数表。对于使用 APA 报告进行指导的统计测试选择，请使用统计分析。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# Statsmodels：统计建模和计量经济学

## 概述

Statsmodels 是 Python 的首要统计建模库，提供各种统计方法的估计、inference 和诊断工具。将此技能应用于严格的统计分析，从简单的线性回归到复杂的 time series 模型和计量经济学分析。

## 何时使用此技能

该技能应该在以下情况下使用：
- 拟合回归模型（OLS、WLS、GLS、分位数回归）
- 执行广义线性建模（逻辑、泊松、伽玛等）
- 分析离散结果（二元、多项、计数、序数）
- 进行 time series 分析（ARIMA、SARIMAX、VAR、预测）
- 运行统计测试和诊断
- 测试模型假设（异方差、自相关、正态性）
- 检测异常值和有影响的观察结果
- 比较模型（AIC/BIC、似然比检验）
- 估计因果效应
- 生成可供发布的统计表和 inference

## 快速开始指南

### 线性回归 (OLS)

```python
import statsmodels.api as sm
import numpy as np
import pandas as pd

# Prepare data - ALWAYS add constant for intercept
X = sm.add_constant(X_data)

# Fit OLS model
model = sm.OLS(y, X)
results = model.fit()

# View comprehensive results
print(results.summary())

# Key results
print(f"R-squared: {results.rsquared:.4f}")
print(f"Coefficients:\\n{results.params}")
print(f"P-values:\\n{results.pvalues}")

# Predictions with confidence intervals
predictions = results.get_prediction(X_new)
pred_summary = predictions.summary_frame()
print(pred_summary)  # includes mean, CI, prediction intervals

# Diagnostics
from statsmodels.stats.diagnostic import het_breuschpagan
bp_test = het_breuschpagan(results.resid, X)
print(f"Breusch-Pagan p-value: {bp_test[1]:.4f}")

# Visualize residuals
import matplotlib.pyplot as plt
plt.scatter(results.fittedvalues, results.resid)
plt.axhline(y=0, color='r', linestyle='--')
plt.xlabel('Fitted values')
plt.ylabel('Residuals')
plt.show()
```

### 逻辑回归（二元结果）

```python
from statsmodels.discrete.discrete_model import Logit

# Add constant
X = sm.add_constant(X_data)

# Fit logit model
model = Logit(y_binary, X)
results = model.fit()

print(results.summary())

# Odds ratios
odds_ratios = np.exp(results.params)
print("Odds ratios:\\n", odds_ratios)

# Predicted probabilities
probs = results.predict(X)

# Binary predictions (0.5 threshold)
predictions = (probs > 0.5).astype(int)

# Model evaluation
from sklearn.metrics import classification_report, roc_auc_score

print(classification_report(y_binary, predictions))
print(f"AUC: {roc_auc_score(y_binary, probs):.4f}")

# Marginal effects
marginal = results.get_margeff()
print(marginal.summary())
```

### 时间序列 (ARIMA)

```python
from statsmodels.tsa.arima.model import ARIMA
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf

# Check stationarity
from statsmodels.tsa.stattools import adfuller

adf_result = adfuller(y_series)
print(f"ADF p-value: {adf_result[1]:.4f}")

if adf_result[1] > 0.05:
    # Series is non-stationary, difference it
    y_diff = y_series.diff().dropna()

# Plot ACF/PACF to identify p, q
fig, (ax1, ax2) = plt.subplots(2, 1, figsize=(12, 8))
plot_acf(y_diff, lags=40, ax=ax1)
plot_pacf(y_diff, lags=40, ax=ax2)
plt.show()

# Fit ARIMA(p,d,q)
model = ARIMA(y_series, order=(1, 1, 1))
results = model.fit()

print(results.summary())

# Forecast
forecast = results.forecast(steps=10)
forecast_obj = results.get_forecast(steps=10)
forecast_df = forecast_obj.summary_frame()

print(forecast_df)  # includes mean and confidence intervals

# Residual diagnostics
results.plot_diagnostics(figsize=(12, 8))
plt.show()
```

### 广义线性模型 (GLM)

```python
import statsmodels.api as sm

# Poisson regression for count data
X = sm.add_constant(X_data)
model = sm.GLM(y_counts, X, family=sm.families.Poisson())
results = model.fit()

print(results.summary())

# Rate ratios (for Poisson with log link)
rate_ratios = np.exp(results.params)
print("Rate ratios:\\n", rate_ratios)

# Check overdispersion
overdispersion = results.pearson_chi2 / results.df_resid
print(f"Overdispersion: {overdispersion:.2f}")

if overdispersion > 1.5:
    # Use Negative Binomial instead
    from statsmodels.discrete.count_model import NegativeBinomial
    nb_model = NegativeBinomial(y_counts, X)
    nb_results = nb_model.fit()
    print(nb_results.summary())
```

## 核心统计建模特征

### 1. 线性回归模型

全面的线性模型套件，用于具有各种误差结构的连续结果。

**可用模型：**
- **OLS**：独立同分布的标准线性回归错误
- **WLS**：异方差误差的加权最小二乘法
- **GLS**：任意协方差结构的广义最小二乘法
- **GLSAR**：time series 具有自回归误差的 GLS
- **分位数回归**：条件分位数（对异常值具有鲁棒性）
- **混合效应**：具有随机效应的分层/多级模型
- **递归/滚动**：时变参数估计

**主要特点：**
- 综合诊断测试
- 稳健的标准错误（HC、HAC、集群稳健）
- 影响力统计（库克距离、杠杆、DFFITS）
- 假设检验（F 检验、Wald 检验）
- 模型比较（AIC、BIC、似然比检验）
- 具有置信度和预测区间的预测

**何时使用：** 连续结果变量，想要 inference 系数，需要诊断

**参考：** 请参阅 `references/linear_models.md`，了解有关模型选择、诊断和最佳实践的详细指南。

### 2. 广义线性模型（GLM）

灵活的框架将线性模型扩展到非正态分布。

**分布系列：**
- **二项式**：二元结果或比例（逻辑回归）
- **泊松**：计数数据
- **负二项式**：计数过度分散
- **Gamma**：正连续、右偏数据
- **逆高斯**：具有特定方差结构的正连续
- **高斯**：相当于 OLS
- **Tweedie**：半连续数据的灵活系列

**链接特征：**
- Logit、Probit、Log、Identity、Inverse、Sqrt、CLogLog、Power
- 根据解释需求和模型拟合进行选择

**主要特点：**
- 通过 IRLS 进行最大似然估计
- 偏差和 Pearson 残差
- 拟合优度统计
- 伪 R 平方度量
- 稳健的标准误

**何时使用：** 非正态结果，需要灵活的方差和链接规范

**参考：** 有关系列选择、链接特征、解释和诊断，请参阅 `references/glm.md`。

### 3. 离散选择模型

分类和计数结果的模型。

**二元模型：**
- **Logit**：逻辑回归（优势比）
- **Probit**：Probit 回归（正态分布）

**多项式模型：**
- **MNLogit**：无序类别（3 个以上级别）
- **条件 Logit**：具有特定于替代变量的选择模型
- **有序模型**：有序结果（有序类别）

**计算模型：**
- **泊松**：标准计数模型
- **负二项式**：计数过度分散
- **零膨胀**：多余的零（ZIP、ZINB）
- **跨栏模型**：零重数据的两阶段模型

**主要特点：**
- 最大似然估计
- 均值的边际效应或平均边际效应
- 通过 AIC/BIC 进行模型比较
- 预测概率和分类
- 拟合优度检验

**何时使用：** 二元、分类或计数结果

**参考：** 请参阅 `references/discrete_choice.md` 以了解模型选择、解释和评估。

### 4.时间序列分析

全面的 time series 建模和预测特征。

**单变量模型：**
- **AutoReg (AR)**：自回归模型
- **ARIMA**：自回归积分移动平均线
- **SARIMAX**：具有外生变量的季节性 ARIMA
- **指数平滑**：简单、Holt、Holt-Winters
- **ETS**：创新状态空间模型

**多变量模型：**
- **VAR**：向量自回归
- **VARMAX**：具有 MA 和外生变量的 VAR
- **动态因子模型**：提取公因子
- **VECM**：矢量误差校正模型（协整）

**高级模型：**
- **状态空间**：卡尔曼滤波，自定义规格
- **政权切换**：马尔可夫切换模型
- **ARDL**：自回归分布滞后

**主要特点：**
- 用于模型识别的 ACF/PACF 分析
- 平稳性检验（ADF、KPSS）
- 使用预测区间进行预测
- 残差诊断（Ljung-Box，异方差）
- 格兰杰因果关系检验
- 脉冲响应函数 (IRF)
- 预测误差方差分解 (FEVD)

**何时使用：** 时间排序数据、预测、理解时间动态

**参考：**有关模型选择、诊断和预测方法，请参阅 `references/time_series.md`。

### 5. 统计测试和诊断

用于模型验证的广泛测试和诊断特征。

**剩余诊断：**
- 自相关检验（Ljung-Box、Durbin-Watson、Breusch-Godfrey）
- 异方差检验（Breusch-Pagan、White、ARCH）
- 正态性检验（Jarque-Bera、Omnibus、Anderson-Darling、Lilliefors）
- 规格测试（RESET、Harvey-Collier）

**影响和异常值：**
- 杠杆（帽子值）
- 库克距离
- DFFITS 和 DFBETA
- 学生化残差
- 影响图

**假设检验：**
- t-tests（一个样本、两个样本、配对）
- 比例测试
- Chi-square 测试
- 非参数检验（Mann-Whitney、Wilcoxon、Kruskal-Wallis）
- ANOVA（单向、双向、重复测量）

**多重比较：**
- 图基的HSD
- 邦费罗尼校正
- 错误发现率 (FDR)

**效果大小和功率：**
- Cohen d，eta 平方
- t-test 的功效分析，比例
- 样本量计算

**稳健的 inference：**
- 异方差一致的 SE (HC0-HC3)
- HAC 标准误 (Newey-West)
- 集群稳健的标准错误

**何时使用：** 验证假设、检测问题、确保稳健 inference

**参考：** 请参阅 `references/stats_diagnostics.md` 了解全面的测试和诊断程序。

## 公式 API（R 型）

Statsmodels 支持 R 式公式以实现直观的模型规范：

```python
import statsmodels.formula.api as smf

# OLS with formula
results = smf.ols('y ~ x1 + x2 + x1:x2', data=df).fit()

# Categorical variables (automatic dummy coding)
results = smf.ols('y ~ x1 + C(category)', data=df).fit()

# Interactions
results = smf.ols('y ~ x1 * x2', data=df).fit()  # x1 + x2 + x1:x2

# Polynomial terms
results = smf.ols('y ~ x + I(x**2)', data=df).fit()

# Logit
results = smf.logit('y ~ x1 + x2 + C(group)', data=df).fit()

# Poisson
results = smf.poisson('count ~ x1 + x2', data=df).fit()

# ARIMA (not available via formula, use regular API)
```

## 选型与比较

### 信息标准

```python
# Compare models using AIC/BIC
models = {
    'Model 1': model1_results,
    'Model 2': model2_results,
    'Model 3': model3_results
}

comparison = pd.DataFrame({
    'AIC': {name: res.aic for name, res in models.items()},
    'BIC': {name: res.bic for name, res in models.items()},
    'Log-Likelihood': {name: res.llf for name, res in models.items()}
})

print(comparison.sort_values('AIC'))
# Lower AIC/BIC indicates better model
```

### 似然比检验（嵌套模型）

```python
# For nested models (one is subset of the other)
from scipy import stats

lr_stat = 2 * (full_model.llf - reduced_model.llf)
df = full_model.df_model - reduced_model.df_model
p_value = 1 - stats.chi2.cdf(lr_stat, df)

print(f"LR statistic: {lr_stat:.4f}")
print(f"p-value: {p_value:.4f}")

if p_value < 0.05:
    print("Full model significantly better")
else:
    print("Reduced model preferred (parsimony)")
```

### Cross-Validation

```python
from sklearn.model_selection import KFold
from sklearn.metrics import mean_squared_error

kf = KFold(n_splits=5, shuffle=True, random_state=42)
cv_scores = []

for train_idx, val_idx in kf.split(X):
    X_train, X_val = X.iloc[train_idx], X.iloc[val_idx]
    y_train, y_val = y.iloc[train_idx], y.iloc[val_idx]

    # Fit model
    model = sm.OLS(y_train, X_train).fit()

    # Predict
    y_pred = model.predict(X_val)

    # Score
    rmse = np.sqrt(mean_squared_error(y_val, y_pred))
    cv_scores.append(rmse)

print(f"CV RMSE: {np.mean(cv_scores):.4f} ± {np.std(cv_scores):.4f}")
```

## 最佳实践

### 数据准备

1. **始终添加常量**：使用 `sm.add_constant()` 除非排除截距
2. **检查缺失值**：拟合前处理或插补
3. **如果需要的话可缩放**：提高收敛性、解释性（但树模型不需要）
4. **对分类进行编码**：使用公式 API 或手动虚拟编码

### 模型构建

1. **从简单开始**：从基本模型开始，根据需要添加复杂性
2. **检查假设**：检验残差、异方差、自相关
3. **使用适当的模型**：将模型与结果类型匹配（二元→Logit，计数→泊松）
4. **考虑替代方案**：如果违反假设，请使用稳健的方法或不同的模型

### 推理

1. **报告效果大小**：不仅仅是 p-values
2. **使用稳健的SE**：当存在异方差或聚类时
3. **多重比较**：测试许多假设时正确
4. **置信区间**：始终与点估计一起报告

### 模型评估

1. **检查残差**：绘制残差与拟合的图，Q-Q 图
2. **影响诊断**：识别并调查有影响的观察结果
3. **样本外验证**：在保留集上进行测试或交叉验证
4. **比较模型**：非嵌套使用AIC/BIC，嵌套使用LR测试

### 报告

1. **综合总结**：使用`.summary()`进行详细输出
2. **记录决策**：记录转换，排除观察结果
3. **仔细解释**：考虑链接函数（例如，日志链接的 exp(β)）
4. **可视化**：绘图预测、置信区间、诊断

## 通用工作流程

### 工作流程 1：线性回归分析

1. 探索数据（图表、描述性）
2. 拟合初始 OLS 模型
3. 检查残留诊断
4. 异方差、自相关检验
5. 检查多重共线性 (VIF)
6. 确定有影响力的观察结果
7. 如果需要，可使用坚固的 SE 进行改装
8. 解释系数和 inference
9. 通过坚持或通过简历进行验证

### 工作流程 2：二元分类

1. 拟合逻辑回归（Logit）
2. 检查收敛问题
3. 解释优势比
4. 计算边际效应
5. 评估分类性能（AUC、混淆矩阵）
6. 检查有影响的观察结果
7. 与替代模型比较 (Probit)
8. 验证测试集的预测

### 工作流程 3：计数数据分析

1. 拟合泊松回归
2. 检查是否过度分散
3. 如果过度分散，则拟合负二项式
4. 检查是否有多余的零（考虑 ZIP/ZINB）
5. 解释比率
6. 评估拟合优度
7. 通过 AIC 比较模型
8. 验证预测

### 工作流程 4：时间序列预测

1. 绘图系列，检查趋势/季节性
2. 平稳性检验（ADF、KPSS）
3. 非平稳时的差异
4. 从 ACF/PACF 中识别 p、q
5. 拟合 ARIMA 或 SARIMAX
6. 检查残留诊断 (Ljung-Box)
7. 生成具有置信区间的预测
8. 评估测试集上的预测准确性

## 参考文档

该技能包括用于详细指导的综合参考文件：

### references/linear_models.md
线性回归模型的详细内容包括：
- OLS、WLS、GLS、GLSAR、分位数回归
- 混合效应模型
- 递归和滚动回归
- 综合诊断（异方差、自相关、多重共线性）
- 影响统计和异常值检测
- 强大的标准错误（HC、HAC、集群）
- 假设检验和模型比较

### references/glm.md
广义线性模型完整指南：
- 所有分布族（二项分布、泊松分布、伽玛分布等）
- 链接特征以及何时使用每个特征
- 模型拟合和解释
- 伪 R 平方和拟合优度
- 诊断和残留分析
- 应用（逻辑、泊松、伽玛回归）

### references/discrete_choice.md
离散结果模型综合指南：
- 二元模型（Logit、Probit）
- 多项式模型（MNLogit、条件 Logit）
- 计数模型（泊松模型、负二项式模型、零膨胀模型、跨栏模型）
- 序数模型
- 边际效应和解释
- 模型诊断与比较

### references/time_series.md
深入time series分析指导：
- 单变量模型（AR、ARIMA、SARIMAX、指数平滑）
- 多元模型（VAR、VARMAX、动态因子）
- 状态空间模型
- 平稳性测试和诊断
- 预测方法与评估
- 格兰杰因果关系、IRF、FEVD

### references/stats_diagnostics.md
全面的统计测试和诊断：
- 残差诊断（自相关、异方差、正态性）
- 影响和异常值检测
- 假设检验（参数和非参数）
- ANOVA 和事后测试
- 多重比较校正
- 鲁棒协方差矩阵
- 功效分析和效应大小

**何时参考：**
- 需要详细参数说明
- 相似模型之间的选择
- 排除收敛或诊断问题
- 了解具体的测试统计数据
- 寻找高级特征的代码示例

**搜索模式：**
```bash
# Find information about specific models
grep -r "Quantile Regression" references/

# Find diagnostic tests
grep -r "Breusch-Pagan" references/stats_diagnostics.md

# Find time series guidance
grep -r "SARIMAX" references/time_series.md
```

## 要避免的常见陷阱

1. **忘记常数项**：除非不需要截距，否则始终使用 `sm.add_constant()`
2. **忽略假设**：检查残差、异方差、自相关
3. **结果类型的错误模型**：二元→Logit/Probit、计数→Poisson/NB，而不是 OLS
4. **不检查收敛**：寻找优化警告
5. **误解系数**：记住链接函数（log、logit 等）
6. **使用具有过度分散的泊松**：检查分散，如果需要，使用负二项式
7. **不使用稳健的SE**：当存在异方差或聚类时
8. **过度拟合**：相对于样本大小的参数太多
9. **数据泄漏**：拟合测试数据或使用未来信息
10. **不验证预测**：始终检查样本外的性能
11. **比较非嵌套模型**：使用AIC/BIC，而不是LR测试
12. **忽略有影响力的观察**：检查库克的距离和影响力
13. **多重测试**：测试多个假设时正确 p-values
14. **不区分 time series**：在非平稳数据上拟合 ARIMA
15. **令人困惑的预测与置信区间**：预测区间更宽

## 寻求帮助

有关详细文档和示例：
- 官方文档：https://www.statsmodels.org/stable/
- 用户指南：https://www.statsmodels.org/stable/user-guide.html
- 示例：https://www.statsmodels.org/stable/examples/index.html
- API参考：https://www.statsmodels.org/stable/api.html

