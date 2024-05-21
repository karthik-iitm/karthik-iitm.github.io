---
title: Spectral Theorem (real version)
pagetitle: Spectral Theorem (real version)
---

If $A$ is a real symmetric matrix, then it is orthogonally diagonalizable. In particular, there exists an orthogonal matrix $Q$ and a diagonal matrix $D$ such that:

$$
A=QDQ^{T}
$$


If the order of $A$ is $n$, we can express $Q$ and $D$ as:

$$
Q=\begin{bmatrix}\vert &  & \vert\\
q_{1} & \cdots & q_{n}\\
\vert &  & \vert
\end{bmatrix},\,\,\,\,D=\begin{bmatrix}\lambda_{1}\\
 & \ddots\\
 &  & \lambda_{n}
\end{bmatrix}
$$


The columns of $Q$ are the eigenvectors of $A$. The corresponding eigenvalues are to be found on the diagonals of $D$. Therefore, $(\lambda_{i},q_{i})$ is an eigenpair of $A$, that is, $Aq_{i}=\lambda_{i}q_{i}$. Also, $q_{1},\cdots,q_{n}$ form an orthonormal basis for $\mathbb{R}^{n}$. Recall that:

$$
Q^{T}Q=QQ^{T}=I
$$


We can also express $A$ as the sum of $n$ outer products:

$$
A=\sum\limits_{i=1}^{n}\lambda_{i}q_{i}q_{i}^{T}
$$


One way of seeing this is to treat the product $QDQ^{T}$ as $(QD)Q^{T}$. Since $D$ is diagonal, $QD$ would just result in scaling the columns of $Q$ by the corresponding diagonal entries in $D$:

$$
QD=\begin{bmatrix}\vert &  & \vert\\
\lambda_{1}q_{1} & \cdots & \lambda_{n}q_{n}\\
\vert &  & \vert
\end{bmatrix}
$$


The outer product now follows.

Here is an example of a symmetric matrix and its spectral decomposition:

$$
A=\begin{bmatrix}2 & 0 & -1\\
0 & 2 & 0\\
-1 & 0 & 2
\end{bmatrix},\,\,\,\,Q=\frac{1}{\sqrt{2}}\begin{bmatrix}1 & 0 & 1\\
0 & 1 & 0\\
1 & 0 & -1
\end{bmatrix},\,\,\,\,D=\begin{bmatrix}1 & 0 & 0\\
0 & 2 & 0\\
0 & 0 & 3
\end{bmatrix}
$$

