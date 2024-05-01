***
#### Learning Objectives
1. Describe the t-distribution family and its relationship with the normal distribution
2. Use results from the assumption of normality or the Central Limit Theorem to perform estimation and hypothesis testing
3. Compare and contrast the parts of estimation and hypothesis testing that differ between simulation and resampling-based approaches with the assumption of normality or the Central Limit Theorem-based approaches
4. Write a computer script to perform hypothesis testing based on results from the assumption of normality or the Central Limit Theorem
5. Discuss the potential limitations of these methods

#### T Test
`One-Sample t-test`
* This test compares the mean of a single sample to a known mean. It evaluates whether the sample mean differs significantly from the population mean.
* $(x - \mu)/(s/\sqrt{n})$
* $x$ is the sample mean
* $\mu$ is the population mean
* $s$ is the sample standard deviation
* $n$ is the sample size

`Two-Sample t-test`
* This test compares the means of two independent groups to see if there is a statistically significant difference between them. It is applicable when the two groups are not related in any way
* $(x_1 - x_2) / \sqrt{s_p(1/n_1 + 1/n_2)}$
* $x_1, x_2$ are the means of the two samples
* $s_p$ is the pooled variance, calculated as weighted average of the variances of the two samples
* $n_1, n_2$ are the sample sizes

`Paired Sample t-test`
* Used to compare the means from the same group at different times, or the differences between pairs of related observations.
* $d/(s_d/\sqrt{n})$
* $d$ is the mean of the differences between the paired observations
* $s_d$ is the standard deviation of these differences
* $n$ is the number of pairs
### Z score
$Z = (point estimate - null value) / SE$
* Ratio of how the sample proportion differs from the hypothesized proportion as compared to the expected variability of the p values

#### Proportion Z-Score
$Z = (p - p_0)/ \sqrt{(p_0(1-p_0))/n}$

