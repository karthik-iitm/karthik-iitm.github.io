---
title: $\mathbf{X} \mathbf{w}=\mathbf{0}$
pagetitle: Xw=0
order: 5
---

::: {.callout-note title="Question"}

How do we solve for $\mathbf{w}$ in the equation $\mathbf{Xw}=\mathbf{0}$?

:::

## Setting

Before we tackle the general problem of $\mathbf{Xw}=\mathbf{y}$, let us first see if we can solve the system when $\mathbf{y}$ is the zero vector. In all the discussions that follow, this will be our setting:

- $\mathbf{X}$ is a matrix of dimensions $n\times d$
- $\mathbf{w}\in\mathbb{R}^{d}$

- $\mathbf{Xw}\in\mathbb{R}^{n}$

The equation that we have taken up is:

$$
\mathbf{Xw}=\mathbf{0}
$$


## Nullspace

We can immediately see that $\mathbf{w}=\mathbf{0}$ is a solution. However, this is a trivial solution and is not particularly interesting. We would like to search for non-trivial solutions. Let us begin optimistically by assuming that at least one such solution exists, say $\mathbf{w}_{1}$. Then, we can see that $k\mathbf{w}_{1}$ is also a solution. This is because:
$$
\mathbf{X}(k\mathbf{w}_{1})=k\cdot\mathbf{Xw}_{1}=\mathbf{0}
$$
Also, if $\mathbf{w}_{1}$ and $\mathbf{w}_{2}$ are two solutions to the equation, then $\mathbf{w}_{1}+\mathbf{w}_{2}$ is also a solution, as:
$$
\mathbf{X}(\mathbf{w}_{1}+\mathbf{w}_{2})=\mathbf{Xw}_{1}+\mathbf{Xw}_{2}=0
$$
From these two observations, we see that the set of all solutions to the equation $\mathbf{Xw}=\mathbf{0}$ is a subspace of $\mathbb{R}^{d}$. We denote this by $\mathcal{N}(\mathbf{X})$ and we call it the nullspace of $\mathbf{X}$. The dimension of the nullspace is called nullity.

All this is fine, but how does it help us find all the solutions? If we can find a basis for the nullspace, that will help us characterize all the solutions. If $B=\{\mathbf{w}_{1},\cdots,\mathbf{w}_{k}\}$ is a basis for the nullspace, then the set of all solutions to the equation is given by $\mathcal{N}(\mathbf{X})=\text{span}(B)$. To get to the basis, we first need to revisit Gaussian elimination.

## Row-Echelon form

The central idea in Gaussian elimination is to transform a matrix into its row-echelon form. Let us take up an example and work with that:

$$
\mathbf{X}=\begin{bmatrix}1 & 0 & -1 & 0\\
2 & 1 & 0 & 1\\
3 & 1 & -1 & 1
\end{bmatrix}
$$


Recall that we can apply a sequence of any of these three row operations on a matrix:

- swap two rows

- scale a row by a non-zero constant

- add a scalar multiple of a row to another row

<u>Step-1</u>
$$
\begin{bmatrix}1 & 0 & -1 & 0\\
2 & 1 & 0 & 1\\
3 & 1 & -1 & 1
\end{bmatrix}\ \xrightarrow{R_{2}\rightarrow R_{2}-2R_{1}}\begin{bmatrix}1 & 0 & -1 & 0\\
0 & 1 & 2 & 1\\
3 & 1 & -1 & 1
\end{bmatrix}
$$

<u>Step-2</u>
$$
\begin{bmatrix}1 & 0 & -1 & 0\\
0 & 1 & 2 & 1\\
3 & 1 & -1 & 1
\end{bmatrix}\xrightarrow{R_{3}\rightarrow R_{3}-3R_{1}}\begin{bmatrix}1 & 0 & -1 & 0\\
0 & 1 & 2 & 1\\
0 & 1 & 2 & 1
\end{bmatrix}
$$

<u>Step-3</u>
$$
\begin{bmatrix}1 & 0 & -1 & 0\\
0 & 1 & 2 & 1\\
0 & 1 & 2 & 1
\end{bmatrix}\xrightarrow{R_{3}\rightarrow R_{3}-R_{2}}\begin{bmatrix}1 & 0 & -1 & 0\\
0 & 1 & 2 & 1\\
0 & 0 & 0 & 0
\end{bmatrix}
$$


The final matrix that we have is in row-echelon form. Here is a quick reminder of when a matrix is in row-echelon matrix is:

-   All rows that have only zeros are at the bottom.

-   The first nonzero entry in a row is always to the right of the first nonzero entry in the row above it.

The first nonzero entry in a row is called a pivot and columns that contain pivots are called pivot columns. The row echelon form a matrix is not unique. However, we can reduce a matrix to its **reduced row echelon form** (RREF), which is unique. A matrix is in reduced row echelon form if:

