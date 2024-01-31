## Formal definition of a limit

We can say that a sequence of real numbers $(X_n)$ converges to a limit $L \in \mathbb{R}$ when...

$$\forall\epsilon>0, \exists N \in \mathbb{N} \text{ s.t. } \forall n \in \mathbb{N}, |X_n-L| < \epsilon.$$

**Example.** Show that the sequence $X_n=\frac{n}{n^2+1} \rightarrow 0$.

Let $\epsilon > 0$. Then we need to make

$$0 < \left|\frac{n}{n^2+1} - 0\right| < \epsilon.$$

We can choose an "intermediate" value between $\frac{n}{n^2+1}$ and $\epsilon$. $\frac{1}{n}$ works.
