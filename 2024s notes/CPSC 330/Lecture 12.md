***
```python
from sklearn.inspection import permutation_importance
def get_permutation_importance(model):
    X_train_perm = X_train.drop(columns=["race", "education.num", "fnlwgt"])
    result = permutation_importance(model, X_train_perm, y_train_num, n_repeats=10, random_state=123)
    perm_sorted_idx = result.importances_mean.argsort()
    plt.boxplot(
        result.importances[perm_sorted_idx].T,
        vert=False,
        labels=X_train_perm.columns[perm_sorted_idx],
    )
    plt.xlabel('Permutation feature importance')
    plt.show()
```

### SHAP (SHapley Additive exPlanations)

- Based on the idea of shapely values. A shapely value is created for each example and each feature.
- Can explain the prediction of an example by computing the **contribution of each feature to the prediction**.
- Great visualizations
- Support for different kinds of models; fast variants for tree-based models
- **SHAP** values tell us how to fairly **distribute the prediction among features**.