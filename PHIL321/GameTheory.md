# Game Theory

While decision theory involved one agent and outcomes depended on these agent's choices as well as the environment, **Game Theory** involves decisions of other agents as playing an active role in determining outcomes. 

## The Prisoner's Dilemma

Consider two prisoners who each have the choice to either 

1. Admit to the crime
2. Claim innocence

Now the outcome of their sentences depends on both of their choices. We can sum it up in this table:
|||Prisoner 1||
|-|-|-|-|
|||Defect|Cooperate|
|Prisoner 2|Defect|3,3|25,1|
||Cooperate|1,25|10,10|

In other words, if both prisoners defect, they will each get 3 years in prison. We call this matrix the **Game Matrix**. 

The paradox is that the optimal solution would be to both defect, getting 3 years each. But this is not the conclusion reached by either prisoner, as they both believe it is always better to cooperate, no matter what the other prisoner does. So this optimal solution is never realized.

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