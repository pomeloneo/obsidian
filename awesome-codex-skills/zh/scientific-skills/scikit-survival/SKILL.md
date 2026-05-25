---
name: scikit-survival
description: 使用 scikit-survival 在 Python 中进行 survival analysis 和 time-to-event modeling 的综合 toolkit。用于 censored survival data、time-to-event analysis、拟合 Cox models、Random Survival Forests、Gradient Boosting models 或 Survival SVMs、用 concordance index 或 Brier score 评估 survival predictions、处理 competing risks，或使用 scikit-survival library 实现任何 survival analysis workflow。
license: GPL-3.0 license
metadata:
    skill-author: K-Dense Inc.
---

# scikit-survival: Survival Analysis in Python

## 概述

scikit-survival 是构建在 scikit-learn 之上的 Python survival analysis library。它为 time-to-event analysis 提供专用工具，可处理 censored data 这一独特挑战，即部分 observations 只被部分获知。

Survival analysis 旨在建立 covariates 与 event time 之间的联系，同时考虑 censored records（尤其是 studies 中 participants 在 observation periods 内未发生 events 的 right-censored data）。

## 何时使用此 Skill

在以下情况使用此 skill：
- 执行 survival analysis 或 time-to-event modeling
- 处理 censored data（right-censored、left-censored 或 interval-censored）
- 拟合 Cox proportional hazards models（standard 或 penalized）
- 构建 ensemble survival models（Random Survival Forests、Gradient Boosting）
- 训练 Survival Support Vector Machines
- 评估 survival model performance（concordance index、Brier score、time-dependent AUC）
- 估计 Kaplan-Meier 或 Nelson-Aalen curves
- 分析 competing risks
- 预处理 survival data 或处理 survival datasets 中的 missing values
- 使用 scikit-survival library 进行任何 analysis

## 核心能力

### 1. Model Types and Selection

scikit-survival 提供多个 model families，各自适合不同场景：

#### Cox Proportional Hazards Models
**Use for**：带可解释 coefficients 的标准 survival analysis
- `CoxPHSurvivalAnalysis`：Basic Cox model
- `CoxnetSurvivalAnalysis`：用于 high-dimensional data 的 elastic net penalized Cox
- `IPCRidge`：Accelerated failure time models 的 ridge regression

**See**：`references/cox-models.md`，了解 Cox models、regularization 和 interpretation 的详细指导

#### Ensemble Methods
**Use for**：具有 complex non-linear relationships 的高 predictive performance
- `RandomSurvivalForest`：Robust、non-parametric ensemble method
- `GradientBoostingSurvivalAnalysis`：Tree-based boosting，用于 maximum performance
- `ComponentwiseGradientBoostingSurvivalAnalysis`：带 feature selection 的 linear boosting
- `ExtraSurvivalTrees`：Extremely randomized trees，用于 additional regularization

**See**：`references/ensemble-models.md`，了解 ensemble methods、hyperparameter tuning 和各 model 使用时机

#### Survival Support Vector Machines
**Use for**：带 margin-based learning 的 medium-sized datasets
- `FastSurvivalSVM`：为速度优化的 linear SVM
- `FastKernelSurvivalSVM`：用于 non-linear relationships 的 kernel SVM
- `HingeLossSurvivalSVM`：带 hinge loss 的 SVM
- `ClinicalKernelTransform`：临床 + molecular data 的 specialized kernel

**See**：`references/svm-models.md`，了解 SVM guidance、kernel selection 和 hyperparameter tuning

#### Model Selection Decision Tree

