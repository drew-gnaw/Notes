## Sets

A **Set** is loosely defined as a "collection of objects". We usually use capital letters for them.

**Example.** $\N = \{1, 2, 3, ... \}$

The statement $x \in A$ means "$x$ is an element of $A$". Similarly, $x \not\in B$ means "$x$ is not an element of $B$".

$\emptyset$ is the empty set; it contains no elements. A set that contains the empty set is NOT the same as the empty set itself.

But this whole definition so far is still vague. We want a PRECISE definition for sets. So, we turn to set builder notation.

---

### Set builder notation

Sometimes, we can "suggest" a way to build a set. Take the following set for example:

$$A = \{2, 4, 6, 8, ..., 16, 18 \}$$

It is pretty clear what belongs in the omitted part. But sometimes it is not so clear. 

$$B = \{3, 5, 7, ... \}$$

Is it a set of all odd numbers greater than 3? or all odd primes? who knows!

Set builder notation solves this by providing a way to deduce all the elements in a set. For example,

$$S = \{1, 4, 9, 16, ... \}$$

is a set of all perfect squares. Set builder notation writes this as 

$$S = \{n^2: n \in \Z\}$$

So as to remove any ambuguity.

For example, set builder notation can be used to define the set of rational numbers:

$$\mathbb{Q} = \{\frac{a}{b} : a \in \Z, b \in \N\}$$

The left side of the colon is a function, and the right side specifies the domain.

---

Let $\mathbb{E}$ be the set of all even integers.

$$\mathbb{E} = \{2n:n\in\Z \}$$

