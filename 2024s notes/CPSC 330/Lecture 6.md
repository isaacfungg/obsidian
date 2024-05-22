***
11, 11:30, 11:45, 12, 12:15, 12:25
#### Column Transformer
```Python
from sklearn.compose import make_column_transformer

ct = make_column_transformer(    
    (StandardScaler(), numeric_feats),  # scaling on numeric features
    ("passthrough", passthrough_feats),  # no transformations on the binary features    
    (OneHotEncoder(), categorical_feats),  # OHE on categorical features
    ("drop", drop_feats),  # drop the drop features
)
```
* In Column Transformer we can separate the columns


###### Viewing the transformed data
```Python
ct.named_transformers_
# {'standardscaler': StandardScaler(), 'passthrough': 'passthrough', 'onehotencoder': OneHotEncoder(), 'drop': 'drop'}

ct.named_transformers_["standardscaler"].get_feature_names_out()
# array(['university_years', 'lab1', 'lab3', 'lab4', 'quiz1'], dtype=object)
```