```
Start
├─ High-dimensional data (p > n)?
│  ├─ Yes → CoxnetSurvivalAnalysis (elastic net)
│  └─ No → Continue
│
├─ Need interpretable coefficients?
│  ├─ Yes → CoxPHSurvivalAnalysis or ComponentwiseGradientBoostingSurvivalAnalysis
│  └─ No → Continue
│
├─ Complex non-linear relationships expected?
│  ├─ Yes
│  │  ├─ Large dataset (n > 1000) → GradientBoostingSurvivalAnalysis
│  │  ├─ Medium dataset → RandomSurvivalForest or FastKernelSurvivalSVM
│  │  └─ Small dataset → RandomSurvivalForest
│  └─ No → CoxPHSurvivalAnalysis or FastSurvivalSVM
│
└─ For maximum performance → Try multiple models and compare
```

### 2. Data Preparation and Preprocessing

建模前，正确准备 survival data：

#### Creating Survival Outcomes
```python
from sksurv.util import Surv

# From separate arrays
y = Surv.from_arrays(event=event_array, time=time_array)

# From DataFrame
y = Surv.from_dataframe('event', 'time', df)
```

#### Essential Preprocessing Steps
1. **Handle missing values**：features 的 imputation strategies
2. **Encode categorical variables**：One-hot encoding 或 label encoding
3. **Standardize features**：对 SVMs 和 regularized Cox models 至关重要
4. **Validate data quality**：检查 negative times、每个 feature 是否有 sufficient events
5. **Train-test split**：在 splits 中保持相近 censoring rates

**See**：`references/data-handling.md`，了解完整 preprocessing workflows、data validation 和 best practices

### 3. Model Evaluation

正确 evaluation 对 survival models 很关键。使用能处理 censoring 的合适 metrics：

#### Concordance Index（C-index）
Ranking/discrimination 的主要 metric：
- **Harrell's C-index**：低 censoring（<40%）时使用
- **Uno's C-index**：中高 censoring（>40%）时使用，更 robust

```python
from sksurv.metrics import concordance_index_censored, concordance_index_ipcw

# Harrell's C-index
c_harrell = concordance_index_censored(y_test['event'], y_test['time'], risk_scores)[0]

# Uno's C-index (recommended)
c_uno = concordance_index_ipcw(y_train, y_test, risk_scores)[0]
```

#### Time-Dependent AUC
在特定 time points 评估 discrimination：

```python
from sksurv.metrics import cumulative_dynamic_auc

times = [365, 730, 1095]  # 1, 2, 3 years
auc, mean_auc = cumulative_dynamic_auc(y_train, y_test, risk_scores, times)
```

#### Brier Score
同时评估 discrimination 和 calibration：

```python
from sksurv.metrics import integrated_brier_score

ibs = integrated_brier_score(y_train, y_test, survival_functions, times)
```

**See**：`references/evaluation-metrics.md`，了解 comprehensive evaluation guidance、metric selection 和与 cross-validation 结合使用 scorers

### 4. Competing Risks Analysis

处理有多个 mutually exclusive event types 的情况：

```python
from sksurv.nonparametric import cumulative_incidence_competing_risks

# Estimate cumulative incidence for each event type
time_points, cif_event1, cif_event2 = cumulative_incidence_competing_risks(y)
```

**Use competing risks when**：
- 存在多个 mutually exclusive event types（例如不同原因死亡）
- 一个 event 的发生会阻止其他 events
- 需要特定 event types 的 probability estimates

**See**：`references/competing-risks.md`，了解 competing risks methods、cause-specific hazard models 和 interpretation

### 5. Non-parametric Estimation

在无 parametric assumptions 的情况下估计 survival functions：

#### Kaplan-Meier Estimator
```python
from sksurv.nonparametric import kaplan_meier_estimator

time, survival_prob = kaplan_meier_estimator(y['event'], y['time'])
```

#### Nelson-Aalen Estimator
```python
from sksurv.nonparametric import nelson_aalen_estimator

time, cumulative_hazard = nelson_aalen_estimator(y['event'], y['time'])
```

## Typical Workflows

### Workflow 1: Standard Survival Analysis

