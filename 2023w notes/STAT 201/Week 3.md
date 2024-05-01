***
#### Bootstrapping
* **Bootstrap Distribution**: An _approximation_ to the _sampling distribution_ of the sample mean
#### Sampling with replacement
```R
virtual_resample <- pennies_sample %>% 
  rep_sample_n(size = 50, replace = TRUE)
```
* rep_sample_n has a false as the default value of replace
* Samples of the bootstrap should be the same size as the sample

Idea Behind Bootstrapping
* We can't take repeated samples from the population (too expensive)
* Instead we can use sample distribution as the source of our repeated samples
* Must take samples with replacement

Properties behind Bootstrap Distribution
* The spread/variability, and shape of the bootstrap should be similar to that of the sampling distribution
* If sample size changes, the spread of the bootstrap distribution changes
* However, the bootstrap will be centred at the value of the point estimate of the original sample. Not the population parameter.

Purpose of bootstrapping
* Lets us estimate the spread/variability of the sampling distribution (measured by standard error)
* It does not "improve" our point estimate for the population parameter
* If only a point estimate is desired, bootstrapping is no better than not bootstrapping
