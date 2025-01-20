
Theorem 2.1.3 Let $X$ have cdf $F_X(x)$, let $Y=g(X)$
a. If $g$ is an increasing function on $\mathscr{X}, F_Y(y)=F_X\left(g^{-1}(y)\right)$ for $y \in \mathscr{Y}$.
b. If $g$ is a decreasing function on $\mathscr{X}$ and $X$ is a continuous random variable, $F_Y(y)=1-$ $F_X\left(g^{-1}(y)\right)$ for $y \in \mathscr{Y}$.


Theorem 2.1.5 Let $X$ have pdf $f_X(x)$ and let $Y=g(X)$, where $g$ is a monotone function. Suppose that $f_X(x)$ is continuous on $\mathscr{X}$ and that $g^{-1}(y)$ has a continuous derivative on $\mathscr{Y}$. Then the pdf of $Y$ is given by
$$
f_Y(y)= \begin{cases}f_X\left(g^{-1}(y)\right)\left|\frac{d}{d y} g^{-1}(y)\right| & y \in \mathscr{Y} \\ 0 & \text { otherwise }\end{cases}
$$
 Theorem 2.1.10 (Probability integral transformation) Let $X$ have continuous cdf $F_X(x)$ and define the random variable $Y$ as $Y=F_X(X)$. Then $Y$ is uniformly distributed on $(0,1)$, that is, $P(Y \leq y)=y, 0<y<1$.

Before we prove this theorem, we will digress for a moment and look at $F_X^{-1}$, the inverse of the cdf $F_X$, in some detail. If $F_X$ is strictly increasing, then $F_X^{-1}$ is well defined by
$$
F_X^{-1}(y)=x \Leftrightarrow F_X(x)=y
$$

$$
F_X^{-1}(y)=\inf \left\{x: F_x(x) \geq y\right\}
$$

Proof of Theorem 2.1.10: For $Y=F_X(X)$ we have, for $0<y<1$,
$$
\begin{aligned}
P(Y \leq y) & =P\left(F_X(X) \leq y\right) \\
& =P\left(F_X^{-1}\left[F_X(X)\right] \leq F_X^{-1}(y)\right) \\
& =P\left(X \leq F_X^{-1}(y)\right) \\
& =F_X\left(F_X^{-1}(y)\right) \\
& =y
\end{aligned}
$$
 


Theorem 2.3.7 If X has mgf $M_X(t)$, then
$$
\mathrm{E} X^n=M_X^{(n)}(0)
$$
where we define
$$
M_X^{(n)}(0)=\left.\frac{d^n}{d t^n} M_X(t)\right|_{t=0}
$$

That is, the nth moment is equal to the nth derivative of $M_X(t)$ evaluated at $t=0$.





Example 2.3.8 (Gamma mgf) In Example 2.1.6 we encountered a special case of the gamma pdf
$$
f(x)=\frac{1}{\Gamma(\alpha) \beta^\alpha} x^{\alpha-1} e^{-x / \beta}, \quad 0<x<\infty, \quad \alpha>0, \quad \beta>0
$$
where $\Gamma(\alpha)$ denotes the gamma function. The mgf is given by
$$
\begin{aligned}
M_X(t) & =\frac{1}{\Gamma(\alpha) \beta^\alpha} \int_0^{\infty} e^{t x} x^{\alpha-1} e^{-x / \beta} d x \\
& =\frac{1}{\Gamma(\alpha) \beta^\alpha} \int_0^{\infty} x^{\alpha-1} e^{-\left(\frac{1}{\beta}-t\right) x} d x \\
& =\frac{1}{\Gamma(\alpha) \beta^\alpha} \int_0^{\infty} x^{\alpha-1} e^{-x /\left(\frac{\beta}{1-\beta t}\right)} d x
\end{aligned}
$$

integrand as the kernel of another gamma pdf.
$$
\int_0^{\infty} x^{a-1} e^{-x / b} d x=\Gamma(a) b^a
$$

$$
M_X(t)=\frac{1}{\Gamma(\alpha) \beta^\alpha} \Gamma(\alpha)\left(\frac{\beta}{1-\beta t}\right)^\alpha=\left(\frac{1}{1-\beta t}\right)^\alpha \quad \text { if } t<\frac{1}{\beta}
$$

The mean of the gamma distribution is given by
$$
\mathrm{E} X=\left.\frac{d}{d t} M_X(t)\right|_{t=0}=\left.\frac{\alpha \beta}{(1-\beta t)^{\alpha+1}}\right|_{t=0}=\alpha \beta
$$



Theorem 2.3.11 Let $F_X(x)$ and $F_Y(y)$ be two cdfs all of whose moments exist.
a. If $X$ and $Y$ have bounded support, then $F_X(u)=F_Y(u)$ for all $u$ if and only if $\mathrm{EX}{ }^r=\mathrm{EY}$ for all integers $r=0,1,2, \ldots$.
b. If the moment generating functions exist and $M_X(t)=M_Y(t)$ for all $t$ in some neighborhood of 0 , then $F_X(u)=F_Y(u)$ for all $u$.



Theorem 2.3.12 (Convergence of mgfs ) Suppose $\left\{X_i, i=1,2, \ldots\right\}$ is a sequence of random variables, each with m g f $M_{X_i}(t)$. Furthermore, suppose that
$$
\lim _{i \rightarrow \infty} M_{X_i}(t)=M_X(t), \quad \text { for all } t \text { in a neighborhood of } 0
$$
and $M_X(t)$ is an $m g f$. Then there is a unique cdf $F_X$ whose moments are determined by $M_X(t)$ and, for all $x$ where $F_X(x)$ is continuous, we have
$$
\lim _{i \rightarrow \infty} F_{X_i}(x)=F_X(x)
$$

