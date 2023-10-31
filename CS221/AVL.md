### AVL Trees

---

AVL Trees are BSTs with an extra property: basically, they are "balanced". Specifically, each node's subchildren's height differ at most by 1. When an insertion causes an excessive height difference, we "rebalance" the tree via a `rotation`.

Now, by enforcing this "balanced" property, the height of a AVL Tree containing $n$ nodes has $O(\log{n})$ height.

### Rotations

Think of a rotation as changing which node is the parent. For example, if we had a tree with the structure

```
    x
   / \
  y   z
 / \ / \
 a b c d
```

Then a rotation to the left would "shift" `x` to the left. Then z becomes the parent. But then `z` would have three children (`x`, `c`, and `d`). So the middle child, `c`, is given to `x` instead.
```
       z
      / \
     x   d
    / \
   y   c
  / \
 a   b
```

Usually, though, we want rotations to be used to "balance" trees.

--- 

In an AVL, we need to keep track of the `balance` of the Tree. We might implement this by introducing a new enum called `balance_type`, which can be `left-heavy (-1)`,` balanced (0)`, or `right-heavy (1)`. Then each node carries this information.

When a node is `left-heavy`, its left subtree is taller.

### Imbalances

There are 4 types of imbalances: LL, LR, RL, RR.

LL and RR imbalances can be resolved by simply rotating the top node:

```
     c
    /
   b
  /
 a
```
(Rotation at the top node, `c`)
```
    b
   / \
  a   c
```

In the LR and RL cases, we rotate the middle node first, which brings it to the LL/RR case. Then we can just rotate again.

### Insertion

---

We insert a node similarly to how we do it in a BST. However, recall that each node has a "balance" associated with it!

When we finish inserting a node, its balance is always 0. But the addition of this node might affect the balance of its parents. So we travel back up the tree, changing the balance of each parent accordingly.

Insertion can be done in $O(\log{n})$ time! This is because the insertion is done in log time (thanks to the AVL balance guarantee), and we do at MOST two rotations, each of which are done in constant time.

There is only one fix maximum required for every insertion.

### Removal

---

We perform removal first by similarly using the predecessor, but this time we just overwrite the data in the node instead of relinking pointers.

When we look for imbalances, we look from the node that was removed. So in the case of predecessors, we look staring from the original predecessor node.

BST removal, finding the predecessor, and the number of fixes we potentially have to make are all $O(\log{n})$. So removal can be done in $O(\log{n})$ time.

### However...

---

We cannot guarantee that nodes in a AVL Tree are stored close to each other in memory. Although each process is $O(\log{n})$ time, what really dominates runtime is `disk accesses`, which occur when we need information that isn't on the CPU.

Imagine we had a HUUUGE Tree. It's so big that it can't fit on the RAM! So therefore, some of it must be stored on disk.


