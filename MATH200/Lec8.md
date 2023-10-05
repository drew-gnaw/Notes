## Lecture 8

### Topics: Tangent plane, linear approximation, and differentials.

All of these come from the limit definition for $f(x, y)$ to be differentiable at $(a, b)$.

Recall the definition for a multivariable function to be differentiable:

$$\lim_{(x,y) \rightarrow (a, b)}{\frac{f(x, y)-[f(p)+f_x(p)(x-a)+f_y(y-b)]}{\sqrt{(x-a)^2+(y-b)^2}}}=0$$

Tangent plane to the graph of $f(x, y)$ at $(a, b, f(a, b)) = P$, $(a, b) = p$.

Every secant line is perpendicular to the vector $<f_x(p), f_y(p), -1>$.

All limit secant lines are contained in the plane $z=f(p)+f_x(p)(x-a)+f_y(p)(x-b)$. This plane contains the point $P$. The normal vector to this plane is $<f_x(p), f_y(p), -1>$, which is the same as the vector in which all secant lines lie.

Linear approximation of $f(x, y)$ at a point $(a, b) = p$:

$$L(x, y)=f(p)+f_x(p)(x-a)+f_y(p)(x-b)$$

Notice! The tangent plane is just the graph of $L(x, y)$, the linear approximation at point $p$.

Now return to the limit definition of differentiability. The second term in the numerator is just the linear approximation/tangent plane. So we are essentially asking "how fast can the linear approximation approach the real function as $(x, y)$ approaches $(a, b)$?". 

We also need the numerator to approach zero much faster than the denominator. In other words, $|f(x, y)-L(x, y)|$ is small, even in comparison to $\sqrt{(x-a)^2+(y-b)^2}$.

### Differential of $f(x, y)$ at $(a, b)=p$:

Consider the following equation:

$$df=f_xdx+f_ydy$$

$f_x$ and $f_y$, left unevaluated, above are called "the differential of $f(x, y)$". However, if they are evaluated at some point $(a, b)=p$, then they are called "the differential of $f(x, y)$ at $p$".

$dx$ and $dy$ represent infinitesimal changes in $x, y$ from $a, b$. Then $df$ represents the corresponding infinitesimal change in $f(x, y)$.

As long as the changes are NOT infinitesimal, then the equation is actually an approximation, written as such:

$$\Delta f \sim f_x\Delta x + f_y\Delta y$$

Where $\Delta x, \Delta y$ represent changes in $x, y$; written as $x-a$ and $y-b$ respectively. Also, $\Delta f = f(x, y)-f(a, b)$.

So.. we have

$$f(x, y)-f(a, b) \sim f_x(x-a) + f_y(y-b)$$

Which is the same thing as before! (Linear approx/tangent plane)

Back to basics. When we said that $f'(a)=3$, we meant that the slope at $a$ was $3$. We could also write it as such:

$$\frac{df}{dx}=3$$

or, equivalently, 

$$df=3dx$$

Now look at the equation $df=f_xdx+f_ydy$ again. It's essentially the same thing!

### Examples

### Q1

Let $f(x, y)= \pi x^2y$. Find

a) Tangent plane to graph at $(1, 5, 5\pi)$

b) Linear approximation of $f(x, y)$ at $(1, 5)$

c) differential of $f(x, y)$ at $(1, 5)$

For part a, we just need to find the partial derivatives. $f_x(1, 5)=2\pi\cdot 1\cdot 5$ and $f_y(1, 5)=\pi$. So we have that the plane has equation

$$z=5\pi + 10\pi(x-1) + \pi(y-5)$$

The linear approximation is very similar:

$$f(x, y) \sim 5\pi + 10\pi(x-1) + \pi(y-5)$$

And the differential:

$$df=10\pi dx+ \pi dy$$

Note that the differential of a function, without a specified point, just requires you to write out the partial derivatives without evaluating them in the answer.

But what's the point of the differential? We can already get the 'actual change' by evaluating the function at both points:

$$f(x+dx, y+dy)-f(x, y)$$

gives us the exact change! Let's try this on the example:

$$\pi \left[(x^2+2xdx+dx^2)(y+dy)-x^2y\right]$$

(steps omitted because i dont give a fuck)

We end up with 

$$2\pi xydx+\pi x^2dy+\pi (\text{higher order terms of dx, dy})$$

The higher order terms can just be omitted, since they are way smaller than $dx, dy$. So we are left with the differential! 

