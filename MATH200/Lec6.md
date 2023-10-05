## Lecture 6

### Distance between two lines
We can find the smallest distance between two lines using the projection formula, but also consider this:

$$\begin{cases} \vec{PQ} \cdot \vec{v_1} = 0 \\ \vec{PQ} \cdot \vec{v_2} = 0 \end{cases}$$

When $P$ is a variable point on $L_1$ and $Q$ is a variable point on $L_2$. Essentially, we are finding a line that is perpendicular to both lines, which will be the shortest line between two points.

### Distance from point to plane

Consider a plane $\pi$ and a normal vector $\vec{n} = <a, b, c>$, and a point $P(x_0, y_0, z_0)$. on the plane. Then consider some point $Q(x, y, z)$, and now we want to find the distance from $Q$ to $\pi$. We can project the vector $\vec{PQ}$ onto $\vec{n}$, which will give the distance between $Q$ and $\pi$.

$$Dist(Q, \pi) = ||proj_{\vec{n}}{\vec{PQ}}||$$
$$Dist(Q, \pi) = \frac{|\vec{PQ} \cdot \vec{n}|}{||\vec{n}||}$$

### Differentiation of multivariable functions

Recall the graph of $f(x,y)=x^2+y^2+1$.

Consider two lines $L_1, L_2$, where $L_1$ lies tangent to the $x=1$ trace and $L_2$ lies tangent to the $y=1$ trace.

In particular, $L_1$ is the limit of secant lines from $P(1, 1, 3)$ to $Q(1, y, f(1, y))$. $L_2$ is similar, but it is the limit of secant lines from $P(1, 1, 3)$ to $Q(x, 1, f(x, 1))$. 

Let $L_{xy}$ be secant to the graph from $P(1, 1, 3)$ to some general point $Q(x, y, f(x, y))$. What is the direction vector for $L_{xy}$?

$$\vec{v_{xy}} = \vec{PQ} = <x-1, y-1, f(x, y) - 3>$$

Now as $Q$ approaches $P$, what do we get? The length is zero, but what we really care about is the direction. So we will normalize the vector, which gives it a unit length 1.

$$\frac{\vec{PQ}}{||\vec{PQ}||} = \frac{<x-1, y-1, f(x, y) - 3>}{\sqrt{(x-1)^2+(y-1)^2+(f(x, y) - f(1, 1))^2}}$$

So will the vector approach a limit as $(x, y) \rightarrow (1, 1)$? No! It depends on how we approach it. For example, if we held $x = 1$ and moved $y$ towards 1, we would get a different line than if we had held $y$ constant.

HOWEVER! In this case, although we have several possible secant lines, they are all contained within one plane. In three dimensions, we say that **a function is differentiable at (x, y) if every possible secant line is conatined in some plane $\pi$**. This is equivalent to asking if for any $\vec{v_{xy}}$, $\vec{v_{xy}} \cdot \vec{n} = 0$ as $(x,y) \rightarrow (1, 1)$. Or, equivalently,

$$\frac{f(x, y) - (f(1, 1)+2(x-1)+2(y-1))}{\sqrt{(x-1)^2+(y-1)^2+(f(x, y) - f(1, 1))^2}} \rightarrow 0$$
as $(x, y) \rightarrow (1, 1)$.

Consider the limit definition in 2d. 

$$\lim_{x\rightarrow a}{\frac{f(x)-f(a)}{x-a}} = L$$
$$\lim_{x\rightarrow a}{\frac{f(x)-f(a)}{x-a}} = \frac{L(x-a)}{(x-a)}$$

### Limits of multivariable functions

$$\lim_{(x, y) \rightarrow (a, b)}{f(x, y)} = L$$
means "$f$ is defined around $(a,b)$, but possibly not at $(a,b)$, and $f(x, y)$ can be as close to $L$ as we like by taking $(x, y)$ sufficiently close to $(a, b)$".

In 2 dimensions, $x$ could only approach a value in two ways: from the left or from the right. But in three dimensions, a point $(x, y)$ can approach another point $(a, b)$ in infinitely many ways. The limit will approach $L$ regardless of which path was taken.

### Examples

### Q1

$$\lim_{(x, y) \rightarrow (1, 1)}{(x^2+\frac{e^{xy}}{y^2})}$$

Nothing is stopping us from just plugging in $x = y = 1$. So we get that the limit is $1+e$.

### Q2

$$\lim_{(x, y) \rightarrow (0, 0)}{\frac{x^2y}{x^2+y^2}}$$

The trick to solving this problem lies in using polar coordinates.

$\begin{cases}x=r\cos(\theta) \\ y=r\sin(\theta)\end{cases}$

So we have:

$$\lim_{r \rightarrow 0}{\frac{r^3\cos^2{\theta}\sin{\theta}}{r^2}}$$
$$\lim_{r \rightarrow 0}{r\cos^2{\theta}\sin{\theta}}$$

And since cos and sin are bounded, we can observe that the whole expression will go to $0$ as $r \rightarrow 0$.

### Q3

$$\lim_{(x, y) \rightarrow (0, 0)}{\frac{xy}{x^2+y^2}}$$

Same idea as last time, now we have:

$$\lim_{r \rightarrow 0}{\frac{r^2\cos{\theta}\sin{\theta}}{r^2}}$$
$$\lim_{r \rightarrow 0}{\cos{\theta}\sin{\theta}}$$

### Q4

$$\lim_{(x, y) \rightarrow (0, 0)}{\frac{xy^2}{x^2+y^4}}$$

The same trick doesn't work as well, as we can't cancel the $r$'s too cleanly. Let's do this another way:

Let's assume we approach the point $(0, 0)$ along a straight line $y=mx$. Then we replace all instances of $y$ with $mx$.

$$\lim_{x \rightarrow 0}{\frac{x(mx)^2}{x^2+(mx)^4}}$$
$$\lim_{x \rightarrow 0}{\frac{xm^2}{1+m^4x^2}}$$

We know this approaches $0$ since the denominator dominates.

HOWEVER! Now let us approach $(0, 0)$ along a parabola. In other words, we approach the origin along $x=y^2$.

$$\lim_{y \rightarrow 0}{\frac{y^2y^2}{y^4+y^4}}$$
$$\lim_{y \rightarrow 0}{\frac{y^4}{y^4+y^4}}$$
$$=\frac{1}{2}$$

So the limit DNE! (since we get different limits for different paths of approach).