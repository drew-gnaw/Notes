# Systems of ODEs

## Introduction

In physical systems, more complex systems are described by more than one variable and equation. For example, the Lotka-Volterra equations describe the populations of a predator and prey system.

### Lota-Volterra Model

We might model the system of predator and prey as such:

$$x(t)=\text{population of prey at time } t$$
$$y(t)=\text{population of predator at time } t$$

and we relate them as follows:

$$\begin{cases}
x'(t)=\alpha x-\beta xy\\
y'(t)=-\gamma y+\delta xy
\end{cases}$$

Where the terms containing $xy$ represent the "interactions" between the species, and $\alpha x$ is reproduction, and $\gamma y$ is decay.

$\alpha, \beta, \gamma, \delta$ are all parameters of the system and are all greater than $0$. We will see how to solve this system. 

**Remark.** This system is bilinear. It is more difficult to solve nonbilinear systems, but we can use some tools from linear systems to study them.

**Definition.** A first-order system is of the form 

$$\begin{cases}
x_1'=f_1(x_1,...,x_n,t)\\
x_2'=f_2(x_1,...,x_n,t)\\
...\\
x_n'=f_n(x_1,...,x_n,t)\\
\end{cases}$$

(It's a system of ODEs).

This can be written in vector notation as 

$$\vec{x}'=f(\vec{x},t)$$

A solution $\vec{x}(t)=(x_1(t), ..., x_n(t))^t$ is a continuous vector function that satisfies the system.

**Remark.** We can write 2nd order ODE's from previous chapters as a 1st order system. Given

$$ay''+by'+cy=f$$

We introduce $x_1$ and $x_2$. We will choose their values to be:

$$x_1=y, x_2=y'$$

Then we can rewrite our system as

$$ax_2'+bx_2+cx_1=f$$

with the added condition that $x_1'=x^2$. So we have the system

$$\begin{cases}
x_1'=x_2\\
ax_2'+bx_2+cx_1=f.
\end{cases}$$

In general, by choosing $x_1=y,x_2=y',...,x_n=y^{(n-1)}$, we can transform any $n^{\text{th}}$ order ODE into an equivalent 1st order system.

