# Game Theory

While decision theory involved one agent and outcomes depended on these agent's choices as well as the environment, **Game Theory** involves decisions of other agents as playing an active role in determining outcomes. 

## The Prisoner's Dilemma

Consider two prisoners who each have the choice to either 

1. Admit to the crime
2. Claim innocence

Now the outcome of their sentences depends on both of their choices. We can sum it up in this table, where the numbers represent utility:
|||Prisoner 1||
|-|-|-|-|
|||Defect|Confess|
|Prisoner 2|Defect|3,3|1,4|
||Confess|4,1|2,2|

In other words, if both prisoners defect, they will each get 3 units of utility. We call this matrix the **Game Matrix**. 

The paradox is that the optimal solution would be to both defect, getting 3 utility each. But this is not the conclusion reached by either prisoner, as they both believe it is always better to confess, no matter what the other prisoner does. So this optimal solution is never realized.

## A Taxonomy of Games

We want to divide certain games into categories. The prisoner's dilemma is described as:

1. Non-cooperative
2. Simultaneous strategy
3. Symmetric
4. Non-zero sum
5. Finite game

Let's talk about each quality.

### Cooperative vs non-cooperative

This is NOT in terms of actual cooperation! It is about whether the players are able to form *binding agreements* (legal or other means) that force the players to keep the agreements.

In the prisoner's dilemma, nothing is stopping either prisoner from lying about their choice. So it is non-cooperative.


### Simultaneous vs non-simultaneous

