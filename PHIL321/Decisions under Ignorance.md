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