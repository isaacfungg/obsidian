***
### Test/Validation/Deployment Data
Validation data
* Only used for hyperparameter tuning
* We don't pass these into fit

Test data
* Only test with this data once

Deployment data
* We use validation and test errors as proxies for deployment error

|            | `   fit` | `score` | `predict` |
| ---------- | -------- | ------- | --------- |
| Train      | ✔️       | ✔️      | ✔️        |
| Validation |          | ✔️      | ✔️        |
| Test       |          | once    | once      |
| Deployment |          |         | ✔️        |
#### Cross Validation
* If the dataset is small then you might end up with a tiny test/validation set
* This causes it so that if you get unlucky it can make it so that it does not represent the data well

###### Solution - Cross Validation
* Split the data into $k$ folds (  $k > 2$, often $k = 10$)
* Each fold gives a score and we usually average our $k$ results.
- It's better to examine the variation in the scores across folds.

