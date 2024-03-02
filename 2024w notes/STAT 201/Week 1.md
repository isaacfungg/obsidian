***
##### Proportion

###### Mutate and Summarize
```R
df %>%
	mutate(columnName = (x = y))
	summarize(newColunName = sum(columnName))
```
* Mutate: Creates a new column in the data frame
* Summarize: Returns a data frame with a single row of summary statistics (Sum, Median)
###### Histograms
```R
ggplot(virtual_prop_red, aes(x = prop_red)) +
  geom_histogram(binwidth = 0.05, boundary = 0.4, color = "white") +
  labs(x = "Proportion of 50 balls that were red", 
       title = "Distribution of 33 proportions red") 
```
* Boundary: Makes sure that the specified point is in the plot on the x-axis

###### Terms
* **Population (Study Population)**: A collection of individuals or observations we are interested in
* **Population Parameter**: A numerical summary about the population that is unknown but you wish you knew
* **Census**: An exhaustive enumeration or counting of all N individuals in the population (To get the actual value of the population parameter)
* **Point Estimate (Sample Statistic)**: A summary statistic computed from a sample that _estimates_ the unknown population parameter
* **Random Sampling**: Results in a sample that is unbiased and representative of the population
* **Statistical Inference**: The act of making a guess about a population using a sample
* **Variance**: The average squared distance from the mean
* **Standard Deviation**: Square root of the variance (Spread)
	*  Useful when considering how far the data are distributed from the mean
* **Standard Error**: The standard deviation of a sampling distribution
	* Measure of the variability of the point estimates in the sampling distribution

###### Sampling Terms
* **Representative**:  If the sample’s characteristics are a “good” representation of the population’s characteristics
* **Generalizable**: If we can make “good” guesses about the population using the sample
* **Biased**: If certain individuals in a population have a higher chance of being included in a sample than others
* **Inference**: The act of “making a guess” about some unknown