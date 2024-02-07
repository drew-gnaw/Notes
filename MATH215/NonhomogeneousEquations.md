## Nonhomogeneous Equations

Now let's study an equation of the form

$$y''+p(x)y'+q(x)y=f(x),$$

Where $f(x) \neq 0$. If it were $0$, then we could use our existing tools to solve it!

Call the left-hand side of the equation $L(x)$. 

**Remark.** $L(x)=0$ gives a homogenous ODE.

**Theorem.** The general solution of $L(y)=f$ is of the form $y=y_p+y_c$, where $y_c$ is the solution of $L(y)=0$ and $y_p$ is a particular solution of $L(y)=f$. We call $y_c$ the *complementary* solution.

Tl;dr: We can split up the work by looking for a particular solution and solving the homogenous equation.

Now I could prove this theorem here, but I don't really want to. Here's my solution to leetcode 70 - climbing stairs instead:

```java
class Solution {
    private Map<Integer, Integer> memo = new HashMap<>();
    public int climbStairs(int n) {
        return fibonacci(n+1);
    }

    private int fibonacci(int n) {
        if (memo.get(n) != null) {
            return memo.get(n);
        }
        if (n == 1 || n == 2) {
            return 1;
        }
        int res = fibonacci(n-1)+fibonacci(n-2);
        memo.put(n, res);
        return res;
    }
}
```

but basically the proof shows that $y-y_p$ is a solution of the homogeneous equation.

### Undetermined coefficients

Basic idea: if $f$ has a certain form, then we can look for a specific form of $y_p$. We also assume that the ODE has constant coefficients. 

Here is a nice table:

|$f(x)$|guess $y_p$ as|
|------|------|
|$P_n(x)=a_0+a_1x+a_2x''$|$x^s(A_0+A_1x+...+A_nx^n)$|
|$P_n(x)=e^{\alpha x}$|$x^s(A_0+A_1x+...+A_nx^n)e^{\alpha x}$|
|$P_n(x)=e^{\alpha x}\cdot\begin{cases} \cos{\beta x}\\\sin{\beta x}\end{cases}$|$x^se^{\alpha x}\cdot(A_0+A_1x+...+A_nx^n)\cos{\beta}x+(B_0+B_1x+...+B_nx^n)\sin{\beta}x$|

Where $s=0, 1, 2$. We choose the smallest of the three that guarantees that no term in $y_p$ is a solution of $L(y)=0$. In other words, we don't want $y_p$ to be a solution of the homogeneous equation.