That is, **convergence, for $|t|<h$, of mgfs to an mgf implies convergence of cdfs.**



Theorem 2.4.1 (Leibnitz's Rule) If $f(x, \theta), a(\theta)$, and $b(\theta)$ are differentiable with respect to $\theta$, then
$$
\frac{d}{d \theta} \int_{a(\theta)}^{b(\theta)} f(x, \theta) d x=f(b(\theta), \theta) \frac{d}{d \theta} b(\theta)-f(a(\theta), \theta) \frac{d}{d \theta} a(\theta)+\int_{a(\theta)}^{b(\theta)} \frac{\partial}{\partial \theta} f(x, \theta) d x
$$




Theorem 2.4.2 Suppose the function $h(x, y)$ is continuous of $y_0$ for each $x$, and there exists a function $g(x)$ satisfying
i. $|h(x, y)|<g(x)$ for all $x$ and $y$
ii. $\int_{-\infty}^{\infty} g(x) d x<\infty$.

Then
$$
\lim _{y \rightarrow y_0} \int_{-\infty}^{\infty} h(x, y) d x=\int_{-\infty}^{\infty} \lim _{y \rightarrow y_0} h(x, y) d x
$$

The key condition in this theorem is the existence of a dominating function $g(x)$, with a finite integral, which ensures that the integrals cannot be too badly behaved.



Theorem 2.4.3 Suppose $f(x, \theta)$ is differentiable at $\theta=\theta_0$, that is,
$$
\lim _{\delta \rightarrow 0} \frac{f\left(x, \theta_0+\delta\right)-f\left(x, \theta_0\right)}{\delta}=\left.\frac{\partial}{\partial \theta} f(x, \theta)\right|_{\theta=\theta_0}
$$
exists for every $x$, and there exists a function $g\left(x, \theta_0\right)$ and a constant $\delta_0>0$ such that
i. $\left|\frac{f\left(x, \theta_0+\delta\right)-f\left(x, \theta_0\right)}{\delta}\right| \leq g\left(x, \theta_0\right)$, for all $x$ and $|\delta| \leq \delta_0$,
ii. $\int_{-\infty}^{\infty} g\left(x, \theta_0\right) d x<\infty$.

Then
$$
\left.\frac{d}{d \theta} \int_{-\infty}^{\infty} f(x, \theta) d x\right|_{\theta=\theta_0}=\int_{-\infty}^{\infty}\left[\left.\frac{\partial}{\partial \theta} f(x, \theta)\right|_{\theta=\theta_0}\right] d x
$$




Theorem 2.4.8 Suppose that the series $\sum_{x=0}^{\infty} h(\theta, x)$ converges for all $\theta$ in an interval $(a, b)$ of real numbers and
i. $\frac{\partial}{\partial \theta} h(\theta, x)$ is continuous in $\theta$ for each $x$,
ii. $\sum_{x=0}^{\infty} \frac{\partial}{\partial \theta} h(\theta, x)$ converges uniformly on every closed bounded subinterval of $(a, b)$.

Then
$$
\frac{d}{d \theta} \sum_{x=0}^{\infty} h(\theta, x)=\sum_{x=0}^{\infty} \frac{\partial}{\partial \theta} h(\theta, x)
$$

The condition of uniform convergence is the key one to verify in order to establish that the differentiation can be taken inside the summation. Recall that a series converges uniformly if its sequence of partial sums converges uniformly.
Example 2.4.9 (Continuation of Exercise 2.4.7) To apply Theorem 2.4.8 we identify
$$
h(\theta, x)=\theta(1-\theta)^x
$$
and
$$
\frac{\partial}{\partial \theta} h(\theta, x)=(1-\theta)^x-\theta x(1-\theta)^{x-1}
$$
and verify that $\sum_{x=0}^{\infty} \frac{\partial}{\partial \theta} h(\theta, x)$ converges uniformly. Define $S_n(\theta)$ by
$$
S_n(\theta)=\sum_{x=0}^n\left[(1-\theta)^x-\theta x(1-\theta)^{x-1}\right]
$$

The convergence will be uniform on $[c, d] \subset(0,1)$ if, given $\varepsilon>0$, we can find an $N$ such that
$$
n>N \Rightarrow\left|S_n(\theta)-S_{\infty}(\theta)\right|<\varepsilon \quad \text { for all } \theta \in[c, d]
$$

$$
\begin{aligned}
S_n(\theta) & =\frac{1-(1-\theta)^{n+1}}{\theta}-\frac{\left(1-(1-\theta)^{n+1}\right)-(n+1) \theta(1-\theta)^n}{\theta} \\
& =(n+1)(1-\theta)^n
\end{aligned}
$$

It is clear that, for $\theta<\theta<1, S_{\infty}=\lim _{n \rightarrow \infty} S_n(\theta)=0$. Since $S_n(\theta)$ is continuous, the convergence is uniform on any closed bounded interval. Therefore, the series of derivatives converges uniformly and the interchange of differentiation and summation is justified.



Theorem 2.4 .10 Suppose the series $\sum_{x=0}^{\infty} h(\theta, x)$ converges uniformly on $[a, b]$ and that, for each $x, h(\theta, x)$ is a continuous function of $\theta$. Then
$$
\int_a^b \sum_{x=0}^{\infty} h(\theta, x) d \theta=\sum_{x=0}^{\infty} \int_a^b h(\theta, x) d \theta
$$


