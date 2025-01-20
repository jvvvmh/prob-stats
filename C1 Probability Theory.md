

Definition 1.2.1 A collection of subsets of $S$ is called a **sigma algebra** (or Borel field) if it satisfies the following three properties:

-  $\empty \in \mathscr{B}$ (the empty set is an element of $\mathscr{B}$ ).
- If $A \in \mathscr{B}$ then $A^c \in \mathscr{B}$ ( $\mathscr{B}$ is closed under complementation).
- If $A_1, A_2, \ldots \in \mathscr{B}$ then $\cup_{i=1}^{\infty} A_i \in \mathscr{B} $ $(\mathscr{B}$ is closed under countable unions).



Definition 1.2.4 Given a sample space $S$ and an associated sigma algebra $\mathscr{B}$, a **probability function** is a function $P$ with domain $\mathscr{B}$ that satisfies

- $P(A) \geq 0$ for all $A \in \mathscr{B}$.
- $P(S)=1$.
- If $A_1, A_2, \ldots \in \mathscr{B}$ are pairwise disjoint, then $P\left(\cup_{i=1}^{\infty} A_i\right)=\sum_{i=1}^{\infty} P\left(A_i\right)$.

The three properties given in Definition 1.2 .4 are usually referred to as the **Axioms of Probability**.



Bonferroni Inequality P10
$$
P\left(\bigcap_{i=1}^n A_i\right) \geq \sum_{i=1}^n P\left(A_i\right)-(n-1)
$$

Theorem 1.3.5 (Bayes' Rule) Let $A_1, A_2, \ldots$ be a partition of the sample space, and let $B$ be any set. Then, for each $i=1,2, \ldots$,
$$
P\left(A_i \mid B\right)=\frac{P\left(B \mid A_i\right) P\left(A_i\right)}{\sum_{j=1}^{\infty} P\left(B \mid A_j\right) P\left(A_j\right)}
$$


Definition 1.3.7 Two events, $A$ and $B$, are statistically independent if
$$
P(A \cap B)=P(A) P(B)
$$


Theorem 1.5.3 The function $F(x)$ is a cdf if and only if the following three conditions hold:
a. $\lim _{x \rightarrow-\infty} F(x)=0$ and $\lim _{x \rightarrow \infty} F(x)=1$.
b. $F(x)$ is a nondecreasing function of $x$.
c. $F(x)$ is right-continuous. That is, for every number $x_0, \lim _{x \downarrow x_0} F(x)=F\left(x_0\right)$.

Theorem 1.6.5 A function $f_X(x)$ is a pdf (or pmf) of a random variable $X$ if and only if
a. $f_X(x) \geq 0$ for all $x$.
b. $\sum_x f_X(x)=1$ (pmf) or $\int_{-\infty}^{\infty} f_X(x) d x=1$ (pdf).





