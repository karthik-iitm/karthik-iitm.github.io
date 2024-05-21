---
title: Question-8
pagetitle: Question-8
---

Let $Ax=b$ be a system of linear equations.

$$
A=\begin{bmatrix}1 & 0 & 0 & 0\\
0 & 0 & 1 & 1\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end{bmatrix},\,\,\,x=\begin{bmatrix}x_{1}\\
x_{2}\\
x_{3}\\
x_{4}
\end{bmatrix},\,\,\,\,b=\begin{bmatrix}b_{1}\\
b_{2}\\
b_{3}\\
b_{4}
\end{bmatrix}
$$


-   Find the dependent and independent variables.

-   When is the system consistent?

-   Find out all solutions to this system whenever it is consistent.

------------------------------------------------------------------------

First, note that $A$ is in rref. We first identify the pivots and the pivot columns:

$$
\begin{bmatrix}\boldsymbol{1} & 0 & 0 & 0\\
0 & 0 & \boldsymbol{1} & 1\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end{bmatrix}
$$


The first and third columns are pivot columns. Hence, $x_{1},x_{3}$ are dependent and $x_{2},x_{4}$ are independent variables. For the system to be consistent $b_{3}=b_{4}=0$. Let us now work with this special case:

$$
A=\begin{bmatrix}1 & 0 & 0 & 0\\
0 & 0 & 1 & 1\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end{bmatrix},\,\,\,x=\begin{bmatrix}x_{1}\\
x_{2}\\
x_{3}\\
x_{4}
\end{bmatrix},\,\,\,\,b=\begin{bmatrix}b_{1}\\
b_{2}\\
0\\
0
\end{bmatrix}
$$


We can give arbitrary values to $x_{2}$ and $x_{4}$ and then solve for $x_{1}$ and $x_{3}$:

$$
\begin{aligned}
x_{2} & =t_{2}\\
x_{4} & =t_{4}\\
x_{3} & =b_{2}-t_{4}\\
x_{1} & =b_{1}
\end{aligned}
$$


The set of all solutions to the system is given by:

$$
S=\left\{ \left(b_{1},t_{2},b_{2}-t_{4},t_{4}\right):t_{2},t_{4}\in\mathbb{R}\right\}
$$

