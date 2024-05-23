---
title: Poisson Distribution
pagetitle: Poisson Distribution
---

## PMF

The support of the distribution is the set of non-negative integers: $\{0,1,2,\cdots\}$. The PMF is given as follows:

$$
P(x)=\cfrac{\lambda^{x}}{x!}e^{-\lambda}
$$


Here $\lambda$ is a parameter governing the distribution. To verify that this is a valid PMF:

$$
\sum\limits_{x=0}^{\infty}\cfrac{\lambda^{x}}{x!}e^{-\lambda}=e^{-\lambda}\sum\limits_{x=0}^{\infty}\cfrac{\lambda^{x}}{x!}=1
$$


We have used the Taylor series expansion for $e^{\lambda}$.

## Bionomial to Poisson

Consider the Binomial distribution, $\text{Binomial}(n,p)$:

$$
P(x)={n \choose x}p^{x}(1-p)^{n-x}
$$


We allow $n\rightarrow\infty$ and $p\rightarrow0$ such that $np=\lambda$. Rewriting the Binomial distribution, we get:

$$
\begin{aligned}
P(x) & =\cfrac{n!}{x!(n-x)!}\,p^{x}(1-p)^{n-x}\\
\\ & =\cfrac{n!}{x!(n-x)!}\,\left(\cfrac{\lambda}{n}\right)^{x}\left(1-\cfrac{\lambda}{n}\right)^{n-x}\\
\\ & =\cfrac{\lambda^{x}}{x!}\cdot\cfrac{(n-x+1)\cdots n}{n^{x}}\cdot\left(1-\cfrac{\lambda}{n}\right)^{n}\left(1-\cfrac{\lambda}{n}\right)^{-x}
\end{aligned}
$$


We can now compute the limits:

$$
\begin{aligned}
\lim_{n\rightarrow\infty}\frac{(n-x+1)\cdots n}{n^{x}} & =\lim_{n\rightarrow\infty}\left[1-\left(\cfrac{x-1}{n}\right)\right]\cdots\left[1-\left(\cfrac{x-x}{n}\right)\right]\\
\\ & =1\\
\\\lim_{n\rightarrow\infty}\left(1-\cfrac{\lambda}{n}\right)^{n} & =e^{-\lambda}\\
\\\lim_{n\rightarrow\infty}\left(1-\cfrac{\lambda}{n}\right)^{-x} & =1
\end{aligned}
$$


Plugging these limits into the expression for $P(x)$, we get the PMF of the Poisson distribution.
