***
**P Satisfies**
* $0 \le P(A0 \le 1$, for any $A \in F$ 
* $P(\emptyset) = 0, P(\Omega) = 1$
* If $A_1, A_2, A_3, ...$ are pairwise disjoint, $\bigcup_{i=1}^{\infty} A_i = \sum_{i=1}^{\infty} A_i$

###### Section 2.1
**Conditional Probability**
$P(A | B) = \frac{P(A \bigcap B)}{P(B)}$

###### Section 2.2
**Bayes Formula**
* $P(B|A) = \frac{P(A|B) * P(B)}{P(A)} = \frac{P(A|B) * P(B)}{P(A|B) * P(B) + P(A|B^C) * P(B^C)}$

###### Section 2.3
* Events A and B are independent iff $P(AB) = P(A) \cdot P(B)$
	* Given P(A), P(B) $\gt$ 0 then P(A|B) = P(A), P(B|A) = P(B)
* Events $A_1, A_2, \dots A_n$ are independent iff for any set of indices 1 ≤ $i_1$ < $i_2$ < ... < $i_k$ ≤ n we have $P(A_i A_{i_2} \dots A_{i_k})$ = ${P(A_{i_1}) \cdot P(A_{i_2}) \dots P(A_{i_k})}$

**Independent Random Variables**
* Let $X_1, X_2, \dots, X_n$ be random variables defined on the same probability space. Then $X_1, X_2, \dots, X_n$ are independent iff $$P(X_1 \in B_1, X_2 \in B_2,\dots, X_n \in B_n)$$
* for all * choices of subsets $B_1, B_2, \dots, B_n$ of the real line.

###### Section 2.4
**Bernoulli Random Variable**
* A Bernoulli r.v. with parameter $p$ satisfies:
$x = \{1$ with prob $p, 0$ with prob $1-p\}$
$x~Bern(p)

**Binomial Random Variables**
* A binomial r.v. with parameters $n$ and $p$ satisfies
* $P(X = k) = \binom{n}{k} \cdot p^k (1-p)^{n-k}$

 Let $X_1, X_2, \dots, X_n$ ~ Bern(p) be independent
 Then $X_1 + X_2 + \dots +X_n$ 

**Geometric Random Variable**
* A geometric random variable with parameter p satisfies:
* $P(X = k) = (1-p)^{k-1}p, k \in \{1, 2,, \dots\}$


###### Section2.5
Events A and B are said to be conditionally independent given event D if P(AB | D) = P(A|D) * P(B|D)

 ###### Section 3.1
 We say that a r.v. X has probability density function $f$ if $P(X \le a) = \int_{-\infty}^{a}f(x)dx$
 * Not every random variable has a pdf

We call X a continuous r.v.
$P(X \in [a, b]) = \int_{a}^{b} = P(X \in(a,b))$
$P(X \in B) = \int_{B} f(x)dx$
$P(X = k) = \int_{k}^{k} f(x)dx = 0$
Pdf must satisfy $\int_{-\infty}^{\infty} f(x)dx = 1, f(x) \ge 0$ for all x

Uniform r.v.
Def: Let X have pdf $f(x) = { \frac{1}{b - a} x \in [a, b], 0 x !\in [a, b]}$
Then we say X has uniform distribution on [a, b], i.e. X ~ Unif[a, b]








