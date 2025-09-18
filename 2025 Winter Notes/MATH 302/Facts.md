***

#### Section 1.2
* There are n! ways of ordering a list of n distinct elements
* If $\# \Omega \lt \infty$ and each outcome is equally likely, then $P(A) = \frac{\# A}{\# \Omega}$
* The number of ways to pick k items from n, where order matters, is $(n)_k = \frac{a!}{(n-k)!}$ called "n pick k"
* The number of ways of choosing k elements out of n, disregarding order, is $\binom{n}{k} = \frac{n!}{(n-k)!k!}$

#### Section 2.1
* $P(A_1 A_2 A_3 ... A_n) = P(A_1) * P(A_2 | A_1) * P(A_3|A_1 A_2) ... P(A_n|A_1 A_2 ... A_{n-1})$
* $P(A) = P(AB) + P(AB^C) = P(A|B) * P(B) + P(A|B^C) * P(B^C)$
* $B_1, B_2, ... B_n$ are a partition of $\Omega$ if they are pairwise disjoint

#### Section 2.2
* If A and B are independent, then so are A and $B^C$ also $A^C$ and B and $A^C B^C$
* 

C = {Door you first picked had car}
G = {Host reveals goat behind different door}

Standard Strategy: Host always reveals a goat behind a different door than the one you chose
P(C|G) = $\frac{P(G|C)\cdot P(C)}{P(G)} = \frac{1 \cdot \frac{1}{3}}{1} = 1/3$
* 2/3 chance remaining door has car

Evil Strategy: Host only reveals goat (behind different door) if you picked car door to start
P(C|G) = $\frac{P(G|C)\cdot P(C)}{P(G)} = \frac{1 \cdot \frac{1}{3}}{\frac{1}{3}} = 1$

Random Strategy: Host reveals random door
P(C|G) = $\frac{P(G|C)\cdot P(C)}{P(G)} = \frac{\frac{2}{3} \cdot \frac{1}{3}}{\frac{2}{3}\frac{2}{3}} = 1/2$
P(G) = P{Host reveals different door than you chose and door revealed is goat} = 2/3 * 2/3

