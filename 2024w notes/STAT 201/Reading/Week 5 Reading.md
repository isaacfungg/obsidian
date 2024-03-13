***
#### Chapter 9 - Hypothesis Testing
Hypothesis tests allow us to take a sample of data from a population and infer about the plausibility of competing hypotheses.
###### 9.2 Understanding Hypothesis Testing
- **Hypothesis Testing:** Involves comparing two hypotheses: the null hypothesis (H0) and the alternative hypothesis (HA).
- **Null Hypothesis (H0):** Represents no effect or difference, indicating a "status quo."
- **Alternative Hypothesis (HA):** Represents the effect or difference the researcher seeks to prove, acting as the "challenger."
- **Example:** H0: Men and women are promoted at the same rate vs. HA: Men are promoted at a higher rate than women.
- **Test Statistic:** A formula used to calculate a value (e.g., difference in sample proportions) from sample data for hypothesis testing.
- **Null Distribution:** The distribution of the test statistic under the assumption that H0 is true, used to evaluate how extreme the observed test statistic is.
- **Observed Test Statistic:** The actual value calculated from the data (e.g., 29.2% difference favoring resumes with male names).
- **p-Value:** The probability of observing a test statistic as extreme as the actual observed, assuming H0 is true. It quantifies the level of "surprise" based on the observed data.
- **Significance Level (α):** A pre-set threshold for the p-value, below which H0 is rejected, indicating statistical significance.
- **Decision:** Reject H0 if the p-value < α, suggesting the observed effect is statistically significant and not likely due to chance.

###### 9.3 Conducting Test Hypothesis
The infer package in R streamlines the process of conducting hypothesis tests and constructing confidence intervals by following a structured workflow:

1. **Specify Variables**: Use `specify()` to identify the response and explanatory variables from the dataset.
2. **Hypothesize the Null**: Include `hypothesize()` to define the null hypothesis (H0), such as no difference between groups.
3. **Generate Replicates**: Apply `generate()` to create replicates of data under H0 by resampling (bootstrap) or permuting.
4. **Calculate Summary Statistics**: Use `calculate()` to compute the test statistic for each replicate, such as the difference in sample proportions.
5. **Visualize p-value**: Employ `visualize()` to display the null distribution and calculate the p-value to evaluate the extremity of the observed statistic under H0.
6. **Compare with Confidence Intervals**: The process is similar for constructing confidence intervals, with the main difference being the omission of the `hypothesize()` step and using bootstrap resampling.

Hypothesis testing with the infer package involves setting up a model assuming the null hypothesis is true, generating data under this model, calculating test statistics, and comparing these to the observed statistic to compute a p-value. This process, encapsulated in Allen Downey's "There is only one test" framework, demonstrates that understanding one hypothesis testing framework allows for generalization across different types of hypothesis tests.