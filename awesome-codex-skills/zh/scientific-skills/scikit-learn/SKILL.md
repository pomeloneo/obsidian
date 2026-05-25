---
name: scikit-learn
description: 使用 scikit-learn 在 Python 中进行 machine learning。用于 supervised learning（classification、regression）、unsupervised learning（clustering、dimensionality reduction）、model evaluation、hyperparameter tuning、preprocessing 或构建 ML pipelines。提供 algorithms、preprocessing techniques、pipelines 和 best practices 的完整 reference documentation。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# Scikit-learn

## 概述

此 skill 为使用 scikit-learn 的 machine learning tasks 提供完整指导。scikit-learn 是 classical machine learning 的行业标准 Python library。将此 skill 用于 classification、regression、clustering、dimensionality reduction、preprocessing、model evaluation 和构建 production-ready ML pipelines。

## 安装

```bash
# Install scikit-learn using uv
uv pip install scikit-learn

# Optional: Install visualization dependencies
uv pip install matplotlib seaborn

# Commonly used with
uv pip install pandas numpy
```

## 何时使用此 Skill

在以下情况使用 scikit-learn skill：

- 构建 classification 或 regression models
- 执行 clustering 或 dimensionality reduction
- 为 machine learning 预处理和转换 data
- 使用 cross-validation 评估 model performance
- 使用 grid 或 random search 调整 hyperparameters
- 为 production workflows 创建 ML pipelines
- 比较不同 algorithms 以完成某项 task
- 处理 structured（tabular）和 text data
- 需要可解释的 classical machine learning approaches

## Quick Start

### Classification Example

```python
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, stratify=y, random_state=42
)

# Preprocess
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# Train model
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train_scaled, y_train)

# Evaluate
y_pred = model.predict(X_test_scaled)
print(classification_report(y_test, y_pred))
```

### Complete Pipeline with Mixed Data

```python
from sklearn.pipeline import Pipeline
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.impute import SimpleImputer
from sklearn.ensemble import GradientBoostingClassifier

# Define feature types
numeric_features = ['age', 'income']
categorical_features = ['gender', 'occupation']

# Create preprocessing pipelines
numeric_transformer = Pipeline([
    ('imputer', SimpleImputer(strategy='median')),
    ('scaler', StandardScaler())
])

categorical_transformer = Pipeline([
    ('imputer', SimpleImputer(strategy='most_frequent')),
    ('onehot', OneHotEncoder(handle_unknown='ignore'))
])

# Combine transformers
preprocessor = ColumnTransformer([
    ('num', numeric_transformer, numeric_features),
    ('cat', categorical_transformer, categorical_features)
])

# Full pipeline
model = Pipeline([
    ('preprocessor', preprocessor),
    ('classifier', GradientBoostingClassifier(random_state=42))
])

# Fit and predict
model.fit(X_train, y_train)
y_pred = model.predict(X_test)
```

## 核心能力

### 1. Supervised Learning

面向 classification 和 regression tasks 的完整 algorithms。

**Key algorithms：**
- **Linear models**：Logistic Regression、Linear Regression、Ridge、Lasso、ElasticNet
- **Tree-based**：Decision Trees、Random Forest、Gradient Boosting
- **Support Vector Machines**：带多种 kernels 的 SVC、SVR
- **Ensemble methods**：AdaBoost、Voting、Stacking
- **Neural Networks**：MLPClassifier、MLPRegressor
- **Others**：Naive Bayes、K-Nearest Neighbors

**When to use：**
- Classification：预测 discrete categories（spam detection、image classification、fraud detection）
- Regression：预测 continuous values（price prediction、demand forecasting）

**See：** `references/supervised_learning.md`，了解详细 algorithm documentation、parameters 和 usage examples。

### 2. Unsupervised Learning

通过 clustering 和 dimensionality reduction 在 unlabeled data 中发现 patterns。

**Clustering algorithms：**
- **Partition-based**：K-Means、MiniBatchKMeans
- **Density-based**：DBSCAN、HDBSCAN、OPTICS
- **Hierarchical**：AgglomerativeClustering
- **Probabilistic**：Gaussian Mixture Models
- **Others**：MeanShift、SpectralClustering、BIRCH

**Dimensionality reduction：**
- **Linear**：PCA、TruncatedSVD、NMF
- **Manifold learning**：t-SNE、UMAP、Isomap、LLE
- **Feature extraction**：FastICA、LatentDirichletAllocation

**When to use：**
- Customer segmentation、anomaly detection、data visualization
- 降低 feature dimensions、exploratory data analysis
- Topic modeling、image compression

**See：** `references/unsupervised_learning.md`，了解详细文档。

### 3. Model Evaluation and Selection

用于 robust model evaluation、cross-validation 和 hyperparameter tuning 的工具。

**Cross-validation strategies：**
- KFold、StratifiedKFold（classification）
- TimeSeriesSplit（temporal data）
- GroupKFold（grouped samples）

**Hyperparameter tuning：**
- GridSearchCV（exhaustive search）
- RandomizedSearchCV（random sampling）
- HalvingGridSearchCV（successive halving）

