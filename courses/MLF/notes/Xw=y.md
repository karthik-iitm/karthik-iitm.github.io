---
title: $\mathbf{Xw} = \mathbf{y}$
pagetitle: Xw=y
order: 6
---

::: {.callout-note title="Question"}

How do we solve for $\mathbf{w}$ in the equation $\mathbf{Xw} =\mathbf{y}$?

:::

## Column space

Now we come to the general form of the equation, $\mathbf{Xw} =\mathbf{y}$. First, we need to know if the equation admits any solution at all. For this, we have to take a closer look at this equation and see what it means:

$$
\begin{equation*}
\begin{bmatrix}
| &  & |\\
\mathbf{c}_{1} & \cdots  & \mathbf{c}_{d}\\
| &  & |
\end{bmatrix}\begin{bmatrix}
w_{1}\\
\vdots \\
w_{d}
\end{bmatrix} =\begin{bmatrix}
y_{1}\\
\vdots \\
y_{n}
\end{bmatrix}
\end{equation*}
$$

Here, $\mathbf{c}_{1} ,\cdots ,\mathbf{c}_{d}$ are the columns of $\mathbf{X}$. Recall that the product of a matrix and a vector can be interpreted as a linear combination of the columns of the matrix:

$$
\begin{equation*}
w_{1}\mathbf{c}_{1} +\cdots +w_{d}\mathbf{c}_{d} =\mathbf{y}
\end{equation*}
$$

$\mathbf{Xw} =\mathbf{y}$ has a solution if and only if $\mathbf{y}$ can be expressed as a linear combination of the columns of $\mathbf{X}$. Since the set of all linear combination of $\mathbf{X}$ is given by the $\text{span} (\{\mathbf{c}_{1} ,\cdots ,\mathbf{c}_{d} \})$, the equation is solvable if and only if $y\in \text{span} (\{\mathbf{c}_{1} ,\cdots ,\mathbf{c}_{n} \})$

The span of the columns of $\mathbf{X}$ is a subspace of $\displaystyle \mathbb{R}^{n}$ and is called the column space of the matrix $\mathbf{X}$ and we denote it by $\mathcal{R}(\mathbf{X})$:
$$
\mathcal{R} (\mathbf{X} )=\text{span} (\{\mathbf{c}_{1} ,\cdots ,\mathbf{c}_{d} \})
$$
 We have now answered the question of when $\mathbf{Xw} =\mathbf{y}$ is solvable. Since this is important, let us highlight it:

::: {.callout-important}

$\mathbf{Xw}=\mathbf{y}$ has a solution if and only if $\mathbf{y}$ is in the column space of $\mathbf{X}$

:::



## Conditions for Solution

Let us reuse the example from the previous unit:

$$
\begin{equation*}
\begin{bmatrix}
1 & 0 & -1 & 0\\
2 & 1 & 0 & 1\\
3 & 1 & -1 & 1
\end{bmatrix}\begin{bmatrix}
w_{1}\\
w_{2}\\
w_{3}\\
w_{4}
\end{bmatrix} =\begin{bmatrix}
y_{1}\\
y_{2}\\
y_{3}
\end{bmatrix}
\end{equation*}
$$

We are back to the row-echelon form, but with the augmented matrix:

$$
\begin{equation*}
\begin{bmatrix}
1 & 0 & -1 & 0 & y_{1}\\
2 & 1 & 0 & 1 & y_{2}\\
3 & 1 & -1 & 1 & y_{3}
\end{bmatrix}
\end{equation*}
$$

If we apply the same sequence of row operations as in the previous case, we get:

$$
\begin{equation*}
\begin{bmatrix}
1 & 0 & -1 & 0 & y_{1}\\
0 & 1 & 2 & 1 & y_{2} -2y_{1}\\
0 & 0 & 0 & 0 & y_{3} -y_{1} -y_{2}
\end{bmatrix}
\end{equation*}
$$

We can immediately see that the system has a solution if and only if the following condition is met:

$$
\begin{equation*}
y_{3} -y_{1} -y_{2} =0
\end{equation*}
$$

Now that we have the row-echelon matrix, let us rephrase the equation as follows:

$$
\begin{equation*}
\begin{bmatrix}
1 & 0 & -1 & 0\\
0 & 1 & 2 & 1\\
0 & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}
w_{1}\\
w_{2}\\
w_{3}\\
w_{4}
\end{bmatrix} =\begin{bmatrix}
y_{1}\\
y_{2} -2y_{1}\\
y_{3} -y_{1} -y_{2}
\end{bmatrix}
\end{equation*}
$$

Going back to a general system, let us call this system after row reduction $\mathbf{Rw} =\mathbf{z}$. We state the following result without proof:

