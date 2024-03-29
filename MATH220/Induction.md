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

**Base case.** $k=1$. Then $3\mathrel{|}F_4$. $F_4=3$. So the base case holds.

**Inductive hypothesis.** $3 \mathrel{|} F_{4k}$ for some $k \geq 1$.

**Inductive step.** Now we will show that $3\mathrel{|}F_{4k+4}$.

We know that $F_{4k+4}=F_{4k+3}+F_{4k+2}=F_{4k+2}+F_{4k+1}+F_{4k+1}+F_{4k}$

$$=F_{4k+1}+F_{4k+1}+F_{4k+1}+F_{4k}+F,_{4k}$$
$$=3F_{4k+1}+2F_{4k}$$

Now since $F_{4k}$ is divisible by 3 by the inductive hypothesis, we can write it as $3a$, where $a$ is an integer. Then we have

$$F_{4k+4}=3[F_{4k+1}+2a]$$

So it is a multiple of $3$. By the principle of mathematical induction, the statement holds for all $k\geq 1$.

---

**Example 3.** Let $f(x)=x\log(x)$, and let $x>0, n\in\mathbb{N}$. Prove that if $n \geq 3$, then 

$$f^{(n)}(x)=\frac{(-1)^n(n-2)!}{x^{n-1}}.$$

**Base case.** Let $n=3$. Then

$$f^{(3)}(x)=\frac{(-1)^3(3-2)!}{x^{3-1}}$$
$$-\frac{1}{x^2}=\frac{(-1)}{x^{2}}$$

So the base case is proven.

**Inductive hypothesis.** Let 
$$f^{(k)}(x)=\frac{(-1)^k(k-2)!}{x^{k-1}}$$ 

for some $n=k$. 

**Inductive step.** Now we will show that 
$$f^{(k+1)}(x)=\frac{(-1)^{k+1}(k-1)!}{x^{k}}.$$

We know that 

$$f^{(k)}(x)=\frac{(-1)^k(k-2)!}{x^{k-1}}.$$

We can differentiate both sides with respect to $x$:

$$f^{(k+1)}(x)=(-1)^k(k-2)!\frac{\text{d}}{\text{d}x}(\frac{1}{x^{k-1}})$$
$$f^{(k+1)}(x)=(-1)^k(k-2)!(1-k)x^{-k}$$
$$f^{(k+1)}(x)=(-1)^{k+1}(k-1)(k-2)!x^{-k}$$
$$f^{(k+1)}(x)=(-1)^{k+1}(k-1)!x^{-k}$$
$$f^{(k+1)}(x)=\frac{(-1)^{k+1}(k-1)!}{x^k}$$

So by the principle of mathematical induction, the statement holds for all $n\geq 3$. $\square$

## Strong induction

Assume all previous past cases instead of just the previous one.

**Example 4.** Prove that every positive integer $n$ can be written as a sum of distinct non-negative powers of $2$.

**Base case.** $n=1$. We see that $n=2^0$. The case is proven.

**Inductive hypothesis.** Assume that for some $n\geq1$, every $1 \leq k \leq n$ can be written as a sum of distinct non-negative powers of $2$. 

**Inductive step.** Now we will show that $n+1$ can be written as a sum of distinct non-negative powers of $2$.

Let $l$ be the largest integer such that $2^l\leq n+1$. Then let $m=n+1-2^l$.

If $m=0$, then $n+1=2^l$. Then $2^l$ is distinct and non-negative, so we are finished.

Otherwise, then $m < n+1$. Then $m$ can be written as a sum of distinct non-negative powers of $2$. Now we also know that $n+1=m+2^l$. So we just have to show that $l$ is distinct from the powers in $m$.

Now we know that $2^l>\frac{n+1}{2}$, since $2^{l+1}>n+1$. Then:

$$-2^l<-\frac{n+1}{2}$$
$$m=n+1-2^l<n+1-\frac{n+1}{2}=\frac{n+1}{2}<2^l.$$

So $m$ is less than $2^l$, and thus its expansion cannot contain $l$. The case is proven, and the proof is complete by the principle of mathematical induction. $\square$