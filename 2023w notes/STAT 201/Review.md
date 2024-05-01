***
#### Z Scores
* A Z score of 0 means the value is exactly at the mean
* A positive Z score means the value is above the mean, and the magnitude tells you how many sd above 
* A negative value means the value is below the mean, and the magnitude tells you how many sd below

#### P-Value
It is the statistical measure that quantifies the probability of observing the data as extreme as, or more extreme than, the data actually observed, assuming that the null hypothesis is true.
Misconceptions
* The p-value does not tell you the probability that the null hypothesis is true or false

```R
# Lower tail FALSE if observing a value greater than the specified value
# Lower tail TRUE if observing a value less than equal to the specified value
pvalue = pnorm(Z-Score, lower.tail=FALSE)
```

#### Rules
**68-95-99.7 rule**
* Approximately 68% of the data fall within one sd of the mean
* Approximately 95% of the data fall within two sd of the mean
* Approximately 99.7% of the data fall within three sd of the mean

