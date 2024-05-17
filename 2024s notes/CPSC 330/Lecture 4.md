***
#### Support Vector Machines (SVM)
* SVM's have two hyperparameters: *c* and *gamma*
* A larger *gamma* and *c* value makes it more complex 
* A smaller *gamma* and *c* value makes it less complex

###### Outside Class Scope
* A high gamma value leads to the model reacting more significantly to deviations in data which can capture more complex patterns but can also lead to overfitting

1. **High C and low gamma**: Use this setting if you want the decision boundary to be more influenced by the training data points that are close to the margin, even if it risks fitting to noise and outliers.
    
2. **Low C and high gamma**: This setup allows the decision boundary to be smooth and not overly complex, which can prevent overfitting but might not capture more complex patterns.
    
3. **High C and high gamma**: This combination can make the decision boundary highly sensitive to the training data, fitting very tightly around data points. It’s useful when you are confident that the data has little noise and the decision boundary needs to be complex.
    
4. **Low C and low gamma**: This configuration leads to a very smooth and simple decision boundary, which is generally good for very noisy data where the priority is to avoid overfitting at the cost of not capturing finer details in data distribution.