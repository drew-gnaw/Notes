## Second order linear differential equations

For DEs of the form 

$$y''+py'+qy=0$$


The solutions are of the form $c_1y1+c_2y_2$ where $y_1, y_2$ are linearly independent.


Now let's assme that we have one solution, called $y_1$. Then we will see a method to obtain $y_2$. The method in question is called a **Reduction of order**.

The basic idea is to derive $y_2$ by solving a first order ODE.

Let $y_1$ be a solution of $y''+py'+qy=0$. Let's consider $y_2=y_1 \times v(x)$, which is another solution. Thus $y_2''+py_2'+qy_2=0$.

Using product rule, we know that $y_2'=y_1'v+y_1v'$ and also that $$y_2''=y_1''v+y_1'v'+y_1'v'+y_1v''$$
$$y_2''=y_1''v+2y_1'v'+y_1v''$$

Then we have 

$$y_1''v+2y_1'v'+y_1v''+p(y_1'v+y_1v')+qy_1v=0.$$

Then we factorize terms in $v$:

$$v(y_1''+py_1'+qy_1)+y_1v''+(2y_1'+py_1)v'=0.$$

Notice the form of the first time. We exploit the fact that $y_1$ is a solution to the ODE, meaning that the inside of the bracket is $0$. Thus, we can simplify:

$$y_1v''+(2y_1'+py_1)v'=0.$$

Now let us set $w=v'$, and divide by $y_1$.

$$w'+\frac{2y_1'+py_1}{y_1}w=0.$$

In order to solve for $w$, we use an integrating factor (or we can separate, whichever works). Suppose we solve $w$. Then we have $v'=w$, and this $v=\int{w}+C$. Knowing that $y_2=y_1v$, we have $y_2=y_1\int{w}+C_1y_1.$

**Example.** $2t^2y''+3ty'-y=0$, for $t>0$.

Let's apply the previous method. In order for this to work, we need to find $y_1$. We can get it by trying some simple functions, like $y_1=t$. After some testing, we find that $y_1=t^{-1}$ works.

Now we perform reduction of order. Let $y_2=y_1v$. Then $y_2=\frac{v}{t}$. We then have

$$y_2'=v'/t-v/t^2$$
$$y_2''=v''/t-2v'/t^2+2v''/t^3$$

Then we can plug these in:

$$2t^2(v''/t-2v'/t^2+2v''/t^3)+3t(v'/t-v/t^2)-v/t$$

$$v(4/t-3/t-1/t)+2tv''-4v'+3v'=0$$

$$2tv''-v'=0$$

Now let $w=v'$. Then we have $2tw'-w=0$. We can rearrange to find that $w'/w=1/2t$. Thus

$$\int{\text{d}w} = \int{\frac{1}{2t}\text{d}t}$$
Therefore we find that $\ln{w}=\frac{1}{2}\ln{t}$, so $w=\sqrt{t}$.

Then we go backwards. $v'=\sqrt{t}$, meaning $v=t^{3/2}$. You don't actually need the $\frac{2}{3}$ coefficient, since the solutions are of the form $y_2c_2$ anyways ($c_2$ takes care of it). So $y_2=y_1v=t^{-1}t^{3/2}=t^{1/2}=\sqrt{t}$.

### 2nd order linear ODE with constant coefficients

Now let's focus on the specific case where we have

$$ay''+by'+cy=0,$$

where $a, b, c$ are all constant. To solve this, we need to find two independent solutions. We will get these by solving a polynomial equation.

Let's consider $y(x)=e^{rx}$, and assume that it is a solution. Note that $y'=re^{rx}$ and $y''=r^2e^{rx}$. Now we can plug it in:

$$ar^2e^{rx}+bre^{rx}+ce^{rx}=0$$
$$e^{rx}\left[ ar^2+br+c \right]=0$$

Since an exponential is never $0$, the solutions are the solutions of $r$, which are the solutions to the polynomial equation $ax^2+bx+c=0$.

To solve this, it's simple AF! First consider the discriminant:

$$\Delta = b^2-4ac$$

- If $\Delta > 0$, we're all good and we have two solutions.
- If $\Delta = 0$, we have one double root.
- If $\Delta < 0$, We have two complex conjugate roots.

---

Let's consider the first case. Just solve the quadratic equation in this case. Then we have:

$$y_1=e^{\frac{-b+\sqrt{\Delta}}{2a}x}, y_2=e^{\frac{-b-\sqrt{\Delta}}{2a}x}$$

And solutions are of the form $$y = C_1e^{r_1x} + C_2e^{r_2x}.$$

---

Now the second case. Since we only have one root, we have $r=\frac{-b}{2a}$. We already know that $y_1=e^{rx}$ is a solution. Then by reduction of order, we can show that $y_2=xe^{rx}$ is also a solution. Then the solutions are of the form

$$y = C_1e^{rx} + C_2xe^{rx}$$
$$y = (C_1 + C_2x)e^{rx}.$$

---

The last case is when the discriminant is $<0$. Then the two complex conjugate roots are of the form

$$r=\frac{-b\pm i\sqrt{-\Delta}}{2a}.$$

Recall that we can represent complex numbers in the plane by setting $z=x+iy$ (The $x$-coordinate is the real part, and the $y$-coordinate is the complex part).

We can then obtain two solutions by "splitting":

$$y_1=e^{\frac{-b}{2a}x}\cdot e^{\frac{i\sqrt{-\Delta}}{2a}x}, y_2=e^{\frac{-b}{2a}x}\cdot e^{\frac{-i\sqrt{-\Delta}}{2a}x}$$

Note that the second term in each is a complex number.

Then the solutions are of the form 

$$y=Z_1e^{\frac{-b}{2a}x}\cdot e^{i\theta x} + Z_2e^{\frac{-b}{2a}x}\cdot e^{-i\theta x},$$

