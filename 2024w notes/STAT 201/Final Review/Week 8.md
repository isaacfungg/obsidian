***
#### Learning Objectives
1. Describe the learning 
#### pnorm (z value to percentile)
You can use *pnorm* with the Z value, the mean, and the standard deviation to get the percentile
```r
pnorm(zValue, mean = x, sd = y)
```
The percentile given represents the proportion of values in a normal distribution that are less than or equal to a specific value. So if you want to calculate the proportion of the other value you would do $1 - pnorm(...)$
#### qnorm (percentile to z value)
You can use *qnorm* with the percentile, the mean, and the standard deviation to get the Z value
```r
qnorm(0.80, mean = x, sd = y)
```