**Metrics：**
- **Classification**：accuracy、precision、recall、F1-score、ROC AUC、confusion matrix
- **Regression**：MSE、RMSE、MAE、R²、MAPE
- **Clustering**：silhouette score、Calinski-Harabasz、Davies-Bouldin

**When to use：**
- 客观比较 model performance
- 查找 optimal hyperparameters
- 通过 cross-validation 防止 overfitting
- 使用 learning curves 理解 model behavior

**See：** `references/model_evaluation.md`，了解 comprehensive metrics 和 tuning strategies。

### 4. Data Preprocessing

将 raw data 转换为适合 machine learning 的格式。

**Scaling and normalization：**
- StandardScaler（zero mean、unit variance）
- MinMaxScaler（bounded range）
- RobustScaler（robust to outliers）
- Normalizer（sample-wise normalization）

**Encoding categorical variables：**
- OneHotEncoder（nominal categories）
- OrdinalEncoder（ordered categories）
- LabelEncoder（target encoding）

**Handling missing values：**
- SimpleImputer（mean、median、most frequent）
- KNNImputer（k-nearest neighbors）
- IterativeImputer（multivariate imputation）

**Feature engineering：**
- PolynomialFeatures（interaction terms）
- KBinsDiscretizer（binning）
- Feature selection（RFE、SelectKBest、SelectFromModel）

**When to use：**
- 训练任何需要 scaled features 的 algorithm 前（SVM、KNN、Neural Networks）
- 将 categorical variables 转为 numeric format
- 系统处理 missing data
- 为 linear models 创建 non-linear features

**See：** `references/preprocessing.md`，了解详细 preprocessing techniques。

### 5. Pipelines and Composition

构建 reproducible、production-ready ML workflows。

**Key components：**
- **Pipeline**：顺序串联 transformers 和 estimators
- **ColumnTransformer**：对不同 columns 应用不同 preprocessing
- **FeatureUnion**：并行组合多个 transformers
- **TransformedTargetRegressor**：转换 target variable

**Benefits：**
- 防止 cross-validation 中的 data leakage
- 简化 code 并提升 maintainability
- 支持 joint hyperparameter tuning
- 确保 training 和 prediction 一致

**When to use：**
- Production workflows 始终使用 Pipelines
- 混合 numerical 和 categorical features 时使用 ColumnTransformer
- 对 preprocessing steps 做 cross-validation 时
- Hyperparameter tuning 包含 preprocessing parameters 时

**See：** `references/pipelines_and_composition.md`，了解 comprehensive pipeline patterns。

## Example Scripts

### Classification Pipeline

运行完整 classification workflow，包括 preprocessing、model comparison、hyperparameter tuning 和 evaluation：

```bash
python scripts/classification_pipeline.py
```

此 script 展示：
- 处理 mixed data types（numeric 和 categorical）
- 使用 cross-validation 进行 model comparison
- 使用 GridSearchCV 做 hyperparameter tuning
- 使用多个 metrics 做 comprehensive evaluation
- Feature importance analysis

### Clustering Analysis

执行 clustering analysis，包括 algorithm comparison 和 visualization：

```bash
python scripts/clustering_analysis.py
```

此 script 展示：
- 查找 optimal number of clusters（elbow method、silhouette analysis）
- 比较多个 clustering algorithms（K-Means、DBSCAN、Agglomerative、Gaussian Mixture）
- 无 ground truth 时评估 clustering quality
- 使用 PCA projection 可视化 results

## Reference Documentation

此 skill 包含用于深入了解特定主题的 comprehensive reference files：

### Quick Reference
**File：** `references/quick_reference.md`
- 常见 import patterns 和 installation instructions
- 常见 tasks 的 quick workflow templates
- Algorithm selection cheat sheets
- Common patterns and gotchas
- Performance optimization tips

### Supervised Learning
**File：** `references/supervised_learning.md`
- Linear models（regression 和 classification）
- Support Vector Machines
- Decision Trees 和 ensemble methods
- K-Nearest Neighbors、Naive Bayes、Neural Networks
- Algorithm selection guide

### Unsupervised Learning
**File：** `references/unsupervised_learning.md`
- 所有 clustering algorithms 的 parameters 和 use cases
- Dimensionality reduction techniques
- Outlier 和 novelty detection
- Gaussian Mixture Models
- Method selection guide

### Model Evaluation
**File：** `references/model_evaluation.md`
- Cross-validation strategies
- Hyperparameter tuning methods
- Classification、regression 和 clustering metrics
- Learning 和 validation curves
- Model selection best practices

### Preprocessing
**File：** `references/preprocessing.md`
- Feature scaling 和 normalization
- Encoding categorical variables
- Missing value imputation
- Feature engineering techniques
- Custom transformers

### Pipelines and Composition
**File：** `references/pipelines_and_composition.md`
- Pipeline construction 和 usage
- Mixed data types 的 ColumnTransformer
- Parallel transformations 的 FeatureUnion
- Complete end-to-end examples
- Best practices

## Common Workflows

### Building a Classification Model

1. **Load and explore data**
   ```python
   import pandas as pd
   df = pd.read_csv('data.csv')
   X = df.drop('target', axis=1)
   y = df['target']
   ```