where $\theta = \frac{\sqrt{-\Delta}}{2a}$, and $Z_1, Z_2$ are complex numbers such that $y$ is real. In other words, these constants are specifically chosen so that $y$ is real.

Now this is an extremely inconvinient form for solutions. We will get a better final result.

Also, from the **principle of superposition**, we know that any linear combination of $y_1, y_2$ is a solution.

So our goal now is to write a linear combination of 

$$z_1=e^{\frac{-b}{2a}x}\cdot e^{i\theta x}, z_2=e^{\frac{-b}{2a}x}\cdot e^{-i\theta x}$$

above that will give a real number.

A final remark is that $z_1$ and $z_2$ are complex conjugates of each other. This is because we can write

$$e^{i\theta x} = \cos{(\theta x)}+i\sin{(\theta x)}$$
$$e^{-i\theta x} = \cos{(-\theta x)}+i\sin{(-\theta x)}$$
$$e^{-i\theta x} = \cos{(\theta x)}-i\sin{(\theta x)}$$

So they are complex conjugates of each other, thanks to Euler's formula.

Remember when we talked about how to represent complex numbers in the plane? Think of that plane. If we have two complex conjugates of each other, their complex parts are positive/negative versions of each other. So if we add them together, then the complex part disappears! We end up with a REAL number!

So we have:

$$e^{i\theta x} + e^{-i\theta x} = 2\cos(\theta x)$$
$$e^{i\theta x} - e^{-i\theta x} = 2i\sin(\theta x)$$

Here is De Moivre's formula,

$$\cos(\theta x) = \frac{e^{i\theta x} + e^{-i\theta x}}{2}$$
$$\sin(\theta x) = \frac{e^{i\theta x} - e^{-i\theta x}}{2i}$$

Now by writing $z_1+z_2$ and $z_1-z_2$, we obtain two linearly independent real solutions

$$y_1=e^{\frac{-b}{2a}x}\cdot \cos(\theta x), y_2=e^{\frac{-b}{2a}x}\cdot \sin(\theta x)$$

So therefore the solutions are of the form
$$y=e^{\frac{-b}{2a}x}{\left[ C_1\cos(\theta x) + C_2\sin(\theta x) \right]},$$

where $\theta = \frac{\sqrt{-\Delta}}{2a}$.

**Example.** Solve:

$$\begin{cases}
y''+y'+y=0\\
y(0)=0\\
y'(0)=1
\end{cases}$$

We have 

$$x'+x+1=0$$

and 

$$\theta = \frac{\sqrt3}{2}.$$

The discriminant is negative. So we are in the third case.

$$r=\frac{1\pm i\sqrt{3}}{2}$$
$$y=e^{\frac{-1}{2}x}{\left[ C_1\cos(\frac{\sqrt3}{2} x) + C_2\sin(\frac{\sqrt3}{2} x) \right]},$$

and

$$y'=\frac{-1}{2}e^{\frac{-1}{2}x}{\left[ C_1\cos(\frac{\sqrt3}{2} x) + C_2\sin(\frac{\sqrt3}{2} x) \right]} + \\e^{\frac{-1}{2}x}\left[ -C_1\frac{\sqrt3}{2}\sin(\frac{\sqrt3}{2} x) + C_2\frac{\sqrt3}{2}\cos(\frac{\sqrt3}{2} x) \right].$$

Now let's substitute the IC $y(0)=0$. We find that $C_1 = 0$. Using the other IC $y'(0)=1$, we find that $C_2=\frac{2}{\sqrt3}$ (The calculations are trivial and left as an exercise to the reader). So the unique solution is 

$$y(x)=\frac{2}{\sqrt3} e^{\frac{-1}{2}x}\sin(\frac{\sqrt3}{2}x).$$

Note that we have a unique solution thanks to the initial value, which narrows us down from many solutions that are a linear combination of two $y_1, y_2$ to just one.

There is an alternative form of $y$ when $\Delta < 0$. If we find a solution in the form 

$$e^{\alpha t}\cdot \left(A\cos(\beta t) + B\sin(\beta t) \right)$$

We want to rewrite it as 

$$e^{\alpha t}\cdot C\cos\left(\omega t - \phi \right).$$

So that we can do the thingy yaknow where $\omega$ is frequency and $C$ is the amplitude n shit

Okay so we want to basically turn $\left(A\cos(\beta t) + B\sin(\beta t) \right)$ into $C\cos\left(\omega t - \phi \right)$. In other words, we need to find $C, \omega, \phi$ such that 

$$\left(A\cos(\beta t) + B\sin(\beta t) \right) =  C\cos\left(\omega t - \phi \right).$$

We can immediately find that $\beta = \omega$.

Using trig identities, we can say that

$$C\cos(\omega t - \phi) = C\cos(\omega t)\cos(\phi) + C\sin(\omega t)\sin(\phi).$$

From here it is obvious that $A = C\cos(\phi)$, $B = C\sin(\phi)$. Now we can divide the second equation by the first:

$$\tan(\phi) = B/A$$

and by adding the squares of the equations to each other:

$$A^2+B^2=C^2(\cos^2(\phi) + \sin^2(\phi))$$
$$A^2+B^2=C^2$$

In order for $C_1$ and $\phi$ to be uniquely defined, we need to assume that $C > 0$ and $0 \leq \phi < 2\pi$.

$$\begin{cases}
C = \sqrt{A^2+B^2}\\
\phi = \tan^{-1}(B/A)
\end{cases}$$

However, the range of $\tan^{-1}$ goes from $-\frac{\pi}{2}$ to $\frac{\pi}{2}$, while we want $\phi$ to go from $0$ to $2\pi$!

