***
#### Confidence Interval
##### Percentile Method
* One method to construct a confidence interval is to use the middle 95% of values of the bootstrap distribution (2.5-97.5%)

##### Code
```R 
pennies_sample %>% 
	rep_saple_n(size=50, replace=TRUE, reps=1000)%>%
	group_by(replicate) %>%
	summarize(mean_year = mean(year))
```
* Set replace to true to resample with replacement
* Grouped rows together 
* Computed the mean of each replicate

#### Infer
```R
pennies_sample %>%
	specify(response = year) %>%
	calculate(stat="mean")
```
**Benefits:**
* You can jump back and forth seamlessly between confidence intervals and hypothesis testing with minimal changes to your code
* Much simpler for conducting inference when you have more than one variable

###### Specify
* The function is used to choose which variables in a data frame will be the focus of our statistical inference
* We can also specify which variables with be the focus using ***formula = y ~ x* ** 
```R
pennies_sample %>%
	specify(formula = year ~ null)
``` 

* To define which event is of interest you can add the success argument
```R
bowl_sample_1 %>%
	specify(response=color, success="red")
```
###### Generate
* First argument is reps, second is type
```R
pennies_sample %>%
	specify(formula = year ~ null) %>%
	generate(reps=1000, type="bootstrap")	

```

###### Calculate
* We can set the stat argument to "mean" to calculate the mean
```R
bootstrap_distribution <- pennies_sample %>%
	specify(formula = year ~ null) %>%
	generate(reps=1000, type="bootstrap") %>%
	calculate(stat = "mean")
```
Other calculations includes:
* "prop" = proportion
###### Visualize
* Quick way to visualize the bootstrap distribution as a histogram
```R
visualize(bootstrap_distribution)
```

###### Confidence Interval with Infer
* We can compute the 95% confidence interval by piping bootstrap_distribution into the get_confidence_interval() function from the infer package
```R
percentile_ci <- bootstrap_distrubution %>%
	get_confidence_interval(level=0.95, type="percentile")
```
* Returns columns ***lower_ci*** and ***upper_ci***

* We can visualize the interval by adding  a shade_confidence_interval() layer
```R
visualize(bootstrap_distribution) + 
	shade_confidence_interval(endpoints = percentile_ci)
```

#### Interpreting Confidence Intervals
In order to interpret a confidence interval's effectiveness, we need to know what the value of the population parameter is.
* Larger sample sizes tend to produce narrower confidence intervals
* Higher confidence levels tend to produce wider confidence intervals


