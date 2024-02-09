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
|$P_n(x)=a_0+a_1x+a_2x^2+...+a_nx^n$|$x^s(A_0+A_1x+...+A_nx^n)$|
|$P_n(x)=e^{\alpha x}$|$x^s(A_0+A_1x+...+A_nx^n)e^{\alpha x}$|
|$P_n(x)=e^{\alpha x}\cdot\begin{cases} \cos{\beta x}\\\sin{\beta x}\end{cases}$|$x^se^{\alpha x}\cdot(A_0+A_1x+...+A_nx^n)\cos{\beta}x+(B_0+B_1x+...+B_nx^n)\sin{\beta}x$|

Where $s=0, 1, 2$. We choose the smallest of the three that guarantees that no term in $y_p$ is a solution of $L(y)=0$. In other words, we don't want $y_p$ to be a solution of the homogeneous equation. So we would try $s=0$ first, and if $y_p$ is a solution to the homogenous equation, we would try $s=1$, etc.

**Example 1.** Solve $y''-9y=-2e^{3x}$

Lets find $y_c$ first. We set $y''-9y=0$. Then by reduction of order, $x^2-9=0$. Thus $r=\pm3$, and $y_c=(C_1e^{3x}+C_2e^{-3x})$.

Now let's find $y_p$. We can use the above table to guess its form:

$$y_p=x^s(A_0)e^{3x}.$$

Let's try $s=0$ first. We get that $y_p=A_0e^{3x}$. But this is a solution to the homogenous equation!

So we try $s=1$. Now we get $y_p=xA_0e^{3x}$. If you differentiate this $y_p$ twice, you will find that it is not a solution to the homogenous equation. Now we can plug it back in:

$${y_p}''=9A_0xe^{3x}+3A_0e^{3x}+3A_0e^{3x}$$

So

$$9A_0xe^{3x}+6A_0e^{3x}-9A_0xe^{3x}=-2e^{3x}$$

And thus we find that $A_0 = -1/3$. Then we conclude that the solution is of the form

$$y=C_1e^{3x}+C_2e^{-3x}-\frac{1}{3}xe^{3x}.$$


**Remark.** If we have $L(y)=ay''+by'+cy=f_1+f_2$, we can solve it as $y=y_c+y_1+y_2$, where

$$\begin{cases}
y_c \text{ is a complementary solution}\\
y_1 \text{ is a particular solution for } L(y)=f_1\\
y_2 \text{ is a particular solution for } L(y)=f_2.
\end{cases}$$

Basically, we can "split up" the right-hand side and solve it separately, which is useful if it is not a "guessable" function right away. For example, if we were to solve 

$$y''-y'+y=e^{x/2}+2\sin{3x},$$

we'd like to split up the right-hand side so that we could use the table to guess each function separately.