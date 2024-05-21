---
title: Reversible Transformations
pagetitle: Reversible Transformations
---

## Simple equations

Solving equations can sometimes be tricky.

$$
x^{2}=4
$$


The right approach to solve this question is as follows:

$$
\begin{aligned}
x^{2}-4 & =0\\
(x-2)(x+2) & =0\\
x & =\pm2
\end{aligned}
$$


The more complicated approach is to apply the transformation "take square root on both sides", which is admissible since both sides are positive. Though this is not quite elegant, this will give us the same answer:

$$
\begin{aligned}
x^{2} & =4\\
|x| & =2\\
x & =\pm2
\end{aligned}
$$


The square root can be viewed as a function from $[0,\infty)$ to $[0,\infty)$. So each non-negative input has exactly one non-negative output. With this, the square root of $x^{2}$ has to be $|x|$, a non-negative quantity.

Solving equations can get tricky when you start transforming equations. For example, consider the following sequence of transformations:

$$
\begin{aligned}
x & =2\\
x^{2} & =4 & \text{squaring}\\
|x| & =2 & \text{square root}\\
x & =\pm2
\end{aligned}
$$


How can $x$ be $2$ and $-2$? The problem is with squaring both sides. The equation $x=2$ and $x^{2}=4$ are not the same. That is, $x=2\implies x^{2}=4$, but $x^{2}=4$ does not lead to $x=2$. Squaring is not a "reversible transformation". We usually ignore $x=-2$, calling it an extraneous solution, but what makes it extraneous is the fact that transformations may not be reversible.

## Gaussian Elimination

A classic example of a reversible transformations is row reduction that is employed in Gaussian elimination. Each row reduction operation is equivalent to pre-multiplying by an invertible (elementary) matrix. Going from a matrix $A$ to its RREF form, $R$, involves a sequence of matrix multiplications:

$$
E_{m}\cdots E_{1}A=R
$$


This can be written as $EA=R$, where $E=E_{m}\cdots E_{1}$, and $E$ is invertible. Solving $Ax=b$, is therefore equivalent to solving $EAx=Eb$. The reversibility of the transformation is what allows us to "temporarily forget" the original system and focus on the reduced system.

## Optimization

A third example of a reversible transformation appears in optimization problems. Let us say we wish to find a rectangle with the longest diagonal with a given perimeter:

$$
\begin{aligned}
\max\,\,\, & \sqrt{x^{2}+y^{2}}\\
\\2(x+y) & =p\\
x,y & \geq0
\end{aligned}
$$


It is easier to maximize $x^{2}+y^{2}$ rather than $\sqrt{x^{2}+y^{2}}$:

$$
\begin{aligned}
\max\,\,\, & x^{2}+y^{2}\\
\\2(x+y) & =p\\
x,y & \geq0
\end{aligned}
$$


What makes these two optimization problems equivalent? If we wish to be really rigorous, we can start by looking at the feasible set. This remains the same for both the problems as the constraints haven't changed. Let us call this set $F$. If $(x_{1},y_{1})$ maximizes the first version, what does it mean?

$$
\sqrt{x_{1}^{2}+y_{1}^{2}}\geq\sqrt{x^{2}+y^{2}},\,\,\forall\,(x,y)\in F
$$


Since both sides are positive, this means:

$$
x_{1}^{2}+y_{1}^{2}\geq x^{2}+y^{2},\,\forall\,(x,y)\in F
$$


Thus $(x_{1},y_{1})$ maximizes the second version. We can now go in the other direction and the result will be the same. The operation of "squaring" the objective happened to be reversible in this case. Another reversible transformation in the context of optimization is to maximize the log-likelihood instead of the likelihood.
