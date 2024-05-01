***
Why do B-Tree nodes have a large number of keys compared to the height of the B-Tree?
* The cost of seeking/fetching a node is significantly greater than the cost of selecting a particular key.

What is true about BTree of order M?
* Internal nodes have one more child than key

What is the maximum number of keys in any node of a BTree of order m?
* $m - 1$

What is the maximum number of keys that can be stored in a B-Tree of order 32 and height 6?
* $32^7 - 1$
* Formula: $o^{h+1}-1$
* o: order, h: height

Hash tables:
* Use O(1) time speed
* Uses more memory than a regular array
* When efficient use of memory is not important pick the largest capacity to avoid collision rate

What is the best definition of a collision in a hash table?
* Two entries with different keys have the same exact hash value

