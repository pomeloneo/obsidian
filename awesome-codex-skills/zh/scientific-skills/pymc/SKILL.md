---
name: pymc
description: 使用 PyMC 进行 Bayesian modeling。构建 hierarchical models、MCMC（NUTS）、variational inference、LOO/WAIC comparison、posterior checks，用于 probabilistic programming and inference。
license: Apache License, Version 2.0
metadata:
    skill-author: K-Dense Inc.
---

# PyMC Bayesian Modeling

## 概览

PyMC 是用于 Bayesian modeling 和 probabilistic programming 的 Python library。使用 PyMC 的现代 API（version 5.x+）构建、拟合、验证和比较 Bayesian models，包括 hierarchical models、MCMC sampling（NUTS）、variational inference 和 model comparison（LOO、WAIC）。

## 何时使用此 Skill

此 skill 应用于：
- 构建 Bayesian models（linear/logistic regression、hierarchical models、time series 等）
- 执行 MCMC sampling 或 variational inference
- 进行 prior/posterior predictive checks
- 诊断 sampling issues（divergences、convergence、ESS）
- 使用 information criteria（LOO、WAIC）比较 multiple models
- 通过 Bayesian methods 实现 uncertainty quantification
- 处理 hierarchical/multilevel data structures
- 以 principled way 处理 missing data 或 measurement error

## 标准 Bayesian Workflow

按照此 workflow 构建和验证 Bayesian models：

### 1. Data Preparation

```python
import pymc as pm
import arviz as az
import numpy as np

# Load and prepare data
X = ...  # Predictors
y = ...  # Outcomes

# Standardize predictors for better sampling
X_mean = X.mean(axis=0)
X_std = X.std(axis=0)
X_scaled = (X - X_mean) / X_std
```

**Key practices：**
- 标准化 continuous predictors（提高 sampling efficiency）
- 尽可能 center outcomes
- 显式处理 missing data（将其视为 parameters）
- 使用带 `coords` 的 named dimensions 提高清晰度

### 2. Model Building

```python
coords = {
    'predictors': ['var1', 'var2', 'var3'],
    'obs_id': np.arange(len(y))
}

with pm.Model(coords=coords) as model:
    # Priors
    alpha = pm.Normal('alpha', mu=0, sigma=1)
    beta = pm.Normal('beta', mu=0, sigma=1, dims='predictors')
    sigma = pm.HalfNormal('sigma', sigma=1)

    # Linear predictor
    mu = alpha + pm.math.dot(X_scaled, beta)

    # Likelihood
    y_obs = pm.Normal('y_obs', mu=mu, sigma=sigma, observed=y, dims='obs_id')
```

**Key practices：**
- 使用 weakly informative priors（不是 flat priors）
- 对 scale parameters 使用 `HalfNormal` 或 `Exponential`
- 尽可能使用 named dimensions（`dims`），而不是 `shape`
- 对将用于 predictions 并会更新的 values 使用 `pm.Data()`

### 3. Prior Predictive Check

**拟合前始终验证 priors：**

```python
with model:
    prior_pred = pm.sample_prior_predictive(samples=1000, random_seed=42)

# Visualize
az.plot_ppc(prior_pred, group='prior')
```

**检查：**
- prior predictions 是否覆盖合理 values？
- 给定 domain knowledge，extreme values 是否合理？
- 如果 priors 生成不合理 data，调整并重新检查

### 4. Fit Model

```python
with model:
    # Optional: Quick exploration with ADVI
    # approx = pm.fit(n=20000)

    # Full MCMC inference
    idata = pm.sample(
        draws=2000,
        tune=1000,
        chains=4,
        target_accept=0.9,
        random_seed=42,
        idata_kwargs={'log_likelihood': True}  # For model comparison
    )
```

**Key parameters：**
- `draws=2000`：每条 chain 的 samples 数
- `tune=1000`：Warmup samples（discarded）
- `chains=4`：运行 4 条 chains 以检查 convergence
- `target_accept=0.9`：difficult posteriors 使用更高值（0.95-0.99）
- 为 model comparison 包含 `log_likelihood=True`

### 5. Check Diagnostics

**使用 diagnostic script：**

```python
from scripts.model_diagnostics import check_diagnostics

results = check_diagnostics(idata, var_names=['alpha', 'beta', 'sigma'])
```

**检查：**
- **R-hat < 1.01**：Chains 已 converged
- **ESS > 400**：effective samples 充足
- **No divergences**：NUTS 成功采样
- **Trace plots**：Chains 应充分混合（fuzzy caterpillar）

