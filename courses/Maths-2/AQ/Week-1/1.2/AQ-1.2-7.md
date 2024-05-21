---
title: Question-7
pagetitle: Question-7
---

$A$ is a square matrix whose columns are $C_{1}$ and $C_{2}$ and $B=\begin{bmatrix}b_{11} & b_{12}\\
b_{21} & b_{22}
\end{bmatrix}$. What are the first and second columns of $AB$?

------------------------------------------------------------------------

We have $A=\begin{bmatrix}\vert & \vert\\
C_{1} & C_{2}\\
\vert & \vert
\end{bmatrix}$. Let us try to understand what happens when we multiply $A$ with a vector $x=\begin{bmatrix}x_{1}\\
x_{2}
\end{bmatrix}$. We have:

$$
Ax=x_{1}C_{1}+x_{2}C_{2}
$$


We see that $Ax$ is a linear combination of the columns of the matrix $A$, with the coefficients coming from the vector.

The first column of $AB$ is equal to the product of $A$ and the first column of $B$:

$$
b_{11}C_{1}+b_{21}C_{2}
$$


The second column of $AB$ is equal to the product of $A$ and the second column of $B$:

$$
b_{12}C_{1}+b_{22}C_{2}
$$


**Remark**: The product of a matrix and a vector is a linear combination of the columns. This is a very important result and will make an appearance throughout the course.
