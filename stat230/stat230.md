STAT 230
=

Example: Suppose you have 20 distinct books, 7 of which are written by Mark Twain.

1. How many ways can you arrange 12 books on a shelf if exactly 3 of them must be Mark Twain books?

    > ${7 \choose 3}{13 \choose 9}$ ways to choose subsets.     
    > Books can be rearranged in $12!$ ways.    
    > Therefore, the answer is $12!{7 \choose 3}{13 \choose 9}$.

Example: Consider drawing 3 numbers at random **with** replacement from the digits 0 to 10. What is the probability that there is a repeated number among the 3.

> We can consider the complement, where there are no repeated numbers.  
> $1 - \frac{10 \cdot 9 \cdot 8}{10^3}$

Example: Suppose there are 4 passengers on an elevator that services 5 floors. Each passenger is equally likely to get off at any floor.

> $|S| = 5^4$

1. What is the probability that the passengers all get off on different floors?

    > $|A| = 5^{(4)}$. Therefore $P(A) = \frac{5^{(4)}}{5^4}$.

2. 2 passengers get off on floor 2, and 2 get off on floor 3.

    > $|A| = {4 \choose 2}{2 \choose 2}$. Therefore $P(A) = \frac{{4 \choose 2}{2 \choose 2}}{5^4}$.

3. 2 passengers get off on one floor, and 2 passengers get off on another floor.

    > ${5 \choose 2}{4 \choose 2}{2 \choose 2}$.

Example: Consider rearranging the letters at random in the name "ZENYATTA" to form a single 'word'.

1. How many ways can this be done?

    > $|S| = {8 \choose 2}{6 \choose 2}{4 \choose 1}{3 \choose 1}{2 \choose 1}{1 \choose 1} = \frac{8!}{2!2!}$.

2. What is the probaility that all of the letters appear in alphabetical order?

    > A = { "AAENTTYZ" }. Therefore $P(A) = \frac{1}{|S|}$.

3. What is the probability that the word begins and ends with "T"?.

    > $|A| = {6 \choose 2}{4 \choose 1}{3 \choose 1}{2 \choose 1}{1 \choose 1}$.

${n \choose n_1}{n - n_1 \choose n_2}...{n_k \choose n_k} = {n \choose n1,n2,...,n_k}$.

Example: Harold's daily morning ritual is to drink 5 cans of pop. He has 2 cans of pop C, 2 cans of pop F, and 1 can of pop P. How many ways can he complete the ritual?

> $|A| = \frac{5!}{2!2!} = 30$.

Example: Find the probability that a bridge hand (13 cards picked at random from a standard deck without replacement) has ...

> $|S| = {52 \choose 13}$.

1. 3 aces.

    > $|A| = {4 \choose 3}{48 \choose 10}$. Therefore $P(A) = \frac{{4 \choose 3}{48 \choose 10}}{52 \choose 13}$.

2. At least 1 ace.

    > Consider the complement. $|A^c| = {48 \choose 13}$. Therefore $P(A) = 1 - \frac{48 \choose 13}{52 \choose 13}$.

3. 6 spaces, 4 hearts, 2 diamonds, 1 club.

    > $|A| = {13 \choose 6}{13 \choose 4}{13 \choose 2}{13 \choose 1}$. Therefore $P(A) = \frac{{13 \choose 6}{13 \choose 4}{13 \choose 2}{13 \choose 1}}{52 \choose 13}$.

For verifying your answer when counting across disjoint unions, adding up the top and bottom numbers for the ${n \choose k}$ in $|A|$ should add up to $|S|$.

Example (*Team captain problem*): Show that ${n \choose k} \cdot k = {n -1 \choose k - 1} \cdot n$.

> We are either picking the team first and then choosing the captain, or the other way around.

