## Merge sort

This algorithm takes advantage of the fact that merging two sorted lists is very simple, and the fact that a list with only one element in it is trivially sorted.

The worse-case performance of merge sort is $O(n\log(n))$, which is the best that any comparison-based sort can do. Comparison sorts, well, compare elements and take corresponding action based on this comparison.

### Abstract view of a comparison-based sort

A comparison-based sort receives some unsorted array. Then it takes this array, performs some set of actions on it, and returns a sorted array. It may perform a different set of actions on a different array, but it will always return a sorted array.

### Decision trees

Imagine a decision tree that selection sort follows. It checks if the first element is less than the second element. Then, based on this result, it will go down two more paths. Each of these paths will have two children, and so on until EVERY path leads to a sorted list.

If we consider an array of size $n$, there are $n!$ ways to arrange $n$ elements in it. In other words, there are $n!$ possible permutations. Then, there MUST be $n!$ different paths in the decision tree, or else two different input arrays would be given the exact same set of actions, which necessarily means that one of these arrays is not sorted properly.

Theoretically, what is the shortest tree with $n!$ nodes? For example, we can construct a tree with 4 leaves in several ways, but the shortest tree will have height 3.

A "perfect" tree is one that is perfectly symmetric and where adding a single node anywhere would increase the height of the tree. A perfect tree must have $2^{k+1}-1$ nodes, while there are $2^k$ leaf nodes. Let's go back to considering the tree with $n!$ different paths, which are leaf nodes. If $2^k=n!$, then $k = \left \lceil{\log_{2}{n!}} \right \rceil$. Note that we use the ceiling function since $k$ is an integer, and we are not sure whether the log will return an integer. Then we use the properties of logarithms:

$$\log{n!}=\log{n}+\log{(n-1)}+...+\log{1}$$

Then, consider the part of the above sequence up to $\log{(n/2)}$. Each of these terms is larger than or equal to $\log{(n/2)}$. Thus, we can say:

$$\log{n!} \geq \frac{n}{2}\log{n/2}$$

So the longest path cannot be shorter than this number. Thus every comparison-based sort at best performs in $O(n\log n)$ in the worst case.