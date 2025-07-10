---
order: 1
title: Week 1
pagetitle: Week 1
---

# Centering the dataset

$$
\mathbf{\bar{x}} = \frac{1}{n} \sum^n_{i=1} \mathbf{x_i}
$$

If the dataset is already centered, $\mathbf{\bar{x}} = \mathbf{0}$, do the following:

$$
\mathbf{x'_i} = \mathbf{x_i} - \mathbf{\bar{x}}
$$

The matrix

$$
\mathbf{X}_c = \begin{bmatrix}
| & & | \\
\mathbf{x'_1} & \cdots & \mathbf{x'_n} \\
| & & |
\end{bmatrix}
$$

is the centered data-matrix.

::: {.callout-note title="Remark"}
From now we will work only with the centered data-matrix and will be calling it $\mathbf{X}$ (the subscript $c$ will be dropped)
:::

# Covariance Matrix

$$
C = \begin{bmatrix}
1 & -0.9 \\
-0.9 & 1 \\
\end{bmatrix}
$$

### Shape

$$
\mathbf{C} \in \mathbf{R}^{d\times d}
$$

### Outer-product form

$$
\mathbf{C} = \frac{1}{n} \sum^n_{i=1} \mathbf{x}_i\mathbf{x}_i^T
$$

### Matrix form

$$
\mathbf{C} = \frac{1}{n} \mathbf{X}\mathbf{X}^T
$$

### Scalar form

$$
\mathbf{C}_{pq} = \frac{1}{n} \sum^n_{i=1} \mathbf{x}_{ip}\mathbf{x}_{iq}
$$

$\mathbf{C}_{pq}$ captures the covariance between the $p^{th}$ feature and the $q^{th}$ feature. As a special case:

$$
\mathbf{C}_{pp} = \frac{1}{n} \sum^n_{i=1} \mathbf{x}_{ip}^2
$$

#### Properties

- $\mathbf{C}^T = \mathbf{C}$
- All eigenvalues of $\mathbf{C}$ are non-negative.
  - $\lambda_1 \ge \cdots \ge \lambda_d \ge 0$
- There is an orthonormal basis for $\mathbf{R}^d$ made up of eigenvectors of $\mathbf{C}$
  - ${\mathbf{w}_1, \cdots, \mathbf{w}_d}$
  - This comes from the spectral theorem.

::: {.callout-note title="Note"}
If $\mathbf{C}$ is a square matrix, then $(\lambda, \mathbf{w})$ is said to be an eigenvalue-eigenvector pair
if $\mathbf{Cw} = \lambda\mathbf{w}$. Note that $\mathbf{w} \neq \mathbf{0}$ for it to be an eigenvector.
:::

::: {.callout-note title="Remark"}
$\mathbf{w}_i$ will always represent a unit-norm vector in the rest of the document.
:::

# Optimization problem

### Minimizing the reconstruction error

$$
\min_{\mathbf{w}} \frac{1}{n} \sum^n_{i=1} || \mathbf{x}_i - (\mathbf{x}_i^T\mathbf{w})\mathbf{w} ||
$$

### Maximizing the variance

$$
\max_{\mathbf{w}} \mathbf{w}^T\mathbf{C}\mathbf{w}
$$

# Principal components

Let $(\lambda_1, \mathbf{w}_1), \cdots, (\lambda_d, \mathbf{w}_d)$ be the eigen-pairs of $\mathbf{C}$ where
$\lambda_1 \ge \cdots \ge \lambda_d$ and ${\mathbf{w}_1, \cdots, \mathbf{w}_d}$ is an orthonormal basis for
$\mathbf{R}^d$.

$\mathbf{w}_i$ is termed the $i^{th}$ principal component of $\mathbf{C}$. To be more precise:

$$
\mathbf{C}\mathbf{w}_i = \lambda_i\mathbf{w}_i
$$

$$
\mathbf{w}_i^T\mathbf{w}_j = \begin{cases}
1, & i = j \\
0, & i \neq j
\end{cases}
$$

$$
\lambda_1 = \max_{\mathbf{w}} \mathbf{w}^T\mathbf{C}\mathbf{w}
$$

$$
\mathbf{w}_1 = \arg\max_{\mathbf{w}} \mathbf{w}^T\mathbf{C}\mathbf{w}
$$

$$
\mathbf{w}_1^T\mathbf{C}\mathbf{w}_1 = \lambda_1
$$

# Projections

Scalar projection of $\mathbf{x}_i$ onto the $j^{th}$ PC

$$
\mathbf{x}_i^T\mathbf{w}_j
$$

The vector projection can be written as the product of the scalar projection and the unit vector that gives the direction.

$$
(\mathbf{x}_i^T\mathbf{w}_j)\mathbf{w}_j
$$

The projection of a data-point $\mathbf{x}_i$ onto the top $k$ principal components

$$
\mathbf{x'}_i = (\mathbf{x}_i^T\mathbf{w}_1)\mathbf{w}_1 + \cdots + (\mathbf{x}_i^T\mathbf{w}_k)\mathbf{w}_k
$$

To represent the reconstruction and scalar projections in matrix form:

$$
\mathbf{W} \in \mathbf{R}^{d\times k}
$$

$$
\mathbf{W} = \begin{bmatrix}
| & & | \\
\mathbf{w}_1 & \cdots & \mathbf{w}_k \\
| & & |
\end{bmatrix}
$$

### Scalar projections

$$
\mathbf{X'} \in \mathbf{R}^{k\times n}
$$

$$
\mathbf{X'} = \begin{bmatrix}
\mathbf{x}_1^T\mathbf{w}_1 & & \mathbf{x}_n^T\mathbf{w}_1 \\
| & \cdots & | \\
\mathbf{x}_1^T\mathbf{w}_k & & \mathbf{x}_n^T\mathbf{w}_k \\
\end{bmatrix}
$$

$$
\mathbf{X'} = \mathbf{W}^T\mathbf{X}
$$

### Reconstruction

$$
\mathbf{X'} \in \mathbf{R}^{d\times n}
$$

$$
\mathbf{X'} = \mathbf{W}\mathbf{W}^T\mathbf{X}
$$

# Reconstruction error revisited (for $k$ directions)

$$
\frac{1}{n} \sum^n_{i=1} || \mathbf{x}_i - \mathbf{x}_i' ||^2
$$

$$
\frac{1}{n} \sum^n_{i=1} || \mathbf{x}_i - \sum_{j=1}^k (\mathbf{x}_i^T\mathbf{w}_j)\mathbf{w}_j ||^2
$$

# Variance captured

Total variance:

$$
\lambda_1 + \cdots + \lambda_d
$$

Variance along a given direction $\mathbf{w}$ (unit vector):

$$
\frac{1}{n} \sum_{i=1}^n (\mathbf{x}_i^T\mathbf{w})^2
$$

$$
\mathbf{w}^T\mathbf{C}\mathbf{w}
$$

Proportion of variance captured by top $k$ PCs:

$$
\frac{\lambda_1 + \cdots + \lambda_k}{\lambda_1 + \cdots + \lambda_d}
$$

Heuristic to choose the value of $k$: smallest value that captures 95% of the variance in the dataset.

# Compression

Reconstruction

$$
\frac{nk+dk}{dn} = \frac{k(d+n)}{dn}
$$

Retaining only scalar projections

$$
\frac{kn}{dn} = \frac{k}{d}
$$