::: {.callout-note title="Remark"}
$\mathbf{w}$ is a solution to $\mathbf{Xw} =\mathbf{y}$ if and only if $\mathbf{w}$ is a solution to $\mathbf{Rw} =\mathbf{z}$, where $\mathbf{R} \ |\mathbf{\ z}$ is the augmented matrix after Gaussian elimination.
:::



This allows us to work with the reduced system while temporarily forgetting the original system.



## General Solution

### Description

If a solution exists, how do we find it? And what about all possible solutions? Let us now turn our attention to the system after row reduction:
$$
\mathbf{R} \mathbf{x} = \mathbf{z}
$$
First note that the set of pivot columns are linearly independent and form a basis for the column space of $\mathbf{R}$. In the example we are working with, this is quite clear:
$$
\begin{equation*}
\mathcal{R} (\mathbf{R} )=\text{span}\left(\left\{\begin{bmatrix}
1\\
0\\
0
\end{bmatrix} ,\begin{bmatrix}
0\\
1\\
0
\end{bmatrix}\right\}\right)
\end{equation*}
$$

So, $\mathbf{y}$ can be uniquely expressed as a linear combination of the columns of this basis. Let us call this the particular solution $\mathbf{w}_{p}$. If $\mathbf{w}_{n}$ is some vector in the nullspace of $\mathbf{X}$, then every general solution $\mathbf{w}_{g}$ to the equation can be expressed in this form:

$$
\begin{equation*}
\mathbf{w}_{g} =\mathbf{w}_{p} +\mathbf{w}_{n}
\end{equation*}
$$

It may still not be clear why every solution should be of this form and we will prove this shortly. Before that, let us express the set of all solutions to a consistent system more formally:
$$
\mathbf{w}_p + \mathcal{N}(\mathbf{X})
$$
This is an affine space. Geometrically, an affine space is a subspace that is translated by some vector. In the simple setting of $\mathbb{R}^{3}$, if the nullspace is a plane passing through the origin, then an affine space would be a plane parallel to it. Coming back to our context, the set of all solutions to $\mathbf{Xw} = \mathbf{y}$ can be obtained by translating the nullspace of $\mathbf{X}$ by a particular solution $\mathbf{x}_p$​​.

### Proof

We will show that this affine space is indeed the solution space. Let us call the set of all solutions $S$. Now, pick up any element in the affine space:
$$
\mathbf{w} = \mathbf{w}_p + \mathbf{w}_n
$$
where $\mathbf{w}_n \in \mathcal{N}(\mathbf{X})$. We see that $\mathbf{w}$ is a solution because:
$$
\begin{equation*}
\mathbf{Xw} =\mathbf{X} (\mathbf{w}_{p} +\mathbf{w}_{n} )=\mathbf{Xw}_{p} +\mathbf{Xw}_{n} =\mathbf{y}
\end{equation*}
$$
We have shown that any arbitrary element of the affine space is also present in $S$. In other words:
$$
\mathbf{w}_p + \mathcal{N}(\mathbf{X}) \subset S
$$
Now we go the other way. Let $\mathbf{w}$ be any element in $S$. We can rewrite $\mathbf{w}$ as:
$$
\mathbf{w} = \mathbf{w}_p + (\mathbf{w} - \mathbf{w}_p)
$$
Now, note that $\mathbf{w} - \mathbf{w}_p \in \mathcal{N}(\mathbf{X})$. This is because:
$$
\mathbf{X}(\mathbf{w} - \mathbf{w}_p) = \mathbf{Xw} - \mathbf{Xw}_p = \mathbf{y} - \mathbf{y} = \mathbf{0}
$$
This shows that $S \subset \mathbf{w}_p + \mathcal{N}(\mathbf{X})$. Thus we have the following beautiful result:

::: {.callout-important}

The set of all solutions to a consistent system $\mathbf{Xw} = \mathbf{y}$ is the affine space $\mathbf{w}_p + \mathcal{N}(\mathbf{X})$, where $\mathbf{w}_{p}$ is a solution to the system.

:::



Coming back to the example we are working with, how do we find the particular solution $\mathbf{w}_{p}$? We set all free variables to zero and solve for the pivot variables:


$$
\begin{equation*}
\mathbf{w}_{p} =\begin{bmatrix}
y_{1}\\
y_{2} -2y_{1}\\
0\\
0
\end{bmatrix}
\end{equation*}
$$

We already know how to get $\mathbf{w}_{n}$. Refer to the previous unit on computing a basis for the nullspace of the matrix.

## Summary

$\mathbf{Xw} =\mathbf{y}$ is solvable if and only if $\mathbf{y}$ is an element of the column space of $\mathbf{X}$. A system that admits a solution is said to be consistent. Every solution to a consistent system of equations can be expressed as $\mathbf{w}_{p} +\mathbf{w}_{n}$, where $\mathbf{w}_{p}$ is a particular solution and $\mathbf{w}_{n}$ is some vector in the nullspace of $\mathbf{X}$. By varying $\mathbf{w}_n$, we can get all possible solutions to the system.