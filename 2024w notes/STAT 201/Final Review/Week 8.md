***
#### Learning Objectives
1. Describe the Law of Large Numbers
2. Describe a normal distribution
3. Explain the Central Limit Theorem and other general asymptotic results and their role in constructing confidence intervals
4. Write a computer script to calculate confidence intervals based on the assumption of normality or the Central Limit Theorem
5. Discuss the potential limitations of these methods
6. Decide whether to use asymptotic theory or bootstrapping to compute estimator uncertainty

#### Law of Large Numbers
* States that the sample average converges to the population mean
	* As the sample increases, the sample average gets closer and closer to the population mean

#### Normal Distribution
* Unimodal and bell-shaped
* Symmetric around the mean
* The standard deviation controls the spread of the curve

#### Central Limit Theorem
* When sample means are based on larger and larger sample sizes, the sampling distribution of these sample means become both increasingly normally shaped and narrow
* When our sample size gets larger
	* Sampling distribution of a point estimate increasingly follows a normal distribution
	* The variation of these sampling distributions gets smaller, as quantified by their standard erros




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

