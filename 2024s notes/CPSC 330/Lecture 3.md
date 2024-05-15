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
- Common practice to pick the model with the minimum cross validation error

#### Types of Errors
`Underfitting`
* The model is too simple
* Both train and validation errors would be high
*  The gap between train and validation error is going to be lower.

`Overfitting`
* The model is too complex
* There will be a big gap between the training and validation error
* The training error will be low 

As you increase the depth of the model, the $E_{train}$ decreases but the $E_{valid} - E_{train}$ increases

###### Bias vs Variance tradeoff
`Bias`
* Tendency to consistently learn the wrong thing (high bias corresponds to underfitting)
`Variance`
* Tendency to learn random things irrespective to the real thing (high variance corresponds to overfitting)

