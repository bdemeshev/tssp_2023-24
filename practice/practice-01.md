1.2. 
$p$ - probability of "head"
$N$ - total number of throws 
$E(N)$, $E(N^2)$, $E(N^3)$  
$Var(N) = E(N^2) -(E(N))^2$   

To find all these $E(N)$, $E(N^2)$, $E(N^3)$  ... it is sufficient to find one fancy function $E(\exp(tN))$

Two states:
(C) = the game continues
(F) = the final state

P(C -> F) = p
P(C -> C) = 1 - p

P(F -> F) = 1
P(F -> C) = 0


We will use the function $E(\exp(tN)) = M(t)$ to calculate $E(N)$, $E(N^2)$, $E(N^3)$....

By definition $M(t) = E(exp(tN))$ 

We will find two functions: $M_F(t)$ and $M_C(t)$, where the letter $F$ or $C$ denotes the initial state. 

If we start at $F$ then we need $N=0$ moves to reach $F$.
$M_F(t) = E\exp(tN) = E\exp(0) = E(1) = 1$
We really don't use this function, just to get the idea. 

Now let's move to the hard case:

(1) $M_C(t) = p \cdot \text{make one move and arrive at F} + (1-p) \cdot \text{make one move and arrive at C}$ 

(2) $M_C(t) = p \cdot \exp(t\cdot 1) + (1-p) \cdot \text{make one move and arrive at C}$ 

(3) $M_C(t) = p \cdot \exp(t\cdot 1) + (1-p) \cdot E(\exp(t(1 + N)))$ 

(4) $M_C(t) = p \cdot \exp(t\cdot 1) + (1-p) \cdot E(\exp(t)\exp (tN)))$ 

(5) $M_C(t) = p \cdot \exp(t\cdot 1) + (1-p) \cdot \exp(t) E(\exp (tN))$ 

(6) $M_C(t) = p \cdot \exp(t\cdot 1) + (1-p) \cdot \exp(t) M_C(t)$

We solve the equation (6) for $M_C(t)$:
$$M_C(t) = \frac{pe^t}{1 - (1-p)e^t}$$
Hence,
$$M_C(t) = E(\exp(tN)) = \frac{pe^t}{1 - (1-p)e^t}$$
This function is not our final goal, we will use it to calculate all the expected values...

Let's look at the derivatives of this $M_C(t)$ function:

$M'_C(t) = E(N\exp(tN))$

$M''_C(t) = E(N^2\exp(tN))$

$M'''_C(t) = E(N^3\exp(tN))$

If we plug in $t=0$ we see that there is a fancy way to calculate expected values:

$M'_C(0) = E(N)$

$M''_C(0) = E(N^2)$

$M'''_C(0) = E(N^3)$


In our case 

$$E(N) = M_C'(0) = \frac{pe^t(1 - (1-p)e^t) - pe^t (- (1-p)e^t)}{(1 - (1-p)e^t)^2} = \frac{p^2 + p(1-p)}{p^2} = 1/p$$


I hope you can take the two remaining derivatives :)

1.4.

Initially the pot is empty. 
1, 2, 3 -> the corresponding sum is added into the pot. 
4, 5 -> you take the pot with money and the game ends
6 -> you get nothing and the game ends

a) What is probability that the game eventually ends by 6?
by symmetry: 1/3
b) Expected duration of the game?
$N$ - random number of throws 


First step equation.
$$E(N) = 3/6 \cdot 1 + 3/6 \cdot E(N + 1)$$

$E(N) = a$

$$6a =  3 + 3 (a + 1)$$
$a = 6/3 = 2$

c) the main question!
$X$ - the random payoff we get
$E(X)$?

First step equation:
$$
E(X) = 3/6 \cdot 0 + 1/6 \cdot (E(X) + 1\cdot 2/3) + 1/6 \cdot (E(X) + 2\cdot 2/3) + 1/6 \cdot (E(X) + 3\cdot 2/3)
$$
You can solve it!

Another good idea!
$$
E(X) = (E(N) - 1)\cdot (1+2+3)/3 \cdot 2/3
$$



