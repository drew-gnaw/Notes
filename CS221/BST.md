## Binary Search Trees

They are trees where every node in the left subtree of a node $v$ has value LESS than $v$, and every node int he right subtree of $v$ has value GREATER then $v$. We say that a BST is "fully ordered".

When we perform an in-order traversal of a BST, the values are printed in ascending order.

Why are they called Binary ***Search*** trees? It's because we can search through them efficiently! Before, we would need to traverse the whole tree to search for a specific value. But with BSTs, we only need to go down ONE subtree! So in the worst case, we need to make $h+1$ comparisons, where $h$ is the height of the tree.


### Searching

I mean, i would write notes about how to search a BST, but cmon you can figure that one out right


### Insertion

Now THIS is a bit tricky! We only insert one node at a time, making sure the BST property holds after every insertion. 

Each time we want to insert a node, we perform a search and see where it ends. If it ends at a left child, we insert there! And if it ends at a right child, we insert also there!


### Removal

Now this is even MORE tricky! After we remove a node, the BST property must hold. Removing a leaf node is fine, but what if we want to remove an internal node? The structure of the tree would be changed!

We can think of three cases:

- The target node has no children
- The target node has one child
- The target node has two children

The first case is easy; just remove it! The second one is also simple, as we can just replace the node to be removed by its child subtree.

What about two children? We could try the same strategy as before, replacing the node with one of its children, but if that child also has two children, then we run into problems.

So let's use the predecessor of the node. The predecessor of a node is the rightmost node in its left subtree, i.e. the node with the largest value in the left subtree. This predecessor cannot have a right child by definition. Then it can replace its ancestor!

However, it could still have a left child. We can deal with this by just following a precedure similar to the one-child case.

You could also do the same thing with a successor (same idea)! But be consistent about which one you are using.

### Efficiency

When we insert nodes in increasing/decreasing order, we get a tree that has a linear structure (its height is $n-1$, where $n$ is the number of nodes). In this case, search can take a long time, still $O(n)$ complexity.

In fact, all three operations take time proportional to the height of the BST. 

In the best case, the tree would be complete. In this case, the height oh the tree is $\lfloor \log(n) \rfloor$, where $n$ is the number of nodes in the tree.

