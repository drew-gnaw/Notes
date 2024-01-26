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







