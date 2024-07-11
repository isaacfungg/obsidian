
**Claim**: There exists only one stable solution

A stable matching is defined where there is no pairs (e, a) and (e_1, a_1) such that e prefers a_1 and a_1 prefers e over their current match.

Since all of the employers have the same preference list then for any pair (e, a) all employers have a ranked equally. Therefore, the determining factor of the matching would be a. 

###### Proof by contradiction
Case 1: More than 1 stable solution

Assume that we have an smp instance with two stable solutions and employers have the same preference list. 

However, given $P = p[e]$ where $P$ is the preference list for all employers. Applicant will get matched in the order of $P$. If the employer has already been chosen move on to the next preferred employer. Because the order has been defined there will be no non unique preference meaning there is no chance for more than one solution causing a contradiction.

Case 2: Zero stable solutions

Assume that we have an smp instance with zero stable solutions and employers have the same preference list.

Since we have determined that the applicants would follow a specific order and choose accordingly that tells us that there is one solution causing a contradiction.




**Claim**: There exists only one stable solution

###### Proof by contradiction

Example:
E = {e1, e2, e3}
A = {a1, a2, a3}

e1: a3 a2 a1
e2: a3 a2 a1
e3: a3 a2 a1

a1: e1, e2, e3
a2: e3, e2, e1
a3: e1, e2, e3

P = {a3, a2, a1} - *Order in which applicants can choose
* Logic: All employers first pick is **a3** so a3 basically gets to "choose" its employer because whatever its preference is it would get. Repeat for all of **P** and if an employer is already picked then go to the next preferred.
##### Example:
According to **P**, **A3** would get to "decide" first. 
{(e1, a3)}
~~e1: a3 a2 a1~~
e2: ~~a3~~ a2 a1
e3: ~~a3~~ a2 a1

a1: ~~e1~~, e2, e3
a2: e3, e2, e1
~~a3: e1, e2, e3~~

Next up would be e2 which has its first preference of e3:
{(e1, a3), (e2, a2)}
~~e1: a3 a2 a1~~
~~e2: a3 a2 a1~~
e3: ~~a3~~ ~~a2~~ a1

a1: ~~e1~~, ~~e2~~, e3
~~a2: e3, e2, e1~~
~~a3: e1, e2, e3~~

Which leaves us with the last pair e3 and a1.


***





