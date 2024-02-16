*** 
#### Merge Sort Correctness
```cpp
void MergeSort(vector<T>& arr) { MSort(arr, 0, arr.size() – 1);

}  
void MSort(vector<T>& arr, int low, int high) {

if (low < high) { // array has more than 1 element int mid = (low + high) / 2;  
MSort(arr, low, mid);  
MSort(arr, mid+1, high);

    Merge(arr, low, mid, high);
  }

}
```

Best case: n = 0 or n =1 (empty or already sorted)
Average: nlogn
Worst case: nlogn
Termination: low < high and so low <= (low =high)/2
𝑙𝑜𝑤 < h𝑖𝑔h and so 𝑙𝑜𝑤 ≤ 𝑙𝑜𝑤+h𝑖𝑔h ൗ < h𝑖𝑔h


#### Trees
Trees are also constructed from nodes
**Root**: Single starting point of the tree (Starts at level 0)
**Ancestors**: Parents of the current node
**Siblings**: On the same level as the current node
**Descendants**: Children of the current node
**Leaf**: Node with no children
**Path**: Sequence of nodes (v1, v2 ... vn)
**Subtree**: Any node in the tree along with all of its descendants
**Binary Tree**: A tree with at most two children per node
* Children node are referred to as left and right
* A **perfect** binary tree is one where no node has only one child and all leaves have the same depth (complete and full)
	* Has 2^(k + 1) - 1 nodes, which 2^k are leaves
* Binary tree is **complete** if the leaves are on at most 2 levels, second to bottom level is completely filled in, the leaves on the bottom are as far left as possible
* Binary tree is **full** if the every node has exactly zero or two children
**Height**: The length of the longest path 
**Depth**: Length of the path to the root


Implementation
```cpp
template <typename T>
class Tree {

public:  
// ..., insert, remove, traverse etc.
  private:
    struct Node {
		T data; 
		Node* left;
		Node* right;
	};  
	Node* root;  
// ... and other private functions

};
```


#### Questions
**Full Trees**
Given a full binary tree with n node, it has a height of at least x nodes:
$$ x = log(n+1) - 1 $$
A full tree of height n has at least x nodes:
$$ x = 2*n + 1$$

**Complete Trees**
A complete binary tree of height n, has at least x nodes:
$$ x = 2^n $$
A complete binary tree with n nodes has 
**Perfect Tree**
A perfect binary tree of height n has x nodes:
$$ x = 2^n - 1$$A perfect binary tree with height n, has x leaves:
$$ x = 2^n $$
gf
$$ 2^{n + 1} - 1$$