**如果出现问题：**
- Divergences → 增加 `target_accept=0.95`，使用 non-centered parameterization
- Low ESS → 采样更多 draws，reparameterize 以减少 correlation
- High R-hat → 运行更久，检查 multimodality

### 6. Posterior Predictive Check

**验证 model fit：**

```python
with model:
    pm.sample_posterior_predictive(idata, extend_inferencedata=True, random_seed=42)

# Visualize
az.plot_ppc(idata)
```

**检查：**
- posterior predictions 是否捕捉 observed data patterns？
- 是否存在明显 systematic deviations（model misspecification）？
- 如果 fit 较差，考虑 alternative models

### 7. Analyze Results

```python
# Summary statistics
print(az.summary(idata, var_names=['alpha', 'beta', 'sigma']))

# Posterior distributions
az.plot_posterior(idata, var_names=['alpha', 'beta', 'sigma'])

# Coefficient estimates
az.plot_forest(idata, var_names=['beta'], combined=True)
```

### 8. Make Predictions

```python
X_new = ...  # New predictor values
X_new_scaled = (X_new - X_mean) / X_std

with model:
    pm.set_data({'X_scaled': X_new_scaled})
    post_pred = pm.sample_posterior_predictive(
        idata.posterior,
        var_names=['y_obs'],
        random_seed=42
    )

# Extract prediction intervals
y_pred_mean = post_pred.posterior_predictive['y_obs'].mean(dim=['chain', 'draw'])
y_pred_hdi = az.hdi(post_pred.posterior_predictive, var_names=['y_obs'])
```

## 常见 Model Patterns

### Linear Regression

用于具有 linear relationships 的 continuous outcomes：

```python
with pm.Model() as linear_model:
    alpha = pm.Normal('alpha', mu=0, sigma=10)
    beta = pm.Normal('beta', mu=0, sigma=10, shape=n_predictors)
    sigma = pm.HalfNormal('sigma', sigma=1)

    mu = alpha + pm.math.dot(X, beta)
    y = pm.Normal('y', mu=mu, sigma=sigma, observed=y_obs)
```

**使用 template：** `assets/linear_regression_template.py`

### Logistic Regression

用于 binary outcomes：

```python
with pm.Model() as logistic_model:
    alpha = pm.Normal('alpha', mu=0, sigma=10)
    beta = pm.Normal('beta', mu=0, sigma=10, shape=n_predictors)

    logit_p = alpha + pm.math.dot(X, beta)
    y = pm.Bernoulli('y', logit_p=logit_p, observed=y_obs)
```

### Hierarchical Models

用于 grouped data（使用 non-centered parameterization）：

```python
with pm.Model(coords={'groups': group_names}) as hierarchical_model:
    # Hyperpriors
    mu_alpha = pm.Normal('mu_alpha', mu=0, sigma=10)
    sigma_alpha = pm.HalfNormal('sigma_alpha', sigma=1)

    # Group-level (non-centered)
    alpha_offset = pm.Normal('alpha_offset', mu=0, sigma=1, dims='groups')
    alpha = pm.Deterministic('alpha', mu_alpha + sigma_alpha * alpha_offset, dims='groups')

    # Observation-level
    mu = alpha[group_idx]
    sigma = pm.HalfNormal('sigma', sigma=1)
    y = pm.Normal('y', mu=mu, sigma=sigma, observed=y_obs)
```

**使用 template：** `assets/hierarchical_model_template.py`

**关键：** 对 hierarchical models 始终使用 non-centered parameterization，以避免 divergences。

### Poisson Regression

用于 count data：

```python
with pm.Model() as poisson_model:
    alpha = pm.Normal('alpha', mu=0, sigma=10)
    beta = pm.Normal('beta', mu=0, sigma=10, shape=n_predictors)

    log_lambda = alpha + pm.math.dot(X, beta)
    y = pm.Poisson('y', mu=pm.math.exp(log_lambda), observed=y_obs)
```

对于 overdispersed counts，改用 `NegativeBinomial`。

### Time Series

用于 autoregressive processes：

```python
with pm.Model() as ar_model:
    sigma = pm.HalfNormal('sigma', sigma=1)
    rho = pm.Normal('rho', mu=0, sigma=0.5, shape=ar_order)
    init_dist = pm.Normal.dist(mu=0, sigma=sigma)

    y = pm.AR('y', rho=rho, sigma=sigma, init_dist=init_dist, observed=y_obs)
```

## Model Comparison

### Comparing Models

使用 LOO 或 WAIC 进行 model comparison：