2. **Split data with stratification**
   ```python
   from sklearn.model_selection import train_test_split
   X_train, X_test, y_train, y_test = train_test_split(
       X, y, test_size=0.2, stratify=y, random_state=42
   )
   ```

3. **Create preprocessing pipeline**
   ```python
   from sklearn.pipeline import Pipeline
   from sklearn.preprocessing import StandardScaler
   from sklearn.compose import ColumnTransformer

   # Handle numeric and categorical features separately
   preprocessor = ColumnTransformer([
       ('num', StandardScaler(), numeric_features),
       ('cat', OneHotEncoder(), categorical_features)
   ])
   ```

4. **Build complete pipeline**
   ```python
   model = Pipeline([
       ('preprocessor', preprocessor),
       ('classifier', RandomForestClassifier(random_state=42))
   ])
   ```

5. **Tune hyperparameters**
   ```python
   from sklearn.model_selection import GridSearchCV

   param_grid = {
       'classifier__n_estimators': [100, 200],
       'classifier__max_depth': [10, 20, None]
   }

   grid_search = GridSearchCV(model, param_grid, cv=5)
   grid_search.fit(X_train, y_train)
   ```

6. **Evaluate on test set**
   ```python
   from sklearn.metrics import classification_report

   best_model = grid_search.best_estimator_
   y_pred = best_model.predict(X_test)
   print(classification_report(y_test, y_pred))
   ```

### Performing Clustering Analysis

1. **Preprocess data**
   ```python
   from sklearn.preprocessing import StandardScaler

   scaler = StandardScaler()
   X_scaled = scaler.fit_transform(X)
   ```

2. **Find optimal number of clusters**
   ```python
   from sklearn.cluster import KMeans
   from sklearn.metrics import silhouette_score

   scores = []
   for k in range(2, 11):
       kmeans = KMeans(n_clusters=k, random_state=42)
       labels = kmeans.fit_predict(X_scaled)
       scores.append(silhouette_score(X_scaled, labels))

   optimal_k = range(2, 11)[np.argmax(scores)]
   ```

3. **Apply clustering**
   ```python
   model = KMeans(n_clusters=optimal_k, random_state=42)
   labels = model.fit_predict(X_scaled)
   ```

4. **Visualize with dimensionality reduction**
   ```python
   from sklearn.decomposition import PCA

   pca = PCA(n_components=2)
   X_2d = pca.fit_transform(X_scaled)

   plt.scatter(X_2d[:, 0], X_2d[:, 1], c=labels, cmap='viridis')
   ```

## Best Practices

### Always Use Pipelines
Pipelines 防止 data leakage 并确保 consistency：
```python
# Good: Preprocessing in pipeline
pipeline = Pipeline([
    ('scaler', StandardScaler()),
    ('model', LogisticRegression())
])

# Bad: Preprocessing outside (can leak information)
X_scaled = StandardScaler().fit_transform(X)
```

### Fit on Training Data Only
永远不要在 test data 上 fit：
```python
# Good
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)  # Only transform

# Bad
scaler = StandardScaler()
X_all_scaled = scaler.fit_transform(np.vstack([X_train, X_test]))
```

### Use Stratified Splitting for Classification
保持 class distribution：
```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, stratify=y, random_state=42
)
```

### Set Random State for Reproducibility
```python
model = RandomForestClassifier(n_estimators=100, random_state=42)
```

### Choose Appropriate Metrics
- Balanced data：Accuracy、F1-score
- Imbalanced data：Precision、Recall、ROC AUC、Balanced Accuracy
- Cost-sensitive：定义 custom scorer

### Scale Features When Required
需要 feature scaling 的 algorithms：
- SVM、KNN、Neural Networks
- 带 regularization 的 PCA、Linear/Logistic Regression
- K-Means clustering

不需要 scaling 的 algorithms：
- Tree-based models（Decision Trees、Random Forest、Gradient Boosting）
- Naive Bayes

## Troubleshooting Common Issues

### ConvergenceWarning
**Issue：** Model didn't converge
**Solution：** 增加 `max_iter` 或 scale features
```python
model = LogisticRegression(max_iter=1000)
```

### Poor Performance on Test Set
**Issue：** Overfitting
**Solution：** 使用 regularization、cross-validation 或 simpler model
```python
# Add regularization
model = Ridge(alpha=1.0)

# Use cross-validation
scores = cross_val_score(model, X, y, cv=5)
```

### Memory Error with Large Datasets
**Solution：** 使用为 large data 设计的 algorithms
```python
# Use SGD for large datasets
from sklearn.linear_model import SGDClassifier
model = SGDClassifier()

# Or MiniBatchKMeans for clustering
from sklearn.cluster import MiniBatchKMeans
model = MiniBatchKMeans(n_clusters=8, batch_size=100)
```

## Additional Resources

- Official Documentation: https://scikit-learn.org/stable/
- User Guide: https://scikit-learn.org/stable/user_guide.html
- API Reference: https://scikit-learn.org/stable/api/index.html
- Examples Gallery: https://scikit-learn.org/stable/auto_examples/index.html
