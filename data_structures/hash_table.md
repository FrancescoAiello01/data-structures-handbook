# Hash table

A hash table is an unordered collection of data stored as key:value pairs.

# In Memory

In memory, a hash table looks like this:

![Image of hash table in Memory](../images/hash table_memory.png)

A hashing function is generally (not always) the first step of a hash table in memory. It points to a key, which then provides an index to the value. In the above representation, the collection of values is a doubly linked list.

# Operations

A hash table supports the following operations:

- **access**: finding a value in a hash table by running a value through the hashing function and then searching.
  - O(1), constant. The hashing function provides an index to the array where the value will be found. With array accessing being an O(1) operation, this function shares the complexity. However, in cases where there are key collisions, algorithmic complexity can degrade to O(n) in the worst case.
- **insertion**: add a new value to the hash table.
  - O(1), constant. The value is processed in the hash function which provides an index/key for the value. The new element is then inserted into the given space in one step.
- **deletion**: remove a value from the hash table.
  - O(1), constant. Deletion is as simple as removing an element from the linked list. The complexity of such an operation is covered in detail in the [doubly linked list](double_list.md) file.

# Use Cases

A hash table is useful when storing data as a table. Its O(1) operations are incredibly efficient.

It is not as good when collisions become an issue. Collisions cause computational complexity to increase. Additionally, when attempting to remedy this, hash functions can become very computationally expensive which can further decrease performance.

# Example

```
hash_table = HT()
hash_table.add("50")
hash_table.add("100")
hash_table.return("50")
hash_table.delete("100")
print(hash_table)
>>> {10293: "50"}
```

(c) 2018 Francesco Aiello. All rights reserved.
