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