```python
from sksurv.datasets import load_breast_cancer
from sksurv.linear_model import CoxPHSurvivalAnalysis
from sksurv.metrics import concordance_index_ipcw
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# 1. Load and prepare data
X, y = load_breast_cancer()
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 2. Preprocess
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# 3. Fit model
estimator = CoxPHSurvivalAnalysis()
estimator.fit(X_train_scaled, y_train)

# 4. Predict
risk_scores = estimator.predict(X_test_scaled)

# 5. Evaluate
c_index = concordance_index_ipcw(y_train, y_test, risk_scores)[0]
print(f"C-index: {c_index:.3f}")
```

### Workflow 2: High-Dimensional Data with Feature Selection

```python
from sksurv.linear_model import CoxnetSurvivalAnalysis
from sklearn.model_selection import GridSearchCV
from sksurv.metrics import as_concordance_index_ipcw_scorer

# 1. Use penalized Cox for feature selection
estimator = CoxnetSurvivalAnalysis(l1_ratio=0.9)  # Lasso-like

# 2. Tune regularization with cross-validation
param_grid = {'alpha_min_ratio': [0.01, 0.001]}
cv = GridSearchCV(estimator, param_grid,
                  scoring=as_concordance_index_ipcw_scorer(), cv=5)
cv.fit(X, y)

# 3. Identify selected features
best_model = cv.best_estimator_
selected_features = np.where(best_model.coef_ != 0)[0]
```

### Workflow 3: Ensemble Method for Maximum Performance

```python
from sksurv.ensemble import GradientBoostingSurvivalAnalysis
from sklearn.model_selection import GridSearchCV

# 1. Define parameter grid
param_grid = {
    'learning_rate': [0.01, 0.05, 0.1],
    'n_estimators': [100, 200, 300],
    'max_depth': [3, 5, 7]
}

# 2. Grid search
gbs = GradientBoostingSurvivalAnalysis()
cv = GridSearchCV(gbs, param_grid, cv=5,
                  scoring=as_concordance_index_ipcw_scorer(), n_jobs=-1)
cv.fit(X_train, y_train)

# 3. Evaluate best model
best_model = cv.best_estimator_
risk_scores = best_model.predict(X_test)
c_index = concordance_index_ipcw(y_train, y_test, risk_scores)[0]
```

### Workflow 4: Comprehensive Model Comparison

```python
from sksurv.linear_model import CoxPHSurvivalAnalysis
from sksurv.ensemble import RandomSurvivalForest, GradientBoostingSurvivalAnalysis
from sksurv.svm import FastSurvivalSVM
from sksurv.metrics import concordance_index_ipcw, integrated_brier_score

# Define models
models = {
    'Cox': CoxPHSurvivalAnalysis(),
    'RSF': RandomSurvivalForest(n_estimators=100, random_state=42),
    'GBS': GradientBoostingSurvivalAnalysis(random_state=42),
    'SVM': FastSurvivalSVM(random_state=42)
}

# Evaluate each model
results = {}
for name, model in models.items():
    model.fit(X_train_scaled, y_train)
    risk_scores = model.predict(X_test_scaled)
    c_index = concordance_index_ipcw(y_train, y_test, risk_scores)[0]
    results[name] = c_index
    print(f"{name}: C-index = {c_index:.3f}")

# Select best model
best_model_name = max(results, key=results.get)
print(f"\nBest model: {best_model_name}")
```

## Integration with scikit-learn

scikit-survival 完全集成 scikit-learn ecosystem：

```python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import cross_val_score, GridSearchCV

# Use pipelines
pipeline = Pipeline([
    ('scaler', StandardScaler()),
    ('model', CoxPHSurvivalAnalysis())
])

# Use cross-validation
scores = cross_val_score(pipeline, X, y, cv=5,
                         scoring=as_concordance_index_ipcw_scorer())

# Use grid search
param_grid = {'model__alpha': [0.1, 1.0, 10.0]}
cv = GridSearchCV(pipeline, param_grid, cv=5)
cv.fit(X, y)
```

## Best Practices