```python
from scripts.model_comparison import compare_models, check_loo_reliability

# Fit models with log_likelihood
models = {
    'Model1': idata1,
    'Model2': idata2,
    'Model3': idata3
}

# Compare using LOO
comparison = compare_models(models, ic='loo')

# Check reliability
check_loo_reliability(models)
```

**Interpretation：**
- **Δloo < 2**：Models 相似，选择 simpler model
- **2 < Δloo < 4**：better model 的 evidence 较弱
- **4 < Δloo < 10**：moderate evidence
- **Δloo > 10**：better model 的 strong evidence

**检查 Pareto-k values：**
- k < 0.7：LOO reliable
- k > 0.7：考虑 WAIC 或 k-fold CV

### Model Averaging

当 models 相似时，average predictions：

```python
from scripts.model_comparison import model_averaging

averaged_pred, weights = model_averaging(models, var_name='y_obs')
```

## Distribution Selection Guide

### For Priors

**Scale parameters**（σ、τ）：
- `pm.HalfNormal('sigma', sigma=1)` - 默认选择
- `pm.Exponential('sigma', lam=1)` - 替代选择
- `pm.Gamma('sigma', alpha=2, beta=1)` - 更 informative

**Unbounded parameters：**
- `pm.Normal('theta', mu=0, sigma=1)` - 用于 standardized data
- `pm.StudentT('theta', nu=3, mu=0, sigma=1)` - 对 outliers robust

**Positive parameters：**
- `pm.LogNormal('theta', mu=0, sigma=1)`
- `pm.Gamma('theta', alpha=2, beta=1)`

**Probabilities：**
- `pm.Beta('p', alpha=2, beta=2)` - Weakly informative
- `pm.Uniform('p', lower=0, upper=1)` - Non-informative（谨慎使用）

**Correlation matrices：**
- `pm.LKJCorr('corr', n=n_vars, eta=2)` - eta=1 uniform，eta>1 prefers identity

### For Likelihoods

**Continuous outcomes：**
- `pm.Normal('y', mu=mu, sigma=sigma)` - continuous data 的默认选择
- `pm.StudentT('y', nu=nu, mu=mu, sigma=sigma)` - 对 outliers robust

**Count data：**
- `pm.Poisson('y', mu=lambda)` - Equidispersed counts
- `pm.NegativeBinomial('y', mu=mu, alpha=alpha)` - Overdispersed counts
- `pm.ZeroInflatedPoisson('y', psi=psi, mu=mu)` - Excess zeros

**Binary outcomes：**
- `pm.Bernoulli('y', p=p)` or `pm.Bernoulli('y', logit_p=logit_p)`

**Categorical outcomes：**
- `pm.Categorical('y', p=probs)`

**参见：** `references/distributions.md` 获取 comprehensive distribution reference

## Sampling and Inference

### MCMC with NUTS

大多数 models 的默认且推荐选择：

```python
idata = pm.sample(
    draws=2000,
    tune=1000,
    chains=4,
    target_accept=0.9,
    random_seed=42
)
```

**按需调整：**
- Divergences → `target_accept=0.95` 或更高
- Slow sampling → 使用 ADVI 初始化
- Discrete parameters → 对 discrete vars 使用 `pm.Metropolis()`

### Variational Inference

用于 exploration 或 initialization 的快速 approximation：

```python
with model:
    approx = pm.fit(n=20000, method='advi')

    # Use for initialization
    start = approx.sample(return_inferencedata=False)[0]
    idata = pm.sample(start=start)
```

**Trade-offs：**
- 比 MCMC 快得多
- 近似（可能低估 uncertainty）
- 适合 large models 或 quick exploration

**参见：** `references/sampling_inference.md` 获取 detailed sampling guide

## Diagnostic Scripts

### Comprehensive Diagnostics

```python
from scripts.model_diagnostics import create_diagnostic_report

create_diagnostic_report(
    idata,
    var_names=['alpha', 'beta', 'sigma'],
    output_dir='diagnostics/'
)
```

创建：
- Trace plots
- Rank plots（mixing check）
- Autocorrelation plots
- Energy plots
- ESS evolution
- Summary statistics CSV

### Quick Diagnostic Check

```python
from scripts.model_diagnostics import check_diagnostics

results = check_diagnostics(idata)
```

检查 R-hat、ESS、divergences 和 tree depth。

## 常见问题与解决方案

### Divergences

**Symptom：** `idata.sample_stats.diverging.sum() > 0`