Example (*Vandermonde's Identity*): Show that ${n + m \choose k} = \sum_{i = 0}^k {n \choose i}{m \choose k - i}$ for non-negative integers $n, m, k$.

## Inclusion Exclusion Principle

> $$P(\cup_{i = 1}^n A_i) = \cup_{i} P(A_i) - \cup_{i < j} P(A_iA_j) + \cup_{i < j < k}P(A_iA_jA_k) - ...$$

Example: Suppose that 2 fair 6 sided dce are rolled. What is the probability that at least 1 of the dice shows a 6?

> $P(A) = 1 - P(A^c) = 1 - (\frac{5}{6})^2 = 1 - \frac{25}{36} = \frac{11}{36}$.

Example: There are 6 stops on the subway and 4 passengers on the subway car. Assume the passengers are equally likely to get off at any stop. Find the probability that:

> $|S| = 6^4$.

1. The passengers all get off at different stops.
2. 2 passengers get off at stop 2 and 2 passengers get off at stop 5.
3. 2 passengers get off at 1 stop and the other 2 passengers get off at another 1 stop.

    > $|A| = {6 \choose 2}{4 \choose 2}{2 \choose 2}$.

Example: 5 tourists plan to attent Octoberfest. There are 7 locations possible. Find the probability that:

> $|S| = 7^5$

1. All tourist attend different locations.
2. The tourists all attend the same location.
3. 2 tourists attend 1 location and 3 tourists attend another location.

    > $|A| = {7 \choose 2} \cdot 2 \cdot {5 \choose 2}{3 \choose 3} = 7 \cdot 6 \cdot {5 \choose 2}{3 \choose 3}$.

Example: Consider rearranging the "NOOB" at random. Let $A$ represent the event that two "O"s appear together, and let $B$ denote the event that the word starts with the letter $N$. Determine.

1. $P(A) = \frac{3!}{\frac{4!}{2!}} = \frac{1}{2}$
2. $P(B) = \frac{3!}{4!} = \frac{1}{4}$
3. The probability that the resulting word does not start with "N" and that the "O"s do not appear together. $P(\overline{A} \cap \overline{B}) = P(\overline{A \cup B})$.

Two events $A$ and $B$ are said to be **indepenedent** if $P(A \cap B) = P(A)P(B)$.

Example: Consider rolling 2 fair 6 sided dice. $A$ is the event where the sum is 10. $B$ is the event that the first die rolls a 6. $C$ is the event that the sum is 7. Are $A$ and $B$ independent?

> $B = \{(6, i) \mid i \in \{1, ..., 6\}\}$. $A = \{(5, 5), (6, 4), (4, 6)\}$. We can see that $A$, $B$ are not independent.

If *knowing* $A$ restricts our choices for $B$, they are not independent.

Two events $A$ and $B$ are **mutually exclusive** if $A$ and $B$ are disjoint.

**Proposition**: Suppose that not both $A$ and $B$ are trivial events. If $A$, $B$ are indepenent **and** mutually exclusive, then either $P(A) = 0$ or $P(B) = 0$.

**Proposition**: If $A$ and $B$ are independent, then $\overline{A}$ and $\overline{B}$ are independent, $A$ and $\overline{B}$ are independent, and $\overline{A}$ and $B$ are independent.

**Definition**: Conditional probabilty of $A$ given $B$, so long as $P(B) > 0$, is denoted by $P(A \mid B) = \frac{P(A \cup B)}{P(B)}$.

**Definition**: For events $A$ and $B$, $P(A \cap B) = P(A \mid B)P(B) = P(B \mid A)P(A)$.

**Bayes Theorem**: $P(B_i | A) = \frac{P(A|B_i)P(B_i)}{\sum_{j = 1}^k P(A | B_j)P(B_j)}$

Example: Pick Pharah, 20% chance of loss. Pick Winston, 10% chance of loss. Pick Winston 70% of the time, Pharah 30% of the time. Given that the game was lost, what is the probability that Pharah was picked?

> Let $P$ be the event that Pharah is picked. Let $L$ be the event where the game is lost. Let $W$ be the event that Winston is picked.
> $$\begin{aligned}P(P| L) &= \frac{P(L| P)P(P)}{P(L)} \\ &= \frac{0.2 \cdot 0.3}{P(L| P)P(P) + P(L| W)P(W)} \\ &= \frac{0.2 \cdot 0.3}{0.2 \cdot 0.3 + 0.1 \cdot 0.7} \\ &= 0.461
> 5\end{aligned}$$

**Probablity Function**: $f_X(x) = P(X = x)$.

1. $0 \le f_X(x) \le 1$.
2. $\sum_{x \in X(S)}f_X(x) = 1$.

**Cumulative Distribution Function (*CDF*)**: $F_X(x) = P(X \le x)$, $x \in \mathbb{R}$. We can use $P(X \le x) = P(\{\omega \in S: X(\omega) \le x\})$.

1. $0 \le F_X(x) \le 1$.
2. $F_X(x) \le F_X(y)$ for $x < y$.
3. $\lim_{x \to -\infty}F_x(x) = 0$, and $\lim_{x \to \infty}F_X(x) = 1$.

Example: $N$ balls labelled $1, 2, ..., N$ are placed in a box, and $n \le N$ are randomly selected without replacement. Find $P(X = x)$ where random variable $X$ is the largest number selected.

> **pdf**: There is only 1 way to select $x \in \{1, ..., n\}$. There are ${x - 1 \choose n - 1}$ ways to pick the remaining $n - 1$ balls. $P(X = x) = \frac{x - 1 \choose n - 1}{N \choose n}$, $x \ge n$. $P(X \le x) = \frac{x \choose n}{N \choose n}$, $x \ge n$.
>
> Now we use the property of **pdf**.
> $$\begin{aligned}P(X = x) &= F(x) - F(x - 1) \\ &= \frac{x \choose n}{N \choose n} - \frac{x - 1 \choose n}{N \choose n} \\ &= \frac{x - 1 \choose N - 1}{N \choose n}\end{aligned}$$

Example: Suppose a tack when flipped has probability $0.6$ of landing point up. If the tack is flipped $10$ times, what is the probability it lands point up more than twice?

> $X \in \{0, 1, 2, ..., 10\}$, $X \sim Bin(n = 10, p = 0.6)$   .
>
>  We want $P(X \ge 3) = 1 - P(X < 2) = 1 - (0.6^{10} + {10 \choose 1}0.6^9 0.4 + {10 \choose 2}0.6^8 0.4^2)$.

Example: Suppose a fair coin is flipped 17 times. Let $X$ denote the number of heads observed, and let $Y$ denote the number of tails observed. Which of the following is false?

> - $X \sim Binomial(17, 0.5)$.
> - $Y \sim Binomial(17, 0.5)$.
> - $X \sim Y$ (*X follows the distribution of Y*).
> - $X + Y = 17$.
> - $X = Y$ (*False, because RV quantity is not fixed*).

Example: Weekly lottery has a probability of 0.02 of winning a prize with a single ticket. If you buy one ticket per week for 52 weeks, what is the probability that you ...

> $X \sim Bin(n=52, p=0.02)$.

1. Win no prizes?

    > We want $P(X = 0) = 0.98^{52}$.

2. Win 3 or more prizes?

    > We want $P(X \ge 3) = 1 - (P(X = 0) + P(X = 1) + P(X = 2))$.

Binomial and hypergeometric distributions are fundamentally different, as the former picks with replacement, whereas the latter picks without replacement.

**Theorem**: If $r$ and $N$ relatively larger than $n$ and $\frac{r}{N} = p$ where $p \in [0, 1]$, then if $X \sim Hypergeometric(N, r, n)$ and $Y \sim Binomial(n, p)$ then $P(X \le k) \approx P(Y \le k)$.

Example: In Overwatch there are 27 playable characters, of which 6 are considered "Tanks". Suppose that three characters are drawn at random.

1. What is the probability that the selection contains exactly 2 tanks.

    > We want $P(T = 2) = \frac{{6 \choose 2}{21 \choose 1}}{27 \choose 3} \approx 0.1077$.

2. Approximate this probability using binomial distribution.

    > $T_{Bin} \sim Bin(3, \frac{6}{27})$.  
    >
    > We want $P(T_{Bin} = 2) = {3 \choose 2}(\frac{6}{27})^2(\frac{21}{27}) \approx 0.1152$.

## Negative Binomial
Question: We want the number of tails until you get the first head.
$$P(X = x) = (1-p)^xp,\ x = 0,1...$$

Question: If I model the total number of coin flips until I get the first head, is this also a geometric distribution? **Yes** because it is essentially the same as the last question.

We generalize to $k$ successes by noticing that the last trial must produce the $k$th success and the remaining $k-1$ successes may appear anywhere from the $1$st to $2$nd last trial.
$${r + k - 1 \choose k - 1}p^k(1-p)^r$$

Example: There is a 50.4% change of flipping a head. What is the probability that you need more than 5 flips to get a tail?

> $1 - P(X \le 4) = 1 - \sum_{x = 0}^4 0.504^x (1 - 0.504)$.;

Exampe: Hanzo is getting more popular. Every time I join a new game, I have a 15% change of picking Hanzo. What is the probability that ...

> Let $W$ be the number of games played before I pick Hanzo. $W \sim Geo(0.15)$. We have $f_W(w) = (1-p)^wp$, $w \in \mathbb{N}_0$.

1. I will need to play 4 games before I get to pick Hanzo?

    > $P(W = 4) = f_w(4) = (0.85)^40.15 = 0.0783$.

2. I will need to play at least 4 games before I get to pick Hanzo, given that I have to play at least 3 games before I pick him?

    > $(P(W \ge 4 | W \ge 3) = \frac{P(W \ge 4 \cap W \ge 3)}{P(W \ge 3)} = \frac{P(W \ge 4)}{P(W \ge 3)} = 0.85$.
    >
    > $$\begin{aligned}P(W \ge w) &= \sum_{t=w}^\infty (1-p)^tp \\ &= p(1-p)^w\sum_{t=0}^\infty (1-p)^t \\ &= p(1-p)^w\frac{1}{1 - (1-p)} \\ &= (1-p)^w\end{aligned}$$

3. I will need to play at least one game before I get to pick Hanzo?

    > $P(W \ge 1) = 1 - P(W = 0) = 1 - p = 0.85$.

## Memoryless Property of Geometric
Let $X \sim Geo(p)$ and $s, t$ be non-negative integers.
$$P(X \ge s + t | X \ge s) = P(X \ge t)$$

Example: Mobile game "Show Me The Money". Game released super rate item which only appears from a loot box which costs $2 per box, with the change of 0.01%.

> Let $X$ be the number of boxes without the rare item.

1. What is the probability that he will need to buy 50 loot boxes to get 2 super rate items?

    > Number of success is fixed but not the number of trials, so we use negative binomial. $X \sim NB(2, 0.0001)$.     
    >
    > We want $P(X = 48) = {48 + 2 - 1 \choose 2 - 1}(0.9999)^{48}(0.0001)^2 = 0.000000488$.

# Poisson
We say that a random variable $X \sim Poisson(\lambda)$ if we have $f_X(x)$ such that.
$$f_X(x) = e^{-\lambda}\frac{\lambda^x}{x!}$$

We verify that this is a valid probability distribution using the exponential series.
$$\begin{aligned}
\sum_{x=0}^\infty f_X(x) &= \sum_{x=0}^\infty e^{-\lambda}\frac{\lambda^x}{x!} \\
&= e^{-\lambda}e^\lambda \\
&= 1
\end{aligned}$$

One way to view poisson is to consider the limiting case of binomial, where you fix $\lambda = np$, and let $n \to \infty$ and $p \to 0$.

## Poisson Process

1. **Independence**: the number of occurrences in non-overlapping intervals are independent.

2. **Individuality**: for sufficiently short periods of time, $\Delta t$, the probability of two or more events occurring in the interval approaches zero.

$$\lim_{\Delta t \to 0} \frac{P(\text{2 of more events in } (t, t + \Delta t))}{\Delta t} = 0$$

3. **Homogeneity or Uniformity**: events occur at a uniform or homogenous rate $\lambda$ and proportional to time interval $\Delta t$.

$$\lim_{\Delta t \to 0} \frac{P(\text{one event in } (t, t + \Delta t)) - \lambda \Delta t}{\Delta t} = 0$$

A process that satisfies the prior conditions on the occurrence of events is often called a **Poisson Process**. More precisely, if $X_t$, for $t \ge 0$, denotes the number of events that have occurred up to time $t$, then $X_t$ is called a **Poisson Process**.

Example: Website hits for a given website occur according to a Poisson process with a rate of 100 hits per minute. Find ...

1. $P(\text{1 hit is observed in a second}) = \frac{e^{-\frac{5}{3}}\frac{5}{3}^1}{1!}$
2. $P(\text{90 hits are observed in a minute}) = \frac{e^{-100}100^{90}}{90!}$

## Relation to Binomial

Consider one unit of time, so that the process follows $Poi(\lambda)$.

We chop up the interval into $n$ equally-sized pieces. If we chop it up finely enough, then by individuality, the probability of two or more events occurring goes to 0.

This means that, over a small enough size, we approximately have either 0 or 1 event occurring with $P(event) = p$ for every piece.

Moreover, the event probability $p$ is proportional to the length of the interval by homogeneity. This means that as $n \to \infty$, $p \to 0$.

Finally, by independence, each $n$ pieces are independent, so we have $Bin(n, p)$, where $n$ is very large and $p$ is very small.

We expect to see $np$ events, recall that rate $\lambda$ is the rate of occurrence over 1 unit of time. So $\lambda = np$, and as $n \to \infty$, $p \to 0$, in $Bin(n, p)$, we approach $Poi(np)$.

Example: A bit error occurs got a given data transmission method independently in out of of every 1000 bits transferred. Suppose a 64 bit message is sent using the transmission system.

1. What is the probability that there are exactly 2 bit errors?

    > $X \sim Bin(64, \frac{1}{1000})$, $P(X = 2) = {64 \choose 2}(\frac{999}{1000})^{62} (\frac{1}{1000})^2 \approx 0.019$.

2. Approximate using Poisson.       

    > $X \sim Poi(\frac{64}{1000})$, $P(X = 2) = \frac{e^{-\frac{64}{1000}}(\frac{64}{1000})^2}{2!} \approx 0.019$.

Example: Shiny versions of Pokemon are possible to encounter and catch starting in Generation 2 (Pokemon Gold / Silver).  Normal encounters with Pokemon while running in grass occur according to a Poisson process with rate 1 per minute on average. 1 in every 8192 encounters will be a Shiny Pokemon, on average.

1. If you run around in the grass for 15 hours, what is the probability you will encounter at least one Shiny Pokemon?

> $X \sim Poi(\frac{900}{8192})$. $P(X \ge 1) = 1 - P(X = 0) = 1 - e^{-\frac{900}{8192}}$. 

2. How long would you have to run around in grass to have better than 50 percent chance of encountering at least one Shiny Pokemon?

> Solve for $t$, where $0.5 = P(X_t \ge 1)$.

Example: An infinite number of Harolds are released in a gold mine. They scatter randomly, so that on average, a gold nugget is surrounded by 6 Harolds. Assume that all gold nuggets are of equal size.

> Let $H$ be the number of Harolds surrounding the nugget. $H \sim Poi(\lambda = 6\ Harolds / nugget)$.

1. What is the probability that a nugget is surrounded by more than 3 Harolds?

    > $$\begin{aligned}P(H > 3) &= 1 - P(H <= 3) \\ &= 1 - f(0) - f(1) - f(2) - f(3) \\ &=  0.8488 \\ f(x) &= \frac{e^{-6}6^x}{x!}\end{aligned}$$
    
2. When 10 nuggets are picked at random, what is the probability that 8 of those nuggets have more than 3 Harolds?

    > $Bin(n=10, p=0.8488)$. $P(N=8) = {10 \choose 8}(0.8488)^8(1-0.8488)^2$.

3. On 2 nuggets there are $t$ Harolds in total. What is the probability that $x$ of them are on the first of the two nuggets?

    > Let $A$ be the event that there are $t$ Harolds on 2 nuggets. Let $B$ be the event that there are $x$ Harolds on the first nugget. $P(B|A) = \frac{P(A \cap B)}{P(A)}$. Where $A \cap B$ is the event where $x$ Harolds are on the first nugget, and $t-x$ Harolds are on nugget 2.
    >
    > These events are independent, so $P(A \cap B) = \frac{e^{-6}6^x}{x!} \cdot \frac{e^{-6}6^{t-x}}{(t-x)!} = \frac{e^{-12}6^t}{x!(t-x)!}$.
    >
    > We can double the original rate, $Poi(12)$ for the denominator. So $P(A) = \frac{e^{-12}12^t}{t!}$.
    >
    > So $P(B|A) = {t \choose x}\frac{1}{2}^t$.

If you order a set of random variables, they become **order statistics**.

Question: Let $X_1, X_2, X_3$ denote the random variables for the outcome of three independent fair random number generators. Assume that their ranges are $\{1, 2, ..., 10\}$. Now let $X_{max}$ denote the maximum value, then $P(X_{max} \le x) = P(X_1 \le x)P(X_2 \le x)P(X_3 \le 3)$.

# Expectation

**Definition**: Let $x_1, x_2, ..., x_n$ be outcomes of random variable $X$. Its **sample mean** is defined as $\overline{x} = \frac{\sum_{i=1}^nx_i}{n}$.

We can calculate a theoretical mean of $X$ directly if we know its distribution. Suppose $X$ is a discrete random variable with probability function $f(x)$, then $E(X)$ is called the **expected value** of $X$ and is defined by $E(X) = \sum_{x \in X(S)}xf(x)$. The expected value is sometimes referred to as the **mean**, **expectation**, or **first moment** of $X$.

Example: A lottery is conducted in which 7 numbers are drawn without replacement between the numbers 1 and 50. A player wins the lottery if the numbers selected on their ticket match all 7 of the drawn numbers.  A ticket to play the lottery costs $1, and the jackpot is valued at $5000000.  Compute the expected return.

> If you win the lottery, the return is 4999999. If you did not win, the return is -1. Let $R$ denote the return amount. $E(R) = (-1)P(\overline{w}) + (4999999)P(w) < 0$.

## "Law of the Unconscious Statistician"

If $g: \mathbb{R} \to \mathbb{R}$, then for a random variable $X$ with probability function $f(x)$, the expected value of $g(x)$ is given be $\sum_{x \in S(X)}g(x)f(x)$.

To retrieve our original expectation function, we set $g(x) = x$.

Example: If $g(x) = x^2$ and $X$ is the result of a fair six sided die roll, then compute $E[g(X)]$.

> $E[g(x)] = E[x^2] = \sum_{x = 1}^6 x^2 \frac{1}{6}$.

## Linearity of Expectation

If $g(x)$ is a linear function $g(x) = ax + b$, then for a random variable $X$, $E[aX + b] = aE[X] + b$.

> $$\begin{aligned}E[aX + b] &= \sum_{x \in X(S)}(ax + b)f(x) \\ &= a\sum_{x \in X(S)}xf(x) + b\sum_{x \in X(S)} \\ &= aE[x] + b\end{aligned}$$

Note: It is **not true** in general that $g(E[X]) = E[g(X)]$.

An extension of linearity is, $E[af(X) + bg(X)] = aE[f(X)] + bE[g(X)]$.

## Expectation of Binomial

> If $X \sim Bin(n, p)$ then $E[X] = np$.

$$\begin{aligned}
E[X] &= \sum_{x = 0}^n xf(x) \\
&= \sum_{x = 1}^n xf(x) \\
&= \sum_{x = 1}^n x \frac{n!}{x!(n-x)!}p^x(1-p)^{n-x} \\
&= \sum_{x=1}^n \frac{n(n-1)!}{(x-1)!((n-1) - (x-1))!}pp^{x-1}(1-p)^{(n-1)-(x-1)} \\
&= np(1-p)^{n-1} \sum_{x=1}^n \left({n - 1 \choose x-1}p^{x-1}(1-p)^{-(x-1)} \right) \\
&= np(1-p)^{n-1} \sum_{x=1}^n \left( {n-1\choose x-1} \left(\frac{p}{1 - p}\right)^{x-1} \right) \\
&= np(1-p)^{n-1} \sum_{y=0}^{n-1} \left( {n-1\choose y} \left(\frac{p}{1 - p}\right)^{y} \right) \\
&= np(1-p)^{n-1} \left(1+\frac{p}{1-p}\right)^{n-1} \\
&= np(1-p)^{n-1} \left(\frac{1}{1-p}\right)^{n-1} \\
&= np
\end{aligned}$$

Example: Suppose two fair six sided die are independently rolled 24 times, at let $X$ denote the number of times the sum of die rolls is 7. Compute $E[X]$.

> 36 outcomes, 6 yield a sum of 7, so $p = \frac{1}{6}$. We are rolling 24 times, so $n = 24$. We have $E[X] = np = 4$.

## Expectation of Poisson

> If $Y \sim Poi(\lambda)$, then $E[Y] = \lambda$.

$$\begin{aligned}
E[Y] &= \sum_{y \ge 0}yf(y) \\
&= \sum_{y \ge 1}y\frac{e^{-\lambda}\lambda^y}{y!} \\
&= \sum_{y \ge 1}\frac{e^{-\lambda}\lambda \lambda^{y-1}}{(y-1)!} \\
&= e^{-\lambda}\lambda \sum_{y \ge 1}\frac{\lambda^{y-1}}{(y-1)!} \\
&= e^{-\lambda}\lambda \sum_{z \ge 0}\frac{\lambda^{z}}{z!} \\
&= e^{-\lambda}\lambda e^{\lambda} \\
&= \lambda
\end{aligned}$$

Example: Suppose that calls to Canadian Tire Financial call center follow a Poisson process with rate 30 calls per minute. Let $X$ denote the number of calls to the center after 1 hour. Compute $E[X]$.

> $E[X] = 30 * 60$.

## Expectation of Hypergeometric

> If $X \sim hyp(N, r, n)$, then $E[X] = n\frac{r}{N}$.

## Expectation of Negative Binomial 

> If $Y \sim NB(k, p)$, then $E[Y] = \frac{k(1-p)}{p}$.

# Variability

Expectation along may not be enough. Oftentimes, we want to study how much a random variable tends to deviate from its mean.

1. **Deviation**: $E[X - \mu] = E[X] - \mu$.
2. **Absolute Deviation**: $E[|X - \mu|]$.
3. **Squared Deviation**: $E[(X - \mu)^2]$. Turns out to be a useful measure of variability.

## Variance

The **variance** of a random variable $X$ is denoted $Var(X)$ and is defined by $Var(X) = E[(X - E[X])^2]$. A simple calculation gives the *short cut formula*, $Var(X) = E[X^2] = E[X]^2$.

$$\begin{aligned}
E[(X - E[X])^2] &= E[X^2 - 2XE[X] + E[X]^2] \\
&= E[X^2] - 2E[X]^2 + E[X]^2 \\
&= E[X^2] - E[X]^2
\end{aligned}$$

We know that $E[(X - E[X])^2] \ge 0$ so we can say that $E[X^2] - E[X]^2 \ge 0$.

### Variance of Linear Combination

For any random variable $X$ and $a, b \in \mathbb{R}$.

$$ Var(aX + b) = a^2Var(X)$$

**Proposition**: $Var(X = 0)$ if and only if $P(X = E[X]) = 1$.

Example: Let $X$ denote the outcome of a fair six sided die. Compute $Var(X)$.

> **Recall**: $Var(X) = E[X^2] - E[X]^2$.   
> We know $X \in \{1, .., 6\}$, $X^2 \in \{1, ..., 36\}$.
>
> $E[X] = 3.5 = \frac{7}{2}$.   
> $E[X^2] = \sum x^2f(x) = \frac{1}{6}(1 + 4 + 9 + 16 + 25 + 36) = \frac{91}{6}$.
> So, $Var(X) = \frac{91}{6} - \frac{49}{4}$.

## Standard Deviation

> **Note**: $Var(X)$ is a squared unit. To recover the original unit, we take the square root of variance.

We define the **standard deviation** of a random variable $X$ as $SD(X)$, where $SD(X) = \sqrt{Var(X)}$.

## Variability of Binomial

> Suppose that $X \sim Bin(n, p)$. Then $Var(X) = np(1-p)$.

## Variability of Poisson

> Suppose that $X \sim Poi(\lambda)$. Then $Var(X) = \lambda$.

Example: Suppose that $X_n$ is binomial with parameters $n$ and $p_n$, so that $np_n \to \lambda$ as $n \to \infty$. If $Y \sim Poi(\lambda)$, show that $\lim_{n \to \infty} Var(X_n) = Var(Y)$.

## Variability of Hypergeometric

> Suppose that $X \sim hyp(N, r, n)$. Then $Var(X) = n\frac{r}{N}(1 - \frac{r}{N})(\frac{N - n}{N - 1})$.

## Variability of Hypergeometric

> Suppose that $Z \sim NB(k, p)$. Then $Var(Z) = \frac{k(1-p)}{p^2}$.

Example: Suppose $X_n$ is binomial with parameters $n$ and $p_n$ so that $np_n \to \lambda$ as $n \to \infty$. If $Y \sim Poi(\lambda)$, show that $\lim_{n \to \infty}Var(X_n) = Var(Y)$.

> **Recall**: $Var(X_n) = np_n(1-p_n)$. We also know that $\lim_{n \to \infty} np_n = \lambda$ and $\lim_{n \to \infty}(1 - p_n) = 1$. We can use the limit law.
> $$\begin{aligned}\lim_{n \to \infty} Var(X_n) &= \lim_{n \to \infty}np_n \lim_{n \to \infty}(1-p_n) \\ &= \lambda \\ &= Var(Y)\end{aligned}$$

# Skewness

$$E\left[\left(\frac{X - E[X]}{SD(X)}\right)^3\right]$$

# Kurtosis

$$E\left[\left(\frac{X - E[X]}{SD(X)}\right)^4\right]$$

**Remark**: There exists distributions without expectation. Suppose $X$ is a random variable with $f_X(x) = \frac{6}{(\pi x)^2}$. Then $E(X) = \infty$ and $Var(X)$ is not defined.

Example: Let $X \sim Geo(p)$. Compute $E[X]$.

> $f(x) = p(1-p)^x$, $x = 0, 1, 2 , ...$.
> $$\begin{aligned}E[X] &= \sum_{x \ge 1} xp(1-p)^x \\ &= p(1-p)\sum_{x \ge 1}x(1-p)^{x-1}\end{aligned}$$
> **Note**: $\frac{d}{d(1-p)} \frac{1}{1 - (1-p)} = \sum_{x \ge 1} x(1-p)^{x-1}$.
>
> $$\begin{aligned}E[X] &= p(1-p) \frac{d}{d(1-p)} \frac{1}{1 - (1-p)} \\ &= p(1-p)\frac{1}{p^2} \\ &= \frac{1-p}{p}\end{aligned}$$

> $f(x) = p(1-p)^x$, $x = 0,1,2...$.
> $$\begin{aligned}\sum_{x \ge 1}P(X \ge x) &= \sum_{x \ge 1}(1-P(X \le x-1)) \\ &= \sum_{x \ge 1}(1-(1-(1-p)^x)) \\ &= \frac{1-p}{1 - (1-p)} \\ &= \frac{1-p}{p}\end{aligned}$$

**Theorem**: Darth Vader Rule. Let $X$ be a non-negative discrete random variable.

$$E[X] = \sum_{x = 1}^\infty P(X \ge x) = \sum_{x \ge 0}P(X > x)$$

Example: A person plays a game in which a fair coin is tossed until the first tail occurs. The person wins $\$2^x$ if $x$ tosses are needed for $x = 1,2,3,4,5$ but loses $\$256$ if $x > 5$.

1. Determine the expected winnings.

    > Let $W$ be the amount of winnings. $W = \begin{cases}2^x, &X = 1, 2,...5 \\ -256, &x > 5\end{cases}$. $W$ is a function of $X \sim Geo(p=\frac{1}{2})$. By law of unconcious statistician.
    > $$\begin{aligned}E[W] &= \sum_{x = 1}^5 2^x P(X = x) - 256P(X > 5) \\ &= 2p + 2^2p(1-p) + ... 2^5p(1-p)^4 - 256(1-p)^5 \\ &= 1 + 1 + 1 + 1 + 1 - \frac{2^8}{2^5} \\ &= 5 - 8 \\ &= -3\end{aligned}$$

2. Determine the variance of the winnings.

    > $$\begin{aligned}Var(W) &= E[W^2] - E[W]^2 \\ &= 2101 \text{ Dollars}^2\end{aligned}$$

Example: Yasmin and Zack are BMath students taking the exact same courses. Let $X$ be the number of assignments that they have in one week. The probability function of $X$ is.

$x$ | 0 | 1 | 2 | 3 | 4 | 5
---|---|---|---|---|---|---
$f(x)$ | 0.09 | 0.1|0.25|0.4|0.15|0.01

Yasmin drinks $2X^2$ cups per week and Zack drinks $|2X - 1|$ cups per week.

1. Compute the expected number of cups that Yasmin and Zack individually drink in a week.

    > $E[2X^2] = \sum_{x = 0}^5 2x^2 P(X = x)$
    >
    > $E[|2X-1|] = \sum_{x = 0}^5 |2x - 1|P(X = x)$.

2. Compute the variance individually.

# Continuous Random Variables

## Expectation

If $X$ is a continuous random variable with pdf $f(x)$ and $g: \mathbb{R} \to \mathbb{R}$.

$$E[g(X)] = \int_{-\infty}^\infty g(x)f(x)dx$$

$$\begin{aligned}Var(X) &= E[(X - E[X])^2] \\ &= \int_{-\infty}^\infty(x-E[X])^2 f(x)dx \\ &= E[X^2] - E[X]^2\end{aligned}$$

Example: $X$ has pdf $f(x) = \begin{cases}6x(1-x), &0 \le x \le 1 \\ 0, &\text{otherwise}\end{cases}$. Compute $E[X]$.

> $$\begin{aligned}E[X] &= \int_0^1 xf(x)dx \\ &=\int_0^1 x(6x-1)dx \\ &= 6\int_0^1 x^2 - x^3 dx \\ &= 6\left[\frac{x^3}{3} - \frac{x^4}{4}\right]_0^1 \\ &= 6\left(\frac{1}{3} - \frac{1}{4}\right) \\ &= \frac{1}{2} \end{aligned}$$

Question: Suppose $X$ has pdf $f(x)$ and $f$ is an even function around the origin on $\mathbb{R}$. If $E[X]$ is well defined, what can we say about it?

> $E[X] = 0$.

Example: Suppose $X$ has CDF $F(x) = \begin{cases}0, &x<0\\\frac{x^2}{2}, &0\le x<\frac{1}{2} \\ \frac{7x}{4} - \frac{3}{4}, &\frac{1}{2} \le x < 1 \\ 1, &x \ge 1 \end{cases}$. Compute $E[X]$ and $Var(X)$.

> We are given **cdf**, but $f(x) = \frac{d}{dx} F(x)$, so we can obtain the pdf.
>
> $f(x) = \begin{cases}0, &x < 0\\x, &0\le x < \frac{1}{2} \\ \frac{7}{4} &\frac{1}{2} \le x < 1 \\ 0, &x \ge 1\end{cases}$.
>
> $$\begin{aligned}E[X] &= \int_0^1 xf(x)dx \\ &= \int_0^\frac{1}{2}x^2dx + \int_\frac{1}{2}^1 \frac{7x}{4}dx \\ &= \left(\frac{x^3}{3}\right)_0^\frac{1}{2} + \left(\frac{7x^2}{8}\right)_\frac{1}{2}^1 \\ &= 0.6979\end{aligned}$$

If we have a function $g$ which has an inverse over the range of $X$, then we have a fairly easy way of obtaining $Y = g(X)$. In short, the method is as follows.

1. Write the CDF of $Y$ as a function of $X$.
2. Use the CDF of $X$ to find the CDF of $Y$. If you want the pdf, take derivatives.
3. Find the range of $Y$.

Example: Let $X$ be a continuous random variable with the following pdf and cdf.

$$f(x) = \begin{cases}\frac{1}{4}, &0 < x \le 4\\ 0, &\text{otherwise}\end{cases}$$

$$F(x) = \begin{cases}1, &x \le 0\\ \frac{x}{4} &0<x< 4\\ 1, &x \ge 4\end{cases}$$

Find the pdf of $Y = X^{-1}$.

> $$\begin{aligned}P(Y \le y) &= P(\frac{1}{X} \le y) \\ &= P(\frac{1}{y} \le X) \\ &= 1 - P(X \le \frac{1}{y} \\&= 1 - F_x\left(\frac{1}{y}\right) \\ &= -f_x\left(\frac{1}{y}\right) \frac{d}{dy} \cdot \frac{1}{y} \\ &= -\frac{1}{4} \cdot \frac{-1}{y^2}, \text{ when } 0 < \frac{1}{y} \le 4 \\ &= \frac{1}{4y}, \text {when } \frac{1}{4} \le y < \infty\end{aligned}$$

## Continuous Uniform Distribution

We say that $X$ has a **continuous uniform distribution** on interval $(a, b)$ if $X$ has pdf $f(x) = \begin{cases}\frac{1}{b-a}, &x \in (a, b)\\ 0, &\text{otherwise}\end{cases}$.

This is abbreviated $X \sim U(a, b)$.

Example: Let $X \sim U(a, b). Show that $E[X] = \frac{a+b}{2}$ and the $V(X) = \frac{(b-a)^2}{12}$.

> $$\begin{aligned}E[X] &= \int_a^b x\frac{1}{b-a}dx \\ &= \frac{1}{b-a} \int_a^b xdx \\ &= \frac{1}{b-a}\left[\frac{x^2}{2}\right]_a^b \\ &= \frac{b^2 - a^2}{2(b - a)} \\ &= \frac{a+b}{2}\end{aligned}$$

## Exponential Distribution

We say that $X$ has an exponential distribution with parameter $\lambda$ ($X \sim \exp(\lambda)$) with $f(x)$.

$$f(x) = \begin{cases}\lambda e^{-\lambda x}, &x > 0 \\ 0, &x \le 0\end{cases}$$

Consider the CDF of $X$.

$$\begin{aligned}
F(x) &= P(X \le x) \\
&= 1 - P(\text{no occurrences between }(0, x)) \\
&= 1 - e^{-\lambda x} \\
\end{aligned}$$

We can then the derivative to obtain the pdf.

$$f(x) = \frac{d}{dx}F(x) = \lambda e^{-\lambda x}$$

We can use a $\theta$ parameterization of exponential distribution (where $\lambda = \frac{1}{\theta})$ where $\theta$ can represent the expected waiting time.

$$f(x) = \frac{1}{\theta}e^{-\frac{x}{\theta}}$$

**Theorem**: If $X$ is the time to the first event of Poisson process with parameter $\lambda$, then $X \sim \exp(\frac{1}{\lambda})$.

Example: Let $X \sim \exp(\theta)$. Find $E[X]$.

> By definition, $\int_0^\infty x \frac{1}{\theta} e^{-\frac{x}{\theta}} dx$.

> $$\begin{aligned}E[X] &= \int_0^\infty x \frac{1}{\theta} e^{-\frac{x}{\theta}} dx \\ &= \left(x \frac{1}{\theta} e^{-\frac{x}{\theta}}(-\theta)\right)_0^\infty - \int_0^\infty \frac{1}{\theta}e^{-\frac{x}{\theta}}(-\theta) dx \\ &= 0 + \theta \\ &= \theta \end{aligned}$$

> $$\begin{aligned}E[X^2] &= \left(x^2 \frac{1}{\theta} e^{-\frac{x}{\theta}} (-\theta)\right)_0^\infty \int_0^\infty 2x e^{-\frac{x}{\theta}} dx \\ &= 0 + \left(2xe^{-\frac{x}{\theta}}(-\theta)\right)_0^\infty + \int_0^\infty 2\theta e^{-\frac{x}{\theta}}dx \\ &= 0 + 0 + 2\theta^2 \\ &= 2\theta^2 \end{aligned}$$
> $Var(X) = E[X^2] - E[X]^2 = \theta^2$.

## Gamma Function

$$\Gamma(\alpha) = \int_0^\infty y^{\alpha-1}e^{-y}dy,\ \alpha > 0$$

- $\Gamma(\alpha) = (\alpha-1)\Gamma(\alpha-1)$, for $\alpha > 1$.
- $\Gamma(\alpha) = (\alpha - 1)!$, for $\alpha \in \mathbb{N}$
- $\Gamma(\frac{1}{2}) = \sqrt \pi$.

> $$\begin{aligned}E[X] &= \int_0^\infty x \frac{1}{\theta} e^{-\frac{x}{\theta}}dx \\ &= \int_0^\infty ye^{-y}\theta dy \\ &= \theta \int_0^\infty y^{2 - 1}e^{-y} dy \\ &= \theta \Gamma(2) \\ &= \theta(2 - 1)! \\ &= \theta\end{aligned}$$

> $$\begin{aligned}E[X^2] &= \int_0^\infty x^2 \frac{1}{\theta} e^{-\frac{x}{\theta}}dx \\ &= \int_0^\infty x \frac{x}{\theta} e^{-\frac{x}{\theta}} dx \\ &= \int_0^\infty \theta y^2 e^{-y} \\ &= \theta^2 \int_0^\infty y^{3-1} e^{-y} \\ &= \theta^2 \Gamma(3) \\ &= \theta^2 2! \\ &= 2\theta^2 \end{aligned}$$
> $Var(X) = E[X^2] - E[X]^2 = \theta^2$.

Example: Buses arrive according to Poisson process with an average of 3 buses per hour.

> Let $T$ be the waiting time for the first bus. $T \sim \exp(\theta = \frac{1}{3})$.

1. Find the probability of waiting at least 15 minutes.

    > $$\begin{aligned}P(T > \frac{1}{4} \text{hour}) &= 1 - P(T \le \frac{1}{4} \text{hour}) \\ &= 1 - F_t(\frac{1}{4}) \\ &= 1 - (1 - e^{-\frac{\frac{1}{4}}{\frac{1}{3}}}) \\&= e^{-\frac{3}{4}}\end{aligned}$$

2. Find the probability of waiting at least another 15 minutes given that you have already been waiting for 6 minutes.

    > $$\begin{aligned}P(T \ge 6 + 15 | T \ge 6) &= \frac{P(T \ge 6 + 15 \cap T \ge 6}{P(T \ge 6)} \\ &= \frac{P(T \ge 21)}{P(T \ge 6)} \\ &= \frac{e^{-\frac{63}{60}}}{e^{-\frac{18}{60}}} \\ &= e^{-\frac{45}{60}} \\ &= e^{-\frac{3}{4}}\end{aligned}

## Memoryless Exponential

> If $X \sim \exp(\theta)$, we have $P(X > s + t | X > s) = P(X > t)$.

- If a continuous random variable has memoryless property, it must follow exponential distribution.

# Normal

Example:

1. 75th percentile of the standard normal distribution.

    > We want $x$ such that $P(Z \le x) = 0.75$. In the $Z$ table, $P(Z \le 0.67) = 0.74857$ and $P(Z \le 0.68) = 0.75175$, so we know that $x \in [0.67, 0.68]$.

2. 58th percentile of the $N(5, 9)$ distribution.

    > Again, we want $x$ such that $P(X \le x) = 0.58$. So $P(Z \le \frac{x - 5}{3}) = 0.58$. We have $\frac{x - 5}{3} \in (0.2, 0.21)$. So $x \in [5.6, 5.63]$.

3. Let $Z \sim N(0, 1)$. Find $c$ such that $P(-c \le Z \le c) = 0.95$.

    > $$\begin{aligned}P(-c \le Z \le c) &= P(Z \le c) - P(Z \le -c) \\ &= 2P(Z \le c) - 1 \\ &= 0.95\end{aligned}$$
    > So $c = 1.96$.

An interesting empirical rule about normal distribution is the **68-95-99.7** rule, which states the probability of $P(\mu - \alpha \sigma \le X \le \mu + \alpha \sigma)$, for $\alpha \in \{1, 2, 3\}$ respectively.

# Inverse Transform Method

**Theorem**: Let $U \sim U(0, 1)$, and $X$ be a continuous random variable with cdf $F$. Then $F^{-1}(U)$ the same distribution as $X$.

# Multivariate Distributions

**Definition**: Suppose $X$ and $Y$ are discrete random variables defined on the same sample space. The **joint probability function** of $X$ and $Y$ is.

$$f(x, y) = P(\{X = x\} \cap \{Y = y\}), x \in X(S), y \in Y(S)$$

A shorthand for this is.

$$f(x, y) = P(X = x, Y = y)$$

Example: Two fair six sided die are rolled. Let $X$ denote the outcome of the first roll, and let $Y$ denote the outcome of the second die roll. Compute the joint probability of $X$ and $Y$.

> $X, Y$ are independent, so $f(x,y) = \frac{1}{36}$ for all $(x, y) in the same space.

## Properties of Joint Probability Function

1. $f(x, y) \ge 0$.
2. $\sum_{x, y}f(x, y) = 1$.

Example: Suppose a fair coin is tossed 3 times. Define the random variables $X$ as the number of heads, and $Y$ as whether a head occurred on the first toss. Find the joint probability function for $(X, Y)$.

## Marginal Probability Function

Suppose that $X, Y$ are discrete random variables. The **marginal probability function** of $X$ is.

$$f_X(x) = P(X = x) = \sum_{y \in Y(S)} f(x, y)$$

Example: Suppose $X, Y$ has joint probability function.

$$f(x, y) = \frac{1}{6}\left(\frac{1}{2}\right)^x \left(\frac{2}{3}\right)^y$$

1. Compute the marginal probability functions $f_X(x)$ and $f_Y(y)$.

    > $$\begin{aligned}f_X(x) &= \sum_{y}f(x,y) \\ &= \sum_{y = 0}^\infty \frac{1}{6}\frac{1}{2^x} \sum_{y = 0}^\infty \left(\frac{2}{3}\right)^y \\ &= \frac{1}{6} \frac{1}{2^x} \frac{1}{1 - \frac{2}{3}} \\ &= \frac{1}{2^{x+1}} \end{aligned}$$

2. Compute $P(X < Y)$.

    > $$\begin{aligned}P(X < Y) &= \sum_{x = 0}^\infty \left(\sum_{y = x + 1}^\infty f(x, y)\right) \\ &= \sum_{x = 0}^\infty \frac{1}{6} \frac{1}{2^x} \sum_{y = x + 1}^\infty \left(\frac{2}{3}\right)^y \\ &= \sum_{x = 0}^\infty 3\cdot \frac{1}{6} \frac{1}{2^{x}} \left(\frac{2}{3}\right)^{x + 1} \end{aligned}$$

## Conditional Probability Function

The **conditional probability function** of $X$ given $Y = y$ is denoted $f_X(x|y)$ and is defined to be.

$$f_X(x|y)= P(X = x | Y = y) = \frac{P(X = x, Y = y)}{P(Y = y)} = \frac{f(x,y)}{f_Y(y)}$$

**Proposition**: If $X \sim Poi(\lambda_1)$ and $Y \sim Poi(\lambda_2)$, then $T = X + Y \sim Poi(\lambda_1 + \lambda_2)$.

**Proposition**: If $X \sim Bin(n, p)$ and $Y \sim Bin(m, p)$ independently, then $T = X + Y \sim Bin(n + m, p)$.

## Multinomial Distribution

If $(X_1, X_2, .., X_k) \sim Mult(n, p_1, ..., p_k)$, then $X_j \sim Bin(n, p_j)$. Also, $X_i + X_j \sim Bin(n, p_i + p_j)$.

- In multinomial distribution, the trials are independent, but the marginal random variables are not! That is because $x_1 + ... + x_k = n$.

Suppose $X, Y$ are discrete random variables with joint probability function $f(x,y)$, Then for a function $g: \mathbb{R}^2 \to \mathbb{R}$ then $E[g(X, Y)] = \sum_{(x, y)}g(x,y)f(x,y)$. This generalizes to multiple variables.

Linearity of expectation carries through as well.

1. $E[ag_1(X,Y) + bg_2(X,Y)] = aE[g_1(X, Y)] + bE[g_2(X, Y)]$.
2. $E[X + Y] = E[X] + E[Y]$.

Example: Let $(X_1, X_2, X_3) \sim Mult(n, p_1, p_2, p_3)$. Show that $E[X_1X_2] = n(n-1)p_1p_2$.

> $$\begin{aligned}E[X_1X_2] &= \frac{1}{2}E[2X_1X_2] \\ &= \frac{1}{2}E[(X_1 + X_2)^2 - X_1^2 - X_2^2] \\ &= \frac{1}{2}(E[(X_1 + X_2)^2] - E[X_1^2] - E[X_2^2]) \\ &= \frac{1}{2}(Var(X_1 + X_2) + E[X_1 + X_2]^2 - Var(X_1) - E[X_1]^2 - Var(X_2) - E[X_2]^2) \\ &= \frac{1}{2}(n(p_1 + p_2)(1 - p_1 - p_2) + (n(p_1+p_2))^2 - np_1(1-p_1) - (np_1)^2 - np_2(1-p_2) - (np_2)^2) \\ &= n(n-1)p_1p_2\end{aligned}$$

# Covariance

If $X, Y$ are joint distribution, then $Cov(X, Y)$ denotes the **covariance** between $X, Y$.

$$Cov(X, Y) = E[(X - E[X])(Y - E[Y])]$$

Shortcut formula.

$$Cov(X, Y) = E[XY] - E[X]E[Y]$$

**Theorem**: If $X,Y$ are independent, then $Cov(X, Y) = 0$. The converse is **false** with counter example $X \sim N(0,1)$, $Y \sim X^2 - 1$.

## Correlation

The **correlation** of $X, Y$ is denoted $corr(X, Y)$.

$$corr(X, Y) = \rho = \frac{Cov(X, Y)}{SD(X)SD(Y)}$$

It follows from the Cauchy-Schawrz inequality that $-1 \le corr(X, Y) \le 1$ and if $|corr(X, Y)| = 1$, $X = aY + b$.

We say that $X, Y$ are uncorrelated if $Cov(X, Y) = 0$.

**Remark**: If $X, Y$ are independent, then $X, Y$ are uncorrelated.

**Remark**: $Cov(X, X) = Var(X)$.

1. $\rho = corr(X, Y)$ has the same sign as $Cov(X, Y)$.
2. $-1 \le \rho \le 1$.
3. $|\rho| = 1 \Rightarrow X = aY + b$.
4. $X, Y$ independent means that $corr(X, Y) = 0$.
5. $corr(X, X) = \frac{Cov(X, X)}{SD(X)^2} = \frac{Var(X)}{Var(X)} = 1$.

# Linear Combinations

Suppose $X_1, ..., X_n$ are jointly distributed RVs with joint probability function $f(x_1, ..., x_n)$. A **linear combination** of the RVs is any random variable of the form $\sum_{i = 1}^n a_i X_i$. Where $a_i \in R$.

$$E\left(\sum_{i = 1}^n a_i X_i\right) = \sum_{i = 1}^n a_iE(X_i)$$

Example: Let $P_1, ..., P_7$ represent number of cans of pop that Harold drinks each day. If each random variable has mean $\mu = 6$, what is the expected number of cans consumed during those 7 days?

> $$\begin{aligned}E[\overline{P}] &= E\left[\frac{1}{7}\sum_{i=1}^7 P_i\right] \\ &= \frac{1}{7}\sum_{i = 1}^7 6 \\ &= 6\end{aligned}$$

Example: Suppose $X \sim N(1, 1)$, $Y \sim U(0, 1)$. Compute $E(2X - 4Y)$.

> $E(2X - 4Y) = 0$.

**Proposition**: Let $X, Y, U, V$ be random variables and $a, b, c, d \in \mathbb{R}$.

$$Cov(aX + bY, cU + dV) = acCov(X, U) + adCov(X, V) + bcCov(Y, U) + bdCov(Y, V)$$

**Proposition**: Let $X, Y$ be random variables and $a, b \in \mathbb{R}$.

$$Var(aX + bY) = a^2Var(X) + b^2Var(Y) + 2abCov(X, Y)$$

In general,

$$Var(\sum_{i = 1}^n a_iX_i) = \sum_{i = 1}^n a_i^2 Var(X_i) + 2\sum_{1 \le i < j \le n}a_ia_jCov(X_i, X_j)$$

If $X, Y$ are independent, then $Var(aX  + bY) = a^2Var(X) + b^2Var(Y)$.

**Proposition**: A linear function of normal is normal. Let $X \sim N(\mu, \sigma^2)$ and $Y = aX + b$, $a, b \in \mathbb{R}$.

$$Y \sim N(a\mu + b, a^2 \sigma^2)$$

Let $X_i \sim N(\mu_i, \sigma_i^2)$ **independently**.

$$\sum_{i = 1}^n a_iX_i + b_i \sim N\left(\sum_{i = 1}^n a_i\mu_i + b_i, \sum_{i = 1}^n a_i^2\sigma_i^2\right)$$

**Proposition**: Sample mean of normal is normal. If all $X_i \sim N(\mu, \sigma^2)$ **independently**.

$$\sum_{i = 1}X_i \sim N(n\mu, n\sigma^2)$$

$$\overline{X} = \frac{1}{n}\sum_{i=1}^n X_i \sim N\left(\mu, \frac{\sigma^2}{n}\right)$$

Example: Compute $Var(\sum_{i=1}^n X_i)$ and $Var(\overline{X})$.

> $\begin{aligned}Var(\sum_{i = 1}^n X_i) &= \sum_{i = 1}Var(X_i) \\ &= n\sigma^2\end{aligned}$

> $\begin{aligned}Var(\overline{X}) &= \frac{1}{n^2}Var(\sum_{i = 1}^n X_i) \\ &= \frac{\sigma}{n}\end{aligned}$

# Indicator Variables

$$E[\mathbb{I}_A] = P(A)$$

$$E[\mathbb{I}_A^2] = P(A)$$

So,

$$Var(\mathbb{I}_A) = P(A)(1 - P(A))$$

Example: $N$ letters to $N$ different people, there are $N$ envelopes. One letter is put in each envelope at random. Find the mean and variance of the number of letters placed in the right envelope.

> Let $\mathbb{I}_i = \begin{cases}1, &\text{Letter is in the correct envelope}\\ 0, &\text{Otherwise}\end{cases}$
>
> This is an indicator RV. $P(\mathbb{I}_i) = \frac{1}{N}$. So $E[\mathbb{I}_i] = \frac{1}{N}$, $Var(\mathbb{I}_i) = \frac{1}{N}(1 - \frac{1}{N})$.
>
> Let $X = \sum_{i=1}^N \mathbb{I}_i$. Now we need $E[X]$ and $Var(X)$.
>
> $E[X] = \sum_{i=1}^NE[\mathbb{I}_i] = 1$.
>
> $$\begin{aligned}Var(X) &= Var(\sum_{i = 1}^n \mathbb{I}_i) \\ &= \sum_{i = 1}^N Var(\mathbb{I}_i) + \sum_{i \neq j} Cov(\mathbb{I}_i, \mathbb{I}_j) \\ &= (1 - \frac{1}{N}) + \sum_{i \neq j} (E[\mathbb{I}_i \mathbb{I}_j] - E[\mathbb{I}_i]E[\mathbb{I}_j]) \\ &= (1 - \frac{1}{N}) + \sum_{i \neq j} (P(\mathbb{I}_i = 1, \mathbb{I}_j = 1) - \frac{1}{N^2}) \\ &= (1 - \frac{1}{N}) + \sum_{i \neq j}(\frac{1}{N(N-1)} - \frac{1}{N^2}) \\ &= 1 \end{aligned}$$

# Life is Normal

**Proposition**: Law of **Large** Numbers. Let $X_i$ be independent and identically distributed random variables with mean $\mu$. Then their sample mean converges to the true mean.

$$\lim_{n \to \infty} \overline{X}_n = \mu$$

**Theorem**: Central Limit Theorem. Suppose that $X_i$ are independent random variables, with a common distribution function $F$. Suppose further than $E(X_i) = \mu$ and $Var(X_i) = \sigma^2 < \infty$. Then for all $x \in \mathbb{R}$ as $n \to \infty$.

$$P\left(\frac{\overline{X} - \mu}{\sigma / \sqrt n} \le x \right) \to \Sigma(x),$$

In other words, if $n$ is large.

$$\overline{X} \approx N(\mu, \frac{\sigma^2}{n}), \sum_{i = 1}^n X_i \approx N(n\mu, n\sigma^2)$$

Example: Eating a box of chocolate. Each box has 20 cubes  of chocolate. The weight of each cube varies. Weight $W$ of each cube is a random variable with mean $\mu = 25$ and $\sigma = 0.1$. Find the probability that the box has at least 500 grams of chocolate in it, assuming the weight of each cube is independent.

> $S_{20} = \sum_{i = 1}^{20} W_i$. By CLT, $S_{20} \approx N(20 \cdot 25, 20 \cdot 0.1^2)$.
>
> $$\begin{aligned}P(S_{20} \ge 500) &= P(Z_{20} \ge \frac{500 - 500}{\sqrt{0.2}}) \\ &= P(Z_{20} \ge 0)\end{aligned}$$

Example: Jason rolls a six sided die 1000 times, and records the results. If the die is a fair die, estimate the probability that the sum of the die is less than 3400.

> $E[X_i] = 3.5$, $Var(X_i) = 2.92$. By CLT, $S_{1000} = \sum_{X_i} \approx N(1000 \cdot 3.5, 1000 \cdot 2.92)$.
>
> $$\begin{aligned}P(S_{1000} < 3400) &= P(Z_{1000} < \frac{3400 - 3500}{\sqrt {2920}}) \\ &= 0.03216\end{aligned}$$

**Theorem**: If $X_n \sim Binomial(n, p)$, then for large $n$.

$$\frac{X_n - np}{\sqrt{np(1-p)}} \approx N(0,1)$$

**Theorem**: If $X_\lambda \sim Poi(\lambda)$, then for large $lambda$.

$$\frac{X_\lambda - \lambda}{\lambda} \approx N(0, 1)$$

When approximating discrete random variables with normal distribution, then discrete distribution will never be truly "normal". In this case, we use **continuity correction**.

$$\begin{aligned}
P(S_n = s) &\approx P(s - 0.5 < S_n < s + 0.5) \\
&\approx P\left(\frac{(s - 0.5) - \mu_{S_n}}{SD(S_n)} < Z < \frac{(s + 0.5) - \mu_{S_n}}{SD(S_n)}\right)
\end{aligned}$$

$$\begin{aligned}
P(a \le X \le b) &\approx P(a - 0.5 \le X \le b + 0.5) \\
&\approx P\left(\frac{(a - 0.5) - \mu_x}{SD(X)} \le Z \le \frac{(b + 0.5) - \mu_x}{SD(X)}\right)
\end{aligned}$$

Example: $X \sim Poi(\lambda)$. Use normal approximation to estimate $P(X = \lambda)$ and $P(X > \lambda)$. Compare this approximation with the true value when $\lambda = 9$.

> $$\begin{aligned}P(X = \lambda) &\approx P(\lambda - 0.5 \le X \le \lambda + 0.5) \\ &\approx P\left(\frac{(\lambda - 0.5) - \lambda}{\sqrt \lambda} \le Z \le \frac{(\lambda + 0.5) - \lambda}{\sqrt \lambda}\right) \\ &= P\left(\frac{-0.5}{\sqrt \lambda} \le Z \le \frac{0.5}{\sqrt \lambda}\right)\end{aligned}$$

> $$\begin{aligned}P(X > x) &\approx P(X \ge \lambda - 0.5) \\ &\approx P\left(Z \ge \frac{(\lambda - 0.5) - \lambda}{\sqrt \lambda}\right) \\ &=1 - P\left(Z < \frac{-0.5}{\sqrt \lambda}\right)\end{aligned}$$

Example: Suppose $X_1, .., X_50$ are independent Geometric random variables with parameter 0.5. Estimate the probability that $\overline{X}_50 > 6.5$.

> We want $P(\overline{X}_{50} > 6.55)$. We need $E[\overline{X}_{50}]$ and $SD(\overline{X}_{50})$.
>
> $\begin{aligned}E[\overline{X}_{50}] &= \frac{1}{50}\sum_{i = 1}^{50} E[X_i] \\ &= \frac{1}{50} \sum_{i=1}^{50} 1 \\ &= 1\end{aligned}$
>
> $\begin{aligned}Var(\overline{X}_{50}) &= \left(\frac{1}{50}\right)^2 \sum_{i = 1}^{50} Var(X_i) \\ &= \left(\frac{1}{50}\right)^2 \sum_{i = 1}^{50} 2 \\ &= \frac{1}{25} \end{aligned}$
>
> $\begin{aligned} P(\overline{X}_{50} > 6.5) &\approx P(\overline{X}_{50} > 6) \\ &\approx P\left(Z > \frac{(6 - 1)}{\sqrt \frac{1}{25}}\right) \\ &= 1 - P(Z < 25) \\ &\approx 0 \end{aligned}$

**Rules of Thumb**.

1. If the number of observations exceeds 30, then CLT provides a reasonable approximation.
2. If the distribution of observations is "close" to being unimodal and "close" to being continuous, then CLT can be reasonable for even smaller values of $n$.
3. If the distribution is highly screwed or very discrete, then a large value of $n$ might be necessary.
4. When approximating a **continuous** distribution with normal, we do not use continuity correction.

# Moment Generating Function

**Definition**: The **moment generating function** or MGF of a random variable $X$ is given by.

$$M_X(t) = E[e^{tX}], t \in \mathbb{R}$$

In particular, if $X$ is discrete with probability function $f(x)$, then.

$$M_X(t) = \sum_{x \in X(S)} e^{tx} f(x), t \in \mathbb{R}$$

**Properties**.

1. $$M_x(t) = \sum_{j = 0}^\infty \frac{t^j E[X^j]}{j!}$$
2. So long as $M_x(t)$ is defined in a neighbourhood of $t = 0$.

    $$\frac{d}{d_t^k}M_x(0) = E[X^k]$$

The significance of MGF is that, under certain conditions, it can show equivalence of two distributions.

**Proposition**: Continuity theorem. If $X, Y$ have MFGs $M_X(t), M_Y(t)$ defined in neighbourhoods of the origin, and satisfying $M_X(t) = M_Y(t)$ for all $t$ where they are defined.

$$X \stackrel{D}{=} Y$$

This means that the MGF uniquely characterises a distribution.

Example: Let $X \sim Poi(\lambda)$. Derive the MGF of $X$, and use it to show that $E[X] = \lambda = Var(X)$.

> $$\begin{aligned}M_X(t) &= E[e^{tx}] \\ &= \sum_{x = 0}^\infty e^{tx} P(X = x) \\ &= \sum_{x = 0}^\infty e^{tx} \frac{e^{-\lambda}\lambda^x}{x!} \\ &= e^{\lambda(e^t - 1)}, \forall t \in \mathbb{R} \end{aligned}$$
>
> $\begin{aligned}E[X] &= M_X^\prime (t) |_{t = 0} \\ &= e^{\lambda(e^t - 1)}\lambda e^t |_{t = 0} \\ &= \lambda\end{aligned}$
>
> $\begin{aligned}E[X^2] &= M_X^{\prime \prime}(t) |_{t = 0} \\ &= (e^{\lambda(e^t - 1)}(\lambda e^{t})^2 + e^{\lambda(e^t - 1)}\lambda e^t) |_{t = 0} \\ &= \lambda ^2 + \lambda\end{aligned}$
>
> $Var(X) = (\lambda^2 + \lambda) - \lambda^2 = \lambda$
