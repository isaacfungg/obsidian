***
#### Confusion Matrix
One way to get a better understanding of the errors is by looking at
* `False positives` (type I errors), where the model incorrectly spots examples as fraud
- `False negatives` (type II errors), where it's missing to spot fraud examples
- **Perfect** prediction has all values **down the diagonal**
- **Off diagonal** entries can often tell us about what is being **mis-predicted**

```python
from sklearn.metrics import ConfusionMatrixDisplay  # Recommended method in sklearn 1.0

pipe.fit(X_train, y_train)
cm = ConfusionMatrixDisplay.from_estimator(
    pipe, X_valid, y_valid, values_format="d", display_labels=["Non fraud", "fraud"]
)
```