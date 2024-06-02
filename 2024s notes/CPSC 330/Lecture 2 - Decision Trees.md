***
#### Topics
* Supervised and unsupervised 
* Scoring models (accuracy)
* Decision Tree
* Parameters and hyperparameters

#### Decision Trees Classification
* Goes down until the values are completely pure if the depth is not specified
```python
from sklearn.tree import DecisionTreeClassifier
model = DecisionTreeClassifier()
model.fit(X_binary, y)
model.score(X_binary, y)
```
* The leaf nodes represent the answers
* `Decision Stump`: A decision tree with only one split
* Most pure (100% of one type)
* Most impure (50% one type and 50% another)

###### Parameters
* The decision tree algorithm primarily learns two things:
	* The best feature to split on
	* The best threshold for the feature to split on at each node

#### Scoring
```python
model.score(X_test, y_test) # Compares the predictions made from X_test to y_test

1 - model.score(X_test, y_test) # Gives the error
```
