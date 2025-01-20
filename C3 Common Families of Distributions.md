# Common Families of Distributions

[TOC]



## Discrete Distributions



### Discrete Uniform Distribution

A random variable $X$ has a discrete uniform $(1, N)$ distribution if
$$
P(X=x \mid N)=\frac{1}{N}, \quad x=1,2, \ldots, N
$$
$$
\mathrm{E} X=\frac{N+1}{2}
$$
$$
\mathrm{E} X^2=\sum_{x=1}^N x^2 \frac{1}{N}=\frac{(N+1)(2 N+1)}{6}
$$
$$
\begin{aligned}
\operatorname{Var} X & =\frac{(N+1)(N-1)}{12}
\end{aligned}
$$

### Hypergeometric Distribution

N balls, M red, N-M green. take K balls, x red.
$$
P(X=x \mid N, M, K)=\frac{\binom{M}{x}\binom{N-M}{K-x}}{\binom{N}{K}}, \quad x=0,1, \ldots, K
$$

$$
M-(N-K) \leq x \leq M
$$

$$
\mathrm{EX}=\frac{K M}{N}
$$
$$
\operatorname{Var} X=\frac{K M}{N}\left(\frac{(N-M)(N-K)}{N(N-1)}\right)
$$
### Binomial Distribution (Count Success)

Counts the number of successes in a fixed number of Bernoulli trials.
$$
P(Y=y \mid n, p)=\binom{n}{y} p^y(1-p)^{n-y}, \quad y=0,1,2, \ldots, n,
$$
Theorem 3.2.2 (Binomial Theorem) For any real numbers $x$ and $y$ and integer $n \geq 0$,
$$
(x+y)^n=\sum_{=0}^n\binom{n}{i} x^{\prime} y^{n-i}
$$

$$
2^n=\sum_{i=0}^n\binom{n}{i}
$$

$$
\mathrm{EX}=n p, \quad \operatorname{Var} X=n p(1-p)
$$

$$
M_X(t)=\left[p e^t+(1-p)\right]^n
$$



### Poisson Distribution (Waiting Time)

For small time intervals, the probability of an arrival is proportional to the length of waiting time. 

$\lambda$ is intensity parameter.
$$
P(X=x \mid \lambda)=\frac{e^{-\lambda} \lambda^x}{x!}, \quad x=0,1, \ldots
$$

$$
e^y=\sum_{i=0}^{\infty} \frac{y^{i}}{i!}
$$

Thus,
$$
\sum_{x=0}^{\infty} P(X=x \mid \lambda)=e^{-\lambda} \sum_{x=0}^{\infty} \frac{\lambda^x}{x!}=e^{-\lambda} e^\lambda=1
$$

The mean of $X$ is easily seen to be
$$
\begin{aligned}
\mathrm{EX} & =\sum_{x=0}^{\infty} x \frac{e^{-\lambda} \lambda^x}{x!} \\
& =\sum_{x=1}^{\infty} x \frac{e^{-\lambda} \lambda^x}{x!} \\
& =\lambda e^{-\lambda} \sum_{x=1}^{\infty} \frac{\lambda^{x-1}}{(x-1)!} \\
& =\lambda e^{-\lambda} \sum_{y=0}^{\infty} \frac{\lambda^y}{y!} \quad \quad \text { (substitute } y=x-1)
\end{aligned}
$$

A similar calculation will show that
$$
\operatorname{Var} X=\lambda
$$
and so the parameter $\lambda$ is both the mean and the variance of the Poisson distribution.

$$
M_X(t)=e^{\lambda\left(e^t-1\right)}
$$


### Negative Binomial Distribution (Wait for r Successes)

Count the number of Bernoulli trials required to get a fixed number of successes. 
$$
P(X=x \mid r, p)=\binom{x-1}{r-1} p^r(1-p)^{x-r}, \quad x=r, r+1, \ldots
$$
The negative binomial distribution is sometimes defined in terms of the random variable $Y=$ number of failures before the $r$ th success. 

$$
P(Y=y)=\binom{r+y-1}{y} p^r(1-p)^y, \quad y=0,1, \ldots .
$$

$$
\binom{r+y-1}{y}=(-1)^y\binom{-r}{y}=(-1)^y \frac{(-r)(-r-1)(-r-2) \cdots \cdots(-r-y+1)}{(y)(y-1)(y-2) \cdots \cdot(2)(1)}
$$

$$
P(Y=y)=(-1)^y\binom{-r}{y} p^r(1-p)^y
$$
a striking resemblance to the binomial distribution.
$$
\begin{aligned}
\mathrm{EY} & =r \frac{(1-p)}{p} .
\end{aligned}
$$

$$
\operatorname{Var} Y=\frac{r(1-p)}{p^2}
$$

If we define the parameter $\mu=r(1-p) / p$, then
$$
\operatorname{Var} Y=\mu+\frac{1}{r} \mu^2
$$

The variance is a quadratic function of the mean.



The negative binomial family of distributions includes the Poisson distribution as a limiting case. If $r \rightarrow \infty$ and $p \rightarrow 1$ such that $r(1-p) \rightarrow \lambda, 0<\lambda<\infty$, then
$$
\begin{aligned}
\mathrm{E} Y & =\frac{r(1-p)}{p} \rightarrow \lambda \\
\operatorname{Var} Y & =\frac{r(1-p)}{p^2} \rightarrow \lambda
\end{aligned}
$$


 

### Geometric Distribution (Wait for one success)

A special case of the negative binomial distribution. If we set $r=1$ we have
$$
P(X=x \mid p)=p(1-p)^{x-1}, \quad x=1,2, \ldots
$$

The mean and variance of $X$ can be calculated by using the negative binomial formulas and by writing $X=Y+1$ to obtain
$$
\mathrm{E} X=\frac{1}{p} \quad \text { and } \quad \operatorname{Var} X=\frac{q}{p^2}
$$

The geometric distribution "memoryless" property. For integers $s>t$, it is the case that
$$
P(X>s \mid X>t)=P(X>s-t)
$$
The probability of getting an additional $s-t$ failures, having already observed $t$ failures, is the same as the probability of observing $s-t$ failures at the start of the sequence.


$$
\begin{aligned}
P(X>n) & =P(\text { no successes in } n \text { trials }) \\
& =(1-p)^n
\end{aligned}
$$
and hence
$$
\begin{aligned}
P(X>s \mid X>t) & =\frac{P(X>s \text { and } X>t)}{P(X>t)} \\
& =\frac{P(X>s)}{P(X>t)} \\
& =(1-p)^{s-t} \\
& =P(X>s-t)
\end{aligned}
$$



## Continuous Distributions

