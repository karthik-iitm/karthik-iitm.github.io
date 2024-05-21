---
title: PCA
pagetitle: PCA
---

## Setting up the problem

Let $X$ be a centered dataset of shape $d\times n$:

$$
X=\begin{bmatrix}\vert &  & \vert\\
x_{1} & \cdots & x_{n}\\
\vert &  & \vert
\end{bmatrix}
$$


The $i^{th}$ column of $X$ is the $i^{th}$ data-point. Since $X$ is centered, we have:

$$
\sum_{i=1}^{n}x_{i}=0
$$


We are going to look for a subspace of dimension $k$ that is closest to the dataset. More precisely, we want to minimize the reconstruction error after projecting the data-points onto this subspace. We can always find an orthonormal basis for a subspace. Let us call this subspace $W$ and an orthonormal basis for that as $\{w_{1},\cdots,w_{k}\}$:

The projection of the $i^{th}$ data-point onto this subspace is:

$$
\sum\limits_{j=1}^{k}(x_{i}^{T}w_{j})w_{j}
$$


The residue in projecting this data-point onto the subspace is:

$$
e_{i}=x_{i}-\left[\sum\limits_{j=1}^{k}(x_{i}^{T}w_{j})w_{j}\right]
$$


The error is $||e_{i}||^{2}$. Let us now expand this error term by using the fact that $||e_{i}||^{2}=e_{i}^{T}e_{i}$.

$$
\begin{aligned}
e_{i}^{T}e_{i} & =x_{i}^{T}x_{i}-\left[\sum\limits_{j=1}^{k}(x_{i}^{T}w_{j})^{2}\right]
\end{aligned}
$$


Since we will be minimizing the error, we can drop $x_{i}^{T}x_{i}$, which is a constant in the context of the minimization problem. We are therefore left with the following quantity for a single data-point:

$$
-\left[\sum\limits_{j=1}^{k}(x_{i}^{T}w_{j})^{2}\right]
$$


For the entire dataset, we sum this error and divide by $n$:

$$
-\frac{1}{n}\sum\limits_{i=1}^{n}\left[\sum\limits_{j=1}^{k}(x_{i}^{T}w_{j})^{2}\right]
$$


Setting $C=\frac{1}{n}\sum\limits_{i=1}^{n}x_{i}x_{i}^{T}$, interchanging the order of the summation and the order of multiplication, we get:

$$
-\sum\limits_{j=1}^{k}w_{j}^{T}\left[\frac{1}{n}\sum\limits_{i=1}^{n}x_{i}x_{i}^{T}\right]w_{j}=-\sum_{j=1}^{k}w_{j}^{T}Cw_{j}
$$


Minimizing the above quantity is the same as maximizing its negation. Therefore, we have the following optimization problem:

$$
\max\,\,\,\sum\limits_{i=1}^{k}w_{i}^{T}Cw_{i}
$$


where $\{w_{1},\cdots,w_{k}\}$ is an orthonormal list of vectors and $C$ is the covariance matrix of the dataset.

## Solving the problem

Since $C$ is a real symmetric matrix, it is diagonalizable. There is an orthonormal basis of eigenvectors of $C$ for $\mathbb{R}^{d}$. Let us denote it by $\{u,\cdots,u_{d}\}$. We also note that $C$ is positive semi-definite, so it has $d$ non-negative eigenvalues. Let us call them $\lambda_{1}\geq\cdots\geq\lambda_{d}\ge0$. We can represent $C$ as:

$$
C=\sum\limits_{i=1}^{d}\lambda_{i}u_{i}u_{i}^{T}
$$


Plugging this back into the objective function, we have:

$$
\begin{aligned}
\sum\limits_{i=1}^{k}w_{i}^{T}Cw_{i} & =\sum\limits_{i=1}^{k}\sum\limits_{j=1}^{d}\lambda_{j}(w_{i}^{T}u_{j})^{2}
\end{aligned}
$$


Changing the order of the summation inside, we have:

$$
\sum_{j=1}^{d}\lambda_{j}\sum_{i=1}^{k}(u_{j}^{T}w_{i})^{2}
$$


The term $\sum\limits_{i=1}^{k}(u_{j}^{T}w_{i})^{2}$ is the squared norm of the projection of $u_{j}$ onto the subspace $W$. Since the norm of a vector is always greater than or equal to the norm of its projection, we have:

$$
\sum_{i=1}^{k}(u_{j}^{T}w_{i})^{2}\leq||u_{j}||^{2}=1
$$


Applying this inequality across all values of $j$, we end up with:

$$
\sum\limits_{i=1}^{k}w_{i}^{T}Cw_{i}\leq\sum_{j=1}^{d}\lambda_{j}
$$


We have thus arrived at an upper bound for the objective function. This upper bound can actually be achieved when $w_{i}=u_{i}$ for $1\leq i\leq k$.

## Summary

In summary, the subspace that is closest to the dataset is the one spanned by the top $k$ eigenvectors of the covariance matrix of the centered dataset.
