## Mechanical Vibrations


The goal is to study **Physical systems** that are modeled with $2^{nd}$ order ODEs, and classify different possible regimes.

Remember when we were solving $2^{nd}$ order ODEs and we simplified it into the form 

$$e^{\alpha t}\cdot C\cos\left(\omega t - \phi \right)?$$

We know that $C$ is the amplitude, $\omega$ is the natural frequency, and $\phi$ is the shift.

If you didn't take physics, $\frac{\omega}{2\pi}$ is the **usual frequency** (Number of cycles per second), and conversely, $\frac{2\pi}{\omega}$ is the **period** (seconds per cycle).

### Examples

We will see that we can describe several physical systems as $2^{nd}$ order ODEs:

- Mass spring systems (either horizontal or vertical)
- RLC circuits
- Pendulums

Let's try a vertical mass spring system. 

**Example 1.** A mass $m$ is attached to a spring with force constant $k$. The spring is hanging from a ceiling, with length $L$ at rest.

The mass is experiencing a force downwards by gravity, $mg$. The spring is pulling it upwards with a force $kz$, where $z$ is the length of the spring. Then we set $x=z-L$.

Now what ODEs satisfies $x(t)$?

From Newton's formula, we know that force = $mz''=-k(z-L)$. Now by replacing $z$ with $x$,

$$mx''+kx=0$$

and we know how to study this using our techniques from 2nd order ODEs.

Since we do not consider damping, this is an example of free undamped motion. We find that $\omega = \frac{k}{m}$ and $x(t) = C\cos(\omega t - \phi)$.

Now let's throw some numbers in. $m=10^{-2}kg$, and $L=2.45\cdot10^{-2}m$. At time $y=0$, we lift the mass up $2\cdot10^{-2}m$. Now we want to find the amplitude and phase shift.

Now we want to find $k$. At equilibrium, we know that the forces even out, so $kL=mg$ (since $L$ is the length at rest, which is equilibrium). Thus $k=\frac{mg}{L}$.

---

### Free undamped motion

In general, any system that exhibits free undamped motion can be described by the second-order ODE

$$x''+(\omega_0)^2x=0,$$

where $\omega_0$ is determined by the parameters of the physical system.

The solution to an ODE of this form is $x(t)=C\cdot \cos(\omega_0t-\phi)$, where $C$ and $\phi$ are determined from initial conditions of the problem.

### Free damped motion

Now if the system loses energy over time via some means of damping, then it is described by the ODE

$$mx''+cx'+kx=0,$$

where each coefficient $m,c,k>0$. We can normalize the ODE as follows:

$$x''+2px'+(\omega_0)^2x=0$$

where $p=\frac{c}{2m}$, ${\omega_0}^2=\frac{k}{m}$.

Now we can perform reduction of order:

$$x^2+2px+{\omega_0}^2=0$$
$$\Delta = 4p^2-4{\omega_0}^2=4(p^2-{\omega_0}^2).$$

Note that this is why we normalized the ODE. If we hadn't, this discriminant would have been really gross.

### Types of damping

Maybe you remember the terms **Overdamping** and **Underdamping**. Now these cases differ in the sign of the discriminant:

---
**Overdamping** happens when $\Delta > 0$. Then we have two distinct real roots, of the form 

$$r_{1,2}=-p\pm\sqrt{p^2-{\omega_0}^2}.$$

Then our solutions are a linear combination of these:

$$x(t)=C_1e^{r_1t}+C_2e^{r_2t}.$$

An important note to make is that $r_{1,2}$ are both negative. This is because $\sqrt{p^2-{\omega_0}^2} < p$. The rest is trivial and left as an exercise to the reader (i dont want to type it out).

Now since both are negative, then we can say that $x(t)\rightarrow 0$ as $t\rightarrow \infty$.

---

**Critical damping** happens when $\Delta = 0$. Then we have a double real root, $-p$. Then our solutions are of the form

$$x(t)=C_1e^{-pt}+C_2te^{-pt},$$

which also goes to $0$ as $t\rightarrow \infty$ for the same reason as before.

---

**Underdamping** happens when $\Delta < 0$. Then we have two complex conjugate roots. They are of the form 

$$r_{1,2}=-p\pm i\sqrt{{\omega_0}^2-p^2}$$

(Note that the argument of $\sqrt{}$ is made positive by flipping the sign). Then, as seen before, 

$$x(t)=e^{-pt}\cdot\left(A\cos{\omega_1}t+B\sin{\omega_1}t\right)$$

Where $\omega_1=\sqrt{{\omega_0}^2-p^2}$. Which can be rewritten in the form

$$x(t)=e^{-pt}\cdot C\cos\left({\omega_1}t-\phi\right),$$

Which ALSO goes to $0$ as $t\rightarrow\infty$. The dominant term, $e^{-pt}$, "forces" oscillation to dampen. Since $-1\leq\cos(\theta)\leq1$, the system oscillates between $-Ce^-{pt}$ and $Ce^{-pt}$. 

Now $\omega_1$ is the "pseudo-frequency" of the system. This is the frequency if we were not losing energy. 