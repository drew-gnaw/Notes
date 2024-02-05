## Formal definition of a limit

We can say that a sequence of real numbers $(X_n)$ converges to a limit $L \in \mathbb{R}$ when...

$$\forall\epsilon>0, \exists N \in \mathbb{N} \text{ s.t. } \forall n \in \mathbb{N}, |X_n-L| < \epsilon.$$

**Example 1.** Show that the sequence $X_n=\frac{n}{n^2+1} \rightarrow 0$.

Let $\epsilon > 0$. Then we need to make

$$0 < \left|\frac{n}{n^2+1} - 0\right| < \epsilon.$$

We can choose an "intermediate" value between $\frac{n}{n^2+1}$ and $\epsilon$. $\frac{1}{n}$ works. So we have:

$$0 < \frac{n}{n^2+1} < \frac{1}{n} < \epsilon.$$

Now Set $N=\lceil\frac{1}{\epsilon} \rceil$, which implies $N \geq \frac{1}{\epsilon}$. Then if $n>N$, then $\frac{1}{n} < \frac{1}{N}$. Then we have $\frac{1}{N} \leq \frac{1}{1/\epsilon}=\epsilon$. So $\frac{1}{n} < \epsilon$. Then the proof is complete by transitivity.

**Remark.** If $0 \leq x_n \leq b_n$, and $b_n \rightarrow 0$, then $x_n\rightarrow 0$. 

**Definition.** Let $A \subseteq \mathbb{R}$ and let $f: A \rightarrow \mathbb{R}$ be a function. We say that $f(x)$ has limit $L$ as $x \rightarrow a$ and write $\lim_{x\rightarrow a}{f(x)} = L$ when

$$\forall \epsilon > 0, \exists \delta>0 \text{ such that if } |x-a|<\delta, \text{ then }|f(x)-L| < \epsilon.$$

Basically, this statement is saying that given an epsilon, which represents some "tolerance" for change in the function output, we should be able to provide a delta, which represents a small change in the input, such that the small change in the input does not result in "breaking" the tolerance.

**Example 2.** Prove that $\lim_{x\rightarrow 1}(5x+3)=8$.

Lets begin with some scratchwork. We consider some $\epsilon > 0$. Then we need $x$ close to 1 so that $|(5x+3)-8| < \epsilon$, or $5|x-1| < \epsilon$. 

Now the end goal is to choose some $\delta$ such that if $|x-1|<\delta$, then $5|x-1|<\epsilon$. Here, it is trivial to conclude that $\delta = \epsilon/5$. So let's write a formal proof.

$\textbf{Proof.}$ Let $\epsilon > 0$ and set $\delta = \epsilon/5$. Now let $x \in \mathbb{R}$ such that $|x-1|<\delta$. Then $|(5x+3)-8| = 5|x-1|<5\delta=\epsilon. \square$

**Example 3.** Prove that $\lim_{x\rightarrow 2}x^2=4$.

Again, let's start with scratchwork. We conside $\epsilon > 0$, and need $|x^2-4|<\epsilon$. 

We want to show that if $|x-2| < \delta$, then $|x^2-4|<\epsilon$. We might try to factor the function:

$|x-2|<\frac{\epsilon}{|x+2|}$. Can we just set the right hand side as delta? No! This is because delta should not depend on $x$, only on $\epsilon$.

Now this proof only really cares about what happens as $x$ goes to $2$. In fact, we might require that $x$ is within some threshold of $2$, like maybe it's at most $1$ away. Lets say that $|x-2|\leq1$. The choice of $1$ was arbitrary, but it is reasonable so that we can ensure that $x$ is positive. This also means that delta is bounded below $1$.

We can rearrange to get $3\leq x+2\leq 5$. So then 

$$|x^2-4|=|x-2||x+2|\leq5|x-2|<5\delta$$

So we just need to set $\delta=\epsilon/5$, and then $5\delta \leq \epsilon$ and then $|x^2-4|<\epsilon$ by transitivity, as required.

Now in the example, we found a $|x-2|$ in the factored form of the function. However, a pesky $|x+2|$ was sitting there. We *bounded* the value of that second term, so that we could get rid of it (by saying that it is at most 5).

However, now the proof would start by declaring that $\epsilon>0$ and then setting $\delta$. While epsilon is considered to be a small number, we consider ALL epsilons $> 0$, which includes real big ones. Then if $\delta = \epsilon/5$, and $\epsilon$ is really big, then $\delta$ would be greater than $1$, which violates our earlier statement. So we need to "cap" delta:

$\delta = \min{(1, \epsilon/5)}$.



