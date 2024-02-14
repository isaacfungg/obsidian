***
Diagram
```R
population -> parameters
sample -> point estimate -> estimates -> parameter
sample -> estimator -> standard error
bootstrap samples -> bootstrap distribution -> estimates -> sampling distribution
bootstrap distribution -> standard deviation -> estimates -> standard error
```

The standard deviation of a bootstrap distribution can provide a reliable estimate of the standard error of an estimator, even if the estimator's distribution is asymmetrical

Suppose you repeated the process above and took 100 more samples and calculated a 90% confidence interval for each sample. How many of the 100 intervals would you expect to capture the true median of the population?
* 90

Does the confidence capture the population parameter we are interested in?
* There is no way to know because we do not have access to data for the entire population

How to interpret confidence interval of 80%?
* We are 80% confident that the true population of individuals in our population is captured by the confidence intervals

Suppose you calculated another 80% confidence interval for the population proportion, but with a sample that was 5 times larger than cancer_sample. How would you expect this second interval compare to the first confidence interval you calculated above.
* The second confidence interval would likely be narrower than the first
* When the sample size increases, the standard error decreases, leading to narrower confidence intervals.

If we increased the confidence level of the confidence interval flow_ci, we would expect that it would become narrower.
* False. Increasing the confidence level of a confidence interval would generally lead to wider intervals, not narrower ones.


###### Infer Coding Example
```R
cancer_ci <- cancer_sample %>%
	specify(response = diagnosis, success = "M") %>%
	generate(type = "bootstrap", reps = 1000) %>%
	calculate(stat = "prop") %>%
	get_ci(type = "percentile", level = 0.80)
```


