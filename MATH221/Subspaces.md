## Subspaces

A collection of points is considered a subset of $\mathbb{R}^n$ if all points in the collection are in $\mathbb{R}^n$. This is different from subspaces.

#### Def. A subspace of $\mathbb{R}^n$ is a subset $V$ of $\mathbb{R}^n$ that satisfies:
- Non Emptiness: the zero vector is in $V$.
- Closure under addition: if $u$ and $v$ are in $V$, then $u+v$ is also in $V$.
-  Closure under scalar multiplication: If $v$ is in $V$ and $c$ is in $\mathbb{R}$, then $cv$ is also in $V$.

A subspace contains the span of any vectors in it, as a consequence of the second and third requirements.

It turns out that a subspace is exactly the same thing as a span, except we don't define it using a specific set of vectors.

### Examples

The solution set of the homogenous system $A\vec{x}=\vec{0}$ is a subspace of $\mathbb{R^n}$, where $A$ is an $m \times n$ matrix.

The solution set of the non-homogenous system $A\vec{x}=\vec{b}$ is **NOT** a subspace of $\mathbb{R^n}$, where $A$ is an $m \times n$ matrix. This is because the zero vector is not in the solution set, since $\vec{b} \neq \vec{0}$. Then it violates the first requirement.

Let $V=\{<a, b> \vert \space ab=0, a,b \in \mathbb{R} \}$. Then $V$ is not a subspace because $<0, 1>$ and $<1, 0>$ are in $V$, but $<1, 1>$ is not in $V$, even though it is the addition of two vectors in $V$. So it violates the second requirement.

We can demonstrate this graphically. Imagine on a graph all of the vectors that satisfy the requirement; we have a bunch of vectors on the $x$ or $y$ axis. So $V$ looks like a cross, but it is not a subspace because it does not include vectors such as $<1, 1>$.

Also consider the set of all vectors where both coordinates are positive. Then this satisfies the first two properties, but not the third one, since it does not contain any vectors going in negative directions.

#### Def. Let $A$ be an $m \times n$ matrix. Then the column space of $A$ is the subspace spanned by the columns of $A$, and the null space of $A$ is the solution set of $A\vec{x} = \vec{0}$.

We denote the column space of $A$ as $\text{Col}(A)$, and the null space of $A$ as $\text{Null}(A)$.

Clearly, $\text{Col}(A) \subset \mathbb{R^m}$, and $\text{Null}(A) \subset \mathbb{R^n}$. The column space is using $m$ because each column has a vector of dimension $m$.