***
Calculate the p-value of the test
```r
pnorm(zValue)
```

What is the highest test statistic value for which we would reject $H_0$ at an $a = 0.03$ significance level
```r
alpha <- 0.03

critical_z_value <- qnorm(1 - alpha, lower.tail = FALSE)
```

#### Question 2
