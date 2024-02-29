***
**Binary Search Tree**
* A binary tree except all elements are sorting according to size
* Left is smaller right is larger

**BST Search**
* If the target is less than the value in the node search its left subtree
* If the target is greater than the value in the node search its right subtree
* Otherwise return true
* Worst case: height of the tree + 1


#### Types of traversal

```
        1
       / \
      2   3
     / \ / \
    4  5 6  7
   / \
  8   9
```
**Preorder traversal O(n)**
* Starts from the root and then recursively traverses the left subtree followed by the right subtree
* (Prints as it is going down)
* Order: 1, 2, 4, 8, 9, 5, 3, 6, 7

**Postorder traversal**
* Traverse left sub tree, traverse right tree, node
* (Goes all the way down before print)
* Order: 8, 9, 4, 5, 2, 6, 7, 3, 1

**In order traversal O(n)**
* Traverse its left sub tree,  Node, Traverse to the right tree
* Order: 8, 4, 9, 2, 5, 1, 6, 3, 7

**Level-order traversal O(n)** 
* Visits nodes level by level from left to right starting from the root
* Order: 1, 2, 3, 4, 5, 6, 7, 8, 9