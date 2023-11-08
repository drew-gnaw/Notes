## B-Trees

When we had Binary search trees, we could only have two children maximum at each node, since every possible key is either less than or more than the root's key. But what if we assigned two keys to a node? Then we could have three children: one that is less, one that is more, and one that is in between both keys!

An $m$-ary tree is a tree where each node has up to $m$ children, and up to $m-1$ keys. In this way, the tree can still be ordered.

We also assign additional pointers. Each node has pointers to left and right siblings, as well as their parent.

