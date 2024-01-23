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

## Slope fields

You know what these are lol

just draw out the slopes at a bunch of points $(y, f(y))$, and you can sketch solutions through the field by following it


## Critical points

**Definition.** Given a autonomonus ODE $y'=f(y)$, the critical points of the ODE are the solutions to $f(y)=0$. This is because in this case, $y'=0$, and $y$ never changes. In a slope field, it looks like a horizontal line.

A **phase line** is used to analyze the function $f(y)$. It contains all the critical points and shows where the function is positive or negative as we change $y$. If $f(y) >0$, then $y'>0$, and the function increases, so we put a right chevron on the line at that point. A similar process is done for left chevrons.

Any given **critical point** can be unstable or stable. An unstable point has the property that the arrows go "away" from it. Thus, it is only stable if we start on it. anywhere else will move away from the point.

If the point is stable, then both arrows point to it. Then it will converge to this point. Finally, some points can be semi-stable, only converging form one side.


