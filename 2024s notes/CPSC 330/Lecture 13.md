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

##### **Viewing the Columns**
```python
pd.DataFrame(
    pipe_xor.named_steps["logisticregression"].coef_.transpose(),
    index=feature_names,
    columns=["Feature coefficient"],
)
```