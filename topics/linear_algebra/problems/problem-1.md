---
title: Problem-1
pagetitle: Problem-1
---

Let $W$ be a finite dimensional real vector space, and let $U$ and $V$ be two subspaces of $W$. Let $U+V$ be the space

$$
U+V=\{u+v\,:\,u\in U\text{ and }v\in V\}
$$


Show the following:

-   $U+V$ is a subspace of $W$.

-   $\text{dim}(U+V)=\text{dim}(U)+\text{dim}(V)-\text{dim}(U\cap V)$

------------------------------------------------------------------------

We see that $0\in U+V$. If $u_{1}+v_{1}\in U+V$ and $u_{2}+v_{2}\in U+V$, then $(u_{1}+u_{2})+(v_{1}+v_{2})\in U+V$. If $u+v\in U+V$ and $\lambda\in\mathbb{R}$, then $\lambda(u+v)=\lambda u+\lambda v\in U+V$. Using these three observations, we conclude that $U+V$ is a subspace of $W$.

We know that $U\cap V$ is a subspace of $W$. Let $\{w_{1},\cdots,w_{k}\}$ be a basis for $U\cap V$. We can now extend this to a basis for $U$ and a basis for $V$. The two bases are $\{w_{1},\cdots,w_{k},u_{1},\cdots,u_{m}\}$ for $U$ and $\{w_{1},\cdots,w_{k},v_{1},\cdots,v_{n}\}$ for $V$. Consider the set $\{w_{1},\cdots,w_{k},u_{1},\cdots,u_{m},v_{1},\cdots,v_{n}\}.$ It is quite easy to see that this set spans $U+V$. If we can show that this set is also linearly independent, then we have a basis for $U+V$.

Let us take a linear combination of this collection and set it to zero:

$$
(a_{1}w_{1}+\cdots+a_{k}w_{k})+(b_{1}u_{1}+\cdots+b_{m}u_{m})+(c_{1}v_{1}+\cdots+c_{n}v_{n})=0
$$


We can now group the terms in the following way:

$$
a_{1}w_{1}+\cdots+a_{k}w_{k}+b_{1}u_{1}+\cdots+b_{m}u_{m}=-(c_{1}v_{1}+\cdots+c_{n}v_{n})
$$


The LHS is a vector in $U$ and the RHS is a vector in $V$. Since the two are equal, the vector in question is in $U\cap V$. We can now express this using the basis for $U\cap V$:

$$
\begin{aligned}
-(c_{1}v_{1}+\cdots+c_{n}v_{n}) & =d_{1}w_{1}+\cdots+d_{k}w_{k}\\
c_{1}v_{1}+\cdots+c_{n}v_{n}+d_{1}w_{1}+\cdots+d_{k}w_{k} & =0
\end{aligned}
$$


This is actually a linear combination of the basis vectors of $V$ set to zero. Hence, $c_{1}=\cdots=c_{n}=d_{1}=\cdots d_{k}=0$. Going back to the original equation, we conclude that $a_{1}=\cdots=a_{k}=b_{1}=\cdots=b_{m}=0$. This implies, the set $\{w_{1},\cdots,w_{k},u_{1},\cdots,u_{m},v_{1},\cdots,v_{n}\}$ is linearly independent. We therefore have shown that this is a basis for $U+V$.

From this, the formula that relates the dimensions of the subspaces $U,V,U\cap V$ and $U+V$ follows:

$$
\boxed{\text{dim}(U+V)=\text{dim}(U)+\text{dim}(V)-\text{dim}(U\cap V)}
$$

