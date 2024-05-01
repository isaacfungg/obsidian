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

Why is taking bootstrap sizes larger than the original sample not a good idea?
* Taking bootstrap sizes of a larger size than the original samples results in an artificially narrower bootstrap distribution, which does not do a good job at estimating the sampling distributions for the original sample size. (we will under-estimate the standard error)
* Also, by taking bootstrap sizes that are smaller than the original size it would cause the estimate to be an over-estimate

Getting the standard error and standard deviation
```R
standard_error <- barrier_sampling_dist$data %>%
	summarize(se = sd(p)) %>%
	as.numeric()

standard_deviation <- barrier_bootstrap_dist$data %>%
	summarize(sd = sd(p)) %>%
	as.numeric()
```


