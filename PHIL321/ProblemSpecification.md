### Some issues with Problem Specification

- The issue of proper description of states.
    - Imagine you are offered a choice to bet on either Team A or Team B. If you bet on Team A and they win, you get $50. Similarly, for team B, you get $30. If you bet wrong, you lose $20 either way. Who whould you bet on?
    - Its not immediately clear. We don't know what the chances of A or B winning are. It is because we are thinking of the question in terms of A or B winning. A wins or B wins are our two states. But what if we use the states "I win my bet" and "I lose my bet"? then the probability is accounted for in the problem specification. However, this specification is not "proper".

- 

### Dominance principle

**A (weak/Pareto-) Dominance principle:** An act A weakly (Pareto-) dominates another act B if, in a state-in-state comparison, A yields outcomes that are at least as good as those yielded by act B, and, in some cases they are even better.

**Principle:** Avoid acts which are dominated.

Sneak peek: Strong dominance means that A is strictly better than B.

### Notation

We introduce some notation for preference. If $O$ is a set of options, and we have two options $x, y \in O$,

$x \succcurlyeq y$ means that an agent has a weak preference for $x$ over $y$. The symbol is distinct from $\geq$ as preferences cannot be compared arithmetically.

We also have an equivalence. $x \sim y$ means that $x$ is always exactly as good as $y$. In other words, $x \succcurlyeq y$ and $x \preccurlyeq y$.

A score function maps from options to a number: $O \rightarrow \mathbb{R}$. Then we have
$$\text{score}(y) \geq \text{score}(x) \equiv y \succcurlyeq x$$

### Properties of weak preference relations

- The property of totality: Given any two options, either $x \succcurlyeq y$ or $y \succcurlyeq x$. Basically, any two options can be compared.

- The property of reflextivity: For any option $x$, $x \succcurlyeq x$.

- The property of transitivity: For some options $x, y, z$, if $x \succcurlyeq y$ and $y \succcurlyeq z$, then $x \succcurlyeq z$.

We call weak preference relation **rational** if it satisfies all three of the above properties. Given a finite set of options, it is always possible to make a score function that represents the preference relation.

