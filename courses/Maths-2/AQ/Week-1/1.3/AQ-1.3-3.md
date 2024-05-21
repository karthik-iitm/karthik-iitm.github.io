---
title: Question-3
pagetitle: Question-3
---

Comment on the truth value of the following statements:

1.  Every system of linear equations has either a unique solution, no solution or infinitely many solutions.

2.  If each equation in a system of linear equations is multiplied by a non-zero constant $c$ then the solution of the system is $c$ times the solution of the old system.

3.  If $Ax=b$ has a solution, then $cAx=b$ where $c\neq0$ will also have a solution.

4.  If $Ax=b$ has a solution, then $\frac{1}{c}Ax=b$ where $c\neq0$ will also have a solution.

------------------------------------------------------------------------

## Statement-1

Geometrically, it is quite clear that these are the only three possibilities. Algebraically, let us try to understand the case of infinite solutions a little better. Why can't a particular system have only two solutions, for instance? Let $x_{1}$ and $x_{2}$ be two solutions, then $(c+1)x_{1}-cx_{2}$ is also a solution. This is because:

$$
\begin{aligned}
A[(c+1)x_{1}-cx_{2}] & =(c+1)Ax_{1}-cAx_{2}\\
 & =(c+1)b-cb\\
 & =b
\end{aligned}
$$


Since $c$ is an arbitrary parameter, we see that there are infinitely many solutions.

## Statement-2

Multiplying each equation by $c$ corresponds to scaling each row of the matrix $A$ by $c$ and scaling each component of the vector $b$ by $c$. Multiplying each row of $A$ by $c$ is the same as multiplying the entire matrix by $c$. Scaling each component of $b$ by $c$ is the same as scaling the vector $b$ by $c$. If $x^{*}$ is a solution of the system $Ax=b$, then:

$$
\begin{aligned}
Ax^{*} & =b\\
cAx^{*} & =cb\\
(cA)x^{*} & =cb
\end{aligned}
$$


Note that the second step is valid only if $c$ is a non-zero constant. We see that the new system is $(cA)x^{*}=cb$. The solution of this system is still $x^{*}$. This shows that multiplying all equations by a non-zero constant doesn't change the solution to the system.

## Statement-3

Let the solution to $Ax=b$ be $x^{*}$. Then, $Ax^{*}=b$.

$$
\begin{aligned}
Ax^{*} & =b\\
cAx^{*} & =cb\\
cA\left(\frac{x^{*}}{c}\right) & =b
\end{aligned}
$$


We see that $\frac{x^{*}}{c}$ is a solution to the system $cAx=b$.

## Statement-4

This is just a special case of the previous statement.
