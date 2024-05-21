---
title: Question-8
pagetitle: Question-8
---

Let $A$ be a real $3\times3$ matrix:

$$
A=\begin{bmatrix}C_{1} & C_{2} & C_{3}\end{bmatrix}
$$


Find the determinant of all the following matrices in terms of $|A|$:

$$
\begin{aligned}
A_{1} & =\begin{bmatrix}C_{1} & C_{2}+5C_{3} & C_{3}\end{bmatrix}\\
A_{2} & =\begin{bmatrix}C_{1}+C_{2}+C_{3} & C_{2} & C_{3}\end{bmatrix}\\
A_{3} & =\begin{bmatrix}C_{1} & C_{2}+5C_{3} & 0\end{bmatrix}\\
A_{4} & =\begin{bmatrix}C_{1}+C_{2} & C_{2}+C_{3} & C_{3}+C_{1}\end{bmatrix}
\end{aligned}
$$


------------------------------------------------------------------------

Since $A_{3}$ has a zero column, $|A_{3}|=0$.

-   To get $A_{1}$, we perform $C_{2}\rightarrow C_{2}+5C_{3}$.

-   To get $A_{2}$, we perform $C_{1}\rightarrow C_{1}+C_{2}+C_{3}$

Both these operations do not change the determinant. So $|A_{1}|=|A_{2}|=|A|$. $A_{4}$ is slightly tricky:

$$
\begin{aligned}
\begin{vmatrix}C_{1}+C_{2} & C_{2}+C_{3} & C_{3}+C_{1}\end{vmatrix} & =\begin{vmatrix}2(C_{1}+C_{2}+C_{3}) & C_{2}+C_{3} & C_{3}+C_{1}\end{vmatrix}\\
 & =2\begin{vmatrix}C_{1}+C_{2}+C_{3} & C_{2}+C_{3} & C_{3}+C_{1}\end{vmatrix}\\
 & =2\begin{vmatrix}C_{1} & C_{2}+C_{3} & C_{3}+C_{1}\end{vmatrix}\\
 & =2\begin{vmatrix}C_{1} & C_{2}+C_{3} & C_{3}\end{vmatrix}\\
 & =2\begin{vmatrix}C_{1} & C_{2} & C_{3}\end{vmatrix}\\
 & =2|A|
\end{aligned}
$$

