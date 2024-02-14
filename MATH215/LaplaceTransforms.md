## Laplace Transforms

**Motivation.** We want to define another representation of a function, that will make solving some ODEs convenient.

The Laplace Transform is an integral transform of a function, i.e.

$$\int_\alpha^\beta{K(s,t)f(t)\text{d}t}.$$

We call $K(s,t)$ a kernel and it is specific to the transform.

**Definition.** The Laplace Transform $f$, denoted $\mathscr{L}\{f()t\}$ or $F(s)$, is defined by $\mathscr{L}\{f()t\} = F(s)= \int_0^\infty{e^{-st}f(t)\text{d}t}$. We assume that the integral is well-defined.

So in the context of Laplace Transforms, the kernel is an exponential function.

**Example 1.** What is the Laplace Transform of $f(t)=1$, assuming $s>0$?

We have

$$\int_0^\infty{e^{-st}\text{d}t}$$
$$=\left[\frac{-e^{-st}}{s} \right]_0^\infty$$
$$=\frac{1}{s}.$$

**Example 2.** We define the *Heaviside function*, $u(t)$, as

$$u(t)=\begin{cases}
1 \text{ if } t > 0\\
0 \text{ if } t < 0
\end{cases}$$

What is $\mathscr{L}(\{u(t-a)\})$, where $a>0$?

Then we have 

$$u(t-a)=\begin{cases}
1 \text{ if } t > a\\
0 \text{ if } t < a
\end{cases}$$

$$\mathscr{L}(\{u(t-a)\})=\int_0^\infty{e^{-st}u(t-a)}$$
$$=\int_0^a{e^{-st}\cdot 0}+\int_a^\infty{e^{-st}\cdot 1}$$
$$=\frac{e^{-sa}}{s},$$

for $s>0$.

Now we will see a table that contains common Laplace Transforms for elementary functions. (You could and should do these as an exercise. You can use integration by parts!)

|$f(t)$|$F(s)$|
|-|-|
|$c$|$\frac{c}{s}$ for $s>0$|
|$t^n$|$n!/s^{n+1}$|
|$e^{at}$|$1/s+a$|
|$\sin(wt)$|$w/(s^2+w^2)$|
|$\cos(wt)$|$s/(s^2+w^2)$|
|$u(t-a)$|$e^{-as}/s$|

**Remark.** We say that $f(t)$ is defined over a *time domain*, where $t$ is the time variable, and $F(s)$ is defined on a *frequency domain*. This makes sense when considering $s$ as an imaginary number (in this case, the kernel is a trigonometric function).


### Existence of Uniqueness of the Laplace Transform

To guarantee existence, we define the following condition:

**Definition.** A function $f$ is of *exponential order* if we can find $M,c>0$ such that when $t\rightarrow\infty$, $f(t)<Me^{ct}$.

Then (existence of uniqueness):

Let $f,g$ be $2$ piecewise continuous functions of exponential order, for a constant $c>0$.

Then their Laplace Transforms exist for all $s>c$, and if $F(s)=G(s)$ for all $s>c$, then $f(t)=g(t)$ for all $t\geq 0$.

From this, we know that we can uniquely identify a function $f(t)$ to its Laplace Transform. So our goal is now to find how to go from a Laplace Transform to the original function.


**Notation.** The inverse Laplace Transform of $F(s)$ is the function $f(t)$, such that $\mathscr{L}(\{f(t)\})=F(s)$. We will denote it $\mathscr{L}^{-1}\{F(s)\}$.

Now the two following properties/theorems are useful for finding the inverse Laplace Transform:


**1: Linearity.** 

$$\mathscr{L}(\{af(t)+g(t)\})=a\mathscr{L}(\{f\})+\mathscr{L}(\{g\})$$

and
 
$$\mathscr{L}^{-1}(\{aF(s)+G(s)\})=a\mathscr{L}^{-1}(\{F(s)\})+\mathscr{L}^{-1}(\{G(s)\})$$

**2: Shift property.**

$$\mathscr{L}(\{e^{-at}f(t)\})=F(s+a).$$


**Remark.** In general, we will try to get inverse Laplace Transforms of rational functions, which are of the form $$F(s)=\frac{P(s)}{Q(s)}.$$

We can do this by using the above two theorems to decompose $F$ into separate terms, and use partial fraction decomposition of $Q$.



