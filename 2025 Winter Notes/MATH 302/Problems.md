###### Section 2.4
What is the probability of $k$ success in n trials?
Ex A = "1 success in 3 trials" = {(1, 0, 0), (0, 1, 0) (0, 0, 1)}

$P(A) = P{{1, 0, 0}} + P{{0, 1, 0}} + P{{0, 0, 1}} = 3 \cdot p(1-p)^2$

Generally, if A = {k successes in n trials} = {All reorderings of (1, 1, ... 0, 0, ... 0)}
$P(A) = (\# $of unique reorderings$$) \cdot P{(1, 1, \dots 0, 0, \dots 0)}$



Roll three dice. X = number of 1s rolled
n = 1, p = prob you roll a 1 = 1/6
$P(x = 0) = \binom{3}{0} \cdot p^0 (1-p)^3 = 1 \cdot 1 \cdot (\frac{5}{6})^3$
$P(x = 1) = \binom{3}{1} \cdot p^1 (1-p)^2 = 3 \cdot \frac{1}{6} \cdot (\frac{5}{6})^2$
$P(x = 2) = \binom{3}{2} \cdot p^2 (1-p) = 3 \cdot (\frac{1}{6})^2 \cdot \frac{5}{6}$
$P(x = 3) = \binom{3}{3} \cdot p^3 (1-p)^0 = 1 \cdot (\frac{1}{6})^3 \cdot 1$

*** 
What is the probability you roll both dice at least 17 times?

P(You roll at least 17 times) = P (x ≥ 17)

$=\sum_{k \ge 17}P(X = k) = \sum_{k \ge 17}(1-p)^{k-1} \cdot p = \frac{(1-p)^{17-1} \cdot p}{1 - (1 - p)}$
$=(1-p)^{16}$

***
Roll two dice at the same time. "success" = the sum is even. Roll until "success". P("you roll both dice an even number of times")

X = # of rolls ~ Geom(p) 
P = P(sum is even) = $P(E_1, E_2) + P(O_1, O_2) = P(E_1) \cdot P(E_2) + P(O_1) \cdot P(O_2)$
= 1/4

$= \sum_{k = even} (1 - p)^{k - 1} \cdot p = \sum_{k = even} (1/2)^k = \frac{1}{2^2} + \frac{1}{2^4} \dots$
= 1/3

###### Section 3.1
Let X ~Unif[3.7]. What is $P(X \in [3, 4])$
$f(x) = 1/4 x \in [3,7], 0x !\in [3,7]$


