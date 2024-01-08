## First Order Differential Equations

We should begin by asking: What is a differential equation?

**Definition.** A differential equation is an equation for an unknown function involving one or more of its derivatives.

**Example 1.**

$$\frac{\text{d}x}{\text{d}t}+x = 2\cos(t)$$

In this example, we would be solving for the function $x(t)$. The equation involves the function, $x$, and its first-order derivative, $\frac{\text{d}x}{\text{d}t}$.

**Example 2.**

$$ay''+by'+cy = g(t)$$

In this example, $y$ is a function of $t$. The equation involves both the first and second order derivatives of $y$.

---

Here is a small aside on notation:

The notation $\frac{\text{d}x}{\text{d}t}$ implies that $x$ ONLY depends on $t$. It should not depend on other variables.

However, the notation $\frac{\partial x}{\partial t}$ implies that $x$ depends on $t$ and other variables.

---

Now, equipped with this knowledge, we can define the difference between ordinary differential equations and partial differential equations.

**Definition.** A ODE has only 1 independent variable, while a PDE has >1 independent variable. In examples 1 and 2 above, we only had one independent variable, $t$.


**Example 3.**

For a multivariable function $f(x, t)$, we have

$$\frac{\partial f}{\partial t} = \frac{\partial^2 f}{\partial x^2}$$

This is the heat equation. It involves two independent variables, so it is a PDE.

---

Any differential equation is either an ODE or a PDE. In this course, the focus will be on ODEs.

**Definition.** The **order** of an ODE is the highest order derivative present in the differential equation.

**Definition.** We say that an ODE is **linear** if it is a linear function of its derivatives. To elaborate on this, if we have the ODE

$$f(y, y', y'', ...) = g(y)\text{,}$$

Then in order for the ODE to be linear, $f(y, y', y'', ...)$ must be able to be written in the form $a_0y + a_1y' + a_2y''+...$, where the values $a_k$ do not depend on $y$ (they may be functions of other variables, however).

---

Why do we care about whether ODEs are linear? Because linear ODEs are much easier to solve, since we can leverage tools from linear algebra. 

**Example 4.** 

$$y''+t^2y=1$$

Is linear, while

$$yy'+y^2=1$$

is not.

---

**Definition.** An **autonomous** ODE is an ODE that doesn't explicitly depend on the independent variable.

For example, the ODE $y'=3y$ is autonomous, since it doesn't depend on $t$ (assuming $y$ is a function of $t$).

**Definition.** A solution to an ODE is a function that satisfies the ODE. 

