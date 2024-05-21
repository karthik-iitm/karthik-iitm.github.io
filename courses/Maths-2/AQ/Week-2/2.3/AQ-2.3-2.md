---
title: Question-2
pagetitle: Question-2
---

Find the inverse of the following matrix:

$$
A=\begin{bmatrix}2 & -1 & 0\\
1 & 0 & -1\\
0 & 1 & -1
\end{bmatrix}
$$


------------------------------------------------------------------------

## Method-1

We reduce $A$ to its RREF while simultaneously applying these operations to the identity matrix on the right:

$$
\begin{aligned}
\begin{bmatrix}2 & -1 & 0\\
1 & 0 & -1\\
0 & 1 & -1
\end{bmatrix} &  & \begin{bmatrix}1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}\\
\\\begin{bmatrix}0 & -1 & 2\\
1 & 0 & -1\\
0 & 1 & -1
\end{bmatrix} &  & \begin{bmatrix}1 & -2 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}\\
\\\begin{bmatrix}1 & 0 & -1\\
0 & -1 & 2\\
0 & 1 & -1
\end{bmatrix} &  & \begin{bmatrix}0 & 1 & 0\\
1 & -2 & 0\\
0 & 0 & 1
\end{bmatrix}\\
\\\begin{bmatrix}1 & 0 & -1\\
0 & -1 & 2\\
0 & 0 & 1
\end{bmatrix} &  & \begin{bmatrix}0 & 1 & 0\\
1 & -2 & 0\\
1 & -2 & 1
\end{bmatrix}\\
\\\begin{bmatrix}1 & 0 & -1\\
0 & 1 & -2\\
0 & 0 & 1
\end{bmatrix} &  & \begin{bmatrix}0 & 1 & 0\\
-1 & 2 & 0\\
1 & -2 & 1
\end{bmatrix}\\
\\\begin{bmatrix}1 & 0 & -1\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix} &  & \begin{bmatrix}0 & 1 & 0\\
1 & -2 & 2\\
1 & -2 & 1
\end{bmatrix}\\
\\\begin{bmatrix}1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix} &  & \begin{bmatrix}1 & -1 & 1\\
1 & -2 & 2\\
1 & -2 & 1
\end{bmatrix}
\end{aligned}
$$


We have:

$$
A^{-1}=\begin{bmatrix}1 & -1 & 1\\
1 & -2 & 2\\
1 & -2 & 1
\end{bmatrix}
$$


## Method-2

Alternatively, we have the cofactor matrix. For the sake of convenience, let us write down $A$ again:

$$
A=\begin{bmatrix}2 & -1 & 0\\
1 & 0 & -1\\
0 & 1 & -1
\end{bmatrix}
$$


First for the nine minors:

$$
\begin{aligned}
M_{11} & =\begin{vmatrix}0 & -1\\
1 & -1
\end{vmatrix} & M_{12} & =\begin{vmatrix}1 & -1\\
0 & -1
\end{vmatrix} & M_{13} & =\begin{vmatrix}1 & 0\\
0 & 1
\end{vmatrix}\\
 & =1 &  & =-1 &  & =1\\
\\M_{21} & =\begin{vmatrix}-1 & 0\\
1 & -1
\end{vmatrix} & M_{22} & =\begin{vmatrix}2 & 0\\
0 & -1
\end{vmatrix} & M_{23} & =\begin{vmatrix}2 & -1\\
0 & 1
\end{vmatrix}\\
 & =1 &  & =-2 &  & =2\\
\\M_{31} & =\begin{vmatrix}-1 & 0\\
0 & -1
\end{vmatrix} & M_{32} & =\begin{vmatrix}2 & 0\\
1 & -1
\end{vmatrix} & M_{33} & =\begin{vmatrix}2 & -1\\
1 & 0
\end{vmatrix}\\
 & =1 &  & =-2 &  & =1
\end{aligned}
$$


And now the cofactor matrix:

$$
C=\begin{bmatrix}1 & 1 & 1\\
-1 & -2 & -2\\
1 & 2 & 1
\end{bmatrix}
$$


The determinant of $A$ is $1$. Finally, the inverse is:

$$
\begin{aligned}
A^{-1} & =\cfrac{1}{\text{det}(A)}\text{adj}(A)\\
 & =\cfrac{1}{\text{det}(A)}\cdot C^{T}\\
 & =\begin{bmatrix}1 & -1 & 1\\
1 & -2 & 2\\
1 & -2 & 1
\end{bmatrix}
\end{aligned}
$$

