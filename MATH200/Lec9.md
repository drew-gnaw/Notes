## Lecture 9

### Consider the definition for $f(x, y, z)$ to be differentiable at some point $P(a, b, c)$.

Then, similarly to in two dimensions, we can derive a formula for linear approximations and differentials at $P$.

$$L(x, y, z)=f(p)+f_x(p)(x-a)+f_y(p)(y-b)+f_z(p)(z-c)$$

$$df=f_x(p)\text{d}x+f_y(p)\text{d}y+f_z(p)\text{d}z$$

What about tangent planes? Well, a function of three variables has no graph in 3d space. However, it does have level surfaces! Each level surface would be a surface in 3d.

Now consider the point $P(a, b, c)$. There must be one unique surface that contains $P$, since $f$ can only produce one output given $P$ as an input. Then we now do have a plane to talk about! But it is not exactly the same story as a function of two variables. 

We can now go back to imagining a point $Q(x, y, z)$ that moves towards $P$ on the surface. If $Q$ is on the surface, then $f(Q)$ actually stays the SAME as we move it! This is because it is on the level surface, which is always equal to the same thing. This is different from the previous discussion involving functions of two variables.

So if $Q \rightarrow P$ on some level surface containing both points, then $f(x, y, z) - f(a, b, c) = 0$. Thus we have:

$$\lim_{(x,y,z) \rightarrow (a, b, c)}{\frac{<f_x, f_y, f_z>(p) \space \cdot <x-a, y-b, z-c>}{||<x-a, y-b, z-c>||}}$$

In other words, the secant line from $Q$ to $P$ eventually lies in some plane $\pi$ as $Q \rightarrow P$. $\pi$ contains $P$, since all secants go through $P$, and has normal vector given by $<f_x, f_y, f_z>(p)$, assuming that the normal vector is not $\vec{0}$. So the equation for this plane $\pi$, which is the tangent plane to the level surface of $f(x, y, z)$ at $(a, b, c)$.

$$f_x(p)(x-a)+f_y(p)(y-b)+f_z(z-c) = 0$$

---

### Examples

### Q1

What is the tangent plane to $x^2/4+y^2/9+z^2=1$ at $P(1, 0, \sqrt{3/4})$?

Right now, we have an ellipsoid which fails the vertical line test, But we know we are looking at a point on the positive z-axis, so we can just isolate for $z$. Then we could differentiate to find partial derivatives.

But what if we use the new formula? Just consider this egg as the level curve $f=1$ of the function $f(x, y, z)=x^2/4+y^2/9+z^2=1$. Then we have:

$$\begin{cases}f(p)=1 \\ f_x = x/2 \\ f_y = 2y/9 \\ f_z = 2z\end{cases}$$

Then, we can evaluate the derivatives at $p$:

$$\begin{cases} f_x(p) = 1/2 \\ f_y(p) = 0 \\ f_z(p) = \sqrt3\end{cases}$$

So we have:

$$\frac{1}{2}(x-1) + 0(y-0) + \sqrt3(z-\sqrt{3/4}) = 0$$

Which is much easier to do. What is the linear approximation of $f$ at $P$?

$$f(x, y, z) \sim 1 + \frac{1}{2}(x-1) + 0(y-0) + \sqrt3(z-\sqrt{3/4})$$

---

What have we learned? A graph $z=f(x, y)$ is also a level surface for some function $F(x, y, z)$! This can be done by simply rearranging the terms, as follows: $0=f(x, y)-z$.

So the tangent plane formula at $P(a, b, c)$ gives:

$$F_x(p)(x-a)+F_y(p)(y-b)+F_z(p)(z-c)=0$$

