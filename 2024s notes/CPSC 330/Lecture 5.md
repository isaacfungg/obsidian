***
#### StandardScaler
```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()  # create feature trasformer object
scaler.fit(X_train)  # fitting the transformer on the train split
X_train_scaled = scaler.transform(X_train)  # transforming the train split
X_test_scaled = scaler.transform(X_test)  # transforming the test split
```
* We never fit on test because that would be considered as looking at the data
* We can fit on train and then we would use transform on test
* For standard scaling we make the mean equal to 0 and the standard deviation to be equal to 1

#### NaN Values
* For *categorial values* we can replace it with the most frequent value
* For *numerical values* we can replace it with the mean or median value of the column

We can do this by using SimpleImputer
```python
imputer = SimpleImputer(strategy="median")
imputer.fit(X_train)
X_train_imp = imputer.transform(X_train)
X_test_imp = imputer.transform(X_test)
```