In a simultaneous game, each player decides on their strategy without knowing what the other player will do (Doesn't necessarily have to happen at the same time). An example of a simultaneous game is Rock-paper-scissors.

### Sequential vs non-sequential

In a sequential game, players have some or full information about the strategies that the other players used in earlier rounds of the game. Games with full info are called perfect games. Example: chess!

### Symmetric vs non-symmetric

A symmetric game is a game where all players face the same strategies and outcomes. In other words, it doesn't matter which player you are.

### 2-person vs n-person games

An example of a game with many players would be monopoly. Many-player games are difficult to analyze and will not be discussed in this course.

### Games with pure strategies vs mixed strategies

Mixed strategies involve some element of probability. In general, to play a game with mixed strategy is to play a pure strategy with some probability $0\leq p\leq1.$

## Common Knowledge Rationality (CKR)

We assume some statements:

1. All players are rational (they play strategies that best promote their individual objectives).
2. All players know that the other players are rational.
3. All players know that all players know that the other players are rational.


... and so on and so forth. The $n^{th}$ assumption is the $n^{th}$ order of CKR.

**Definition.** To solve a game is to figure out which strategies rational players would choose if confronted with the game in question.

## 2-Person Zero-sum games

Zero-sum refers to the idea what "whatever the first player gains is what the second player loses." Take rock-paper-scissors for example. We can express the game matrix as follows:

||Rock|Paper|Scissors|
|-|-|-|-|
|Rock|0,0|1, -1|-1, 1|
|Paper|-1, 1|0,0|1, -1|
|Scissors|1, -1|-1, 1|0,0|

We can see that this is a zero-sum game, since the 1 and -1 balance each other out.

We might simplify the table by only taking the first number of the two, since we know that it is a zero-sum game. The convention is that the number listed in any cell in the table below is the outcome for the **Row** player. If we wanted the outcomes for the **Column** player, we would just multiply everything by $-1$.

||c1|c2|c3|
|-|-|-|-|
|r1|0|1|-1|
|r2|-1|0|1|
|r3|1|-1|0|

So, the **Row** Player tries to maximize the numbers, whereas the **Column** player tries to minimize them.

Let's consider the following matrix of a zero-sum game:

||c1|c2|c3|
|-|-|-|-|
|r1|3|-3|7|
|r2|4|5|6|
|r3|2|7|-1|

We want to analyze this game. We should start by looking for any dominances. By comparing each row to each other row, we find that none of the rows dominate each other. So at this point, the Row Player has no preferred choice.

Now the column player might also look for dominances. Again, there are no dominances between the columns either. So dominance reasoning has no recommendations at all for this game! So we will need to apply some other reasoning to this game. Let's lay out some hypotheticals:

- If **Row** knew that **Column** was going to play c1, then **Row** should play r2.
- If **Column** knew that **Row** was going to play r2, then **Column** should play c1.

Notice that these hypotheticals coincide! Both statements lead to the combination r2, c1. Now let's look at another starting point.

- If **Row** knew that **Column** was going to play c2, then **Row** should play r3.
- If **Column** knew that **Row** was going to play r3, then **Column** should play c3.

This time, we don't find that the **Column** player will choose c2. There is no "loop" here! It's left as an exercise to the reader to find that there also isn't a loop if we start with the assumption of c3.

**Definition.** A pair of strategies is said to be in **equilibrium** if and only if it holds that once the pair is chosen, then none of the players could reach a better outcome by unilaterally switching to another strategy.

In the above example, neither player could switch their strategy to improve their score. It is certainly possible that either player could end up with a better score, but *both* players would need to change their strategy.

In the case of the prisoner's dilemma, there is a situation where both prisoners get 3 units of utility. However, if we begin at that point, then either prisoner could gain more utility by changing their strategy to confessing. So this is not an **equilibrium**. The only equilibrium is when both prisoners confess.

### The Minimax Condition (for 2-Person Zero-sum games only!)

A pair of strategies is in **equilibrium** if (but not only if) the outcomes determined by them equal the minimal value of its row and the maximal value of its column.

Consider the following game matrix for a 2-Person Zero-sum game:

||c1|c2|c3|
|-|-|-|-|
|r1|9|8|7|
|r2|7|-5|6|
|r3|4|1|-2|

Since we know that we can apply the Minimax Condition, we will look for the minimal values in each row. For each minimal value we find, we will check if it is the maximum in its column. This allows us to find equilibria. 

In row 1, the value $7$ is the minimal value. It turns out that it is also the maximum value in its column. So the strategies r1, c3 are in equilibrium.

You can go through and find out that there are no other equilibria.

Another example!!

||c1|c2|c3|
|-|-|-|-|
|r1|4|1|2|
|r2|5|1|9|
|r3|2|-3|-2|

We find that both cells containing $1$ are the minima in their row, and the maxima in their column. So we have two equilibria? There is no problem with having two equilibria in the context of 2-Person Zero-sum games. This is because we can actually show that whenever we have two or more equilibria, then they will all exist along the same row(s) or column(s). 

In the matrix

||c1|c2|c3|c4|
|-|-|-|-|-|
|r1|1|2|3|1|
|r2|0|5|0|0|
|r3|1|6|4|1|

There are even four equilibria! 

We can revisit the rock-paper-scissors matrix:

||c1|c2|c3|
|-|-|-|-|
|r1|0|1|-1|
|r2|-1|0|1|
|r3|1|-1|0|

There are no _pure strategy_ equilibria! 

Here is a Major Result: For 2-Person Zero-sum games, there is ALWAYS at least one equilibrium of either pure strategies or mixed strategies.

## Mixed Strategies

Let's consider rock-paper-scissors. We have the game matrix above.

Here is an idea: instead of always using just one pure strategy (e.g. always playing scissors), we might use a mixture of these pure strategies with probabilities.

**Example.** We could decide to play rock, paper, and scissors each one-third of the time. We write it out like

$$[\text{Rock } \frac{1}{3}, \text{Paper } \frac{1}{3}, \text{Scissors } \frac{1}{3}]$$


where the numbers represent the corresponding probabilities.

Using this notation, we can describe a pure strategy where we only play rock:
$$[\text{Rock } 1, \text{Paper } 0, \text{Scissors } 0].$$

Now we want to know how to calculate the expected utility of playing one mixed strategy versus another. We will need to think of it as a **compound gamble**. Here is the game matrix again:

||c1|c2|c3|
|-|-|-|-|
|r1|0|1|-1|
|r2|-1|0|1|
|r3|1|-1|0|

We put the strategies against each other:

$$[\text{r1 } 1, \text{r2 } 0, \text{r3 } 0].$$

and

$$[\text{c1 } 0, \text{c2 } 1, \text{c3 } 0].$$

Intuitively, we see that the row player will always win. Let's formalize it a bit by looking at the expected utility of the row player:

We will begin with the top left cell. We multiply the probability that the row player picks r1, the probability that the column player picks c1, and the value in the cell. In this case, we find that we have $1\times0\times0=0$.

Now each cell in the top row is multiplied by the probability that the row player picks r1. So we can write it out like

$$EU=1\times[0\times0+1\times1+0\times-1]+0\times[...]+0\times[...]$$

In this case, we don't really need to care about what's inside the other two rows, since the probability is 0 anyways. So we find that the expected utility is 1, which is in favor of the row player.

Okay, now what if we apply this calculation to mixed strategies?

**Example 2.** Consider the following strategies:

$$[\text{r1 } \frac{1}{3}, \text{r2 } \frac{1}{3}, \text{r3 } \frac{1}{3}] \text{ vs } [\text{c1 } 0, \text{c2 } 1, \text{c3 } 0].$$

We get the following expansion:

$$EU=\frac{1}{3}\times[0\times0+1\times1+0\times-1]+\\\frac{1}{3}\times[-1\times0+0\times1+1\times0]+\\\frac{1}{3}\times[1\times0+-1\times1+0\times1],$$

Which evaluates to $EU=0$. So we are saying that if one player picks at random, and the other always chooses the scissors, then there is no expected gain or loss. This makes sense intuitively!

**Example 3.** Consider the following strategies:

$$[\text{r1 } \frac{1}{3}, \text{r2 } \frac{1}{3}, \text{r3 } \frac{1}{3}] \text{ vs } [\text{c1 } x, \text{c2 } y, \text{c3 } z],$$

where $x+y+z=1$. Let's find the expected utility:

$$EU=\frac{1}{3}\times[0\times x+1\times y+-1\times z]+\\\frac{1}{3}\times[-1\times x+0\times y+1\times z]+\\\frac{1}{3}\times[1\times x+-1\times y+0\times z]$$

$$EU=\frac{1}{3}\times[-x+x+y-y+z-z]=0.$$

So, playing at random, no matter the opponent's strategy, will always result in an expected utility of $0$.

**Example 4.** Now what if the game is non-symmetric? Here is a game matrix:

||c1|c2|
|-|-|-|
|r1|6|3|
|r2|2|4|

Lets compare the strategies

$$[\text{r1 } \frac{1}{2}, \text{r2 } \frac{1}{2}] \text{ vs } [\text{c1 } 1, \text{c2 } 0]$$

Then we have 

$$EU=\frac{1}{2}[6\times1+3\times0+2\times1+4\times0]=4.$$

Then the expected utility is 4 per round.

If we consider the strategies 

$$[\text{r1 } \frac{1}{2}, \text{r2 } \frac{1}{2}] \text{ vs } [\text{c1 } \frac{1}{2}, \text{c2 } \frac{1}{2}],$$

We are not in equilibrium, since the row player is better off just always playing r1, which yields a greater expected utility.