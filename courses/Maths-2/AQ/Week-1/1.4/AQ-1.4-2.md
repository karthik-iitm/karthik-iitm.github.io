---
title: Question-2
pagetitle: Question-2
---

Consider the two matrices:

$$
A=\begin{bmatrix}2 & -1 & 1\\
1 & -3 & 4\\
-1 & 0 & 2
\end{bmatrix},\,\,\,\,B=\begin{bmatrix}1 & 3 & -2\\
0 & 1 & -1\\
3 & 4 & 2
\end{bmatrix}
$$


Find $\text{det}(A),\text{det}(B),\text{det}(AB),\text{det}(BA)$.

------------------------------------------------------------------------

The following solution to find the determinant is unnecessarily long. We can perform a sequence of row operations on $A$:

$R_{3}\rightarrow R_{3}+R_{2}$

$$
\begin{aligned}
\begin{bmatrix}2 & -1 & 1\\
1 & -3 & 4\\
-1 & 0 & 2
\end{bmatrix} & \rightarrow\begin{bmatrix}2 & -1 & 1\\
1 & -3 & 4\\
0 & -3 & 6
\end{bmatrix}
\end{aligned}
$$


This operation doesn't change the determinant.

$R_{3}\rightarrow\frac{-1}{3}R_{3}$

$$
\begin{bmatrix}2 & -1 & 1\\
1 & -3 & 4\\
0 & -3 & 6
\end{bmatrix}\rightarrow\begin{bmatrix}2 & -1 & 1\\
1 & -3 & 4\\
0 & 1 & -2
\end{bmatrix}
$$


This operation scales the determinant by $\frac{-1}{3}$.

$R_{1}\rightarrow R_{1}-2R_{2}$

$$
\begin{bmatrix}2 & -1 & 1\\
1 & -3 & 4\\
0 & 1 & -2
\end{bmatrix}\rightarrow\begin{bmatrix}0 & 5 & -7\\
1 & -3 & 4\\
0 & 1 & -2
\end{bmatrix}
$$


This operation doesn't change the determinant.

$R_{1}\leftrightarrow R_{2}$

$$
\begin{bmatrix}0 & 5 & -7\\
1 & -3 & 4\\
0 & 1 & -2
\end{bmatrix}\rightarrow\begin{bmatrix}1 & -3 & 4\\
0 & 5 & -7\\
0 & 1 & -2
\end{bmatrix}
$$


This operation scales the determinant by $-1$.

$R_{2}\rightarrow R_{2}-5R_{3}$

$$
\begin{bmatrix}1 & -3 & 4\\
0 & 5 & -7\\
0 & 1 & -2
\end{bmatrix}\rightarrow\begin{bmatrix}1 & -3 & 4\\
0 & 0 & 3\\
0 & 1 & -2
\end{bmatrix}
$$


This operation doesn't change the determinant.

$R_{2}\rightarrow\frac{1}{3}R_{2}$

$$
\begin{bmatrix}1 & -3 & 4\\
0 & 0 & 3\\
0 & 1 & -2
\end{bmatrix}\rightarrow\begin{bmatrix}1 & -3 & 4\\
0 & 0 & 1\\
0 & 1 & -2
\end{bmatrix}
$$


This operation scales the determinant by $\frac{1}{3}$.

$R_{2}\leftrightarrow R_{3}$

$$
\begin{bmatrix}1 & -3 & 4\\
0 & 0 & 1\\
0 & 1 & -2
\end{bmatrix}\rightarrow\begin{bmatrix}1 & -3 & 4\\
0 & 1 & -2\\
0 & 0 & 1
\end{bmatrix}
$$


This operation scales the determinant by $-1$.

The final matrix that we have is an upper triangular matrix. The determinant of an upper triangular matrix is the product of its diagonal entries, which is $1$ in this case. So we have:

$$
\begin{aligned}
1 & =\text{det}(A)\times\frac{-1}{3}\times(-1)\times\frac{1}{3}\times(-1)\\
\text{det}(A) & =-9
\end{aligned}
$$


For $\text{det}(B)$, we will expand the determinant along the first column:

$$
\begin{vmatrix}1 & 3 & -2\\
0 & 1 & -1\\
3 & 4 & 2
\end{vmatrix}=1(2+4)+3(-3+2)=3
$$


For $\text{det}(AB)$, we just use the property that $\text{det}(AB)=\text{det}(A)\cdot\text{det}(B)$. Thus, we get $\text{det}(AB)=-27$. $\text{det}(BA)$ is going to be the same.
