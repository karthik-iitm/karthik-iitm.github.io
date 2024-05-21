---
title: Question-6
pagetitle: Question-6
---

$A$ is a square matrix of order $2$.

-   Is $A=\pm I$ the only solution to $A^{2}=I$

-   Is $A=0$ the only solution to $A^{2}=0$

------------------------------------------------------------------------

Let $A=\begin{bmatrix}a & b\\
c & d
\end{bmatrix}$. We can now compute $A^{2}$:

$$
\begin{aligned}
A^{2} & =\begin{bmatrix}a & b\\
c & d
\end{bmatrix}\begin{bmatrix}a & b\\
c & d
\end{bmatrix}\\
 & =\begin{bmatrix}a^{2}+bc & ab+bd\\
ac+cd & bc+d^{2}
\end{bmatrix}
\end{aligned}
$$


## $A^{2}=0$

If $A^{2}=0$, then:

$$
\begin{aligned}
a^{2}+bc & =0\\
b(a+d) & =0\\
c(a+d) & =0\\
d^{2}+bc & =0
\end{aligned}
$$


One solution is to have $a=b=c=d=0$. But this is not the only one. The presence of $a+d$ in two equations suggests that it might be useful to set $a+d=0$. We can set $a=1,d=-1$. Since $bc$ appears in two equations, we can set $b=1,c=-1$. We have $A=\begin{bmatrix}1 & 1\\
-1 & -1
\end{bmatrix}.$ Verify that $A^{2}=0$.

## $A^{2}=I$

Moving to $A^{2}=I$, we have to solve the following system:

$$
\begin{aligned}
a^{2}+bc & =1\\
b(a+d) & =0\\
c(a+d) & =0\\
d^{2}+bc & =1
\end{aligned}
$$


We can set $a=1,d=-1$ and $b=d=0$. This results in $A=\begin{bmatrix}1 & 0\\
0 & -1
\end{bmatrix}$. Verify that $A^{2}=I$.

## Insights

We can therefore conclude that $A^{2}=0$ admits solutions other than $A=0$ and $A^{2}=I$ admits solutions other than $A=\pm I$. This question is insightful for the following reason. Consider the corresponding equations in $\mathbb{R}$:

$$
x^{2}=0\text{ and }x^{2}=1
$$


$x=0$ is the only solution to the first equation and $x=\pm1$ are the only two solutions to the second. This shows the difference between simple algebraic equations in one variable and their matrix counterparts.
