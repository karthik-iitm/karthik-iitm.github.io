---
title: Question-6
pagetitle: Question-6
---

Suppose a system of linear equations consists of only one equation and four variables:

$$
x_{1}+x_{2}+x_{3}+x_{4}=a
$$


where $a$ is a constant. Find out the number of independent variables and find all possible solutions to this system.

------------------------------------------------------------------------

We can form the matrix corresponding to this:

$$
\begin{bmatrix}\boldsymbol{1} & 1 & 1 & 1\end{bmatrix}
$$


The first column is a pivot column. Hence, $x_{1}$ is a dependent variable. $x_{2},x_{3},x_{4}$ are independent variables. So this equation has three independent variables. To solve the system, we give arbitrary values to the independent variables and then solve for the dependent variable:

$$
\begin{aligned}
x_{2} & =t_{2}\\
x_{3} & =t_{3}\\
x_{4} & =t_{4}\\
\implies x_{1} & =a-(t_{2}+t_{3}+t_{4})
\end{aligned}
$$


Therefore, the set of all solutions to this system can be represented by this set:

$$
S=\left\{ \left(a-(t_{2}+t_{3}+t_{4}),t_{2},t_{3},t_{4}\right)\,:\,t_{2},t_{3},t_{4}\in\mathbb{R}\right\}
$$

