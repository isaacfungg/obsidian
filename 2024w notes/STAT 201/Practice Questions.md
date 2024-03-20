***
A researcher is interested in the number of hours spent sleeping per night for some population of adults. They take a random sample of $n$ individuals from this population and find the average amount for this sample. They suspect the distribution of sleep times resembles a Normal distribution and they want to construct a 90% confidence interval for the mean number of hours spent sleeping per night. They are deciding between using a $z$* or $t_{n-1}$* critical values in their confidence interval.

1. Briefly explain in what scenarios might the researcher use a $t_{n-1}$* critical value over $z$* ?

The researcher would use a $t_{n-1}$* critical value when the sample size is small (usually n < 30) or when the standard deviation is unknown. The t-distribution accounts for the additional variability expected in estimated derived from smaller samples and when using the sample standard deviation as an estimator for the population standard deviation.

2. Suppose the researcher constructs two confidence intervals, one using $t$ and one using $n$ critical values with everything else remaining the same. How would you expect these intervals to differ?

The Interval using t critical values will generally be wider than the one using z critical values. This is because the t-distribution accounts for uncertainty of estimating the population standard deviation from the sample, especially with smaller sample sizes, leading to a wider interval to achieve the same level of confidence.

***
The Central Limit Theorem is important because it states that for a large enough sample size, the sampling distribution of the sample mean is approximately normal regardless of the population.

`Has to be for the sample distribution of the sample mean`

***
Given a sample of 100, and find that 20% are overweight. Then a 95% confidence interval for the true population is 
$$0.20 +- qnorm(0.975) * 0.04$$
Formula
$$p +- qnrom() * \sqrt{(p(1-p)/n}$$
***
Suppose the true proportion of heads for weighted coin is 0.4. The coin is flipped 100 times. In the group of 100 tosses, the proportion of heads would have mean and variance of:

**Mean**: 0.40 - Should be the same as the true proportion
**Variance**: 0.0024
$p(1-p)/n$

***
