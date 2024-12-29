



# Probability

[18.600 Probability and Random Variables: Fall 2023 (mit.edu)](https://math.mit.edu/~sheffield/fall2023math600.html)

[TOC]

A simple recursion:
$$
\binom{n}{k}=\binom{n-1}{k-1}+\binom{n-1}{k} .
$$


If you have n elements you wish to divide into r distinct piles of sizes $n_1, n_2 . . . n_r$, how many ways to do that?
$$
\binom{n}{n_1, n_2, \ldots, n_r}:=\frac{n!}{n_{1}!n_{2}!\ldots n_{r}!} .
$$


A higher dimensional analog of binomial theorem:
$$
\left(x_1+x_2+\ldots+x_r\right)^n=\sum_{n_1, \ldots, n_r: n_1+\ldots+n_r=n}\binom{n}{n_1, \ldots, n_r} x_1^{n_1} x_2^{n_2} \ldots x_r^{n_r}
$$

The sum on the right is taken over all collections $\left(n_1, n_2, \ldots, n_r\right)$ of $r$ non-negative integers that add up to $n$.



How many sequences $a_1, \ldots, a_k$ of non-negative integers satisfy $a_1+a_2+\ldots+a_k=n$ ?

- Answer: $\binom{n+k-1}{k-1}$. Represent partition by $k-1$ bars and $n$ stars, $* *|* *||* * * *| *$.



Inclusion-exclusion identity:
$$
\begin{aligned}
P\left(U_{i=1}^n E_i\right) & =\sum_{j=1}^n P\left(E_i\right)-\sum_{i_1<i_2} P\left(E_{i_1} E_{i_2}\right)+\ldots \\
& +(-1)^{(r+1)} \sum_{i_1<i_2<\ldots<i_r}^n P\left(E_{i_1} E_{i_2} \ldots E_{i_r}\right) \\
& +\ldots+(-1)^{n+1} P\left(E_1 E_2 \ldots E_n\right) .
\end{aligned}
$$
Hat problem:

- n people toss hats into a bin, randomly shuffle, return one hat to each person. Find probability nobody gets own hat.
- Inclusion-exclusion. Let $E_i$ be the event that $i$ th person gets own hat.
- What is $P\left(E_{i_1} E_{i_2} \ldots E_{i_r}\right)$ ?
- Answer: $\frac{(n-r)!}{n!}$.
- There are $\binom{n}{r}$ terms like that in the inclusion exclusion sum. What is $\binom{n}{r} \frac{(n-r)!}{n!}$ ?
- Answer: $\frac{1}{r!}$.
- $P\left(U_{i=1}^n E_i\right)=1-\frac{1}{2!}+\frac{1}{3!}-\frac{1}{4!}+\ldots \pm \frac{1}{n!}$
- $1-P\left(\cup_{i=1}^n E_i\right)=1-1+\frac{1}{2!}-\frac{1}{3!}+\frac{1}{4!}-\ldots \pm \frac{1}{n!} \approx 1 / e \approx 0.36788$.



Puzzle:

- Given that your friend has exactly two children, one of whom is a son born on a Tuesday, what is the probability the second child is a son.
- Make state space matrix of 196 = 14 × 14 elements.
- Easy to see answer is 13/27.



Independence:

- Say E and F are independent if $P(EF) = P(E)P(F)$.

- Equivalent statement: $P(E|F) = P(E)$. Also equivalent: $P(F|E) = P(F)$.



### **Discrete random variables**

#### **Binomial**

Number of heads is binomial random variable with parameters (n, p).

- $\binom{n}{k} p^k(1-p)^{n-k}$.

- Can use binomial theorem to show probabilities sum to one:
  - $1=1^n=(p+q)^n=\sum_{k=0}^n\binom{n}{k} p^k q^{n-k}$.
- np, npq

- Let $\lambda$ be some moderate-sized number. Say $\lambda=2$ or $\lambda=3$.

#### **Poisson**

- Suppose I have a coin that comes on heads with probability $\lambda / n$ and I toss it $n$ times.
- How many heads do I expect to see?
- Answer: $n p=\lambda$.
- Let $k$ be some moderate sized number (say $k=4$ ). What is the probability that I see exactly $k$ heads?
- Binomial formula:
$$
\binom{n}{k} p^k(1-p)^{n-k}=\frac{n(n-1)(n-2) \ldots(n-k+1)}{k} p^k(1-p)^{n-k}
$$
- This is approximately $\frac{\lambda^k}{k!}(1-p)^{n-k} \approx \frac{\lambda^k}{k!} e^{-\lambda}$.
- A Poisson random variable $X$ with parameter $\lambda$ satisfies $P\{X=k\}=\frac{\lambda^k}{k!} e^{-\lambda}$ for integer $k \geq 0$.
- $\lambda, \lambda$

#### **Poisson point process**

- A Poisson point process is a random function $N(t)$ called a Poisson process of rate $\lambda$.
- For each $t>s \geq 0$, the value $N(t)-N(s)$ describes the number of events occurring in the time interval ( $s, t$ ) and is Poisson with rate $(t-s) \lambda$.
- Probability to **see zero events** in first $t$ time units is $e^{-\lambda t}$.
- Let $T_{k}$ be time elapsed, since the previous event, until the $k$ th event occurs. Then the $T_{k}$ are independent random variables, each of which is **exponential** with parameter $\lambda$.

#### **Geometric distribution**

- Consider a sequence of independent tosses of a coin that comes up heads with probability p. The first head is on the Xth toss.

- Let $X$ be a geometric with parameter $p$, $P\{X=k\}=(1-p)^{k-1} p=q^{k-1} p$ for $k \geq 1$.
- What is $E[X]$ ?
- By definition $E[X]=\sum_{k=1}^{\infty} q^{k-1} p k$.
- There's a trick to computing sums like this.
- Note $E[X-1]=\sum_{k=1}^{\infty} q^{k-1} p(k-1)$. Setting $j=k-1$, we have $E[X-1]=q \sum_{j=0}^{\infty} q^{j-1} p j=q E[X]$.
- Kind of makes sense. $X-1$ is "number of extra tosses after first." Given first coin heads (probability $p$ ), $X-1$ is 0 . Given first coin tails (probability q), conditional law of $X-1$ is geometric with parameter $p$. In latter case, conditional expectation of $X-1$ is same as a priori expectation of $X$.
- Thus $E[X]-1=E[X-1]=p \cdot 0+q E[X]=q E[X]$ and solving for $E[X]$ gives $E[X]=1 /(1-q)=1 / p$.
  $1 / p, q / p^{2}$

#### **Negative binomial (r, p):**

Consider a sequence of independent tosses of a coin that comes up heads with probability p . Let X be such that the rth heads is on the Xth toss.
$P(X=k)=\binom{k-1}{r-1} p^{r} q^{k-r}$
Write $X=X_{1}+X_{2}+\ldots+X_{r}$ where $X_{k}$ is number of tosses (following ( $\mathrm{k}-1$ )th head) required to get kth head. Each $X_{k}$ is geometric with parameter p.
$r p, r q / p^{2}$



### 总结

- Binomial (number of heads in $n$ tosses), geometric (steps required to obtain one heads), negative binomial (steps required to obtain $n$ heads).
- Poisson is limit of binomial as $n \rightarrow \infty$ when $p=\lambda / n$.
- Poisson point process: toss one $\lambda / n$ coin during each length $1 / n$ time increment, take $n \rightarrow \infty$ limit.
- Exponential: time till first event in $\lambda$ Poisson point process.
- Gamma distribution: time till nth event in $\lambda$ Poisson point process.
- Sum of two independent binomial random variables with parameters $\left(n_{1}, p\right)$ and $\left(n_{2}, p\right)$ is itself binomial $\left(n_{1}+n_{2}, p\right)$.
- Sum of $n$ independent geometric random variables with parameter $p$ is negative binomial with parameter $(n, p)$.
- Expectation of geometric random variable with parameter $p$ is $1 / p$.
- Expectation of binomial random variable with parameters $(n, p)$ is $n p$.
- Variance of binomial random variable with parameters $(n, p)$ is $n p(1-p)=n p q$.
- Sum of $n$ independent exponential random variables each with parameter $\lambda$ is gamma with parameters $(n, \lambda)$.
- Memoryless properties: given that exponential random variable $X$ is greater than $T>0$, the conditional law of $X-T$ is the same as the original law of $X$.
- Write $p=\lambda / n$. Poisson random variable expectation is $\lim _{n \rightarrow \infty} n p=\lim _{n \rightarrow \infty} n \frac{\lambda}{n}=\lambda$. Variance is $\lim _{n \rightarrow \infty} n p(1-p)=\lim _{n \rightarrow \infty} n(1-\lambda / n) \lambda / n=\lambda$.
- Sum of $\lambda_{1}$ Poisson and independent $\lambda_{2}$ Poisson is a $\lambda_{1}+\lambda_{2}$ Poisson.
- Times between successive events in $\lambda$ Poisson process are independent exponentials with parameter $\lambda$.
- Minimum of independent exponentials with parameters $\lambda_{1}$ and $\lambda_{2}$ is itself exponential with parameter $\lambda_{1}+\lambda_{2}$.
- DeMoivre-Laplace limit theorem (special case of central limit theorem):

$$
\lim _{n \rightarrow \infty} P\left\{a \leq \frac{S_{n}-n p}{\sqrt{n p q}} \leq b\right\} \rightarrow \Phi(b)-\Phi(a)
$$

- Toss a million fair coins. Approximate the probability that I get more than 501, 000 heads.

- Answer: well, $\sqrt{n p q}=\sqrt{10^{6} \times .5 \times .5}=500$. So we're asking for probability to be over two SDs above mean. This is approximately $1-\Phi(2)=\Phi(-2)$.

  

- Values: $\Phi(-3) \approx .0013, \Phi(-2) \approx .023$ and $\Phi(-1) \approx .159$.

- Rule of thumb: "two thirds of time within one SD of mean, 95 percent of time within 2 SDs of mean."



### Continuous random variables:

#### Gamma Distribution

- Say $X$ is an exponential random variable of parameter $\lambda$ when its probability distribution function is $f(x)=\lambda e^{-\lambda x}$ for $x \geq 0$ (and $f(x)=0$ if $x<0$ ).
- For $a>0$ have

$$
F_{X}(a)=\int_{0}^{a} f(x) d x=\int_{0}^{a} \lambda e^{-\lambda x} d x=-\left.e^{-\lambda x}\right|_{0} ^{a}=1-e^{-\lambda a}
$$

- Thus $P\{X<a\}=1-e^{-\lambda a}$ and $P\{X>a\}=e^{-\lambda a}$.
- Formula $P\{X>a\}=e^{-\lambda a}$ is very important in practice.
- Repeated integration by parts gives $E\left[X^{n}\right]=n!/ \lambda^{n}$.
- If $\lambda=1$, then $E\left[X^{n}\right]=n!$. Value $\Gamma(n):=E\left[X^{n-1}\right]$ defined for real $n>0$ and $\Gamma(n)=(n-1)!$.
- Say that random variable $X$ has gamma distribution with parameters $(\alpha, \lambda)$ if $f_{X}(x)=\left\{\begin{array}{ll}\frac{(\lambda x)^{\alpha-1} e^{-\lambda x} \lambda}{\Gamma(\alpha)} & x \geq 0 \\ 0 & x<0\end{array}\right.$.
- Same as exponential distribution when $\alpha=1$. Otherwise, multiply by $x^{\alpha-1}$ and divide by $\Gamma(\alpha)$. The fact that $\Gamma(\alpha)$ is what you need to divide by to make the total integral one just follows from the definition of $\Gamma$.
- Waiting time interpretation makes sense only for integer $\alpha$, but distribution is defined for general positive $\alpha$.



#### Beta Distribution

- Two part experiment: first let $p$ be uniform random variable $[0,1]$, then let $X$ be binomial $(n, p)$ (number of heads when we toss $n p$-coins).
- Given that $X=a-1$ and $n-X=b-1$ the conditional law of $p$ is called the $\beta$ distribution.
- The density function is a constant (that doesn't depend on $x$ ) times $x^{a-1}(1-x)^{b-1}$.
- That is $f(x)=\frac{1}{B(a, b)} x^{a-1}(1-x)^{b-1}$ on $[0,1]$, where $B(a, b)$ is constant chosen to make integral one. Can show

$$
B(a, b)=\frac{\Gamma(a) \Gamma(b)}{\Gamma(a+b)} .
$$

- Turns out that $E[X]=\frac{a}{a+b}$ and the mode of $X$ is $\frac{(a-1)}{(a-1)+(b-1)}$.
- Let $X_{i}$ be an i.i.d. sequence of random variables with finite mean $\mu$ and variance $\sigma^{2}$.
- Write $S_{n}=\sum_{i=1}^{n} X_{i}$. So $E\left[S_{n}\right]=n \mu$ and $\operatorname{Var}\left[S_{n}\right]=n \sigma^{2}$ and $\mathrm{SD}\left[S_{n}\right]=\sigma \sqrt{n}$.
- Write $B_{n}=\frac{X_{1}+X_{2}+\ldots+X_{n}-n \mu}{\sigma \sqrt{n}}$. Then $B_{n}$ is the difference between $S_{n}$ and its expectation, measured in standard deviation units.



#### Cauchy Distribution

- A standard Cauchy random variable is a random real number with probability density $f(x)=\frac{1}{\pi} \frac{1}{1+x^{2}}$.
- There is a "spinning flashlight" interpretation. Put a flashlight at $(0,1)$, spin it to a uniformly random angle in $[-\pi / 2, \pi / 2]$, and consider point $X$ where light beam hits the $x$-axis.
- $F_{X}(x)=P\{X \leq x\}=P\{\tan \theta \leq x\}=P\left\{\theta \leq \tan ^{-1} x\right\}=$ $\frac{1}{2}+\frac{1}{\pi} \tan ^{-1} x$.
- Find $f_{X}(x)=\frac{d}{d x} F(x)=\frac{1}{\pi} \frac{1}{1+x^{2}}$.



#### Uniform distribution

- Suppose $X$ is a random variable with probability density function $f(x)= \begin{cases}\frac{1}{\beta-\alpha} & x \in[\alpha, \beta] \\ 0 & x \notin[\alpha, \beta] .\end{cases}$
- Then $E[X]=\frac{\alpha+\beta}{2}$.
- And $\operatorname{Var}[X]=\operatorname{Var}[(\beta-\alpha) Y+\alpha]=\operatorname{Var}[(\beta-\alpha) Y]=$ $(\beta-\alpha)^{2} \operatorname{Var}[Y]=(\beta-\alpha)^{2} / 12$.

Independent

- We say $X$ and $Y$ are independent if for any two (measurable) sets $A$ and $B$ of real numbers we have

$$
P\{X \in A, Y \in B\}=P\{X \in A\} P\{Y \in B\}
$$

- When $X$ and $Y$ are discrete random variables, they are independent if $P\{X=x, Y=y\}=P\{X=x\} P\{Y=y\}$ for all $x$ and $y$ for which $P\{X=x\}$ and $P\{Y=y\}$ are non-zero.
- When $X$ and $Y$ are continuous, they are independent if $f(x, y)=f_{X}(x) f_{Y}(y)$.
- Say we have independent random variables $X$ and $Y$ and we know their density functions $f_{X}$ and $f_{Y}$.
- Now let's try to find $F_{X+Y}(a)=P\{X+Y \leq a\}$.
- This is the integral over $\{(x, y): x+y \leq a\}$ of $f(x, y)=f_{X}(x) f_{Y}(y)$. Thus,

$$
\begin{aligned}
P\{X+Y & \leq a\}=\int_{-\infty}^{\infty} \int_{-\infty}^{a-y} f_{X}(x) f_{Y}(y) d x d y \\
& =\int_{-\infty}^{\infty} F_{X}(a-y) f_{Y}(y) d y .
\end{aligned}
$$

Differentiating both sides gives $f_{X+Y}(a)=\frac{d}{d a} \int_{-\infty}^{\infty} F_{X}(a-y) f_{Y}(y) d y=\int_{-\infty}^{\infty} f_{X}(a-y) f_{Y}(y) d y$.

- Latter formula makes some intuitive sense. We're integrating over the set of $x, y$ pairs that add up to $a$.

### Order statistics

- Consider i.i.d random variables $X_{1}, X_{2}, \ldots, X_{n}$ with continuous probability density $f$.
- Let $Y_{1}<Y_{2}<Y_{3} \ldots<Y_{n}$ be list obtained by sorting the $X_{j}$.
- In particular, $Y_{1}=\min \left\{X_{1}, \ldots, X_{n}\right\}$ and $Y_{n}=\max \left\{X_{1}, \ldots, X_{n}\right\}$ is the maximum.
- What is the joint probability density of the $Y_{i}$ ?
- Answer: $f\left(x_{1}, x_{2}, \ldots, x_{n}\right)=n!\prod_{i=1}^{n} f\left(x_{i}\right)$ if $x_{1}<x_{2} \ldots<x_{n}$, zero otherwise.
- Let $\sigma:\{1,2, \ldots, n\} \rightarrow\{1,2, \ldots, n\}$ be the permutation such that $X_{j}=Y_{\sigma(j)}$
- Are $\sigma$ and the vector $\left(Y_{1}, \ldots, Y_{n}\right)$ independent of each other?
- Yes.
- For both discrete and continuous random variables $X$ and $Y$ we have $E[X+Y]=E[X]+E[Y]$.
- In both discrete and continuous settings, $E[a X]=a E[X]$ when $a$ is a constant. And $E\left[\sum a_{i} X_{i}\right]=\sum a_{i} E\left[X_{i}\right]$.
- But what about that delightful "area under $1-F_{X}$ " formula for the expectation?
- When $X$ is non-negative with probability one, do we always have $E[X]=\int_{0}^{\infty} P\{X>x\}$, in both discrete and continuous settings?
- Define $g(y)$ so that $1-F_{X}(g(y))=y$. (Draw horizontal line at height $y$ and look where it hits graph of $1-F_{X}$.)
- Choose $Y$ uniformly on $[0,1]$ and note that $g(Y)$ has the same probability distribution as $X$.
- So $E[X]=E[g(Y)]=\int_{0}^{1} g(y) d y$, which is indeed the area under the graph of $1-F_{X}$.




### Conditional Variance

- Definition:

$$
\operatorname{Var}(X \mid Y)=E\left[(X-E[X \mid Y])^{2} \mid Y\right]=E\left[X^{2}-E[X \mid Y]^{2} \mid Y\right]
$$

- $\operatorname{Var}(X \mid Y)$ is a random variable that depends on $Y$. It is the variance of $X$ in the conditional distribution for $X$ given $Y$.
- Note $E[\operatorname{Var}(X \mid Y)]=E\left[E\left[X^{2} \mid Y\right]\right]-E\left[E[X \mid Y]^{2} \mid Y\right]=$ $E\left[X^{2}\right]-E\left[E[X \mid Y]^{2}\right]$.
- If we subtract $E[X]^{2}$ from first term and add equivalent value $E[E[X \mid Y]]^{2}$ to the second, RHS becomes $\operatorname{Var}[X]-\operatorname{Var}[E[X \mid Y]]$, which implies following:
- Useful fact: $\operatorname{Var}(X)=\operatorname{Var}(E[X \mid Y])+E[\operatorname{Var}(X \mid Y)]$.
- One can discover $X$ in two stages: first sample $Y$ from marginal and compute $E[X \mid Y]$, then sample $X$ from distribution given $Y$ value.
- Above fact breaks variance into two parts, corresponding to these two stages.



### Moment Generating Function

- Let $X$ be a random variable and $M(t)=E\left[e^{t X}\right]$.

- Then $M^{\prime}(0)=E[X]$ and $M^{\prime \prime}(0)=E\left[X^{2}\right]$. Generally, nth derivative of $M$ at zero is $E\left[X^{n}\right]$.
- If $X_{1} \ldots X_{n}$ are i.i.d. copies of $X$ and $Z=X_{1}+\ldots+X_{n}$ then what is $M_{Z}$ ?
- Answer: $M_{X}^{n}$.
- If $Z=a X$ then $M_{Z}(t)=E\left[e^{t Z}\right]=E\left[e^{t a X}\right]=M_{X}(a t)$.
- If $Z=X+b$ then $M_{Z}(t)=E\left[e^{t Z}\right]=E\left[e^{t X+b t}\right]=e^{b t} M_{X}(t)$.



- If $X$ is binomial with parameters $(p, n)$ then
  $M_{X}(t)=\left(p e^{t}+1-p\right)^{n}$.
- If $X$ is Poisson with parameter $\lambda>0$ then $M_{X}(t)=\exp \left[\lambda\left(e^{t}-1\right)\right]$.
- If $X$ is normal with mean 0 , variance 1 , then $M_{X}(t)=e^{t^{2} / 2}$.
- If $X$ is normal with mean $\mu$, variance $\sigma^{2}$, then $M_{X}(t)=e^{\sigma^{2} t^{2} / 2+\mu t}$.
- If $X$ is exponential with parameter $\lambda>0$ then $M_{X}(t)=\frac{\lambda}{\lambda-t}$.



- The characteristic function of $X$ is defined by $\phi(t)=\phi_{X}(t):=E\left[e^{i t X}\right]$. Like $M(t)$ except with $i$ thrown in.
- Recall that by definition $e^{i t}=\cos (t)+i \sin (t)$.
- If $X$ has an $m$ th moment then $E\left[X^{m}\right]=i^{m} \phi_{X}^{(m)}(0)$.
- But characteristic functions have a distinct advantage: they are always well defined for all $t$ even if $f_{X}$ decays slowly.



### Central limit theorem

Let $X_i$ be an i.i.d. sequence of random variables with finite mean $\mu$ and variance $\sigma^2$.
Write $S_n=\sum_{i=1}^n X_i$. So $E\left[S_n\right]=n \mu$ and $\operatorname{Var}\left[S_n\right]=n \sigma^2$ and $\operatorname{SD}\left[S_n\right]=\sigma \sqrt{n}$.
Write $B_n=\frac{X_1+X_2+\ldots+X_n-n \mu}{\sigma \sqrt{n}}$. Then $B_n$ is the difference between $S_n$ and its expectation, measured in standard deviation units.

Central limit theorem:
$$
\lim _{n \rightarrow \infty} P\left\{a \leq B_{n} \leq b\right\} \rightarrow \Phi(b)-\Phi(a)
$$



### Law of Large Numbers

- Suppose $X_{i}$ are i.i.d. random variables with mean $\mu$.
- Then the value $A_{n}:=\frac{X_{1}+X_{2}+\ldots+X_{n}}{n}$ is called the empirical average of the first $n$ trials.
- Intuition: when $n$ is large, $A_{n}$ is typically close to $\mu$.
- Recall: weak law of large numbers states that for all $\epsilon>0$ we have $\lim _{n \rightarrow \infty} P\left\{\left|A_{n}-\mu\right|>\epsilon\right\}=0$.
- The strong law of large numbers states that **with probability one** $\lim _{n \rightarrow \infty} A_{n}=\mu$.
- It is called "strong" because it implies the weak law of large numbers. But it takes a bit of thought to see why this is the case.

### Markov chain 

- $P\left\{X_{n+1}=j \mid X_{n}=i, X_{n-1}=i_{n-1}, \ldots, X_{1}=i_{1}, X_{0}=i_{0}\right\}=P_{i j}$.
- Probability distribution for next state depends only on the current state.
- Say Markov chain is **ergodic** if some power of the transition matrix has all non-zero entries.
- Turns out that if chain has this property, then $\pi_{j}:=\lim _{n \rightarrow \infty} P_{i j}^{(n)}$ exists and the $\pi_{j}$ are the **unique** non-negative solutions of $\pi_{j}=\sum_{k=0}^{M} \pi_{k} P_{k j}$ that sum to one.
- This means that the row vector

$$
\pi=\left(\begin{array}{llll}
\pi_{0} & \pi_{1} & \ldots & \pi_{M}
\end{array}\right)
$$

is a left eigenvector of $A$ with eigenvalue 1, i.e., $\pi A=\pi$.

- We call $\pi$ the stationary distribution of the Markov chain.


### Markov and Chebyshev Inequalities

If $X$ is any nonnegative random variable, then

$$
P(X \geq a) \leq \frac{E X}{a}, \quad \text { for any } a>0 .
$$

Chebyshev's Inequality
If $X$ is any random variable, then for any $b>0$ we have
$$
P(|X-E X| \geq b) \leq \frac{\operatorname{Var}(X)}{b^{2}} .
$$







