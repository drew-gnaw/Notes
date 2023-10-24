## Wasted space

### Linked Lists

A null-terminated linked-list "wastes" space by storing other information that is NOT data. For example, pointers to the next node and the null termination. So how much space is wasted on null values? Exactly 1! Since each linked-list has a single null termination (an empty list just has a null head pointer).

In a doubly linked list, we usually have two null pointers. The only exception is in the case of an empty list, which again only has 1.

The total amount of space a linked-list wastes on non-data content is $O(n)$. But since it has a constant amount of nulls, it wastes only $O(1)$ space on nulls.

### Arrays

Now... what about arrays? Arrays waste space in that their capacity might exceed the number of elements it has. Then there are empty spaces (wasted spaces). In the best case, it wastes $O(1)$ space, but in the worst case it wastes $O(n)$ space.

### Binary Trees

Each node has its data (non-wasted space), but also has two pointers that could either be null or point to another node. If there are $n$ nodes, then there are $2n$ pointers. We can prove that if a tree has $n$ nodes, then it has $n+1$ null pointers, using induction!

But induction sucks ass! So let's do it as follows:

In a binary tree, every pointer extends from a parent to a child. If the tree has $n$ nodes, it has $n-1$ parent nodes (minus the root). Then it has $n-1$ pointers. But since the number of pointers + the number of nulls $= 2n$, then there must be $n+1$ nulls. $\square$

