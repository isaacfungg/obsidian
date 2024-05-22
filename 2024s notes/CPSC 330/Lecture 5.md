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


#### Pipelines
```Python
knn = KNeighborsRegressor()

scaler = StandardScaler()
scaler.fit(X_train_imp)
X_train_scaled = scaler.transform(X_train_imp)
X_test_scaled = scaler.transform(X_test_imp)
scores = cross_validate(knn, X_train_scaled, y_train, return_train_score=True)
pd.DataFrame(scores)
```
* In this example we fit on X_train but then perform cross validate after. This breaks the golden rule because since we fit on the entire X_train then when the cross validate does its folds then it would be leaking information
* **Solution**: Use pipelines


```python
from sklearn.pipeline import make_pipeline

pipe = make_pipeline(
    SimpleImputer(strategy="median"), 
    StandardScaler(), 
    KNeighborsRegressor()
)

pipe.fit(X_train, y_train);
```

When you call `fit` on the pipeline, it carries out the following steps:

- Fit `SimpleImputer` on `X_train`
- Transform `X_train` using the fit `SimpleImputer` to create `X_train_imp`
- Fit `StandardScaler` on `X_train_imp`
- Transform `X_train_imp` using the fit `StandardScaler` to create `X_train_imp_scaled`
- Fit the model (`KNeighborsRegressor` in our case) on `X_train_imp_scaled`


#### Ordinal Encoding (Occasionally Recommended)
```Python
from sklearn.preprocessing import OrdinalEncoder

enc = OrdinalEncoder()
enc.fit(X_toy)
X_toy_ord = enc.transform(X_toy)
df = pd.DataFrame(
    data=X_toy_ord,
    columns=["language_enc"],
    index=X_toy.index,
)
pd.concat([X_toy, df], axis=1)
```
* Turns categorial data into numerical
* It is better for categorial values like ["cold", "warm", "hot"] besides languages because it will create some order that can make the data messy
* **Solution**: Use *One-Hot Encoding* that will create n new binary columns where a language would be 1 if true and 0 if false

#### One-Hot Encoding
```Python
from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder(handle_unknown="ignore", sparse_output=False)
enc.fit(X_toy)
X_toy_ohe = enc.transform(X_toy)
pd.DataFrame(
    data=X_toy_ohe,
    columns=enc.get_feature_names_out(["language"]),
    index=X_toy.index,
)
```