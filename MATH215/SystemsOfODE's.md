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

An autonomous system is a system of ODEs where none of them depend on the independent variable ($t$). We can draw a generalization of the slope field, called a ***vector field***, which shows the direction of $\vec{x'}$.

**Example 1.** 

$$\begin{cases}
x_1'=-x_1+2x_2\\
x_2'=x_1
\end{cases}$$

This is a 2D autonomous system with $\vec{x'}=\begin{bmatrix}-x_1+2x_2\\x_1\end{bmatrix}$:

![image of vectorfield](vectorfield.png)

If we do this for many points, using computers, we can visualize solutions.

**Definition.** A 1st order linear system is of the form $\vec{x'}=P(t)\vec{x}+\vec{f}(t)$, where $P(t)$ is a matrix, and $\vec{f}(t)$ is a vector. If $\vec{f}(x)=0$, we call the system homogenous. For example,

$$\vec{x'}=\begin{bmatrix}2 & 0 \\ 3 & 1\end{bmatrix}\vec{x}+\begin{bmatrix}1 \\ 4\end{bmatrix}$$

If $P(t)$ is continuous, and the linear system of size $n$ has $n$ independent solutions $\vec{x_1}(t)...\vec{x_n}(t)$, the solutions of $\vec{x'}=P(t)\vec{x}$ are linear combinations of the solutions $\vec{x_1}(t)...\vec{x_n}(t)$.

**Definition.** The fundamental matrix associated with $\vec{x}=P\vec{x}$ is

$$x(t)=\begin{bmatrix}\vec{x_1},\vec{x_2}, ... ,\vec{x_n} \end{bmatrix}=\begin{bmatrix}x_{11} \\ x_{12} &\dots\\ \vdots & \dots\\ x_{1n}\end{bmatrix}$$

Then the general solution is $\vec{x}(t)=x(t)\times\vec{c}$, where $\vec{c}$ is a constant vector.

## Eigenvalue method

Now we consider systems of linear ODEs with constant coefficients.

**Example 2.** 

$$\vec{x'}=\begin{bmatrix}2 & 0 \\ -1 & -1\end{bmatrix}\vec{x}$$

Let's assume that we have a solution

$$\vec{x}(t)=\vec{v}e^{\lambda t}.$$

What can we say about $\lambda$ and $\vec{v}$? Let's take the derivative to find out:

$$\vec{x}'(t)=\lambda\vec{v}e^{\lambda t}$$
$$\vec{x}'(t)=\lambda \vec{x}$$

Therefore, we have that the matrix $P(x)$ is equal to $\lambda$. 

So we obtain $P\vec{v}=\lambda\vec{v}$.

This means that $\lambda$ is an eigenvalue of $P$, and $\vec{v}$ is the associated eigenvector of $P$. In particular, if we can find $n$ different eigenvalues, we can fully solve the problem.

**Theorem.** If $P$ has $n$ distinct real eigenvalues $\lambda_1, \lambda_2,...,\lambda_n$, then there are $n$ associated linearly independent eigenvectors $\vec{v_1},\vec{v_2},...\vec{v_n}$, and the general solution of $\vec{x'}=P\vec{x}$ is 

$$\vec{x}=C_1\vec{v_1}e^{\lambda_1 t}+C_2\vec{v_2}e^{\lambda_2 t}+...+C_n\vec{v_n}e^{\lambda_n t}.$$

