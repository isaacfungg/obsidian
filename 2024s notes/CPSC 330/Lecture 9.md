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

```python
from sklearn.metrics import confusion_matrix

predictions = pipe.predict(X_valid)
TN, FP, FN, TP = confusion_matrix(y_valid, predictions).ravel()
TN, FP, FN, TP # (59700, 8, 38, 64)
```

Precision: $TP / (TP + FP)$
Recall: $TP/(TP+FN)$


### F1-score
- F1-score **combines precision and recall** to give one score, which could be used in hyperparameter optimization, for instance.
- F1-score is a harmonic mean of precision and recall.
$$f1 = 2 \times \frac{ precision \times recall}{precision + recall}$$
```python
from sklearn.metrics import accuracy_score, f1_score, precision_score, recall_score

data["accuracy"].append(accuracy_score(y_valid, pipe_lr.predict(X_valid)))
data["error"].append(1 - accuracy_score(y_valid, pipe_lr.predict(X_valid)))
data["precision"].append(
    precision_score(y_valid, pipe_lr.predict(X_valid), zero_division=1)
)
data["recall"].append(recall_score(y_valid, pipe_lr.predict(X_valid)))
data["f1 score"].append(f1_score(y_valid, pipe_lr.predict(X_valid)))
data["calculation"].append("sklearn")
df = pd.DataFrame(data)
df.set_index(["calculation"])
```