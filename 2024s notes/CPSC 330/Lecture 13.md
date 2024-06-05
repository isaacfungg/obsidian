***
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