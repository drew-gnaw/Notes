## Induction

You already know what induction is lol, domino thingy

---

**Example 1.** Let $n \in\mathbb{N}$. Prove that for all $n \geq 7$, $n!>3^n$.

Let's use induction. We can show that it is true for a base case, $n=7$. 

**Base case.** $n=7$. Then $7!>3^7$ which is $5040>2187$. This is true. So the case is proven for $n=7$.

**Inductive hypothesis.** Assume that for some $n=k$, we have $k! > 3^k$.

**Inductive step.** Now we will show that $(k+1)!>3^{k+1}$. 

$$(k+1)!=(k+1)k!>8k!>8\cdot 3^k>3\cdot 3^k=3^{k+1}.$$

Then we have proven the inductive step by transitivity. So by the principle of mathematical induction, the property holds for all $n \geq 7$. $\square$

---

**Example 2.** Let $F_n$ represent the $n^{\text{th}}$ fibonacci number. Prove that if $k\in\mathbb{N}$, then $3\mathrel{|}F_{4k}$. In other words, every fourth fibonacci number is divisible by 3.

**Base Case.** $k=1$. Then $3\mathrel{|}F_4$. $F_4=3$. So the base case holds.

**Inductive hypothesis.** $3 \mathrel{|} F_{4k}$ for some $k \geq 1$.

**Inductive step.** Now we will show that $3\mathrel{|}F_{4k+4}$.

We know that $F_{4k+4}=F_{4k+3}+F_{4k+2}=F_{4k+2}+F_{4k+1}+F_{4k+1}+F_{4k}$

$$=F_{4k+1}+F_{4k+1}+F_{4k+1}+F_{4k}+F,_{4k}$$
$$=3F_{4k+1}+2F_{4k}$$

Now since $F_{4k}$ is divisible by 3 by the inductive hypothesis, we can write it as $3a$, where $a$ is an integer. Then we have

$$F_{4k+4}=3[F_{4k+1}+2a]$$

So it is a multiple of $3$. By the principle of mathematical induction, the statement holds for all $k\geq 1$.


