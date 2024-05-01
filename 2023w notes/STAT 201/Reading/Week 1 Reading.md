***
#### Chapter 7 - Sampling

###### Needed Packages
* `ggplot2` for data visualization
* `dplyr` for data wrangling
* `tidyr` for converting data to "tidy format"
* `readr` for importing spreadsheet data into R

#### 7.1 - Sampling Bowl Activity
###### 7.1.1 - What Proportion of this bowl's balls are red?
* There is a bowl with a certain number of red and white balls mixed together.

###### 7.1.2 - Using a shovel once
* By using the shovel that holds 50 balls we find that 17 of the balls picked up are red thus 34% of the shovel's balls are red.
* Would our guess at the proportion be 34% every time? No
###### 7.1.3 - Using the shovel 33 times
* We now get sample from the bowl 33 times.
* At the low end,  proportion of 0.20 and 0.25 red
* At the high end, proportion of 0.45-0.5 red
* The most frequently occurring proportions were between 0.30-0.35
###### 7.1.4 - What did we just do?
* We extracted a `sample` of 50 balls using the shovel to make an `estimate`

#### 7.2  - Virtual Sampling

###### 7.2.1-7.2.3 - Using the virtual shovel 
```r
virtual_samples <- bowl %>%
	rep_sample_n(size=50, reps=50) 

virtual_prop_red <- virtual_samples %>%
	group_by(replicate) %>%
	summarize(red = sum(color == "red")) %>%
	mutate(prop_red = red / 50)
```

###### 7.2.4 - Using Different Shovels
* As sample size increases, the variation of the 1000 replicates of the proportion of red decreases
* A `standard deviation` is a summary statistic that measures the amount of variation within a numerical variable



#### 7.3 Sampling Framework

###### 7.3.1 - Terminology and notation
* A `population` is a collection of individuals or observations we are interested in
* A `population parameter` is some numerical summary about the population that is unknown but you wish you knew
* A `census` is an exhaustive enumeration or counting of all N individuals in the population (process)
* `Sampling` is the act of collecting a sample from the population, which we generally only do when we can't perform a census
	* `Representative`: roughly "looks like" the population
	* `Generalizable`: Can be used to generalize the population
	* `Biased`: If certain individuals have a higher chance of being included
* `Point estimate`, is a summary statistic from a sample that estimates the unknown population parameter
* `Inference`, is the act of "making a guess" about some unknown.
