---
title: Question-9
pagetitle: Question-9
---

Suppose $A=\begin{bmatrix}4 & -1 & 3\\
2 & 0 & 1\\
3 & -2 & 0
\end{bmatrix}$. Find the determinant of the cofactor matrix of $A$.

------------------------------------------------------------------------

We have the following relation:

$$
A \cdot \text{adj}(A)=\text{adj}(A)\cdot A=\text{det}(A)\cdot I
$$


We also know that $\text{adj}(A)=C^{T}$, where $C$ is the cofactor matrix. Therefore, $|\text{adj}(A)|=\text{det}|C^{T}|=\text{det}|C|$. It is enough if we compute the determinant of the adjugate:

$$
\begin{aligned}
A\cdot\text{adj}(A) & =\text{det}(A)\cdot I\\
\implies\text{det}(A)\cdot\text{det}(\text{adj}(A)) & =\text{det}(A)^{3}\\
\implies\text{det}(\text{adj}(A)) & =\text{det}(A)^{2} & \text{det}(A)\neq0
\end{aligned}
$$


Let us now compute $\text{det}(A)$:

$$
\begin{aligned}
\begin{vmatrix}4 & -1 & 3\\
2 & 0 & 1\\
3 & -2 & 0
\end{vmatrix} & =4\times(0+2)+1(0-3)+3(-4-0)\\
 & =8-3-12\\
 & =-7
\end{aligned}
$$


So the determinant of the cofactor matrix is $49$.
