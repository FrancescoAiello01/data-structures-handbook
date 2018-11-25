# AVL Tree

An AVL tree is a self-balancing binary search tree. The tree automatically balances itself when the heights of the children differ by more than 1.

# In Memory

In memory, an AVL tree looks like this:

\[sketch or diagram\]

\[description of diagram\]

# Operations

An AVL tree supports the following operations:

- **retrieval/access/read**: obtain a value stored in the structure. This involves searching the tree for the value.
  - O(log(n)), logarithmic time. Accessing an element in a binary search tree, or in this case, AVL tree requires a tree traversal. These are done in either pre-order, in-order, or post-order and efficiency is constant throughout. Due to the binary and balanced nature of the tree, the efficiency of such traversals in search of an element is, on average, O(log(n)) and therefore would also be the efficiency of retrieval.
- **search**: search for an element stored in the structure.
  - O(log(n)), logarithmic time. Searching a tree can be done in either pre-order, in-order, or post-order traversals. Due to the binary and balanced nature of the tree, on average, searching for an element is O(log(n)).
- **insertion**: insert a new element into the tree.
  - O(log(n)), logarithmic time. AVL trees start off with an insertion like that of a standard binary search tree. But, when the difference in height of children varies by more than 1, the tree self balances. It does this with two base movements, a left or right rotation with 4 possible cases:
  - 1.  Left Left rotation
  - 2.  Left Right rotation
  - 3.  Right Right rotation
  - 4.  Right Left rotation
  - The insert operation efficiency of an AVL tree is the same as a BST being O(h), h = height. However, an AVL tree self-balances, so the height is O(log(n)) and therefore, insert efficiency is O(log(n)).
- **deletion**: remove an element from the tree.
- O(log(n)), logarithmic time. Deletion is very similar to insertion in that the 4 possible cases are the same:
- 1.  Left Left rotation
- 2.  Left Right rotation
- 3.  Right Right rotation
- 4.  Right Left rotation
- To start off, the node is deleted using the BST deletion operation. The difference here is that after one of the above cases is executed, there are parent nodes that may not be balanced and another operation may be required all the way back to the root. Like the insertion operation, the algorithmic complexity is O(log(n)) due to the balanced nature of the tree.

# Use Cases

An AVL tree is useful when there are a large number of nodes and when the values of being inserted don't always vary. For example, inserting sorted values into a tree. A standard BST would degrade into a linked list, but an AVL tree would stay balanced and retain the logarithmic efficiency.

It is not as good when large numbers of values are being inserted and removed frequently. AVL trees have slower insertion/removal, but very fast retrieval. Therefore, they are great as databases that are frequently read, but less effective when values are being constantly changed.

# Example

```
sample code showing creation, and exercising all of the operations
or
a program that doesn't use the structure, and then a version that does
```

(c) 2018 Francesco Aiello. All rights reserved.
