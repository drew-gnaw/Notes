## Linear Equations

### Integrating factor

We say that a first order ODE is linear if it is of the form 

$$y'+p(x)y=f(x)$$

ODEs of this form can be solved directly. The trick is to consider a function $r(x)\cdot y(x)$, where $r(x)$ is a function to be determined later. The derivative is $r'(x)\cdot y(x)+r(x)\cdot y'(x)$.

Then, we can multiply the ODE by $r(x)$:

$$r(x)\cdot y'+r(x)\cdot p(x)y=r(x)\cdot f(x)$$

Now we make the assumption that $r'(x)=r(x)p(x)$. Then we have

$$r(x)y'(x)+r'(x)y(x)=r(x)f(x)$$
$$(r(x)y(x))' = r(x)f(x)$$
$$\int{(r(x)y(x))' = \int{r(x)f(x)}}$$

Which is separable.

---

In summary, to use the integrating factor method for a linear ODE

$$y'+py=f \text{:}$$
First, compute $r(x)$ by solving $\frac{r'}{r} = f$.

Then, solve $\frac{d}{dx}(ry)=rf$. We get $r(x)y(x)=\int{r(x)f(x)\text{d}x} + C$. Then divide by $r(x)$ to find $y(x)$.

**Example 1.** Solve the initial-value problem

$$\begin{cases} y'=x-y \\ y(1)=1 \end{cases}$$

We rearrange the ODE to $y'+y=x$. Then we find the integrating factor $r(x)=e^{\int1\text{d}x} = e^x$.

Then we have $ye^x = \int^{x}{e^uu\text{d}u}+C$.

Solving, we get $y(x)=x-1+Ce^{-x}$. We can use the initial value given to solve for $C$, and we find that it is $e$.