- It is in row echelon form.
- The only nonzero entry in a pivot column is the pivot.
- All pivots are equal to $1$.

The matrix that we have obtained in this example is actually in RREF. Let us call the RREF of $\mathbf{X}$ as $\mathbf{R}$. We state the following result without proof.

::: {.callout-note}

If $\mathbf{R}$ is the reduced row echelon form of $\mathbf{X}$, then $\mathbf{Xw}=\mathbf{0}$ if and only if $\mathbf{Rw}=\mathbf{0}$

:::

Thus, the nullspace of a matrix and the nullspace of its RREF are the same. This lets us forget $\mathbf{X}$ and instead deal with its row-echelon form directly.

## Recipe for a Basis

Now we have to solve the following equation:

$$
\begin{bmatrix}
\textbf{1} & 0 & -1 & 0\\
0 & \textbf{1} & 2 & 1\\
0 & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}w_{1}\\
w_{2}\\
w_{3}\\
w_{4}
\end{bmatrix}=\begin{bmatrix}0\\
0\\
0\\
0
\end{bmatrix}
$$

Columns $1$ and $2$ are called the pivot columns as they contain the pivots. The variables corresponding to the pivots are called pivot variables, while the others are called free variables. We can now state the algorithm for finding a basis for the nullspace of $\mathbf{\boldsymbol{X}}$:

### Algorithm

::: {.callout-note title="Algorithm: Find a basis of ${\displaystyle \mathcal{N}(\mathbf{X})}$"}

- $B=\{\}$

- For each free variable $w_{i}$:
  - Set $w_{i}=1$ and $w_{j}=0$ for all free variables, $j\neq i$
  - Solve for the pivot variables
  - Add $\mathbf{w}$ to $B$
- Return ${\displaystyle B}$​

:::

$B$ is the required basis. Let us try it out here. $w_{1}$ and $w_{2}$ are the pivot variables. $w_{3}$ and $w_{4}$ are the free variables. First, let us set $w_{3}=1,w_{4}=0$. This gives us $w_{1}=1,w_{2}=-2$. The first element of the basis is therefore $\begin{bmatrix}1 & -2 & 1 & 0\end{bmatrix}^{T}$. Next, we set $w_{3}=0,w_{4}=1$. This gives us $w_{1}=0,w_{2}=-1$. The second element of the basis is $\begin{bmatrix}0 & -1 & 0 & 1\end{bmatrix}^{T}$. Thus, a basis for $\mathcal{N}(\mathbf{X})$ is:

$$
B=\left\{ \begin{bmatrix}1\\
-2\\
1\\
0
\end{bmatrix},\begin{bmatrix}0\\
-1\\
0\\
1
\end{bmatrix}\right\}
$$


The set of all solutions for the equation $\mathbf{Xw}=\mathbf{0}$ is $\text{span}(B)$.

### Proof

If you are wondering why this algorithm works, note that the rank of the matrix, $r$, is equal to the number of non-zero rows in the row-echelon form of ${\displaystyle \mathbf{X}}$. If we look at the columns, then we have ${\displaystyle r}$ pivot columns. These ${\displaystyle r}$ columns are linearly independent by construction. Therefore, each of the remaining ${\displaystyle d-r}$ columns can be expressed as a unique linear combination of these ${\displaystyle r}$ pivot columns. The coefficients of this linear combination are going to come from our ${\displaystyle d}$ variables, ${\displaystyle w_{1},\cdots,w_{d}}$.

Recall that the matrix ${\displaystyle \mathbf{X}}$ is ${\displaystyle n\times d}$. From the rank-nullity theorem, we know that the nullity is going to be $d-r$. Thus a basis of $\mathcal{N}(\mathbf{X})$ will have $d-r$ linearly independent vectors. We have to hunt for these $d-r$ vectors. To get there, we divide the $d$ variables into two parts:

-   $r$ pivot variables: variables corresponding to the pivot columns

-   $d-r$ free variables: all other variables

To get a basis vector, we set one of the $d-r$ free variables to $1$ and the rest to $0$. Basically, here we are trying to express a non-pivot column as a linear combination of the ${\displaystyle r}$ pivot columns. Then we determine the $r$ pivot variables (coefficients of the combination) by solving the $r$ equations corresponding to them. The resulting ${\displaystyle \mathbf{w}}$ vector is one element in the basis. By repeating this process with each of the $d-r$ free variables, we are guaranteed to have $d-r$ linearly independent vectors.

## Summary

In order to solve the equation $\mathbf{Xw}=\mathbf{0}$, we first reduce the matrix $\mathbf{X}$ to its row-echelon form. Then we use an iterative algorithm to construct a basis for the nullspace of $\mathbf{X}$. The span of the basis is the set of all solutions to this equation.
