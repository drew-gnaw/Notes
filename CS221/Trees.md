## Trees

Trees are defined similarly to Linked lists, but each node can point to several nodes. The connection between two nodes is called an edge, and a Tree is connected such that there is a path to every node in it. 

We commonly use familial descriptions to talk about nodes:
-  A node is a parent to another node if there is one edge between them. 
- A node is an ancestor to another node if there is some way to get from ancestor to descendant by only moving down the tree.
- A path is a sequence of nodes, where each node is the parent of the next.
- A node is a leaf node if it has no children.

We can classify trees as n-ary trees based on the maximum number of descendants any node in the tree has. (Binary tree, ternary tree...)

The height of a node $v$ is the length of the longest path from $v$ to a leaf node, and the depth of a node $w$ is the length from the root to $w$. We can think of the root of the tree to be "level $0$", and each child is one level higher.

In a Tree, each node can only have ONE parent! The root has no parents.

### Binary trees

Since there are only two children, we usually just refer to them as "left" and "right".

We say that a Binary Tree is "perfect" if every node has either $0$ or $2$ children, and every leaf has the same depth. Basically, adding another node would increase its height.

Therefore, a perfect tree has $2^{h+1}-1$ nodes, $2^h$ of which are leaf nodes. $h$ is the height of the Tree.

We say that a Binary Tree is "complete" if every leaf node is at most on two different levels, the second-to-bottom level is completely filled in, and every leaf on the bottom level is as far to the left as possible.

We say that a Binary Tree is "full" if every node has $0$ or $2$ children.

The implementation of a Tree is very similar to that of a linked list, but we just have two pointers for the two children.

