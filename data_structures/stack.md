# Stack

A stack is a linear, last in first out (LIFO) data structure.

# In Memory

In memory, a stack looks like this:

![Image of Stack in Memory](../images/stack_memory.png)

The above diagram of stacks in memory is nearly identical to that of a linked list. A linked list is a common method of implementing a stack due to its O(1) insertion and O(1) deletion. In the diagram, each element in the stack has a value and a reference to the next element. In the above representation, the tail of the linked list is the top of the stack.

# Operations

A stack supports the following operations:

- **push**: adds an item to the top of the stack.
  - O(1), constant time operation. Pushing an element onto the stack is a constant time operation because it inserts a new item to the linked list. This always takes the same number of steps: at the given position, the algorithm changes the previous node's 'next's previous to the inserted node. And, 'next' node to the node to be inserted. Therefore, this always takes the same computation regardless of the size of the stack.
- **pop**: removes an item from the top of the stack.
  - O(1), constant. Similar to push, an element is removed from the linked list as a constant operation. At the given position, the algorithm changes the previous node's 'next' node to the 'next' of the node to be deleted. And conversely, the 'previous' of the 'next' node to the original node's 'previous'.
- **peek**: returns the element from the top of the stack.
  - O(1), constant. This is a constant time operation because a reference to the top of the stack is always available. The top node value is returned in one step.

# Use Cases

A stack is useful when items need to be inserted/available in a LIFO format. This is useful in many situations, most notably when used implicitly in function recursion.

It is not as good when access to the middle of the stack is necessary because as the stack grows, the complexity approaches O(n) complexity.

# Example

```
my_stack = Stack()
my_stack.push(50)
my_stack.push(20)
my_stack.peek()
>>> 20
my_stack.pop()
```

(c) 2018 YOUR NAME. All rights reserved.
