***
```R
# Confidence Intervals for 90%
ci <- df %>%
	summarise(lower_ci = quantile(stat, 0.05), upper_ci = quantile(stat, 0.95))
```

```R
# Visualizing using the infer package
ci_plot <-
	visualize(df) +
	shade_confidence_interval(endpoints=ci) 
```