# Binary Search Tree

A binary search tree (BST) is a node-based tree that dictates the position of insertion based on a comparison of children and parent node values (parent value > child value = left insertion, parent value < child value = right insertion).

# In Memory

In memory, a BST looks like this:

![Image of Array in Memory](../images/bst_memory.png)

A BST is very similar to a linked list in memory. Each element has link to a parent, child and value.

# Operations

A BST supports the following operations:

- **retrieval/access/read**: obtain a value stored in the structure. This involves searching the tree for the value.
  - O(log(n)), logarithmic time. Accessing an element in a binary search tree requires a tree traversal. This is done in either pre-order, in-order, or post-order and efficiency is constant throughout. In a balanced tree, this process is logarithmically efficient, but can degrade if balance is lost.
- **search**: search for an element stored in the structure.
  - O(log(n)), logarithmic time. Searching a tree can be done in either pre-order, in-order, or post-order traversals. In a balanced BST, efficiency is logarithmic, but similarly to retrieval, efficiency can degrade if balance is lost.
- **insertion**: adding a new element to the BST.
  - O(log(n)), logarithmic efficiency. Insertion into a BST is logarithmic, but efficiency is dependent on height. When inserting, the value of the child is compared to the parent (starting at the node). If the child value is less than the parent, it is inserted to the left. If the child value is greater than the parent, it is inserted to the right. If the space to the left or right is not empty, the comparison continues until an empty space is found. This process is logarithmic as long as the tree stays reasonably balanced. A tree can degrade into the O(n) efficiency of a linked list if balance is not retained.
- **deletion**: remove an element from the tree.
  - O(log(n)), logarithmic efficiency. Removing an element from a BST has three possible cases:
  - 1.  If a node is a leaf, the element is simply removed.
  - 2.  If a node has only one child, the child is copied to the node and the child is deleted.
  - 3.  If a node has two children, a successor must be found. This can be done through in-order traversal. The in-order successor is copied to the node and the in-order successor is deleted.
  - Similarly to all the other operations, logarithmic efficiency is only retained as long as the tree stays relatively balanced.

# Use Cases

A BST itself is not particularly useful in any situation unless values will always come in such a way that the tree will balance itself. However, BSTs are an excellent building block for other data structures that maintain the balance and therefore take advantage of the logarithmic efficiency.

# Example

Example implementation of a BST in Python.

```
class BinarySearchTree:

    def __init__(self, value = None):
        self.value = value
        self.left = None
        self.right = None

    def insert(self, child):
        if self.value > child.value:
            if self.left == None:
                self.left = child
            else:
                self.left.insert(child)
        else:
            if self.right == None:
                self.right = child
            else:
                self.right.insert(child)

    def find(self, searchee):
        if searchee == self.value:
            return True
        if self.value > searchee:
            if self.left is None:
                return False
            return self.left.find(searchee)
        else:
            if self.right is None:
                return False
            return self.right.find(searchee)

    def in_order_traversal(self, callback):
        if self.left is not None:
            self.left.in_order_traversal(callback)
        callback(self.value)
        if self.right is not None:
            self.right.in_order_traversal(callback)

    def pre_order_traversal(self, callback):
        callback(self.value)
        if self.left is not None:
            self.left.pre_order_traversal(callback)
        if self.right is not None:
            self.right.pre_order_traversal(callback)

    def post_order_traversal(self, callback):
        if self.left is not None:
            self.left.post_order_traversal(callback)
        if self.right is not None:
            self.right.post_order_traversal(callback)
        callback(self.value)

    def delete(self, deletee):
        if self.right is not None and self.right.value == deletee:
            if self.right.left is None:
                self.right = self.right.right
            elif self.right.right is None:
                self.right = self.right.left
            else:
                successor = self.right.right
                while successor.left is not None:
                    successor = successor.left
                self.right.delete(successor.value)
                self.right.value = successor.value
        elif self.left is not None and self.left.value == deletee:
            if self.left.right is None:
                self.left = self.left.left
            elif self.left.left is None:
                self.left = self.left.right
            else:
                successor = self.left.left
                while successor.right is not None:
                    successor = successor.right
                self.left.delete(successor.value)
                self.left.value = successor.value
        else:
            if deletee > self.value:
                if self.right is not None:
                    self.right.delete(deletee)
            else:
                if self.left is not None:
                    self.left.delete(deletee)
```

(c) 2018 Francesco Aiello. All rights reserved.
