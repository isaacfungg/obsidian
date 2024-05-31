***
#### Random Forest Classifier
```python
from sklearn.ensemble import RandomForestClassifier

pipe_rf = make_pipeline(
    preprocessor,
    RandomForestClassifier(
        n_jobs=-1,
        random_state=123,
    ),
)
results["Random forests"] = mean_std_cross_val_scores(
    pipe_rf, X_train, y_train_num, return_train_score=True, scoring=scoring_metric
)
pd.DataFrame(results).T
```
- `n_estimators`: number of decision trees (higher = more complexity)
- `max_depth`: max depth of each decision tree (higher = more complexity)
- `max_features`: the number of features you get to look at each split (higher = more complexity)

###### Strengths
- Usually **one of the best** performing **off-the-shelf** classifiers without heavy tuning of hyperparameters
- **Don't** require **scaling** of data
- **Less** likely to **overfit**
- Slower than decision trees because we are fitting multiple trees but  **can easily parallelize training** because all trees are independent of each other
- In general, able to capture a much broader picture of the data compared to a single decision tree.



#### Gradient Boosted Trees
- **No** randomization
- The key idea is:  combining many simple models called **weak learners to create a strong learner**
- They combine **multiple shallow** (depth 1 to 5) decision trees
- They build trees in a **serial manner**, where each tree tries to **correct the mistakes** of the previous one