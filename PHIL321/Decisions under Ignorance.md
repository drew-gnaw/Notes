## Decisions under Ignorance

**Example: Monkfish dinner.** A person is presented with two choices for food: either:

- $a_1$ : Monkfish
- $a_2$ : Hamburger
- $a_3$ : No main course

There are also two chefs.

|Option|Good chef| Bad chef |
|-|---------|----------|
|$a_1$|Good dinner | Terrible dinner|
|$a_2$| OK | OK|
|$a_3$|Hungry | Hungry|

Now we would like to rank these options, instead of using word descriptions.

|Option|Good chef| Bad chef |
|-|---------|----------|
|$a_1$|4 | 1|
|$a_2$| 3| 3|
|$a_3$|2 | 2|

We don't have any information on the probabilities about which chef she will get. It cannot be assumed that it is $50/50$. Now when an agent lacks information, they are making a decision under ignorance (sometimes called a decision under uncertainty).

However, we can still make some decisions. We can begin with pairwise comparisons. If we compare $a_1$ and $a_2$, nothing can be concluded. The same is true for $a_1$ and $a_3$. However, comparing between $a_2$ and $a_3$ tells us that $a_2$ is strictly better than $a_3$. Therefore, even without all the information, we can say that $a_2$ strictly Pareto-dominates $a_3$.

We call the dinner options "**acts**", as in the act that the agent chooses, and the chef possibilities "**states**", as in the state of the world. A pair of an act and a state maps to an **outcome**.

| |$s_1$|$ s_2$ |
|-|---------|----------|
|$a_1$|$O_{11}$ | $O_{12}$|
|$a_2$|$O_{21}$ | $O_{22}$|
|$a_3$|$O_{31}$ | $O_{32}$|

Where $O_{ij}=v(a_i, s_j)$. ($v$ is a function that produces the numerical value)

Now we can say that an act $a_i$ weakly dominates act $a_j$ if and only if $v(a_i, s) \geq v(a_j, s)$ for EVERY state $s$. (This requires at least an ordinal scale).

If we are to define strict dominance, we have the added condition that $v(a_i, s) > v(a_j, s)$ for at least one state $s$.

### The Maximin Principle

Compare the minimal values/worst outcomes  provided by each act, then choose an act whose min/worst is the maximal one among the minimums.

In other words, MAXIMIZE the MINIMUMS.

This principle can be more accurately described as:

$$a_i \succcurlyeq a_j \leftrightarrow \min(a_i) \geq \min(a_j)$$

This principle only requires an ordinal scale! (No difference or ratio needed)

However, there is an issue with ties. Consider the following specification:

| |$s_1$|$s_2$|
|-|-----|----|
|$a_1$|$1|$1000000|
|$a_2$|$1|$2|

This principle does not prefer the strictly better choice, $a_1$. It is indifferent! So we find that the general problem with this principle is that it is too pessimistic (only focuses on the worst case). This principle may be suitable for when we cannot afford risk.

---

#### Lexical Maximin

Designed specifically to break ties. If the worst outcomes are equal, we can choose an act such that the second worst outcome is certain to be as good as possible. Then if that's a tie, go for the third, etc.

If an act has several of the same outcome in different states, then we consider them all at once. For example, if we have the act

| |$s_1$|$s_2$|$s_3$|$s_4$|
|-|-----|----|-|-|
|$a_1$|$1|$3|$1|$4|

Then the first minimum is $1. Then the next is $3, and the third minimum is $4. We do NOT count $1 twice.

We can state this principle as:


$$
\begin{align*}
a_i \succ a_j &\leftrightarrow \text{there exists some positive integer } n \text{ such that } \\
{\min}^{n}{a_i} &> {\min}^{n}{a_j} \text{ and } \\
{\min}^{m}{a_i} &= {\min}^{m}{a_j} \text { for all } m < n
\end{align*}
$$

where $\min^n$ represents the $n^{th}$ minimum.

### The Maximax Principle

Choose the best of the best! We maximize the POTENTIAL!! 🤑🤑🤑💰💰🤑💵🤑

Contrary to the Minimax principle, it can be criticized for being too optimistic! It may be applicable in situations where no serious risk is involved.

### The Optimism-Pessimism Principle (The $\alpha$-index rule)

We consider both the worst and best possible outcomes for each act, according to one's own degree of optimism.

We choose some $\alpha$ between $0$ and $1$ to represent our degree of optimism. If $\alpha = 0$, we are totally pessimistic, meaning we operate identically to the minimax principle. Similarly, if $\alpha = 1$, we are completely optimistic and we operate identically to the maximax principle.

Now if $\max(a_i)$ is the best possible outcome for act $a_i$, and $\min(a_i)$ is the worst possible outcome for act $a_i$, then the value to be maximized is 

$$\alpha\cdot\max(a_i) + (1 - \alpha)\cdot\min(a_i).$$

We can object to this principle in that we ignore all the intermediate values, and only use the min and max.

This principle requires an interval scale since we are taking weighted averages.

### The Minimax Regret Principle

Consider the following scenario:

| |$s_1$|$s_2$|
|-|-|-|
|$a_1$|$1.50|$1.75
|$a_2$|$1|$10000

What if we choose act $a_1$ and it turns out that $s_2$ is true? Then we miss out on $\$10000-\$1.75=\$9998.25$. Let's call the amount of missed opportunity for an act in a state the **regret** for that act and state. So each cell has a regret value. The regret value is always maximized; we compare it to the largest entry in the same column. If we chose the best option, then the regret is $0$.

We can actually construct a **regret table**:

| regret |$s_1$|$s_2$|
|-|-|-|
|$a_1$|$0|$9998.25
|$a_2$|$0.50|$0

Then the max regret for act $a_1$ (highest regret value in a cell in that row) is $\$9998.25$, while the max regret for $a_2$ is $\$0.50$. Finally, we should minimize the regret, so we should choose $a_2$.





