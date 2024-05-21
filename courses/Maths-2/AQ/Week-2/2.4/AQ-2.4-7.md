---
title: Question-7
pagetitle: Question-7
---

Solve the following system using Gaussian elimination.

$$
\begin{aligned}
2x_{1}+x_{2} & =3\\
x_{1}+3x_{2} & =4
\end{aligned}
$$


------------------------------------------------------------------------

Let us form the augmented matrix:

$$
\begin{bmatrix}2 & 1 &  & 3\\
1 & 3 &  & 4
\end{bmatrix}
$$


We now start row reduction:

$R_{1}\leftrightarrow R_{2}$

$$
\begin{bmatrix}1 & 3 &  & 4\\
2 & 1 &  & 3
\end{bmatrix}
$$


$R_{2}\rightarrow R_{2}-2R_{1}$

$$
\begin{bmatrix}1 & 3 &  & 4\\
0 & -5 &  & -5
\end{bmatrix}
$$


$R_{2}\rightarrow\cfrac{-1}{5}R_{2}$

$$
\begin{bmatrix}1 & 3 &  & 4\\
0 & 1 &  & 1
\end{bmatrix}
$$


The matrix is now in REF. We now proceed to get the RREF.

$R_{1}\rightarrow R_{1}-3R_{2}$

$$
\begin{bmatrix}\boldsymbol{1} & 0 &  & 1\\
0 & \boldsymbol{1} &  & 1
\end{bmatrix}
$$


We have transformed $Ax=b$ into $Rx=c$, where $R$ is in RREF. All that remains is to read off the solution here:

$$
\begin{aligned}
x_{2} & =1\\
x_{1} & =1
\end{aligned}
$$


Since both $x_{1}$ and $x_{2}$ are dependent variables, the solution is unique.
