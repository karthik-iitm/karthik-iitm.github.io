---
title: Inverse and Determinant
pagetitle: Inverse and Determinant
---

Let $A$ be a square matrix of order $n$. $A$ is invertible if and only if $\text{det}(A)\neq0$.

------------------------------------------------------------------------

## Invertible $\implies$ Non-zero determinant

If $A$ is invertible, $A^{-1}$ exists. We have:

$$
\begin{aligned}
AA^{-1} & =I\\
\\\text{det}(A)\cdot\text{det}\left(A^{-1}\right) & =1
\end{aligned}
$$


Since the product of two real numbers is $1$, both of them have to be non-zero, establishing that $\text{det}(A)\neq0$. We can compute the determinant of $A^{-1}$ and it is $\cfrac{1}{\text{det}(A)}$.

## Non-zero determinant $\implies$ Invertible

We use the following identity:

$$
A \cdot \text{adj}(A)=\text{adj}(A)\cdot A=\text{det}(A)\cdot I
$$


where $\text{adj}(A)$ is the adjugate of $A$. If $\text{det}(A)\neq0$, we can divide the above identity uniformly by $\text{det}(A)$ to get:

$$
\begin{aligned}
A\cdot\left[\cfrac{1}{\text{det}(A)}\text{adj}(A)\right] & =\left[\cfrac{1}{\text{det}(A)}\text{adj}(A)\right]A=I
\end{aligned}
$$


We now have a matrix $B$ such that $AB=BA=I$. It follows that $A$ is invertible. Specifically, the inverse of $A$ can be represented as:

$$
A^{-1}=\cfrac{1}{\text{det}(A)}\text{adj}(A)
$$

