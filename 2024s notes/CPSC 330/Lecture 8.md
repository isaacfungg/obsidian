***
#### GridSearchCV
* For GridSearchCV we needL
	- An instantiated model or a pipeline
	- A parameter grid: A user specifies a set of values for each hyperparameter.
	- Other optional arguments

```python
from sklearn.model_selection import GridSearchCV

pipe_svm = make_pipeline(preprocessor, SVC())

param_grid = {
    "columntransformer__countvectorizer__max_features": [100, 200, 400, 800, 1000, 2000],
    "svc__gamma": [0.001, 0.01, 0.1, 1.0, 10, 100],
    "svc__C": [0.001, 0.01, 0.1, 1.0, 10, 100],
}

# Create a grid search object 
gs = GridSearchCV(pipe_svm, 
                  param_grid = param_grid, 
                  n_jobs=-1, 
                  return_train_score=True
                 )

# Get the best score
gs.best_score_

# Get the best hyperparameter values
gs.best_params_

# Get the test scores with the best params
gs.score(X_test, y_test)
```

### The `__` syntax
- Above: we have a nesting of transformers.
- We can access the parameters of the "inner" objects by using __ to go "deeper":
- `svc__gamma`: the `gamma` of the `svc` of the pipeline
- `svc__C`: the `C` of the `svc` of the pipeline
- `columntransformer__countvectorizer__max_features`: the `max_features` hyperparameter of `CountVectorizer`in the column transformer `preprocessor`.


#### HeatMap
```python
param_grid4 = {"svc__gamma": np.logspace(-3, 2, 6), "svc__C": np.linspace(2, 3, 6)}

display_heatmap(param_grid4, pipe_svm, X_train, y_train)
```


#### Randomized hyperparameter search
```python
# Create a random search object
random_search = RandomizedSearchCV(pipe_svm,                                    
                  param_distributions = param_grid, 
                  n_iter=100, 
                  n_jobs=-1, 
                  return_train_score=True)

# Carry out the search
random_search.fit(X_train, y_train)
```
* Note the `n_iter`, we didn't need this for `GridSearchCV`.
- Larger `n_iter` will take longer but it'll do more searching.
    - Remember you still need to multiply by number of folds!
- You can set the `random_state` for reproducibility but you don't have to do it.


#### Passing probability distributions to random search
```python
from scipy.stats import expon, lognorm, loguniform, randint, uniform, norm, randint

y = uniform.rvs(0, 5, 10000) # Uniformed distribution
y = norm.rvs(0, 1, 10000) # Normal distribution
y = expon.rvs(0, 1, 10000) # Skewed distribution
```