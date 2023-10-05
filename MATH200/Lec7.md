## Lecture 7

### Limit definition of continuity

We say that a function of two variables $f(x, y)$ is continuous at a point $(a, b)$ if:

$$\begin{cases} f(a, b) \space \text{is defined}, \\
\lim\limits_{(x,y) \rightarrow (a,b)}{f(x,y)=f(a,b)}\end{cases}$$

And we follow a similar procedure for a function with three parameters $f(x, y, z)$. 

If $f(x, y, ...)$ is given by a single expression (not piecewise) formed using standard functions, and standard operations, it is continuous in all of its domain. We can also say that $f(x, y, ...)$ is differentiable at all points in its domain $(a, b, ...)$ provided $f(x, y, ...)$ is defined at all nearby points. 

(A standard function is a polynomial, rational, trig, exp, log. A standard operation is +, -, *, /, composition.)

### Partial derivatives

This is really just a sub-topic of the whole concept of differentiability. 

Given a function $f(x, y)$, its partial derivatives are:

$f_x(x, y) = \frac{\partial f}{\partial x}$: differentiate $f(x, y)$ with respect to $x$ while treating $y$ as a constant.

$f_y(x, y) = \frac{\partial f}{\partial y}$: differentiate $f(x, y)$ with respect to $y$ while treating $x$ as a constant.

In general for functions with more parameters, they are defined similarly (treating all other variables as constant).

---

<div>

#### Examples

#### Q1

$f(x, y)=x^2y+e^{x+y^2}$.

$f_x = 2xy+e^{x+y^2}$ (hold $y$ constant)

$f_y = x^2+2ye^{x+y^2}$ (hold $x$ constant)

#### Q2

$f(x, y, z) = x^2yz^3$

$f_x = 2xyz^3$

$f_y = x^2z^3$

$f_z = 3x^2yz^2$

</div>

---

Note that the partial deriavtives are functions of two variables themselves!

By the definition of single variable differentiation:

$$f_x(a, b)=\lim_{x \rightarrow a}{\frac{f(x, b) - f(a, b)}{x-a}}$$

We can think of this as the slope of the tangent line to the $y=b$ trace of the graph, at $x=a$. We are holding $y$ CONSTANT, while moving $x$ along. We can say that $f_x$ is the rate of change if we hold all other variables constant, and move it along the $x$ axis.

Now let's look back at the limit definition for differentiability (handout 3). We replace $x=a+t$ and $y=b$. Then the limit becomes:

$$\lim_{t \rightarrow 0}{\frac{f(a+t, b)-f(a, b)-f_x(a, b)t}{t}} = 0$$

$$\lim_{t \rightarrow 0}{\frac{f(a+t, b)-f(a, b)}{t}} = f_x(a, b)$$

### Higher-order partial derivatives

Denoted as $$f_{xx} = \frac{\partial^2 f}{\partial x^2}$$

or, we can have several variables:

$$f_{xy} =\frac{\partial }{\partial y} \left(\frac{\partial f}{\partial x}\right)$$

Order matters (the derivatives are composed in the order given, with the innermost derivative corresponding to the variable closest to $f$)

> Theorem: if $f_{xy}, f_{yx}$ are continuous at $p$, then $f_{xy}(p) = f_{yx}(p)$.

This theorem applies to all standard expressions (non-piecewise). It also applies by mathematical induction to higher partials such as $f_{xyz} = f{xzy} = f_{zyx} = ...$
