***
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


#### Count Vectorizer
Used to count the number of times a values is used
- `binary`
    - whether to use absence/presence feature values or counts
- `max_features`
    - only consider top `max_features` ordered by frequency in the corpus
- `max_df`
    - max "document frequency": ignore features which occur in more than `max_df` documents
- `min_df`
    - min "document frequency": ignore features which occur in less than `min_df` documents
- `ngram_range`
    - consider word sequences in the given range