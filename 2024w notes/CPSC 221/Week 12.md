***
1. Where to place **rear** of queue to achieve O(1) for en/dequeue?

2. Which input tree produces an output that will determine the type of traversal no matter the order?
```cpp
for (i = 0; i < 3; i++) {
	C1.Insert(i + 1);
}

for ("     "){
	C2.Insert(c1.remove());
}

for ("       ") {
	cout << c2.remove() <<
}
```

3. If capacity of array = 57 when reaching capacity, increase size by 36. What is total cost over n insertions?

4. What are the possible insert values? Calling deletemin, which key's positions are changed?
```         
		18
        /  \
      38    33
     /  \   / \
   48   58 69 62
  /  \   \
74    51  87

```

5. Do circled edges represent a possible sequence of Kruskal's algorithm?
* If a set of edges forms a valid partial execution of Kruskal's algorithm, select the next edge that would be added by the algorithm. If not, select the first edge incorrectly added to the tree by the algorithm.
```
- (B,C) = 7
- (B,E) = 19
- (D,G) = 21
- (C,D) = 36
- (E,F) = 45
- (C,H) = 51
- (D,E) = 56
- (D,F) = 57
- (C,E) = 62
- (E,G) = 64
- (A,H) = 69
- (A,G) = 77
- (B,H) = 93
- (G,H) = 94

```

6.  For AVL tree that has had a node removed but not balanced yet, what key value might've been removed? Critically unbalanced node (lowest)? How to repair imbalance with rotations?

7. Inserting duplicate value into BST such that duplicate value is in LEFT subtree of original value. What operations do you have to do?
```
      115
     /    \
     38    RST
    /   \
   18    85
  /  \    / \
 13   28 68  110

```
How to make it 18 subtree of 18?


8. What is this big O(?)

Find exact expression for return value.
```
gloggy(int n){
  int r = 2;
  int s = 0;
  for (int q = 0, q < n, q++){
    s = s + q * q;
    for (int t = 0; t < 2 * s; t++){
      t++;
    }
  }
  return s/r;
}

```

9. A BST with 388 NULL pointers, how many nodes?

10. Split n elements into n/4 subarrays each with 4 elements
* Cost to merge ordered n/4 subarrays?
* Levels that recursion tree will have when run on an unordered array of 8n elements?
* Cost to run this version of merge sort on unordered array of 8n elements?

11. Which key could have been the first one inserted?
	* P, C
* Which key could have been the last one inserted?
	* N
* Keys that must have been inserted before key `M`:
	* C, A
* Keys that must have been inserted after key `M`:
	* N
```
Key k, hash(k)
A 6
P 3
N 1
I 2
M 6
G 6
C 0

```


12. Final state of the hash table
```
Cuckoo hashing
key(k)  hash1(k)  hash2(k)
S       6         2
E       3         4
Q       4         1
U       4         6
O       5         4
I       0         5
A       2         5

keys inserted in order: O E Q V U A S I
0 1 2 3 4 5 6
[ ][ ][ ][ ][ ][ ][ ]

```


13. Expect values do appear on same page
```
☐ a queue implemented as a linked list, we dequeue then enqueue
☐ a dictionary implemented as an unsorted array with int keys, where we do delete(i) and then insert(j), paying attention only to where i was found and j ends up
☐ a queue implemented as a circular array, we do two enqueues

```



Programming mix function
```cpp

void DoublyLinkedList::Mix() {
	if (!head || !head->next) return;

	Node *current = head;
	while (current && current->next) {
		Node* nextNode = current->next;
		
	}
}
```