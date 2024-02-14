***
#### Questions
**Sampling Distribution:** Requires sampling from the population
**Bootstrap Sample Distribution:** Requires sampling from a sample from the population
**Bootstrap Sampling Distribution:** Requires sampling from a sample from the population
**Sample Distribution** Requires sampling from the population

* For both the sampling distributions and bootstrap distributions, as the sample size increase, the standard deviation decreases
* For both the sampling distribution and bootstrap distributions, as the sample size increase, the distributions appear more bell-shaped
* We can obtain a useful approximation of standard error by producing a bootstrap distribution if we only have access to a single sample.
* The standard deviation of a bootstrap distribution is a "good guess" of the standard deviation of the corresponding sampling distribution

Getting the standard error and standard deviation
```R
standard_error <- barrier_sampling_dist$data %>%
	summarize(se = sd(p)) %>%
	as.numeric()

standard_deviation <- barrier_bootstrap_dist$data %>%
	summarize(sd = sd(p)) %>%
	as.numeric()
```


