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

Let $\mathbb{E}$ be the set of all even integers.

$$\mathbb{E} = \{2n:n\in\Z\}$$

---

**Definition.** For a given set $S$, we write $|S|$ to represent its **cardinality**. For finite sets, this is the number of elements in $S$.

$$|\emptyset| = 0$$
$$|\{1, 2, 3\}| = 3$$
$$|\N|=|\Z|=|\mathbb{Q}| < |\R| = |\mathbb{C}|$$

---

In this course, our goal is to prove that a given mathematical statement is always true.

**Example 2.** Let $T\subseteq N$.

$$T=\left\{ 3x+5y:x,y\in\mathbb{Z}, x, y \geq 0, (x,y)\neq(0,0) \right\}$$

$T$ is a subset of $\mathbb{N}$. There are some elements that are in $\mathbb{N}$ but not in $T$. The set which contains the *difference* of the two sets, i.e. the elements in $\mathbb{N}$ but not in $T$, is denoted $\mathbb{N}\setminus T$.





