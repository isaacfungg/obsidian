***
**Feature engineering** is the process of **transforming raw data into features** that better represent the underlying problem to the predictive models, resulting in improved model accuracy on unseen data.

### Better features usually help more than a better model.
- Good features would ideally:
    - capture **most important aspects** of the problem
    - allow learning with **few examples**
    - **generalize** to new scenarios.
- There is a trade-off between **simple** and **expressive** features:
    - With **simple features** overfitting risk is low, but **scores might be low**.
    - With **complicated features** scores can be high, but so is **overfitting risk**.

### The best features may be dependent on the model you use.
- Examples:
    - For counting-based methods like decision trees, separate relevant **groups of variable values**
        - Discretization
            - Partitioning and converting continuous attributes into discrete intervals
            - Enables using continuous features for algorithms requiring discrete features
    - For distance-based methods like kNN, we want different class labels to be "far".
        - Standardization
            - Avoid dominance of wide-ranging features over other features with smaller ranges
    - For regression-based methods like linear regression, we want targets to have a linear dependency on features.

### Feature crosses for one-hot encoded features
- You can think of **feature crosses of one-hot-features as logical conjunctions**
- Suppose you want to predict whether you will **find parking or not** based on two features:
    - **area** (possible categories: UBC campus and Rogers Arena)
    - **time** of the day (possible categories: 9am and 7pm)
- A **feature cross** in this case would create **four new features**:
    - UBC campus and 9am
    - UBC campus and 7pm
    - Rogers Arena and 9am
    - Rogers Arena and 7pm.
- The features UBC campus and 9am on their own are not that informative but the newly created feature UBC campus and 9am or Rogers Arena and 7pm would be quite informative.
#### PolynomialFeatures
```python
from sklearn.preprocessing import PolynomialFeatures
pipe_xor = make_pipeline(
    PolynomialFeatures(interaction_only=True, include_bias=False), LogisticRegression()
)
pipe_xor.fit(X_xor, y_xor)
pipe_xor.score(X_xor, y_xor)
```
- Enhancing model performance by capturing interactions between features and non-linear effects.
- Used in regression models, including linear regression, to model complex relationships.

###### Viewing the Columns
```python
pd.DataFrame(
    pipe_xor.named_steps["logisticregression"].coef_.transpose(),
    index=feature_names,
    columns=["Feature coefficient"],
)
```

***
#### KBinsDiscretizer
```python
from sklearn.preprocessing import KBinsDiscretizer

discretization_feats = ["latitude", "longitude"]
numeric_feats = ["rooms_per_household"]

preprocessor2 = make_column_transformer(
    (KBinsDiscretizer(n_bins=20, encode="onehot"), discretization_feats),
    (make_pipeline(SimpleImputer(), StandardScaler()), numeric_feats),
)
```
* It discretizes continuous features into discrete values across k bins, where k is a user-defined number. This can help capture non-linear relationships between features and the target variable.

***
#### RFE algorithm
1. Decide , the number of features to select.
2. Assign importances to features, e.g. by fitting a model and looking at `coef_` or `feature_importances_`.
3. Remove the least important feature.
4. Repeat steps 2-3 until only  features are remaining.

```python
from sklearn.feature_selection import RFE

# create ranking of features
rfe = RFE(LogisticRegression(), n_features_to_select=5)
rfe.fit(X_train_scaled, y_train)
rfe.ranking_

# array([16, 12, 19, 13, 23, 20, 10,  1,  9, 22,  2, 25,  5,  7, 15,  4, 26, 18, 21,  8,  1,  1,  1,  6, 14, 24,  3,  1, 17, 11])

print(rfe.support_)
# [False False False False False False False  True False False False False False False False False False False False False  True  True  True FalseFalse False False  True False False]

print("selected features: ", cancer.feature_names[rfe.support_])
# selected features:  ['mean concave points' 'worst radius' 'worst texture' 'worst perimeter' 'worst concave points']
```

###### RFECV - Same but with cross validation
```python
rfe_pipe = make_pipeline(
    StandardScaler(),
    RFECV(LogisticRegression(max_iter=2000), cv=10),
    RandomForestClassifier(n_estimators=100, random_state=42),
)
```

#### (Optional) Forward or backward selection
- Also called wrapper methods
- Shrink or grow feature set by removing or adding one feature at a time
- Makes the decision based on whether adding/removing the feature improves the CV score or not