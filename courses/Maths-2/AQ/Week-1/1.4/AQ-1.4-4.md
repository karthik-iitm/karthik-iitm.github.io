---
title: Question-4
pagetitle: Question-4
---

Let $A=\begin{bmatrix}a_{11} & a_{12} & a_{13}\\
ta_{11}-sa_{31} & ta_{12}-sa_{32} & ta_{13}-sa_{33}\\
ra_{31} & ra_{32} & ra_{33}
\end{bmatrix}$ be a matrix and $r,s,t\neq0$. Find $\text{det}(A)$.

------------------------------------------------------------------------

Consider the matrix $B$:

$$
B=\begin{bmatrix}a_{11} & a_{12} & a_{13}\\
0 & 0 & 0\\
a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$


We can now do the following row operations on $B$:

$$
\begin{aligned}
R_{2} & \rightarrow R_{2}+tR_{1}-sR_{3}\\
R_{3} & \rightarrow rR_{3}
\end{aligned}
$$


These two row operations will give us $A$. The determinants are related as follows:

$$
\text{det}(A)=r\cdot\text{det}(B)
$$


Since $B$ has a zero row, its determinant is zero. Hence $\text{det}(A)=0$.