**Solutions：**
1. 增加 `target_accept=0.95` 或 `0.99`
2. 使用 non-centered parameterization（hierarchical models）
3. 添加更强 priors 以约束 parameters
4. 检查 model misspecification

### Low Effective Sample Size

**Symptom：** `ESS < 400`

**Solutions：**
1. 采样更多 draws：`draws=5000`
2. Reparameterize 以减少 posterior correlation
3. 对带 correlated predictors 的 regression 使用 QR decomposition

### High R-hat

**Symptom：** `R-hat > 1.01`

**Solutions：**
1. 运行更长 chains：`tune=2000, draws=5000`
2. 检查 multimodality
3. 使用 ADVI 改善 initialization

### Slow Sampling

**Solutions：**
1. 使用 ADVI initialization
2. 降低 model complexity
3. 增加 parallelization：`cores=8, chains=8`
4. 如合适，使用 variational inference

## Best Practices

### Model Building

1. **始终 standardize predictors** 以改善 sampling
2. **使用 weakly informative priors**（不是 flat）
3. **使用 named dimensions**（`dims`）提升清晰度
4. 对 hierarchical models 使用 **Non-centered parameterization**
5. 拟合前 **Check prior predictive**

### Sampling

1. 为 convergence **运行 multiple chains**（至少 4 条）
2. 以 **`target_accept=0.9`** 为 baseline（必要时更高）
3. 为 model comparison **包含 `log_likelihood=True`**
4. 为 reproducibility **设置 random seed**

### Validation

1. interpretation 前 **Check diagnostics**（R-hat、ESS、divergences）
2. 使用 **Posterior predictive check** 进行 model validation
3. 适当时 **Compare multiple models**
4. **Report uncertainty**（HDI intervals，而不只是 point estimates）

### Workflow

1. 从简单开始，逐步增加 complexity
2. Prior predictive check → Fit → Diagnostics → Posterior predictive check
3. 基于 checks 迭代 model specification
4. 记录 assumptions 和 prior choices

## 资源

此 skill 包含：

### References (`references/`)

- **`distributions.md`**：按 category（continuous、discrete、multivariate、mixture、time series）组织的 PyMC distributions 综合目录。选择 priors 或 likelihoods 时使用。

- **`sampling_inference.md`**：sampling algorithms（NUTS、Metropolis、SMC）、variational inference（ADVI、SVGD）以及 handling sampling issues 的详细指南。遇到 convergence problems 或选择 inference methods 时使用。

- **`workflows.md`**：common model types、data preparation、prior selection 和 model validation 的完整 workflow examples 和 code patterns。可作为 standard Bayesian analyses 的 cookbook。

### Scripts (`scripts/`)

- **`model_diagnostics.py`**：Automated diagnostic checking 和 report generation。Functions：`check_diagnostics()` 用于 quick checks，`create_diagnostic_report()` 用于带 plots 的 comprehensive analysis。

- **`model_comparison.py`**：使用 LOO/WAIC 的 model comparison utilities。Functions：`compare_models()`、`check_loo_reliability()`、`model_averaging()`。

### Templates (`assets/`)

- **`linear_regression_template.py`**：Bayesian linear regression 的完整 template，包含 full workflow（data prep、prior checks、fitting、diagnostics、predictions）。

- **`hierarchical_model_template.py`**：hierarchical/multilevel models 的完整 template，包含 non-centered parameterization 和 group-level analysis。

## 快速参考

### Model Building
```python
with pm.Model(coords={'var': names}) as model:
    # Priors
    param = pm.Normal('param', mu=0, sigma=1, dims='var')
    # Likelihood
    y = pm.Normal('y', mu=..., sigma=..., observed=data)
```

### Sampling
```python
idata = pm.sample(draws=2000, tune=1000, chains=4, target_accept=0.9)
```

### Diagnostics
```python
from scripts.model_diagnostics import check_diagnostics
check_diagnostics(idata)
```

### Model Comparison
```python
from scripts.model_comparison import compare_models
compare_models({'m1': idata1, 'm2': idata2}, ic='loo')
```

### Predictions
```python
with model:
    pm.set_data({'X': X_new})
    pred = pm.sample_posterior_predictive(idata.posterior)
```

## Additional Notes

- PyMC 与 ArviZ 集成，用于 visualization 和 diagnostics
- 使用 `pm.model_to_graphviz(model)` 可视化 model structure
- 使用 `idata.to_netcdf('results.nc')` 保存 results
- 使用 `az.from_netcdf('results.nc')` 加载
- 对 very large models，考虑 minibatch ADVI 或 data subsampling