1. **始终 standardize features**，用于 SVMs 和 regularized Cox models
2. Censoring > 40% 时，使用 **Uno's C-index** 而不是 Harrell's
3. **报告多个 evaluation metrics**（C-index、integrated Brier score、time-dependent AUC）
4. 对 Cox models **检查 proportional hazards assumption**
5. 使用合适 scorers 做 **cross-validation** 和 hyperparameter tuning
6. Modeling 前 **validate data quality**（检查 negative times、每个 feature 的 sufficient events）
7. **比较多种 model types** 以找到最佳 performance
8. 对 Random Survival Forests 使用 **permutation importance**（非 built-in importance）
9. 存在多个 event types 时 **考虑 competing risks**
10. 在 analysis 中 **记录 censoring mechanism 和 rates**

## 应避免的常见陷阱

1. **高 censoring 时使用 Harrell's C-index** → 使用 Uno's C-index
2. **SVMs 未 standardize features** → 始终 standardize
3. **忘记向 concordance_index_ipcw 传入 y_train** → IPCW calculation 必需
4. **将 competing events 当作 censored** → 使用 competing risks methods
5. **未检查每个 feature 是否有 sufficient events** → 经验法则：每个 feature 10+ events
6. **使用 RSF 的 built-in feature importance** → 使用 permutation importance
7. **忽视 proportional hazards assumption** → 验证或使用 alternative models
8. **Cross-validation 中未使用合适 scorers** → 使用 as_concordance_index_ipcw_scorer()

## Reference Files

此 skill 包含特定主题的详细 reference files：

- **`references/cox-models.md`**：Cox proportional hazards models、penalized Cox（CoxNet）、IPCRidge、regularization strategies 和 interpretation 的完整指南
- **`references/ensemble-models.md`**：Random Survival Forests、Gradient Boosting、hyperparameter tuning、feature importance 和 model selection
- **`references/evaluation-metrics.md`**：Concordance index（Harrell's vs Uno's）、time-dependent AUC、Brier score、comprehensive evaluation pipelines
- **`references/data-handling.md`**：Data loading、preprocessing workflows、handling missing data、feature encoding、validation checks
- **`references/svm-models.md`**：Survival Support Vector Machines、kernel selection、clinical kernel transform、hyperparameter tuning
- **`references/competing-risks.md`**：Competing risks analysis、cumulative incidence functions、cause-specific hazard models

需要特定 tasks 的详细信息时加载这些 reference files。

## Additional Resources

- **Official Documentation**: https://scikit-survival.readthedocs.io/
- **GitHub Repository**: https://github.com/sebp/scikit-survival
- **Built-in Datasets**: 使用 `sksurv.datasets` 获取 practice datasets（GBSG2、WHAS500、veterans lung cancer 等）
- **API Reference**: Classes 和 functions 完整列表见 https://scikit-survival.readthedocs.io/en/stable/api/index.html

## Quick Reference: Key Imports

```python
# Models
from sksurv.linear_model import CoxPHSurvivalAnalysis, CoxnetSurvivalAnalysis, IPCRidge
from sksurv.ensemble import RandomSurvivalForest, GradientBoostingSurvivalAnalysis
from sksurv.svm import FastSurvivalSVM, FastKernelSurvivalSVM
from sksurv.tree import SurvivalTree

# Evaluation metrics
from sksurv.metrics import (
    concordance_index_censored,
    concordance_index_ipcw,
    cumulative_dynamic_auc,
    brier_score,
    integrated_brier_score,
    as_concordance_index_ipcw_scorer,
    as_integrated_brier_score_scorer
)

# Non-parametric estimation
from sksurv.nonparametric import (
    kaplan_meier_estimator,
    nelson_aalen_estimator,
    cumulative_incidence_competing_risks
)

# Data handling
from sksurv.util import Surv
from sksurv.preprocessing import OneHotEncoder, encode_categorical
from sksurv.datasets import load_gbsg2, load_breast_cancer, load_veterans_lung_cancer

# Kernels
from sksurv.kernels import ClinicalKernelTransform
```
