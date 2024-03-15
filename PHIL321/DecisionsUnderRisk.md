# Decisions Under Risk

Its when we know the probabilities of each state.

## The Ellsbergg Paradox

Consider an urn. It contains red, black, and yellow balls. It has 30 red balls, and 60 balls that are either black or yellow. We present two gambles:

*Gamble 1*. Get $100 if red is drawn.

*Gamble 2*. Get $100 if black is drawn.

We have the following table:

||Red|Black|Yellow|
|-|-|-|-|
|Gamble 1|$100|$0|$0|
|Gamble 2|$0|$100|$0|

Empirically, people tend to pick Gamble 1, since it carries some "certainty" as to the chance of winning. We can't be sure if the number of black balls is very small.

Now let's consider another pair of gambles.

*Gamble 3*. Get $100 if red or yellow is drawn.

*Gamble 4*. Get $100 if black or yellow is drawn.

Now we have the table:

||Red|Black|Yellow|
|-|-|-|-|
|Gamble 3|$100|$0|$100|
|Gamble 4|$0|$100|$100|

Now people will prefer Gamble 4 over Gamble 3. Again, this is because there is a "certain" 66% chance of winning, since we know that 2/3 of the balls are either black or yellow.

Now this combination of preferences is inconsistent. Let's show this:

Suppose that the proportion of black balls in the mixture of black and yellow is $p$, where $0\leq p \leq1$. Then the proportion of yellow balls in the mixture is $(1-p)$. So

$$EU(a_1)=u(100)\cdot\frac{1}{3}+u(0)\cdot\frac{2}{3}p+u(0)\cdot\frac{2}{3}(1-p)$$
$$EU(a_2)=u(0)\cdot\frac{1}{3}+u(100)\cdot\frac{2}{3}p+u(0)\cdot\frac{2}{3}(1-p)$$

Then we can calculate the difference:

$$EU(a_2)-EU(a_1)=u(\$100)\cdot\left(\frac{2}{3}p-\frac{1}{3}\right)-u(0)\cdot\left(\frac{2}{3}p-1\right)$$

Now we repeat the process for Gambles 3 and 4:

$$EU(a_3)=u(100)\cdot\frac{1}{3}+u(0)\cdot\frac{2}{3}p+u(100)\cdot\frac{2}{3}(1-p)$$
$$EU(a_4)=u(0)\cdot\frac{1}{3}+u(100)\cdot\frac{2}{3}p+u(100)\cdot\frac{2}{3}(1-p)$$

$$EU(a_4)-EU(a_3)=u(\$100)\cdot\left(\frac{2}{3}p-\frac{1}{3}\right)-u(0)\cdot\left(\frac{2}{3}p-1\right)$$

Now both of the expressions $EU(a_2)-EU(a_1)$ and $EU(a_4)-EU(a_3)$ are the same. So the principle of maximizing expected utility would say that if we were to prefer $a_1$ to $a_2$, then we would necessarily also need to prefer $a_3$ to $a_4$. But this goes against our empirical findings!

## St. Petersburg Paradox

Lets begin by explaining the St. Petersburg game. The rules are as follows:

You flip a fair coin. If it lands on heads, you get $2^n$ units of utility, where $n$ is the number of flips that you have done in total, and the game is over. If it lands on tails, we keep playing.

So how much money should you be willing to pay to play this game? Well, we can look at the expected utility to answer this. We have a $1/2$ chance to get $\$2$ (if the coin lands on heads the first time). We also have a $1/4$ chance to get $\$4$ (if the coin lands on tails, then heads). We continue this process to see that the expected utility is

$$\frac{1}{2}\cdot{2}+\frac{1}{4}\cdot{4}+\frac{1}{8}\cdot{8}+\frac{1}{16}\cdot{16}+...$$

$$=1+1+1+1+1+...\implies\infty$$

So the expected utility is infinity?? According to this, we should be willing to pay an infinite amount of utility for the chance to play this game. But this is absurd! Most people would not be happy to spend a billion dollars for the off-chance that they gain more money.

