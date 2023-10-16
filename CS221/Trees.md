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

## Traversals

### In-order

In order traversals have the form 

```cpp
void inOrder(Node* nd) {
    if (nd != nullptr) {
        inOrder(nd->left);
        visit(nd);
        inOrder(nd->right);
    }
}
```

This visits the nodes from left to right. In a BST, it would print them out from smallest to largest.

### Pre-order

These are very similar, but we visit the node before its children.

```cpp
void preOrder(Node* nd) {
    if (nd != nullptr) {
        visit(nd);          // visit the node before its children!
        inOrder(nd->left);
        inOrder(nd->right);
    }
}
```

This is useful when we are dealing with creating trees. We need to make the node first, then deal with its children. It's also good for copying trees.

### Post-order

Honestly if you can't infer what post-order is at this point it might be over...

```cpp
void postOrder(Node* nd) {
    if (nd != nullptr) {
        inOrder(nd->left);
        inOrder(nd->right);
        visit(nd);
    }
}
```

This is useful for deallocation! We can be sure that the children are deallocated before we remove the node itself.

Tip: You can trace around the tree counter-clockwise, and whenever you pass by a node on its (left/under/right), write out its value. Then you have the order of (Pre-order/In-order/Post-order) traversals.

Visiting a node can be doing whatever. Maybe we are copying the node, or getting its value, etc.

### Recursive calls

Imagine we wanted to write a function that gets the height of a tree, given its root. We can do this by adding one to the maximum height of either subtree. Recursion!! (remember the base case: if the head is null, the height is -1). This approach uses a Post-order traversal, since we visit both children before the node itself. (The visit for the current node is us adding 1 to the maximum height).

### Iteration?

We CAN traverse a tree iteratively. This makes use of a stack ADT, as follows:

```cpp
void prePrint(Node* nd) {
    Stack<Node*> st;
    if (nd != NULL) {
        st.push(nd);
    }

    while (!st.isEmpty()) {
        Node* p = st.peek();
        st.pop();
        cout << p->data << endl;
        if (p->right != NULL) {
            st.push(p->right);
        }
        if (p->left != NULL) {
        st.push(p->left); // we push left in last so that it is on top of the stack
        }
    }
}
```

This iteratively traverses a tree. The space complexity of this algorithm depends on the height of the tree.

Now, what if we replace the stack with a queue? Then we visit sibling nodes one after the other! This results in a level-order traversal, which traverses the nodes from top to bottom. In this case, the space complexity depends on the width of the tree.

Traversal of a tree, if each visit takes constant time, is generally linear time.

 