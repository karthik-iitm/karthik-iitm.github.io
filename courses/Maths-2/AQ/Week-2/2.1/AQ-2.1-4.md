---
title: Question-4
pagetitle: Question-4
---

Consider the matrix:

$$
\begin{bmatrix}a & b & c\\
b & c & a\\
c & a & b
\end{bmatrix}
$$


If $a+b+c$ is divisible by $6$, is $\text{det}(A)$ also divisible by $6$?

------------------------------------------------------------------------

We can compute the determinant as follows:

$$
\begin{aligned}
\begin{vmatrix}a & b & c\\
b & c & a\\
c & a & b
\end{vmatrix} & =\begin{vmatrix}a+b+c & a+b+c & a+b+c\\
b & c & a\\
c & a & b
\end{vmatrix}\\
 & =(a+b+c)\begin{vmatrix}1 & 1 & 1\\
b & c & a\\
c & a & b
\end{vmatrix}\\
 & =(a+b+c)\begin{vmatrix}1 & 0 & 0\\
b & c-b & a-b\\
c & a-c & b-c
\end{vmatrix}\\
 & =(a+b+c)(ab+bc+ca-a^{2}-b^{2}-c^{2})
\end{aligned}
$$


The determinant of the matrix is divisible by $a+b+c$. Therefore, it is also divisible by $6$.
