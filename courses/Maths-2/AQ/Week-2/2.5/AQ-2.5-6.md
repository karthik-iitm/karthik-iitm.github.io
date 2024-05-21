---
title: Question-6
pagetitle: Question-6
---

Let the reduced row echelon form of a matrix $A$ be:

$$
\begin{bmatrix}1 & 0 & -1\\
0 & 1 & 1
\end{bmatrix}
$$


The first and the third columns of $A$ are $\begin{bmatrix}-1\\
1
\end{bmatrix}$ and $\begin{bmatrix}2\\
-1
\end{bmatrix}$ respectively. Find the second column of $A$ and thereby the complete matrix.

------------------------------------------------------------------------

Let the matrix $A$ be:

$$
\begin{bmatrix}-1 & a & 2\\
1 & b & -1
\end{bmatrix}
$$


We can start row reduction:

$$
\begin{aligned}
\begin{bmatrix}-1 & a & 2\\
1 & b & -1
\end{bmatrix} & \rightarrow\begin{bmatrix}-1 & a & 2\\
0 & a+b & 1
\end{bmatrix}
\end{aligned}
$$


$$
\begin{aligned}
\begin{bmatrix}-1 & a & 2\\
0 & a+b & 1
\end{bmatrix} & \rightarrow\begin{bmatrix}1 & -a & -2\\
0 & a+b & 1
\end{bmatrix}
\end{aligned}
$$


At this stage, we have to decide if we can divide the second row by $a+b$. This can be done if $a+b\neq0$. This is the case as $a+b=0$ would mean that the second column is no longer a pivot column.

$$
\begin{bmatrix}1 & -a & -2\\
0 & a+b & 1
\end{bmatrix}\rightarrow\begin{bmatrix}1 & -a & -2\\
0 & 1 & \cfrac{1}{a+b}
\end{bmatrix}
$$


If $a=0$, the matrix becomes:

$$
\begin{bmatrix}1 & 0 & -2\\
0 & 1 & \cfrac{1}{b}
\end{bmatrix}
$$


This is in RREF, but no matter what value we choose for $b$, we can never make it equal to the RREF given in the question. So $a\neq0$ and we can proceed with elimination:

$$
\begin{bmatrix}1 & -a & -2\\
0 & 1 & \cfrac{1}{a+b}
\end{bmatrix}\rightarrow\begin{bmatrix}1 & 0 & \cfrac{-a-2b}{a+b}\\
\\0 & 1 & \cfrac{1}{a+b}
\end{bmatrix}
$$


We can now do a direct comparison:

$$
\begin{aligned}
a+b & =1\\
-a-2b & =-1
\end{aligned}
$$


From this, we get $a=1,b=0$. Thus the matrix $A$ is:

$$
\begin{bmatrix}1 & 1 & 2\\
1 & 0 & -1
\end{bmatrix}
$$

