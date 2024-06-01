***
#### Topics
* Supervised and unsupervised 
* Scoring models (accuracy)





* Most pure (100% of one type)
* Most impure (50% one type and 50% another)
#### Decision Trees Classification
* Goes down until the values are completely pure if the depth is not specified
```python
from sklearn.tree import DecisionTreeClassifier
model = DecisionTreeClassifier()
model.fit(X_binary, y)
model.score(X_binary, y)
```
* The leaf nodes represent the answers
* 

#### Scoring
```python
model.score(X_test, y_test) # Compares the predictions made from X_test to y_test

1 - model.score(X_test, y_test) # Gives the error
```
